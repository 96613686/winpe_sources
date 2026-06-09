# CWdsDeviceControllerPacket::GetMetadata(ushort const *,CWdsMetadata *)

- ea: `0x18000dde4`
- end: `0x18000def6`
- name: `?GetMetadata@CWdsDeviceControllerPacket@@QEAAKPEBGPEAVCWdsMetadata@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(CWdsDeviceControllerPacket *this, const unsigned __int16 *, struct CWdsMetadata *, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002bd8`
- `0x180003398`
- `0x18000dfa0`

## callees

- `0x18000ba74`
- `0x18000dde4`
- `0x1800129e4`
- `0x180012ac8`
- `0x180014d58`
- `0x1800150b8`

## string_xrefs

- `0x18000de2a`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x18000de73`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`
- `0x18000de9d`: `base\eco\wds\lib\metadata\com\wdsdevicecontrollerpacket.cpp`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerPacket::GetMetadata(
        CWdsDeviceControllerPacket *this,
        const unsigned __int16 *a2,
        struct CWdsMetadata *a3,
        unsigned int a4)
{
  unsigned int ULONG; // esi
  const char *v8; // rdx
  unsigned int v9; // edi
  const char *v10; // rdx
  unsigned int v11; // eax
  void *v12; // rbx
  const char *v13; // rdx
  void *Block; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v16; // [rsp+78h] [rbp+20h] BYREF

  Block = 0;
  v16 = 0;
  ULONG = CControlPacket::GetULONG(this, a2, L"Count", a4, &v16);
  if ( !ElValidateWin32(ULONG, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x225u) )
  {
    v9 = 0;
    if ( v16 )
    {
      do
      {
        ULONG = CControlPacket::GetString(this, a2, L"Entry", v9, (unsigned __int16 **)&Block);
        v11 = ElValidateWin32(ULONG, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x22Du);
        v12 = Block;
        if ( v11 )
          break;
        ULONG = CWdsMetadata::AppendEntry(a3, (const unsigned __int16 *)Block);
        if ( ElValidateWin32(ULONG, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdsdevicecontrollerpacket.cpp", 0x230u) )
          break;
        if ( v12 )
        {
          operator delete(v12);
          v12 = 0;
          Block = 0;
        }
        ++v9;
      }
      while ( v9 < v16 );
      if ( v12 )
        operator delete(v12);
    }
  }
  return ULONG;
}

```

## disassembly

```asm
0x18000dde4  mov     rax, rsp
0x18000dde7  mov     [rax+8], rbx
0x18000ddeb  mov     [rax+10h], rsi
0x18000ddef  mov     [rax+18h], rdi
0x18000ddf3  push    r12
0x18000ddf5  push    r14
0x18000ddf7  push    r15
0x18000ddf9  sub     rsp, 40h
0x18000ddfd  and     qword ptr [rax-28h], 0
0x18000de02  mov     r12, r8
0x18000de05  and     dword ptr [rax+20h], 0
0x18000de09  lea     rax, [rax+20h]
0x18000de0d  lea     r8, aCount; "Count"
0x18000de14  mov     [rsp+58h+var_38], rax; unsigned int *
0x18000de19  mov     r14, rdx
0x18000de1c  mov     r15, rcx
0x18000de1f  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18000de24  mov     r9d, 225h; unsigned int
0x18000de2a  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000de31  mov     ecx, eax; unsigned int
0x18000de33  mov     esi, eax
0x18000de35  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000de3a  test    eax, eax
0x18000de3c  jnz     loc_18000DEDA
0x18000de42  xor     edi, edi
0x18000de44  cmp     [rsp+58h+arg_18], edi
0x18000de48  jbe     loc_18000DEDA
0x18000de4e  lea     rax, [rsp+58h+Block]
0x18000de53  mov     r9d, edi; unsigned int
0x18000de56  lea     r8, aEntry; "Entry"
0x18000de5d  mov     [rsp+58h+var_38], rax; unsigned __int16 **
0x18000de62  mov     rdx, r14; unsigned __int16 *
0x18000de65  mov     rcx, r15; this
0x18000de68  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x18000de6d  mov     r9d, 22Dh; unsigned int
0x18000de73  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000de7a  mov     ecx, eax; unsigned int
0x18000de7c  mov     esi, eax
0x18000de7e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000de83  mov     rbx, [rsp+58h+Block]
0x18000de88  test    eax, eax
0x18000de8a  jnz     short loc_18000DECD
0x18000de8c  mov     rdx, rbx; unsigned __int16 *
0x18000de8f  mov     rcx, r12; this
0x18000de92  call    ?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendEntry(ushort const *)
0x18000de97  mov     r9d, 230h; unsigned int
0x18000de9d  lea     r8, aBaseEcoWdsLibM_5; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000dea4  mov     ecx, eax; unsigned int
0x18000dea6  mov     esi, eax
0x18000dea8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000dead  test    eax, eax
0x18000deaf  jnz     short loc_18000DECD
0x18000deb1  test    rbx, rbx
0x18000deb4  jz      short loc_18000DEC5
0x18000deb6  mov     rcx, rbx; Block
0x18000deb9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000debe  xor     ebx, ebx
0x18000dec0  mov     [rsp+58h+Block], rbx
0x18000dec5  inc     edi
0x18000dec7  cmp     edi, [rsp+58h+arg_18]
0x18000decb  jb      short loc_18000DE4E
0x18000decd  test    rbx, rbx
0x18000ded0  jz      short loc_18000DEDA
0x18000ded2  mov     rcx, rbx; Block
0x18000ded5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000deda  mov     rbx, [rsp+58h+arg_0]
0x18000dedf  mov     eax, esi
0x18000dee1  mov     rsi, [rsp+58h+arg_8]
0x18000dee6  mov     rdi, [rsp+58h+arg_10]
0x18000deeb  add     rsp, 40h
0x18000deef  pop     r15
0x18000def1  pop     r14
0x18000def3  pop     r12
0x18000def5  retn
```
