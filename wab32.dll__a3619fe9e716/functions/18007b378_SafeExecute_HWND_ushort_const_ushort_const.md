# SafeExecute(HWND__ *,ushort const *,ushort const *)

- ea: `0x18007b378`
- end: `0x18007b5a9`
- name: `?SafeExecute@@YAJPEAUHWND__@@PEBG1@Z`
- size: `561`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180039b64`
- `0x180053be0`
- `0x180058210`
- `0x18005a9b0`
- `0x180060850`

## callees

- `0x180005d08`
- `0x18007b2d4`
- `0x18007b378`
- `0x18007b5b0`
- `0x18007b8e8`
- `0x180091eaa`
- `0x180091ef0`
- `0x180091f80`
- `0x180093010`

## import_xrefs

- `SHLWAPI!UrlIsW` at `0x18007b3f9`
- `SHLWAPI!UrlIsW` at `0x18007b3f9`
- `SHLWAPI!PathCreateFromUrlW` at `0x18007b46d`
- `SHLWAPI!PathCreateFromUrlW` at `0x18007b46d`
- `SHLWAPI!PathIsDirectoryW` at `0x18007b481`
- `SHLWAPI!PathIsDirectoryW` at `0x18007b481`
- `SHLWAPI!UrlCanonicalizeW` at `0x18007b3dd`
- `SHLWAPI!UrlCanonicalizeW` at `0x18007b3dd`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18007b415`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18007b415`
- `SHELL32!ShellExecuteExW` at `0x18007b572`
- `SHELL32!ShellExecuteExW` at `0x18007b572`

## pseudocode

```c
__int64 __fastcall SafeExecute(HWND a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HRESULT v5; // ebx
  BOOL IsW; // ebx
  const struct _GUID *v8; // rdx
  const unsigned __int16 *v9; // rcx
  void *v10; // rcx
  void *v12; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcchCanonicalized; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchPath; // [rsp+3Ch] [rbp-C4h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszCanonicalized[2088]; // [rsp+2C0h] [rbp+1C0h] BYREF

  memset_0(pszCanonicalized, 0, 0x1048u);
  pcchCanonicalized = 2084;
  v5 = UrlCanonicalizeW(a3, pszCanonicalized, &pcchCanonicalized, 0);
  if ( v5 >= 0 )
  {
    IsW = UrlIsW(pszCanonicalized, URLIS_FILEURL);
    if ( !StrCmpNICW(L"mshelp://", pszCanonicalized, 9) )
      return (unsigned int)ShowHelp(pszCanonicalized);
    if ( IsW )
    {
      v12 = 0;
      memset_0(pszPath, 0, 0x208u);
      pcchPath = 260;
      v5 = PathCreateFromUrlW(pszCanonicalized, pszPath, &pcchPath, 0);
      if ( v5 >= 0 )
      {
        if ( PathIsDirectoryW(pszPath) )
        {
          v5 = SafeExecuteDirectory(pszPath);
        }
        else
        {
          v5 = CreateAttachmentServices(v9, v8, &v12);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(void *, WCHAR *))(*(_QWORD *)v12 + 40LL))(v12, pszPath);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v12 + 72LL))(v12);
              if ( !v5 )
              {
                v5 = (*(__int64 (__fastcall **)(void *, HWND, const WCHAR *, _QWORD))(*(_QWORD *)v12 + 96LL))(
                       v12,
                       a1,
                       L"open",
                       0);
                if ( v5 >= 0 )
                  v5 = 0;
              }
            }
          }
        }
      }
      v10 = v12;
      if ( v12 )
      {
        v12 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    else
    {
      pExecInfo.cbSize = 112;
      v5 = 0;
      *(_OWORD *)&pExecInfo.lpParameters = 0;
      pExecInfo.hwnd = 0;
      pExecInfo.lpVerb = 0;
      pExecInfo.lpFile = pszCanonicalized;
      memset(&pExecInfo.hInstApp, 0, 56);
      *(_QWORD *)&pExecInfo.nShow = 1;
      pExecInfo.fMask = 0x100000;
      if ( !ShellExecuteExW(&pExecInfo) )
        return (unsigned int)HrGetLastError();
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007b378  mov     [rsp-8+arg_8], rbx
0x18007b37d  mov     [rsp-8+arg_18], rdi
0x18007b382  push    rbp
0x18007b383  lea     rbp, [rsp-1220h]
0x18007b38b  mov     eax, 1320h
0x18007b390  call    _alloca_probe
0x18007b395  sub     rsp, rax
0x18007b398  mov     rax, cs:__security_cookie
0x18007b39f  xor     rax, rsp
0x18007b3a2  mov     [rbp+1220h+var_10], rax
0x18007b3a9  mov     rbx, r8
0x18007b3ac  mov     rdi, rcx
0x18007b3af  mov     r8d, 1048h; Size
0x18007b3b5  lea     rcx, [rbp+1220h+pszCanonicalized]; void *
0x18007b3bc  xor     edx, edx; Val
0x18007b3be  call    memset_0
0x18007b3c3  xor     r9d, r9d; dwFlags
0x18007b3c6  mov     [rsp+1320h+pcchCanonicalized], 824h
0x18007b3ce  lea     r8, [rsp+1320h+pcchCanonicalized]; pcchCanonicalized
0x18007b3d3  mov     rcx, rbx; pszUrl
0x18007b3d6  lea     rdx, [rbp+1220h+pszCanonicalized]; pszCanonicalized
0x18007b3dd  call    cs:__imp_UrlCanonicalizeW
0x18007b3e3  mov     ebx, eax
0x18007b3e5  test    eax, eax
0x18007b3e7  js      loc_18007B583
0x18007b3ed  mov     edx, 3; UrlIs
0x18007b3f2  lea     rcx, [rbp+1220h+pszCanonicalized]; pszUrl
0x18007b3f9  call    cs:__imp_UrlIsW
0x18007b3ff  mov     r8d, 9; nChar
0x18007b405  lea     rdx, [rbp+1220h+pszCanonicalized]; pszStr2
0x18007b40c  lea     rcx, pszStr1; "mshelp://"
0x18007b413  mov     ebx, eax
0x18007b415  call    cs:__imp_StrCmpNICW
0x18007b41b  test    eax, eax
0x18007b41d  jnz     short loc_18007B430
0x18007b41f  lea     rcx, [rbp+1220h+pszCanonicalized]
0x18007b426  call    ShowHelp
0x18007b42b  jmp     loc_18007B581
0x18007b430  test    ebx, ebx
0x18007b432  jz      loc_18007B522
0x18007b438  xor     edx, edx; Val
0x18007b43a  mov     [rsp+1320h+var_12F0], 0
0x18007b443  mov     r8d, 208h; Size
0x18007b449  lea     rcx, [rbp+1220h+pszPath]; void *
0x18007b44d  call    memset_0
0x18007b452  xor     r9d, r9d; dwFlags
0x18007b455  mov     [rsp+1320h+pcchPath], 104h
0x18007b45d  lea     r8, [rsp+1320h+pcchPath]; pcchPath
0x18007b462  lea     rdx, [rbp+1220h+pszPath]; pszPath
0x18007b466  lea     rcx, [rbp+1220h+pszCanonicalized]; pszUrl
0x18007b46d  call    cs:__imp_PathCreateFromUrlW
0x18007b473  mov     ebx, eax
0x18007b475  test    eax, eax
0x18007b477  js      loc_18007B501
0x18007b47d  lea     rcx, [rbp+1220h+pszPath]; pszPath
0x18007b481  call    cs:__imp_PathIsDirectoryW
0x18007b487  test    eax, eax
0x18007b489  jz      short loc_18007B498
0x18007b48b  lea     rcx, [rbp+1220h+pszPath]
0x18007b48f  call    _SafeExecuteDirectory
0x18007b494  mov     ebx, eax
0x18007b496  jmp     short loc_18007B501
0x18007b498  lea     r8, [rsp+1320h+var_12F0]; void **
0x18007b49d  call    ?CreateAttachmentServices@@YAJPEBGAEBU_GUID@@PEAPEAX@Z; CreateAttachmentServices(ushort const *,_GUID const &,void * *)
0x18007b4a2  mov     ebx, eax
0x18007b4a4  test    eax, eax
0x18007b4a6  js      short loc_18007B501
0x18007b4a8  mov     rcx, [rsp+1320h+var_12F0]
0x18007b4ad  lea     rdx, [rbp+1220h+pszPath]
0x18007b4b1  mov     rax, [rcx]
0x18007b4b4  mov     rax, [rax+28h]
0x18007b4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b4bd  mov     ebx, eax
0x18007b4bf  test    eax, eax
0x18007b4c1  js      short loc_18007B501
0x18007b4c3  mov     rcx, [rsp+1320h+var_12F0]
0x18007b4c8  mov     rax, [rcx]
0x18007b4cb  mov     rax, [rax+48h]
0x18007b4cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b4d4  mov     ebx, eax
0x18007b4d6  test    eax, eax
0x18007b4d8  jnz     short loc_18007B501
0x18007b4da  mov     rcx, [rsp+1320h+var_12F0]
0x18007b4df  lea     r8, aOpen_0; "open"
0x18007b4e6  xor     r9d, r9d
0x18007b4e9  mov     rdx, rdi
0x18007b4ec  mov     rax, [rcx]
0x18007b4ef  mov     rax, [rax+60h]
0x18007b4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b4f8  mov     ebx, eax
0x18007b4fa  xor     eax, eax
0x18007b4fc  test    ebx, ebx
0x18007b4fe  cmovns  ebx, eax
0x18007b501  mov     rcx, [rsp+1320h+var_12F0]
0x18007b506  test    rcx, rcx
0x18007b509  jz      short loc_18007B583
0x18007b50b  mov     [rsp+1320h+var_12F0], 0
0x18007b514  mov     rax, [rcx]
0x18007b517  mov     rax, [rax+10h]
0x18007b51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b520  jmp     short loc_18007B583
0x18007b522  xorps   xmm0, xmm0
0x18007b525  mov     [rsp+1320h+pExecInfo.cbSize], 70h ; 'p'
0x18007b52d  xor     ebx, ebx
0x18007b52f  movdqa  xmmword ptr [rsp+1320h+pExecInfo.lpParameters], xmm0
0x18007b535  lea     rax, [rbp+1220h+pszCanonicalized]
0x18007b53c  mov     [rsp+1320h+pExecInfo.hwnd], rbx
0x18007b541  lea     rcx, [rsp+1320h+pExecInfo]; pExecInfo
0x18007b546  mov     [rsp+1320h+pExecInfo.lpVerb], rbx
0x18007b54b  mov     [rsp+1320h+pExecInfo.lpFile], rax
0x18007b550  mov     [rsp+1320h+pExecInfo.hInstApp], rbx
0x18007b555  movups  xmmword ptr [rbp+1220h+pExecInfo.lpIDList], xmm0
0x18007b559  mov     qword ptr [rsp+1320h+pExecInfo.nShow], 1
0x18007b562  movups  xmmword ptr [rbp+1220h+pExecInfo.hkeyClass], xmm0
0x18007b566  mov     [rsp+1320h+pExecInfo.fMask], 100000h
0x18007b56e  movups  xmmword ptr [rbp+1220h+pExecInfo.60h], xmm0
0x18007b572  call    cs:__imp_ShellExecuteExW
0x18007b578  test    eax, eax
0x18007b57a  jnz     short loc_18007B583
0x18007b57c  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18007b581  mov     ebx, eax
0x18007b583  mov     eax, ebx
0x18007b585  mov     rcx, [rbp+1220h+var_10]
0x18007b58c  xor     rcx, rsp; StackCookie
0x18007b58f  call    __security_check_cookie
0x18007b594  lea     r11, [rsp+1320h+var_s0]
0x18007b59c  mov     rbx, [r11+18h]
0x18007b5a0  mov     rdi, [r11+28h]
0x18007b5a4  mov     rsp, r11
0x18007b5a7  pop     rbp
0x18007b5a8  retn
```
