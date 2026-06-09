# ContainerCommon::LazyMachineId::LazyMachineId(void)

- ea: `0x1800c5c1c`
- end: `0x1800c5f6d`
- name: `??0LazyMachineId@ContainerCommon@@QEAA@XZ`
- size: `849`
- prototype: `__int64 __fastcall(ContainerCommon::LazyMachineId *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001bbfc`
- `0x1800641d0`

## callees

- `0x180006770`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x18002c6f4`
- `0x18006c144`
- `0x180083f2c`
- `0x180092008`
- `0x180092ee4`
- `0x180098c50`
- `0x1800c5c1c`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5cff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5e07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5e58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5cff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5e07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c5e58`

## string_xrefs

- `0x1800c5d77`: `ContainerTestProtocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
ContainerCommon::LazyMachineId *__fastcall ContainerCommon::LazyMachineId::LazyMachineId(
        ContainerCommon::LazyMachineId *this)
{
  __int64 v2; // rcx
  unsigned int EventlogServiceRegPath; // eax
  unsigned int v4; // r15d
  HKEY *phkResult; // rax
  __int64 v6; // r9
  HKEY *v7; // rax
  HKEY *v8; // rax
  PVOID *v9; // rcx
  LPCWSTR lpSubKey[4]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v13; // [rsp+68h] [rbp-18h]
  __int64 v14; // [rsp+6Ch] [rbp-14h]
  char v15; // [rsp+74h] [rbp-Ch]
  HKEY v16; // [rsp+B0h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+38h] BYREF
  HKEY v18; // [rsp+C0h] [rbp+40h] BYREF

  v16 = (HKEY)this;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(this);
  *((_QWORD *)this + 4) = 0;
  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpSubKey);
  EventlogServiceRegPath = RegistryPaths::GetEventlogServiceRegPath(v2, &hKey, lpSubKey);
  v4 = EventlogServiceRegPath;
  if ( EventlogServiceRegPath )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids,
        EventlogServiceRegPath);
    }
    pExceptionObject[0] = &byte_1800EC961;
    pExceptionObject[1] = 0;
    pExceptionObject[2] = 0;
    v13 = v4;
    v14 = -1;
    v15 = 0;
    throw (EvtException *)pExceptionObject;
  }
  LODWORD(v16) = 0;
  v18 = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v18);
  if ( !RegOpenKeyExW(hKey, lpSubKey[0], 0, 1u, phkResult) )
  {
    if ( !(unsigned int)RegReadDWORDValueNoThrow(v18, 0, L"ContainerTestMode", (unsigned int *)&v16) )
    {
      v6 = (unsigned int)v16;
      if ( (unsigned int)((_DWORD)v16 - 1) <= 2 )
      {
        *((_DWORD *)this + 8) = (_DWORD)v16;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids, v6);
        }
      }
    }
    if ( !(unsigned int)RegReadDWORDValueNoThrow(v18, 0, L"ContainerTestProtocol", (unsigned int *)&v16)
      && (unsigned int)((_DWORD)v16 - 1) <= 1 )
    {
      *((_DWORD *)this + 9) = (_DWORD)v16;
    }
    if ( !*((_DWORD *)this + 8) )
    {
      LODWORD(hKey) = 0;
      if ( (unsigned int)RegReadDWORDValueNoThrow(v18, 0, L"ContainerMode", (unsigned int *)&hKey) || !(_DWORD)hKey )
        *((_DWORD *)this + 8) = 1;
      else
        *((_DWORD *)this + 8) = 2;
    }
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v18);
  v16 = 0;
  v7 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v16);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control", 0, 1u, v7) )
  {
    if ( (unsigned int)RegReadStringValueNoThrow(v16) )
    {
      v8 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v16);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SQMClient", 0, 1u, v8)
        && (unsigned int)RegReadStringValueNoThrow(v16)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids);
      }
    }
  }
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v16);
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids,
        *((unsigned int *)this + 8));
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)v9 + 7) & 0x100000) != 0 && *((_BYTE *)v9 + 25) >= 4u )
      {
        WPP_SF_d(v9[2], 16, WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids, *((unsigned int *)this + 9));
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x100000) != 0 && *((_BYTE *)v9 + 25) >= 4u )
        WPP_SF_S(v9[2], 17, WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids, *(_QWORD *)this);
    }
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpSubKey);
  return this;
}

```

## disassembly

```asm
0x1800c5c1c  mov     [rsp-28h+arg_18], rbx
0x1800c5c21  mov     [rsp-28h+arg_0], rcx
0x1800c5c26  push    rbp
0x1800c5c27  push    rsi
0x1800c5c28  push    rdi
0x1800c5c29  push    r12
0x1800c5c2b  push    r15
0x1800c5c2d  mov     rbp, rsp
0x1800c5c30  sub     rsp, 80h
0x1800c5c37  mov     rbx, rcx
0x1800c5c3a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800c5c3f  nop
0x1800c5c40  xor     r12d, r12d
0x1800c5c43  mov     [rbx+20h], r12
0x1800c5c47  mov     [rbp+hKey], r12
0x1800c5c4b  lea     rcx, [rbp+lpSubKey]; void *
0x1800c5c4f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800c5c54  nop
0x1800c5c55  lea     r8, [rbp+lpSubKey]
0x1800c5c59  lea     rdx, [rbp+hKey]
0x1800c5c5d  call    ?GetEventlogServiceRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegistryPaths::GetEventlogServiceRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800c5c62  mov     r15d, eax
0x1800c5c65  test    eax, eax
0x1800c5c67  jz      short loc_1800C5CD8
0x1800c5c69  lea     rsi, WPP_GLOBAL_Control
0x1800c5c70  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5c77  cmp     rcx, rsi
0x1800c5c7a  jz      short loc_1800C5CA4
0x1800c5c7c  mov     edi, 100000h
0x1800c5c81  test    [rcx+1Ch], edi
0x1800c5c84  jz      short loc_1800C5CA4
0x1800c5c86  cmp     byte ptr [rcx+19h], 2
0x1800c5c8a  jb      short loc_1800C5CA4
0x1800c5c8c  lea     edx, [r12+0Ch]
0x1800c5c91  mov     r9d, eax
0x1800c5c94  lea     r8, WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids
0x1800c5c9b  mov     rcx, [rcx+10h]
0x1800c5c9f  call    WPP_SF_d
0x1800c5ca4  lea     rax, byte_1800EC961
0x1800c5cab  mov     [rbp+pExceptionObject], rax
0x1800c5caf  mov     [rbp+var_28], r12
0x1800c5cb3  mov     [rbp+var_20], r12
0x1800c5cb7  mov     [rbp+var_18], r15d
0x1800c5cbb  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x1800c5cc3  mov     [rbp+var_C], r12b
0x1800c5cc7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800c5cce  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800c5cd2  call    _CxxThrowException_0
0x1800c5cd8  mov     dword ptr [rbp+arg_0], r12d
0x1800c5cdc  mov     [rbp+arg_10], r12
0x1800c5ce0  lea     rcx, [rbp+arg_10]
0x1800c5ce4  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800c5ce9  mov     [rsp+80h+phkResult], rax; phkResult
0x1800c5cee  mov     r9d, 1; samDesired
0x1800c5cf4  xor     r8d, r8d; ulOptions
0x1800c5cf7  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800c5cfb  mov     rcx, [rbp+hKey]; hKey
0x1800c5cff  call    cs:__imp_RegOpenKeyExW
0x1800c5d05  lea     rsi, WPP_GLOBAL_Control
0x1800c5d0c  mov     edi, 100000h
0x1800c5d11  mov     r15b, 4
0x1800c5d14  test    eax, eax
0x1800c5d16  jnz     loc_1800C5DD5
0x1800c5d1c  lea     r9, [rbp+arg_0]; unsigned int *
0x1800c5d20  lea     r8, aContainertestm; "ContainerTestMode"
0x1800c5d27  xor     edx, edx; wchar_t *
0x1800c5d29  mov     rcx, [rbp+arg_10]; HKEY
0x1800c5d2d  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x1800c5d32  test    eax, eax
0x1800c5d34  jnz     short loc_1800C5D73
0x1800c5d36  mov     r9d, dword ptr [rbp+arg_0]
0x1800c5d3a  lea     eax, [r9-1]
0x1800c5d3e  cmp     eax, 2
0x1800c5d41  ja      short loc_1800C5D73
0x1800c5d43  mov     [rbx+20h], r9d
0x1800c5d47  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5d4e  cmp     rcx, rsi
0x1800c5d51  jz      short loc_1800C5D73
0x1800c5d53  test    [rcx+1Ch], edi
0x1800c5d56  jz      short loc_1800C5D73
0x1800c5d58  cmp     [rcx+19h], r15b
0x1800c5d5c  jb      short loc_1800C5D73
0x1800c5d5e  mov     edx, 0Dh
0x1800c5d63  lea     r8, WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids
0x1800c5d6a  mov     rcx, [rcx+10h]
0x1800c5d6e  call    WPP_SF_d
0x1800c5d73  lea     r9, [rbp+arg_0]; unsigned int *
0x1800c5d77  lea     r8, aContainertestp; "ContainerTestProtocol"
0x1800c5d7e  xor     edx, edx; wchar_t *
0x1800c5d80  mov     rcx, [rbp+arg_10]; HKEY
0x1800c5d84  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x1800c5d89  test    eax, eax
0x1800c5d8b  jnz     short loc_1800C5D9B
0x1800c5d8d  mov     ecx, dword ptr [rbp+arg_0]
0x1800c5d90  lea     eax, [rcx-1]
0x1800c5d93  cmp     eax, 1
0x1800c5d96  ja      short loc_1800C5D9B
0x1800c5d98  mov     [rbx+24h], ecx
0x1800c5d9b  cmp     [rbx+20h], r12d
0x1800c5d9f  jnz     short loc_1800C5DD5
0x1800c5da1  mov     dword ptr [rbp+hKey], r12d
0x1800c5da5  lea     r9, [rbp+hKey]; unsigned int *
0x1800c5da9  lea     r8, aContainermode; "ContainerMode"
0x1800c5db0  xor     edx, edx; wchar_t *
0x1800c5db2  mov     rcx, [rbp+arg_10]; HKEY
0x1800c5db6  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x1800c5dbb  test    eax, eax
0x1800c5dbd  jnz     short loc_1800C5DCE
0x1800c5dbf  cmp     dword ptr [rbp+hKey], r12d
0x1800c5dc3  jz      short loc_1800C5DCE
0x1800c5dc5  mov     dword ptr [rbx+20h], 2
0x1800c5dcc  jmp     short loc_1800C5DD5
0x1800c5dce  mov     dword ptr [rbx+20h], 1
0x1800c5dd5  lea     rcx, [rbp+arg_10]
0x1800c5dd9  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800c5dde  mov     [rbp+arg_0], r12
0x1800c5de2  lea     rcx, [rbp+arg_0]
0x1800c5de6  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800c5deb  mov     [rsp+80h+phkResult], rax; phkResult
0x1800c5df0  mov     r9d, 1; samDesired
0x1800c5df6  xor     r8d, r8d; ulOptions
0x1800c5df9  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Control"
0x1800c5e00  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c5e07  call    cs:__imp_RegOpenKeyExW
0x1800c5e0d  test    eax, eax
0x1800c5e0f  jnz     loc_1800C5EAC
0x1800c5e15  mov     r9, rbx
0x1800c5e18  lea     r8, aContainerid; "ContainerID"
0x1800c5e1f  lea     rdx, pszFormat
0x1800c5e26  mov     rcx, [rbp+arg_0]; hKey
0x1800c5e2a  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800c5e2f  test    eax, eax
0x1800c5e31  jz      short loc_1800C5EAC
0x1800c5e33  lea     rcx, [rbp+arg_0]
0x1800c5e37  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800c5e3c  mov     [rsp+80h+phkResult], rax; phkResult
0x1800c5e41  mov     r9d, 1; samDesired
0x1800c5e47  xor     r8d, r8d; ulOptions
0x1800c5e4a  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\SQMClient"
0x1800c5e51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c5e58  call    cs:__imp_RegOpenKeyExW
0x1800c5e5e  test    eax, eax
0x1800c5e60  jnz     short loc_1800C5EAC
0x1800c5e62  mov     r9, rbx
0x1800c5e65  lea     r8, aMachineid; "MachineId"
0x1800c5e6c  lea     rdx, pszFormat
0x1800c5e73  mov     rcx, [rbp+arg_0]; hKey
0x1800c5e77  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800c5e7c  test    eax, eax
0x1800c5e7e  jz      short loc_1800C5EAC
0x1800c5e80  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5e87  cmp     rcx, rsi
0x1800c5e8a  jz      short loc_1800C5EAC
0x1800c5e8c  test    [rcx+1Ch], edi
0x1800c5e8f  jz      short loc_1800C5EAC
0x1800c5e91  cmp     byte ptr [rcx+19h], 2
0x1800c5e95  jb      short loc_1800C5EAC
0x1800c5e97  mov     edx, 0Eh
0x1800c5e9c  lea     r8, WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids
0x1800c5ea3  mov     rcx, [rcx+10h]
0x1800c5ea7  call    WPP_SF_
0x1800c5eac  lea     rcx, [rbp+arg_0]
0x1800c5eb0  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800c5eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5ebc  cmp     rcx, rsi
0x1800c5ebf  jz      loc_1800C5F49
0x1800c5ec5  test    [rcx+1Ch], edi
0x1800c5ec8  jz      short loc_1800C5EF0
0x1800c5eca  cmp     [rcx+19h], r15b
0x1800c5ece  jb      short loc_1800C5EF0
0x1800c5ed0  mov     edx, 0Fh
0x1800c5ed5  mov     r9d, [rbx+20h]
0x1800c5ed9  lea     r8, WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids
0x1800c5ee0  mov     rcx, [rcx+10h]
0x1800c5ee4  call    WPP_SF_d
0x1800c5ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5ef0  cmp     rcx, rsi
0x1800c5ef3  jz      short loc_1800C5F49
0x1800c5ef5  test    [rcx+1Ch], edi
0x1800c5ef8  jz      short loc_1800C5F20
0x1800c5efa  cmp     [rcx+19h], r15b
0x1800c5efe  jb      short loc_1800C5F20
0x1800c5f00  mov     edx, 10h
0x1800c5f05  mov     r9d, [rbx+24h]
0x1800c5f09  lea     r8, WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids
0x1800c5f10  mov     rcx, [rcx+10h]
0x1800c5f14  call    WPP_SF_d
0x1800c5f19  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5f20  cmp     rcx, rsi
0x1800c5f23  jz      short loc_1800C5F49
0x1800c5f25  test    [rcx+1Ch], edi
0x1800c5f28  jz      short loc_1800C5F49
0x1800c5f2a  cmp     [rcx+19h], r15b
0x1800c5f2e  jb      short loc_1800C5F49
0x1800c5f30  mov     edx, 11h
0x1800c5f35  mov     r9, [rbx]
0x1800c5f38  lea     r8, WPP_2f1ae35dc365305f56d22887f1a13636_Traceguids
0x1800c5f3f  mov     rcx, [rcx+10h]
0x1800c5f43  call    WPP_SF_S
0x1800c5f48  nop
0x1800c5f49  lea     rcx, [rbp+lpSubKey]; void *
0x1800c5f4d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800c5f52  nop
0x1800c5f53  mov     rax, rbx
0x1800c5f56  mov     rbx, [rsp+80h+arg_18]
0x1800c5f5e  add     rsp, 80h
0x1800c5f65  pop     r15
0x1800c5f67  pop     r12
0x1800c5f69  pop     rdi
0x1800c5f6a  pop     rsi
0x1800c5f6b  pop     rbp
0x1800c5f6c  retn
```
