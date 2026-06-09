# NetpGetWinRegConfigMaxSizes

- ea: `0x180007cf4`
- end: `0x180007de4`
- name: `NetpGetWinRegConfigMaxSizes`
- size: `240`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800075cc`
- `0x180007acc`
- `0x180007dec`

## callees

- `0x180007cf4`
- `0x18001fbd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007daa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180007daa`

## pseudocode

```c
LSTATUS __fastcall NetpGetWinRegConfigMaxSizes(HKEY a1, __int64 a2, DWORD *a3)
{
  LSTATUS result; // eax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-29h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+64h] [rbp-25h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-21h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-1Dh] BYREF
  DWORD cbMaxClassLen; // [rsp+70h] [rbp-19h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+74h] [rbp-15h] BYREF
  DWORD cSubKeys; // [rsp+78h] [rbp-11h] BYREF
  DWORD cchClass; // [rsp+7Ch] [rbp-Dh] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+80h] [rbp-9h] BYREF
  WCHAR Class[32]; // [rsp+90h] [rbp+7h] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  cchClass = 32;
  result = RegQueryInfoKeyW(
             a1,
             Class,
             &cchClass,
             0,
             &cSubKeys,
             &cbMaxSubKeyLen,
             &cbMaxClassLen,
             &cValues,
             &cbMaxValueNameLen,
             &cbMaxValueLen,
             &cbSecurityDescriptor,
             &ftLastWriteTime);
  if ( !result )
  {
    if ( a3 )
      *a3 = cbMaxValueLen;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007cf4  mov     [rsp-8+arg_8], rbx
0x180007cf9  push    rbp
0x180007cfa  lea     rbp, [rsp-57h]
0x180007cff  sub     rsp, 0E0h
0x180007d06  mov     rax, cs:__security_cookie
0x180007d0d  xor     rax, rsp
0x180007d10  mov     [rbp+57h+var_10], rax
0x180007d14  lea     rax, [rbp+57h+ftLastWriteTime]
0x180007d18  mov     [rbp+57h+cSubKeys], 0
0x180007d1f  mov     [rsp+0E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007d24  lea     rdx, [rbp+57h+Class]; lpClass
0x180007d28  lea     rax, [rbp+57h+cbSecurityDescriptor]
0x180007d2c  mov     [rbp+57h+cbMaxSubKeyLen], 0
0x180007d33  mov     [rsp+0E0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x180007d38  mov     rbx, r8
0x180007d3b  lea     rax, [rbp+57h+cbMaxValueLen]
0x180007d3f  mov     [rbp+57h+cbMaxClassLen], 0
0x180007d46  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180007d4b  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x180007d4f  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180007d53  mov     [rbp+57h+cValues], 0
0x180007d5a  mov     [rsp+0E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180007d5f  xor     r9d, r9d; lpReserved
0x180007d62  lea     rax, [rbp+57h+cValues]
0x180007d66  mov     [rbp+57h+cbMaxValueNameLen], 0
0x180007d6d  mov     [rsp+0E0h+lpcValues], rax; lpcValues
0x180007d72  lea     rax, [rbp+57h+cbMaxClassLen]
0x180007d76  mov     [rsp+0E0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x180007d7b  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180007d7f  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180007d84  lea     rax, [rbp+57h+cSubKeys]
0x180007d88  mov     [rsp+0E0h+lpcSubKeys], rax; lpcSubKeys
0x180007d8d  mov     [rbp+57h+cbMaxValueLen], 0
0x180007d94  mov     [rbp+57h+cbSecurityDescriptor], 0
0x180007d9b  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], 0
0x180007da3  mov     [rbp+57h+cchClass], 20h ; ' '
0x180007daa  call    cs:__imp_RegQueryInfoKeyW
0x180007db1  nop     dword ptr [rax+rax+00h]
0x180007db6  test    eax, eax
0x180007db8  jnz     short loc_180007DC6
0x180007dba  test    rbx, rbx
0x180007dbd  jz      short loc_180007DC4
0x180007dbf  mov     eax, [rbp+57h+cbMaxValueLen]
0x180007dc2  mov     [rbx], eax
0x180007dc4  xor     eax, eax
0x180007dc6  mov     rcx, [rbp+57h+var_10]
0x180007dca  xor     rcx, rsp; StackCookie
0x180007dcd  call    __security_check_cookie
0x180007dd2  mov     rbx, [rsp+0E0h+arg_8]
0x180007dda  add     rsp, 0E0h
0x180007de1  pop     rbp
0x180007de2  retn
```
