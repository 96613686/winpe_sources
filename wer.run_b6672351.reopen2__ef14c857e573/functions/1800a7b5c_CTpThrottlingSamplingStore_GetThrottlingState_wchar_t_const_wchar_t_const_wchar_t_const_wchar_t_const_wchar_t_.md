# CTpThrottlingSamplingStore::GetThrottlingState(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,int *)

- ea: `0x1800a7b5c`
- end: `0x1800a7de7`
- name: `?GetThrottlingState@CTpThrottlingSamplingStore@@CAJPEB_W0000HPEAH@Z`
- size: `651`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *, LPCWSTR lpValueName, int, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a7ac8`
- `0x1800a7df0`

## callees

- `0x1800a7b5c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a7c73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a7c73`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7cee`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a7cee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a7d99`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a7d99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a7cb4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a7d29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a7cb4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a7d29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7c26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7db2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7dc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7c26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7db2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a7dc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7c0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a7c0e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a7d5f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a7d5f`

## string_xrefs

- `0x1800a7d8f`: `AccessTime`

## pseudocode

```c
__int64 __fastcall CTpThrottlingSamplingStore::GetThrottlingState(
        const wchar_t *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        LPCWSTR lpValueName,
        int a6,
        int *a7)
{
  int *v7; // r12
  unsigned int v8; // esi
  bool v9; // cf
  int v10; // r15d
  unsigned int v11; // r14d
  HKEY v12; // rdi
  HKEY v13; // rbx
  LPCWSTR v14; // rdx
  LSTATUS v15; // eax
  const WCHAR *v16; // r14
  BYTE Data[8]; // [rsp+30h] [rbp-48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpSubKey[7]; // [rsp+40h] [rbp-38h]
  DWORD cbData; // [rsp+C0h] [rbp+48h] BYREF
  DWORD Type; // [rsp+C8h] [rbp+50h] BYREF
  struct _FILETIME v23; // [rsp+D0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+D8h] [rbp+60h] BYREF

  v7 = a7;
  cbData = 8;
  SystemTimeAsFileTime = 0;
  v23 = 0;
  hKey = 0;
  Type = 0;
  *(_QWORD *)Data = 0;
  lpSubKey[0] = L"SOFTWARE\\Microsoft\\TelemetryClient\\ThrottleStore";
  lpSubKey[1] = a1;
  lpSubKey[2] = a2;
  lpSubKey[3] = a3;
  lpSubKey[4] = a4;
  if ( !a7 )
    return (unsigned int)-2147024809;
  v9 = a6 != 0;
  a6 = -a6;
  v8 = 0;
  v10 = 0;
  *a7 = 0;
  v11 = 0;
  v12 = (HKEY)(v9 - 0x7FFFFFFFLL);
  v13 = v12;
  while ( v11 < 5 )
  {
    v14 = lpSubKey[v11];
    if ( !v14 || !*v14 )
      break;
    v15 = RegOpenKeyExW(v13, v14, 0, 0x103u, &hKey);
    if ( v15 )
    {
      hKey = 0;
      if ( v15 != 2 )
      {
        if ( v15 > 0 )
          v8 = (unsigned __int16)v15 | 0x80070000;
        else
          v8 = v15;
      }
      break;
    }
    if ( v12 != v13 )
      RegCloseKey(v13);
    v13 = hKey;
    hKey = 0;
    if ( v11 == 4 )
      v10 = 1;
    ++v11;
  }
  if ( v12 != v13 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v23 = SystemTimeAsFileTime;
    if ( v10
      && (v16 = lpValueName) != 0
      && !RegQueryValueExW(v13, lpValueName, 0, &Type, Data, &cbData)
      && Type == 11
      && cbData == 8 )
    {
      if ( *(_QWORD *)Data != -1 && *(unsigned __int64 *)&v23 >= *(_QWORD *)Data )
      {
        RegDeleteValueW(v13, v16);
        goto LABEL_33;
      }
    }
    else
    {
      cbData = 8;
      if ( RegQueryValueExW(v13, L"ThrottleExpiryTime", 0, &Type, Data, &cbData) || Type != 11 || cbData != 8 )
        goto LABEL_33;
      if ( *(_QWORD *)Data != -1 && *(unsigned __int64 *)&v23 >= *(_QWORD *)Data )
      {
        RegDeleteTreeW(v13, (LPCWSTR)&Src);
        goto LABEL_33;
      }
    }
    *v7 = 1;
    RegSetValueExW(v13, L"AccessTime", 0, 0xBu, (const BYTE *)&v23, 8u);
  }
LABEL_33:
  if ( v13 && v12 != v13 )
    RegCloseKey(v13);
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x1800a7b5c  push    rbp
0x1800a7b5e  push    rbx
0x1800a7b5f  push    rsi
0x1800a7b60  push    rdi
0x1800a7b61  push    r12
0x1800a7b63  push    r13
0x1800a7b65  push    r14
0x1800a7b67  push    r15
0x1800a7b69  mov     rbp, rsp
0x1800a7b6c  sub     rsp, 78h
0x1800a7b70  mov     r12, [rbp+arg_30]
0x1800a7b74  lea     rax, aSoftwareMicros_31; "SOFTWARE\\Microsoft\\TelemetryClient\\T"...
0x1800a7b7b  xor     r13d, r13d
0x1800a7b7e  mov     [rbp+cbData], 8
0x1800a7b85  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800a7b89  mov     [rbp+arg_10], r13
0x1800a7b8d  mov     [rbp+hKey], r13
0x1800a7b91  mov     [rbp+Type], r13d
0x1800a7b95  mov     qword ptr [rbp+Data], r13
0x1800a7b99  mov     [rbp+lpSubKey], rax
0x1800a7b9d  mov     [rbp+var_30], rcx
0x1800a7ba1  mov     [rbp+var_28], rdx
0x1800a7ba5  mov     [rbp+var_20], r8
0x1800a7ba9  mov     [rbp+var_18], r9
0x1800a7bad  test    r12, r12
0x1800a7bb0  jnz     short loc_1800A7BBC
0x1800a7bb2  mov     esi, 80070057h
0x1800a7bb7  jmp     loc_1800A7DD3
0x1800a7bbc  neg     [rbp+arg_28]
0x1800a7bbf  mov     esi, r13d
0x1800a7bc2  mov     r15d, r13d
0x1800a7bc5  mov     [r12], r13d
0x1800a7bc9  sbb     rdi, rdi
0x1800a7bcc  mov     r14d, r13d
0x1800a7bcf  neg     rdi
0x1800a7bd2  add     rdi, 0FFFFFFFF80000001h
0x1800a7bd9  mov     rbx, rdi
0x1800a7bdc  cmp     r14d, 5
0x1800a7be0  jnb     loc_1800A7C66
0x1800a7be6  mov     eax, r14d
0x1800a7be9  mov     rdx, [rbp+rax*8+lpSubKey]; lpSubKey
0x1800a7bee  test    rdx, rdx
0x1800a7bf1  jz      short loc_1800A7C66
0x1800a7bf3  cmp     [rdx], r13w
0x1800a7bf7  jz      short loc_1800A7C66
0x1800a7bf9  lea     rax, [rbp+hKey]
0x1800a7bfd  mov     r9d, 103h; samDesired
0x1800a7c03  xor     r8d, r8d; ulOptions
0x1800a7c06  mov     [rsp+78h+phkResult], rax; phkResult
0x1800a7c0b  mov     rcx, rbx; hKey
0x1800a7c0e  call    cs:__imp_RegOpenKeyExW
0x1800a7c15  nop     dword ptr [rax+rax+00h]
0x1800a7c1a  test    eax, eax
0x1800a7c1c  jnz     short loc_1800A7C4C
0x1800a7c1e  cmp     rdi, rbx
0x1800a7c21  jz      short loc_1800A7C32
0x1800a7c23  mov     rcx, rbx; hKey
0x1800a7c26  call    cs:__imp_RegCloseKey
0x1800a7c2d  nop     dword ptr [rax+rax+00h]
0x1800a7c32  mov     rbx, [rbp+hKey]
0x1800a7c36  cmp     r14d, 4
0x1800a7c3a  mov     eax, 1
0x1800a7c3f  mov     [rbp+hKey], r13
0x1800a7c43  cmovz   r15d, eax
0x1800a7c47  add     r14d, eax
0x1800a7c4a  jmp     short loc_1800A7BDC
0x1800a7c4c  mov     [rbp+hKey], r13
0x1800a7c50  cmp     eax, 2
0x1800a7c53  jz      short loc_1800A7C66
0x1800a7c55  test    eax, eax
0x1800a7c57  jg      short loc_1800A7C5D
0x1800a7c59  mov     esi, eax
0x1800a7c5b  jmp     short loc_1800A7C66
0x1800a7c5d  movzx   esi, ax
0x1800a7c60  or      esi, 80070000h
0x1800a7c66  cmp     rdi, rbx
0x1800a7c69  jz      loc_1800A7DA5
0x1800a7c6f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a7c73  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a7c7a  nop     dword ptr [rax+rax+00h]
0x1800a7c7f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a7c83  mov     [rbp+arg_10], rax
0x1800a7c87  test    r15d, r15d
0x1800a7c8a  jz      short loc_1800A7CFF
0x1800a7c8c  mov     r14, [rbp+lpValueName]
0x1800a7c90  test    r14, r14
0x1800a7c93  jz      short loc_1800A7CFF
0x1800a7c95  lea     rax, [rbp+cbData]
0x1800a7c99  xor     r8d, r8d; lpReserved
0x1800a7c9c  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800a7ca1  lea     r9, [rbp+Type]; lpType
0x1800a7ca5  lea     rax, [rbp+Data]
0x1800a7ca9  mov     rdx, r14; lpValueName
0x1800a7cac  mov     rcx, rbx; hKey
0x1800a7caf  mov     [rsp+78h+phkResult], rax; lpData
0x1800a7cb4  call    cs:__imp_RegQueryValueExW
0x1800a7cbb  nop     dword ptr [rax+rax+00h]
0x1800a7cc0  test    eax, eax
0x1800a7cc2  jnz     short loc_1800A7CFF
0x1800a7cc4  cmp     [rbp+Type], 0Bh
0x1800a7cc8  jnz     short loc_1800A7CFF
0x1800a7cca  cmp     [rbp+cbData], 8
0x1800a7cce  jnz     short loc_1800A7CFF
0x1800a7cd0  mov     rax, qword ptr [rbp+Data]
0x1800a7cd4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a7cd8  jz      loc_1800A7D6D
0x1800a7cde  cmp     [rbp+arg_10], rax
0x1800a7ce2  jb      loc_1800A7D6D
0x1800a7ce8  mov     rdx, r14; lpValueName
0x1800a7ceb  mov     rcx, rbx; hKey
0x1800a7cee  call    cs:__imp_RegDeleteValueW
0x1800a7cf5  nop     dword ptr [rax+rax+00h]
0x1800a7cfa  jmp     loc_1800A7DA5
0x1800a7cff  lea     rax, [rbp+cbData]
0x1800a7d03  mov     [rbp+cbData], 8
0x1800a7d0a  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800a7d0f  lea     r9, [rbp+Type]; lpType
0x1800a7d13  lea     rax, [rbp+Data]
0x1800a7d17  xor     r8d, r8d; lpReserved
0x1800a7d1a  lea     rdx, aThrottleexpiry; "ThrottleExpiryTime"
0x1800a7d21  mov     [rsp+78h+phkResult], rax; lpData
0x1800a7d26  mov     rcx, rbx; hKey
0x1800a7d29  call    cs:__imp_RegQueryValueExW
0x1800a7d30  nop     dword ptr [rax+rax+00h]
0x1800a7d35  test    eax, eax
0x1800a7d37  jnz     short loc_1800A7DA5
0x1800a7d39  cmp     [rbp+Type], 0Bh
0x1800a7d3d  jnz     short loc_1800A7DA5
0x1800a7d3f  cmp     [rbp+cbData], 8
0x1800a7d43  jnz     short loc_1800A7DA5
0x1800a7d45  mov     rax, qword ptr [rbp+Data]
0x1800a7d49  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a7d4d  jz      short loc_1800A7D6D
0x1800a7d4f  cmp     [rbp+arg_10], rax
0x1800a7d53  jb      short loc_1800A7D6D
0x1800a7d55  lea     rdx, Src; lpSubKey
0x1800a7d5c  mov     rcx, rbx; hKey
0x1800a7d5f  call    cs:__imp_RegDeleteTreeW
0x1800a7d66  nop     dword ptr [rax+rax+00h]
0x1800a7d6b  jmp     short loc_1800A7DA5
0x1800a7d6d  lea     rax, [rbp+arg_10]
0x1800a7d71  mov     dword ptr [rsp+78h+lpcbData], 8; cbData
0x1800a7d79  mov     r9d, 0Bh; dwType
0x1800a7d7f  mov     [rsp+78h+phkResult], rax; lpData
0x1800a7d84  xor     r8d, r8d; Reserved
0x1800a7d87  mov     dword ptr [r12], 1
0x1800a7d8f  lea     rdx, aAccesstime; "AccessTime"
0x1800a7d96  mov     rcx, rbx; hKey
0x1800a7d99  call    cs:__imp_RegSetValueExW
0x1800a7da0  nop     dword ptr [rax+rax+00h]
0x1800a7da5  test    rbx, rbx
0x1800a7da8  jz      short loc_1800A7DBE
0x1800a7daa  cmp     rdi, rbx
0x1800a7dad  jz      short loc_1800A7DBE
0x1800a7daf  mov     rcx, rbx; hKey
0x1800a7db2  call    cs:__imp_RegCloseKey
0x1800a7db9  nop     dword ptr [rax+rax+00h]
0x1800a7dbe  mov     rcx, [rbp+hKey]; hKey
0x1800a7dc2  test    rcx, rcx
0x1800a7dc5  jz      short loc_1800A7DD3
0x1800a7dc7  call    cs:__imp_RegCloseKey
0x1800a7dce  nop     dword ptr [rax+rax+00h]
0x1800a7dd3  mov     eax, esi
0x1800a7dd5  add     rsp, 78h
0x1800a7dd9  pop     r15
0x1800a7ddb  pop     r14
0x1800a7ddd  pop     r13
0x1800a7ddf  pop     r12
0x1800a7de1  pop     rdi
0x1800a7de2  pop     rsi
0x1800a7de3  pop     rbx
0x1800a7de4  pop     rbp
0x1800a7de5  retn
```
