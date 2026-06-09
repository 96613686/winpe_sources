# CWdsDeviceControllerPacket::AddMetadata(ushort const *,CWdsMetadata const *)

- ea: `0x180014f60`
- end: `0x18001508b`
- name: `?AddMetadata@CWdsDeviceControllerPacket@@QEAAKPEBGPEBVCWdsMetadata@@@Z`
- size: `299`
- prototype: `unsigned int __fastcall(CWdsDeviceControllerPacket *__hidden this, const unsigned __int16 *, const struct CWdsMetadata *)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180013ed0`
- `0x180014590`
- `0x180014990`
- `0x180014e68`

## callees

- `0x18000df24`
- `0x18000f9f8`
- `0x1800119d4`
- `0x180011e48`
- `0x180014f60`
- `0x1800153bc`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180015040`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015065`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015040`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180015065`

## pseudocode

```c
__int64 __fastcall CWdsDeviceControllerPacket::AddMetadata(
        CWdsDeviceControllerPacket *this,
        unsigned __int16 *a2,
        const struct CWdsMetadata *a3)
{
  unsigned int v3; // ebp
  unsigned __int16 *v5; // rbx
  unsigned int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // esi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int16 *v20; // [rsp+20h] [rbp-38h]
  unsigned __int16 *v21; // [rsp+70h] [rbp+18h] BYREF
  struct CWdsMetadataEntry *v22; // [rsp+78h] [rbp+20h] BYREF

  v3 = *((_DWORD *)a3 + 15);
  v5 = 0;
  v21 = 0;
  v8 = CControlPacket::AddVariable<unsigned long>(this, a2, L"Count", 0xFFFFFFFF, (__int64)v20, v3);
  if ( !(unsigned int)ElValidateWin32_11(v8, v9, v10, 0x72u) )
  {
    v11 = 0;
    if ( v3 )
    {
      do
      {
        v22 = 0;
        v8 = CWdsMetadata::GetByIndex(a3, v11, &v22);
        if ( (unsigned int)ElValidateWin32_11(v8, v12, v13, 0x79u) )
          break;
        v8 = CWdsMetadataEntry::ToString(v22, &v21);
        v16 = ElValidateWin32_11(v8, v14, v15, 0x7Cu);
        v5 = v21;
        if ( v16 )
          break;
        v8 = CControlPacket::AddString(this, a2, L"Entry", v11, v21);
        if ( (unsigned int)ElValidateWin32_11(v8, v17, v18, 0x82u) )
          break;
        if ( v5 )
        {
          operator delete[](v5);
          v5 = 0;
          v21 = 0;
        }
        ++v11;
      }
      while ( v11 < v3 );
      if ( v5 )
        operator delete[](v5);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180014f60  mov     rax, rsp
0x180014f63  mov     [rax+8], rbx
0x180014f67  mov     [rax+10h], rbp
0x180014f6b  push    rsi
0x180014f6c  push    rdi
0x180014f6d  push    r12
0x180014f6f  push    r14
0x180014f71  push    r15
0x180014f73  sub     rsp, 30h
0x180014f77  mov     ebp, [r8+3Ch]
0x180014f7b  mov     r14, r8
0x180014f7e  xor     ebx, ebx
0x180014f80  mov     [rax-30h], ebp
0x180014f83  lea     r8, aCount; "Count"
0x180014f8a  mov     [rax+18h], rbx
0x180014f8e  or      r9d, 0FFFFFFFFh
0x180014f92  mov     r15, rdx
0x180014f95  mov     r12, rcx
0x180014f98  call    ??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z; CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)
0x180014f9d  lea     r9d, [rbx+72h]
0x180014fa1  mov     ecx, eax
0x180014fa3  mov     edi, eax
0x180014fa5  call    ElValidateWin32_11
0x180014faa  test    eax, eax
0x180014fac  jnz     loc_180015071
0x180014fb2  xor     esi, esi
0x180014fb4  test    ebp, ebp
0x180014fb6  jz      loc_180015071
0x180014fbc  and     [rsp+58h+arg_18], 0
0x180014fc2  lea     r8, [rsp+58h+arg_18]; struct CWdsMetadataEntry **
0x180014fc7  mov     edx, esi; unsigned int
0x180014fc9  mov     rcx, r14; this
0x180014fcc  call    ?GetByIndex@CWdsMetadata@@QEBAKKPEAPEBVCWdsMetadataEntry@@@Z; CWdsMetadata::GetByIndex(ulong,CWdsMetadataEntry const * *)
0x180014fd1  mov     r9d, 79h ; 'y'
0x180014fd7  mov     ecx, eax
0x180014fd9  mov     edi, eax
0x180014fdb  call    ElValidateWin32_11
0x180014fe0  test    eax, eax
0x180014fe2  jnz     short loc_18001505D
0x180014fe4  mov     rcx, [rsp+58h+arg_18]; this
0x180014fe9  lea     rdx, [rsp+58h+arg_10]; unsigned __int16 **
0x180014fee  call    ?ToString@CWdsMetadataEntry@@QEBAKPEAPEAG@Z; CWdsMetadataEntry::ToString(ushort * *)
0x180014ff3  mov     r9d, 7Ch ; '|'
0x180014ff9  mov     ecx, eax
0x180014ffb  mov     edi, eax
0x180014ffd  call    ElValidateWin32_11
0x180015002  mov     rbx, [rsp+58h+arg_10]
0x180015007  test    eax, eax
0x180015009  jnz     short loc_18001505D
0x18001500b  mov     r9d, esi; unsigned int
0x18001500e  mov     [rsp+58h+var_38], rbx; unsigned __int16 *
0x180015013  lea     r8, aEntry; "Entry"
0x18001501a  mov     rdx, r15; unsigned __int16 *
0x18001501d  mov     rcx, r12; this
0x180015020  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x180015025  mov     r9d, 82h
0x18001502b  mov     ecx, eax
0x18001502d  mov     edi, eax
0x18001502f  call    ElValidateWin32_11
0x180015034  test    eax, eax
0x180015036  jnz     short loc_18001505D
0x180015038  test    rbx, rbx
0x18001503b  jz      short loc_180015053
0x18001503d  mov     rcx, rbx
0x180015040  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180015047  nop     dword ptr [rax+rax+00h]
0x18001504c  xor     ebx, ebx
0x18001504e  mov     [rsp+58h+arg_10], rbx
0x180015053  inc     esi
0x180015055  cmp     esi, ebp
0x180015057  jb      loc_180014FBC
0x18001505d  test    rbx, rbx
0x180015060  jz      short loc_180015071
0x180015062  mov     rcx, rbx
0x180015065  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001506c  nop     dword ptr [rax+rax+00h]
0x180015071  mov     rbx, [rsp+58h+arg_0]
0x180015076  mov     eax, edi
0x180015078  mov     rbp, [rsp+58h+arg_8]
0x18001507d  add     rsp, 30h
0x180015081  pop     r15
0x180015083  pop     r14
0x180015085  pop     r12
0x180015087  pop     rdi
0x180015088  pop     rsi
0x180015089  retn
```
