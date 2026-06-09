# SingletonHelpers::SingletonHelper::TryRedirectLaunchToProcess(wil::basic_zstring_view<ushort> const &,wil::basic_zstring_view<ushort> const &,ulong,winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,bool,StandardMessage,FlowEndpointBase *)

- ea: `0x14005bd30`
- end: `0x14005be54`
- name: `?TryRedirectLaunchToProcess@SingletonHelper@SingletonHelpers@@KA?AW4RedirectionResult@details@2@AEBV?$basic_zstring_view@G@wil@@0KAEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@_NW4StandardMessage@@PEAVFlowEndpointBase@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD dwProcessId, HWND hWnd, DWORD, HKEY hkey)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14005b34c`

## callees

- `0x140009dfc`
- `0x140053000`
- `0x140053190`
- `0x140057044`
- `0x1400578bc`
- `0x140057d88`
- `0x14005bd30`
- `0x14005beb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14005bd98`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14005bd98`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x14005be33`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x14005be33`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x14005bdd1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x14005bdd1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14005bdc0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14005bdc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SingletonHelpers::SingletonHelper::TryRedirectLaunchToProcess(
        __int64 *a1,
        HKEY *a2,
        int a3,
        __int64 a4,
        DWORD dwProcessId,
        HWND hWnd,
        DWORD pcbData,
        HKEY hkey)
{
  HWND v10; // rdi
  __int64 v11; // r8
  char v12; // bl
  _BYTE v14[112]; // [rsp+50h] [rbp-79h] BYREF
  int v15; // [rsp+C0h] [rbp-9h]

  SingletonHelpers::details::GetSingletonSessionSubKey(&hkey, a1, a2, 0x20019u);
  LODWORD(hWnd) = 0;
  pcbData = 4;
  RegGetValueW(hkey, 0, L"CommunicationHWND", 0x18u, 0, &hWnd, &pcbData);
  v10 = (HWND)(unsigned int)hWnd;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  if ( !v10 )
    return 1;
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId((HWND)(unsigned int)v10, &dwProcessId) || a3 != dwProcessId )
    return 1;
  AllowSetForegroundWindow(dwProcessId);
  ConnectionlessEndpoint::ConnectionlessEndpoint((ConnectionlessEndpoint *)v14);
  v14[92] = 1;
  FlowEndpointBase::Initialize((__int64)v14, 0);
  v15 = 4;
  v12 = FlowEndpointBase::InvokeMessageToEndpointSync(v14, (unsigned int)v10, v11, a4);
  FlowEndpointBase::Uninitialize((FlowEndpointBase *)v14);
  FlowEndpointBase::~FlowEndpointBase((FlowEndpointBase *)v14);
  if ( v12 )
    return 0;
  else
    return (unsigned int)IsWindow(v10) + 1;
}

```

## disassembly

```asm
0x14005bd30  push    rbp
0x14005bd32  push    rbx
0x14005bd33  push    rsi
0x14005bd34  push    rdi
0x14005bd35  lea     rbp, [rsp-1Fh]
0x14005bd3a  sub     rsp, 0E8h
0x14005bd41  mov     rsi, r9
0x14005bd44  mov     ebx, r8d
0x14005bd47  mov     r9d, 20019h
0x14005bd4d  mov     r8, rdx
0x14005bd50  mov     rdx, rcx
0x14005bd53  lea     rcx, [rbp+37h+hkey]
0x14005bd57  call    ?GetSingletonSessionSubKey@details@SingletonHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@G@4@0K@Z; SingletonHelpers::details::GetSingletonSessionSubKey(wil::basic_zstring_view<ushort> const &,wil::basic_zstring_view<ushort> const &,ulong)
0x14005bd5c  mov     dword ptr [rbp+37h+hWnd], 0
0x14005bd63  mov     [rbp+37h+arg_30], 4
0x14005bd6a  lea     rax, [rbp+37h+arg_30]
0x14005bd6e  mov     [rsp+100h+pcbData], rax; pcbData
0x14005bd73  lea     rax, [rbp+37h+hWnd]
0x14005bd77  mov     [rsp+100h+pvData], rax; pvData
0x14005bd7c  mov     [rsp+100h+pdwType], 0; pdwType
0x14005bd85  mov     r9d, 18h; dwFlags
0x14005bd8b  mov     r8, cs:lpValueName; lpValue
0x14005bd92  xor     edx, edx; lpSubKey
0x14005bd94  mov     rcx, [rbp+37h+hkey]; hkey
0x14005bd98  call    cs:__imp_RegGetValueW
0x14005bd9e  mov     edi, dword ptr [rbp+37h+hWnd]
0x14005bda1  lea     rcx, [rbp+37h+hkey]
0x14005bda5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14005bdaa  test    rdi, rdi
0x14005bdad  jz      loc_14005BE43
0x14005bdb3  mov     [rbp+37h+dwProcessId], 0
0x14005bdba  lea     rdx, [rbp+37h+dwProcessId]; lpdwProcessId
0x14005bdbe  mov     ecx, edi; hWnd
0x14005bdc0  call    cs:__imp_GetWindowThreadProcessId
0x14005bdc6  test    eax, eax
0x14005bdc8  jz      short loc_14005BE43
0x14005bdca  mov     ecx, [rbp+37h+dwProcessId]; dwProcessId
0x14005bdcd  cmp     ebx, ecx
0x14005bdcf  jnz     short loc_14005BE43
0x14005bdd1  call    cs:__imp_AllowSetForegroundWindow
0x14005bdd7  lea     rcx, [rbp+37h+var_B0]; this
0x14005bddb  call    ??0ConnectionlessEndpoint@@QEAA@XZ; ConnectionlessEndpoint::ConnectionlessEndpoint(void)
0x14005bde0  nop
0x14005bde1  mov     [rbp+37h+var_54], 1
0x14005bde5  xor     edx, edx
0x14005bde7  lea     rcx, [rbp+37h+var_B0]
0x14005bdeb  call    ?Initialize@FlowEndpointBase@@QEAAXPEAVFlowEndpointMessageReceiver@@KW4EndpointInitializationOptions@@@Z; FlowEndpointBase::Initialize(FlowEndpointMessageReceiver *,ulong,EndpointInitializationOptions)
0x14005bdf0  mov     [rbp+37h+var_40], 4
0x14005bdf7  lea     rax, [rbp+37h+var_B0]
0x14005bdfb  mov     [rsp+100h+var_C0], rax
0x14005be00  mov     [rsp+100h+var_B8], 1
0x14005be05  mov     r9, rsi
0x14005be08  mov     edx, edi
0x14005be0a  lea     rcx, [rbp+37h+var_B0]
0x14005be0e  call    ?InvokeMessageToEndpointSync@FlowEndpointBase@@QEAA_NPEAUHWND__@@W4StandardMessage@@AEBUValueSet@Collections@Foundation@Windows@winrt@@@Z; FlowEndpointBase::InvokeMessageToEndpointSync(HWND__ *,StandardMessage,winrt::Windows::Foundation::Collections::ValueSet const &)
0x14005be13  mov     bl, al
0x14005be15  lea     rcx, [rbp+37h+var_B0]; this
0x14005be19  call    ?Uninitialize@FlowEndpointBase@@QEAAXXZ; FlowEndpointBase::Uninitialize(void)
0x14005be1e  nop
0x14005be1f  lea     rcx, [rbp+37h+var_B0]; this
0x14005be23  call    ??1FlowEndpointBase@@UEAA@XZ; FlowEndpointBase::~FlowEndpointBase(void)
0x14005be28  test    bl, bl
0x14005be2a  jz      short loc_14005BE30
0x14005be2c  xor     eax, eax
0x14005be2e  jmp     short loc_14005BE48
0x14005be30  mov     rcx, rdi; hWnd
0x14005be33  call    cs:__imp_IsWindow
0x14005be39  neg     eax
0x14005be3b  sbb     eax, eax
0x14005be3d  neg     eax
0x14005be3f  inc     eax
0x14005be41  jmp     short loc_14005BE48
0x14005be43  mov     eax, 1
0x14005be48  add     rsp, 0E8h
0x14005be4f  pop     rdi
0x14005be50  pop     rsi
0x14005be51  pop     rbx
0x14005be52  pop     rbp
0x14005be53  retn
```
