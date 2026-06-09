# CASFV1MetadataObject::RemoveAll(void)

- ea: `0x18001fc80`
- end: `0x18001fce7`
- name: `?RemoveAll@CASFV1MetadataObject@@QEAAJXZ`
- size: `103`
- prototype: `__int64 __fastcall(CASFV1MetadataObject *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800161dc`
- `0x180024120`

## callees

- `0x180013090`
- `0x180017ff0`
- `0x18001af78`
- `0x18001fc80`

## pseudocode

```c
__int64 __fastcall CASFV1MetadataObject::RemoveAll(CASFV1MetadataObject *this)
{
  unsigned __int16 v1; // si
  char *v2; // rbx
  unsigned __int16 i; // di
  struct CASFV1MetadataObject::METADATA_REC *Ptr; // rax
  CASFV1MetadataObject *v5; // rcx
  __int64 result; // rax

  v1 = *((_WORD *)this + 324);
  v2 = (char *)this + 56;
  for ( i = 0; i < v1; ++i )
  {
    Ptr = (struct CASFV1MetadataObject::METADATA_REC *)CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::GetPtr(v2, i);
    if ( Ptr )
      CASFV1MetadataObject::CleanRecord(v5, Ptr);
  }
  CTSparseBlock<unsigned long,CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC,20,0>::FreeList(v2);
  result = 0;
  *((_DWORD *)v2 + 148) = 0;
  return result;
}

```

## disassembly

```asm
0x18001fc80  mov     [rsp+arg_0], rbx
0x18001fc85  mov     [rsp+arg_8], rsi
0x18001fc8a  push    rdi
0x18001fc8b  sub     rsp, 20h
0x18001fc8f  movzx   esi, word ptr [rcx+288h]
0x18001fc96  lea     rbx, [rcx+38h]
0x18001fc9a  xor     edi, edi
0x18001fc9c  xor     eax, eax
0x18001fc9e  cmp     ax, si
0x18001fca1  jnb     short loc_18001FCC3
0x18001fca3  movzx   edx, di
0x18001fca6  mov     rcx, rbx
0x18001fca9  call    ?GetPtr@?$CTDynArray@UMETADATA_REC@CASFV1MetadataObject@@$0BE@@@QEAAPEAUMETADATA_REC@CASFV1MetadataObject@@K@Z; CTDynArray<CASFV1MetadataObject::METADATA_REC,20>::GetPtr(ulong)
0x18001fcae  test    rax, rax
0x18001fcb1  jz      short loc_18001FCBB
0x18001fcb3  mov     rdx, rax; struct CASFV1MetadataObject::METADATA_REC *
0x18001fcb6  call    ?CleanRecord@CASFV1MetadataObject@@QEAAXPEAUMETADATA_REC@1@@Z; CASFV1MetadataObject::CleanRecord(CASFV1MetadataObject::METADATA_REC *)
0x18001fcbb  inc     di
0x18001fcbe  cmp     di, si
0x18001fcc1  jb      short loc_18001FCA3
0x18001fcc3  mov     rcx, rbx
0x18001fcc6  call    ?FreeList@?$CTSparseBlock@KUMETADATA_LIBRARY_REC@CASFV1MetadataLibraryObject@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC,20,0>::FreeList(int)
0x18001fccb  mov     rsi, [rsp+28h+arg_8]
0x18001fcd0  xor     eax, eax
0x18001fcd2  mov     dword ptr [rbx+250h], 0
0x18001fcdc  mov     rbx, [rsp+28h+arg_0]
0x18001fce1  add     rsp, 20h
0x18001fce5  pop     rdi
0x18001fce6  retn
```
