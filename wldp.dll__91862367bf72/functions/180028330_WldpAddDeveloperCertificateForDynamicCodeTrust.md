# WldpAddDeveloperCertificateForDynamicCodeTrust

- ea: `0x180028330`
- end: `0x180028666`
- name: `WldpAddDeveloperCertificateForDynamicCodeTrust`
- size: `822`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800049d0`
- `0x180021ec0`
- `0x180027fd0`
- `0x180028330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180028413`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180028413`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002860c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002861e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002860c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002861e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028627`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800283dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800283dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800283b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028538`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180028538`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800285cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028637`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800285cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028637`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800285ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800285ad`
- `ntdll!NtSetSystemInformation` at `0x1800285ed`
- `ntdll!NtSetSystemInformation` at `0x1800285ed`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800283a8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180028401`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180028495`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800283a8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180028401`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180028495`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800284dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800284dd`

## pseudocode

```c
__int64 __fastcall WldpAddDeveloperCertificateForDynamicCodeTrust(PCCERT_CONTEXT pCertContext)
{
  wchar_t *v2; // rsi
  signed int LastError; // eax
  int SepRegistryLocation; // ebx
  wchar_t *v5; // rax
  wchar_t *v6; // r10
  wchar_t **i; // rax
  wchar_t *v8; // rcx
  int v9; // r9d
  int v10; // r8d
  DWORD v11; // ecx
  LSTATUS v12; // eax
  DWORD j; // edi
  LSTATUS v14; // eax
  NTSTATUS v15; // ebx
  unsigned __int8 v17[4]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-90h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-88h] BYREF
  _OWORD SystemInformation[2]; // [rsp+90h] [rbp-70h] BYREF
  BYTE pvData[64]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[264]; // [rsp+F0h] [rbp-10h] BYREF

  pcbData = 0;
  cbData = 0;
  hKey = 0;
  lpSubKey = 0;
  v17[0] = 0;
  SecurityDescriptor = 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !CertGetCertificateContextProperty(pCertContext, 0x59u, 0, &pcbData) )
  {
    v2 = 0;
LABEL_3:
    LastError = GetLastError();
    SepRegistryLocation = LastError;
    if ( LastError > 0 )
      SepRegistryLocation = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_36;
  }
  v5 = (wchar_t *)LocalAlloc(0x40u, pcbData);
  v2 = v5;
  if ( !v5 )
  {
    SepRegistryLocation = -2147024882;
    goto LABEL_36;
  }
  if ( !CertGetCertificateContextProperty(pCertContext, 0x59u, v5, &pcbData) )
    goto LABEL_3;
  v6 = wcschr(v2, 0x2Fu);
  if ( !v6 )
  {
LABEL_9:
    SepRegistryLocation = -2147418113;
    goto LABEL_36;
  }
  for ( i = &off_180043B10; ; i += 2 )
  {
    if ( i == off_180043B50 )
      goto LABEL_35;
    v8 = *i;
    do
    {
      v9 = *(wchar_t *)((char *)v8 + (char *)(v6 + 1) - (char *)*i);
      v10 = *v8 - v9;
      if ( v10 )
        break;
      ++v8;
    }
    while ( v9 );
    if ( !v10 )
      break;
  }
  v11 = *((_DWORD *)i + 3);
  cbData = v11;
  if ( !*((_DWORD *)i + 2) )
  {
LABEL_35:
    SepRegistryLocation = -805306355;
    goto LABEL_36;
  }
  if ( v11 > 0x40 )
    goto LABEL_9;
  if ( !CertGetCertificateContextProperty(pCertContext, 0xFu, pvData, &cbData) )
    goto LABEL_3;
  SepRegistryLocation = WldpGetSepRegistryLocation(
                          L"CIDeveloperCerts",
                          L"SYSTEM\\CurrentControlSet\\Control\\CI\\Developer\\DeveloperUnlockCertificates",
                          v17,
                          (unsigned __int16 **)&lpSubKey);
  if ( SepRegistryLocation < 0 )
    goto LABEL_36;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;CIID;KA;;;SY)(A;CIID;KA;;;BA)(A;CIID;KR;;;WD)(A;CIID;KR;;;RC)(A;;KR;;;AC)(A;;KR;;;S-1-15-3-1024-1"
           "065365936-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681)",
          1u,
          &SecurityDescriptor,
          0) )
    goto LABEL_3;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, &SecurityAttributes, &hKey, 0);
  SepRegistryLocation = v12;
  if ( v12 > 0 )
    SepRegistryLocation = (unsigned __int16)v12 | 0x80070000;
  if ( SepRegistryLocation >= 0 )
  {
    for ( j = 0; j < cbData; ++j )
    {
      SepRegistryLocation = StringCchPrintfW(&ValueName[2 * j], 6u, L"%02X", pvData[j]);
      if ( SepRegistryLocation < 0 )
        goto LABEL_36;
    }
    v14 = RegSetValueExW(hKey, ValueName, 0, 3u, pvData, cbData);
    SepRegistryLocation = v14;
    if ( v14 > 0 )
      SepRegistryLocation = (unsigned __int16)v14 | 0x80070000;
    if ( SepRegistryLocation >= 0 )
    {
      RegCloseKey(hKey);
      hKey = 0;
      LODWORD(SystemInformation[0]) = 0x10000000;
      v15 = NtSetSystemInformation(SystemContextSwitchInformation|0x80, SystemInformation, 0x20u);
      if ( v15 >= 0 )
        SepRegistryLocation = 0;
      else
        SepRegistryLocation = v15 | 0x10000000;
    }
  }
LABEL_36:
  LocalFree(SecurityDescriptor);
  if ( v17[0] )
    LocalFree((HLOCAL)lpSubKey);
  LocalFree(v2);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)SepRegistryLocation;
}

```

## disassembly

```asm
0x180028330  mov     [rsp-8+arg_8], rbx
0x180028335  mov     [rsp-8+arg_10], rsi
0x18002833a  push    rbp
0x18002833b  push    rdi
0x18002833c  push    r14
0x18002833e  lea     rbp, [rsp-210h]
0x180028346  sub     rsp, 310h
0x18002834d  mov     rax, cs:__security_cookie
0x180028354  xor     rax, rsp
0x180028357  mov     [rbp+220h+var_20], rax
0x18002835e  xor     r14d, r14d
0x180028361  lea     r9, [rsp+320h+pcbData]; pcbData
0x180028366  xor     eax, eax
0x180028368  mov     [rsp+320h+pcbData], r14d
0x18002836d  xorps   xmm0, xmm0
0x180028370  mov     [rsp+320h+cbData], r14d
0x180028375  xorps   xmm1, xmm1
0x180028378  mov     [rsp+320h+hKey], r14
0x18002837d  xor     r8d, r8d; pvData
0x180028380  mov     [rsp+320h+lpSubKey], r14
0x180028385  lea     edi, [rax+59h]
0x180028388  mov     [rsp+320h+var_2D0], r14b
0x18002838d  mov     edx, edi; dwPropId
0x18002838f  mov     [rsp+320h+SecurityDescriptor], r14
0x180028394  mov     rbx, rcx
0x180028397  mov     qword ptr [rbp+220h+SecurityAttributes.bInheritHandle], rax
0x18002839b  movups  [rbp+220h+SystemInformation], xmm0
0x18002839f  movups  [rbp+220h+var_280], xmm0
0x1800283a3  movups  xmmword ptr [rsp+320h+SecurityAttributes.nLength], xmm1
0x1800283a8  call    cs:__imp_CertGetCertificateContextProperty
0x1800283ae  test    eax, eax
0x1800283b0  jnz     short loc_1800283D3
0x1800283b2  mov     esi, r14d
0x1800283b5  call    cs:__imp_GetLastError
0x1800283bb  mov     ebx, eax
0x1800283bd  test    eax, eax
0x1800283bf  jle     loc_180028607
0x1800283c5  movzx   ebx, ax
0x1800283c8  or      ebx, 80070000h
0x1800283ce  jmp     loc_180028607
0x1800283d3  mov     edx, [rsp+320h+pcbData]; uBytes
0x1800283d7  mov     ecx, 40h ; '@'; uFlags
0x1800283dc  call    cs:__imp_LocalAlloc
0x1800283e2  mov     rsi, rax
0x1800283e5  test    rax, rax
0x1800283e8  jnz     short loc_1800283F4
0x1800283ea  mov     ebx, 8007000Eh
0x1800283ef  jmp     loc_180028607
0x1800283f4  lea     r9, [rsp+320h+pcbData]; pcbData
0x1800283f9  mov     r8, rsi; pvData
0x1800283fc  mov     edx, edi; dwPropId
0x1800283fe  mov     rcx, rbx; pCertContext
0x180028401  call    cs:__imp_CertGetCertificateContextProperty
0x180028407  test    eax, eax
0x180028409  jz      short loc_1800283B5
0x18002840b  mov     edx, 2Fh ; '/'; Ch
0x180028410  mov     rcx, rsi; Str
0x180028413  call    cs:__imp_wcschr
0x180028419  mov     r10, rax
0x18002841c  test    rax, rax
0x18002841f  jnz     short loc_18002842B
0x180028421  mov     ebx, 8000FFFFh
0x180028426  jmp     loc_180028607
0x18002842b  lea     rax, off_180043B10; "SHA1"
0x180028432  lea     rcx, off_180043B50; "SVCHOST"
0x180028439  cmp     rax, rcx
0x18002843c  jz      loc_180028602
0x180028442  mov     rcx, [rax]
0x180028445  lea     rdx, [r10+2]
0x180028449  sub     rdx, rcx
0x18002844c  movzx   r8d, word ptr [rcx]
0x180028450  movzx   r9d, word ptr [rcx+rdx]
0x180028455  sub     r8d, r9d
0x180028458  jnz     short loc_180028463
0x18002845a  add     rcx, 2
0x18002845e  test    r9d, r9d
0x180028461  jnz     short loc_18002844C
0x180028463  test    r8d, r8d
0x180028466  jz      short loc_18002846E
0x180028468  add     rax, 10h
0x18002846c  jmp     short loc_180028432
0x18002846e  mov     ecx, [rax+0Ch]
0x180028471  mov     [rsp+320h+cbData], ecx
0x180028475  cmp     [rax+8], r14d
0x180028479  jz      loc_180028602
0x18002847f  cmp     ecx, 40h ; '@'
0x180028482  ja      short loc_180028421
0x180028484  lea     r9, [rsp+320h+cbData]; pcbData
0x180028489  mov     edx, 0Fh; dwPropId
0x18002848e  lea     r8, [rbp+220h+pvData]; pvData
0x180028492  mov     rcx, rbx; pCertContext
0x180028495  call    cs:__imp_CertGetCertificateContextProperty
0x18002849b  test    eax, eax
0x18002849d  jz      loc_1800283B5
0x1800284a3  lea     r9, [rsp+320h+lpSubKey]; unsigned __int16 **
0x1800284a8  lea     r8, [rsp+320h+var_2D0]; unsigned __int8 *
0x1800284ad  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\CI"...
0x1800284b4  lea     rcx, aCidevelopercer; "CIDeveloperCerts"
0x1800284bb  call    ?WldpGetSepRegistryLocation@@YAJPEBGPEAGPEAEPEAPEAG@Z; WldpGetSepRegistryLocation(ushort const *,ushort *,uchar *,ushort * *)
0x1800284c0  mov     ebx, eax
0x1800284c2  test    eax, eax
0x1800284c4  js      loc_180028607
0x1800284ca  xor     r9d, r9d; SecurityDescriptorSize
0x1800284cd  lea     r8, [rsp+320h+SecurityDescriptor]; SecurityDescriptor
0x1800284d2  lea     rcx, aOBagBadACiidKa; "O:BAG:BAD:(A;CIID;KA;;;SY)(A;CIID;KA;;;"...
0x1800284d9  lea     edx, [r9+1]; StringSDRevision
0x1800284dd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800284e3  test    eax, eax
0x1800284e5  jz      loc_1800283B5
0x1800284eb  mov     rax, [rsp+320h+SecurityDescriptor]
0x1800284f0  xor     r9d, r9d; lpClass
0x1800284f3  mov     rdx, [rsp+320h+lpSubKey]; lpSubKey
0x1800284f8  xor     r8d, r8d; Reserved
0x1800284fb  mov     [rsp+320h+lpdwDisposition], r14; lpdwDisposition
0x180028500  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028507  mov     [rbp+220h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002850b  lea     rax, [rsp+320h+hKey]
0x180028510  mov     [rsp+320h+phkResult], rax; phkResult
0x180028515  lea     rax, [rsp+320h+SecurityAttributes]
0x18002851a  mov     [rsp+320h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18002851f  mov     [rsp+320h+samDesired], 2001Fh; samDesired
0x180028527  mov     [rsp+320h+dwOptions], r14d; dwOptions
0x18002852c  mov     [rsp+320h+SecurityAttributes.nLength], 18h
0x180028534  mov     [rbp+220h+SecurityAttributes.bInheritHandle], r14d
0x180028538  call    cs:__imp_RegCreateKeyExW
0x18002853e  mov     ebx, eax
0x180028540  test    eax, eax
0x180028542  jle     short loc_18002854D
0x180028544  movzx   ebx, ax
0x180028547  or      ebx, 80070000h
0x18002854d  test    ebx, ebx
0x18002854f  js      loc_180028607
0x180028555  mov     edi, r14d
0x180028558  mov     eax, [rsp+320h+cbData]
0x18002855c  cmp     edi, eax
0x18002855e  jnb     short loc_18002858E
0x180028560  mov     eax, edi
0x180028562  lea     ecx, [rdi+rdi]
0x180028565  lea     r8, a02x; "%02X"
0x18002856c  mov     edx, 6; unsigned __int64
0x180028571  movzx   r9d, [rbp+rax+220h+pvData]
0x180028577  lea     rax, [rbp+220h+ValueName]
0x18002857b  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x18002857f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028584  mov     ebx, eax
0x180028586  test    eax, eax
0x180028588  js      short loc_180028607
0x18002858a  inc     edi
0x18002858c  jmp     short loc_180028558
0x18002858e  mov     rcx, [rsp+320h+hKey]; hKey
0x180028593  lea     rdx, [rbp+220h+ValueName]; lpValueName
0x180028597  mov     [rsp+320h+samDesired], eax; cbData
0x18002859b  mov     r9d, 3; dwType
0x1800285a1  lea     rax, [rbp+220h+pvData]
0x1800285a5  xor     r8d, r8d; Reserved
0x1800285a8  mov     qword ptr [rsp+320h+dwOptions], rax; lpData
0x1800285ad  call    cs:__imp_RegSetValueExW
0x1800285b3  mov     ebx, eax
0x1800285b5  test    eax, eax
0x1800285b7  jle     short loc_1800285C2
0x1800285b9  movzx   ebx, ax
0x1800285bc  or      ebx, 80070000h
0x1800285c2  test    ebx, ebx
0x1800285c4  js      short loc_180028607
0x1800285c6  mov     rcx, [rsp+320h+hKey]; hKey
0x1800285cb  call    cs:__imp_RegCloseKey
0x1800285d1  mov     edi, 10000000h
0x1800285d6  mov     [rsp+320h+hKey], r14
0x1800285db  mov     r8d, 20h ; ' '; SystemInformationLength
0x1800285e1  mov     dword ptr [rbp+220h+SystemInformation], edi
0x1800285e4  lea     rdx, [rbp+220h+SystemInformation]; SystemInformation
0x1800285e8  mov     ecx, 0A4h; SystemInformationClass
0x1800285ed  call    cs:__imp_NtSetSystemInformation
0x1800285f3  mov     ebx, eax
0x1800285f5  test    eax, eax
0x1800285f7  jns     short loc_1800285FD
0x1800285f9  or      ebx, edi
0x1800285fb  jmp     short loc_180028607
0x1800285fd  mov     ebx, r14d
0x180028600  jmp     short loc_180028607
0x180028602  mov     ebx, 0D000000Dh
0x180028607  mov     rcx, [rsp+320h+SecurityDescriptor]; hMem
0x18002860c  call    cs:__imp_LocalFree
0x180028612  cmp     [rsp+320h+var_2D0], r14b
0x180028617  jz      short loc_180028624
0x180028619  mov     rcx, [rsp+320h+lpSubKey]; hMem
0x18002861e  call    cs:__imp_LocalFree
0x180028624  mov     rcx, rsi; hMem
0x180028627  call    cs:__imp_LocalFree
0x18002862d  mov     rcx, [rsp+320h+hKey]; hKey
0x180028632  test    rcx, rcx
0x180028635  jz      short loc_18002863D
0x180028637  call    cs:__imp_RegCloseKey
0x18002863d  mov     eax, ebx
0x18002863f  mov     rcx, [rbp+220h+var_20]
0x180028646  xor     rcx, rsp; StackCookie
0x180028649  call    __security_check_cookie
0x18002864e  lea     r11, [rsp+320h+var_10]
0x180028656  mov     rbx, [r11+28h]
0x18002865a  mov     rsi, [r11+30h]
0x18002865e  mov     rsp, r11
0x180028661  pop     r14
0x180028663  pop     rdi
0x180028664  pop     rbp
0x180028665  retn
```
