# Model Porting Guide Part 2

Clothings porting is a MUCH MORE complex process than anything else that was described previously.
Be ready that it will take a LOT of time and there's no guarantee that it will work eventually.
This guide recomendations WILL NOT allow you to make a colorable nor a physical clothes.
You have been warned.


## 1. Finding the most suitable "donor" model

Every movement is driven by the bones, and every bone influence is determined by a weights.
Weights is the crucial part when we're talking about the clothes porting. 
You can't just go straightforward and insert it into the game, it'll be just static model.
Without right armature and weights the game will not recognize imported model as the clothings.
So, we need to find and "borrow" them.

Open the model in Blender that you want to port. As example, I'll use Enterprise and her coat.

![screenshot](https://user-images.githubusercontent.com/52298587/182175591-01bdecaa-016b-4150-b110-cd93a38d39d0.png)

So, the model is here. Now we need to get rid from every part that is not her coat.

![screenshot](https://user-images.githubusercontent.com/52298587/182177338-302ca83b-261d-45c2-8f44-6ca6525cc42e.png)

Done. Open the game now.

![screenshot](https://user-images.githubusercontent.com/52298587/182177780-4397ab1c-96d9-40c8-bef1-d7204ef24203.png)

So we need to find a donor model that will allows us to transfer mesh weights.
But what model is the most suitable for this? Let's find out the clothes that have an almost the same shape as coat model.
It's the "Naked coat (no belt)" in my case. 

![screenshot](https://user-images.githubusercontent.com/52298587/182179822-9e5db838-e218-4005-84eb-496871ae471b.png)

So, what's next?

## 2. Extracting the model

Now we need to extract this model from the game. You need to open SB3Utility. 
If you're using BR from ScrewThisNoise, it's located in the game's folder called "[MODDING] Tools".

![screenshot](https://user-images.githubusercontent.com/52298587/182180750-bd2e5393-3de1-4b75-b83a-3803f7b82266.png)

Here's how it looks. But now we need to back to the game and find what acrhive contains that model that we want to extract.

![screenshot](https://user-images.githubusercontent.com/52298587/182181275-0063735a-8888-4de2-b84d-bb4cfc7c2ea5.png)

Find these clothes in that menu and click RMB on the active box. Click LMB on "Print item info".

![screenshot](https://user-images.githubusercontent.com/52298587/182181544-2ab4d6d9-665b-40e4-8aa3-1c25002c446c.png)

Now we have the mod's name and name of the asset. Locate this mod by any convenient tool and extract it in any convenient folder.

![screenshot](https://user-images.githubusercontent.com/52298587/182182337-f5f74f4d-9c28-4018-9d19-7c238d37d374.png)

Open SB3Utility again and locate the extracted AssetBundles, in my case I need to open "co_Mint_NakedCoat.unity3d".

![screenshot](https://user-images.githubusercontent.com/52298587/182183057-23e3cdca-6d49-4ec5-8c87-8a16fe370d5c.png)

Bundle is opened, now we're opening asset by double-clicking in the left menu.

![SB3UtilityGUI_20220801_182233_Iv2tKcIJOr](https://user-images.githubusercontent.com/52298587/182183572-14545fc7-5e19-41bc-9a14-ea17c2444e0b.png)

Now asset is opened and we need to extract the meshes. Switch to this tab.

![SB3UtilityGUI_20220801_182558_9FscKaQsQU](https://user-images.githubusercontent.com/52298587/182184259-21cdc16a-3dbc-4a14-9667-52fa8170ef18.png)

Choose one of these meshes and press Export.

![screenshot](https://user-images.githubusercontent.com/52298587/182184506-d83e512d-7bda-43b8-9823-7b563934df57.png)

Mesh is exported, you can find it near the unity3d file that you're opened in SB3Utility.

## 3. Adjusting position and transfering weights

Now you can open exported FBX in Blender.

![screenshot](https://user-images.githubusercontent.com/52298587/182185277-7e19997e-23da-4829-bdc6-55e27068387c.png)

The model imported, but where it is? 

![screenshot](https://user-images.githubusercontent.com/52298587/182185421-4042fba6-f293-4378-96c3-878c1d2b6c61.png)

Correct the scale by increasing it to "1.000" in all dimensions.

![screenshot](https://user-images.githubusercontent.com/52298587/182185703-78a58aae-18ff-4b9a-9af4-36791e408553.png)

Well, the next step will be the most difficult.

![screenshot](https://user-images.githubusercontent.com/52298587/182194634-2cf8d279-44f3-444b-84c6-7f1288bebacd.png)

We need to move Enterprise's coat closer to the imported model, in my case I'll also need to move the sleeves.

![screenshot](https://user-images.githubusercontent.com/52298587/182196646-b6b077bf-e884-4171-a863-d2291dedcd41.png)

Use the Pose Mode to move the model, it's the most convenient and accurate method.

![screenshot](https://user-images.githubusercontent.com/52298587/182197364-77ea2f70-3943-4f7a-9935-acafcf811f6e.png)

After some time it'll look like this. I had to scale down it a little bit, now I think it's ready.

![screenshot](https://user-images.githubusercontent.com/52298587/182197671-a839ab9f-88be-43e8-848c-43fc7fc07a62.png)

If you're think it's ready, Apply transformations in this menu.

![screenshot](https://user-images.githubusercontent.com/52298587/182197947-1946b3a8-3246-4d55-b3d7-b2e1b741d37c.png)

Now we're need to change the parent. 

![screenshot](https://user-images.githubusercontent.com/52298587/182198142-8a593eb3-c54e-4320-9a97-71213150e721.png)

You can delete the original armature.

![screenshot](https://user-images.githubusercontent.com/52298587/182198278-95a2eae4-046b-4d61-8411-a13c0186d20c.png)

And set the new parent. 

![screenshot](https://user-images.githubusercontent.com/52298587/182198570-d0ed4cbb-4f1c-4442-a49a-c29a1499a1e2.png)

Delete all vertex groups. 

![screenshot](https://user-images.githubusercontent.com/52298587/182198815-43192cab-4be6-4f54-b9a4-58842518404a.png)

Enter the Weight Paint mode and select both models. 

![screenshot](https://user-images.githubusercontent.com/52298587/182198910-78fbec7b-ba83-4a8c-9664-8bb724182080.png)

Open the Transfer Weights menu.

![screenshot](https://user-images.githubusercontent.com/52298587/182198985-cf4e2c9c-09c7-48b7-a804-da1068db5c3c.png)

This little tab will appear in the left bottom corner. Expand it to see more trasfer settings.

![screenshot](https://user-images.githubusercontent.com/52298587/182199215-c8a7199d-0569-4b0b-bdb0-542fb7088b0a.png)

Set the things like this.

![screenshot](https://user-images.githubusercontent.com/52298587/182199307-7cfca186-5db1-4b6d-84d6-456fa2e331b8.png)

Now you can see that the model was painted in diffrent colors, that means the weights was successfully transfered from the donor model.

![screenshot](https://user-images.githubusercontent.com/52298587/182199555-3e727b66-cefa-4814-8183-301211d67c61.png)

And now you can delete the original model, switch to the Pose Mode and see how it's moving. 
If you can drag clothes by moving bones than everything is okay and you can export this model.

![screenshot](https://user-images.githubusercontent.com/52298587/182346113-5182902d-c3d2-4863-8996-edaa6bd76b1e.png)

Clear your transforms befoure exporting.

![screenshot](https://user-images.githubusercontent.com/52298587/182346292-daeb54e9-dd1f-46da-92ec-b13c596fb433.png)

And don't forget to apply the general transforms that was done before.

## 3. Preparing the mod

Refer to the previous part of this guide to find out how to prepare textures and materials.
I'll skip this annoying part here.

![screenshot](https://user-images.githubusercontent.com/52298587/182347717-fde4a651-0f28-42a5-9271-79875d538b2c.png)

So the model is imported and already placed in the left window. We need to prepare it.
Expand the "cf_o_root" tree down to the latest children object.
You can see some objects called "n_top_a" or "n_bot_b".
These objects manage the state of clothes: 


n_top_a - top state 0

n_top_b - top state 1

n_bot_a - bottom state 0

n_bot_b - bottom state 1

State 0 - fully on

State 1 - half off


If you don't know what to do and you have only one object, just place it in "n_top_a" if it's the top clothes and if it's the bottom clothes in "n_bot_a".

![screenshot](https://user-images.githubusercontent.com/52298587/182349664-ba11b691-4827-4094-a7de-0034a1f83b37.png)

Move the first bone of the tree out of the Armature root bone.
And don't forget to delete the previous child object.

![screenshot](https://user-images.githubusercontent.com/52298587/182350035-5302df30-2207-47f9-b63e-ace8540ac251.png)

Set the Cha Clothes Component and expact the Rend Normal 01 list, set the object there as the only one in list.
Done. Now you can save your prefab and prepare the csv file.

Here's the example:

    [ID],5,1,[NAME],abdata,[PREFAB UNITY3D FILE],[PREFAB NAME],0,0,0,0,3,[BODYMASK UNITY3D FILE],[BODY MASK TEXTURE],0,0,0,0,0,0,0,0,0,0,0,[THUMBNAIL UNITY3D FILE],[THUMBNAIL]

Clothes category are STRICTLY depends on the digits in the first line of csv file. 
Top clothes are in "105" category, you can check this catergory in game by right clicking on the clothes boxes in the clothes menu.

Now we can assemble this mod.


