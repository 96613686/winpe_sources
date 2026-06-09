# CWdsMetadata::QueryOptional(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *,CWdsMetadataValue const *)

- ea: `0x18000af78`
- end: `0x18000b1a1`
- name: `?QueryOptional@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@PEBV3@@Z`
- size: `553`
- prototype: ``
- caller_count: `8`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000b1a8`
- `0x18000fae0`
- `0x18000fcc0`
- `0x18000fe40`
- `0x180010020`
- `0x180010180`
- `0x1800102e0`
- `0x1800105d0`

## callees

- `0x180009b3c`
- `0x18000a3f0`
- `0x18000adf4`
- `0x18000ae38`
- `0x18000af78`
- `0x180014d58`
- `0x1800150b8`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::QueryOptional(
        CWdsMetadata *a1,
        const unsigned __int16 *a2,
        int a3,
        CWdsMetadataValue *a4,
        struct CWdsMetadataValue *a5)
{
  unsigned __int16 *v5; // rbp
  __int64 v6; // r15
  unsigned int InstancesOfTag; // edi
  unsigned int v11; // eax
  const char *v12; // rdx
  unsigned int v13; // r9d
  unsigned int v14; // ecx
  _DWORD *v15; // rsi
  const char *v16; // rdx
  const char *v17; // rdx
  void *v18; // rcx
  void *v19; // rbx
  const struct CWdsMetadataValue *v20; // r14
  int v21; // eax
  unsigned __int16 *v22; // rdx
  const char *v23; // rdx
  unsigned __int16 *v25; // [rsp+30h] [rbp-38h] BYREF
  void *Block; // [rsp+38h] [rbp-30h] BYREF
  int v27; // [rsp+40h] [rbp-28h]
  int v28; // [rsp+44h] [rbp-24h]

  v5 = 0;
  v6 = a3;
  v25 = 0;
  if ( (unsigned int)(a3 - 1) <= 6
    || (InstancesOfTag = 87,
        !(unsigned int)ElValidateWin32(
                         0x57u,
                         (const char *)a2,
                         "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp",
                         0xEADu)) )
  {
    v11 = CWdsMetadata::CountInstancesOfTag(a1, a2);
    if ( !v11 )
    {
      InstancesOfTag = CWdsMetadataValue::Copy(a4, a5);
      v13 = 3768;
      v14 = InstancesOfTag;
LABEL_5:
      ElValidateWin32(v14, v12, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", v13);
      return InstancesOfTag;
    }
    if ( v11 > 1 )
    {
      if ( g_ErrLibTraceFunction )
        g_ErrLibTraceFunction(L"Expected 0 or 1 instances of Tag [%s]; received %u instances", a2, v11);
      v14 = 13;
      v13 = 3775;
      InstancesOfTag = 13;
      goto LABEL_5;
    }
    v15 = 0;
    Block = 0;
    v27 = 0;
    v28 = 0;
    InstancesOfTag = CWdsMetadata::GetInstancesOfTag(a1, a2, &Block);
    if ( (unsigned int)ElValidateWin32(InstancesOfTag, v16, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xEC9u) )
    {
      v18 = Block;
      if ( !Block )
        return InstancesOfTag;
LABEL_12:
      operator delete(v18);
      return InstancesOfTag;
    }
    v19 = Block;
    InstancesOfTag = 0;
    if ( v28 )
      v15 = *(_DWORD **)Block;
    else
      InstancesOfTag = 1413;
    if ( (unsigned int)ElValidateWin32(InstancesOfTag, v17, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xECCu) )
    {
      if ( !v19 )
        return InstancesOfTag;
      v18 = v19;
      goto LABEL_12;
    }
    if ( !v15[8] )
    {
      v20 = (const struct CWdsMetadataValue *)(v15 + 10);
      if ( v15[10] == (_DWORD)v6 )
        goto LABEL_26;
    }
    v21 = CWdsMetadataEntry::ToString((CWdsMetadataEntry *)v15, &v25);
    v5 = v25;
    v22 = L"<error>";
    v20 = (const struct CWdsMetadataValue *)(v15 + 10);
    if ( !v21 )
      v22 = v25;
    if ( g_ErrLibTraceFunction )
      g_ErrLibTraceFunction(L"Entry %s is of type %s; expected %s", v22, off_180017520[*(int *)v20], off_180017520[v6]);
    InstancesOfTag = 13;
    if ( !(unsigned int)ElValidateWin32(
                          0xDu,
                          (const char *)v22,
                          "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp",
                          0xEDFu) )
    {
LABEL_26:
      InstancesOfTag = CWdsMetadataValue::Copy(a4, v20);
      ElValidateWin32(InstancesOfTag, v23, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xEE3u);
    }
    if ( v19 )
      operator delete(v19);
    if ( v5 )
      operator delete(v5);
  }
  return InstancesOfTag;
}

```

## disassembly

```asm
0x18000af78  mov     rax, rsp
0x18000af7b  mov     [rax+8], rbx
0x18000af7f  mov     [rax+10h], rbp
0x18000af83  mov     [rax+18h], rsi
0x18000af87  mov     [rax+20h], rdi
0x18000af8b  push    r12
0x18000af8d  push    r14
0x18000af8f  push    r15
0x18000af91  sub     rsp, 50h
0x18000af95  xor     ebp, ebp
0x18000af97  movsxd  r15, r8d
0x18000af9a  mov     [rax-38h], rbp
0x18000af9e  lea     rsi, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000afa5  mov     r12, r9
0x18000afa8  mov     rbx, rdx
0x18000afab  mov     r14, rcx
0x18000afae  lea     eax, [r15-1]
0x18000afb2  cmp     eax, 6
0x18000afb5  jbe     short loc_18000AFD2
0x18000afb7  lea     edi, [rbp+57h]
0x18000afba  mov     r9d, 0EADh; unsigned int
0x18000afc0  mov     ecx, edi; unsigned int
0x18000afc2  mov     r8, rsi; char *
0x18000afc5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000afca  test    eax, eax
0x18000afcc  jnz     loc_18000B180
0x18000afd2  mov     rdx, rbx; unsigned __int16 *
0x18000afd5  mov     rcx, r14; this
0x18000afd8  call    ?CountInstancesOfTag@CWdsMetadata@@QEBAKPEBG@Z; CWdsMetadata::CountInstancesOfTag(ushort const *)
0x18000afdd  test    eax, eax
0x18000afdf  jnz     short loc_18000B008
0x18000afe1  mov     rdx, [rsp+68h+arg_20]; struct CWdsMetadataValue *
0x18000afe9  mov     rcx, r12; this
0x18000afec  call    ?Copy@CWdsMetadataValue@@QEAAKPEBV1@@Z; CWdsMetadataValue::Copy(CWdsMetadataValue const *)
0x18000aff1  mov     edi, eax
0x18000aff3  mov     r9d, 0EB8h; unsigned int
0x18000aff9  mov     ecx, eax; unsigned int
0x18000affb  mov     r8, rsi; char *
0x18000affe  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b003  jmp     loc_18000B180
0x18000b008  cmp     eax, 1
0x18000b00b  jbe     short loc_18000B03E
0x18000b00d  mov     r9, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000b014  test    r9, r9
0x18000b017  jz      short loc_18000B02F
0x18000b019  mov     r8d, eax
0x18000b01c  lea     rcx, aExpected0Or1In; "Expected 0 or 1 instances of Tag [%s]; "...
0x18000b023  mov     rax, r9
0x18000b026  mov     rdx, rbx
0x18000b029  call    cs:__guard_dispatch_icall_fptr
0x18000b02f  mov     ecx, 0Dh
0x18000b034  mov     r9d, 0EBFh
0x18000b03a  mov     edi, ecx
0x18000b03c  jmp     short loc_18000AFFB
0x18000b03e  xor     esi, esi
0x18000b040  lea     r8, [rsp+68h+Block]
0x18000b045  and     [rsp+68h+Block], rsi
0x18000b04a  mov     rdx, rbx
0x18000b04d  and     [rsp+68h+var_28], esi
0x18000b051  mov     rcx, r14
0x18000b054  and     [rsp+68h+var_24], esi
0x18000b058  call    ?GetInstancesOfTag@CWdsMetadata@@QEBAKPEBGPEAV?$CDynArray@PEBVCWdsMetadataEntry@@VCDeallocateNone@@@@@Z; CWdsMetadata::GetInstancesOfTag(ushort const *,CDynArray<CWdsMetadataEntry const *,CDeallocateNone> *)
0x18000b05d  mov     r9d, 0EC9h; unsigned int
0x18000b063  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000b06a  mov     ecx, eax; unsigned int
0x18000b06c  mov     edi, eax
0x18000b06e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b073  test    eax, eax
0x18000b075  jz      short loc_18000B08F
0x18000b077  mov     rcx, [rsp+68h+Block]; Block
0x18000b07c  test    rcx, rcx
0x18000b07f  jz      loc_18000B180
0x18000b085  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b08a  jmp     loc_18000B180
0x18000b08f  mov     rbx, [rsp+68h+Block]
0x18000b094  xor     edi, edi
0x18000b096  cmp     [rsp+68h+var_24], esi
0x18000b09a  ja      short loc_18000B0A3
0x18000b09c  mov     edi, 585h
0x18000b0a1  jmp     short loc_18000B0A6
0x18000b0a3  mov     rsi, [rbx]
0x18000b0a6  mov     r9d, 0ECCh; unsigned int
0x18000b0ac  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000b0b3  mov     ecx, edi; unsigned int
0x18000b0b5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b0ba  test    eax, eax
0x18000b0bc  jz      short loc_18000B0CC
0x18000b0be  test    rbx, rbx
0x18000b0c1  jz      loc_18000B180
0x18000b0c7  mov     rcx, rbx
0x18000b0ca  jmp     short loc_18000B085
0x18000b0cc  cmp     [rsi+20h], ebp
0x18000b0cf  jnz     short loc_18000B0DA
0x18000b0d1  lea     r14, [rsi+28h]
0x18000b0d5  cmp     [r14], r15d
0x18000b0d8  jz      short loc_18000B145
0x18000b0da  lea     rdx, [rsp+68h+var_38]; unsigned __int16 **
0x18000b0df  mov     rcx, rsi; this
0x18000b0e2  call    ?ToString@CWdsMetadataEntry@@QEBAKPEAPEAG@Z; CWdsMetadataEntry::ToString(ushort * *)
0x18000b0e7  mov     rbp, [rsp+68h+var_38]
0x18000b0ec  lea     rdx, aError; "<error>"
0x18000b0f3  test    eax, eax
0x18000b0f5  lea     r14, [rsi+28h]
0x18000b0f9  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18000b100  cmovz   rdx, rbp
0x18000b104  test    rax, rax
0x18000b107  jz      short loc_18000B128
0x18000b109  movsxd  r8, dword ptr [r14]
0x18000b10c  lea     rcx, off_180017520; "<Invalid>"
0x18000b113  mov     r9, [rcx+r15*8]
0x18000b117  mov     r8, [rcx+r8*8]
0x18000b11b  lea     rcx, aEntrySIsOfType; "Entry %s is of type %s; expected %s"
0x18000b122  call    cs:__guard_dispatch_icall_fptr
0x18000b128  mov     ecx, 0Dh; unsigned int
0x18000b12d  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000b134  mov     r9d, 0EDFh; unsigned int
0x18000b13a  mov     edi, ecx
0x18000b13c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b141  test    eax, eax
0x18000b143  jnz     short loc_18000B166
0x18000b145  mov     rdx, r14; struct CWdsMetadataValue *
0x18000b148  mov     rcx, r12; this
0x18000b14b  call    ?Copy@CWdsMetadataValue@@QEAAKPEBV1@@Z; CWdsMetadataValue::Copy(CWdsMetadataValue const *)
0x18000b150  mov     r9d, 0EE3h; unsigned int
0x18000b156  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000b15d  mov     ecx, eax; unsigned int
0x18000b15f  mov     edi, eax
0x18000b161  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b166  test    rbx, rbx
0x18000b169  jz      short loc_18000B173
0x18000b16b  mov     rcx, rbx; Block
0x18000b16e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b173  test    rbp, rbp
0x18000b176  jz      short loc_18000B180
0x18000b178  mov     rcx, rbp; Block
0x18000b17b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b180  lea     r11, [rsp+68h+var_18]
0x18000b185  mov     eax, edi
0x18000b187  mov     rbx, [r11+20h]
0x18000b18b  mov     rbp, [r11+28h]
0x18000b18f  mov     rsi, [r11+30h]
0x18000b193  mov     rdi, [r11+38h]
0x18000b197  mov     rsp, r11
0x18000b19a  pop     r15
0x18000b19c  pop     r14
0x18000b19e  pop     r12
0x18000b1a0  retn
```
