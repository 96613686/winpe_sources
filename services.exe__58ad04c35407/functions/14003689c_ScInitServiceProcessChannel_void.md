# ScInitServiceProcessChannel(void)

- ea: `0x14003689c`
- end: `0x140036ae0`
- name: `?ScInitServiceProcessChannel@@YAXXZ`
- size: `580`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400848e0`

## callees

- `0x14001f99c`
- `0x14003689c`
- `0x140043284`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003692f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003697f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140036a60`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003692f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003697f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140036a60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400368ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140036a28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400368ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140036a28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400369d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140036a7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400369d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140036a7e`
- `ntdll!RtlInitializeSRWLock` at `0x1400368c6`
- `ntdll!RtlInitializeSRWLock` at `0x1400368c6`

## string_xrefs

- `0x140036928`: `ServicesPipeTimeout`
- `0x140036a1a`: `System\CurrentControlSet\Control\SCMConfig`
- `0x140036a59`: `AutostartServicesPipeTimeout`

## pseudocode

```c
void ScInitServiceProcessChannel(void)
{
  DWORD cbData; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  RtlInitializeSRWLock(&g_ScServiceChannelLock);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 16, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids);
  }
  else
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"ServicesPipeTimeout", 0, &Type, &g_ControlMessageTimeout, &cbData) || Type != 4 )
      *(_DWORD *)&g_ControlMessageTimeout = 30000;
    else
      g_fDefaultControlMessageTimeout = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"HandlerTimeout", 0, &Type, &g_dwHandlerTimeout, &cbData) || Type != 4 )
    {
      *(_DWORD *)&g_dwHandlerTimeout = *(_DWORD *)&g_ControlMessageTimeout & 0x7FFFFFFF;
    }
    else if ( *(_DWORD *)&g_dwHandlerTimeout
           && (*(_DWORD *)&g_dwHandlerTimeout & 0x7FFFFFFFu) < *(_DWORD *)&g_ControlMessageTimeout )
    {
      *(_DWORD *)&g_dwHandlerTimeout = *(_DWORD *)&g_ControlMessageTimeout & 0x7FFFFFFF
                                     | *(_DWORD *)&g_dwHandlerTimeout & 0x80000000;
    }
    RegCloseKey(hKey);
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SCMConfig", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"AutostartServicesPipeTimeout", 0, &Type, &g_AutostartControlMessageTimeout, &cbData)
      || Type != 4 )
    {
      *(_DWORD *)&g_AutostartControlMessageTimeout = 45000;
    }
    RegCloseKey(hKey);
  }
  if ( *(_DWORD *)&g_AutostartControlMessageTimeout < *(_DWORD *)&g_ControlMessageTimeout )
    *(_DWORD *)&g_AutostartControlMessageTimeout = *(_DWORD *)&g_ControlMessageTimeout;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
    WPP_SF_LLL(WPP_GLOBAL_Control->StubInfo, 17, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids);
}

```

## disassembly

```asm
0x14003689c  mov     [rsp-8+arg_18], rsi
0x1400368a1  push    rbp
0x1400368a2  mov     rbp, rsp
0x1400368a5  sub     rsp, 30h
0x1400368a9  lea     rcx, g_ScServiceChannelLock
0x1400368b0  mov     [rbp+hKey], 0
0x1400368b8  mov     [rbp+Type], 0
0x1400368bf  mov     [rbp+cbData], 0
0x1400368c6  call    cs:__imp_RtlInitializeSRWLock
0x1400368cc  lea     rax, [rbp+hKey]
0x1400368d0  mov     r9d, 20019h; samDesired
0x1400368d6  xor     r8d, r8d; ulOptions
0x1400368d9  mov     [rsp+30h+phkResult], rax; phkResult
0x1400368de  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control"
0x1400368e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400368ec  call    cs:__imp_RegOpenKeyExW
0x1400368f2  lea     rsi, WPP_GLOBAL_Control
0x1400368f9  test    eax, eax
0x1400368fb  jnz     loc_1400369E1
0x140036901  mov     rcx, [rbp+hKey]; hKey
0x140036905  lea     rax, [rbp+cbData]
0x140036909  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14003690e  lea     r9, [rbp+Type]; lpType
0x140036912  lea     rax, ?g_ControlMessageTimeout@@3KA; ulong g_ControlMessageTimeout
0x140036919  mov     [rbp+cbData], 4
0x140036920  xor     r8d, r8d; lpReserved
0x140036923  mov     [rsp+30h+phkResult], rax; lpData
0x140036928  lea     rdx, ValueName; "ServicesPipeTimeout"
0x14003692f  call    cs:__imp_RegQueryValueExW
0x140036935  test    eax, eax
0x140036937  jnz     short loc_140036947
0x140036939  cmp     [rbp+Type], 4
0x14003693d  jnz     short loc_140036947
0x14003693f  mov     cs:?g_fDefaultControlMessageTimeout@@3EA, al; uchar g_fDefaultControlMessageTimeout
0x140036945  jmp     short loc_140036951
0x140036947  mov     cs:?g_ControlMessageTimeout@@3KA, 7530h; ulong g_ControlMessageTimeout
0x140036951  mov     rcx, [rbp+hKey]; hKey
0x140036955  lea     rax, [rbp+cbData]
0x140036959  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14003695e  lea     r9, [rbp+Type]; lpType
0x140036962  lea     rax, g_dwHandlerTimeout
0x140036969  mov     [rbp+cbData], 4
0x140036970  xor     r8d, r8d; lpReserved
0x140036973  mov     [rsp+30h+phkResult], rax; lpData
0x140036978  lea     rdx, aHandlertimeout; "HandlerTimeout"
0x14003697f  call    cs:__imp_RegQueryValueExW
0x140036985  test    eax, eax
0x140036987  jnz     short loc_1400369C2
0x140036989  cmp     [rbp+Type], 4
0x14003698d  jnz     short loc_1400369C2
0x14003698f  mov     ecx, cs:g_dwHandlerTimeout
0x140036995  test    ecx, ecx
0x140036997  jz      short loc_1400369D5
0x140036999  mov     r8d, cs:?g_ControlMessageTimeout@@3KA; ulong g_ControlMessageTimeout
0x1400369a0  mov     eax, ecx
0x1400369a2  mov     edx, 7FFFFFFFh
0x1400369a7  and     eax, edx
0x1400369a9  cmp     eax, r8d
0x1400369ac  jnb     short loc_1400369D5
0x1400369ae  and     ecx, 80000000h
0x1400369b4  and     r8d, edx
0x1400369b7  or      ecx, r8d
0x1400369ba  mov     cs:g_dwHandlerTimeout, ecx
0x1400369c0  jmp     short loc_1400369D5
0x1400369c2  mov     eax, cs:?g_ControlMessageTimeout@@3KA; ulong g_ControlMessageTimeout
0x1400369c8  mov     edx, 7FFFFFFFh
0x1400369cd  and     eax, edx
0x1400369cf  mov     cs:g_dwHandlerTimeout, eax
0x1400369d5  mov     rcx, [rbp+hKey]; hKey
0x1400369d9  call    cs:__imp_RegCloseKey
0x1400369df  jmp     short loc_140036A08
0x1400369e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400369e8  cmp     rcx, rsi
0x1400369eb  jz      short loc_140036A08
0x1400369ed  test    byte ptr [rcx+1Ch], 1
0x1400369f1  jz      short loc_140036A08
0x1400369f3  mov     rcx, [rcx+10h]
0x1400369f7  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x1400369fe  mov     edx, 10h
0x140036a03  call    WPP_SF_
0x140036a08  lea     rax, [rbp+hKey]
0x140036a0c  mov     r9d, 20019h; samDesired
0x140036a12  xor     r8d, r8d; ulOptions
0x140036a15  mov     [rsp+30h+phkResult], rax; phkResult
0x140036a1a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\SCM"...
0x140036a21  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140036a28  call    cs:__imp_RegOpenKeyExW
0x140036a2e  test    eax, eax
0x140036a30  jnz     short loc_140036A84
0x140036a32  mov     rcx, [rbp+hKey]; hKey
0x140036a36  lea     rax, [rbp+cbData]
0x140036a3a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140036a3f  lea     r9, [rbp+Type]; lpType
0x140036a43  lea     rax, ?g_AutostartControlMessageTimeout@@3KA; ulong g_AutostartControlMessageTimeout
0x140036a4a  mov     [rbp+cbData], 4
0x140036a51  xor     r8d, r8d; lpReserved
0x140036a54  mov     [rsp+30h+phkResult], rax; lpData
0x140036a59  lea     rdx, aAutostartservi; "AutostartServicesPipeTimeout"
0x140036a60  call    cs:__imp_RegQueryValueExW
0x140036a66  test    eax, eax
0x140036a68  jnz     short loc_140036A70
0x140036a6a  cmp     [rbp+Type], 4
0x140036a6e  jz      short loc_140036A7A
0x140036a70  mov     cs:?g_AutostartControlMessageTimeout@@3KA, 0AFC8h; ulong g_AutostartControlMessageTimeout
0x140036a7a  mov     rcx, [rbp+hKey]; hKey
0x140036a7e  call    cs:__imp_RegCloseKey
0x140036a84  mov     ecx, cs:?g_AutostartControlMessageTimeout@@3KA; ulong g_AutostartControlMessageTimeout
0x140036a8a  mov     r9d, cs:?g_ControlMessageTimeout@@3KA; ulong g_ControlMessageTimeout
0x140036a91  cmp     ecx, r9d
0x140036a94  jnb     short loc_140036A9F
0x140036a96  mov     ecx, r9d
0x140036a99  mov     cs:?g_AutostartControlMessageTimeout@@3KA, ecx; ulong g_AutostartControlMessageTimeout
0x140036a9f  mov     r10, cs:WPP_GLOBAL_Control
0x140036aa6  cmp     r10, rsi
0x140036aa9  jz      short loc_140036AD5
0x140036aab  test    byte ptr [r10+1Ch], 4
0x140036ab0  jz      short loc_140036AD5
0x140036ab2  mov     eax, cs:g_dwHandlerTimeout
0x140036ab8  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140036abf  mov     dword ptr [rsp+30h+lpcbData], eax
0x140036ac3  mov     edx, 11h
0x140036ac8  mov     dword ptr [rsp+30h+phkResult], ecx
0x140036acc  mov     rcx, [r10+10h]
0x140036ad0  call    WPP_SF_LLL
0x140036ad5  mov     rsi, [rsp+30h+arg_18]
0x140036ada  add     rsp, 30h
0x140036ade  pop     rbp
0x140036adf  retn
```
