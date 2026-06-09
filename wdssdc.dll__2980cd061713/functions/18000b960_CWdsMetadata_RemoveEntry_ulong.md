# CWdsMetadata::RemoveEntry(ulong)

- ea: `0x18000b960`
- end: `0x18000ba3a`
- name: `?RemoveEntry@CWdsMetadata@@QEAAKK@Z`
- size: `218`
- prototype: `unsigned int __fastcall(CWdsMetadata *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180009390`

## callees

- `0x1800015d4`
- `0x18000b960`
- `0x18000ba40`
- `0x18000bb00`
- `0x18000be44`
- `0x18000bec0`
- `0x18000c274`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::RemoveEntry(CWdsMetadata *this, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rbx
  unsigned int v4; // esi
  __int64 v5; // rdi
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8

  v3 = 0;
  v4 = a2;
  LODWORD(v5) = 0;
  if ( (unsigned int)a2 < *((_DWORD *)this + 15) )
  {
    _mm_lfence();
    v3 = *(_QWORD **)(*((_QWORD *)this + 6) + 8LL * (unsigned int)a2);
  }
  else
  {
    LODWORD(v5) = 1413;
  }
  if ( !(unsigned int)ElValidateWin32_1((unsigned int)v5, a2, a3, 3403) )
  {
    v8 = v3[3];
    if ( !v8
      || (v5 = (unsigned int)CWdsMetadata::RemoveEntryFromGroup(v7, (char *)this + 24, v8, v3),
          !(unsigned int)ElValidateWin32_1(v5, v9, v10, 3410)) )
    {
      CWdsMetadata::RemoveEntryFromGroup(v7, this, *v3, v3);
      LODWORD(v5) = CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem((char *)this + 48, v4);
      if ( !(unsigned int)ElValidateWin32_1((unsigned int)v5, v11, v12, 3418) )
      {
        CWdsMetadataEntry::Shutdown((CWdsMetadataEntry *)v3);
        CWdsMetadataValue::Shutdown((CWdsMetadataValue *)(v3 + 5));
        operator delete(v3);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b960  mov     rax, rsp
0x18000b963  mov     [rax+8], rbx
0x18000b967  mov     [rax+10h], rbp
0x18000b96b  mov     [rax+18h], rsi
0x18000b96f  mov     [rax+20h], rdi
0x18000b973  push    r14
0x18000b975  sub     rsp, 20h
0x18000b979  xor     ebx, ebx
0x18000b97b  mov     esi, edx
0x18000b97d  xor     edi, edi
0x18000b97f  mov     rbp, rcx
0x18000b982  cmp     edx, [rcx+3Ch]
0x18000b985  jb      short loc_18000B98E
0x18000b987  mov     edi, 585h
0x18000b98c  jmp     short loc_18000B999
0x18000b98e  lfence
0x18000b991  mov     rax, [rcx+30h]
0x18000b995  mov     rbx, [rax+rsi*8]
0x18000b999  mov     r9d, 0D4Bh
0x18000b99f  mov     ecx, edi
0x18000b9a1  call    ElValidateWin32_1
0x18000b9a6  test    eax, eax
0x18000b9a8  jnz     short loc_18000BA1C
0x18000b9aa  mov     r8, [rbx+18h]
0x18000b9ae  test    r8, r8
0x18000b9b1  jz      short loc_18000B9D2
0x18000b9b3  lea     rdx, [rbp+18h]
0x18000b9b7  mov     r9, rbx
0x18000b9ba  call    ?RemoveEntryFromGroup@CWdsMetadata@@AEAAKPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBGPEAVCWdsMetadataEntry@@@Z; CWdsMetadata::RemoveEntryFromGroup(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *,CWdsMetadataEntry *)
0x18000b9bf  mov     r9d, 0D52h
0x18000b9c5  mov     ecx, eax
0x18000b9c7  mov     edi, eax
0x18000b9c9  call    ElValidateWin32_1
0x18000b9ce  test    eax, eax
0x18000b9d0  jnz     short loc_18000BA1C
0x18000b9d2  mov     r8, [rbx]
0x18000b9d5  mov     r9, rbx
0x18000b9d8  mov     rdx, rbp
0x18000b9db  call    ?RemoveEntryFromGroup@CWdsMetadata@@AEAAKPEAV?$CDynArray@PEAUCEntryGroup@CWdsMetadata@@VCDeallocatePointer@@@@PEBGPEAVCWdsMetadataEntry@@@Z; CWdsMetadata::RemoveEntryFromGroup(CDynArray<CWdsMetadata::CEntryGroup *,CDeallocatePointer> *,ushort const *,CWdsMetadataEntry *)
0x18000b9e0  mov     edx, esi
0x18000b9e2  lea     rcx, [rbp+30h]
0x18000b9e6  call    ?RemoveItem@?$CDynArray@PEAVCWdsMetadataEntry@@VCDeallocatePointer@@@@QEAAKK@Z; CDynArray<CWdsMetadataEntry *,CDeallocatePointer>::RemoveItem(ulong)
0x18000b9eb  mov     r9d, 0D5Ah
0x18000b9f1  mov     ecx, eax
0x18000b9f3  mov     edi, eax
0x18000b9f5  call    ElValidateWin32_1
0x18000b9fa  test    eax, eax
0x18000b9fc  jnz     short loc_18000BA1C
0x18000b9fe  mov     rcx, rbx; this
0x18000ba01  call    ?Shutdown@CWdsMetadataEntry@@QEAAXXZ; CWdsMetadataEntry::Shutdown(void)
0x18000ba06  lea     rcx, [rbx+28h]; this
0x18000ba0a  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000ba0f  mov     edx, 40h ; '@'
0x18000ba14  mov     rcx, rbx; Block
0x18000ba17  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba1c  mov     rbx, [rsp+28h+arg_0]
0x18000ba21  mov     eax, edi
0x18000ba23  mov     rdi, [rsp+28h+arg_18]
0x18000ba28  mov     rbp, [rsp+28h+arg_8]
0x18000ba2d  mov     rsi, [rsp+28h+arg_10]
0x18000ba32  add     rsp, 20h
0x18000ba36  pop     r14
0x18000ba38  retn
```
