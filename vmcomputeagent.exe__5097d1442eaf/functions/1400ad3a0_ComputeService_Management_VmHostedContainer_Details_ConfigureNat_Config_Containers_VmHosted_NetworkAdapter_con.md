# ComputeService::Management::VmHostedContainer::Details::ConfigureNat(Config::Containers::VmHosted::NetworkAdapter const &,_GUID const &,uint)

- ea: `0x1400ad3a0`
- end: `0x1400ad66f`
- name: `?ConfigureNat@Details@VmHostedContainer@Management@ComputeService@@YAXAEBUNetworkAdapter@VmHosted@Containers@Config@@AEBU_GUID@@I@Z`
- size: `719`
- prototype: `void(ComputeService::Management::VmHostedContainer::Details *__hidden this, const struct Config::Containers::VmHosted::NetworkAdapter *, const struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400ad678`

## callees

- `0x140005360`
- `0x140008760`
- `0x1400341ac`
- `0x14008ae64`
- `0x1400ad3a0`
- `0x1400b1b90`
- `0x1400b1bb8`
- `0x1400b23e0`
- `0x1400b2508`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ad4c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400ad4c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ad4b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400ad4b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ad4bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ad5b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ad4bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400ad5b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400ad4ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400ad4ed`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1400ad3f2`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1400ad3f2`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1400ad3d3`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1400ad3d3`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x1400ad40c`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x1400ad40c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ad542`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ad597`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ad542`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1400ad597`

## string_xrefs

- `0x1400ad5d8`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400ad5ed`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400ad602`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400ad617`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400ad633`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400ad648`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400ad65d`: `onecore\vm\compute\management\orchestration\vmhostedcontainer\vmhostednetworkutilities.cpp`
- `0x1400ad4df`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ComputeService::Management::VmHostedContainer::Details::ConfigureNat(
        ComputeService::Management::VmHostedContainer::Details *this,
        const GUID *a2,
        const struct _GUID *a3)
{
  unsigned int v3; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // r8d
  const unsigned __int16 *v10; // r9
  _QWORD *v11; // r8
  _QWORD *v12; // r8
  __int64 v13; // r8
  HKEY Value; // rsi
  DWORD LastError; // ebx
  unsigned int v16; // eax
  _QWORD *v17; // rcx
  const WCHAR *v18; // rdx
  unsigned int v19; // eax
  char *v20; // rdi
  DWORD v21; // eax
  const WCHAR *v22; // rdx
  unsigned int v23; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-50h]
  unsigned int phkResulta; // [rsp+20h] [rbp-50h]
  unsigned int phkResultb; // [rsp+20h] [rbp-50h]
  unsigned int phkResultc; // [rsp+20h] [rbp-50h]
  bool cbData; // [rsp+28h] [rbp-48h]
  char v29; // [rsp+30h] [rbp-40h] BYREF
  __int16 v30; // [rsp+31h] [rbp-3Fh]
  ULONG InterfaceIndex; // [rsp+34h] [rbp-3Ch] BYREF
  NET_LUID InterfaceLuid; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v34; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v3 = (unsigned int)a3;
  InterfaceIndex = 0;
  InterfaceLuid.Value = 0;
  v6 = SetCurrentThreadCompartmentId((NET_IF_COMPARTMENT_ID)a3);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v6,
      phkResult);
  v30 = 258;
  v7 = ConvertInterfaceGuidToLuid(a2, &InterfaceLuid);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x253,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v7,
      phkResult);
  v8 = ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex);
  if ( v8 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x254,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v8,
      phkResult);
  if ( !InterfaceIndex )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x258,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)0x4C6,
      phkResult);
  wil::details::ScopeExitFnGuard__lambda_d6d2541099fc7e2a91d28a9f5de2928d___::operator()(&v29);
  if ( *((_QWORD *)this + 13) )
  {
    v11 = (_QWORD *)((char *)this + 88);
    if ( *((_QWORD *)this + 14) > 7u )
      v11 = (_QWORD *)*v11;
    ComputeService::Net::SetDefaultRoute((ComputeService::Net *)InterfaceIndex, v3, (unsigned int)v11, v10);
  }
  LOBYTE(v9) = *((_BYTE *)this + 192);
  if ( (_BYTE)v9 || *((_WORD *)this + 97) )
    ComputeService::Net::UpdateInterface(
      (ComputeService::Net *)InterfaceIndex,
      v3,
      v9,
      *((_WORD *)this + 97),
      phkResult);
  v12 = (_QWORD *)((char *)this + 56);
  if ( *((_QWORD *)this + 10) > 7u )
    v12 = (_QWORD *)*v12;
  LOBYTE(v10) = *((_BYTE *)this + 120);
  ComputeService::Net::Details::AddOrRemoveIPAddress(
    (ComputeService::Net::Details *)InterfaceIndex,
    v3,
    (unsigned int)v12,
    v10,
    phkResult,
    cbData);
  InterfaceLuid.Value = 0;
  LOBYTE(v13) = 1;
  Vml::GuidToString(lpSubKey, a2, v13);
  Value = (HKEY)InterfaceLuid.Value;
  if ( InterfaceLuid.Value )
  {
    LastError = GetLastError();
    RegCloseKey(Value);
    SetLastError(LastError);
  }
  InterfaceLuid.Value = 0;
  v16 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\",
          0,
          0x20006u,
          (PHKEY)&InterfaceLuid);
  if ( v16 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x34F,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v16,
      phkResulta);
  v17 = (_QWORD *)((char *)this + 128);
  if ( *((_QWORD *)this + 19) > 7u )
    v17 = (_QWORD *)*v17;
  v18 = (const WCHAR *)lpSubKey;
  if ( v34 > 7 )
    v18 = lpSubKey[0];
  v19 = RegSetKeyValueW((HKEY)InterfaceLuid.Value, v18, L"NameServer", 1u, v17, 2 * *((_DWORD *)this + 36) + 2);
  if ( v19 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x358,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v19,
      phkResultb);
  v20 = (char *)this + 160;
  v21 = 2 * *((_DWORD *)v20 + 4) + 2;
  if ( *((_QWORD *)v20 + 3) > 7u )
    v20 = *(char **)v20;
  v22 = (const WCHAR *)lpSubKey;
  if ( v34 > 7 )
    v22 = lpSubKey[0];
  v23 = RegSetKeyValueW((HKEY)InterfaceLuid.Value, v22, L"Domain", 1u, v20, v21);
  if ( v23 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x361,
      (unsigned int)"onecore\\vm\\compute\\management\\orchestration\\vmhostedcontainer\\vmhostednetworkutilities.cpp",
      (const char *)v23,
      phkResultc);
  std::wstring::~wstring(lpSubKey);
  if ( InterfaceLuid.Value )
    RegCloseKey((HKEY)InterfaceLuid.Value);
}

```

## disassembly

```asm
0x1400ad3a0  push    rbp
0x1400ad3a2  push    rbx
0x1400ad3a3  push    rsi
0x1400ad3a4  push    rdi
0x1400ad3a5  push    r14
0x1400ad3a7  mov     rbp, rsp
0x1400ad3aa  sub     rsp, 70h
0x1400ad3ae  mov     rax, cs:__security_cookie
0x1400ad3b5  xor     rax, rsp
0x1400ad3b8  mov     [rbp+var_10], rax
0x1400ad3bc  mov     ebx, r8d
0x1400ad3bf  mov     rsi, rdx
0x1400ad3c2  mov     rdi, rcx
0x1400ad3c5  xor     r14d, r14d
0x1400ad3c8  mov     [rbp+InterfaceIndex], r14d
0x1400ad3cc  mov     qword ptr [rbp+InterfaceLuid], r14
0x1400ad3d0  mov     ecx, r8d; CompartmentId
0x1400ad3d3  call    cs:__imp_SetCurrentThreadCompartmentId
0x1400ad3d9  mov     rcx, [rbp+28h]; this
0x1400ad3dd  test    eax, eax
0x1400ad3df  jnz     loc_1400AD5EA
0x1400ad3e5  mov     [rbp+var_3F], 102h
0x1400ad3eb  lea     rdx, [rbp+InterfaceLuid]; InterfaceLuid
0x1400ad3ef  mov     rcx, rsi; InterfaceGuid
0x1400ad3f2  call    cs:__imp_ConvertInterfaceGuidToLuid
0x1400ad3f8  mov     rcx, [rbp+28h]; this
0x1400ad3fc  test    eax, eax
0x1400ad3fe  jnz     loc_1400AD5FF
0x1400ad404  lea     rdx, [rbp+InterfaceIndex]; InterfaceIndex
0x1400ad408  lea     rcx, [rbp+InterfaceLuid]; InterfaceLuid
0x1400ad40c  call    cs:__imp_ConvertInterfaceLuidToIndex
0x1400ad412  mov     rcx, [rbp+28h]; this
0x1400ad416  test    eax, eax
0x1400ad418  jnz     loc_1400AD614
0x1400ad41e  cmp     [rbp+InterfaceIndex], r14d
0x1400ad422  jz      loc_1400AD629
0x1400ad428  lea     rcx, [rbp+var_40]
0x1400ad42c  call    wil__details__ScopeExitFnGuard__lambda_d6d2541099fc7e2a91d28a9f5de2928d_____operator__
0x1400ad431  cmp     [rdi+68h], r14
0x1400ad435  jz      short loc_1400AD44F
0x1400ad437  lea     r8, [rdi+58h]
0x1400ad43b  cmp     qword ptr [r8+18h], 7
0x1400ad440  jbe     short loc_1400AD445
0x1400ad442  mov     r8, [r8]; unsigned int
0x1400ad445  mov     edx, ebx; unsigned int
0x1400ad447  mov     ecx, [rbp+InterfaceIndex]; this
0x1400ad44a  call    ?SetDefaultRoute@Net@ComputeService@@YAXKIPEBG@Z; ComputeService::Net::SetDefaultRoute(ulong,uint,ushort const *)
0x1400ad44f  mov     r8b, [rdi+0C0h]; unsigned int
0x1400ad456  test    r8b, r8b
0x1400ad459  jnz     short loc_1400AD465
0x1400ad45b  cmp     [rdi+0C2h], r14w
0x1400ad463  jbe     short loc_1400AD477
0x1400ad465  movzx   r9d, word ptr [rdi+0C2h]; bool
0x1400ad46d  mov     edx, ebx; unsigned int
0x1400ad46f  mov     ecx, [rbp+InterfaceIndex]; this
0x1400ad472  call    ?UpdateInterface@Net@ComputeService@@YAXKI_NK@Z; ComputeService::Net::UpdateInterface(ulong,uint,bool,ulong)
0x1400ad477  lea     r8, [rdi+38h]
0x1400ad47b  cmp     qword ptr [r8+18h], 7
0x1400ad480  jbe     short loc_1400AD485
0x1400ad482  mov     r8, [r8]; unsigned int
0x1400ad485  mov     r9b, [rdi+78h]; unsigned __int16 *
0x1400ad489  mov     edx, ebx; unsigned int
0x1400ad48b  mov     ecx, [rbp+InterfaceIndex]; this
0x1400ad48e  call    ?AddOrRemoveIPAddress@Details@Net@ComputeService@@YAXKIPEBGE_N@Z; ComputeService::Net::Details::AddOrRemoveIPAddress(ulong,uint,ushort const *,uchar,bool)
0x1400ad493  mov     qword ptr [rbp+InterfaceLuid], r14
0x1400ad497  mov     r8b, 1
0x1400ad49a  mov     rdx, rsi
0x1400ad49d  lea     rcx, [rbp+lpSubKey]
0x1400ad4a1  call    ?GuidToString@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; Vml::GuidToString(_GUID const &,bool)
0x1400ad4a6  nop
0x1400ad4a7  mov     rsi, qword ptr [rbp+InterfaceLuid]
0x1400ad4ab  test    rsi, rsi
0x1400ad4ae  jz      short loc_1400AD4C9
0x1400ad4b0  call    cs:__imp_GetLastError
0x1400ad4b6  mov     ebx, eax
0x1400ad4b8  mov     rcx, rsi; hKey
0x1400ad4bb  call    cs:__imp_RegCloseKey
0x1400ad4c1  mov     ecx, ebx; dwErrCode
0x1400ad4c3  call    cs:__imp_SetLastError
0x1400ad4c9  mov     qword ptr [rbp+InterfaceLuid], r14
0x1400ad4cd  lea     rax, [rbp+InterfaceLuid]
0x1400ad4d1  mov     [rsp+70h+phkResult], rax; unsigned int
0x1400ad4d6  mov     r9d, 20006h; samDesired
0x1400ad4dc  xor     r8d, r8d; ulOptions
0x1400ad4df  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Tc"...
0x1400ad4e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400ad4ed  call    cs:__imp_RegOpenKeyExW
0x1400ad4f3  mov     rcx, [rbp+28h]; this
0x1400ad4f7  test    eax, eax
0x1400ad4f9  jnz     loc_1400AD645
0x1400ad4ff  lea     rcx, [rdi+80h]
0x1400ad506  mov     eax, [rcx+10h]
0x1400ad509  lea     eax, ds:2[rax*2]
0x1400ad510  cmp     qword ptr [rcx+18h], 7
0x1400ad515  jbe     short loc_1400AD51A
0x1400ad517  mov     rcx, [rcx]
0x1400ad51a  lea     rdx, [rbp+lpSubKey]
0x1400ad51e  cmp     [rbp+var_18], 7
0x1400ad523  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x1400ad528  mov     dword ptr [rsp+70h+cbData], eax; cbData
0x1400ad52c  mov     [rsp+70h+phkResult], rcx; unsigned int
0x1400ad531  mov     r9d, 1; dwType
0x1400ad537  lea     r8, aNameserver; "NameServer"
0x1400ad53e  mov     rcx, qword ptr [rbp+InterfaceLuid]; hKey
0x1400ad542  call    cs:__imp_RegSetKeyValueW
0x1400ad548  mov     rcx, [rbp+28h]; this
0x1400ad54c  test    eax, eax
0x1400ad54e  jnz     loc_1400AD65A
0x1400ad554  add     rdi, 0A0h
0x1400ad55b  mov     eax, [rdi+10h]
0x1400ad55e  lea     eax, ds:2[rax*2]
0x1400ad565  cmp     qword ptr [rdi+18h], 7
0x1400ad56a  jbe     short loc_1400AD56F
0x1400ad56c  mov     rdi, [rdi]
0x1400ad56f  lea     rdx, [rbp+lpSubKey]
0x1400ad573  cmp     [rbp+var_18], 7
0x1400ad578  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x1400ad57d  mov     dword ptr [rsp+70h+cbData], eax; cbData
0x1400ad581  mov     [rsp+70h+phkResult], rdi; unsigned int
0x1400ad586  mov     r9d, 1; dwType
0x1400ad58c  lea     r8, aDomain; "Domain"
0x1400ad593  mov     rcx, qword ptr [rbp+InterfaceLuid]; hKey
0x1400ad597  call    cs:__imp_RegSetKeyValueW
0x1400ad59d  mov     rcx, [rbp+28h]; this
0x1400ad5a1  test    eax, eax
0x1400ad5a3  jnz     short loc_1400AD5D5
0x1400ad5a5  lea     rcx, [rbp+lpSubKey]; void *
0x1400ad5a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400ad5ae  nop
0x1400ad5af  mov     rcx, qword ptr [rbp+InterfaceLuid]; hKey
0x1400ad5b3  test    rcx, rcx
0x1400ad5b6  jz      short loc_1400AD5BE
0x1400ad5b8  call    cs:__imp_RegCloseKey
0x1400ad5be  mov     rcx, [rbp+var_10]
0x1400ad5c2  xor     rcx, rsp; StackCookie
0x1400ad5c5  call    __security_check_cookie
0x1400ad5ca  add     rsp, 70h
0x1400ad5ce  pop     r14
0x1400ad5d0  pop     rdi
0x1400ad5d1  pop     rsi
0x1400ad5d2  pop     rbx
0x1400ad5d3  pop     rbp
0x1400ad5d4  retn
0x1400ad5d5  mov     r9d, eax; char *
0x1400ad5d8  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400ad5df  mov     edx, 361h; void *
0x1400ad5e4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ad5ea  mov     r9d, eax; char *
0x1400ad5ed  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400ad5f4  mov     edx, 24Dh; void *
0x1400ad5f9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ad5ff  mov     r9d, eax; char *
0x1400ad602  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400ad609  mov     edx, 253h; void *
0x1400ad60e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ad614  mov     r9d, eax; char *
0x1400ad617  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400ad61e  mov     edx, 254h; void *
0x1400ad623  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ad629  mov     rcx, [rbp+28h]; this
0x1400ad62d  mov     r9d, 4C6h; char *
0x1400ad633  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400ad63a  mov     edx, 258h; void *
0x1400ad63f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ad645  mov     r9d, eax; char *
0x1400ad648  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400ad64f  mov     edx, 34Fh; void *
0x1400ad654  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400ad65a  mov     r9d, eax; char *
0x1400ad65d  lea     r8, aOnecoreVmCompu_13; "onecore\\vm\\compute\\management\\orche"...
0x1400ad664  mov     edx, 358h; void *
0x1400ad669  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
