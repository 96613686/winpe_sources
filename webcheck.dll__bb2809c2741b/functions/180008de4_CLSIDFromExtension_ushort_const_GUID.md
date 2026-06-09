# _CLSIDFromExtension(ushort const *,_GUID *)

- ea: `0x180008de4`
- end: `0x180008e98`
- name: `?_CLSIDFromExtension@@YAJPEBGPEAU_GUID@@@Z`
- size: `180`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCLSID pclsid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009330`

## callees

- `0x180008648`
- `0x180008de4`
- `0x180029280`

## import_xrefs

- `ADVAPI32!RegQueryValueW` at `0x180008e1e`
- `ADVAPI32!RegQueryValueW` at `0x180008e5d`
- `ADVAPI32!RegQueryValueW` at `0x180008e1e`
- `ADVAPI32!RegQueryValueW` at `0x180008e5d`
- `ole32!CLSIDFromString` at `0x180008e72`
- `ole32!CLSIDFromString` at `0x180008e72`

## string_xrefs

- `0x180008e28`: `\CLSID`

## pseudocode

```c
HRESULT __fastcall _CLSIDFromExtension(LPCWSTR lpSubKey, LPCLSID pclsid)
{
  LONG cbData[4]; // [rsp+20h] [rbp-168h] BYREF
  WCHAR Data[80]; // [rsp+30h] [rbp-158h] BYREF
  WCHAR sz[80]; // [rsp+D0h] [rbp-B8h] BYREF

  cbData[0] = 160;
  if ( RegQueryValueW(HKEY_CLASSES_ROOT, lpSubKey, Data, cbData) )
    return -2147467259;
  StringCchCatW(Data, 0x50u, L"\\CLSID");
  cbData[0] = 160;
  if ( RegQueryValueW(HKEY_CLASSES_ROOT, Data, sz, cbData) )
    return -2147467259;
  else
    return CLSIDFromString(sz, pclsid);
}

```

## disassembly

```asm
0x180008de4  push    rbx
0x180008de6  sub     rsp, 180h
0x180008ded  mov     rax, cs:__security_cookie
0x180008df4  xor     rax, rsp
0x180008df7  mov     [rsp+188h+var_18], rax
0x180008dff  mov     rbx, rdx
0x180008e02  mov     [rsp+188h+cbData], 0A0h
0x180008e0a  mov     rdx, rcx; lpSubKey
0x180008e0d  lea     r9, [rsp+188h+cbData]; lpcbData
0x180008e12  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180008e19  lea     r8, [rsp+188h+Data]; lpData
0x180008e1e  call    cs:__imp_RegQueryValueW
0x180008e24  test    eax, eax
0x180008e26  jnz     short loc_180008E7A
0x180008e28  lea     r8, aClsid; "\\CLSID"
0x180008e2f  lea     edx, [rax+50h]; unsigned __int64
0x180008e32  lea     rcx, [rsp+188h+Data]; unsigned __int16 *
0x180008e37  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008e3c  lea     r9, [rsp+188h+cbData]; lpcbData
0x180008e41  mov     [rsp+188h+cbData], 0A0h
0x180008e49  lea     r8, [rsp+188h+sz]; lpData
0x180008e51  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180008e58  lea     rdx, [rsp+188h+Data]; lpSubKey
0x180008e5d  call    cs:__imp_RegQueryValueW
0x180008e63  test    eax, eax
0x180008e65  jnz     short loc_180008E7A
0x180008e67  mov     rdx, rbx; pclsid
0x180008e6a  lea     rcx, [rsp+188h+sz]; lpsz
0x180008e72  call    cs:__imp_CLSIDFromString
0x180008e78  jmp     short loc_180008E7F
0x180008e7a  mov     eax, 80004005h
0x180008e7f  mov     rcx, [rsp+188h+var_18]
0x180008e87  xor     rcx, rsp; StackCookie
0x180008e8a  call    __security_check_cookie
0x180008e8f  add     rsp, 180h
0x180008e96  pop     rbx
0x180008e97  retn
```
