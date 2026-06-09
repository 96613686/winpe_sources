# CASFV1MetadataLibraryObject::RemoveAll(void)

- ea: `0x18001fc10`
- end: `0x18001fc77`
- name: `?RemoveAll@CASFV1MetadataLibraryObject@@QEAAJXZ`
- size: `103`
- prototype: `__int64 __fastcall(CASFV1MetadataLibraryObject *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800161a4`
- `0x180023e50`

## callees

- `0x180013038`
- `0x180017ff0`
- `0x18001af78`
- `0x18001fc10`

## pseudocode

```c
__int64 __fastcall CASFV1MetadataLibraryObject::RemoveAll(CASFV1MetadataLibraryObject *this)
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
    Ptr = (struct CASFV1MetadataObject::METADATA_REC *)CTDynArray<CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC,20>::GetPtr(
                                                         v2,
                                                         i);
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
0x18001fc10  mov     [rsp+arg_0], rbx
0x18001fc15  mov     [rsp+arg_8], rsi
0x18001fc1a  push    rdi
0x18001fc1b  sub     rsp, 20h
0x18001fc1f  movzx   esi, word ptr [rcx+288h]
0x18001fc26  lea     rbx, [rcx+38h]
0x18001fc2a  xor     edi, edi
0x18001fc2c  xor     eax, eax
0x18001fc2e  cmp     ax, si
0x18001fc31  jnb     short loc_18001FC53
0x18001fc33  movzx   edx, di
0x18001fc36  mov     rcx, rbx
0x18001fc39  call    ?GetPtr@?$CTDynArray@UMETADATA_LIBRARY_REC@CASFV1MetadataLibraryObject@@$0BE@@@QEAAPEAUMETADATA_LIBRARY_REC@CASFV1MetadataLibraryObject@@K@Z; CTDynArray<CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC,20>::GetPtr(ulong)
0x18001fc3e  test    rax, rax
0x18001fc41  jz      short loc_18001FC4B
0x18001fc43  mov     rdx, rax; struct CASFV1MetadataObject::METADATA_REC *
0x18001fc46  call    ?CleanRecord@CASFV1MetadataObject@@QEAAXPEAUMETADATA_REC@1@@Z; CASFV1MetadataObject::CleanRecord(CASFV1MetadataObject::METADATA_REC *)
0x18001fc4b  inc     di
0x18001fc4e  cmp     di, si
0x18001fc51  jb      short loc_18001FC33
0x18001fc53  mov     rcx, rbx
0x18001fc56  call    ?FreeList@?$CTSparseBlock@KUMETADATA_LIBRARY_REC@CASFV1MetadataLibraryObject@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFV1MetadataLibraryObject::METADATA_LIBRARY_REC,20,0>::FreeList(int)
0x18001fc5b  mov     rsi, [rsp+28h+arg_8]
0x18001fc60  xor     eax, eax
0x18001fc62  mov     dword ptr [rbx+250h], 0
0x18001fc6c  mov     rbx, [rsp+28h+arg_0]
0x18001fc71  add     rsp, 20h
0x18001fc75  pop     rdi
0x18001fc76  retn
```
