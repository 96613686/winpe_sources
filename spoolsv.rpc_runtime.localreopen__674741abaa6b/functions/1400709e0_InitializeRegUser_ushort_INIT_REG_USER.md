# InitializeRegUser(ushort *,INIT_REG_USER *)

- ea: `0x1400709e0`
- end: `0x140070d91`
- name: `?InitializeRegUser@@YAHPEAGPEAUINIT_REG_USER@@@Z`
- size: `945`
- prototype: `__int64 __fastcall(unsigned __int16 *, HKEY *)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400711b8`
- `0x140071470`

## callees

- `0x140002980`
- `0x140004790`
- `0x14000f600`
- `0x1400161d0`
- `0x140016314`
- `0x140018a8c`
- `0x1400257ec`
- `0x14005e898`
- `0x140069514`
- `0x1400702f8`
- `0x1400709e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140070d3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140070d59`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140070d3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140070d59`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140070a8a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140070d0a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140070a8a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140070d0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070d1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070d1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140070aba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140070af0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140070cc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140070aba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140070af0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140070cc3`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x140070c29`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x140070c9b`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x140070c29`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x140070c9b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140070c06`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140070c7c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140070c06`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140070c7c`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140070b12`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140070b43`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140070b12`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140070b43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140070b89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140070b89`

## pseudocode

```c
__int64 __fastcall InitializeRegUser(unsigned __int16 *a1, HKEY *a2)
{
  _OWORD *v2; // r15
  unsigned int v5; // r13d
  void *v6; // rdi
  HANDLE v7; // rsi
  const unsigned __int16 *v8; // rdx
  ProcessUtils *v9; // rcx
  __int16 ImpersonationTokenForUserViaBroker; // ax
  HANDLE v11; // r12
  int v12; // r14d
  void *v13; // rax
  unsigned int v14; // eax
  const unsigned __int16 *v15; // rdx
  ProcessUtils *v16; // rcx
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-11h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-9h] BYREF
  _OWORD v21[2]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v22; // [rsp+88h] [rbp+1Fh]
  DWORD cbSecurityDescriptor; // [rsp+D0h] [rbp+67h] BYREF
  DWORD dwDisposition; // [rsp+E0h] [rbp+77h] BYREF
  int v25; // [rsp+E8h] [rbp+7Fh]

  v2 = 0;
  hKey = 0;
  cbSecurityDescriptor = 0;
  dwDisposition = 0;
  v22 = 0;
  lpMem = 0;
  v5 = 0;
  Token = 0;
  v6 = 0;
  v25 = 0;
  v7 = 0;
  memset(v21, 0, sizeof(v21));
  if ( a1 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl)
      && (unsigned int)IsWindowsProtectedPrintEnabled()
      && ProcessUtils::IsCurrentProcess(v9, v8) )
    {
      ImpersonationTokenForUserViaBroker = GetImpersonationTokenForUserViaBroker(1, a1, 0, &Token);
      v7 = Token;
      if ( ImpersonationTokenForUserViaBroker || !SetThreadToken(0, Token) )
        goto LABEL_15;
      v25 = 1;
    }
    if ( !RegOpenKeyExW(HKEY_USERS, a1, 0, 0x2001Fu, a2) )
      goto LABEL_9;
LABEL_15:
    *a2 = 0;
    goto LABEL_34;
  }
LABEL_9:
  v11 = 0;
  v12 = 0;
  if ( RegOpenKeyExW(*a2, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &hKey) )
    goto LABEL_20;
  if ( RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor) == 122 )
  {
    v13 = (void *)DllAllocSplMem(cbSecurityDescriptor);
    v6 = v13;
    if ( v13 )
    {
      if ( !RegGetKeySecurity(hKey, 4u, v13, &cbSecurityDescriptor) )
      {
        v14 = DuplicateDaclWithLPACCapability(v6, v21, (struct _ACL **)&lpMem);
        if ( !v14 )
        {
          v2 = v21;
LABEL_18:
          v12 = 1;
          goto LABEL_19;
        }
        if ( v14 == 183 )
        {
          v2 = v6;
          goto LABEL_18;
        }
      }
    }
  }
LABEL_19:
  RegCloseKey(hKey);
LABEL_20:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl)
    && (!(unsigned int)IsWindowsProtectedPrintEnabled() || !ProcessUtils::IsCurrentProcess(v16, v15)) )
  {
    v11 = RevertToPrinterSelf();
  }
  DeleteSymbolicLink(*a2, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Devices");
  if ( !RegCreateKeyExW(
          *a2,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Devices",
          0,
          (LPWSTR)&szNULL,
          0,
          0x7001Fu,
          0,
          a2 + 2,
          &dwDisposition) )
  {
    if ( v12 )
      RegSetKeySecurity(a2[2], 4u, v2);
    DeleteSymbolicLink(*a2, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PrinterPorts");
    if ( !RegCreateKeyExW(
            *a2,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PrinterPorts",
            0,
            (LPWSTR)&szNULL,
            0,
            0x7001Fu,
            0,
            a2 + 3,
            &dwDisposition) )
    {
      if ( v12 )
        RegSetKeySecurity(a2[3], 4u, v2);
      if ( !RegOpenKeyExW(*a2, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows", 0, 0x2001Fu, a2 + 1) )
      {
        a2[4] = 0;
        v5 = 1;
      }
    }
  }
  if ( v11 )
    ImpersonatePrinterClient(v11);
LABEL_34:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    if ( v25 )
      SetThreadToken(0, 0);
    if ( v7 )
      CloseHandle(v7);
  }
  if ( v6 )
    HeapFree(g_hSpoolssHeap, 0, v6);
  if ( lpMem )
    HeapFree(g_hSpoolssHeap, 0, lpMem);
  if ( !v5 )
    FreeRegUser((struct INIT_REG_USER *)a2);
  return v5;
}

```

## disassembly

```asm
0x1400709e0  mov     [rsp-8+arg_8], rbx
0x1400709e5  push    rbp
0x1400709e6  push    rsi
0x1400709e7  push    rdi
0x1400709e8  push    r12
0x1400709ea  push    r13
0x1400709ec  push    r14
0x1400709ee  push    r15
0x1400709f0  lea     rbp, [rsp-27h]
0x1400709f5  sub     rsp, 90h
0x1400709fc  xor     r15d, r15d
0x1400709ff  xor     eax, eax
0x140070a01  mov     [rbp+57h+hKey], r15
0x140070a05  xorps   xmm0, xmm0
0x140070a08  mov     [rbp+57h+cbSecurityDescriptor], r15d
0x140070a0c  mov     rbx, rdx
0x140070a0f  mov     [rbp+57h+dwDisposition], r15d
0x140070a13  mov     r14, rcx
0x140070a16  mov     [rbp+57h+var_38], rax
0x140070a1a  lea     r12d, [r15+1]
0x140070a1e  mov     [rbp+57h+lpMem], r15
0x140070a22  mov     r13d, r15d
0x140070a25  mov     [rbp+57h+Token], r15
0x140070a29  mov     edi, r15d
0x140070a2c  mov     [rbp+57h+arg_18], r15d
0x140070a30  mov     esi, r15d
0x140070a33  movups  [rbp+57h+var_58], xmm0
0x140070a37  movups  [rbp+57h+var_48], xmm0
0x140070a3b  test    rcx, rcx
0x140070a3e  jz      loc_140070ACE
0x140070a44  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140070a4b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140070a50  test    al, al
0x140070a52  jz      short loc_140070AA2
0x140070a54  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140070a59  test    eax, eax
0x140070a5b  jz      short loc_140070AA2
0x140070a5d  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x140070a62  test    al, al
0x140070a64  jz      short loc_140070AA2
0x140070a66  lea     r9, [rbp+57h+Token]; void **
0x140070a6a  xor     r8d, r8d; unsigned int
0x140070a6d  mov     rdx, r14; unsigned __int16 *
0x140070a70  mov     ecx, r12d; unsigned int
0x140070a73  call    ?GetImpersonationTokenForUserViaBroker@@YAJKPEBGKPEAPEAX@Z; GetImpersonationTokenForUserViaBroker(ulong,ushort const *,ulong,void * *)
0x140070a78  mov     rsi, [rbp+57h+Token]
0x140070a7c  test    ax, ax
0x140070a7f  jnz     loc_140070B6D
0x140070a85  mov     rdx, rsi; Token
0x140070a88  xor     ecx, ecx; Thread
0x140070a8a  call    cs:__imp_SetThreadToken
0x140070a91  nop     dword ptr [rax+rax+00h]
0x140070a96  test    eax, eax
0x140070a98  jz      loc_140070B6D
0x140070a9e  mov     [rbp+57h+arg_18], r12d
0x140070aa2  mov     r9d, 2001Fh; samDesired
0x140070aa8  mov     [rsp+0C0h+phkResult], rbx; phkResult
0x140070aad  xor     r8d, r8d; ulOptions
0x140070ab0  mov     rdx, r14; lpSubKey
0x140070ab3  mov     rcx, 0FFFFFFFF80000003h; hKey
0x140070aba  call    cs:__imp_RegOpenKeyExW
0x140070ac1  nop     dword ptr [rax+rax+00h]
0x140070ac6  test    eax, eax
0x140070ac8  jnz     loc_140070B6D
0x140070ace  mov     rcx, [rbx]; hKey
0x140070ad1  lea     rax, [rbp+57h+hKey]
0x140070ad5  mov     r9d, 20019h; samDesired
0x140070adb  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140070ae0  xor     r8d, r8d; ulOptions
0x140070ae3  lea     rdx, szCurrentVersionPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x140070aea  mov     r12, r15
0x140070aed  mov     r14d, r15d
0x140070af0  call    cs:__imp_RegOpenKeyExW
0x140070af7  nop     dword ptr [rax+rax+00h]
0x140070afc  test    eax, eax
0x140070afe  jnz     loc_140070B95
0x140070b04  mov     rcx, [rbp+57h+hKey]; hKey
0x140070b08  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x140070b0c  xor     r8d, r8d; pSecurityDescriptor
0x140070b0f  lea     edx, [rax+4]; SecurityInformation
0x140070b12  call    cs:__imp_RegGetKeySecurity
0x140070b19  nop     dword ptr [rax+rax+00h]
0x140070b1e  cmp     eax, 7Ah ; 'z'
0x140070b21  jnz     short loc_140070B85
0x140070b23  mov     ecx, [rbp+57h+cbSecurityDescriptor]; dwBytes
0x140070b26  call    DllAllocSplMem
0x140070b2b  mov     rdi, rax
0x140070b2e  test    rax, rax
0x140070b31  jz      short loc_140070B85
0x140070b33  mov     rcx, [rbp+57h+hKey]; hKey
0x140070b37  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x140070b3b  mov     r8, rax; pSecurityDescriptor
0x140070b3e  mov     edx, 4; SecurityInformation
0x140070b43  call    cs:__imp_RegGetKeySecurity
0x140070b4a  nop     dword ptr [rax+rax+00h]
0x140070b4f  test    eax, eax
0x140070b51  jnz     short loc_140070B85
0x140070b53  lea     r8, [rbp+57h+lpMem]; struct _ACL **
0x140070b57  mov     rcx, rdi; void *
0x140070b5a  lea     rdx, [rbp+57h+var_58]; void *
0x140070b5e  call    ?DuplicateDaclWithLPACCapability@@YAKPEAX0PEAPEAU_ACL@@@Z; DuplicateDaclWithLPACCapability(void *,void *,_ACL * *)
0x140070b63  test    eax, eax
0x140070b65  jnz     short loc_140070B75
0x140070b67  lea     r15, [rbp+57h+var_58]
0x140070b6b  jmp     short loc_140070B7F
0x140070b6d  mov     [rbx], r15
0x140070b70  jmp     loc_140070CF0
0x140070b75  cmp     eax, 0B7h
0x140070b7a  jnz     short loc_140070B85
0x140070b7c  mov     r15, rdi
0x140070b7f  mov     r14d, 1
0x140070b85  mov     rcx, [rbp+57h+hKey]; hKey
0x140070b89  call    cs:__imp_RegCloseKey
0x140070b90  nop     dword ptr [rax+rax+00h]
0x140070b95  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140070b9c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140070ba1  test    al, al
0x140070ba3  jz      short loc_140070BBF
0x140070ba5  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140070baa  test    eax, eax
0x140070bac  jz      short loc_140070BB7
0x140070bae  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x140070bb3  test    al, al
0x140070bb5  jnz     short loc_140070BBF
0x140070bb7  call    RevertToPrinterSelf
0x140070bbc  mov     r12, rax
0x140070bbf  mov     rcx, [rbx]; HKEY
0x140070bc2  lea     rdx, szRegDevicesPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x140070bc9  call    ?DeleteSymbolicLink@@YAHPEAUHKEY__@@PEBG@Z; DeleteSymbolicLink(HKEY__ *,ushort const *)
0x140070bce  lea     rcx, [rbp+57h+dwDisposition]
0x140070bd2  xor     r8d, r8d; Reserved
0x140070bd5  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x140070bda  lea     rax, [rbx+10h]
0x140070bde  mov     rcx, [rbx]; hKey
0x140070be1  lea     r9, szNULL; lpClass
0x140070be8  mov     [rsp+0C0h+var_88], rax; phkResult
0x140070bed  lea     rdx, szRegDevicesPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x140070bf4  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140070bf9  mov     [rsp+0C0h+samDesired], 7001Fh; samDesired
0x140070c01  mov     dword ptr [rsp+0C0h+phkResult], r13d; dwOptions
0x140070c06  call    cs:__imp_RegCreateKeyExW
0x140070c0d  nop     dword ptr [rax+rax+00h]
0x140070c12  test    eax, eax
0x140070c14  jnz     loc_140070CE0
0x140070c1a  test    r14d, r14d
0x140070c1d  jz      short loc_140070C35
0x140070c1f  mov     rcx, [rbx+10h]; hKey
0x140070c23  lea     edx, [rax+4]; SecurityInformation
0x140070c26  mov     r8, r15; pSecurityDescriptor
0x140070c29  call    cs:__imp_RegSetKeySecurity
0x140070c30  nop     dword ptr [rax+rax+00h]
0x140070c35  mov     rcx, [rbx]; HKEY
0x140070c38  lea     rdx, szRegPrinterPortsPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x140070c3f  call    ?DeleteSymbolicLink@@YAHPEAUHKEY__@@PEBG@Z; DeleteSymbolicLink(HKEY__ *,ushort const *)
0x140070c44  lea     rcx, [rbp+57h+dwDisposition]
0x140070c48  xor     r8d, r8d; Reserved
0x140070c4b  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x140070c50  lea     rax, [rbx+18h]
0x140070c54  mov     rcx, [rbx]; hKey
0x140070c57  lea     r9, szNULL; lpClass
0x140070c5e  mov     [rsp+0C0h+var_88], rax; phkResult
0x140070c63  lea     rdx, szRegPrinterPortsPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x140070c6a  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140070c6f  mov     [rsp+0C0h+samDesired], 7001Fh; samDesired
0x140070c77  mov     dword ptr [rsp+0C0h+phkResult], r13d; dwOptions
0x140070c7c  call    cs:__imp_RegCreateKeyExW
0x140070c83  nop     dword ptr [rax+rax+00h]
0x140070c88  test    eax, eax
0x140070c8a  jnz     short loc_140070CE0
0x140070c8c  test    r14d, r14d
0x140070c8f  jz      short loc_140070CA7
0x140070c91  mov     rcx, [rbx+18h]; hKey
0x140070c95  lea     edx, [rax+4]; SecurityInformation
0x140070c98  mov     r8, r15; pSecurityDescriptor
0x140070c9b  call    cs:__imp_RegSetKeySecurity
0x140070ca2  nop     dword ptr [rax+rax+00h]
0x140070ca7  mov     rcx, [rbx]; hKey
0x140070caa  lea     rax, [rbx+8]
0x140070cae  mov     r9d, 2001Fh; samDesired
0x140070cb4  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140070cb9  xor     r8d, r8d; ulOptions
0x140070cbc  lea     rdx, szRegWindowsPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x140070cc3  call    cs:__imp_RegOpenKeyExW
0x140070cca  nop     dword ptr [rax+rax+00h]
0x140070ccf  xor     r15d, r15d
0x140070cd2  test    eax, eax
0x140070cd4  jnz     short loc_140070CE3
0x140070cd6  mov     [rbx+20h], r15
0x140070cda  lea     r13d, [r15+1]
0x140070cde  jmp     short loc_140070CE3
0x140070ce0  xor     r15d, r15d
0x140070ce3  test    r12, r12
0x140070ce6  jz      short loc_140070CF0
0x140070ce8  mov     rcx, r12; hToken
0x140070ceb  call    ImpersonatePrinterClient
0x140070cf0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140070cf7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140070cfc  test    al, al
0x140070cfe  jz      short loc_140070D2A
0x140070d00  cmp     [rbp+57h+arg_18], r15d
0x140070d04  jz      short loc_140070D16
0x140070d06  xor     edx, edx; Token
0x140070d08  xor     ecx, ecx; Thread
0x140070d0a  call    cs:__imp_SetThreadToken
0x140070d11  nop     dword ptr [rax+rax+00h]
0x140070d16  test    rsi, rsi
0x140070d19  jz      short loc_140070D2A
0x140070d1b  mov     rcx, rsi; hObject
0x140070d1e  call    cs:__imp_CloseHandle
0x140070d25  nop     dword ptr [rax+rax+00h]
0x140070d2a  test    rdi, rdi
0x140070d2d  jz      short loc_140070D47
0x140070d2f  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140070d36  mov     r8, rdi; lpMem
0x140070d39  xor     edx, edx; dwFlags
0x140070d3b  call    cs:__imp_HeapFree
0x140070d42  nop     dword ptr [rax+rax+00h]
0x140070d47  mov     r8, [rbp+57h+lpMem]; lpMem
0x140070d4b  test    r8, r8
0x140070d4e  jz      short loc_140070D65
0x140070d50  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140070d57  xor     edx, edx; dwFlags
0x140070d59  call    cs:__imp_HeapFree
0x140070d60  nop     dword ptr [rax+rax+00h]
0x140070d65  test    r13d, r13d
0x140070d68  jnz     short loc_140070D72
0x140070d6a  mov     rcx, rbx; struct INIT_REG_USER *
0x140070d6d  call    ?FreeRegUser@@YAXPEAUINIT_REG_USER@@@Z; FreeRegUser(INIT_REG_USER *)
0x140070d72  mov     rbx, [rsp+0C0h+arg_8]
0x140070d7a  mov     eax, r13d
0x140070d7d  add     rsp, 90h
0x140070d84  pop     r15
0x140070d86  pop     r14
0x140070d88  pop     r13
0x140070d8a  pop     r12
0x140070d8c  pop     rdi
0x140070d8d  pop     rsi
0x140070d8e  pop     rbp
0x140070d8f  retn
```
