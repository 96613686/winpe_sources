# DllRegisterServer

- ea: `0x1800bff40`
- end: `0x1800c019c`
- name: `DllRegisterServer`
- size: `604`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180099040`
- `0x1800994a0`
- `0x1800b7084`
- `0x1800bfec0`
- `0x1800bff40`
- `0x1800c6950`
- `0x1800c6b44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bffac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bffac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bffe7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c001b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bffe7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c001b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c002c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c002c`
- `msdmo!DMORegister` at `0x1800c00dd`
- `msdmo!DMORegister` at `0x1800c00dd`
- `MFPlat!MFTRegister` at `0x1800c0140`
- `MFPlat!MFTRegister` at `0x1800c0140`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rcx
  HRESULT v1; // ebx
  __int64 v2; // rcx
  __int64 v3; // rcx
  const DMO_PARTIAL_MEDIATYPE *v4; // r15
  MFT_REGISTER_TYPE_INFO *v5; // r14
  __int64 v6; // rcx
  MFT_REGISTER_TYPE_INFO *v7; // rsi
  const DMO_PARTIAL_MEDIATYPE *pOutTypes; // rdi
  __int64 v9; // rcx
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  GUID guidCategory; // [rsp+60h] [rbp-A0h] BYREF
  CLSID clsidMFT; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[80]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  v1 = sub_1800C6B44();
  if ( v1 < 0 )
    return v1;
  v1 = sub_1800C6950(v0, SubKey);
  if ( v1 < 0 )
    return v1;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 2u, &hKey) )
  {
    *(_DWORD *)Data = 8388609;
    RegSetValueExW(hKey, L"Merit", 0, 4u, Data, 4u);
    *(_DWORD *)Data = 256;
    RegSetValueExW(hKey, L"WMSDKMerit", 0, 4u, Data, 4u);
    RegCloseKey(hKey);
  }
  v4 = (const DMO_PARTIAL_MEDIATYPE *)sub_1800BFEC0(v2, 9, off_180212220);
  if ( !v4 )
    return -2147024882;
  v5 = 0;
  v7 = (MFT_REGISTER_TYPE_INFO *)sub_1800B7084(v3, 9, off_180212220);
  if ( v7 )
  {
    pOutTypes = (const DMO_PARTIAL_MEDIATYPE *)sub_1800BFEC0(v6, 13, &off_180210040);
    if ( pOutTypes )
    {
      v5 = (MFT_REGISTER_TYPE_INFO *)sub_1800B7084(v9, 13, off_1802122E0);
      v1 = DMORegister(L"WMVideo Decoder DMO", &clsidDMO, &::guidCategory, 0, 9u, v4, 0xDu, pOutTypes);
      if ( v1 >= 0 )
      {
        guidCategory = (GUID)xmmword_18021E9F8;
        clsidMFT = clsidDMO;
        v1 = MFTRegister(&clsidMFT, &guidCategory, (LPWSTR)L"WMVideo Decoder DMO", 0, 0, v7, 0xDu, v5, 0);
      }
      goto LABEL_13;
    }
  }
  else
  {
    pOutTypes = 0;
  }
  v1 = -2147024882;
LABEL_13:
  j_j__o_free(v4);
  if ( pOutTypes )
    j_j__o_free(pOutTypes);
  if ( v7 )
    j_j__o_free(v7);
  if ( v5 )
    j_j__o_free(v5);
  return v1;
}

```

## disassembly

```asm
0x1800bff40  push    rbp
0x1800bff42  push    rbx
0x1800bff43  push    rsi
0x1800bff44  push    rdi
0x1800bff45  push    r14
0x1800bff47  push    r15
0x1800bff49  lea     rbp, [rsp-38h]
0x1800bff4e  sub     rsp, 138h
0x1800bff55  mov     rax, cs:__security_cookie
0x1800bff5c  xor     rax, rsp
0x1800bff5f  mov     [rbp+60h+var_40], rax
0x1800bff63  mov     [rsp+160h+hKey], 0
0x1800bff6c  call    sub_1800C6B44
0x1800bff71  mov     ebx, eax
0x1800bff73  test    eax, eax
0x1800bff75  js      loc_1800C017D
0x1800bff7b  lea     rdx, [rbp+60h+SubKey]
0x1800bff7f  call    sub_1800C6950
0x1800bff84  mov     ebx, eax
0x1800bff86  test    eax, eax
0x1800bff88  js      loc_1800C017D
0x1800bff8e  lea     rax, [rsp+160h+hKey]
0x1800bff93  mov     r9d, 2; samDesired
0x1800bff99  xor     r8d, r8d; ulOptions
0x1800bff9c  mov     [rsp+160h+phkResult], rax; phkResult
0x1800bffa1  lea     rdx, [rbp+60h+SubKey]; lpSubKey
0x1800bffa5  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800bffac  call    cs:RegOpenKeyExW
0x1800bffb3  nop     dword ptr [rax+rax+00h]
0x1800bffb8  test    eax, eax
0x1800bffba  jnz     short loc_1800C0038
0x1800bffbc  mov     rcx, [rsp+160h+hKey]; hKey
0x1800bffc1  lea     ebx, [rax+4]
0x1800bffc4  lea     rax, [rsp+160h+Data]
0x1800bffc9  mov     [rsp+160h+cbData], ebx; cbData
0x1800bffcd  mov     r9d, ebx; dwType
0x1800bffd0  mov     [rsp+160h+phkResult], rax; lpData
0x1800bffd5  xor     r8d, r8d; Reserved
0x1800bffd8  mov     dword ptr [rsp+160h+Data], 800001h
0x1800bffe0  lea     rdx, aMerit; "Merit"
0x1800bffe7  call    cs:RegSetValueExW
0x1800bffee  nop     dword ptr [rax+rax+00h]
0x1800bfff3  mov     rcx, [rsp+160h+hKey]; hKey
0x1800bfff8  lea     rax, [rsp+160h+Data]
0x1800bfffd  mov     [rsp+160h+cbData], ebx; cbData
0x1800c0001  lea     rdx, aWmsdkmerit; "WMSDKMerit"
0x1800c0008  mov     r9d, ebx; dwType
0x1800c000b  mov     [rsp+160h+phkResult], rax; lpData
0x1800c0010  xor     r8d, r8d; Reserved
0x1800c0013  mov     dword ptr [rsp+160h+Data], 100h
0x1800c001b  call    cs:RegSetValueExW
0x1800c0022  nop     dword ptr [rax+rax+00h]
0x1800c0027  mov     rcx, [rsp+160h+hKey]; hKey
0x1800c002c  call    cs:RegCloseKey
0x1800c0033  nop     dword ptr [rax+rax+00h]
0x1800c0038  mov     ebx, 9
0x1800c003d  lea     r8, off_180212220
0x1800c0044  mov     edx, ebx
0x1800c0046  call    sub_1800BFEC0
0x1800c004b  mov     r15, rax
0x1800c004e  test    rax, rax
0x1800c0051  jnz     short loc_1800C005D
0x1800c0053  mov     ebx, 8007000Eh
0x1800c0058  jmp     loc_1800C017D
0x1800c005d  lea     r8, off_180212220
0x1800c0064  mov     edx, ebx
0x1800c0066  xor     r14d, r14d
0x1800c0069  call    sub_1800B7084
0x1800c006e  mov     rsi, rax
0x1800c0071  test    rax, rax
0x1800c0074  jnz     short loc_1800C0082
0x1800c0076  xor     edi, edi
0x1800c0078  mov     ebx, 8007000Eh
0x1800c007d  jmp     loc_1800C014E
0x1800c0082  lea     r8, off_180210040
0x1800c0089  mov     edx, 0Dh
0x1800c008e  call    sub_1800BFEC0
0x1800c0093  mov     rdi, rax
0x1800c0096  test    rax, rax
0x1800c0099  jz      short loc_1800C0078
0x1800c009b  lea     r8, off_1802122E0; "NV12"
0x1800c00a2  mov     edx, 0Dh
0x1800c00a7  call    sub_1800B7084
0x1800c00ac  mov     [rsp+160h+pOutTypes], rdi; pOutTypes
0x1800c00b1  lea     r8, guidCategory; guidCategory
0x1800c00b8  mov     [rsp+160h+cOutTypes], 0Dh; cOutTypes
0x1800c00c0  lea     rdx, clsidDMO; clsidDMO
0x1800c00c7  mov     qword ptr [rsp+160h+cbData], r15; pInTypes
0x1800c00cc  lea     rcx, pszName; "WMVideo Decoder DMO"
0x1800c00d3  xor     r9d, r9d; dwFlags
0x1800c00d6  mov     dword ptr [rsp+160h+phkResult], ebx; cInTypes
0x1800c00da  mov     r14, rax
0x1800c00dd  call    cs:DMORegister
0x1800c00e4  nop     dword ptr [rax+rax+00h]
0x1800c00e9  mov     ebx, eax
0x1800c00eb  test    eax, eax
0x1800c00ed  js      short loc_1800C014E
0x1800c00ef  movups  xmm0, cs:xmmword_18021E9F8
0x1800c00f6  mov     [rsp+160h+pAttributes], 0; pAttributes
0x1800c00ff  xor     r9d, r9d; Flags
0x1800c0102  movups  xmm1, xmmword ptr cs:clsidDMO.Data1
0x1800c0109  mov     [rsp+160h+pOutTypes], r14; pOutputTypes
0x1800c010e  lea     r8, pszName; "WMVideo Decoder DMO"
0x1800c0115  mov     [rsp+160h+cOutTypes], 0Dh; cOutputTypes
0x1800c011d  lea     rdx, [rsp+160h+guidCategory]; guidCategory
0x1800c0122  mov     qword ptr [rsp+160h+cbData], rsi; pInputTypes
0x1800c0127  lea     rcx, [rsp+160h+clsidMFT]; clsidMFT
0x1800c012c  movdqu  xmmword ptr [rsp+160h+guidCategory.Data1], xmm0
0x1800c0132  mov     dword ptr [rsp+160h+phkResult], 0; cInputTypes
0x1800c013a  movdqu  xmmword ptr [rsp+160h+clsidMFT.Data1], xmm1
0x1800c0140  call    cs:MFTRegister
0x1800c0147  nop     dword ptr [rax+rax+00h]
0x1800c014c  mov     ebx, eax
0x1800c014e  mov     rcx, r15
0x1800c0151  call    j_j__o_free
0x1800c0156  test    rdi, rdi
0x1800c0159  jz      short loc_1800C0163
0x1800c015b  mov     rcx, rdi
0x1800c015e  call    j_j__o_free
0x1800c0163  test    rsi, rsi
0x1800c0166  jz      short loc_1800C0170
0x1800c0168  mov     rcx, rsi
0x1800c016b  call    j_j__o_free
0x1800c0170  test    r14, r14
0x1800c0173  jz      short loc_1800C017D
0x1800c0175  mov     rcx, r14
0x1800c0178  call    j_j__o_free
0x1800c017d  mov     eax, ebx
0x1800c017f  mov     rcx, [rbp+60h+var_40]
0x1800c0183  xor     rcx, rsp; StackCookie
0x1800c0186  call    __security_check_cookie
0x1800c018b  add     rsp, 138h
0x1800c0192  pop     r15
0x1800c0194  pop     r14
0x1800c0196  pop     rdi
0x1800c0197  pop     rsi
0x1800c0198  pop     rbx
0x1800c0199  pop     rbp
0x1800c019a  retn
```
