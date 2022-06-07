# Greetings.

This is the first part in a series of guides on porting models into Koikatsu
By following this guides you will know how to:

- Find suitable models
- Import into Blender
- Prepare and adjust
- Export to Unity
- Correct textures and materials
- Apply physics
- And finally build a mod


## 1. Finding a model
TODO

## 2. Imporing into Blender
TODO

## 3. Preparing and adjusting model

Imported model will look like this.
![screenshot1](https://user-images.githubusercontent.com/52298587/172271644-1fefb24c-807c-4528-8eb5-dac6587581d0.png)

As example, I want to port only hair model into Koikatsu. So, how to separate imported model into parts?

### 3a. Mesh separation

Select your model via **LEFT CLICK**, it must have an orange outline after selection.

![screenshot2](https://user-images.githubusercontent.com/52298587/172272029-8f7c990f-a51d-493f-82fe-265c97f1f717.png)

Switch to **Modeling** tab

![screenshot3](https://user-images.githubusercontent.com/52298587/172272235-ddfeeb37-e34f-44b2-9def-c013ebd909d3.png)

As you can see, now our character's model is showed up as a polygons mesh.

![screenshot4](https://user-images.githubusercontent.com/52298587/172272326-c30e8cbd-28e5-4477-93a4-0d1656f3e91d.png)

### 3a-a. Separate by material

An easiest method to separate imported mesh mesh correctly.

![screenshot5](https://user-images.githubusercontent.com/52298587/172273072-24f84c6f-6ff7-4337-8578-7886d9efdfeb.png)

### 3b. Delete unneeded parts 

![screenshot6](https://user-images.githubusercontent.com/52298587/172273241-acb589c6-702e-4534-98f9-9f70473839ba.png)

Now our model is separated into many small parts (objects), it's up to you what's you want to save and what's you want to delete.

![screenshot7](https://user-images.githubusercontent.com/52298587/172273525-600bb542-b7a6-4bc7-a7d8-f2284388d51f.png)

Hide armature by clicking onto this eye icon, it'll be easy to clean up without an armature, and save it for later, we will need it for creating a physics in Unity.

![screenshot8](https://user-images.githubusercontent.com/52298587/172273977-66a1bcdf-4bd1-4763-b6ac-a2bbe324471a.png)

Select all unneeded parts, hold a **Left Shift** to add selection and press **Delete** onto your keyboard or **Right Click**>**Delete** to delete all selected parts.

### 3c. Join parts (objects)

![screenshot9](https://user-images.githubusercontent.com/52298587/172274495-e9c34851-a6aa-41d6-abc2-34ecebc50126.png)

All unneeded parts are gone. Perfect. But now we need to join some parts into complete shape. 

![screenshot10](https://user-images.githubusercontent.com/52298587/172274806-abeab563-4a0b-4b44-b484-b4afff1ae60b.png)

Choose two or more parts (like this) and press **Ctrl+J** onto your keyboard.

![screenshot11](https://user-images.githubusercontent.com/52298587/172274973-db6b67f8-d8c7-409a-afe1-ff949ac9a049.png)

Nice. Repeat this with all the parts you think should be one. 

### 3d. Clean up other trash

![screenshot12](https://user-images.githubusercontent.com/52298587/172275311-5270d373-2c07-4eca-9723-0970a3f64400.png)

Just delete this objects

![screenshot13](https://user-images.githubusercontent.com/52298587/172275510-85a840ff-035a-4586-81af-d05553cda169.png)

And by holding **Right Shift** drag-and-drop your object out of parent object. Delete this parent object after doing that.

![screenshot14](https://user-images.githubusercontent.com/52298587/172275842-f21ee7a2-3f3b-4569-9d95-e1570be2f14a.png)

Select mesh objects and delete **Blend Shape Keys** on all of them.

![screenshot15](https://user-images.githubusercontent.com/52298587/172277705-12335d51-5287-41cc-b92b-b5b840a895dc.png)

Switch back to Layout tab

![screenshot16](https://user-images.githubusercontent.com/52298587/172277776-a64aaa55-fd3e-4ea5-9321-bf99b5e61c9d.png)

And select **Edit** mode

![screenshot17](https://user-images.githubusercontent.com/52298587/172277846-9994f950-2f59-4e70-aca2-5961496a6742.png)

This is a mess. And we need to clean this out.

![screenshot18](https://user-images.githubusercontent.com/52298587/172277939-082a84d6-c690-40be-a597-7e06f68b6dce.png)

Find a part of armature that is looks like a parent for all other hair parts.

![screenshot19](https://user-images.githubusercontent.com/52298587/172278180-5149554d-1d35-49e4-a8fc-9828bb292147.png)

Choose this option to select all child parts of armature and hit **Ctrl+I**, that will invert selection. Hit **Delete** and choose **Bones**.
Et voila. All body boned are gone. 

![screenshot20](https://user-images.githubusercontent.com/52298587/172278555-47353281-0766-4695-be3c-f27974d5d44e.png)

Delete other unneeded bones such as **Eyes** or **Tongue** if they are present on the imported model.

### 3e. Objects and materials renaming

![screenshot](https://user-images.githubusercontent.com/52298587/172276121-086f785b-7e13-4ad0-a51a-76670a51ec49.png)

Now you can rename your objects. Select and hit **F2** onto your keyboard. Rename it as you like.

![screenshot](https://user-images.githubusercontent.com/52298587/172276522-dba7da1d-bda4-4622-b0aa-14f91862e4a4.png)

If your models bones are named in that way you can't understand it, feel free to rename them. As example, if bones names are on Japanese, translate into English. 

![screenshot](https://user-images.githubusercontent.com/52298587/172276923-2b05194c-6d81-483e-b061-651bf4ca95eb.png)

And don't forget rename model's materials. It's very important to follow some naming template because Unity will place all of the materials into one folder.
It'll be very confusing to find the right material later.

## 4. Export to Unity
