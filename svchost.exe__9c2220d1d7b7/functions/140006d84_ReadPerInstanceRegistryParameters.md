# ReadPerInstanceRegistryParameters

- ea: `0x140006d84`
- end: `0x140007452`
- name: `ReadPerInstanceRegistryParameters`
- size: `1742`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140006320`

## callees

- `0x140001900`
- `0x1400021c0`
- `0x140004f90`
- `0x140006a3c`
- `0x140006d84`
- `0x140008cc9`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006ec0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140006ec0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006fc9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400073b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400073cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400073ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006fc9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400073b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400073cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400073ec`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140007389`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140007389`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007402`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007418`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007402`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007418`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140006e82`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140006f69`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140006e82`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140006f69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006e35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000732f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140006e35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000732f`
- `ntdll!RtlValidSecurityDescriptor` at `0x1400072bd`
- `ntdll!RtlValidSecurityDescriptor` at `0x1400072bd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140007188`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140007188`

## string_xrefs

- `0x14000701d`: `CoInitializeSecurityParam`
- `0x14000703e`: `CoInitializeSecurityAllowLowBox`
- `0x140007066`: `CoInitializeSecurityAllowInteractiveUsers`
- `0x14000708e`: `CoInitializeSecurityAllowComCapability`
- `0x1400070b6`: `CoInitializeSecurityAllowCrossContainer`
- `0x140007100`: `ImpersonationLevel`
- `0x14000715c`: `CoInitializeSecurityAppID`
- `0x1400071ae`: `COM_UnmarshalingPolicy`
- `0x1400071c6`: `COM_RoSettings`
- `0x14000726d`: `NoGuiAccess`
- `0x1400072a5`: `COMAccessPermissionsSD`

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
0x140006d84  mov     [rsp-8+arg_0], rbx
0x140006d89  push    rbp
0x140006d8a  push    rsi
0x140006d8b  push    rdi
0x140006d8c  push    r12
0x140006d8e  push    r13
0x140006d90  push    r14
0x140006d92  push    r15
0x140006d94  lea     rbp, [rsp-1A0h]
0x140006d9c  sub     rsp, 2A0h
0x140006da3  mov     rax, cs:__security_cookie
0x140006daa  xor     rax, rsp
0x140006dad  mov     [rbp+1D0h+var_40], rax
0x140006db4  xor     r13d, r13d
0x140006db7  lea     rax, [rsp+2D0h+dwBytes]
0x140006dbc  mov     rdi, r8
0x140006dbf  mov     cs:ServiceNames, r13
0x140006dc6  mov     rbx, rdx
0x140006dc9  mov     [rsp+2D0h+var_290], r13d
0x140006dce  lea     r9, ServiceNames
0x140006dd5  mov     [rsp+2D0h+cchName], r13d
0x140006dda  lea     r8d, [r13+7]
0x140006dde  mov     dword ptr [rsp+2D0h+dwBytes+4], r13d
0x140006de3  mov     rdx, [rdi+18h]; lpValue
0x140006de7  mov     rcx, rbx; hkey
0x140006dea  mov     [rsp+2D0h+hKey], r13
0x140006def  mov     r12d, r13d
0x140006df2  mov     [rsp+2D0h+hkey], r13
0x140006df7  mov     esi, r13d
0x140006dfa  mov     [rsp+2D0h+lpsz], r13
0x140006dff  mov     [rsp+2D0h+lpString2], r13
0x140006e04  mov     [rsp+2D0h+SecurityDescriptor], r13
0x140006e09  mov     dword ptr [rsp+2D0h+dwBytes], r13d
0x140006e0e  mov     [rsp+2D0h+phkResult], rax; dwBytes
0x140006e13  call    RegQueryValueWithAlloc
0x140006e18  mov     rdx, [rdi+18h]; lpSubKey
0x140006e1c  mov     r14d, eax
0x140006e1f  lea     rax, [rsp+2D0h+hKey]
0x140006e24  mov     r9d, 20019h; samDesired
0x140006e2a  xor     r8d, r8d; ulOptions
0x140006e2d  mov     [rsp+2D0h+phkResult], rax; phkResult
0x140006e32  mov     rcx, rbx; hKey
0x140006e35  call    cs:__imp_RegOpenKeyExW
0x140006e3c  nop     dword ptr [rax+rax+00h]
0x140006e41  test    eax, eax
0x140006e43  jnz     loc_1400072FC
0x140006e49  mov     r15d, r13d
0x140006e4c  xor     ecx, ecx
0x140006e4e  mov     r13d, dword ptr [rsp+2D0h+dwBytes]
0x140006e53  mov     ebx, r13d
0x140006e56  mov     [rsp+2D0h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x140006e5b  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x140006e60  mov     [rsp+2D0h+lpcchClass], rcx; lpcchClass
0x140006e65  lea     r8, [rbp+1D0h+Name]; lpName
0x140006e69  mov     [rsp+2D0h+lpClass], rcx; lpClass
0x140006e6e  mov     edx, esi; dwIndex
0x140006e70  mov     [rsp+2D0h+phkResult], rcx; lpReserved
0x140006e75  mov     rcx, [rsp+2D0h+hKey]; hKey
0x140006e7a  mov     [rsp+2D0h+cchName], 101h
0x140006e82  call    cs:__imp_RegEnumKeyExW
0x140006e89  nop     dword ptr [rax+rax+00h]
0x140006e8e  inc     esi
0x140006e90  xor     ecx, ecx
0x140006e92  test    eax, eax
0x140006e94  jnz     short loc_140006EA2
0x140006e96  mov     eax, [rsp+2D0h+cchName]
0x140006e9a  lea     ebx, [rbx+rax*2]
0x140006e9d  add     ebx, 2
0x140006ea0  jmp     short loc_140006E56
0x140006ea2  test    ebx, ebx
0x140006ea4  jz      loc_140006FE6
0x140006eaa  cmp     esi, 1
0x140006ead  jbe     loc_140006FE6
0x140006eb3  mov     rcx, cs:g_hHeap; hHeap
0x140006eba  lea     r8d, [rbx+2]; dwBytes
0x140006ebe  xor     edx, edx; dwFlags
0x140006ec0  call    cs:__imp_HeapAlloc
0x140006ec7  nop     dword ptr [rax+rax+00h]
0x140006ecc  xor     ecx, ecx
0x140006ece  mov     r15, rax
0x140006ed1  test    rax, rax
0x140006ed4  jz      loc_140006FE6
0x140006eda  mov     rsi, rax
0x140006edd  test    r14d, r14d
0x140006ee0  jnz     short loc_140006F3B
0x140006ee2  cmp     r13d, 2
0x140006ee6  jb      short loc_140006F3B
0x140006ee8  mov     rbx, cs:ServiceNames
0x140006eef  test    rbx, rbx
0x140006ef2  jz      short loc_140006F3B
0x140006ef4  jmp     short loc_140006F36
0x140006ef6  or      r8, 0FFFFFFFFFFFFFFFFh
0x140006efa  inc     r8
0x140006efd  cmp     [rbx+r8*2], cx
0x140006f02  jnz     short loc_140006EFA
0x140006f04  lea     r8, ds:2[r8*2]; Size
0x140006f0c  mov     rdx, rbx; Src
0x140006f0f  mov     rcx, rsi; void *
0x140006f12  call    memcpy_0
0x140006f17  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006f1b  xor     ecx, ecx
0x140006f1d  inc     rax
0x140006f20  cmp     [rbx+rax*2], cx
0x140006f24  jnz     short loc_140006F1D
0x140006f26  lea     rsi, [rsi+rax*2]
0x140006f2a  add     rsi, 2
0x140006f2e  lea     rbx, [rbx+rax*2]
0x140006f32  add     rbx, 2
0x140006f36  cmp     [rbx], cx
0x140006f39  jnz     short loc_140006EF6
0x140006f3b  mov     ebx, ecx
0x140006f3d  mov     [rsp+2D0h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x140006f42  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x140006f47  mov     [rsp+2D0h+lpcchClass], rcx; lpcchClass
0x140006f4c  lea     r8, [rbp+1D0h+Name]; lpName
0x140006f50  mov     [rsp+2D0h+lpClass], rcx; lpClass
0x140006f55  mov     edx, ebx; dwIndex
0x140006f57  mov     [rsp+2D0h+phkResult], rcx; lpReserved
0x140006f5c  mov     rcx, [rsp+2D0h+hKey]; hKey
0x140006f61  mov     [rsp+2D0h+cchName], 101h
0x140006f69  call    cs:__imp_RegEnumKeyExW
0x140006f70  nop     dword ptr [rax+rax+00h]
0x140006f75  xor     ecx, ecx
0x140006f77  test    eax, eax
0x140006f79  jnz     short loc_140006FB1
0x140006f7b  lea     rax, [rbp+1D0h+Name]
0x140006f7f  or      r8, 0FFFFFFFFFFFFFFFFh
0x140006f83  inc     r8
0x140006f86  cmp     [rax+r8*2], cx
0x140006f8b  jnz     short loc_140006F83
0x140006f8d  lea     r8, ds:2[r8*2]; Size
0x140006f95  mov     rcx, rsi; void *
0x140006f98  lea     rdx, [rbp+1D0h+Name]; Src
0x140006f9c  call    memcpy_0
0x140006fa1  mov     eax, [rsp+2D0h+cchName]
0x140006fa5  inc     ebx
0x140006fa7  inc     eax
0x140006fa9  xor     ecx, ecx
0x140006fab  lea     rsi, [rsi+rax*2]
0x140006faf  jmp     short loc_140006F3D
0x140006fb1  mov     [rsi], cx
0x140006fb4  mov     r8, cs:ServiceNames; lpMem
0x140006fbb  test    r8, r8
0x140006fbe  jz      short loc_140006FD7
0x140006fc0  mov     rcx, cs:g_hHeap; hHeap
0x140006fc7  xor     edx, edx; dwFlags
0x140006fc9  call    cs:__imp_HeapFree
0x140006fd0  nop     dword ptr [rax+rax+00h]
0x140006fd5  xor     ecx, ecx
0x140006fd7  mov     rax, r15
0x140006fda  mov     r14d, ecx
0x140006fdd  mov     cs:ServiceNames, rax
0x140006fe4  jmp     short loc_140006FED
0x140006fe6  mov     rax, cs:ServiceNames
0x140006fed  test    rax, rax
0x140006ff0  jz      loc_1400072F1
0x140006ff6  cmp     r13d, 2
0x140006ffa  jnb     short loc_140007006
0x140006ffc  xor     r13d, r13d
0x140006fff  test    r15, r15
0x140007002  jz      short loc_140007013
0x140007004  jmp     short loc_140007009
0x140007006  xor     r13d, r13d
0x140007009  cmp     [rax], r13w
0x14000700d  jz      loc_1400072F1
0x140007013  mov     rcx, [rsp+2D0h+hKey]
0x140007018  lea     r8, [rsp+2D0h+var_290]
0x14000701d  lea     rdx, aCoinitializese_3; "CoInitializeSecurityParam"
0x140007024  call    RegQueryDword
0x140007029  test    eax, eax
0x14000702b  jnz     short loc_140007034
0x14000702d  mov     eax, [rsp+2D0h+var_290]
0x140007031  mov     [rdi+28h], eax
0x140007034  mov     rcx, [rsp+2D0h+hKey]
0x140007039  lea     r8, [rsp+2D0h+var_290]
0x14000703e  lea     rdx, aCoinitializese_0; "CoInitializeSecurityAllowLowBox"
0x140007045  call    RegQueryDword
0x14000704a  test    eax, eax
0x14000704c  jnz     short loc_14000705C
0x14000704e  cmp     [rsp+2D0h+var_290], r13d
0x140007053  jz      short loc_14000705C
0x140007055  or      dword ptr [rdi+94h], 2
0x14000705c  mov     rcx, [rsp+2D0h+hKey]
0x140007061  lea     r8, [rsp+2D0h+var_290]
0x140007066  lea     rdx, aCoinitializese_2; "CoInitializeSecurityAllowInteractiveUse"...
0x14000706d  call    RegQueryDword
0x140007072  test    eax, eax
0x140007074  jnz     short loc_140007084
0x140007076  cmp     [rsp+2D0h+var_290], r13d
0x14000707b  jz      short loc_140007084
0x14000707d  or      dword ptr [rdi+94h], 10h
0x140007084  mov     rcx, [rsp+2D0h+hKey]
0x140007089  lea     r8, [rsp+2D0h+var_290]
0x14000708e  lea     rdx, aCoinitializese_1; "CoInitializeSecurityAllowComCapability"
0x140007095  call    RegQueryDword
0x14000709a  test    eax, eax
0x14000709c  jnz     short loc_1400070AC
0x14000709e  cmp     [rsp+2D0h+var_290], r13d
0x1400070a3  jz      short loc_1400070AC
0x1400070a5  or      dword ptr [rdi+94h], 20h
0x1400070ac  mov     rcx, [rsp+2D0h+hKey]
0x1400070b1  lea     r8, [rsp+2D0h+var_290]
0x1400070b6  lea     rdx, aCoinitializese_4; "CoInitializeSecurityAllowCrossContainer"
0x1400070bd  call    RegQueryDword
0x1400070c2  test    eax, eax
0x1400070c4  jnz     short loc_1400070D4
0x1400070c6  cmp     [rsp+2D0h+var_290], r13d
0x1400070cb  jz      short loc_1400070D4
0x1400070cd  or      dword ptr [rdi+94h], 40h
0x1400070d4  cmp     [rdi+28h], r13d
0x1400070d8  jz      loc_1400071ED
0x1400070de  mov     rcx, [rsp+2D0h+hKey]
0x1400070e3  lea     r8, [rsp+2D0h+var_290]
0x1400070e8  lea     rdx, aAuthentication; "AuthenticationLevel"
0x1400070ef  call    RegQueryDword
0x1400070f4  test    eax, eax
0x1400070f6  lea     r8, [rsp+2D0h+var_290]
0x1400070fb  mov     ecx, 4
0x140007100  lea     rdx, aImpersonationl; "ImpersonationLevel"
0x140007107  cmovz   ecx, [rsp+2D0h+var_290]
0x14000710c  mov     [rdi+2Ch], ecx
0x14000710f  mov     rcx, [rsp+2D0h+hKey]
0x140007114  call    RegQueryDword
0x140007119  test    eax, eax
0x14000711b  lea     r8, [rsp+2D0h+var_290]
0x140007120  mov     ecx, 2
0x140007125  lea     rdx, aAuthentication_0; "AuthenticationCapabilities"
0x14000712c  cmovz   ecx, [rsp+2D0h+var_290]
0x140007131  mov     [rdi+30h], ecx
0x140007134  mov     rcx, [rsp+2D0h+hKey]
0x140007139  call    RegQueryDword
0x14000713e  test    eax, eax
0x140007140  mov     dword ptr [rsp+2D0h+dwBytes], r13d
0x140007145  mov     ecx, 3000h
0x14000714a  lea     rax, [rsp+2D0h+dwBytes]
0x14000714f  cmovz   ecx, [rsp+2D0h+var_290]
0x140007154  lea     r9, [rsp+2D0h+lpsz]
0x140007159  mov     [rdi+34h], ecx
0x14000715c  lea     rdx, aCoinitializese_5; "CoInitializeSecurityAppID"
0x140007163  mov     rcx, [rsp+2D0h+hKey]; hkey
0x140007168  mov     r8d, 1
0x14000716e  mov     [rsp+2D0h+phkResult], rax; dwBytes
0x140007173  call    RegQueryValueWithAlloc
0x140007178  mov     r15, [rsp+2D0h+lpsz]
0x14000717d  test    eax, eax
0x14000717f  jnz     short loc_1400071A4
0x140007181  lea     rdx, [rdi+38h]; pclsid
0x140007185  mov     rcx, r15; lpsz
0x140007188  call    cs:__imp_CLSIDFromString
0x14000718f  nop     dword ptr [rax+rax+00h]
0x140007194  test    eax, eax
0x140007196  jns     short loc_1400071A4
0x140007198  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000719f  movdqu  xmmword ptr [rdi+38h], xmm0
0x1400071a4  mov     rcx, [rsp+2D0h+hKey]
0x1400071a9  lea     r8, [rsp+2D0h+var_290]
0x1400071ae  lea     rdx, aComUnmarshalin; "COM_UnmarshalingPolicy"
0x1400071b5  call    RegQueryDword
0x1400071ba  test    eax, eax
0x1400071bc  lea     r8, [rsp+2D0h+var_290]
0x1400071c1  mov     ebx, 0FFFFh
0x1400071c6  lea     rdx, aComRosettings; "COM_RoSettings"
0x1400071cd  mov     ecx, ebx
0x1400071cf  cmovz   ecx, [rsp+2D0h+var_290]
0x1400071d4  mov     [rdi+48h], ecx
0x1400071d7  mov     rcx, [rsp+2D0h+hKey]
0x1400071dc  call    RegQueryDword
0x1400071e1  test    eax, eax
0x1400071e3  cmovz   ebx, [rsp+2D0h+var_290]
0x1400071e8  mov     [rdi+4Ch], ebx
0x1400071eb  jmp     short loc_1400071F2
0x1400071ed  mov     r15, [rsp+2D0h+lpsz]
0x1400071f2  mov     rcx, [rsp+2D0h+hKey]
0x1400071f7  lea     r8, [rsp+2D0h+var_290]
0x1400071fc  lea     rdx, aDefaultrpcstac; "DefaultRpcStackSize"
0x140007203  call    RegQueryDword
0x140007208  test    eax, eax
0x14000720a  jnz     short loc_140007213
0x14000720c  mov     eax, [rsp+2D0h+var_290]
0x140007210  mov     [rdi+50h], eax
0x140007213  mov     rcx, [rsp+2D0h+hKey]
0x140007218  lea     r8, [rsp+2D0h+var_290]
0x14000721d  lea     rdx, aRpcexceptionfi; "RpcExceptionFilterMode"
0x140007224  call    RegQueryDword
0x140007229  test    eax, eax
0x14000722b  jnz     short loc_14000723B
0x14000722d  cmp     [rsp+2D0h+var_290], r13d
0x140007232  jnz     short loc_14000723B
0x140007234  mov     dword ptr [rdi+54h], 1
0x14000723b  mov     rcx, [rsp+2D0h+hKey]
0x140007240  lea     r8, [rsp+2D0h+var_290]
0x140007245  lea     rdx, aSystemcritical; "SystemCritical"
0x14000724c  call    RegQueryDword
0x140007251  test    eax, eax
0x140007253  jnz     short loc_140007263
0x140007255  cmp     [rsp+2D0h+var_290], r13d
0x14000725a  mov     eax, r13d
0x14000725d  setnz   al
0x140007260  mov     [rdi+58h], eax
0x140007263  mov     rcx, [rsp+2D0h+hKey]
  ... truncated ...
```
