# CThumbnailCacheDataFile::MoveFileToTempDirectoryAndDelete(ushort const *)

- ea: `0x180028a6c`
- end: `0x180028b00`
- name: `?MoveFileToTempDirectoryAndDelete@CThumbnailCacheDataFile@@QEAAJPEBG@Z`
- size: `148`
- prototype: `int(CThumbnailCacheDataFile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800287c4`

## callees

- `0x1800112c8`
- `0x180028a6c`
- `0x180028b08`
- `0x1800346ec`
- `0x1800433f8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180028aba`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180028aba`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180028aad`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180028aad`

## string_xrefs

- `0x180028ad2`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbfile.cpp`
- `0x180028aed`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbfile.cpp`

## pseudocode

```c
__int64 __fastcall CThumbnailCacheDataFile::MoveFileToTempDirectoryAndDelete(
        CThumbnailCacheDataFile *this,
        const unsigned __int16 *a2)
{
  __int64 v2; // rax
  CFileHandleCache *v5; // rcx
  int v6; // eax
  const char *v7; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *((_QWORD *)this + 6);
  if ( v2 )
    ++*(_DWORD *)(v2 + 12);
  CThumbnailCacheDataFile::_CloseFileAndMapping(this);
  v6 = CFileHandleCache::CloseFileHandle(v5, (const unsigned __int16 *)this + 214);
  if ( v6 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x237,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbfile.cpp",
      (const char *)(unsigned int)v6,
      v9);
  if ( !MoveFileExW((LPCWSTR)this + 214, a2, 1u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x239,
             (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbfile.cpp",
             v7);
  DeleteFileW(a2);
  return 0;
}

```

## disassembly

```asm
0x180028a6c  mov     [rsp+arg_0], rbx
0x180028a71  push    rdi; int
0x180028a72  sub     rsp, 20h
0x180028a76  mov     rax, [rcx+30h]
0x180028a7a  mov     rdi, rdx
0x180028a7d  mov     rbx, rcx
0x180028a80  test    rax, rax
0x180028a83  jz      short loc_180028A88
0x180028a85  inc     dword ptr [rax+0Ch]
0x180028a88  call    ?_CloseFileAndMapping@CThumbnailCacheDataFile@@AEAAXXZ; CThumbnailCacheDataFile::_CloseFileAndMapping(void)
0x180028a8d  lea     rdx, [rbx+1ACh]; unsigned __int16 *
0x180028a94  call    ?CloseFileHandle@CFileHandleCache@@QEAAJPEBG@Z; CFileHandleCache::CloseFileHandle(ushort const *)
0x180028a99  test    eax, eax
0x180028a9b  js      short loc_180028ACD
0x180028a9d  mov     r8d, 1; dwFlags
0x180028aa3  lea     rcx, [rbx+1ACh]; lpExistingFileName
0x180028aaa  mov     rdx, rdi; lpNewFileName
0x180028aad  call    cs:__imp_MoveFileExW
0x180028ab3  test    eax, eax
0x180028ab5  jz      short loc_180028AE8
0x180028ab7  mov     rcx, rdi; lpFileName
0x180028aba  call    cs:__imp_DeleteFileW
0x180028ac0  xor     eax, eax
0x180028ac2  mov     rbx, [rsp+28h+arg_0]
0x180028ac7  add     rsp, 20h
0x180028acb  pop     rdi
0x180028acc  retn
0x180028acd  mov     rcx, [rsp+28h]; this
0x180028ad2  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180028ad9  mov     r9d, eax; char *
0x180028adc  mov     edx, 237h; void *
0x180028ae1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028ae6  jmp     short loc_180028A9D
0x180028ae8  mov     rcx, [rsp+28h]; this
0x180028aed  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180028af4  mov     edx, 239h; void *
0x180028af9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028afe  jmp     short loc_180028AC2
```
