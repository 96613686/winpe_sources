# InternetTime_IsManualPeerListOn(void)

- ea: `0x180016ccc`
- end: `0x180016d96`
- name: `?InternetTime_IsManualPeerListOn@@YAHXZ`
- size: `202`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001c300`

## callees

- `0x180016ccc`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `SHLWAPI!SHGetValueW` at `0x180016d43`
- `SHLWAPI!SHGetValueW` at `0x180016d43`
- `SHLWAPI!__imp_StrCmpICW` at `0x180016d59`
- `SHLWAPI!__imp_StrCmpICW` at `0x180016d6f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180016d59`
- `SHLWAPI!__imp_StrCmpICW` at `0x180016d6f`

## string_xrefs

- `0x180016d35`: `System\CurrentControlSet\Services\W32Time\Parameters`

## pseudocode

```c
__int64 InternetTime_IsManualPeerListOn(void)
{
  unsigned int v0; // ebx
  DWORD pcbData; // [rsp+30h] [rbp-238h] BYREF
  DWORD pdwType[3]; // [rsp+34h] [rbp-234h] BYREF
  WCHAR pszStr1; // [rsp+40h] [rbp-228h] BYREF
  _BYTE v5[526]; // [rsp+42h] [rbp-226h] BYREF

  pszStr1 = 0;
  v0 = 1;
  memset_0(v5, 0, 0x206u);
  pcbData = 520;
  pdwType[0] = 0;
  if ( !SHGetValueW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\W32Time\\Parameters",
          L"Type",
          pdwType,
          &pszStr1,
          &pcbData)
    && (!StrCmpICW(&pszStr1, L"NT5DS") || !StrCmpICW(&pszStr1, L"NoSync")) )
  {
    return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x180016ccc  push    rbx
0x180016cce  sub     rsp, 260h
0x180016cd5  mov     rax, cs:__security_cookie
0x180016cdc  xor     rax, rsp
0x180016cdf  mov     [rsp+268h+var_18], rax
0x180016ce7  xor     eax, eax
0x180016ce9  lea     rcx, [rsp+268h+var_226]; void *
0x180016cee  xor     edx, edx; Val
0x180016cf0  mov     [rsp+268h+pszStr1], ax
0x180016cf5  mov     r8d, 206h; Size
0x180016cfb  mov     ebx, 1
0x180016d00  call    memset_0
0x180016d05  lea     rax, [rsp+268h+var_238]
0x180016d0a  mov     [rsp+268h+var_238], 208h
0x180016d12  mov     [rsp+268h+pcbData], rax; pcbData
0x180016d17  lea     r9, [rsp+268h+pdwType]; pdwType
0x180016d1c  lea     rax, [rsp+268h+pszStr1]
0x180016d21  mov     [rsp+268h+pdwType], 0
0x180016d29  lea     r8, aType; "Type"
0x180016d30  mov     [rsp+268h+pvData], rax; pvData
0x180016d35  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\W3"...
0x180016d3c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180016d43  call    cs:__imp_SHGetValueW
0x180016d49  test    eax, eax
0x180016d4b  jnz     short loc_180016D7B
0x180016d4d  lea     rdx, aNt5ds; "NT5DS"
0x180016d54  lea     rcx, [rsp+268h+pszStr1]; pszStr1
0x180016d59  call    cs:__imp_StrCmpICW
0x180016d5f  test    eax, eax
0x180016d61  jz      short loc_180016D79
0x180016d63  lea     rdx, aNosync; "NoSync"
0x180016d6a  lea     rcx, [rsp+268h+pszStr1]; pszStr1
0x180016d6f  call    cs:__imp_StrCmpICW
0x180016d75  test    eax, eax
0x180016d77  jnz     short loc_180016D7B
0x180016d79  xor     ebx, ebx
0x180016d7b  mov     eax, ebx
0x180016d7d  mov     rcx, [rsp+268h+var_18]
0x180016d85  xor     rcx, rsp; StackCookie
0x180016d88  call    __security_check_cookie
0x180016d8d  add     rsp, 260h
0x180016d94  pop     rbx
0x180016d95  retn
```
