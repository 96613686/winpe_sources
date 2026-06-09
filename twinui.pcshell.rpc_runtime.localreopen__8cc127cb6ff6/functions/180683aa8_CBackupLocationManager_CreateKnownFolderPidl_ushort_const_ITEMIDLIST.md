# CBackupLocationManager::_CreateKnownFolderPidl(ushort const *,_ITEMIDLIST * *)

- ea: `0x180683aa8`
- end: `0x180683c06`
- name: `?_CreateKnownFolderPidl@CBackupLocationManager@@AEBAJPEBGPEAPEFAU_ITEMIDLIST@@@Z`
- size: `350`
- prototype: `int(CBackupLocationManager *__hidden this, const unsigned __int16 *, struct _ITEMIDLIST **)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180683ec8`
- `0x1806849dc`

## callees

- `0x1800c7bc0`
- `0x180356360`
- `0x18067aea4`
- `0x180683aa8`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180683bd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180683bd8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180683b61`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180683b61`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180683b52`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180683b7e`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180683b52`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180683b7e`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x180683bba`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x180683bba`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180683b01`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180683b01`
- `Windows.Storage!__imp_PathComparePaths` at `0x180683b19`
- `Windows.Storage!__imp_PathComparePaths` at `0x180683b19`

## pseudocode

```c
__int64 __fastcall CBackupLocationManager::_CreateKnownFolderPidl(
        PCWSTR *this,
        const unsigned __int16 *a2,
        struct _ITEMIDLIST **a3)
{
  HRESULT v6; // ebx
  const WCHAR *FileNameW; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  IBindCtx *pbc; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF

  *a3 = 0;
  ppszPath = 0;
  v6 = SHGetKnownFolderPath(&FOLDERID_UserPinned, 0x8000u, 0, &ppszPath);
  if ( v6 >= 0 )
  {
    if ( (PathComparePaths(ppszPath, a2) & 8) != 0 )
    {
      v6 = StringCchCopyW(pszPath, 0x104u, L"::{1f3427c8-5c10-4210-aa03-2ee45287d668}\\");
      if ( v6 < 0 )
        goto LABEL_10;
      v6 = PathCchAppend(pszPath, 0x104u, *this);
      if ( v6 < 0 )
        goto LABEL_10;
      FileNameW = PathFindFileNameW(a2);
      if ( FileNameW )
      {
        v6 = PathCchAppend(pszPath, 0x104u, FileNameW);
        if ( v6 >= 0 )
        {
          pbc = 0;
          if ( (int)BindCtx_SetMode(v9, v8, &pbc) >= 0 )
          {
            v6 = SHParseDisplayName(pszPath, pbc, a3, 0, 0);
            ((void (__fastcall *)(IBindCtx *))pbc->lpVtbl->Release)(pbc);
          }
        }
        goto LABEL_10;
      }
    }
    v6 = -2147467259;
LABEL_10:
    CoTaskMemFree(ppszPath);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180683aa8  mov     [rsp-8+arg_18], rbx
0x180683aad  push    rbp
0x180683aae  push    rsi
0x180683aaf  push    rdi
0x180683ab0  push    r12
0x180683ab2  push    r14
0x180683ab4  lea     rbp, [rsp-160h]
0x180683abc  sub     rsp, 260h
0x180683ac3  mov     rax, cs:__security_cookie
0x180683aca  xor     rax, rsp
0x180683acd  mov     [rbp+180h+var_30], rax
0x180683ad4  mov     r14, r8
0x180683ad7  mov     qword ptr [r8], 0
0x180683ade  mov     rdi, rdx
0x180683ae1  mov     [rsp+280h+ppszPath], 0
0x180683aea  mov     rsi, rcx
0x180683aed  lea     r9, [rsp+280h+ppszPath]; ppszPath
0x180683af2  xor     r8d, r8d; hToken
0x180683af5  lea     rcx, FOLDERID_UserPinned; rfid
0x180683afc  mov     edx, 8000h; dwFlags
0x180683b01  call    cs:__imp_SHGetKnownFolderPath
0x180683b07  mov     ebx, eax
0x180683b09  test    eax, eax
0x180683b0b  js      loc_180683BDE
0x180683b11  mov     rcx, [rsp+280h+ppszPath]
0x180683b16  mov     rdx, rdi
0x180683b19  call    cs:__imp_PathComparePaths
0x180683b1f  test    al, 8
0x180683b21  jz      short loc_180683B6C
0x180683b23  mov     r12d, 104h
0x180683b29  lea     r8, a1f3427c85c1042_0; "::{1f3427c8-5c10-4210-aa03-2ee45287d668"...
0x180683b30  mov     edx, r12d; unsigned __int64
0x180683b33  lea     rcx, [rsp+280h+pszPath]; unsigned __int16 *
0x180683b38  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180683b3d  mov     ebx, eax
0x180683b3f  test    eax, eax
0x180683b41  js      loc_180683BD3
0x180683b47  mov     r8, [rsi]; pszMore
0x180683b4a  lea     rcx, [rsp+280h+pszPath]; pszPath
0x180683b4f  mov     edx, r12d; cchPath
0x180683b52  call    cs:__imp_PathCchAppend
0x180683b58  mov     ebx, eax
0x180683b5a  test    eax, eax
0x180683b5c  js      short loc_180683BD3
0x180683b5e  mov     rcx, rdi; pszPath
0x180683b61  call    cs:__imp_PathFindFileNameW
0x180683b67  test    rax, rax
0x180683b6a  jnz     short loc_180683B73
0x180683b6c  mov     ebx, 80004005h
0x180683b71  jmp     short loc_180683BD3
0x180683b73  mov     r8, rax; pszMore
0x180683b76  lea     rcx, [rsp+280h+pszPath]; pszPath
0x180683b7b  mov     rdx, r12; cchPath
0x180683b7e  call    cs:__imp_PathCchAppend
0x180683b84  mov     ebx, eax
0x180683b86  test    eax, eax
0x180683b88  js      short loc_180683BD3
0x180683b8a  lea     r8, [rsp+280h+pbc]
0x180683b8f  mov     [rsp+280h+pbc], 0
0x180683b98  call    BindCtx_SetMode
0x180683b9d  test    eax, eax
0x180683b9f  js      short loc_180683BD3
0x180683ba1  mov     rdx, [rsp+280h+pbc]; pbc
0x180683ba6  lea     rcx, [rsp+280h+pszPath]; pszName
0x180683bab  xor     r9d, r9d; sfgaoIn
0x180683bae  mov     [rsp+280h+psfgaoOut], 0; psfgaoOut
0x180683bb7  mov     r8, r14; ppidl
0x180683bba  call    cs:__imp_SHParseDisplayName
0x180683bc0  mov     rcx, [rsp+280h+pbc]
0x180683bc5  mov     ebx, eax
0x180683bc7  mov     rax, [rcx]
0x180683bca  mov     rax, [rax+10h]
0x180683bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180683bd3  mov     rcx, [rsp+280h+ppszPath]; pv
0x180683bd8  call    cs:__imp_CoTaskMemFree
0x180683bde  mov     eax, ebx
0x180683be0  mov     rcx, [rbp+180h+var_30]
0x180683be7  xor     rcx, rsp; StackCookie
0x180683bea  call    __security_check_cookie
0x180683bef  mov     rbx, [rsp+280h+arg_18]
0x180683bf7  add     rsp, 260h
0x180683bfe  pop     r14
0x180683c00  pop     r12
0x180683c02  pop     rdi
0x180683c03  pop     rsi
0x180683c04  pop     rbp
0x180683c05  retn
```
