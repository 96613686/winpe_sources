# CWdsMetadata::RemoveEntry(ulong)

- ea: `0x18000ac50`
- end: `0x18000ad39`
- name: `?RemoveEntry@CWdsMetadata@@QEAAKK@Z`
- size: `233`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000ad40`
- `0x18000c4e0`
- `0x18000c8c4`
- `0x18000f160`

## callees

- `0x180009838`
- `0x18000a380`
- `0x18000ab70`
- `0x18000ac50`
- `0x18000d3b4`
- `0x180014d58`
- `0x1800150b8`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::RemoveEntry(CWdsMetadata *this, const char *a2)
{
  _QWORD *v2; // rbx
  unsigned int v3; // esi
  unsigned int v4; // edi
  __int64 v6; // rcx
  __int64 v7; // r8
  const char *v8; // rdx
  const char *v9; // rdx

  v2 = 0;
  v3 = (unsigned int)a2;
  v4 = 0;
  if ( (unsigned int)a2 < *((_DWORD *)this + 15) )
  {
    _mm_lfence();
    v2 = *(_QWORD **)(*((_QWORD *)this + 6) + 8LL * (unsigned int)a2);
  }
  else
  {
    v4 = 1413;
  }
  if ( !ElValidateWin32(v4, a2, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xD4Bu) )
  {
    v7 = v2[3];
    if ( !v7
      || (v4 = CWdsMetadata::RemoveEntryFromGroup(v6, (char *)this + 24, v7, v2),
          !ElValidateWin32(v4, v8, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xD52u)) )
    {
      CWdsMetadata::RemoveEntryFromGroup(v6, this, *v2, v2);
      v4 = CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem((char *)this + 48, v3);
      if ( !ElValidateWin32(v4, v9, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0xD5Au) )
      {
        CWdsMetadataEntry::Shutdown((CWdsMetadataEntry *)v2);
        CWdsMetadataValue::Shutdown((CWdsMetadataValue *)(v2 + 5));
        operator delete(v2);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000ac50  mov     rax, rsp
0x18000ac53  mov     [rax+8], rbx
0x18000ac57  mov     [rax+10h], rbp
0x18000ac5b  mov     [rax+18h], rsi
0x18000ac5f  mov     [rax+20h], rdi
0x18000ac63  push    r14
0x18000ac65  sub     rsp, 20h
0x18000ac69  xor     ebx, ebx
0x18000ac6b  mov     esi, edx
0x18000ac6d  xor     edi, edi
0x18000ac6f  mov     rbp, rcx
0x18000ac72  cmp     edx, [rcx+3Ch]
0x18000ac75  jb      short loc_18000AC7E
0x18000ac77  mov     edi, 585h
0x18000ac7c  jmp     short loc_18000AC89
0x18000ac7e  lfence
0x18000ac81  mov     rax, [rcx+30h]
0x18000ac85  mov     rbx, [rax+rsi*8]
0x18000ac89  mov     r9d, 0D4Bh; unsigned int
0x18000ac8f  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000ac96  mov     ecx, edi; unsigned int
0x18000ac98  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000ac9d  test    eax, eax
0x18000ac9f  jnz     short loc_18000AD1C
0x18000aca1  mov     r8, [rbx+18h]
0x18000aca5  test    r8, r8
0x18000aca8  jz      short loc_18000ACD0
0x18000acaa  lea     rdx, [rbp+18h]
0x18000acae  mov     r9, rbx
0x18000acb1  call    ?RemoveEntryFromGroup@CWdsMetadata@@AEAAKPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBGPEAVCWdsMetadataEntry@@@Z; CWdsMetadata::RemoveEntryFromGroup(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *,CWdsMetadataEntry *)
0x18000acb6  mov     r9d, 0D52h; unsigned int
0x18000acbc  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000acc3  mov     ecx, eax; unsigned int
0x18000acc5  mov     edi, eax
0x18000acc7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000accc  test    eax, eax
0x18000acce  jnz     short loc_18000AD1C
0x18000acd0  mov     r8, [rbx]
0x18000acd3  mov     r9, rbx
0x18000acd6  mov     rdx, rbp
0x18000acd9  call    ?RemoveEntryFromGroup@CWdsMetadata@@AEAAKPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBGPEAVCWdsMetadataEntry@@@Z; CWdsMetadata::RemoveEntryFromGroup(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *,CWdsMetadataEntry *)
0x18000acde  mov     edx, esi
0x18000ace0  lea     rcx, [rbp+30h]
0x18000ace4  call    ?RemoveItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKK@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem(ulong)
0x18000ace9  mov     r9d, 0D5Ah; unsigned int
0x18000acef  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000acf6  mov     ecx, eax; unsigned int
0x18000acf8  mov     edi, eax
0x18000acfa  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000acff  test    eax, eax
0x18000ad01  jnz     short loc_18000AD1C
0x18000ad03  mov     rcx, rbx; this
0x18000ad06  call    ?Shutdown@CWdsMetadataEntry@@QEAAXXZ; CWdsMetadataEntry::Shutdown(void)
0x18000ad0b  lea     rcx, [rbx+28h]; this
0x18000ad0f  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000ad14  mov     rcx, rbx; Block
0x18000ad17  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ad1c  mov     rbx, [rsp+28h+arg_0]
0x18000ad21  mov     eax, edi
0x18000ad23  mov     rdi, [rsp+28h+arg_18]
0x18000ad28  mov     rbp, [rsp+28h+arg_8]
0x18000ad2d  mov     rsi, [rsp+28h+arg_10]
0x18000ad32  add     rsp, 20h
0x18000ad36  pop     r14
0x18000ad38  retn
```
