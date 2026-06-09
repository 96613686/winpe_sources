# GetEUDCImage

- ea: `0x18001ef44`
- end: `0x18001f115`
- name: `GetEUDCImage`
- size: `465`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, registry_config`

## callers

- `0x18001f950`
- `0x18001fcb0`

## callees

- `0x180019dc0`
- `0x18001ba0c`
- `0x18001edf0`
- `0x18001ef44`
- `0x18001f11c`
- `0x18001f470`
- `0x180023434`
- `0x18002a590`

## import_xrefs

- `KERNEL32!RegOpenKeyExA` at `0x18001efd2`
- `KERNEL32!RegOpenKeyExA` at `0x18001efd2`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18001f0ba`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18001f0ba`
- `KERNEL32!GetACP` at `0x18001ef8e`
- `KERNEL32!GetACP` at `0x18001ef8e`
- `KERNEL32!RegQueryValueExA` at `0x18001f03c`
- `KERNEL32!RegQueryValueExA` at `0x18001f076`
- `KERNEL32!RegQueryValueExA` at `0x18001f03c`
- `KERNEL32!RegQueryValueExA` at `0x18001f076`
- `KERNEL32!RegCloseKey` at `0x18001eff1`
- `KERNEL32!RegCloseKey` at `0x18001f085`
- `KERNEL32!RegCloseKey` at `0x18001f100`
- `KERNEL32!RegCloseKey` at `0x18001eff1`
- `KERNEL32!RegCloseKey` at `0x18001f085`
- `KERNEL32!RegCloseKey` at `0x18001f100`

## pseudocode

```c
__int64 __fastcall GetEUDCImage(HDC hdc, unsigned __int8 **a2, unsigned int *a3)
{
  UINT ACP; // eax
  __int64 AllocOtm; // rax
  void *v8; // rbx
  unsigned int v10; // edi
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE Data[259]; // [rsp+40h] [rbp-C0h] BYREF
  char v15; // [rsp+143h] [rbp+43h]
  CHAR Dst[272]; // [rsp+150h] [rbp+50h] BYREF
  char pszDest[256]; // [rsp+260h] [rbp+160h] BYREF

  hKey = 0;
  cbData = 259;
  Type = 0;
  ACP = GetACP();
  if ( StringCchPrintfA(pszDest, 0x100u, "EUDC\\%lu", ACP) < 0
    || RegOpenKeyExA(HKEY_CURRENT_USER, pszDest, 0, 0x20019u, &hKey) )
  {
    return 0;
  }
  AllocOtm = GetAllocOtm(hdc);
  v8 = (void *)AllocOtm;
  if ( !AllocOtm )
  {
    RegCloseKey(hKey);
    return 0;
  }
  if ( RegQueryValueExA(hKey, (LPCSTR)(AllocOtm + *(_QWORD *)(AllocOtm + 200)), 0, &Type, Data, &cbData) )
  {
    cbData = 259;
    v15 = 0;
    if ( RegQueryValueExA(hKey, "SystemDefaultEUDCFont", 0, &Type, Data, &cbData) )
      goto LABEL_8;
  }
  v10 = 1;
  if ( Type - 1 > 1 )
    goto LABEL_8;
  v15 = 0;
  if ( !ExpandEnvironmentStringsA((LPCSTR)Data, Dst, 0x104u) )
    StringCchCopyA(Dst, 0x104u, (STRSAFE_LPCSTR)Data);
  if ( !(unsigned int)FixFontPath(Dst) )
  {
LABEL_8:
    RegCloseKey(hKey);
    T2free(v8);
    return 0;
  }
  if ( (unsigned int)GetSFNTImageFromFile(Dst, 0, a2, a3) )
    v10 = 0;
  RegCloseKey(hKey);
  T2free(v8);
  return v10;
}

```

## disassembly

```asm
0x18001ef44  push    rbp
0x18001ef46  push    rbx
0x18001ef47  push    rsi
0x18001ef48  push    rdi
0x18001ef49  push    r14
0x18001ef4b  lea     rbp, [rsp-270h]
0x18001ef53  sub     rsp, 370h
0x18001ef5a  mov     rax, cs:__security_cookie
0x18001ef61  xor     rax, rsp
0x18001ef64  mov     [rbp+290h+var_30], rax
0x18001ef6b  mov     edi, 103h
0x18001ef70  mov     [rsp+390h+hKey], 0
0x18001ef79  mov     [rsp+390h+cbData], edi
0x18001ef7d  mov     r14, r8
0x18001ef80  mov     rsi, rdx
0x18001ef83  mov     [rsp+390h+Type], 0
0x18001ef8b  mov     rbx, rcx
0x18001ef8e  call    cs:__imp_GetACP
0x18001ef94  mov     r9d, eax
0x18001ef97  lea     r8, pszFormat; "EUDC\\%lu"
0x18001ef9e  lea     edx, [rdi-3]; cchDest
0x18001efa1  lea     rcx, [rbp+290h+pszDest]; pszDest
0x18001efa8  call    StringCchPrintfA
0x18001efad  test    eax, eax
0x18001efaf  js      short loc_18001EFF7
0x18001efb1  lea     rax, [rsp+390h+hKey]
0x18001efb6  mov     r9d, 20019h; samDesired
0x18001efbc  xor     r8d, r8d; ulOptions
0x18001efbf  mov     [rsp+390h+phkResult], rax; phkResult
0x18001efc4  lea     rdx, [rbp+290h+pszDest]; lpSubKey
0x18001efcb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001efd2  call    cs:__imp_RegOpenKeyExA
0x18001efd8  test    eax, eax
0x18001efda  jnz     short loc_18001EFF7
0x18001efdc  mov     rcx, rbx; hdc
0x18001efdf  call    GetAllocOtm
0x18001efe4  mov     rcx, [rsp+390h+hKey]; hKey
0x18001efe9  mov     rbx, rax
0x18001efec  test    rax, rax
0x18001efef  jnz     short loc_18001F016
0x18001eff1  call    cs:__imp_RegCloseKey
0x18001eff7  xor     eax, eax
0x18001eff9  mov     rcx, [rbp+290h+var_30]
0x18001f000  xor     rcx, rsp; StackCookie
0x18001f003  call    __security_check_cookie
0x18001f008  add     rsp, 370h
0x18001f00f  pop     r14
0x18001f011  pop     rdi
0x18001f012  pop     rsi
0x18001f013  pop     rbx
0x18001f014  pop     rbp
0x18001f015  retn
0x18001f016  mov     rdx, [rax+0C8h]
0x18001f01d  lea     r9, [rsp+390h+Type]; lpType
0x18001f022  lea     rax, [rsp+390h+cbData]
0x18001f027  add     rdx, rbx; lpValueName
0x18001f02a  mov     [rsp+390h+lpcbData], rax; lpcbData
0x18001f02f  xor     r8d, r8d; lpReserved
0x18001f032  lea     rax, [rsp+390h+Data]
0x18001f037  mov     [rsp+390h+phkResult], rax; lpData
0x18001f03c  call    cs:__imp_RegQueryValueExA
0x18001f042  test    eax, eax
0x18001f044  jz      short loc_18001F098
0x18001f046  mov     rcx, [rsp+390h+hKey]; hKey
0x18001f04b  lea     rax, [rsp+390h+cbData]
0x18001f050  mov     [rsp+390h+lpcbData], rax; lpcbData
0x18001f055  lea     r9, [rsp+390h+Type]; lpType
0x18001f05a  lea     rax, [rsp+390h+Data]
0x18001f05f  mov     [rsp+390h+cbData], edi
0x18001f063  xor     r8d, r8d; lpReserved
0x18001f066  mov     [rsp+390h+phkResult], rax; lpData
0x18001f06b  lea     rdx, ValueName; "SystemDefaultEUDCFont"
0x18001f072  mov     [rbp+290h+var_24D], 0
0x18001f076  call    cs:__imp_RegQueryValueExA
0x18001f07c  test    eax, eax
0x18001f07e  jz      short loc_18001F098
0x18001f080  mov     rcx, [rsp+390h+hKey]; hKey
0x18001f085  call    cs:__imp_RegCloseKey
0x18001f08b  mov     rcx, rbx; lpMem
0x18001f08e  call    T2free
0x18001f093  jmp     loc_18001EFF7
0x18001f098  mov     eax, [rsp+390h+Type]
0x18001f09c  mov     edi, 1
0x18001f0a1  dec     eax
0x18001f0a3  cmp     eax, edi
0x18001f0a5  ja      short loc_18001F080
0x18001f0a7  mov     r8d, 104h; nSize
0x18001f0ad  mov     [rbp+290h+var_24D], 0
0x18001f0b1  lea     rdx, [rbp+290h+Dst]; lpDst
0x18001f0b5  lea     rcx, [rsp+390h+Data]; lpSrc
0x18001f0ba  call    cs:__imp_ExpandEnvironmentStringsA
0x18001f0c0  test    eax, eax
0x18001f0c2  jnz     short loc_18001F0D7
0x18001f0c4  lea     r8, [rsp+390h+Data]; pszSrc
0x18001f0c9  mov     edx, 104h; cchDest
0x18001f0ce  lea     rcx, [rbp+290h+Dst]; pszDest
0x18001f0d2  call    StringCchCopyA
0x18001f0d7  lea     rcx, [rbp+290h+Dst]; pszDest
0x18001f0db  call    FixFontPath
0x18001f0e0  test    eax, eax
0x18001f0e2  jz      short loc_18001F080
0x18001f0e4  xor     edx, edx
0x18001f0e6  lea     rcx, [rbp+290h+Dst]
0x18001f0ea  mov     r9, r14
0x18001f0ed  mov     r8, rsi
0x18001f0f0  call    GetSFNTImageFromFile
0x18001f0f5  test    eax, eax
0x18001f0f7  jz      short loc_18001F0FB
0x18001f0f9  xor     edi, edi
0x18001f0fb  mov     rcx, [rsp+390h+hKey]; hKey
0x18001f100  call    cs:__imp_RegCloseKey
0x18001f106  mov     rcx, rbx; lpMem
0x18001f109  call    T2free
0x18001f10e  mov     eax, edi
0x18001f110  jmp     loc_18001EFF9
```
