# FileProvCbUnload

- ea: `0x14002ece0`
- end: `0x14002ed53`
- name: `FileProvCbUnload`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14002f10c`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002ed1b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002ed2e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002ed1b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002ed2e`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002ed41`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002ed41`

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
0x14002ece0  sub     rsp, 28h
0x14002ece4  lea     rcx, g_CompressionScheme
0x14002eceb  call    FileProvUninitializeCompressionScheme
0x14002ecf0  lea     rcx, qword_1400195C0
0x14002ecf7  call    FileProvUninitializeCompressionScheme
0x14002ecfc  lea     rcx, qword_140019900
0x14002ed03  call    FileProvUninitializeCompressionScheme
0x14002ed08  lea     rcx, qword_140019C40
0x14002ed0f  call    FileProvUninitializeCompressionScheme
0x14002ed14  lea     rcx, FileProvCompressContextLookaside; Lookaside
0x14002ed1b  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002ed22  nop     dword ptr [rax+rax+00h]
0x14002ed27  lea     rcx, FileProvCompressWorkitemsLookaside; Lookaside
0x14002ed2e  call    cs:__imp_ExDeleteNPagedLookasideList
0x14002ed35  nop     dword ptr [rax+rax+00h]
0x14002ed3a  lea     rcx, FileProvCompressReadLookaside; Lookaside
0x14002ed41  call    cs:__imp_ExDeletePagedLookasideList
0x14002ed48  nop     dword ptr [rax+rax+00h]
0x14002ed4d  add     rsp, 28h
0x14002ed51  retn
```
