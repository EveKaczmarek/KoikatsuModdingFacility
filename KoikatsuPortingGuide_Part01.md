# Model Porting Guide Part 1

Greetings. This is the first part in a series of guides on porting models into Koikatsu
By following these guides you will know how to:

- Find suitable models
- Import into Blender
- Prepare and adjust
- Export to Unity
- Correct textures and materials
- Apply physics
- And finally, build a mod


## 1. Finding a model
TODO

## 2. Importing into Blender
TODO

## 3. Preparing and adjusting the model

The imported model will look like this.
![screenshot1](https://user-images.githubusercontent.com/52298587/172271644-1fefb24c-807c-4528-8eb5-dac6587581d0.png)

For example, I want to port only hair models into Koikatsu. So, how to separate the imported model into parts?

### 3a. Mesh separation

Select your model with the **LEFT CLICK**, it must have an orange outline after selection.

![screenshot2](https://user-images.githubusercontent.com/52298587/172272029-8f7c990f-a51d-493f-82fe-265c97f1f717.png)

Switch to **Modeling** tab

![screenshot3](https://user-images.githubusercontent.com/52298587/172272235-ddfeeb37-e34f-44b2-9def-c013ebd909d3.png)

As you can see, now our character's model is shown up as a polygons mesh.

![screenshot4](https://user-images.githubusercontent.com/52298587/172272326-c30e8cbd-28e5-4477-93a4-0d1656f3e91d.png)

### 3a-a. Separate by material

The easiest method to separate imported mesh correctly.

![screenshot5](https://user-images.githubusercontent.com/52298587/172273072-24f84c6f-6ff7-4337-8578-7886d9efdfeb.png)

### 3b. Delete unneeded parts 

![screenshot6](https://user-images.githubusercontent.com/52298587/172273241-acb589c6-702e-4534-98f9-9f70473839ba.png)

Now our model is separated into many small parts (objects), it's up to you what you want to save and what you want to delete.
Switch back to the **Layout** tab.

![screenshot7](https://user-images.githubusercontent.com/52298587/172273525-600bb542-b7a6-4bc7-a7d8-f2284388d51f.png)

Hide the armature by clicking on this eye icon, it'll be easy to clean up without an armature, and save it for later, we will need it for creating a physics in Unity.

![screenshot8](https://user-images.githubusercontent.com/52298587/172273977-66a1bcdf-4bd1-4763-b6ac-a2bbe324471a.png)

Select all unneeded parts, hold a **Left Shift** to add a selection, and press **Delete** onto your keyboard or **Right Click**>**Delete** to delete all selected parts.

![screenshot](https://user-images.githubusercontent.com/52298587/172954997-290d4a50-90f3-4e29-942f-52b846dc4973.png)

If some parts of the model still need to be separated, switch to **Modeling** tab.

![dhLdKi6aPR](https://user-images.githubusercontent.com/52298587/172955387-f573cf8b-c9a4-4477-ac36-ae4d8cbd9433.png)

Select a few dots of part that you want to separate further and hit **CTRL+L**

![h1KVtvBdkB](https://user-images.githubusercontent.com/52298587/172955649-b3952af6-0631-4283-8019-6073a984fe02.png)

Now all you need is separate this part by selection. Repeat this until done.

### 3c. Join parts (objects)

![screenshot9](https://user-images.githubusercontent.com/52298587/172274495-e9c34851-a6aa-41d6-abc2-34ecebc50126.png)

All unneeded parts are gone. Perfect. But now we need to join some parts into complete shape. 

![screenshot10](https://user-images.githubusercontent.com/52298587/172274806-abeab563-4a0b-4b44-b484-b4afff1ae60b.png)

Choose two or more parts (like this) and press **Ctrl+J** onto your keyboard.

![screenshot11](https://user-images.githubusercontent.com/52298587/172274973-db6b67f8-d8c7-409a-afe1-ff949ac9a049.png)

Nice. Repeat this with all the parts you think should be one. 

### 3d. Clean up other trash

![screenshot12](https://user-images.githubusercontent.com/52298587/172275311-5270d373-2c07-4eca-9723-0970a3f64400.png)

Just delete this objects by clicking on them with the **RIGHT CLICK** and choosing **Delete Hierarchy**

![screenshot13](https://user-images.githubusercontent.com/52298587/172275510-85a840ff-035a-4586-81af-d05553cda169.png)

And by holding **Right Shift** drag and drop your object out of the parent object. Delete this parent object after doing that.
Do this only if the parent object is present, skip if the armature is already on top of the list.

![screenshot14](https://user-images.githubusercontent.com/52298587/172275842-f21ee7a2-3f3b-4569-9d95-e1570be2f14a.png)

Select mesh objects and delete **Blend Shape Keys** on all of them.

![screenshot15](https://user-images.githubusercontent.com/52298587/172277705-12335d51-5287-41cc-b92b-b5b840a895dc.png)

Switch back to **Layout** tab

![screenshot16](https://user-images.githubusercontent.com/52298587/172277776-a64aaa55-fd3e-4ea5-9321-bf99b5e61c9d.png)

And select **Edit** mode

![screenshot17](https://user-images.githubusercontent.com/52298587/172277846-9994f950-2f59-4e70-aca2-5961496a6742.png)

This is a mess. And we need to clean this out.

![screenshot18](https://user-images.githubusercontent.com/52298587/172277939-082a84d6-c690-40be-a597-7e06f68b6dce.png)

Find a part of the armature that looks like a parent for all other hair parts.

![screenshot19](https://user-images.githubusercontent.com/52298587/172278180-5149554d-1d35-49e4-a8fc-9828bb292147.png)

Choose this option to select all child parts of the armature and hit **Ctrl+I**, which will invert the selection. Hit **Delete** and choose **Bones**.

![5XkfkLCVjY](https://user-images.githubusercontent.com/52298587/172956826-5af39cb0-e263-4244-a681-a61175bc5dfc.png)

Now we need to delete hidden bones that are completely useless outside MMD. Open this menu and switch layers.

![9W0yPKT89D](https://user-images.githubusercontent.com/52298587/172956902-9e2717cf-b705-4d31-8a59-ee2ec654e003.png)

Now you can see these bones, you need to get rid of them. Switch to another hidden layer when bones will be deleted. Don't forget to switch back to the main layer.

Et voila. All body bones are gone. 

![screenshot20](https://user-images.githubusercontent.com/52298587/172278555-47353281-0766-4695-be3c-f27974d5d44e.png)

Delete other unneeded bones such as **Eyes** or **Tongue** if they are present on the imported model.

### 3e. Objects and materials renaming

![screenshot](https://user-images.githubusercontent.com/52298587/172276121-086f785b-7e13-4ad0-a51a-76670a51ec49.png)

Now you can rename your objects. Select and hit **F2** on your keyboard. Rename it as you like.

![screenshot](https://user-images.githubusercontent.com/52298587/172276522-dba7da1d-bda4-4622-b0aa-14f91862e4a4.png)

If your models' bones are named in that way you can't understand it, feel free to rename them. For example, if bones' names are in Japanese, translate them into English. 

![screenshot](https://user-images.githubusercontent.com/52298587/172276923-2b05194c-6d81-483e-b061-651bf4ca95eb.png)

And don't forget to rename the model materials. 

You can do this by the **Left Double Click** on the name.

It's very important to follow some naming template because Unity will place all of the materials into one folder.
It'll be very confusing to find the right material later.

## 4. Export to Unity

### 4a. Exporting FBX

![ZzP6BfxXU5](https://user-images.githubusercontent.com/52298587/172958372-52242e1a-31e9-4154-9ce3-6bc45f146ba1.png)

Now this model is ready to be exported. 

![l6dTvv9Ecw](https://user-images.githubusercontent.com/52298587/172958451-6be94f1a-e457-4fd4-babf-b8fd77aa3f20.png)

Open this menu and choose to export to **FBX**.

![WlqdaI0llM](https://user-images.githubusercontent.com/52298587/172958661-ce3f6aed-5ce7-418e-b4a2-a5d4ded723ea.png)

Set this exporting option in the newly opened window, choose exporting path, and hit **Export FBX**.
Do not close Blender, soon we will be back there soon.

### 4b. Importing model to Unity

![dwI5UrY5UC](https://user-images.githubusercontent.com/52298587/172958855-69d10a04-216c-4643-9a7b-94469b5aaaac.png)

Open the modding project and wait, Unity will load exported model, it may take some time.

![KJzjXXC7Pl](https://user-images.githubusercontent.com/52298587/172959482-f5fb434e-756f-4ea4-9526-ddaa92ad1ee8.png)

Open the mod folder and drag and drop the model to the left window.

### 4c. Preparing a prefab

![DgZMuElO7g](https://user-images.githubusercontent.com/52298587/172959896-b487f7a5-debb-4ec8-b0cd-15d0ca6a019e.png)

Expand the model hierarchy and delete **Animator** component.

![3NJ33qNTYt](https://user-images.githubusercontent.com/52298587/172960170-b066cb07-c981-4e1e-88d9-34d587dc938b.png)

Hit on the model with the **Right Click** and choose **Create Empty**

![928YRj4FEx](https://user-images.githubusercontent.com/52298587/172960412-7d6a15e5-d7f0-429f-ab58-abd131bb830e.png)

Rename the empty object to **N_move**. 

![U1tG3NBc7K](https://user-images.githubusercontent.com/52298587/172960539-f8d2edb6-c75d-462c-9c7d-06570a418b9d.png)

Move **N_move** object to the top and drag **armature** into it.

![XnFKijjRMC](https://user-images.githubusercontent.com/52298587/172960895-3129d0d0-8d09-459e-a867-e109e4ae8bfe.png)

Unity will warn you about some "breakages", just press **Continue**.

![5ogNZ5u7RE](https://user-images.githubusercontent.com/52298587/172961214-3e701656-43aa-46a7-bbbe-24a197155a01.png)

Select the objects under the armature and set **Update when offscreen** in the right window.

![hjd8g1TMtK](https://user-images.githubusercontent.com/52298587/172961356-ac045f6b-1307-459a-a80a-a60f8f7ec261.png)

You can rename the object if you want to. 

![4d3EctxWcC](https://user-images.githubusercontent.com/52298587/172961529-b0644734-aea6-44aa-9b9d-415123e6f142.png)

Now you can drag and drop the object into **Prefab** folder, all further settings must be applied to **Prefab** only.

### 4d. Correcting textures and materials

![HqDuiXDNdD](https://user-images.githubusercontent.com/52298587/172962337-8407a86a-24ec-45bd-9247-9a1d98b97508.png)

Open **Materials** folder. As you can see, the model is textureless and strange looking. Blender doesn't export textures and materials, we need to import textures manually. Find the folder where the original model is located, and find the textures inside it.

![XdO9mxEzIr](https://user-images.githubusercontent.com/52298587/172963235-1c0593c5-7255-407e-b4a6-cb3c04ca4622.png)

Next, open **Koikatsu** folder, **[MODDING] Tools**, **KK Image Converter** and open **KKImageConverter.exe**.

![hA72GFcJJn](https://user-images.githubusercontent.com/52298587/172963413-ff3f93fc-91ba-4436-befa-38186be1a8e3.png)

Choose **output folder**, for example, your Desktop or anything else, drag-and-drop model texture onto this window and hit **Convert all**.
Close the window when the conversion is completed.

![QpEMOwQiJm](https://user-images.githubusercontent.com/52298587/172963865-e1da320a-123b-4616-88d6-3fae16276a33.png)

Locate the converted texture(s) and drop them into the Textures folder.

![Unity_20220610_025710_pQSeT1Q3lf](https://user-images.githubusercontent.com/52298587/172963971-9af25da2-d5ec-427a-8d1f-b309e7cd752c.png)

Select texture(s) and set these parameters.

**sRGB (Color Texture) - TRUE**

**Compression - High Quality**

If your texture(s) are containing alpha channel (transparency), set **Alpha Is Transparency**.

![WmqpqZg1Do](https://user-images.githubusercontent.com/52298587/172964757-a58a3494-70f8-420a-9695-dc36079ce82d.png)

Open Blender again and open object material settings. Now you can see which texture belongs to which material. Refer to these settings when you will set textures in Unity.

![dTaPE1ganU](https://user-images.githubusercontent.com/52298587/172965201-bb21f60c-bf15-49a0-af6a-6babcfad91bf.png)

Open the Materials folder in Unity and set shaders. For hair, it will be **Shader Forge > main_hair** and **Shader Forge > main_item_studio** for accessories.

![q8qaf3dMHW](https://user-images.githubusercontent.com/52298587/172965562-2bde6b93-39e0-4602-af29-b4d8810dee54.png)

Click on the small rectangle to the right of **ShadowColor** and set **V** to 230.

![EMCmydjLRR](https://user-images.githubusercontent.com/52298587/172965840-d54d81ff-f850-4188-a8d5-b0604a30e477.png)

Set textures by clicking on **Select** button to the right of **MainTex**.

![SEZbmeg0Zz](https://user-images.githubusercontent.com/52298587/172971010-933bacb6-0f58-42ad-b6e3-4bf8922ac4db.png)

Choose the armature and change position, the model should be somewhere around the floor level.

![pLgnmTFuho](https://user-images.githubusercontent.com/52298587/172971330-50df4572-92ec-43de-956a-827ed5441c26.png)

And be sure that model is not so big, use this picture as a reference to the model scale.

### 4e. Setting mod components

![XrPzAR7Bj2](https://user-images.githubusercontent.com/52298587/172966101-f75ea2e4-ca7f-40fb-bcb4-687ab7a81b76.png)

Select **prefab** and add the following components:

**Cha Accessory Component**

**Dynamic Bone**

You can find them in the opened menu by simply typing the component name on the keyboard.

![Unity_20220610_032603_9AURcqWCsS](https://user-images.githubusercontent.com/52298587/172966531-f229f644-5543-45e0-82ac-81a0dd7f7109.png)

Count the number of objects, set this amount to **Size** (in my case it's 5), and distribute them by elements. Click on the small dot to the right of **None** to open a menu.

## 5. Creating hair physics

*WIP*

![Unity_20220610_045116_3KoN3e305Z](https://user-images.githubusercontent.com/52298587/172974229-87393a52-dba5-4708-8e7b-48f247436517.png)

Expand the model armature and find the first bone that is the parent for others. Set this bone to the **Root Bone** in **Dynamic Bones** component.

Set the following settings:

**Damping - 0.2**

**Elasticity - 0.1**

**Stiffness - 0.1**

**Inert - 0**

**Radius - 0**

**Force - -0.001**

**Colliders - 10**

![Unity_20220610_045156_kIaRRqAVHO](https://user-images.githubusercontent.com/52298587/172974289-316b8c90-6bd0-4a20-a6a4-0b173304a284.png)

Click on the rectangle to the right of **Elasticity Distrib**, and create two dots in the new window by double-clicking. Right-click on the first dot, click on **Edit key...**, and set **Time** to **0** and **Value** to **1**. Do the same to the second but set **Time** to **1** and **Value** to **0**. 

![i0U2eb9T3n](https://user-images.githubusercontent.com/52298587/172968249-bcf70a79-ffc2-4d4f-a1e6-8f72b661a754.png)

Now you can see the sinusoid that is going from **0:1** to **1:0**. Click on the small gear in the left corner and click on save. Now you can use this sinusoid for another **Distrib** option. 

![LHa5laehle](https://user-images.githubusercontent.com/52298587/172968523-a655f128-e6f9-4e7f-bd4d-288d75c97d99.png)

Set only on **Elasticity Distrib** and **Stiffness Distrib**.

These physics settings are pretty general and you can achieve a nice motion by using them.

![fvYflWl1jm](https://user-images.githubusercontent.com/52298587/172968887-96fbcbc0-20cf-43c2-8fe9-ba83b61c8665.png)

Now you can save your progress in prefab settings.

