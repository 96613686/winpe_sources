# CThumbnailCacheIndex::MoveFileToTempDirectoryAndDelete(ushort const *)

- ea: `0x18002e1ec`
- end: `0x18002e2cd`
- name: `?MoveFileToTempDirectoryAndDelete@CThumbnailCacheIndex@@QEAAJPEBG@Z`
- size: `225`
- prototype: `__int64 __fastcall(CThumbnailCacheIndex *__hidden this, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1800287c4`

## callees

- `0x18000bfd8`
- `0x18000cb84`
- `0x180010ea4`
- `0x180028b08`
- `0x18002e1ec`
- `0x180033f48`
- `0x1800346ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e297`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e2b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e297`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002e2b5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002e2a4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002e2a4`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002e26a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18002e26a`

## string_xrefs

- `0x18002e221`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbidx.cpp`
- `0x18002e279`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbidx.cpp`

## pseudocode

```c
__int64 __fastcall CThumbnailCacheIndex::MoveFileToTempDirectoryAndDelete(
        CThumbnailCacheIndex *this,
        LPCWSTR lpFileName,
        unsigned int a3)
{
  __int64 v3; // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rbx
  CFileHandleCache *v10; // rcx
  const char *v11; // r9
  unsigned int LastError; // eax
  void *v13; // rcx
  unsigned int v14; // edi
  void *v15; // rcx
  int v16; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v18; // [rsp+30h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 9);
  if ( v3 )
    ++*(_DWORD *)(v3 + 12);
  v6 = CReadersWriterLock::AcquireWriterLock((CThumbnailCacheIndex *)((char *)this + 8), (unsigned int)lpFileName, a3);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = *(_QWORD *)wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(
                      &v18,
                      this);
    CThumbnailCacheIndex::_CloseFileAndMapping(this);
    CFileHandleCache::CloseFileHandle(v10, (const unsigned __int16 *)this + 50);
    if ( MoveFileExW((LPCWSTR)this + 50, lpFileName, 1u) )
    {
      DeleteFileW(lpFileName);
      v15 = *(void **)(v9 + 16);
      *(_DWORD *)(v9 + 56) = 0;
      ReleaseMutex(v15);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xE0,
                    (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
                    v11);
      v13 = *(void **)(v9 + 16);
      v14 = LastError;
      *(_DWORD *)(v9 + 56) = 0;
      ReleaseMutex(v13);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbidx.cpp",
      (const char *)(unsigned int)v6,
      v16);
    return v7;
  }
}

```

## disassembly

```asm
0x18002e1ec  mov     [rsp+arg_8], rbx
0x18002e1f1  mov     [rsp+arg_10], rsi
0x18002e1f6  push    rdi; int
0x18002e1f7  sub     rsp, 20h
0x18002e1fb  mov     rax, [rcx+48h]
0x18002e1ff  mov     rsi, rdx
0x18002e202  mov     rdi, rcx
0x18002e205  test    rax, rax
0x18002e208  jz      short loc_18002E20D
0x18002e20a  inc     dword ptr [rax+0Ch]
0x18002e20d  add     rcx, 8; this
0x18002e211  call    ?AcquireWriterLock@CReadersWriterLock@@QEAAJKK@Z; CReadersWriterLock::AcquireWriterLock(ulong,ulong)
0x18002e216  mov     ebx, eax
0x18002e218  test    eax, eax
0x18002e21a  jns     short loc_18002E23C
0x18002e21c  mov     rcx, [rsp+28h]; this
0x18002e221  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18002e228  mov     r9d, eax; char *
0x18002e22b  mov     edx, 0D5h; void *
0x18002e230  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e235  mov     eax, ebx
0x18002e237  jmp     loc_18002E2BD
0x18002e23c  mov     rdx, rdi
0x18002e23f  lea     rcx, [rsp+28h+arg_0]
0x18002e244  call    ??0?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@PEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(_RTL_SRWLOCK *)
0x18002e249  mov     rcx, rdi; this
0x18002e24c  mov     rbx, [rax]
0x18002e24f  call    ?_CloseFileAndMapping@CThumbnailCacheIndex@@AEAAXXZ; CThumbnailCacheIndex::_CloseFileAndMapping(void)
0x18002e254  lea     rdx, [rdi+64h]; unsigned __int16 *
0x18002e258  call    ?CloseFileHandle@CFileHandleCache@@QEAAJPEBG@Z; CFileHandleCache::CloseFileHandle(ushort const *)
0x18002e25d  mov     r8d, 1; dwFlags
0x18002e263  lea     rcx, [rdi+64h]; lpExistingFileName
0x18002e267  mov     rdx, rsi; lpNewFileName
0x18002e26a  call    cs:__imp_MoveFileExW
0x18002e270  test    eax, eax
0x18002e272  jnz     short loc_18002E2A1
0x18002e274  mov     rcx, [rsp+28h]; this
0x18002e279  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18002e280  mov     edx, 0E0h; void *
0x18002e285  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002e28a  mov     rcx, [rbx+10h]; hMutex
0x18002e28e  mov     edi, eax
0x18002e290  mov     dword ptr [rbx+38h], 0
0x18002e297  call    cs:__imp_ReleaseMutex
0x18002e29d  mov     eax, edi
0x18002e29f  jmp     short loc_18002E2BD
0x18002e2a1  mov     rcx, rsi; lpFileName
0x18002e2a4  call    cs:__imp_DeleteFileW
0x18002e2aa  mov     rcx, [rbx+10h]; hMutex
0x18002e2ae  mov     dword ptr [rbx+38h], 0
0x18002e2b5  call    cs:__imp_ReleaseMutex
0x18002e2bb  xor     eax, eax
0x18002e2bd  mov     rbx, [rsp+28h+arg_8]
0x18002e2c2  mov     rsi, [rsp+28h+arg_10]
0x18002e2c7  add     rsp, 20h
0x18002e2cb  pop     rdi
0x18002e2cc  retn
```
