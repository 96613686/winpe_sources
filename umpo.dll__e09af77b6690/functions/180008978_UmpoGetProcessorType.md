# UmpoGetProcessorType

- ea: `0x180008978`
- end: `0x180008bda`
- name: `UmpoGetProcessorType`
- size: `610`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800088b0`

## callees

- `0x180008978`
- `0x180010070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180008b84`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180008bb7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180008b84`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180008bb7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008a26`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008a67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008aa8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008a26`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008a67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008aa8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800089df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800089df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b1d`

## pseudocode

```c
__int64 __fastcall UmpoGetProcessorType(_DWORD *a1, _DWORD *a2)
{
  unsigned int ValueW; // ebx
  LSTATUS v5; // eax
  unsigned int i; // esi
  __int64 v7; // rdi
  const wchar_t *v8; // rdx
  wchar_t *v9; // rax
  signed __int64 v10; // rdx
  int v11; // r8d
  int v12; // ecx
  int v13; // eax
  wchar_t *v15; // r13
  unsigned int v16; // esi
  wchar_t *v17; // r12
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t pvData[32]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str[64]; // [rsp+90h] [rbp-70h] BYREF
  _WORD v22[128]; // [rsp+110h] [rbp+10h] BYREF

  hkey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  pcbData = 0;
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Hardware\\Description\\System\\CentralProcessor\\0", 0, 1u, &hkey);
  if ( ValueW )
    goto LABEL_16;
  pcbData = 64;
  ValueW = RegGetValueW(hkey, 0, L"VendorIdentifier", 2u, 0, pvData, &pcbData);
  if ( ValueW )
    goto LABEL_16;
  pcbData = 128;
  ValueW = RegGetValueW(hkey, 0, L"Identifier", 2u, 0, Str, &pcbData);
  if ( ValueW )
    goto LABEL_16;
  pcbData = 256;
  v5 = RegGetValueW(hkey, 0, L"ProcessorNameString", 2u, 0, v22, &pcbData);
  ValueW = v5;
  if ( v5 == 2 )
  {
    v22[0] = 0;
    ValueW = 0;
  }
  else if ( v5 )
  {
    goto LABEL_16;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
    {
      *a2 = 0;
      *a1 = 0;
      goto LABEL_16;
    }
    v7 = 4LL * i;
    v8 = (&UmpoProcessorVendorMapping)[v7];
    if ( *((_BYTE *)&UmpoProcessorVendorMapping + 8 * v7 + 24) )
      break;
    if ( wcsstr(pvData, v8) )
      goto LABEL_19;
LABEL_13:
    ;
  }
  v9 = pvData;
  v10 = (char *)v8 - (char *)pvData;
  do
  {
    v11 = *(wchar_t *)((char *)v9 + v10);
    v12 = *v9 - v11;
    if ( v12 )
      break;
    ++v9;
  }
  while ( v11 );
  if ( v12 )
    goto LABEL_13;
LABEL_19:
  v15 = v22;
  *a1 = *((_DWORD *)&UmpoProcessorVendorMapping + 2 * v7 + 2);
  v16 = 0;
  if ( *((_BYTE *)&UmpoProcessorVendorMapping + 8 * v7 + 25) )
    v15 = Str;
  while ( v16 < *((_DWORD *)&UmpoProcessorVendorMapping + 2 * v7 + 3) )
  {
    v17 = (&UmpoProcessorVendorMapping)[v7 + 1];
    if ( wcsstr(v15, *(const wchar_t **)&v17[8 * v16]) )
    {
      v13 = *(_DWORD *)&v17[8 * v16 + 4];
      goto LABEL_15;
    }
    ++v16;
  }
  v13 = 0;
LABEL_15:
  *a2 = v13;
LABEL_16:
  if ( hkey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hkey);
  return ValueW;
}

```

## disassembly

```asm
0x180008978  mov     [rsp-8+arg_10], rbx
0x18000897d  push    rbp
0x18000897e  push    rsi
0x18000897f  push    rdi
0x180008980  push    r12
0x180008982  push    r13
0x180008984  push    r14
0x180008986  push    r15
0x180008988  lea     rbp, [rsp-120h]
0x180008990  sub     rsp, 220h
0x180008997  mov     rax, cs:__security_cookie
0x18000899e  xor     rax, rsp
0x1800089a1  mov     [rbp+150h+var_40], rax
0x1800089a8  xor     r12d, r12d
0x1800089ab  mov     [rsp+250h+hkey], 0FFFFFFFFFFFFFFFFh
0x1800089b4  mov     r14, rdx
0x1800089b7  mov     [rsp+250h+var_210], r12d
0x1800089bc  mov     r15, rcx
0x1800089bf  lea     rax, [rsp+250h+hkey]
0x1800089c4  xor     r8d, r8d; ulOptions
0x1800089c7  mov     [rsp+250h+phkResult], rax; phkResult
0x1800089cc  lea     r9d, [r12+1]; samDesired
0x1800089d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800089d8  lea     rdx, aHardwareDescri; "Hardware\\Description\\System\\CentralP"...
0x1800089df  call    cs:__imp_RegOpenKeyExW
0x1800089e5  mov     ebx, eax
0x1800089e7  test    eax, eax
0x1800089e9  jnz     loc_180008B12
0x1800089ef  mov     rcx, [rsp+250h+hkey]; hkey
0x1800089f4  lea     rax, [rsp+250h+var_210]
0x1800089f9  mov     [rsp+250h+pcbData], rax; pcbData
0x1800089fe  lea     r13d, [r12+2]
0x180008a03  lea     rax, [rsp+250h+var_200]
0x180008a08  mov     [rsp+250h+var_210], 40h ; '@'
0x180008a10  mov     [rsp+250h+pvData], rax; pvData
0x180008a15  lea     r8, Value; "VendorIdentifier"
0x180008a1c  mov     r9d, r13d; dwFlags
0x180008a1f  mov     [rsp+250h+phkResult], r12; pdwType
0x180008a24  xor     edx, edx; lpSubKey
0x180008a26  call    cs:__imp_RegGetValueW
0x180008a2c  mov     ebx, eax
0x180008a2e  test    eax, eax
0x180008a30  jnz     loc_180008B12
0x180008a36  mov     rcx, [rsp+250h+hkey]; hkey
0x180008a3b  lea     rax, [rsp+250h+var_210]
0x180008a40  mov     [rsp+250h+pcbData], rax; pcbData
0x180008a45  lea     r8, aIdentifier; "Identifier"
0x180008a4c  lea     rax, [rbp+150h+Str]
0x180008a50  mov     [rsp+250h+var_210], 80h
0x180008a58  mov     [rsp+250h+pvData], rax; pvData
0x180008a5d  mov     r9d, r13d; dwFlags
0x180008a60  xor     edx, edx; lpSubKey
0x180008a62  mov     [rsp+250h+phkResult], r12; pdwType
0x180008a67  call    cs:__imp_RegGetValueW
0x180008a6d  mov     ebx, eax
0x180008a6f  test    eax, eax
0x180008a71  jnz     loc_180008B12
0x180008a77  mov     rcx, [rsp+250h+hkey]; hkey
0x180008a7c  lea     rax, [rsp+250h+var_210]
0x180008a81  mov     [rsp+250h+pcbData], rax; pcbData
0x180008a86  lea     r8, aProcessornames; "ProcessorNameString"
0x180008a8d  lea     rax, [rbp+150h+var_140]
0x180008a91  mov     [rsp+250h+var_210], 100h
0x180008a99  mov     [rsp+250h+pvData], rax; pvData
0x180008a9e  mov     r9d, r13d; dwFlags
0x180008aa1  xor     edx, edx; lpSubKey
0x180008aa3  mov     [rsp+250h+phkResult], r12; pdwType
0x180008aa8  call    cs:__imp_RegGetValueW
0x180008aae  mov     ebx, eax
0x180008ab0  cmp     eax, r13d
0x180008ab3  jz      loc_180008BA5
0x180008ab9  test    eax, eax
0x180008abb  jnz     short loc_180008B12
0x180008abd  mov     esi, r12d
0x180008ac0  cmp     esi, r13d
0x180008ac3  jnb     loc_180008BCF
0x180008ac9  lea     r9, UmpoProcessorVendorMapping
0x180008ad0  mov     edi, esi
0x180008ad2  shl     rdi, 5
0x180008ad6  mov     rdx, [rdi+r9]; SubStr
0x180008ada  cmp     [rdi+r9+18h], r12b
0x180008adf  jz      loc_180008BB2
0x180008ae5  lea     rax, [rsp+250h+var_200]
0x180008aea  sub     rdx, rax
0x180008aed  movzx   ecx, word ptr [rax]
0x180008af0  movzx   r8d, word ptr [rax+rdx]
0x180008af5  sub     ecx, r8d
0x180008af8  jnz     short loc_180008B02
0x180008afa  add     rax, r13
0x180008afd  test    r8d, r8d
0x180008b00  jnz     short loc_180008AED
0x180008b02  test    ecx, ecx
0x180008b04  jz      short loc_180008B4F
0x180008b06  inc     esi
0x180008b08  jmp     short loc_180008AC0
0x180008b0a  mov     eax, [r12+r15*8+8]
0x180008b0f  mov     [r14], eax
0x180008b12  mov     rcx, [rsp+250h+hkey]; hKey
0x180008b17  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008b1b  jz      short loc_180008B23
0x180008b1d  call    cs:__imp_RegCloseKey
0x180008b23  mov     eax, ebx
0x180008b25  mov     rcx, [rbp+150h+var_40]
0x180008b2c  xor     rcx, rsp; StackCookie
0x180008b2f  call    __security_check_cookie
0x180008b34  mov     rbx, [rsp+250h+arg_10]
0x180008b3c  add     rsp, 220h
0x180008b43  pop     r15
0x180008b45  pop     r14
0x180008b47  pop     r13
0x180008b49  pop     r12
0x180008b4b  pop     rdi
0x180008b4c  pop     rsi
0x180008b4d  pop     rbp
0x180008b4e  retn
0x180008b4f  mov     eax, [rdi+r9+8]
0x180008b54  lea     r13, [rbp+150h+var_140]
0x180008b58  mov     [r15], eax
0x180008b5b  mov     esi, r12d
0x180008b5e  cmp     [rdi+r9+19h], r12b
0x180008b63  lea     rax, [rbp+150h+Str]
0x180008b67  cmovnz  r13, rax
0x180008b6b  cmp     esi, [rdi+r9+0Ch]
0x180008b70  jnb     short loc_180008B9E
0x180008b72  mov     r12, [rdi+r9+10h]
0x180008b77  mov     rcx, r13; Str
0x180008b7a  mov     r15d, esi
0x180008b7d  add     r15, r15
0x180008b80  mov     rdx, [r12+r15*8]; SubStr
0x180008b84  call    cs:__imp_wcsstr
0x180008b8a  test    rax, rax
0x180008b8d  jnz     loc_180008B0A
0x180008b93  inc     esi
0x180008b95  lea     r9, UmpoProcessorVendorMapping
0x180008b9c  jmp     short loc_180008B6B
0x180008b9e  xor     eax, eax
0x180008ba0  jmp     loc_180008B0F
0x180008ba5  mov     [rbp+150h+var_140], r12w
0x180008baa  mov     ebx, r12d
0x180008bad  jmp     loc_180008ABD
0x180008bb2  lea     rcx, [rsp+250h+var_200]; Str
0x180008bb7  call    cs:__imp_wcsstr
0x180008bbd  test    rax, rax
0x180008bc0  jz      loc_180008B06
0x180008bc6  lea     r9, UmpoProcessorVendorMapping
0x180008bcd  jmp     short loc_180008B4F
0x180008bcf  mov     [r14], r12d
0x180008bd2  mov     [r15], r12d
0x180008bd5  jmp     loc_180008B12
```
