# COSAsyncDownloader::`scalar deleting destructor'(uint)

- ea: `0x180016e10`
- end: `0x180016e67`
- name: `??_GCOSAsyncDownloader@@UEAAPEAXI@Z`
- size: `87`
- prototype: `void *__fastcall(COSAsyncDownloader *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180016e10`
- `0x180018054`
- `0x180042a24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016e37`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016e37`

## pseudocode

```c
COSAsyncDownloader *__fastcall COSAsyncDownloader::`scalar deleting destructor'(COSAsyncDownloader *this, char a2)
{
  CSusArrayList<CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::_tagMapEntry,CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::CMapEntryOps>::~CSusArrayList<CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::_tagMapEntry,CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::CMapEntryOps>((char *)this + 64);
  *((_QWORD *)this + 2) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  *(_QWORD *)this = &CUHHandlerDownloadBase::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x60);
  return this;
}

```

## disassembly

```asm
0x180016e10  mov     [rsp+arg_0], rbx
0x180016e15  push    rdi
0x180016e16  sub     rsp, 20h
0x180016e1a  mov     rdi, rcx
0x180016e1d  mov     ebx, edx
0x180016e1f  add     rcx, 40h ; '@'
0x180016e23  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UUpdateSessionId@COSAsyncDownloader@@PEAVCOSDownloader@@VCSusSortedArrayListItemOpsUpdateSessionId@2@V?$CSusArrayListItemOpInterfacePtr@PEAVCOSDownloader@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::_tagMapEntry,CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::CMapEntryOps>::~CSusArrayList<CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::_tagMapEntry,CSusMap<COSAsyncDownloader::UpdateSessionId,COSDownloader *,COSAsyncDownloader::CSusSortedArrayListItemOpsUpdateSessionId,CSusArrayListItemOpInterfacePtr<COSDownloader *>>::CMapEntryOps>(void)
0x180016e28  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x180016e2f  lea     rcx, [rdi+18h]; lpCriticalSection
0x180016e33  mov     [rdi+10h], rax
0x180016e37  call    cs:__imp_DeleteCriticalSection
0x180016e3d  lea     rax, ??_7CUHHandlerDownloadBase@@6B@; const CUHHandlerDownloadBase::`vftable'
0x180016e44  mov     [rdi], rax
0x180016e47  test    bl, 1
0x180016e4a  jz      short loc_180016E59
0x180016e4c  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x180016e51  mov     rcx, rdi; void *
0x180016e54  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016e59  mov     rbx, [rsp+28h+arg_0]
0x180016e5e  mov     rax, rdi
0x180016e61  add     rsp, 20h
0x180016e65  pop     rdi
0x180016e66  retn
```
