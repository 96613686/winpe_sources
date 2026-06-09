# CWdsDeviceControllerPacket::AddDevice(ushort const *)

- ea: `0x18000dcec`
- end: `0x18000dd28`
- name: `?AddDevice@CWdsDeviceControllerPacket@@QEAAKPEBG@Z`
- size: `60`
- prototype: `unsigned int(CWdsDeviceControllerPacket *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x180012910`
- `0x180014d58`

## string_xrefs

- `0x18000dd10`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerPacket::AddDevice(CWdsDeviceControllerPacket *this, unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  const char *v3; // rdx

  v2 = CControlPacket::AddString(this, (const char *)L"DeviceIdentifier", 0, -1, a2);
  ElValidateWin32(v2, v3, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0xFEu);
  return v2;
}

```

## disassembly

```asm
0x18000dcec  push    rbx
0x18000dcee  sub     rsp, 30h
0x18000dcf2  mov     [rsp+38h+var_18], rdx; unsigned __int16 *
0x18000dcf7  or      r9d, 0FFFFFFFFh; unsigned int
0x18000dcfb  lea     rdx, aDeviceidentifi
0x18000dd02  xor     r8d, r8d; unsigned __int16 *
0x18000dd05  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z
0x18000dd0a  mov     r9d, 0FEh; unsigned int
0x18000dd10  lea     r8, aBaseEcoWdsLibM_5
0x18000dd17  mov     ecx, eax; unsigned int
0x18000dd19  mov     ebx, eax
0x18000dd1b  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000dd20  mov     eax, ebx
0x18000dd22  add     rsp, 30h
0x18000dd26  pop     rbx
0x18000dd27  retn
```
