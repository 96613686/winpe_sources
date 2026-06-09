# ComHandlerBase::SetDefaultName(void)

- ea: `0x18007d35c`
- end: `0x18007d504`
- name: `?SetDefaultName@ComHandlerBase@@IEAAXXZ`
- size: `424`
- prototype: `void __fastcall(ComHandlerBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a530`

## callees

- `0x1800339c0`
- `0x18007d35c`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d418`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d48b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d418`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d48b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d444`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d4b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d444`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d4b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d45e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d4de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d45e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d4de`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007d3e3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18007d3e3`

## string_xrefs

- `0x18007d382`: `Wow6432Node\CLSID\`

## pseudocode

```c
void __fastcall ComHandlerBase::SetDefaultName(ComHandlerBase *this)
{
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR v5[18]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v7[90]; // [rsp+66h] [rbp-9Ah] BYREF
  OLECHAR Data[256]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  wcscpy(v5, L"Wow6432Node\\CLID\\");
  memset_0(v7, 0, 0x52u);
  Type = 0;
  cbData = 0;
  if ( StringFromGUID2((const GUID *const)((char *)this + 40), &sz, 42) )
  {
    cbData = 510;
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, &v5[12], 0, 0x20019u, &hKey) )
    {
      if ( !RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)Data, &cbData) && Type - 1 <= 1 )
      {
LABEL_9:
        _bstr_t::operator=((BSTR **)this + 8, Data);
LABEL_10:
        RegCloseKey(hKey);
        return;
      }
      RegCloseKey(hKey);
    }
    cbData = 510;
    if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, v5, 0, 0x20019u, &hKey) )
      return;
    if ( RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)Data, &cbData) || Type - 1 > 1 )
      goto LABEL_10;
    goto LABEL_9;
  }
}

```

## disassembly

```asm
0x18007d35c  mov     [rsp-8+arg_8], rbx
0x18007d361  push    rbp
0x18007d362  lea     rbp, [rsp-1D0h]
0x18007d36a  sub     rsp, 2D0h
0x18007d371  mov     rax, cs:__security_cookie
0x18007d378  xor     rax, rsp
0x18007d37b  mov     [rbp+1D0h+var_10], rax
0x18007d382  movups  xmm0, xmmword ptr cs:aWow6432nodeCls; "Wow6432Node\\CLSID\\"
0x18007d389  xor     edx, edx; Val
0x18007d38b  mov     rbx, rcx
0x18007d38e  movups  xmm1, xmmword ptr cs:aWow6432nodeCls+10h; "ode\\CLSID\\"
0x18007d395  lea     rcx, [rsp+2D0h+var_26A]; void *
0x18007d39a  mov     [rsp+2D0h+hKey], 0
0x18007d3a3  movaps  xmmword ptr [rsp+2D0h+var_290], xmm0
0x18007d3a8  movsd   xmm0, qword ptr cs:aWow6432nodeCls+1Eh; "ID\\"
0x18007d3b0  lea     r8d, [rdx+52h]; Size
0x18007d3b4  movaps  xmmword ptr [rsp+2D0h+SubKey], xmm1
0x18007d3b9  movsd   qword ptr [rsp+2D0h+SubKey+0Eh], xmm0
0x18007d3bf  call    memset_0
0x18007d3c4  lea     rcx, [rbx+28h]; rguid
0x18007d3c8  mov     [rsp+2D0h+Type], 0
0x18007d3d0  mov     r8d, 2Ah ; '*'; cchMax
0x18007d3d6  mov     [rsp+2D0h+cbData], 0
0x18007d3de  lea     rdx, [rsp+2D0h+sz]; lpsz
0x18007d3e3  call    cs:__imp_StringFromGUID2
0x18007d3e9  test    eax, eax
0x18007d3eb  jz      loc_18007D4E4
0x18007d3f1  lea     rax, [rsp+2D0h+hKey]
0x18007d3f6  mov     [rsp+2D0h+cbData], 1FEh
0x18007d3fe  mov     r9d, 20019h; samDesired
0x18007d404  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007d409  xor     r8d, r8d; ulOptions
0x18007d40c  lea     rdx, [rsp+2D0h+SubKey+8]; lpSubKey
0x18007d411  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18007d418  call    cs:__imp_RegOpenKeyExW
0x18007d41e  test    eax, eax
0x18007d420  jnz     short loc_18007D464
0x18007d422  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007d427  lea     rax, [rsp+2D0h+cbData]
0x18007d42c  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x18007d431  lea     r9, [rsp+2D0h+Type]; lpType
0x18007d436  lea     rax, [rbp+1D0h+Data]
0x18007d43a  xor     r8d, r8d; lpReserved
0x18007d43d  xor     edx, edx; lpValueName
0x18007d43f  mov     [rsp+2D0h+phkResult], rax; lpData
0x18007d444  call    cs:__imp_RegQueryValueExW
0x18007d44a  test    eax, eax
0x18007d44c  jnz     short loc_18007D459
0x18007d44e  mov     eax, [rsp+2D0h+Type]
0x18007d452  dec     eax
0x18007d454  cmp     eax, 1
0x18007d457  jbe     short loc_18007D4CC
0x18007d459  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007d45e  call    cs:__imp_RegCloseKey
0x18007d464  lea     rax, [rsp+2D0h+hKey]
0x18007d469  mov     [rsp+2D0h+cbData], 1FEh
0x18007d471  mov     r9d, 20019h; samDesired
0x18007d477  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18007d47c  xor     r8d, r8d; ulOptions
0x18007d47f  lea     rdx, [rsp+2D0h+var_290]; lpSubKey
0x18007d484  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18007d48b  call    cs:__imp_RegOpenKeyExW
0x18007d491  test    eax, eax
0x18007d493  jnz     short loc_18007D4E4
0x18007d495  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007d49a  lea     rax, [rsp+2D0h+cbData]
0x18007d49f  mov     [rsp+2D0h+lpcbData], rax; lpcbData
0x18007d4a4  lea     r9, [rsp+2D0h+Type]; lpType
0x18007d4a9  lea     rax, [rbp+1D0h+Data]
0x18007d4ad  xor     r8d, r8d; lpReserved
0x18007d4b0  xor     edx, edx; lpValueName
0x18007d4b2  mov     [rsp+2D0h+phkResult], rax; lpData
0x18007d4b7  call    cs:__imp_RegQueryValueExW
0x18007d4bd  test    eax, eax
0x18007d4bf  jnz     short loc_18007D4D9
0x18007d4c1  mov     eax, [rsp+2D0h+Type]
0x18007d4c5  dec     eax
0x18007d4c7  cmp     eax, 1
0x18007d4ca  ja      short loc_18007D4D9
0x18007d4cc  lea     rdx, [rbp+1D0h+Data]
0x18007d4d0  lea     rcx, [rbx+40h]
0x18007d4d4  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18007d4d9  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18007d4de  call    cs:__imp_RegCloseKey
0x18007d4e4  mov     rcx, [rbp+1D0h+var_10]
0x18007d4eb  xor     rcx, rsp; StackCookie
0x18007d4ee  call    __security_check_cookie
0x18007d4f3  mov     rbx, [rsp+2D0h+arg_8]
0x18007d4fb  add     rsp, 2D0h
0x18007d502  pop     rbp
0x18007d503  retn
```
