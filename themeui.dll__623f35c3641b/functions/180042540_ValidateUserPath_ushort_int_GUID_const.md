# ValidateUserPath(ushort *,int,_GUID const &)

- ea: `0x180042540`
- end: `0x18004265e`
- name: `?ValidateUserPath@@YAJPEAGHAEBU_GUID@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, const struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800423d0`
- `0x180042470`

## callees

- `0x18000ab10`
- `0x1800358c0`
- `0x180042540`
- `0x180060460`

## import_xrefs

- `SHELL32!SHGetKnownFolderPath` at `0x1800425b0`
- `SHELL32!SHGetKnownFolderPath` at `0x1800425b0`
- `SHLWAPI!PathFileExistsW` at `0x180042571`
- `SHLWAPI!PathFileExistsW` at `0x180042609`
- `SHLWAPI!PathFileExistsW` at `0x180042571`
- `SHLWAPI!PathFileExistsW` at `0x180042609`
- `SHLWAPI!StrStrW` at `0x180042589`
- `SHLWAPI!StrStrW` at `0x1800425e0`
- `SHLWAPI!StrStrW` at `0x180042589`
- `SHLWAPI!StrStrW` at `0x1800425e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042633`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042633`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800425fa`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800425fa`

## pseudocode

```c
__int64 __fastcall ValidateUserPath(unsigned __int16 *a1, unsigned int a2, const struct _GUID *a3)
{
  int v5; // ebx
  const WCHAR *v6; // rsi
  PWSTR v7; // rax
  PWSTR ppszPath; // [rsp+20h] [rbp-248h] BYREF
  WCHAR pszFirst[264]; // [rsp+30h] [rbp-238h] BYREF

  v5 = 0;
  PathExpandEnvStringsWrap(a1, a2);
  if ( !PathFileExistsW(a1) )
  {
    v6 = StrStrW(a1, L"AppData");
    if ( v6 )
    {
      ppszPath = 0;
      if ( SHGetKnownFolderPath(a3, 0x8000u, 0, &ppszPath) >= 0 )
      {
        if ( (int)StringCchCopyW(pszFirst, 0x104u, ppszPath) >= 0 )
        {
          v7 = StrStrW(pszFirst, L"AppData");
          if ( v7 )
          {
            *v7 = 0;
            if ( PathCchAppend(pszFirst, 0x104u, v6) >= 0 )
            {
              if ( PathFileExistsW(pszFirst) )
              {
                v5 = StringCchCopyW(a1, 0x104u, pszFirst);
                if ( v5 >= 0 )
                  v5 = 1;
              }
            }
          }
        }
        CoTaskMemFree(ppszPath);
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180042540  mov     [rsp+arg_8], rbx
0x180042545  push    rbp
0x180042546  push    rsi
0x180042547  push    rdi
0x180042548  sub     rsp, 250h
0x18004254f  mov     rax, cs:__security_cookie
0x180042556  xor     rax, rsp
0x180042559  mov     [rsp+268h+var_28], rax
0x180042561  mov     rbp, r8
0x180042564  mov     rdi, rcx
0x180042567  xor     ebx, ebx
0x180042569  call    ?PathExpandEnvStringsWrap@@YAXPEAGK@Z; PathExpandEnvStringsWrap(ushort *,ulong)
0x18004256e  mov     rcx, rdi; pszPath
0x180042571  call    cs:__imp_PathFileExistsW
0x180042577  test    eax, eax
0x180042579  jnz     loc_180042639
0x18004257f  lea     rdx, aAppdata; "AppData"
0x180042586  mov     rcx, rdi; pszFirst
0x180042589  call    cs:__imp_StrStrW
0x18004258f  mov     rsi, rax
0x180042592  test    rax, rax
0x180042595  jz      loc_180042639
0x18004259b  lea     r9, [rsp+268h+ppszPath]; ppszPath
0x1800425a0  mov     [rsp+268h+ppszPath], rbx
0x1800425a5  xor     r8d, r8d; hToken
0x1800425a8  mov     edx, 8000h; dwFlags
0x1800425ad  mov     rcx, rbp; rfid
0x1800425b0  call    cs:__imp_SHGetKnownFolderPath
0x1800425b6  test    eax, eax
0x1800425b8  js      short loc_180042639
0x1800425ba  mov     r8, [rsp+268h+ppszPath]; unsigned __int16 *
0x1800425bf  lea     rcx, [rsp+268h+pszFirst]; unsigned __int16 *
0x1800425c4  mov     ebp, 104h
0x1800425c9  mov     edx, ebp; unsigned __int64
0x1800425cb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800425d0  test    eax, eax
0x1800425d2  js      short loc_18004262E
0x1800425d4  lea     rdx, aAppdata; "AppData"
0x1800425db  lea     rcx, [rsp+268h+pszFirst]; pszFirst
0x1800425e0  call    cs:__imp_StrStrW
0x1800425e6  test    rax, rax
0x1800425e9  jz      short loc_18004262E
0x1800425eb  xor     ecx, ecx
0x1800425ed  mov     r8, rsi; pszMore
0x1800425f0  mov     [rax], cx
0x1800425f3  mov     edx, ebp; cchPath
0x1800425f5  lea     rcx, [rsp+268h+pszFirst]; pszPath
0x1800425fa  call    cs:__imp_PathCchAppend
0x180042600  test    eax, eax
0x180042602  js      short loc_18004262E
0x180042604  lea     rcx, [rsp+268h+pszFirst]; pszPath
0x180042609  call    cs:__imp_PathFileExistsW
0x18004260f  test    eax, eax
0x180042611  jz      short loc_18004262E
0x180042613  lea     r8, [rsp+268h+pszFirst]; unsigned __int16 *
0x180042618  mov     edx, ebp; unsigned __int64
0x18004261a  mov     rcx, rdi; unsigned __int16 *
0x18004261d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180042622  mov     ebx, eax
0x180042624  mov     eax, 1
0x180042629  test    ebx, ebx
0x18004262b  cmovns  ebx, eax
0x18004262e  mov     rcx, [rsp+268h+ppszPath]; pv
0x180042633  call    cs:__imp_CoTaskMemFree
0x180042639  mov     eax, ebx
0x18004263b  mov     rcx, [rsp+268h+var_28]
0x180042643  xor     rcx, rsp; StackCookie
0x180042646  call    __security_check_cookie
0x18004264b  mov     rbx, [rsp+268h+arg_8]
0x180042653  add     rsp, 250h
0x18004265a  pop     rdi
0x18004265b  pop     rsi
0x18004265c  pop     rbp
0x18004265d  retn
```
