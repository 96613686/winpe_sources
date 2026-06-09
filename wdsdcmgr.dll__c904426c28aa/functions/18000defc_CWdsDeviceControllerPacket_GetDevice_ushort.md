# CWdsDeviceControllerPacket::GetDevice(ushort * *)

- ea: `0x18000defc`
- end: `0x18000df38`
- name: `?GetDevice@CWdsDeviceControllerPacket@@QEAAKPEAPEAG@Z`
- size: `60`
- prototype: `unsigned int(CWdsDeviceControllerPacket *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x180012ac8`
- `0x180014d58`

## string_xrefs

- `0x18000df20`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerPacket::GetDevice(CWdsDeviceControllerPacket *this, unsigned __int16 **a2)
{
  unsigned int String; // ebx
  const char *v3; // rdx

  String = CControlPacket::GetString(this, L"DeviceIdentifier", 0, 0xFFFFFFFF, a2);
  ElValidateWin32(String, v3, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x2BBu);
  return String;
}

```

## disassembly

```asm
0x18000defc  push    rbx
0x18000defe  sub     rsp, 30h
0x18000df02  mov     [rsp+38h+var_18], rdx; unsigned __int16 **
0x18000df07  or      r9d, 0FFFFFFFFh; unsigned int
0x18000df0b  lea     rdx, aDeviceidentifi; "DeviceIdentifier"
0x18000df12  xor     r8d, r8d; unsigned __int16 *
0x18000df15  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x18000df1a  mov     r9d, 2BBh; unsigned int
0x18000df20  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000df27  mov     ecx, eax; unsigned int
0x18000df29  mov     ebx, eax
0x18000df2b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000df30  mov     eax, ebx
0x18000df32  add     rsp, 30h
0x18000df36  pop     rbx
0x18000df37  retn
```
