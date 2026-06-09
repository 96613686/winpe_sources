# EcbBootPlanFinalSaveDiskData

- ea: `0x1800b1c20`
- end: `0x1800b1f31`
- name: `EcbBootPlanFinalSaveDiskData`
- size: `785`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062740`

## callees

- `0x180021e0c`
- `0x1800b1c20`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1f10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b1f10`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1cd3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1d06`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1d39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1d9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1dd0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1e36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1e9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1ecb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1efe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1cd3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1d06`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1d39`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1d9d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1dd0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1e36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1e9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1ecb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1efe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b1c9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b1c9c`

## string_xrefs

- `0x1800b1ef7`: `VolumeCreateTime`

## pseudocode

```c
__int64 __fastcall EcbBootPlanFinalSaveDiskData(__int64 a1)
{
  unsigned int v2; // ebx
  HRESULT v3; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[104]; // [rsp+60h] [rbp-A0h] BYREF

  dwDisposition = 0;
  hKey = 0;
  v2 = RegCreateKeyExW(
         *(HKEY *)(*(_QWORD *)&PfSvcGlobals + 1432LL),
         L"DiskAssessment",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         &dwDisposition);
  if ( !v2 )
  {
    v2 = RegSetValueExW(hKey, L"DiskNumber", 0, 4u, (const BYTE *)(a1 + 552), 4u);
    if ( !v2 )
    {
      v2 = RegSetValueExW(hKey, L"RPM", 0, 4u, (const BYTE *)(a1 + 584), 4u);
      if ( !v2 )
      {
        v2 = RegSetValueExW(hKey, L"SizeInGb", 0, 4u, (const BYTE *)(a1 + 572), 4u);
        if ( !v2 )
        {
          v3 = StringCchPrintfW(pszDest, 0x64u, L"%16.10f", *(_QWORD *)(a1 + 592));
          if ( v3 < 0 )
          {
LABEL_6:
            v2 = (unsigned __int16)v3;
            goto LABEL_15;
          }
          v2 = RegSetValueExW(hKey, L"PeakTransferMBsPerSecond", 0, 1u, (const BYTE *)pszDest, 0x3Cu);
          if ( !v2 )
          {
            v2 = RegSetValueExW(hKey, L"SeekBreakPages", 0, 4u, (const BYTE *)(a1 + 616), 4u);
            if ( !v2 )
            {
              v3 = StringCchPrintfW(pszDest, 0x64u, L"%16.10f", *(double *)(a1 + 600) * 1000.0);
              if ( v3 < 0 )
                goto LABEL_6;
              v2 = RegSetValueExW(hKey, L"LongSeekMicrosecondsBase", 0, v2 + 1, (const BYTE *)pszDest, 0x3Cu);
              if ( !v2 )
              {
                v3 = StringCchPrintfW(pszDest, 0x64u, L"%16.10f", *(double *)(a1 + 608) * 1000.0);
                if ( v3 < 0 )
                  goto LABEL_6;
                v2 = RegSetValueExW(hKey, L"LongSeekMicrosecondsPerSqrtGB", 0, v2 + 1, (const BYTE *)pszDest, 0x3Cu);
                if ( !v2 )
                {
                  v2 = RegSetValueExW(hKey, L"VolumeSerialNumber", 0, 4u, (const BYTE *)(a1 + 848), 4u);
                  if ( !v2 )
                    v2 = RegSetValueExW(hKey, L"VolumeCreateTime", 0, 0xBu, (const BYTE *)(a1 + 840), 8u);
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1800b1c20  push    rbp
0x1800b1c22  push    rbx
0x1800b1c23  push    rdi
0x1800b1c24  push    r14
0x1800b1c26  lea     rbp, [rsp-48h]
0x1800b1c2b  sub     rsp, 148h
0x1800b1c32  mov     rax, cs:__security_cookie
0x1800b1c39  xor     rax, rsp
0x1800b1c3c  mov     [rbp+60h+var_30], rax
0x1800b1c40  mov     rdi, rcx
0x1800b1c43  mov     [rsp+160h+dwDisposition], 0
0x1800b1c4b  mov     rcx, cs:PfSvcGlobals
0x1800b1c52  lea     rax, [rsp+160h+dwDisposition]
0x1800b1c57  mov     [rsp+160h+lpdwDisposition], rax; lpdwDisposition
0x1800b1c5c  lea     rdx, aDiskassessment; "DiskAssessment"
0x1800b1c63  lea     rax, [rsp+160h+hKey]
0x1800b1c68  mov     [rsp+160h+hKey], 0
0x1800b1c71  mov     [rsp+160h+phkResult], rax; phkResult
0x1800b1c76  xor     r9d, r9d; lpClass
0x1800b1c79  mov     rcx, [rcx+598h]; hKey
0x1800b1c80  xor     r8d, r8d; Reserved
0x1800b1c83  mov     [rsp+160h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800b1c8c  mov     [rsp+160h+samDesired], 2; samDesired
0x1800b1c94  mov     [rsp+160h+dwOptions], 0; dwOptions
0x1800b1c9c  call    cs:__imp_RegCreateKeyExW
0x1800b1ca2  mov     ebx, eax
0x1800b1ca4  test    eax, eax
0x1800b1ca6  jnz     loc_1800B1F06
0x1800b1cac  mov     rcx, [rsp+160h+hKey]; hKey
0x1800b1cb1  lea     r14d, [rbx+4]
0x1800b1cb5  lea     rax, [rdi+228h]
0x1800b1cbc  mov     [rsp+160h+samDesired], r14d; cbData
0x1800b1cc1  mov     r9d, r14d; dwType
0x1800b1cc4  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x1800b1cc9  xor     r8d, r8d; Reserved
0x1800b1ccc  lea     rdx, aDisknumber; "DiskNumber"
0x1800b1cd3  call    cs:__imp_RegSetValueExW
0x1800b1cd9  mov     ebx, eax
0x1800b1cdb  test    eax, eax
0x1800b1cdd  jnz     loc_1800B1F06
0x1800b1ce3  mov     rcx, [rsp+160h+hKey]; hKey
0x1800b1ce8  lea     rax, [rdi+248h]
0x1800b1cef  mov     [rsp+160h+samDesired], r14d; cbData
0x1800b1cf4  lea     rdx, aRpm; "RPM"
0x1800b1cfb  mov     r9d, r14d; dwType
0x1800b1cfe  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x1800b1d03  xor     r8d, r8d; Reserved
0x1800b1d06  call    cs:__imp_RegSetValueExW
0x1800b1d0c  mov     ebx, eax
0x1800b1d0e  test    eax, eax
0x1800b1d10  jnz     loc_1800B1F06
0x1800b1d16  mov     rcx, [rsp+160h+hKey]; hKey
0x1800b1d1b  lea     rax, [rdi+23Ch]
0x1800b1d22  mov     [rsp+160h+samDesired], r14d; cbData
0x1800b1d27  lea     rdx, aSizeingb; "SizeInGb"
0x1800b1d2e  mov     r9d, r14d; dwType
0x1800b1d31  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x1800b1d36  xor     r8d, r8d; Reserved
0x1800b1d39  call    cs:__imp_RegSetValueExW
0x1800b1d3f  mov     ebx, eax
0x1800b1d41  test    eax, eax
0x1800b1d43  jnz     loc_1800B1F06
0x1800b1d49  movsd   xmm3, qword ptr [rdi+250h]
0x1800b1d51  lea     r8, a1610f; "%16.10f"
0x1800b1d58  movq    r9, xmm3
0x1800b1d5d  lea     edx, [rax+64h]; cchDest
0x1800b1d60  lea     rcx, [rsp+160h+pszDest]; pszDest
0x1800b1d65  call    StringCchPrintfW
0x1800b1d6a  test    eax, eax
0x1800b1d6c  jns     short loc_1800B1D76
0x1800b1d6e  movzx   ebx, ax
0x1800b1d71  jmp     loc_1800B1F06
0x1800b1d76  mov     rcx, [rsp+160h+hKey]; hKey
0x1800b1d7b  lea     rax, [rsp+160h+pszDest]
0x1800b1d80  mov     [rsp+160h+samDesired], 3Ch ; '<'; cbData
0x1800b1d88  lea     rdx, aPeaktransfermb; "PeakTransferMBsPerSecond"
0x1800b1d8f  mov     r9d, 1; dwType
0x1800b1d95  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x1800b1d9a  xor     r8d, r8d; Reserved
0x1800b1d9d  call    cs:__imp_RegSetValueExW
0x1800b1da3  mov     ebx, eax
0x1800b1da5  test    eax, eax
0x1800b1da7  jnz     loc_1800B1F06
0x1800b1dad  mov     rcx, [rsp+160h+hKey]; hKey
0x1800b1db2  lea     rax, [rdi+268h]
0x1800b1db9  mov     [rsp+160h+samDesired], r14d; cbData
0x1800b1dbe  lea     rdx, aSeekbreakpages; "SeekBreakPages"
0x1800b1dc5  mov     r9d, r14d; dwType
0x1800b1dc8  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x1800b1dcd  xor     r8d, r8d; Reserved
0x1800b1dd0  call    cs:__imp_RegSetValueExW
0x1800b1dd6  mov     ebx, eax
0x1800b1dd8  test    eax, eax
0x1800b1dda  jnz     loc_1800B1F06
0x1800b1de0  movsd   xmm3, qword ptr [rdi+258h]
0x1800b1de8  lea     r8, a1610f; "%16.10f"
0x1800b1def  mulsd   xmm3, cs:__real@408f400000000000
0x1800b1df7  lea     edx, [rax+64h]; cchDest
0x1800b1dfa  lea     rcx, [rsp+160h+pszDest]; pszDest
0x1800b1dff  movq    r9, xmm3
0x1800b1e04  call    StringCchPrintfW
0x1800b1e09  test    eax, eax
0x1800b1e0b  js      loc_1800B1D6E
0x1800b1e11  mov     rcx, [rsp+160h+hKey]; hKey
0x1800b1e16  lea     rax, [rsp+160h+pszDest]
0x1800b1e1b  mov     [rsp+160h+samDesired], 3Ch ; '<'; cbData
0x1800b1e23  lea     r9d, [rbx+1]; dwType
0x1800b1e27  xor     r8d, r8d; Reserved
0x1800b1e2a  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x1800b1e2f  lea     rdx, aLongseekmicros_0; "LongSeekMicrosecondsBase"
0x1800b1e36  call    cs:__imp_RegSetValueExW
0x1800b1e3c  mov     ebx, eax
0x1800b1e3e  test    eax, eax
0x1800b1e40  jnz     loc_1800B1F06
0x1800b1e46  movsd   xmm3, qword ptr [rdi+260h]
0x1800b1e4e  lea     r8, a1610f; "%16.10f"
0x1800b1e55  mulsd   xmm3, cs:__real@408f400000000000
0x1800b1e5d  lea     edx, [rax+64h]; cchDest
0x1800b1e60  lea     rcx, [rsp+160h+pszDest]; pszDest
0x1800b1e65  movq    r9, xmm3
0x1800b1e6a  call    StringCchPrintfW
0x1800b1e6f  test    eax, eax
0x1800b1e71  js      loc_1800B1D6E
0x1800b1e77  mov     rcx, [rsp+160h+hKey]; hKey
0x1800b1e7c  lea     rax, [rsp+160h+pszDest]
0x1800b1e81  mov     [rsp+160h+samDesired], 3Ch ; '<'; cbData
0x1800b1e89  lea     r9d, [rbx+1]; dwType
0x1800b1e8d  xor     r8d, r8d; Reserved
0x1800b1e90  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x1800b1e95  lea     rdx, aLongseekmicros; "LongSeekMicrosecondsPerSqrtGB"
0x1800b1e9c  call    cs:__imp_RegSetValueExW
0x1800b1ea2  mov     ebx, eax
0x1800b1ea4  test    eax, eax
0x1800b1ea6  jnz     short loc_1800B1F06
0x1800b1ea8  mov     rcx, [rsp+160h+hKey]; hKey
0x1800b1ead  lea     rax, [rdi+350h]
0x1800b1eb4  mov     [rsp+160h+samDesired], r14d; cbData
0x1800b1eb9  lea     rdx, aVolumeserialnu; "VolumeSerialNumber"
0x1800b1ec0  mov     r9d, r14d; dwType
0x1800b1ec3  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x1800b1ec8  xor     r8d, r8d; Reserved
0x1800b1ecb  call    cs:__imp_RegSetValueExW
0x1800b1ed1  mov     ebx, eax
0x1800b1ed3  test    eax, eax
0x1800b1ed5  jnz     short loc_1800B1F06
0x1800b1ed7  mov     rcx, [rsp+160h+hKey]; hKey
0x1800b1edc  lea     rax, [rdi+348h]
0x1800b1ee3  mov     [rsp+160h+samDesired], 8; cbData
0x1800b1eeb  lea     r9d, [rbx+0Bh]; dwType
0x1800b1eef  xor     r8d, r8d; Reserved
0x1800b1ef2  mov     qword ptr [rsp+160h+dwOptions], rax; lpData
0x1800b1ef7  lea     rdx, aVolumecreateti; "VolumeCreateTime"
0x1800b1efe  call    cs:__imp_RegSetValueExW
0x1800b1f04  mov     ebx, eax
0x1800b1f06  mov     rcx, [rsp+160h+hKey]; hKey
0x1800b1f0b  test    rcx, rcx
0x1800b1f0e  jz      short loc_1800B1F16
0x1800b1f10  call    cs:__imp_RegCloseKey
0x1800b1f16  mov     eax, ebx
0x1800b1f18  mov     rcx, [rbp+60h+var_30]
0x1800b1f1c  xor     rcx, rsp; StackCookie
0x1800b1f1f  call    __security_check_cookie
0x1800b1f24  add     rsp, 148h
0x1800b1f2b  pop     r14
0x1800b1f2d  pop     rdi
0x1800b1f2e  pop     rbx
0x1800b1f2f  pop     rbp
0x1800b1f30  retn
```
