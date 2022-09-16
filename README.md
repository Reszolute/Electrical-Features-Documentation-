# Electrical Features Documentation
GTAV electrical features that are used commonly in the powerplant. When touched you will get an electric type effect and you will ragdoll on the ground. When the object is shot it has sparks coming from point of impact. Most of this is editable.

(This is also all in chronological order) 

# Collision Materials
This is what collision materials your object should use

For the Electrocution effect

![unknown](https://user-images.githubusercontent.com/113695236/190647058-9e51f46c-8b75-4039-8093-b4a555286666.png)

For the Spark effect when shot

![unknown2](https://user-images.githubusercontent.com/113695236/190647189-45d38595-7c73-4c04-af61-0d0bee0510c5.png)

# Collision Material Flags
The material flags shouldn't matter too much. They of course need all the proper flags so the collision works properly. I have noticed that when using planes the VFX doesn't work as properly. So try making the plane thicker.

![Screenshot 2022-09-16 151517](https://user-images.githubusercontent.com/113695236/190647456-d6a7e810-965b-48bb-926c-d9c02f5ddb76.png)

# Bone part (3DS)
The object you have will need a bone. This is MANDATORY or else the object wont work properly.

The bone that you will create via GIMS will need these properties.

![image](https://user-images.githubusercontent.com/113695236/190650640-fd859449-97db-4318-b4cb-28200ef5ba39.png)


This is what your hierarchy should look like. The model mesh and the collision composite are parented to the bone. And the bone is parented to the main model.

![image](https://user-images.githubusercontent.com/113695236/190650375-bbc614e6-ae47-41eb-a02b-4b41a0af8e16.png)

# Bone part (Blender)
The object you have will need a bone. This is MANDATORY or else the object wont work properly.

You will need to create an Armature by pressing Shift + A and clicking armature. 

On blender the armature doesn't need any custom properties. 

Your hierarchy should look like this.

![image](https://user-images.githubusercontent.com/113695236/190651142-8b8d983a-9a74-4371-848a-b20c521b7feb.png)

# Extensions
 This needs to be added in the YTYP's extension.
 
 Be aware some there are some parts that have to be be edited for this to work properly.
``` <extensions>
        <Item type="CExtensionDefAudioEmitter">
          <name>prop_sub_trans_02a</name>
          <offsetPosition x="0.00000000" y="0.00000000" z="0.00000000"/>
          <offsetRotation x="0.00000000" y="0.00000000" z="0.00000000" w="1.00000000"/>
          <effectHash value="2463218603"/>
        </Item>
        <Item type="CExtensionDefParticleEffect">
          <name>REPLACE_MODEL_NAME</name>
          <offsetPosition x="0.09973145" y="-0.01536560" z="2.23046500"/>
          <offsetRotation x="0.00000000" y="0.00000000" z="0.00000000" w="1.00000000"/>
          <fxName>sht_sparking_wires</fxName>
          <fxType value="2"/>
          <boneTag value="0"/>
          <scale value="1.00000000"/>
          <probability value="100"/>
          <flags value="0"/>
          <color value="0xFFFFFFFF"/>
        </Item>
      </extensions>
```
# Archetype Flag Value
In the YTYP a flag value needs to be specified on said object. 

You will find this line at the top of the objects YTYP's 
```
<flags value="0"/>
```
The value needs to be replaced with this value
```
537002016
```
So it should look like this
```    
<flags value="537002016"/>
```    

# CExtensionDefAudioEmitter
This is where you define the model name so that when you go in-game you can hear a humming sound as you usually would hear from objects that have electric current.

``` 
<Item type="CExtensionDefAudioEmitter">
          <name>purge_electrify</name>
          <offsetPosition x="0.00000000" y="0.00000000" z="0.00000000"/>
          <offsetRotation x="0.00000000" y="0.00000000" z="0.00000000" w="0.00000000"/>
          <effectHash value="2463218603"/>
        </Item>
 ``` 

# CExtensionDefParticleEffect
This is where you define the prop name and you could also change the FX particle that appears when shooting the object.
 
 ``` 
<Item type="CExtensionDefParticleEffect">
          <name>purge_electrify</name>
          <offsetPosition x="0.0" y="-0.0" z="0.0"/>
          <offsetRotation x="0.00000000" y="0.00000000" z="0.00000000" w="0.00000000"/>
          <fxName>sht_sparking_wires</fxName>
          <fxType value="2"/>
          <boneTag value="0"/>
          <scale value="1.00000000"/>
          <probability value="100"/>
          <flags value="0"/>
          <color value="0xFFFFFFFF"/>
        </Item>
 ``` 
 
 For the FX particle this is what needs to be changed. A wbesite that can be used to specify which particle you want is this one: https://particles.altv.mp/
  
  ``` 
 <fxName>sht_sparking_wires</fxName>
  ``` 
 
 
This is the percentage that you want the effect to appear. If set to 0 the particle will never appear when the object is shot or triggered.

``` 
 <probability value="100"/>
``` 

# YTYP 
This is rougly what the whole YTYP should look like (Per object of course)
```  
<?xml version="1.0" encoding="UTF-8" standalone="no"?>
<CMapTypes>
  <extensions/>
  <archetypes>
    <Item type="CBaseArchetypeDef">
      <lodDist value="106.30200000"/>
      <flags value="537002016"/>
      <specialAttribute value="0"/>
      <bbMin x="-2.61309900" y="-2.45158400" z="-1.63556800"/>
      <bbMax x="2.61309900" y="2.45158400" z="1.63556800"/>
      <bsCentre x="0.00000000" y="0.00000000" z="0.00000000"/>
      <bsRadius value="3.93874000"/>
      <hdTextureDist value="69.09629000"/>
      <name>purge_electrify</name>
      <textureDictionary>purge_electrify</textureDictionary>
      <clipDictionary/>
      <drawableDictionary/>
      <physicsDictionary>purge_electrify</physicsDictionary>
      <assetType>ASSET_TYPE_DRAWABLE</assetType>
      <assetName>purge_electrify</assetName>
      <extensions>
        <Item type="CExtensionDefAudioEmitter">
          <name>purge_electrify</name>
          <offsetPosition x="0.00000000" y="0.00000000" z="0.00000000"/>
          <offsetRotation x="0.00000000" y="0.00000000" z="0.00000000" w="0.00000000"/>
          <effectHash value="2463218603"/>
        </Item>
        <Item type="CExtensionDefParticleEffect">
          <name>purge_electrify</name>
          <offsetPosition x="0.0" y="-0.0" z="0.0"/>
          <offsetRotation x="0.00000000" y="0.00000000" z="0.00000000" w="0.00000000"/>
          <fxName>sht_sparking_wires</fxName>
          <fxType value="2"/>
          <boneTag value="0"/>
          <scale value="1.00000000"/>
          <probability value="100"/>
          <flags value="0"/>
          <color value="0xFFFFFFFF"/>
        </Item>
      </extensions>
    </Item>
  </archetypes>
  <name>models</name>
  <dependencies/>
  <compositeEntityTypes/>
</CMapTypes>
```  

