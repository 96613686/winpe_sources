# CWdsDeviceControllerPacket::AddDeviceListCount(ulong)

- ea: `0x18000dd30`
- end: `0x18000dddb`
- name: `?AddDeviceListCount@CWdsDeviceControllerPacket@@QEAAKK@Z`
- size: `171`
- prototype: `unsigned int __fastcall(CWdsDeviceControllerPacket *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x18000dd30`
- `0x18001284c`
- `0x180014d58`

## string_xrefs

- `0x18000dd4f`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x18000dd77`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x18000ddab`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerPacket::AddDeviceListCount(
        CWdsDeviceControllerPacket *this,
        const char *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v4; // esi
  unsigned int v6; // edi
  const char *v7; // rdx

  v4 = (unsigned int)a2;
  if ( !*((_DWORD *)this + 10)
    || (v6 = 5023,
        !ElValidateWin32(0x139Fu, a2, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x16Au)) )
  {
    if ( !*((_DWORD *)this + 8)
      || *((_DWORD *)this + 8) == v4
      || (v6 = 87,
          !ElValidateWin32(0x57u, a2, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x17Au)) )
    {
      v6 = CControlPacket::AddULONG(this, L"DeviceList.Count", 0, a4, v4);
      if ( !ElValidateWin32(v6, v7, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x181u) )
      {
        *((_DWORD *)this + 9) = v4;
        *((_DWORD *)this + 10) = 1;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000dd30  mov     [rsp+arg_0], rbx
0x18000dd35  mov     [rsp+arg_8], rsi
0x18000dd3a  push    rdi
0x18000dd3b  sub     rsp, 30h
0x18000dd3f  cmp     dword ptr [rcx+28h], 0
0x18000dd43  mov     esi, edx
0x18000dd45  mov     rbx, rcx
0x18000dd48  jz      short loc_18000DD67
0x18000dd4a  mov     edi, 139Fh
0x18000dd4f  lea     r8, aBaseEcoWdsLibM_5
0x18000dd56  mov     ecx, edi; unsigned int
0x18000dd58  mov     r9d, 16Ah; unsigned int
0x18000dd5e  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000dd63  test    eax, eax
0x18000dd65  jnz     short loc_18000DDC9
0x18000dd67  cmp     dword ptr [rbx+20h], 0
0x18000dd6b  jbe     short loc_18000DD8F
0x18000dd6d  cmp     [rbx+20h], esi
0x18000dd70  jz      short loc_18000DD8F
0x18000dd72  mov     edi, 57h ; 'W'
0x18000dd77  lea     r8, aBaseEcoWdsLibM_5
0x18000dd7e  mov     ecx, edi; unsigned int
0x18000dd80  mov     r9d, 17Ah; unsigned int
0x18000dd86  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000dd8b  test    eax, eax
0x18000dd8d  jnz     short loc_18000DDC9
0x18000dd8f  xor     r8d, r8d; unsigned __int16 *
0x18000dd92  mov     [rsp+38h+var_18], esi; unsigned int
0x18000dd96  lea     rdx, aDevicelistCoun
0x18000dd9d  mov     rcx, rbx; this
0x18000dda0  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z
0x18000dda5  mov     r9d, 181h; unsigned int
0x18000ddab  lea     r8, aBaseEcoWdsLibM_5
0x18000ddb2  mov     ecx, eax; unsigned int
0x18000ddb4  mov     edi, eax
0x18000ddb6  call    ?ElValidateWin32@@YAKKPEBD0K@Z
0x18000ddbb  test    eax, eax
0x18000ddbd  jnz     short loc_18000DDC9
0x18000ddbf  mov     [rbx+24h], esi
0x18000ddc2  mov     dword ptr [rbx+28h], 1
0x18000ddc9  mov     rbx, [rsp+38h+arg_0]
0x18000ddce  mov     eax, edi
0x18000ddd0  mov     rsi, [rsp+38h+arg_8]
0x18000ddd5  add     rsp, 30h
0x18000ddd9  pop     rdi
0x18000ddda  retn
```
