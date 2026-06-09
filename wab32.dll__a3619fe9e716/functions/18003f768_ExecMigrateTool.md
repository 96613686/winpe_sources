# ExecMigrateTool

- ea: `0x18003f768`
- end: `0x18003f8ec`
- name: `ExecMigrateTool`
- size: `388`
- prototype: `__int64 __fastcall(LPCWSTR lpParameters)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003fd10`
- `0x18003fd40`

## callees

- `0x1800045e4`
- `0x18003f768`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x18003f8cb`
- `SHELL32!ShellExecuteW` at `0x18003f8cb`
- `ADVAPI32!RegOpenKeyExW` at `0x18003f7de`
- `ADVAPI32!RegOpenKeyExW` at `0x18003f7de`
- `ADVAPI32!RegCloseKey` at `0x18003f898`
- `ADVAPI32!RegCloseKey` at `0x18003f898`
- `ADVAPI32!RegQueryValueExW` at `0x18003f822`
- `ADVAPI32!RegQueryValueExW` at `0x18003f822`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003f845`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003f845`

## string_xrefs

- `0x18003f7d0`: `Software\Microsoft\Windows\CurrentVersion\App Paths\wabmig.exe`

## pseudocode

```c
HINSTANCE __fastcall ExecMigrateTool(LPCWSTR lpParameters)
{
  const WCHAR *v2; // rbx
  __int64 v3; // rcx
  const WCHAR *v4; // rax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Data[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Dst[264]; // [rsp+260h] [rbp+160h] BYREF

  memset_0(Data, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\App Paths\\wabmig.exe",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_14;
  }
  Type = 0;
  cbData[0] = 520;
  v2 = 0;
  if ( !RegQueryValueExW(hKey, &Str, 0, &Type, (LPBYTE)Data, cbData) && Type == 2 )
  {
    Type = ExpandEnvironmentStringsW(Data, Dst, 0x104u);
    if ( Type )
    {
      if ( (int)StringCchCopyW(Data, 0x104u, Dst) >= 0 )
      {
        v3 = -1;
        do
          ++v3;
        while ( Data[v3] );
        v4 = Data;
        if ( !v3 )
          v4 = 0;
        v2 = v4;
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( !v2 )
LABEL_14:
    v2 = L"wabmig.exe";
  return ShellExecuteW(0, L"open", v2, lpParameters, 0, 1);
}

```

## disassembly

```asm
0x18003f768  push    rbp
0x18003f76a  push    rbx
0x18003f76b  push    rsi
0x18003f76c  push    rdi
0x18003f76d  lea     rbp, [rsp-388h]
0x18003f775  sub     rsp, 488h
0x18003f77c  mov     rax, cs:__security_cookie
0x18003f783  xor     rax, rsp
0x18003f786  mov     [rbp+3A0h+var_30], rax
0x18003f78d  mov     rdi, rcx
0x18003f790  xor     edx, edx; Val
0x18003f792  lea     rcx, [rsp+4A0h+Data]; void *
0x18003f797  mov     r8d, 208h; Size
0x18003f79d  call    memset_0
0x18003f7a2  xor     edx, edx; Val
0x18003f7a4  lea     rcx, [rbp+3A0h+Dst]; void *
0x18003f7ab  mov     r8d, 208h; Size
0x18003f7b1  call    memset_0
0x18003f7b6  lea     rax, [rsp+4A0h+hKey]
0x18003f7bb  xor     esi, esi
0x18003f7bd  mov     r9d, 20019h; samDesired
0x18003f7c3  mov     [rsp+4A0h+phkResult], rax; phkResult
0x18003f7c8  xor     r8d, r8d; ulOptions
0x18003f7cb  mov     [rsp+4A0h+hKey], rsi
0x18003f7d0  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003f7d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f7de  call    cs:__imp_RegOpenKeyExW
0x18003f7e4  test    eax, eax
0x18003f7e6  jnz     loc_18003F8A8
0x18003f7ec  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18003f7f1  lea     rax, [rsp+4A0h+cbData]
0x18003f7f6  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x18003f7fb  lea     r9, [rsp+4A0h+Type]; lpType
0x18003f800  lea     rax, [rsp+4A0h+Data]
0x18003f805  mov     [rsp+4A0h+Type], esi
0x18003f809  xor     r8d, r8d; lpReserved
0x18003f80c  mov     [rsp+4A0h+phkResult], rax; lpData
0x18003f811  lea     rdx, Str; lpValueName
0x18003f818  mov     [rsp+4A0h+cbData], 208h
0x18003f820  mov     ebx, esi
0x18003f822  call    cs:__imp_RegQueryValueExW
0x18003f828  test    eax, eax
0x18003f82a  jnz     short loc_18003F88E
0x18003f82c  cmp     [rsp+4A0h+Type], 2
0x18003f831  jnz     short loc_18003F88E
0x18003f833  mov     r8d, 104h; nSize
0x18003f839  lea     rdx, [rbp+3A0h+Dst]; lpDst
0x18003f840  lea     rcx, [rsp+4A0h+Data]; lpSrc
0x18003f845  call    cs:__imp_ExpandEnvironmentStringsW
0x18003f84b  mov     [rsp+4A0h+Type], eax
0x18003f84f  test    eax, eax
0x18003f851  jz      short loc_18003F88E
0x18003f853  lea     r8, [rbp+3A0h+Dst]; unsigned __int16 *
0x18003f85a  mov     edx, 104h; unsigned __int64
0x18003f85f  lea     rcx, [rsp+4A0h+Data]; unsigned __int16 *
0x18003f864  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f869  test    eax, eax
0x18003f86b  js      short loc_18003F88E
0x18003f86d  lea     rax, [rsp+4A0h+Data]
0x18003f872  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003f876  inc     rcx
0x18003f879  cmp     [rax+rcx*2], si
0x18003f87d  jnz     short loc_18003F876
0x18003f87f  test    rcx, rcx
0x18003f882  lea     rax, [rsp+4A0h+Data]
0x18003f887  cmovz   rax, rbx
0x18003f88b  mov     rbx, rax
0x18003f88e  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18003f893  test    rcx, rcx
0x18003f896  jz      short loc_18003F8A3
0x18003f898  call    cs:__imp_RegCloseKey
0x18003f89e  mov     [rsp+4A0h+hKey], rsi
0x18003f8a3  test    rbx, rbx
0x18003f8a6  jnz     short loc_18003F8AF
0x18003f8a8  lea     rbx, aWabmigExe; "wabmig.exe"
0x18003f8af  mov     dword ptr [rsp+4A0h+lpcbData], 1; nShowCmd
0x18003f8b7  lea     rdx, aOpen_0; "open"
0x18003f8be  mov     r9, rdi; lpParameters
0x18003f8c1  mov     [rsp+4A0h+phkResult], rsi; lpDirectory
0x18003f8c6  mov     r8, rbx; lpFile
0x18003f8c9  xor     ecx, ecx; hwnd
0x18003f8cb  call    cs:__imp_ShellExecuteW
0x18003f8d1  mov     rcx, [rbp+3A0h+var_30]
0x18003f8d8  xor     rcx, rsp; StackCookie
0x18003f8db  call    __security_check_cookie
0x18003f8e0  add     rsp, 488h
0x18003f8e7  pop     rdi
0x18003f8e8  pop     rsi
0x18003f8e9  pop     rbx
0x18003f8ea  pop     rbp
0x18003f8eb  retn
```
