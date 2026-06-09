# ReadPerInstanceRegistryParameters

- ea: `0x1400068a4`
- end: `0x140006f1d`
- name: `ReadPerInstanceRegistryParameters`
- size: `1657`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140005ea0`

## callees

- `0x140001bf0`
- `0x140002090`
- `0x140004bd0`
- `0x140006568`
- `0x1400068a4`
- `0x140008679`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400069d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400069d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006ad1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006e9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006eb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006eca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006ad1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006e9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006eb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006eca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140006e79`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140006e79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006eda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006eea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006eda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006eea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000699c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140006a77`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000699c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140006a77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006955`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006e25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006955`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006e25`
- `ntdll!RtlValidSecurityDescriptor` at `0x140006db9`
- `ntdll!RtlValidSecurityDescriptor` at `0x140006db9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140006c8a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140006c8a`

## string_xrefs

- `0x140006b1f`: `CoInitializeSecurityParam`
- `0x140006b40`: `CoInitializeSecurityAllowLowBox`
- `0x140006b68`: `CoInitializeSecurityAllowInteractiveUsers`
- `0x140006b90`: `CoInitializeSecurityAllowComCapability`
- `0x140006bb8`: `CoInitializeSecurityAllowCrossContainer`
- `0x140006c02`: `ImpersonationLevel`
- `0x140006c5e`: `CoInitializeSecurityAppID`
- `0x140006caa`: `COM_UnmarshalingPolicy`
- `0x140006cc2`: `COM_RoSettings`
- `0x140006d69`: `NoGuiAccess`
- `0x140006da1`: `COMAccessPermissionsSD`

## pseudocode

```c
__int64 __fastcall ReadPerInstanceRegistryParameters(__int64 a1, HKEY a2, __int64 a3)
{
  const WCHAR *v5; // rdx
  WCHAR *v6; // r12
  PSECURITY_DESCRIPTOR v7; // rsi
  unsigned int ValueWithAlloc; // r14d
  wchar_t *v9; // r15
  unsigned int v10; // r13d
  int i; // ebx
  LSTATUS v12; // eax
  _WORD *v13; // rax
  _WORD *v14; // rsi
  wchar_t *v15; // rbx
  __int64 v16; // r8
  __int64 v17; // rax
  DWORD j; // ebx
  __int64 v19; // r8
  wchar_t *v20; // rax
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  int v24; // ecx
  int v25; // eax
  int v26; // ecx
  int v27; // eax
  OLECHAR *v28; // r15
  int v29; // eax
  int v30; // ebx
  int v31; // ecx
  unsigned int v32; // eax
  int v33; // eax
  int v35; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  SIZE_T dwBytes; // [rsp+54h] [rbp-ACh] BYREF
  LPCOLESTR lpsz; // [rsp+60h] [rbp-A0h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-98h]
  LPCWCH lpString2; // [rsp+70h] [rbp-90h]
  HKEY hkey; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  ServiceNames = 0;
  v35 = 0;
  cchName = 0;
  v5 = *(const WCHAR **)(a3 + 24);
  hKey = 0;
  v6 = 0;
  hkey = 0;
  v7 = 0;
  lpsz = 0;
  lpString2 = 0;
  SecurityDescriptor = 0;
  dwBytes = 0;
  ValueWithAlloc = RegQueryValueWithAlloc(a2, v5, (SIZE_T)&dwBytes);
  if ( RegOpenKeyExW(a2, *(LPCWSTR *)(a3 + 24), 0, 0x20019u, &hKey) )
  {
    v28 = (OLECHAR *)lpsz;
    goto LABEL_79;
  }
  v9 = 0;
  v10 = dwBytes;
  for ( i = dwBytes; ; i += 2 * cchName + 2 )
  {
    cchName = 257;
    v12 = RegEnumKeyExW(hKey, (DWORD)v7, Name, &cchName, 0, 0, 0, 0);
    LODWORD(v7) = (_DWORD)v7 + 1;
    if ( v12 )
      break;
  }
  if ( i && (unsigned int)v7 > 1 && (v13 = HeapAlloc(g_hHeap, 0, (unsigned int)(i + 2)), (v9 = v13) != 0) )
  {
    v14 = v13;
    if ( !ValueWithAlloc && v10 >= 2 )
    {
      v15 = ServiceNames;
      if ( ServiceNames )
      {
        while ( *v15 )
        {
          v16 = -1;
          do
            ++v16;
          while ( v15[v16] );
          memcpy_0(v14, v15, 2 * v16 + 2);
          v17 = -1;
          do
            ++v17;
          while ( v15[v17] );
          v14 += v17 + 1;
          v15 += v17 + 1;
        }
      }
    }
    for ( j = 0; ; ++j )
    {
      cchName = 257;
      if ( RegEnumKeyExW(hKey, j, Name, &cchName, 0, 0, 0, 0) )
        break;
      v19 = -1;
      do
        ++v19;
      while ( Name[v19] );
      memcpy_0(v14, Name, 2 * v19 + 2);
      v14 += cchName + 1;
    }
    *v14 = 0;
    if ( ServiceNames )
      HeapFree(g_hHeap, 0, ServiceNames);
    v20 = v9;
    ValueWithAlloc = 0;
    ServiceNames = v9;
  }
  else
  {
    v20 = ServiceNames;
  }
  if ( !v20 || (v10 >= 2 || v9) && !*v20 )
  {
    ValueWithAlloc = 13;
    goto LABEL_89;
  }
  if ( !(unsigned int)RegQueryDword(hKey, L"CoInitializeSecurityParam", &v35) )
    *(_DWORD *)(a3 + 40) = v35;
  if ( !(unsigned int)RegQueryDword(hKey, L"CoInitializeSecurityAllowLowBox", &v35) && v35 )
    *(_DWORD *)(a3 + 148) |= 2u;
  if ( !(unsigned int)RegQueryDword(hKey, L"CoInitializeSecurityAllowInteractiveUsers", &v35) && v35 )
    *(_DWORD *)(a3 + 148) |= 0x10u;
  if ( !(unsigned int)RegQueryDword(hKey, L"CoInitializeSecurityAllowComCapability", &v35) && v35 )
    *(_DWORD *)(a3 + 148) |= 0x20u;
  if ( !(unsigned int)RegQueryDword(hKey, L"CoInitializeSecurityAllowCrossContainer", &v35) && v35 )
    *(_DWORD *)(a3 + 148) |= 0x40u;
  if ( *(_DWORD *)(a3 + 40) )
  {
    v21 = RegQueryDword(hKey, L"AuthenticationLevel", &v35);
    v22 = 4;
    if ( !v21 )
      v22 = v35;
    *(_DWORD *)(a3 + 44) = v22;
    v23 = RegQueryDword(hKey, L"ImpersonationLevel", &v35);
    v24 = 2;
    if ( !v23 )
      v24 = v35;
    *(_DWORD *)(a3 + 48) = v24;
    v25 = RegQueryDword(hKey, L"AuthenticationCapabilities", &v35);
    LODWORD(dwBytes) = 0;
    v26 = 12288;
    if ( !v25 )
      v26 = v35;
    *(_DWORD *)(a3 + 52) = v26;
    v27 = RegQueryValueWithAlloc(hKey, L"CoInitializeSecurityAppID", (SIZE_T)&dwBytes);
    v28 = (OLECHAR *)lpsz;
    if ( !v27 && CLSIDFromString(lpsz, (LPCLSID)(a3 + 56)) < 0 )
      *(GUID *)(a3 + 56) = GUID_NULL;
    v29 = RegQueryDword(hKey, L"COM_UnmarshalingPolicy", &v35);
    v30 = 0xFFFF;
    v31 = 0xFFFF;
    if ( !v29 )
      v31 = v35;
    *(_DWORD *)(a3 + 72) = v31;
    if ( !(unsigned int)RegQueryDword(hKey, L"COM_RoSettings", &v35) )
      v30 = v35;
    *(_DWORD *)(a3 + 76) = v30;
  }
  else
  {
    v28 = (OLECHAR *)lpsz;
  }
  if ( !(unsigned int)RegQueryDword(hKey, L"DefaultRpcStackSize", &v35) )
    *(_DWORD *)(a3 + 80) = v35;
  if ( !(unsigned int)RegQueryDword(hKey, L"RpcExceptionFilterMode", &v35) && !v35 )
    *(_DWORD *)(a3 + 84) = 1;
  if ( !(unsigned int)RegQueryDword(hKey, L"SystemCritical", &v35) )
    *(_DWORD *)(a3 + 88) = v35 != 0;
  if ( !(unsigned int)RegQueryDword(hKey, L"NoGuiAccess", &v35) && v35 )
    *(_DWORD *)(a3 + 148) |= 8u;
  v32 = RegQueryValueWithAlloc(hKey, L"COMAccessPermissionsSD", (SIZE_T)&dwBytes + 4);
  v7 = SecurityDescriptor;
  if ( v32 )
  {
    if ( v32 == 2 )
      goto LABEL_79;
    ValueWithAlloc = v32;
  }
  else
  {
    if ( RtlValidSecurityDescriptor(SecurityDescriptor) )
    {
      *(_QWORD *)(a3 + 152) = v7;
      v7 = 0;
LABEL_79:
      GetMitigationConfiguration(hKey, a3);
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Diagnostics\\PerfTrack\\TraceProfile",
              0,
              0x20019u,
              &hkey) )
      {
        HIDWORD(dwBytes) = 0;
        v33 = RegQueryValueWithAlloc(hkey, L"svchost", (SIZE_T)&dwBytes + 4);
        v6 = (WCHAR *)lpString2;
        if ( !v33 && CompareStringOrdinal(*(LPCWCH *)(a3 + 24), -1, lpString2, -1, 1) == 2 )
          *(_DWORD *)(a3 + 148) |= 4u;
      }
      goto LABEL_83;
    }
    ValueWithAlloc = 13;
  }
LABEL_83:
  if ( v7 )
    HeapFree(g_hHeap, 0, v7);
  if ( v6 )
    HeapFree(g_hHeap, 0, v6);
  if ( v28 )
    HeapFree(g_hHeap, 0, v28);
LABEL_89:
  if ( hKey )
    RegCloseKey(hKey);
  if ( hkey )
    RegCloseKey(hkey);
  return ValueWithAlloc;
}

```

## disassembly

```asm
0x1400068a4  mov     [rsp-8+arg_0], rbx
0x1400068a9  push    rbp
0x1400068aa  push    rsi
0x1400068ab  push    rdi
0x1400068ac  push    r12
0x1400068ae  push    r13
0x1400068b0  push    r14
0x1400068b2  push    r15
0x1400068b4  lea     rbp, [rsp-1A0h]
0x1400068bc  sub     rsp, 2A0h
0x1400068c3  mov     rax, cs:__security_cookie
0x1400068ca  xor     rax, rsp
0x1400068cd  mov     [rbp+1D0h+var_40], rax
0x1400068d4  xor     r13d, r13d
0x1400068d7  lea     rax, [rsp+2D0h+dwBytes]
0x1400068dc  mov     rdi, r8
0x1400068df  mov     cs:ServiceNames, r13
0x1400068e6  mov     rbx, rdx
0x1400068e9  mov     [rsp+2D0h+var_290], r13d
0x1400068ee  lea     r9, ServiceNames
0x1400068f5  mov     [rsp+2D0h+cchName], r13d
0x1400068fa  lea     r8d, [r13+7]
0x1400068fe  mov     dword ptr [rsp+2D0h+dwBytes+4], r13d
0x140006903  mov     rdx, [rdi+18h]; lpValue
0x140006907  mov     rcx, rbx; hkey
0x14000690a  mov     [rsp+2D0h+hKey], r13
0x14000690f  mov     r12d, r13d
0x140006912  mov     [rsp+2D0h+hkey], r13
0x140006917  mov     esi, r13d
0x14000691a  mov     [rsp+2D0h+lpsz], r13
0x14000691f  mov     [rsp+2D0h+lpString2], r13
0x140006924  mov     [rsp+2D0h+SecurityDescriptor], r13
0x140006929  mov     dword ptr [rsp+2D0h+dwBytes], r13d
0x14000692e  mov     [rsp+2D0h+phkResult], rax; dwBytes
0x140006933  call    RegQueryValueWithAlloc
0x140006938  mov     rdx, [rdi+18h]; lpSubKey
0x14000693c  mov     r14d, eax
0x14000693f  lea     rax, [rsp+2D0h+hKey]
0x140006944  mov     r9d, 20019h; samDesired
0x14000694a  xor     r8d, r8d; ulOptions
0x14000694d  mov     [rsp+2D0h+phkResult], rax; phkResult
0x140006952  mov     rcx, rbx; hKey
0x140006955  call    cs:__imp_RegOpenKeyExW
0x14000695b  test    eax, eax
0x14000695d  jnz     loc_140006DF2
0x140006963  mov     r15d, r13d
0x140006966  xor     ecx, ecx
0x140006968  mov     r13d, dword ptr [rsp+2D0h+dwBytes]
0x14000696d  mov     ebx, r13d
0x140006970  mov     [rsp+2D0h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x140006975  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x14000697a  mov     [rsp+2D0h+lpcchClass], rcx; lpcchClass
0x14000697f  lea     r8, [rbp+1D0h+Name]; lpName
0x140006983  mov     [rsp+2D0h+lpClass], rcx; lpClass
0x140006988  mov     edx, esi; dwIndex
0x14000698a  mov     [rsp+2D0h+phkResult], rcx; lpReserved
0x14000698f  mov     rcx, [rsp+2D0h+hKey]; hKey
0x140006994  mov     [rsp+2D0h+cchName], 101h
0x14000699c  call    cs:__imp_RegEnumKeyExW
0x1400069a2  inc     esi
0x1400069a4  xor     ecx, ecx
0x1400069a6  test    eax, eax
0x1400069a8  jnz     short loc_1400069B6
0x1400069aa  mov     eax, [rsp+2D0h+cchName]
0x1400069ae  lea     ebx, [rbx+rax*2]
0x1400069b1  add     ebx, 2
0x1400069b4  jmp     short loc_140006970
0x1400069b6  test    ebx, ebx
0x1400069b8  jz      loc_140006AE8
0x1400069be  cmp     esi, 1
0x1400069c1  jbe     loc_140006AE8
0x1400069c7  mov     rcx, cs:g_hHeap; hHeap
0x1400069ce  lea     r8d, [rbx+2]; dwBytes
0x1400069d2  xor     edx, edx; dwFlags
0x1400069d4  call    cs:__imp_HeapAlloc
0x1400069da  xor     ecx, ecx
0x1400069dc  mov     r15, rax
0x1400069df  test    rax, rax
0x1400069e2  jz      loc_140006AE8
0x1400069e8  mov     rsi, rax
0x1400069eb  test    r14d, r14d
0x1400069ee  jnz     short loc_140006A49
0x1400069f0  cmp     r13d, 2
0x1400069f4  jb      short loc_140006A49
0x1400069f6  mov     rbx, cs:ServiceNames
0x1400069fd  test    rbx, rbx
0x140006a00  jz      short loc_140006A49
0x140006a02  jmp     short loc_140006A44
0x140006a04  or      r8, 0FFFFFFFFFFFFFFFFh
0x140006a08  inc     r8
0x140006a0b  cmp     [rbx+r8*2], cx
0x140006a10  jnz     short loc_140006A08
0x140006a12  lea     r8, ds:2[r8*2]; Size
0x140006a1a  mov     rdx, rbx; Src
0x140006a1d  mov     rcx, rsi; void *
0x140006a20  call    memcpy_0
0x140006a25  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006a29  xor     ecx, ecx
0x140006a2b  inc     rax
0x140006a2e  cmp     [rbx+rax*2], cx
0x140006a32  jnz     short loc_140006A2B
0x140006a34  lea     rsi, [rsi+rax*2]
0x140006a38  add     rsi, 2
0x140006a3c  lea     rbx, [rbx+rax*2]
0x140006a40  add     rbx, 2
0x140006a44  cmp     [rbx], cx
0x140006a47  jnz     short loc_140006A04
0x140006a49  mov     ebx, ecx
0x140006a4b  mov     [rsp+2D0h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x140006a50  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x140006a55  mov     [rsp+2D0h+lpcchClass], rcx; lpcchClass
0x140006a5a  lea     r8, [rbp+1D0h+Name]; lpName
0x140006a5e  mov     [rsp+2D0h+lpClass], rcx; lpClass
0x140006a63  mov     edx, ebx; dwIndex
0x140006a65  mov     [rsp+2D0h+phkResult], rcx; lpReserved
0x140006a6a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x140006a6f  mov     [rsp+2D0h+cchName], 101h
0x140006a77  call    cs:__imp_RegEnumKeyExW
0x140006a7d  xor     ecx, ecx
0x140006a7f  test    eax, eax
0x140006a81  jnz     short loc_140006AB9
0x140006a83  lea     rax, [rbp+1D0h+Name]
0x140006a87  or      r8, 0FFFFFFFFFFFFFFFFh
0x140006a8b  inc     r8
0x140006a8e  cmp     [rax+r8*2], cx
0x140006a93  jnz     short loc_140006A8B
0x140006a95  lea     r8, ds:2[r8*2]; Size
0x140006a9d  mov     rcx, rsi; void *
0x140006aa0  lea     rdx, [rbp+1D0h+Name]; Src
0x140006aa4  call    memcpy_0
0x140006aa9  mov     eax, [rsp+2D0h+cchName]
0x140006aad  inc     ebx
0x140006aaf  inc     eax
0x140006ab1  xor     ecx, ecx
0x140006ab3  lea     rsi, [rsi+rax*2]
0x140006ab7  jmp     short loc_140006A4B
0x140006ab9  mov     [rsi], cx
0x140006abc  mov     r8, cs:ServiceNames; lpMem
0x140006ac3  test    r8, r8
0x140006ac6  jz      short loc_140006AD9
0x140006ac8  mov     rcx, cs:g_hHeap; hHeap
0x140006acf  xor     edx, edx; dwFlags
0x140006ad1  call    cs:__imp_HeapFree
0x140006ad7  xor     ecx, ecx
0x140006ad9  mov     rax, r15
0x140006adc  mov     r14d, ecx
0x140006adf  mov     cs:ServiceNames, rax
0x140006ae6  jmp     short loc_140006AEF
0x140006ae8  mov     rax, cs:ServiceNames
0x140006aef  test    rax, rax
0x140006af2  jz      loc_140006DE7
0x140006af8  cmp     r13d, 2
0x140006afc  jnb     short loc_140006B08
0x140006afe  xor     r13d, r13d
0x140006b01  test    r15, r15
0x140006b04  jz      short loc_140006B15
0x140006b06  jmp     short loc_140006B0B
0x140006b08  xor     r13d, r13d
0x140006b0b  cmp     [rax], r13w
0x140006b0f  jz      loc_140006DE7
0x140006b15  mov     rcx, [rsp+2D0h+hKey]
0x140006b1a  lea     r8, [rsp+2D0h+var_290]
0x140006b1f  lea     rdx, aCoinitializese_3; "CoInitializeSecurityParam"
0x140006b26  call    RegQueryDword
0x140006b2b  test    eax, eax
0x140006b2d  jnz     short loc_140006B36
0x140006b2f  mov     eax, [rsp+2D0h+var_290]
0x140006b33  mov     [rdi+28h], eax
0x140006b36  mov     rcx, [rsp+2D0h+hKey]
0x140006b3b  lea     r8, [rsp+2D0h+var_290]
0x140006b40  lea     rdx, aCoinitializese_0; "CoInitializeSecurityAllowLowBox"
0x140006b47  call    RegQueryDword
0x140006b4c  test    eax, eax
0x140006b4e  jnz     short loc_140006B5E
0x140006b50  cmp     [rsp+2D0h+var_290], r13d
0x140006b55  jz      short loc_140006B5E
0x140006b57  or      dword ptr [rdi+94h], 2
0x140006b5e  mov     rcx, [rsp+2D0h+hKey]
0x140006b63  lea     r8, [rsp+2D0h+var_290]
0x140006b68  lea     rdx, aCoinitializese_2; "CoInitializeSecurityAllowInteractiveUse"...
0x140006b6f  call    RegQueryDword
0x140006b74  test    eax, eax
0x140006b76  jnz     short loc_140006B86
0x140006b78  cmp     [rsp+2D0h+var_290], r13d
0x140006b7d  jz      short loc_140006B86
0x140006b7f  or      dword ptr [rdi+94h], 10h
0x140006b86  mov     rcx, [rsp+2D0h+hKey]
0x140006b8b  lea     r8, [rsp+2D0h+var_290]
0x140006b90  lea     rdx, aCoinitializese_1; "CoInitializeSecurityAllowComCapability"
0x140006b97  call    RegQueryDword
0x140006b9c  test    eax, eax
0x140006b9e  jnz     short loc_140006BAE
0x140006ba0  cmp     [rsp+2D0h+var_290], r13d
0x140006ba5  jz      short loc_140006BAE
0x140006ba7  or      dword ptr [rdi+94h], 20h
0x140006bae  mov     rcx, [rsp+2D0h+hKey]
0x140006bb3  lea     r8, [rsp+2D0h+var_290]
0x140006bb8  lea     rdx, aCoinitializese_4; "CoInitializeSecurityAllowCrossContainer"
0x140006bbf  call    RegQueryDword
0x140006bc4  test    eax, eax
0x140006bc6  jnz     short loc_140006BD6
0x140006bc8  cmp     [rsp+2D0h+var_290], r13d
0x140006bcd  jz      short loc_140006BD6
0x140006bcf  or      dword ptr [rdi+94h], 40h
0x140006bd6  cmp     [rdi+28h], r13d
0x140006bda  jz      loc_140006CE9
0x140006be0  mov     rcx, [rsp+2D0h+hKey]
0x140006be5  lea     r8, [rsp+2D0h+var_290]
0x140006bea  lea     rdx, aAuthentication; "AuthenticationLevel"
0x140006bf1  call    RegQueryDword
0x140006bf6  test    eax, eax
0x140006bf8  lea     r8, [rsp+2D0h+var_290]
0x140006bfd  mov     ecx, 4
0x140006c02  lea     rdx, aImpersonationl; "ImpersonationLevel"
0x140006c09  cmovz   ecx, [rsp+2D0h+var_290]
0x140006c0e  mov     [rdi+2Ch], ecx
0x140006c11  mov     rcx, [rsp+2D0h+hKey]
0x140006c16  call    RegQueryDword
0x140006c1b  test    eax, eax
0x140006c1d  lea     r8, [rsp+2D0h+var_290]
0x140006c22  mov     ecx, 2
0x140006c27  lea     rdx, aAuthentication_0; "AuthenticationCapabilities"
0x140006c2e  cmovz   ecx, [rsp+2D0h+var_290]
0x140006c33  mov     [rdi+30h], ecx
0x140006c36  mov     rcx, [rsp+2D0h+hKey]
0x140006c3b  call    RegQueryDword
0x140006c40  test    eax, eax
0x140006c42  mov     dword ptr [rsp+2D0h+dwBytes], r13d
0x140006c47  mov     ecx, 3000h
0x140006c4c  lea     rax, [rsp+2D0h+dwBytes]
0x140006c51  cmovz   ecx, [rsp+2D0h+var_290]
0x140006c56  lea     r9, [rsp+2D0h+lpsz]
0x140006c5b  mov     [rdi+34h], ecx
0x140006c5e  lea     rdx, aCoinitializese_5; "CoInitializeSecurityAppID"
0x140006c65  mov     rcx, [rsp+2D0h+hKey]; hkey
0x140006c6a  mov     r8d, 1
0x140006c70  mov     [rsp+2D0h+phkResult], rax; dwBytes
0x140006c75  call    RegQueryValueWithAlloc
0x140006c7a  mov     r15, [rsp+2D0h+lpsz]
0x140006c7f  test    eax, eax
0x140006c81  jnz     short loc_140006CA0
0x140006c83  lea     rdx, [rdi+38h]; pclsid
0x140006c87  mov     rcx, r15; lpsz
0x140006c8a  call    cs:__imp_CLSIDFromString
0x140006c90  test    eax, eax
0x140006c92  jns     short loc_140006CA0
0x140006c94  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140006c9b  movdqu  xmmword ptr [rdi+38h], xmm0
0x140006ca0  mov     rcx, [rsp+2D0h+hKey]
0x140006ca5  lea     r8, [rsp+2D0h+var_290]
0x140006caa  lea     rdx, aComUnmarshalin; "COM_UnmarshalingPolicy"
0x140006cb1  call    RegQueryDword
0x140006cb6  test    eax, eax
0x140006cb8  lea     r8, [rsp+2D0h+var_290]
0x140006cbd  mov     ebx, 0FFFFh
0x140006cc2  lea     rdx, aComRosettings; "COM_RoSettings"
0x140006cc9  mov     ecx, ebx
0x140006ccb  cmovz   ecx, [rsp+2D0h+var_290]
0x140006cd0  mov     [rdi+48h], ecx
0x140006cd3  mov     rcx, [rsp+2D0h+hKey]
0x140006cd8  call    RegQueryDword
0x140006cdd  test    eax, eax
0x140006cdf  cmovz   ebx, [rsp+2D0h+var_290]
0x140006ce4  mov     [rdi+4Ch], ebx
0x140006ce7  jmp     short loc_140006CEE
0x140006ce9  mov     r15, [rsp+2D0h+lpsz]
0x140006cee  mov     rcx, [rsp+2D0h+hKey]
0x140006cf3  lea     r8, [rsp+2D0h+var_290]
0x140006cf8  lea     rdx, aDefaultrpcstac; "DefaultRpcStackSize"
0x140006cff  call    RegQueryDword
0x140006d04  test    eax, eax
0x140006d06  jnz     short loc_140006D0F
0x140006d08  mov     eax, [rsp+2D0h+var_290]
0x140006d0c  mov     [rdi+50h], eax
0x140006d0f  mov     rcx, [rsp+2D0h+hKey]
0x140006d14  lea     r8, [rsp+2D0h+var_290]
0x140006d19  lea     rdx, aRpcexceptionfi; "RpcExceptionFilterMode"
0x140006d20  call    RegQueryDword
0x140006d25  test    eax, eax
0x140006d27  jnz     short loc_140006D37
0x140006d29  cmp     [rsp+2D0h+var_290], r13d
0x140006d2e  jnz     short loc_140006D37
0x140006d30  mov     dword ptr [rdi+54h], 1
0x140006d37  mov     rcx, [rsp+2D0h+hKey]
0x140006d3c  lea     r8, [rsp+2D0h+var_290]
0x140006d41  lea     rdx, aSystemcritical; "SystemCritical"
0x140006d48  call    RegQueryDword
0x140006d4d  test    eax, eax
0x140006d4f  jnz     short loc_140006D5F
0x140006d51  cmp     [rsp+2D0h+var_290], r13d
0x140006d56  mov     eax, r13d
0x140006d59  setnz   al
0x140006d5c  mov     [rdi+58h], eax
0x140006d5f  mov     rcx, [rsp+2D0h+hKey]
0x140006d64  lea     r8, [rsp+2D0h+var_290]
0x140006d69  lea     rdx, aNoguiaccess; "NoGuiAccess"
0x140006d70  call    RegQueryDword
0x140006d75  test    eax, eax
0x140006d77  jnz     short loc_140006D87
0x140006d79  cmp     [rsp+2D0h+var_290], r13d
  ... truncated ...
```
