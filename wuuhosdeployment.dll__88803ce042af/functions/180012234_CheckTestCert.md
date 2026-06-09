# CheckTestCert

- ea: `0x180012234`
- end: `0x18001233e`
- name: `CheckTestCert`
- size: `266`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180012784`
- `0x180012ab0`
- `0x180012e10`

## callees

- `0x18000956c`
- `0x1800114b8`
- `0x180012234`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012318`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012318`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800122d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800122d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001228d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001228d`

## string_xrefs

- `0x18001227f`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1800122dd`: `Test certificate found in registry.`

## pseudocode

```c
__int64 __fastcall CheckTestCert(__int64 a1)
{
  unsigned int v2; // ebx
  _QWORD v4[2]; // [rsp+30h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  BYTE Data[24]; // [rsp+50h] [rbp-20h] BYREF

  v2 = -2145078525;
  if ( a1 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
            0,
            1u,
            &hKey) )
    {
      v4[1] = Data;
      cbData = 20;
      v4[0] = 1;
      if ( RegQueryValueExW(hKey, L"TestCert", 0, 0, Data, &cbData) >= 0 )
      {
        WUTrace(0, 0, 32, 4);
        v2 = VerifyKnownCerts(a1, v4);
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180012234  mov     [rsp-8+arg_8], rbx
0x180012239  mov     [rsp-8+arg_10], rdi
0x18001223e  push    rbp
0x18001223f  mov     rbp, rsp
0x180012242  sub     rsp, 70h
0x180012246  mov     rax, cs:__security_cookie
0x18001224d  xor     rax, rsp
0x180012250  mov     [rbp+var_8], rax
0x180012254  mov     rdi, rcx
0x180012257  mov     ebx, 8024B303h
0x18001225c  test    rcx, rcx
0x18001225f  jz      loc_18001231E
0x180012265  lea     rax, [rbp+hKey]
0x180012269  mov     [rbp+hKey], 0
0x180012271  mov     r9d, 1; samDesired
0x180012277  mov     [rsp+70h+phkResult], rax; phkResult
0x18001227c  xor     r8d, r8d; ulOptions
0x18001227f  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180012286  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001228d  call    cs:__imp_RegOpenKeyExW
0x180012293  test    eax, eax
0x180012295  jnz     short loc_18001230F
0x180012297  mov     rcx, [rbp+hKey]; hKey
0x18001229b  lea     rax, [rbp+Data]
0x18001229f  mov     [rbp+var_38], rax
0x1800122a3  lea     rdx, ValueName; "TestCert"
0x1800122aa  lea     rax, [rbp+cbData]
0x1800122ae  mov     [rbp+cbData], 14h
0x1800122b5  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800122ba  xor     r9d, r9d; lpType
0x1800122bd  lea     rax, [rbp+Data]
0x1800122c1  mov     [rbp+var_40], 1
0x1800122c9  xor     r8d, r8d; lpReserved
0x1800122cc  mov     [rsp+70h+phkResult], rax; lpData
0x1800122d1  call    cs:__imp_RegQueryValueExW
0x1800122d7  test    eax, eax
0x1800122d9  js      short loc_18001230F
0x1800122db  xor     edx, edx
0x1800122dd  lea     rax, aTestCertificat; "Test certificate found in registry."
0x1800122e4  mov     [rsp+70h+lpcbData], rax
0x1800122e9  xor     ecx, ecx
0x1800122eb  mov     [rsp+70h+phkResult], 0
0x1800122f4  lea     r9d, [rdx+4]
0x1800122f8  lea     r8d, [rdx+20h]
0x1800122fc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180012301  lea     rdx, [rbp+var_40]
0x180012305  mov     rcx, rdi
0x180012308  call    VerifyKnownCerts
0x18001230d  mov     ebx, eax
0x18001230f  mov     rcx, [rbp+hKey]; hKey
0x180012313  test    rcx, rcx
0x180012316  jz      short loc_18001231E
0x180012318  call    cs:__imp_RegCloseKey
0x18001231e  mov     eax, ebx
0x180012320  mov     rcx, [rbp+var_8]
0x180012324  xor     rcx, rsp; StackCookie
0x180012327  call    __security_check_cookie
0x18001232c  lea     r11, [rsp+70h+var_s0]
0x180012331  mov     rbx, [r11+18h]
0x180012335  mov     rdi, [r11+20h]
0x180012339  mov     rsp, r11
0x18001233c  pop     rbp
0x18001233d  retn
```
