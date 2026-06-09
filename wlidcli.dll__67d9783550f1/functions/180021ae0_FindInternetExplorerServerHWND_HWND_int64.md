# FindInternetExplorerServerHWND(HWND__ *,__int64)

- ea: `0x180021ae0`
- end: `0x180021c30`
- name: `?FindInternetExplorerServerHWND@@YAHPEAUHWND__@@_J@Z`
- size: `336`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180002da0`
- `0x18000e870`
- `0x18000e9a4`
- `0x180021ae0`
- `0x18005b8e4`

## import_xrefs

- `USER32!IsWindowEnabled` at `0x180021b9b`
- `USER32!IsWindowEnabled` at `0x180021b9b`
- `USER32!FindWindowExW` at `0x180021b86`
- `USER32!FindWindowExW` at `0x180021bb5`
- `USER32!FindWindowExW` at `0x180021bd1`
- `USER32!FindWindowExW` at `0x180021beb`
- `USER32!FindWindowExW` at `0x180021b86`
- `USER32!FindWindowExW` at `0x180021bb5`
- `USER32!FindWindowExW` at `0x180021bd1`
- `USER32!FindWindowExW` at `0x180021beb`
- `USER32!GetWindowThreadProcessId` at `0x180021b37`
- `USER32!GetWindowThreadProcessId` at `0x180021b37`
- `USER32!GetClassNameW` at `0x180021b4b`
- `USER32!GetClassNameW` at `0x180021b4b`

## pseudocode

```c
__int64 __fastcall FindInternetExplorerServerHWND(HWND a1, __int64 a2)
{
  unsigned int v4; // edi
  int v5; // r8d
  HWND Window; // rax
  HWND v7; // rdx
  HWND v8; // rax
  HWND v9; // rbx
  HWND v10; // rax
  const unsigned __int16 *dwProcessId; // [rsp+20h] [rbp-248h] BYREF
  WCHAR ClassName[264]; // [rsp+30h] [rbp-238h] BYREF

  LODWORD(dwProcessId) = 0;
  v4 = 1;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\launchbrowser.cpp",
    "FindInternetExplorerServerHWND",
    (const char *)0x7C,
    0,
    dwProcessId);
  GetWindowThreadProcessId(a1, (LPDWORD)&dwProcessId);
  GetClassNameW(a1, ClassName, 260);
  if ( (_DWORD)dwProcessId == *(_DWORD *)a2 && !wcscmp_0(ClassName, L"IEFrame") )
  {
    Window = FindWindowExW(a1, 0, L"Shell DocObject View", 0);
    v7 = 0;
    if ( Window )
    {
LABEL_10:
      v10 = FindWindowExW(Window, 0, L"Internet Explorer_Server", 0);
      if ( v10 )
      {
        v4 = 0;
        *(_QWORD *)(a2 + 8) = v10;
      }
    }
    else
    {
      while ( 1 )
      {
        v8 = FindWindowExW(a1, v7, L"TabWindowClass", 0);
        v9 = v8;
        if ( !v8 )
          break;
        if ( IsWindowEnabled(v8) )
        {
          Window = FindWindowExW(v9, 0, L"Shell DocObject View", 0);
          if ( !Window )
            break;
          goto LABEL_10;
        }
        v7 = v9;
      }
    }
  }
  MsaTracingInternal::TraceFunctionExit((MsaTracingInternal *)"FindInternetExplorerServerHWND", (const char *)v4, v5);
  return v4;
}

```

## disassembly

```asm
0x180021ae0  mov     [rsp+arg_10], rbx
0x180021ae5  push    rsi
0x180021ae6  push    rdi
0x180021ae7  push    r14
0x180021ae9  sub     rsp, 250h
0x180021af0  mov     rax, cs:__security_cookie
0x180021af7  xor     rax, rsp
0x180021afa  mov     [rsp+268h+var_28], rax
0x180021b02  mov     r14, rdx
0x180021b05  mov     dword ptr [rsp+268h+dwProcessId], 0; unsigned __int16 *
0x180021b0d  mov     rsi, rcx
0x180021b10  lea     rdx, aFindinternetex; "FindInternetExplorerServerHWND"
0x180021b17  mov     edi, 1
0x180021b1c  lea     rcx, aClientcoreDsEx_4; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180021b23  xor     r9d, r9d; unsigned int
0x180021b26  lea     r8d, [rdi+7Bh]; char *
0x180021b2a  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180021b2f  lea     rdx, [rsp+268h+dwProcessId]; lpdwProcessId
0x180021b34  mov     rcx, rsi; hWnd
0x180021b37  call    cs:__imp_GetWindowThreadProcessId
0x180021b3d  mov     r8d, 104h; nMaxCount
0x180021b43  lea     rdx, [rsp+268h+ClassName]; lpClassName
0x180021b48  mov     rcx, rsi; hWnd
0x180021b4b  call    cs:__imp_GetClassNameW
0x180021b51  mov     eax, [r14]
0x180021b54  cmp     dword ptr [rsp+268h+dwProcessId], eax
0x180021b58  jnz     loc_180021BFC
0x180021b5e  lea     rdx, aIeframe; "IEFrame"
0x180021b65  lea     rcx, [rsp+268h+ClassName]; String1
0x180021b6a  call    wcscmp_0
0x180021b6f  test    eax, eax
0x180021b71  jnz     loc_180021BFC
0x180021b77  xor     r9d, r9d; lpszWindow
0x180021b7a  lea     r8, aShellDocobject; "Shell DocObject View"
0x180021b81  xor     edx, edx; hWndChildAfter
0x180021b83  mov     rcx, rsi; hWndParent
0x180021b86  call    cs:__imp_FindWindowExW
0x180021b8c  xor     r9d, r9d
0x180021b8f  xor     edx, edx
0x180021b91  test    rax, rax
0x180021b94  jnz     short loc_180021BE1
0x180021b96  jmp     short loc_180021BAB
0x180021b98  mov     rcx, rbx; hWnd
0x180021b9b  call    cs:__imp_IsWindowEnabled
0x180021ba1  xor     r9d, r9d; lpszWindow
0x180021ba4  test    eax, eax
0x180021ba6  jnz     short loc_180021BC5
0x180021ba8  mov     rdx, rbx; hWndChildAfter
0x180021bab  lea     r8, aTabwindowclass; "TabWindowClass"
0x180021bb2  mov     rcx, rsi; hWndParent
0x180021bb5  call    cs:__imp_FindWindowExW
0x180021bbb  mov     rbx, rax
0x180021bbe  test    rax, rax
0x180021bc1  jnz     short loc_180021B98
0x180021bc3  jmp     short loc_180021BFC
0x180021bc5  lea     r8, aShellDocobject; "Shell DocObject View"
0x180021bcc  xor     edx, edx; hWndChildAfter
0x180021bce  mov     rcx, rbx; hWndParent
0x180021bd1  call    cs:__imp_FindWindowExW
0x180021bd7  test    rax, rax
0x180021bda  jz      short loc_180021BFC
0x180021bdc  xor     r9d, r9d; lpszWindow
0x180021bdf  xor     edx, edx; hWndChildAfter
0x180021be1  lea     r8, aInternetExplor; "Internet Explorer_Server"
0x180021be8  mov     rcx, rax; hWndParent
0x180021beb  call    cs:__imp_FindWindowExW
0x180021bf1  test    rax, rax
0x180021bf4  jz      short loc_180021BFC
0x180021bf6  xor     edi, edi
0x180021bf8  mov     [r14+8], rax
0x180021bfc  mov     edx, edi; char *
0x180021bfe  lea     rcx, aFindinternetex; "FindInternetExplorerServerHWND"
0x180021c05  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x180021c0a  mov     eax, edi
0x180021c0c  mov     rcx, [rsp+268h+var_28]
0x180021c14  xor     rcx, rsp; StackCookie
0x180021c17  call    __security_check_cookie
0x180021c1c  mov     rbx, [rsp+268h+arg_10]
0x180021c24  add     rsp, 250h
0x180021c2b  pop     r14
0x180021c2d  pop     rdi
0x180021c2e  pop     rsi
0x180021c2f  retn
```
