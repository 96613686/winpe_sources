# FileProvCbUnload

- ea: `0x14002ec90`
- end: `0x14002ed03`
- name: `FileProvCbUnload`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14002f0bc`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002eccb`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002ecde`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002eccb`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002ecde`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002ecf1`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002ecf1`

## pseudocode

```c
void FileProvCbUnload()
{
  FileProvUninitializeCompressionScheme((__int64)g_CompressionScheme);
  FileProvUninitializeCompressionScheme((__int64)qword_1400195C0);
  FileProvUninitializeCompressionScheme((__int64)qword_140019900);
  FileProvUninitializeCompressionScheme((__int64)qword_140019C40);
  ExDeleteNPagedLookasideList(&FileProvCompressContextLookaside);
  ExDeleteNPagedLookasideList(&FileProvCompressWorkitemsLookaside);
  ExDeletePagedLookasideList(&FileProvCompressReadLookaside);
}

```

## disassembly

```asm
0x14002ec90  sub     rsp, 28h
0x14002ec94  lea     rcx, g_CompressionScheme
0x14002ec9b  call    FileProvUninitializeCompressionScheme
0x14002eca0  lea     rcx, qword_1400195C0
0x14002eca7  call    FileProvUninitializeCompressionScheme
0x14002ecac  lea     rcx, qword_140019900
0x14002ecb3  call    FileProvUninitializeCompressionScheme
0x14002ecb8  lea     rcx, qword_140019C40
0x14002ecbf  call    FileProvUninitializeCompressionScheme
0x14002ecc4  lea     rcx, FileProvCompressContextLookaside; Lookaside
0x14002eccb  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002ecd2  nop     dword ptr [rax+rax+00h]
0x14002ecd7  lea     rcx, FileProvCompressWorkitemsLookaside; Lookaside
0x14002ecde  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002ece5  nop     dword ptr [rax+rax+00h]
0x14002ecea  lea     rcx, FileProvCompressReadLookaside; Lookaside
0x14002ecf1  call    cs:__imp_ExDeletePagedLookasideList
0x14002ecf8  nop     dword ptr [rax+rax+00h]
0x14002ecfd  add     rsp, 28h
0x14002ed01  retn
```
