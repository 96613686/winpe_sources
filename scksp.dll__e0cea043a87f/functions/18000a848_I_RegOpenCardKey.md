# I_RegOpenCardKey

- ea: `0x18000a848`
- end: `0x18000a93e`
- name: `I_RegOpenCardKey`
- size: `246`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000aa4c`
- `0x18000aee4`
- `0x1800183ec`

## callees

- `0x18000a750`
- `0x18000a848`
- `0x18000a944`
- `0x18000d9d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a8e6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a8e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a919`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a928`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a919`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a928`

## pseudocode

```c
__int64 __fastcall I_RegOpenCardKey(__int64 a1, unsigned int a2, HKEY *a3, REGSAM a4)
{
  unsigned int v8; // ebx
  unsigned int ByteString; // eax
  LPCWSTR v10; // rdi
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-20h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+60h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+C0h] [rbp+48h] BYREF

  lpSubKey[0] = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  *a3 = 0;
  v8 = I_RegOpenECDSAKey(&hKey);
  if ( !v8 )
  {
    ByteString = I_RegGetByteString(a1, a2, lpSubKey);
    v10 = lpSubKey[0];
    v8 = ByteString;
    if ( !ByteString )
    {
      v8 = RegCreateKeyExW(hKey, lpSubKey[0], 0, (LPWSTR)&Class, 0, a4, 0, &phkResult, &dwDisposition);
      if ( !v8 )
      {
        *a3 = phkResult;
        phkResult = 0;
      }
    }
    if ( v10 )
      CspFreeH(v10);
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v8;
}

```

## disassembly

```asm
0x18000a848  push    rbp
0x18000a84a  push    rbx
0x18000a84b  push    rdi
0x18000a84c  push    r12
0x18000a84e  push    r14
0x18000a850  push    r15
0x18000a852  mov     rbp, rsp
0x18000a855  sub     rsp, 78h
0x18000a859  mov     r15, rcx
0x18000a85c  mov     [rbp+lpSubKey], 0
0x18000a864  lea     rcx, [rbp+hKey]
0x18000a868  mov     [rbp+dwDisposition], 0
0x18000a86f  mov     r12d, r9d
0x18000a872  mov     [rbp+hKey], 0
0x18000a87a  mov     r14, r8
0x18000a87d  mov     [rbp+var_20], 0
0x18000a885  mov     edi, edx
0x18000a887  mov     qword ptr [r8], 0
0x18000a88e  call    I_RegOpenECDSAKey
0x18000a893  mov     ebx, eax
0x18000a895  test    eax, eax
0x18000a897  jnz     short loc_18000A90E
0x18000a899  lea     r8, [rbp+lpSubKey]
0x18000a89d  mov     edx, edi
0x18000a89f  mov     rcx, r15
0x18000a8a2  call    I_RegGetByteString
0x18000a8a7  mov     rdi, [rbp+lpSubKey]
0x18000a8ab  mov     ebx, eax
0x18000a8ad  test    eax, eax
0x18000a8af  jnz     short loc_18000A901
0x18000a8b1  mov     rcx, [rbp+hKey]; hKey
0x18000a8b5  lea     rax, [rbp+dwDisposition]
0x18000a8b9  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x18000a8be  lea     r9, Class; lpClass
0x18000a8c5  lea     rax, [rbp+var_20]
0x18000a8c9  xor     r8d, r8d; Reserved
0x18000a8cc  mov     [rsp+78h+phkResult], rax; phkResult
0x18000a8d1  mov     rdx, rdi; lpSubKey
0x18000a8d4  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000a8dd  mov     [rsp+78h+samDesired], r12d; samDesired
0x18000a8e2  mov     [rsp+78h+dwOptions], ebx; dwOptions
0x18000a8e6  call    cs:__imp_RegCreateKeyExW
0x18000a8ec  mov     ebx, eax
0x18000a8ee  test    eax, eax
0x18000a8f0  jnz     short loc_18000A901
0x18000a8f2  mov     rax, [rbp+var_20]
0x18000a8f6  mov     [r14], rax
0x18000a8f9  mov     [rbp+var_20], 0
0x18000a901  test    rdi, rdi
0x18000a904  jz      short loc_18000A90E
0x18000a906  mov     rcx, rdi
0x18000a909  call    CspFreeH
0x18000a90e  cmp     [rbp+hKey], 0
0x18000a913  jz      short loc_18000A91F
0x18000a915  mov     rcx, [rbp+hKey]; hKey
0x18000a919  call    cs:__imp_RegCloseKey
0x18000a91f  mov     rcx, [rbp+var_20]; hKey
0x18000a923  test    rcx, rcx
0x18000a926  jz      short loc_18000A92E
0x18000a928  call    cs:__imp_RegCloseKey
0x18000a92e  mov     eax, ebx
0x18000a930  add     rsp, 78h
0x18000a934  pop     r15
0x18000a936  pop     r14
0x18000a938  pop     r12
0x18000a93a  pop     rdi
0x18000a93b  pop     rbx
0x18000a93c  pop     rbp
0x18000a93d  retn
```
