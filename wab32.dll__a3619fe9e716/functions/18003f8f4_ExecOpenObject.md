# ExecOpenObject

- ea: `0x18003f8f4`
- end: `0x18003fa78`
- name: `ExecOpenObject`
- size: `388`
- prototype: `__int64 __fastcall(LPCWSTR lpParameters)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003fb90`
- `0x18003fd70`
- `0x180040000`

## callees

- `0x1800045e4`
- `0x18003f8f4`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x18003fa57`
- `SHELL32!ShellExecuteW` at `0x18003fa57`
- `ADVAPI32!RegOpenKeyExW` at `0x18003f96a`
- `ADVAPI32!RegOpenKeyExW` at `0x18003f96a`
- `ADVAPI32!RegCloseKey` at `0x18003fa24`
- `ADVAPI32!RegCloseKey` at `0x18003fa24`
- `ADVAPI32!RegQueryValueExW` at `0x18003f9ae`
- `ADVAPI32!RegQueryValueExW` at `0x18003f9ae`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003f9d1`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003f9d1`

## string_xrefs

- `0x18003f95c`: `Software\Microsoft\Windows\CurrentVersion\App Paths\wab.exe`

## pseudocode

```c
HINSTANCE __fastcall ExecOpenObject(LPCWSTR lpParameters)
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
         L"Software\\Microsoft\\Windows\\CurrentVersion\\App Paths\\wab.exe",
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
    v2 = L"wab.exe";
  return ShellExecuteW(0, L"open", v2, lpParameters, 0, 1);
}

```

## disassembly

```asm
0x18003f8f4  push    rbp
0x18003f8f6  push    rbx
0x18003f8f7  push    rsi
0x18003f8f8  push    rdi
0x18003f8f9  lea     rbp, [rsp-388h]
0x18003f901  sub     rsp, 488h
0x18003f908  mov     rax, cs:__security_cookie
0x18003f90f  xor     rax, rsp
0x18003f912  mov     [rbp+3A0h+var_30], rax
0x18003f919  mov     rdi, rcx
0x18003f91c  xor     edx, edx; Val
0x18003f91e  lea     rcx, [rsp+4A0h+Data]; void *
0x18003f923  mov     r8d, 208h; Size
0x18003f929  call    memset_0
0x18003f92e  xor     edx, edx; Val
0x18003f930  lea     rcx, [rbp+3A0h+Dst]; void *
0x18003f937  mov     r8d, 208h; Size
0x18003f93d  call    memset_0
0x18003f942  lea     rax, [rsp+4A0h+hKey]
0x18003f947  xor     esi, esi
0x18003f949  mov     r9d, 20019h; samDesired
0x18003f94f  mov     [rsp+4A0h+phkResult], rax; phkResult
0x18003f954  xor     r8d, r8d; ulOptions
0x18003f957  mov     [rsp+4A0h+hKey], rsi
0x18003f95c  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003f963  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f96a  call    cs:__imp_RegOpenKeyExW
0x18003f970  test    eax, eax
0x18003f972  jnz     loc_18003FA34
0x18003f978  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18003f97d  lea     rax, [rsp+4A0h+cbData]
0x18003f982  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x18003f987  lea     r9, [rsp+4A0h+Type]; lpType
0x18003f98c  lea     rax, [rsp+4A0h+Data]
0x18003f991  mov     [rsp+4A0h+Type], esi
0x18003f995  xor     r8d, r8d; lpReserved
0x18003f998  mov     [rsp+4A0h+phkResult], rax; lpData
0x18003f99d  lea     rdx, Str; lpValueName
0x18003f9a4  mov     [rsp+4A0h+cbData], 208h
0x18003f9ac  mov     ebx, esi
0x18003f9ae  call    cs:__imp_RegQueryValueExW
0x18003f9b4  test    eax, eax
0x18003f9b6  jnz     short loc_18003FA1A
0x18003f9b8  cmp     [rsp+4A0h+Type], 2
0x18003f9bd  jnz     short loc_18003FA1A
0x18003f9bf  mov     r8d, 104h; nSize
0x18003f9c5  lea     rdx, [rbp+3A0h+Dst]; lpDst
0x18003f9cc  lea     rcx, [rsp+4A0h+Data]; lpSrc
0x18003f9d1  call    cs:__imp_ExpandEnvironmentStringsW
0x18003f9d7  mov     [rsp+4A0h+Type], eax
0x18003f9db  test    eax, eax
0x18003f9dd  jz      short loc_18003FA1A
0x18003f9df  lea     r8, [rbp+3A0h+Dst]; unsigned __int16 *
0x18003f9e6  mov     edx, 104h; unsigned __int64
0x18003f9eb  lea     rcx, [rsp+4A0h+Data]; unsigned __int16 *
0x18003f9f0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f9f5  test    eax, eax
0x18003f9f7  js      short loc_18003FA1A
0x18003f9f9  lea     rax, [rsp+4A0h+Data]
0x18003f9fe  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003fa02  inc     rcx
0x18003fa05  cmp     [rax+rcx*2], si
0x18003fa09  jnz     short loc_18003FA02
0x18003fa0b  test    rcx, rcx
0x18003fa0e  lea     rax, [rsp+4A0h+Data]
0x18003fa13  cmovz   rax, rbx
0x18003fa17  mov     rbx, rax
0x18003fa1a  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18003fa1f  test    rcx, rcx
0x18003fa22  jz      short loc_18003FA2F
0x18003fa24  call    cs:__imp_RegCloseKey
0x18003fa2a  mov     [rsp+4A0h+hKey], rsi
0x18003fa2f  test    rbx, rbx
0x18003fa32  jnz     short loc_18003FA3B
0x18003fa34  lea     rbx, aWabExe; "wab.exe"
0x18003fa3b  mov     dword ptr [rsp+4A0h+lpcbData], 1; nShowCmd
0x18003fa43  lea     rdx, aOpen_0; "open"
0x18003fa4a  mov     r9, rdi; lpParameters
0x18003fa4d  mov     [rsp+4A0h+phkResult], rsi; lpDirectory
0x18003fa52  mov     r8, rbx; lpFile
0x18003fa55  xor     ecx, ecx; hwnd
0x18003fa57  call    cs:__imp_ShellExecuteW
0x18003fa5d  mov     rcx, [rbp+3A0h+var_30]
0x18003fa64  xor     rcx, rsp; StackCookie
0x18003fa67  call    __security_check_cookie
0x18003fa6c  add     rsp, 488h
0x18003fa73  pop     rdi
0x18003fa74  pop     rsi
0x18003fa75  pop     rbx
0x18003fa76  pop     rbp
0x18003fa77  retn
```
