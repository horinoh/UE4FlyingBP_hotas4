# UE4FlyingBP_hotas4

## 適用の仕方 (How to apply)
- hotas4 をつなぐ (Connect hotas4)
- New Project - Blueprint - Flying のテンプレートを選択してプロジェクトを作る (New Project - Blueprint - Select Flying template and create project)
- Config/DefaultInput.ini を上書きする (Overwrite Config/DefaultInput.ini)
- Edit - Plugins - Input Devices - Windows RawInput を有効にする (Edit - Plugins - Input Devices - Enable Windows RawInput)

## やったこと (What I have done)
- DefaultInput.ini
    - Raw Input の設定を追加した (Added Raw Input settings)
    - MoveUp, MoveRight, Thrust に GenericUSBController_Axis<N> を追加 (Added GenericUSBController_Axis<N> to MoveUp, MoveRight, Thrust)
~~~
[/Script/RawInput.RawInputSettings]
+DeviceConfigurations=(VendorID="0x044F",ProductID="0xB67C",AxisProperties=((Key=GenericUSBController_Axis1,bInverted=True,Offset=0.500000),(Key=GenericUSBController_Axis2,Offset=-0.500000),(Key=GenericUSBController_Axis3,Offset=-0.500000),(bEnabled=False,Key=GenericUSBController_Axis4),(bEnabled=False,Key=GenericUSBController_Axis5),(bEnabled=False,Key=GenericUSBController_Axis6),(Key=GenericUSBController_Axis7,Offset=-0.500000),(Key=GenericUSBController_Axis8,bInverted=True,Offset=0.500000)),ButtonProperties=((Key=GenericUSBController_Button1),(Key=GenericUSBController_Button2),(Key=GenericUSBController_Button3),(Key=GenericUSBController_Button4),(Key=GenericUSBController_Button5),(Key=GenericUSBController_Button6),(Key=GenericUSBController_Button7),(Key=GenericUSBController_Button8),(Key=GenericUSBController_Button9),(Key=GenericUSBController_Button10),(Key=GenericUSBController_Button11),(Key=GenericUSBController_Button12),(Key=GenericUSBController_Button13),(Key=GenericUSBController_Button14),(Key=GenericUSBController_Button15),(Key=GenericUSBController_Button16),(Key=GenericUSBController_Button17),(Key=GenericUSBController_Button18),(Key=GenericUSBController_Button19),(Key=GenericUSBController_Button20)))
~~~
~~~
[/Script/Engine.InputSettings]
...
+AxisMappings=(AxisName="MoveUp",Scale=2.000000,Key=GenericUSBController_Axis1)
+AxisMappings=(AxisName="MoveRight",Scale=2.000000,Key=GenericUSBController_Axis2)
+AxisMappings=(AxisName="Thrust",Scale=2.000000,Key=GenericUSBController_Axis8)
~~~
