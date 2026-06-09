# InitializeRegUser(ushort *,INIT_REG_USER *)

- ea: `0x140069f68`
- end: `0x14006a2b6`
- name: `?InitializeRegUser@@YAHPEAGPEAUINIT_REG_USER@@@Z`
- size: `846`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct INIT_REG_USER *)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14006a688`
- `0x14006a910`

## callees

- `0x1400041c0`
- `0x14000e590`
- `0x1400117d0`
- `0x140014eb0`
- `0x140014fc4`
- `0x140017604`
- `0x140023860`
- `0x1400590f0`
- `0x1400633f8`
- `0x140069910`
- `0x140069f68`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a26d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a285`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a26d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006a285`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006a00e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006a248`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006a00e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x14006a248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006a256`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006a256`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006a038`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006a068`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006a207`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006a038`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006a068`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14006a207`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14006a17f`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14006a1e5`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14006a17f`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14006a1e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14006a162`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14006a1cc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14006a162`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14006a1cc`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14006a080`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14006a0ab`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14006a080`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x14006a0ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006a0eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14006a0eb`

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
      ImpersonationTokenForUserViaBroker = GetImpersonationTokenForUserViaBroker(1u, a1, 0, &Token);
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
0x140069f68  mov     [rsp-8+arg_8], rbx
0x140069f6d  push    rbp
0x140069f6e  push    rsi
0x140069f6f  push    rdi
0x140069f70  push    r12
0x140069f72  push    r13
0x140069f74  push    r14
0x140069f76  push    r15
0x140069f78  lea     rbp, [rsp-27h]
0x140069f7d  sub     rsp, 90h
0x140069f84  xor     r15d, r15d
0x140069f87  xor     eax, eax
0x140069f89  mov     [rbp+57h+hKey], r15
0x140069f8d  xorps   xmm0, xmm0
0x140069f90  mov     [rbp+57h+cbSecurityDescriptor], r15d
0x140069f94  mov     rbx, rdx
0x140069f97  mov     [rbp+57h+dwDisposition], r15d
0x140069f9b  mov     r14, rcx
0x140069f9e  mov     [rbp+57h+var_38], rax
0x140069fa2  lea     r12d, [r15+1]
0x140069fa6  mov     [rbp+57h+lpMem], r15
0x140069faa  mov     r13d, r15d
0x140069fad  mov     [rbp+57h+Token], r15
0x140069fb1  mov     edi, r15d
0x140069fb4  mov     [rbp+57h+arg_18], r15d
0x140069fb8  mov     esi, r15d
0x140069fbb  movups  [rbp+57h+var_58], xmm0
0x140069fbf  movups  [rbp+57h+var_48], xmm0
0x140069fc3  test    rcx, rcx
0x140069fc6  jz      short loc_14006A046
0x140069fc8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x140069fcf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x140069fd4  test    al, al
0x140069fd6  jz      short loc_14006A020
0x140069fd8  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140069fdd  test    eax, eax
0x140069fdf  jz      short loc_14006A020
0x140069fe1  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x140069fe6  test    al, al
0x140069fe8  jz      short loc_14006A020
0x140069fea  lea     r9, [rbp+57h+Token]; void **
0x140069fee  xor     r8d, r8d; unsigned int
0x140069ff1  mov     rdx, r14; unsigned __int16 *
0x140069ff4  mov     ecx, r12d; unsigned int
0x140069ff7  call    ?GetImpersonationTokenForUserViaBroker@@YAJKPEBGKPEAPEAX@Z; GetImpersonationTokenForUserViaBroker(ulong,ushort const *,ulong,void * *)
0x140069ffc  mov     rsi, [rbp+57h+Token]
0x14006a000  test    ax, ax
0x14006a003  jnz     loc_14006A0CF
0x14006a009  mov     rdx, rsi; Token
0x14006a00c  xor     ecx, ecx; Thread
0x14006a00e  call    cs:__imp_SetThreadToken
0x14006a014  test    eax, eax
0x14006a016  jz      loc_14006A0CF
0x14006a01c  mov     [rbp+57h+arg_18], r12d
0x14006a020  mov     r9d, 2001Fh; samDesired
0x14006a026  mov     [rsp+0C0h+phkResult], rbx; phkResult
0x14006a02b  xor     r8d, r8d; ulOptions
0x14006a02e  mov     rdx, r14; lpSubKey
0x14006a031  mov     rcx, 0FFFFFFFF80000003h; hKey
0x14006a038  call    cs:__imp_RegOpenKeyExW
0x14006a03e  test    eax, eax
0x14006a040  jnz     loc_14006A0CF
0x14006a046  mov     rcx, [rbx]; hKey
0x14006a049  lea     rax, [rbp+57h+hKey]
0x14006a04d  mov     r9d, 20019h; samDesired
0x14006a053  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14006a058  xor     r8d, r8d; ulOptions
0x14006a05b  lea     rdx, szCurrentVersionPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x14006a062  mov     r12, r15
0x14006a065  mov     r14d, r15d
0x14006a068  call    cs:__imp_RegOpenKeyExW
0x14006a06e  test    eax, eax
0x14006a070  jnz     short loc_14006A0F1
0x14006a072  mov     rcx, [rbp+57h+hKey]; hKey
0x14006a076  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x14006a07a  xor     r8d, r8d; pSecurityDescriptor
0x14006a07d  lea     edx, [rax+4]; SecurityInformation
0x14006a080  call    cs:__imp_RegGetKeySecurity
0x14006a086  cmp     eax, 7Ah ; 'z'
0x14006a089  jnz     short loc_14006A0E7
0x14006a08b  mov     ecx, [rbp+57h+cbSecurityDescriptor]; dwBytes
0x14006a08e  call    DllAllocSplMem
0x14006a093  mov     rdi, rax
0x14006a096  test    rax, rax
0x14006a099  jz      short loc_14006A0E7
0x14006a09b  mov     rcx, [rbp+57h+hKey]; hKey
0x14006a09f  lea     r9, [rbp+57h+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x14006a0a3  mov     r8, rax; pSecurityDescriptor
0x14006a0a6  mov     edx, 4; SecurityInformation
0x14006a0ab  call    cs:__imp_RegGetKeySecurity
0x14006a0b1  test    eax, eax
0x14006a0b3  jnz     short loc_14006A0E7
0x14006a0b5  lea     r8, [rbp+57h+lpMem]; struct _ACL **
0x14006a0b9  mov     rcx, rdi; void *
0x14006a0bc  lea     rdx, [rbp+57h+var_58]; void *
0x14006a0c0  call    ?DuplicateDaclWithLPACCapability@@YAKPEAX0PEAPEAU_ACL@@@Z; DuplicateDaclWithLPACCapability(void *,void *,_ACL * *)
0x14006a0c5  test    eax, eax
0x14006a0c7  jnz     short loc_14006A0D7
0x14006a0c9  lea     r15, [rbp+57h+var_58]
0x14006a0cd  jmp     short loc_14006A0E1
0x14006a0cf  mov     [rbx], r15
0x14006a0d2  jmp     loc_14006A22E
0x14006a0d7  cmp     eax, 0B7h
0x14006a0dc  jnz     short loc_14006A0E7
0x14006a0de  mov     r15, rdi
0x14006a0e1  mov     r14d, 1
0x14006a0e7  mov     rcx, [rbp+57h+hKey]; hKey
0x14006a0eb  call    cs:__imp_RegCloseKey
0x14006a0f1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14006a0f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14006a0fd  test    al, al
0x14006a0ff  jz      short loc_14006A11B
0x14006a101  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x14006a106  test    eax, eax
0x14006a108  jz      short loc_14006A113
0x14006a10a  call    ?IsCurrentProcess@ProcessUtils@@YA_NPEBG@Z; ProcessUtils::IsCurrentProcess(ushort const *)
0x14006a10f  test    al, al
0x14006a111  jnz     short loc_14006A11B
0x14006a113  call    RevertToPrinterSelf
0x14006a118  mov     r12, rax
0x14006a11b  mov     rcx, [rbx]; HKEY
0x14006a11e  lea     rdx, szRegDevicesPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x14006a125  call    ?DeleteSymbolicLink@@YAHPEAUHKEY__@@PEBG@Z; DeleteSymbolicLink(HKEY__ *,ushort const *)
0x14006a12a  lea     rcx, [rbp+57h+dwDisposition]
0x14006a12e  xor     r8d, r8d; Reserved
0x14006a131  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x14006a136  lea     rax, [rbx+10h]
0x14006a13a  mov     rcx, [rbx]; hKey
0x14006a13d  lea     r9, szNULL; lpClass
0x14006a144  mov     [rsp+0C0h+var_88], rax; phkResult
0x14006a149  lea     rdx, szRegDevicesPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x14006a150  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x14006a155  mov     [rsp+0C0h+samDesired], 7001Fh; samDesired
0x14006a15d  mov     dword ptr [rsp+0C0h+phkResult], r13d; dwOptions
0x14006a162  call    cs:__imp_RegCreateKeyExW
0x14006a168  test    eax, eax
0x14006a16a  jnz     loc_14006A21E
0x14006a170  test    r14d, r14d
0x14006a173  jz      short loc_14006A185
0x14006a175  mov     rcx, [rbx+10h]; hKey
0x14006a179  lea     edx, [rax+4]; SecurityInformation
0x14006a17c  mov     r8, r15; pSecurityDescriptor
0x14006a17f  call    cs:__imp_RegSetKeySecurity
0x14006a185  mov     rcx, [rbx]; HKEY
0x14006a188  lea     rdx, szRegPrinterPortsPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x14006a18f  call    ?DeleteSymbolicLink@@YAHPEAUHKEY__@@PEBG@Z; DeleteSymbolicLink(HKEY__ *,ushort const *)
0x14006a194  lea     rcx, [rbp+57h+dwDisposition]
0x14006a198  xor     r8d, r8d; Reserved
0x14006a19b  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x14006a1a0  lea     rax, [rbx+18h]
0x14006a1a4  mov     rcx, [rbx]; hKey
0x14006a1a7  lea     r9, szNULL; lpClass
0x14006a1ae  mov     [rsp+0C0h+var_88], rax; phkResult
0x14006a1b3  lea     rdx, szRegPrinterPortsPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x14006a1ba  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x14006a1bf  mov     [rsp+0C0h+samDesired], 7001Fh; samDesired
0x14006a1c7  mov     dword ptr [rsp+0C0h+phkResult], r13d; dwOptions
0x14006a1cc  call    cs:__imp_RegCreateKeyExW
0x14006a1d2  test    eax, eax
0x14006a1d4  jnz     short loc_14006A21E
0x14006a1d6  test    r14d, r14d
0x14006a1d9  jz      short loc_14006A1EB
0x14006a1db  mov     rcx, [rbx+18h]; hKey
0x14006a1df  lea     edx, [rax+4]; SecurityInformation
0x14006a1e2  mov     r8, r15; pSecurityDescriptor
0x14006a1e5  call    cs:__imp_RegSetKeySecurity
0x14006a1eb  mov     rcx, [rbx]; hKey
0x14006a1ee  lea     rax, [rbx+8]
0x14006a1f2  mov     r9d, 2001Fh; samDesired
0x14006a1f8  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14006a1fd  xor     r8d, r8d; ulOptions
0x14006a200  lea     rdx, szRegWindowsPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x14006a207  call    cs:__imp_RegOpenKeyExW
0x14006a20d  xor     r15d, r15d
0x14006a210  test    eax, eax
0x14006a212  jnz     short loc_14006A221
0x14006a214  mov     [rbx+20h], r15
0x14006a218  lea     r13d, [r15+1]
0x14006a21c  jmp     short loc_14006A221
0x14006a21e  xor     r15d, r15d
0x14006a221  test    r12, r12
0x14006a224  jz      short loc_14006A22E
0x14006a226  mov     rcx, r12; hToken
0x14006a229  call    ImpersonatePrinterClient
0x14006a22e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x14006a235  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x14006a23a  test    al, al
0x14006a23c  jz      short loc_14006A25C
0x14006a23e  cmp     [rbp+57h+arg_18], r15d
0x14006a242  jz      short loc_14006A24E
0x14006a244  xor     edx, edx; Token
0x14006a246  xor     ecx, ecx; Thread
0x14006a248  call    cs:__imp_SetThreadToken
0x14006a24e  test    rsi, rsi
0x14006a251  jz      short loc_14006A25C
0x14006a253  mov     rcx, rsi; hObject
0x14006a256  call    cs:__imp_CloseHandle
0x14006a25c  test    rdi, rdi
0x14006a25f  jz      short loc_14006A273
0x14006a261  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006a268  mov     r8, rdi; lpMem
0x14006a26b  xor     edx, edx; dwFlags
0x14006a26d  call    cs:__imp_HeapFree
0x14006a273  mov     r8, [rbp+57h+lpMem]; lpMem
0x14006a277  test    r8, r8
0x14006a27a  jz      short loc_14006A28B
0x14006a27c  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006a283  xor     edx, edx; dwFlags
0x14006a285  call    cs:__imp_HeapFree
0x14006a28b  test    r13d, r13d
0x14006a28e  jnz     short loc_14006A298
0x14006a290  mov     rcx, rbx; struct INIT_REG_USER *
0x14006a293  call    ?FreeRegUser@@YAXPEAUINIT_REG_USER@@@Z; FreeRegUser(INIT_REG_USER *)
0x14006a298  mov     rbx, [rsp+0C0h+arg_8]
0x14006a2a0  mov     eax, r13d
0x14006a2a3  add     rsp, 90h
0x14006a2aa  pop     r15
0x14006a2ac  pop     r14
0x14006a2ae  pop     r13
0x14006a2b0  pop     r12
0x14006a2b2  pop     rdi
0x14006a2b3  pop     rsi
0x14006a2b4  pop     rbp
0x14006a2b5  retn
```
