# RegCreateKeyHelperPrivate

- ea: `0x180010150`
- end: `0x1800102ba`
- name: `RegCreateKeyHelperPrivate`
- size: `362`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800102c0`

## callees

- `0x18000fac4`
- `0x180010150`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010288`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010297`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010288`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010297`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800101e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001024b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800101e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001024b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegCreateKeyHelperPrivate(__int64 a1, const WCHAR *a2, const WCHAR *a3, HKEY *a4)
{
  int v5; // r14d
  signed int v8; // ebx
  REGSAM v9; // r15d
  LSTATUS v10; // eax
  HKEY v11; // rcx
  REGSAM samDesired; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF

  phkResult = 0;
  v5 = 0;
  hKey = 0;
  *a4 = 0;
  samDesired = 131078;
  v8 = SetRegistryType(a1, &samDesired);
  if ( v8 >= 0 )
  {
    v9 = samDesired;
    if ( a2 )
    {
      v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, samDesired, 0, &phkResult, 0);
      if ( v10 )
      {
LABEL_4:
        v8 = (unsigned __int16)v10 | 0x80070000;
        if ( v10 <= 0 )
          v8 = v10;
        goto LABEL_15;
      }
      v11 = phkResult;
      v5 = 1;
    }
    else
    {
      v11 = HKEY_LOCAL_MACHINE;
    }
    if ( a3 )
    {
      v10 = RegCreateKeyExW(v11, a3, 0, 0, 1u, v9, 0, &hKey, 0);
      if ( !v10 )
      {
        *a4 = hKey;
        hKey = 0;
        goto LABEL_17;
      }
      goto LABEL_4;
    }
    if ( v5 )
    {
      *a4 = phkResult;
      phkResult = 0;
    }
    else
    {
      *a4 = HKEY_LOCAL_MACHINE;
    }
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_17:
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010150  push    rbp
0x180010152  push    rbx
0x180010153  push    rsi
0x180010154  push    rdi
0x180010155  push    r12
0x180010157  push    r14
0x180010159  push    r15
0x18001015b  mov     rbp, rsp
0x18001015e  sub     rsp, 70h
0x180010162  mov     rax, cs:__security_cookie
0x180010169  xor     rax, rsp
0x18001016c  mov     [rbp+var_8], rax
0x180010170  mov     rsi, rdx
0x180010173  mov     [rbp+var_18], 0
0x18001017b  xor     r14d, r14d
0x18001017e  mov     [rbp+hKey], 0
0x180010186  lea     rdx, [rbp+var_20]
0x18001018a  mov     [r9], r14
0x18001018d  mov     rdi, r9
0x180010190  mov     [rbp+var_20], 20006h
0x180010197  mov     r12, r8
0x18001019a  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x18001019f  mov     ebx, eax
0x1800101a1  test    eax, eax
0x1800101a3  js      loc_18001027F
0x1800101a9  mov     r15d, [rbp+var_20]
0x1800101ad  test    rsi, rsi
0x1800101b0  jz      short loc_18001020B
0x1800101b2  mov     [rsp+70h+lpdwDisposition], r14; lpdwDisposition
0x1800101b7  lea     rax, [rbp+var_18]
0x1800101bb  mov     [rsp+70h+phkResult], rax; phkResult
0x1800101c0  mov     rdx, rsi; lpSubKey
0x1800101c3  mov     [rsp+70h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800101c8  mov     rsi, 0FFFFFFFF80000002h
0x1800101cf  mov     [rsp+70h+samDesired], r15d; samDesired
0x1800101d4  xor     r9d, r9d; lpClass
0x1800101d7  xor     r8d, r8d; Reserved
0x1800101da  mov     [rsp+70h+dwOptions], r14d; dwOptions
0x1800101df  mov     rcx, rsi; hKey
0x1800101e2  call    cs:__imp_RegCreateKeyExW
0x1800101e8  test    eax, eax
0x1800101ea  jz      short loc_1800101FF
0x1800101ec  movzx   ebx, ax
0x1800101ef  or      ebx, 80070000h
0x1800101f5  test    eax, eax
0x1800101f7  cmovle  ebx, eax
0x1800101fa  jmp     loc_18001027F
0x1800101ff  mov     rcx, [rbp+var_18]
0x180010203  mov     r14d, 1
0x180010209  jmp     short loc_180010215
0x18001020b  mov     rsi, 0FFFFFFFF80000002h
0x180010212  mov     rcx, rsi; hKey
0x180010215  test    r12, r12
0x180010218  jz      short loc_180010266
0x18001021a  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180010223  lea     rax, [rbp+hKey]
0x180010227  mov     [rsp+70h+phkResult], rax; phkResult
0x18001022c  xor     r9d, r9d; lpClass
0x18001022f  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010238  xor     r8d, r8d; Reserved
0x18001023b  mov     [rsp+70h+samDesired], r15d; samDesired
0x180010240  mov     rdx, r12; lpSubKey
0x180010243  mov     [rsp+70h+dwOptions], 1; dwOptions
0x18001024b  call    cs:__imp_RegCreateKeyExW
0x180010251  test    eax, eax
0x180010253  jnz     short loc_1800101EC
0x180010255  mov     rax, [rbp+hKey]
0x180010259  mov     [rdi], rax
0x18001025c  mov     [rbp+hKey], 0
0x180010264  jmp     short loc_18001028E
0x180010266  test    r14d, r14d
0x180010269  jz      short loc_18001027C
0x18001026b  mov     rax, [rbp+var_18]
0x18001026f  mov     [rdi], rax
0x180010272  mov     [rbp+var_18], 0
0x18001027a  jmp     short loc_18001027F
0x18001027c  mov     [rdi], rsi
0x18001027f  mov     rcx, [rbp+hKey]; hKey
0x180010283  test    rcx, rcx
0x180010286  jz      short loc_18001028E
0x180010288  call    cs:__imp_RegCloseKey
0x18001028e  mov     rcx, [rbp+var_18]; hKey
0x180010292  test    rcx, rcx
0x180010295  jz      short loc_18001029D
0x180010297  call    cs:__imp_RegCloseKey
0x18001029d  mov     eax, ebx
0x18001029f  mov     rcx, [rbp+var_8]
0x1800102a3  xor     rcx, rsp; StackCookie
0x1800102a6  call    __security_check_cookie
0x1800102ab  add     rsp, 70h
0x1800102af  pop     r15
0x1800102b1  pop     r14
0x1800102b3  pop     r12
0x1800102b5  pop     rdi
0x1800102b6  pop     rsi
0x1800102b7  pop     rbx
0x1800102b8  pop     rbp
0x1800102b9  retn
```
