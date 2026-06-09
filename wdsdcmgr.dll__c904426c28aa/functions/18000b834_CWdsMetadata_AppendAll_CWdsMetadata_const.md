# CWdsMetadata::AppendAll(CWdsMetadata const *)

- ea: `0x18000b834`
- end: `0x18000b923`
- name: `?AppendAll@CWdsMetadata@@QEAAKPEBV1@@Z`
- size: `239`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, const struct CWdsMetadata *)`
- caller_count: `8`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180002268`
- `0x1800042f4`
- `0x180005818`
- `0x1800062f0`
- `0x18000e194`
- `0x18000e504`
- `0x18000e65c`
- `0x18000f8e0`

## callees

- `0x18000a3f0`
- `0x18000ad94`
- `0x18000b834`
- `0x18000ba74`
- `0x180014d58`
- `0x1800150b8`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::AppendAll(CWdsMetadata *this, const struct CWdsMetadata *a2)
{
  void *v2; // rbx
  unsigned int appended; // edi
  unsigned int v4; // esi
  const char *v7; // rdx
  const char *v8; // rdx
  int v9; // eax
  const char *v10; // rdx
  void *Block; // [rsp+48h] [rbp+10h] BYREF
  struct CWdsMetadataEntry *v13; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  appended = 0;
  v4 = 0;
  Block = 0;
  if ( *((_DWORD *)a2 + 15) )
  {
    do
    {
      v13 = 0;
      appended = CWdsMetadata::GetByIndex(a2, v4, &v13);
      if ( (unsigned int)ElValidateWin32(appended, v7, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x1013u) )
        break;
      appended = CWdsMetadataEntry::ToString(v13, (unsigned __int16 **)&Block);
      v9 = ElValidateWin32(appended, v8, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x1016u);
      v2 = Block;
      if ( v9 )
        break;
      appended = CWdsMetadata::AppendEntry(this, (const unsigned __int16 *)Block);
      if ( (unsigned int)ElValidateWin32(appended, v10, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x1019u) )
        break;
      if ( v2 )
      {
        operator delete(v2);
        v2 = 0;
        Block = 0;
      }
      ++v4;
    }
    while ( v4 < *((_DWORD *)a2 + 15) );
    if ( v2 )
      operator delete(v2);
  }
  return appended;
}

```

## disassembly

```asm
0x18000b834  mov     [rsp+arg_0], rbx
0x18000b839  mov     [rsp+arg_18], rbp
0x18000b83e  push    rsi
0x18000b83f  push    rdi
0x18000b840  push    r14
0x18000b842  sub     rsp, 20h
0x18000b846  xor     ebx, ebx
0x18000b848  xor     edi, edi
0x18000b84a  xor     esi, esi
0x18000b84c  mov     [rsp+38h+Block], rbx
0x18000b851  mov     rbp, rdx
0x18000b854  mov     r14, rcx
0x18000b857  cmp     [rdx+3Ch], ebx
0x18000b85a  jbe     loc_18000B90E
0x18000b860  and     [rsp+38h+arg_10], 0
0x18000b866  lea     r8, [rsp+38h+arg_10]; struct CWdsMetadataEntry **
0x18000b86b  mov     edx, esi; unsigned int
0x18000b86d  mov     rcx, rbp; this
0x18000b870  call    ?GetByIndex@CWdsMetadata@@QEBAKKPEAPEBVCWdsMetadataEntry@@@Z; CWdsMetadata::GetByIndex(ulong,CWdsMetadataEntry const * *)
0x18000b875  mov     r9d, 1013h; unsigned int
0x18000b87b  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000b882  mov     ecx, eax; unsigned int
0x18000b884  mov     edi, eax
0x18000b886  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b88b  test    eax, eax
0x18000b88d  jnz     short loc_18000B901
0x18000b88f  mov     rcx, [rsp+38h+arg_10]; this
0x18000b894  lea     rdx, [rsp+38h+Block]; unsigned __int16 **
0x18000b899  call    ?ToString@CWdsMetadataEntry@@QEBAKPEAPEAG@Z; CWdsMetadataEntry::ToString(ushort * *)
0x18000b89e  mov     r9d, 1016h; unsigned int
0x18000b8a4  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000b8ab  mov     ecx, eax; unsigned int
0x18000b8ad  mov     edi, eax
0x18000b8af  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b8b4  mov     rbx, [rsp+38h+Block]
0x18000b8b9  test    eax, eax
0x18000b8bb  jnz     short loc_18000B901
0x18000b8bd  mov     rdx, rbx; unsigned __int16 *
0x18000b8c0  mov     rcx, r14; this
0x18000b8c3  call    ?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendEntry(ushort const *)
0x18000b8c8  mov     r9d, 1019h; unsigned int
0x18000b8ce  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000b8d5  mov     ecx, eax; unsigned int
0x18000b8d7  mov     edi, eax
0x18000b8d9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000b8de  test    eax, eax
0x18000b8e0  jnz     short loc_18000B901
0x18000b8e2  test    rbx, rbx
0x18000b8e5  jz      short loc_18000B8F6
0x18000b8e7  mov     rcx, rbx; Block
0x18000b8ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b8ef  xor     ebx, ebx
0x18000b8f1  mov     [rsp+38h+Block], rbx
0x18000b8f6  inc     esi
0x18000b8f8  cmp     esi, [rbp+3Ch]
0x18000b8fb  jb      loc_18000B860
0x18000b901  test    rbx, rbx
0x18000b904  jz      short loc_18000B90E
0x18000b906  mov     rcx, rbx; Block
0x18000b909  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b90e  mov     rbx, [rsp+38h+arg_0]
0x18000b913  mov     eax, edi
0x18000b915  mov     rbp, [rsp+38h+arg_18]
0x18000b91a  add     rsp, 20h
0x18000b91e  pop     r14
0x18000b920  pop     rdi
0x18000b921  pop     rsi
0x18000b922  retn
```
