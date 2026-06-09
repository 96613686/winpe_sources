# RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,RegistryHiveType)

- ea: `0x18000fe08`
- end: `0x18000ff6e`
- name: `?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEAPEA_WW4RegistryHiveType@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18001a094`
- `0x18003b800`

## callees

- `0x180005f64`
- `0x18000a60c`
- `0x18000fac4`
- `0x18000fe08`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ff46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000feb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ff05`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000feb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ff05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fe87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fe87`

## pseudocode

```c
__int64 __fastcall RegQueryStringValue(int a1, const WCHAR *a2, const WCHAR *a3, void **a4)
{
  int v8; // ebx
  LSTATUS v9; // eax
  BYTE *v10; // rax
  REGSAM samDesired; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-1Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  DWORD Type; // [rsp+40h] [rbp-10h] BYREF

  samDesired = 1;
  Type = 0;
  hKey = 0;
  cbData = 0;
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v8 = SetRegistryType(a1, &samDesired);
  if ( v8 < 0 )
    goto LABEL_16;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey);
  if ( v9 )
    goto LABEL_13;
  v9 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
  if ( v9 || !cbData )
    goto LABEL_13;
  if ( Type != 1 )
  {
    v8 = -2147024883;
LABEL_16:
    CSusBaseAllocTag<942762101>::operator delete(*a4);
    *a4 = 0;
    goto LABEL_17;
  }
  cbData += 2;
  v10 = (BYTE *)SusAlloc(cbData);
  *a4 = v10;
  if ( !v10 )
  {
    v8 = -2147024882;
    goto LABEL_16;
  }
  v9 = RegQueryValueExW(hKey, a3, 0, &Type, v10, &cbData);
  if ( v9 )
  {
LABEL_13:
    v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 <= 0 )
      v8 = v9;
    if ( v8 >= 0 )
      goto LABEL_17;
    goto LABEL_16;
  }
  *(_WORD *)((char *)*a4 + (cbData & 0xFFFFFFFE)) = 0;
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000fe08  mov     [rsp-28h+arg_0], rbx
0x18000fe0d  push    rbp
0x18000fe0e  push    rsi
0x18000fe0f  push    rdi
0x18000fe10  push    r14
0x18000fe12  push    r15
0x18000fe14  mov     rbp, rsp
0x18000fe17  sub     rsp, 50h
0x18000fe1b  mov     rax, cs:__security_cookie
0x18000fe22  xor     rax, rsp
0x18000fe25  mov     [rbp+var_8], rax
0x18000fe29  xor     r15d, r15d
0x18000fe2c  mov     [rbp+samDesired], 1
0x18000fe33  mov     [rbp+Type], r15d
0x18000fe37  mov     rdi, r9
0x18000fe3a  mov     [rbp+hKey], r15
0x18000fe3e  mov     rsi, r8
0x18000fe41  mov     [rbp+cbData], r15d
0x18000fe45  mov     r14, rdx
0x18000fe48  test    r9, r9
0x18000fe4b  jnz     short loc_18000FE57
0x18000fe4d  mov     eax, 80070057h
0x18000fe52  jmp     loc_18000FF4E
0x18000fe57  lea     rdx, [rbp+samDesired]
0x18000fe5b  mov     [r9], r15
0x18000fe5e  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18000fe63  mov     ebx, eax
0x18000fe65  test    eax, eax
0x18000fe67  js      loc_18000FF32
0x18000fe6d  mov     r9d, [rbp+samDesired]; samDesired
0x18000fe71  lea     rax, [rbp+hKey]
0x18000fe75  xor     r8d, r8d; ulOptions
0x18000fe78  mov     [rsp+50h+phkResult], rax; phkResult
0x18000fe7d  mov     rdx, r14; lpSubKey
0x18000fe80  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fe87  call    cs:__imp_RegOpenKeyExW
0x18000fe8d  test    eax, eax
0x18000fe8f  jnz     loc_18000FF20
0x18000fe95  mov     rcx, [rbp+hKey]; hKey
0x18000fe99  lea     rax, [rbp+cbData]
0x18000fe9d  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000fea2  lea     r9, [rbp+Type]; lpType
0x18000fea6  xor     r8d, r8d; lpReserved
0x18000fea9  mov     [rsp+50h+phkResult], r15; lpData
0x18000feae  mov     rdx, rsi; lpValueName
0x18000feb1  call    cs:__imp_RegQueryValueExW
0x18000feb7  test    eax, eax
0x18000feb9  jnz     short loc_18000FF20
0x18000febb  mov     ecx, [rbp+cbData]
0x18000febe  test    ecx, ecx
0x18000fec0  jz      short loc_18000FF20
0x18000fec2  cmp     [rbp+Type], 1
0x18000fec6  jz      short loc_18000FECF
0x18000fec8  mov     ebx, 8007000Dh
0x18000fecd  jmp     short loc_18000FF32
0x18000fecf  add     ecx, 2; unsigned __int64
0x18000fed2  mov     [rbp+cbData], ecx
0x18000fed5  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x18000feda  mov     [rdi], rax
0x18000fedd  test    rax, rax
0x18000fee0  jnz     short loc_18000FEE9
0x18000fee2  mov     ebx, 8007000Eh
0x18000fee7  jmp     short loc_18000FF32
0x18000fee9  lea     rcx, [rbp+cbData]
0x18000feed  xor     r8d, r8d; lpReserved
0x18000fef0  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x18000fef5  lea     r9, [rbp+Type]; lpType
0x18000fef9  mov     rcx, [rbp+hKey]; hKey
0x18000fefd  mov     rdx, rsi; lpValueName
0x18000ff00  mov     [rsp+50h+phkResult], rax; lpData
0x18000ff05  call    cs:__imp_RegQueryValueExW
0x18000ff0b  test    eax, eax
0x18000ff0d  jnz     short loc_18000FF20
0x18000ff0f  mov     ecx, [rbp+cbData]
0x18000ff12  mov     rax, [rdi]
0x18000ff15  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000ff19  mov     [rcx+rax], r15w
0x18000ff1e  jmp     short loc_18000FF3D
0x18000ff20  movzx   ebx, ax
0x18000ff23  or      ebx, 80070000h
0x18000ff29  test    eax, eax
0x18000ff2b  cmovle  ebx, eax
0x18000ff2e  test    ebx, ebx
0x18000ff30  jns     short loc_18000FF3D
0x18000ff32  mov     rcx, [rdi]; lpMem
0x18000ff35  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18000ff3a  mov     [rdi], r15
0x18000ff3d  mov     rcx, [rbp+hKey]; hKey
0x18000ff41  test    rcx, rcx
0x18000ff44  jz      short loc_18000FF4C
0x18000ff46  call    cs:__imp_RegCloseKey
0x18000ff4c  mov     eax, ebx
0x18000ff4e  mov     rcx, [rbp+var_8]
0x18000ff52  xor     rcx, rsp; StackCookie
0x18000ff55  call    __security_check_cookie
0x18000ff5a  mov     rbx, [rsp+50h+arg_0]
0x18000ff62  add     rsp, 50h
0x18000ff66  pop     r15
0x18000ff68  pop     r14
0x18000ff6a  pop     rdi
0x18000ff6b  pop     rsi
0x18000ff6c  pop     rbp
0x18000ff6d  retn
```
