# CWdsDeviceControllerPacket::GetDeviceListCount(ulong *)

- ea: `0x18000df40`
- end: `0x18000df98`
- name: `?GetDeviceListCount@CWdsDeviceControllerPacket@@QEAAKPEAK@Z`
- size: `88`
- prototype: `unsigned int __fastcall(CWdsDeviceControllerPacket *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x18000df40`
- `0x1800129e4`
- `0x180014d58`

## string_xrefs

- `0x18000df71`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerPacket::GetDeviceListCount(
        CWdsDeviceControllerPacket *this,
        unsigned int *a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int ULONG; // ebx
  const char *v6; // rdx
  unsigned int v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  ULONG = CControlPacket::GetULONG(this, L"DeviceList.Count", 0, a4, &v8);
  if ( !ElValidateWin32(ULONG, v6, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x313u) )
    *a2 = v8;
  return ULONG;
}

```

## disassembly

```asm
0x18000df40  mov     [rsp+arg_0], rbx
0x18000df45  push    rdi
0x18000df46  sub     rsp, 30h
0x18000df4a  and     [rsp+38h+arg_10], 0
0x18000df4f  lea     rax, [rsp+38h+arg_10]
0x18000df54  mov     rdi, rdx
0x18000df57  mov     [rsp+38h+var_18], rax; unsigned int *
0x18000df5c  lea     rdx, aDevicelistCoun; "DeviceList.Count"
0x18000df63  xor     r8d, r8d; unsigned __int16 *
0x18000df66  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18000df6b  mov     r9d, 313h; unsigned int
0x18000df71  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000df78  mov     ecx, eax; unsigned int
0x18000df7a  mov     ebx, eax
0x18000df7c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000df81  test    eax, eax
0x18000df83  jnz     short loc_18000DF8B
0x18000df85  mov     ecx, [rsp+38h+arg_10]
0x18000df89  mov     [rdi], ecx
0x18000df8b  mov     eax, ebx
0x18000df8d  mov     rbx, [rsp+38h+arg_0]
0x18000df92  add     rsp, 30h
0x18000df96  pop     rdi
0x18000df97  retn
```
