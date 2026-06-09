# CollectorService::DeleteSubscription(ushort const *,ulong)

- ea: `0x180003f08`
- end: `0x180004281`
- name: `?DeleteSubscription@CollectorService@@QEAAXPEBGK@Z`
- size: `889`
- prototype: `void __fastcall(CollectorService *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180003560`

## callees

- `0x18000195c`
- `0x1800024f0`
- `0x1800032dc`
- `0x180003810`
- `0x180003e6c`
- `0x180003f08`
- `0x180005d7c`
- `0x1800062d4`
- `0x180006370`
- `0x1800064e0`
- `0x18000fb2c`
- `0x1800120f8`
- `0x1800155e8`
- `0x18001fe50`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180003feb`
- `RPCRT4!RpcImpersonateClient` at `0x180003f62`
- `RPCRT4!RpcImpersonateClient` at `0x18000400e`
- `RPCRT4!RpcImpersonateClient` at `0x180003f62`
- `RPCRT4!RpcImpersonateClient` at `0x18000400e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000423e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000423e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800040f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800040f2`

## string_xrefs

- `0x180003fab`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x18000405c`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x180004140`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x1800041d6`: `admin\wmi\events\forwarding\collector\service\service.cpp`

## pseudocode

```c
void __fastcall CollectorService::DeleteSubscription(CollectorService *this, const unsigned __int16 *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  const WCHAR *p_pExceptionObject; // rdx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  void **v14; // [rsp+30h] [rbp-89h] BYREF
  char v15; // [rsp+38h] [rbp-81h]
  const char *v16; // [rsp+40h] [rbp-79h]
  __int64 v17; // [rsp+48h] [rbp-71h]
  __int64 v18; // [rsp+50h] [rbp-69h]
  unsigned int v19; // [rsp+58h] [rbp-61h]
  int v20; // [rsp+5Ch] [rbp-5Dh]
  int v21; // [rsp+60h] [rbp-59h]
  HKEY phkResult[2]; // [rsp+68h] [rbp-51h] BYREF
  char v23[8]; // [rsp+78h] [rbp-41h] BYREF
  RPC_STATUS (__stdcall *v24)(); // [rsp+80h] [rbp-39h]
  char *v25; // [rsp+88h] [rbp-31h]
  __int128 v26; // [rsp+90h] [rbp-29h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-19h]
  void **pExceptionObject; // [rsp+A8h] [rbp-11h] BYREF
  char v29; // [rsp+B0h] [rbp-9h]
  const char *v30; // [rsp+B8h] [rbp-1h]
  unsigned __int64 v31; // [rsp+C0h] [rbp+7h]
  __int64 v32; // [rsp+C8h] [rbp+Fh]
  unsigned int v33; // [rsp+D0h] [rbp+17h]
  int v34; // [rsp+D4h] [rbp+1Bh]
  int v35; // [rsp+D8h] [rbp+1Fh]

  CollectorService::WaitForInit(this);
  v26 = 0;
  v27 = 0;
  v25 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v4 = RpcImpersonateClient(0);
  v5 = v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v4);
    }
    v29 = 0;
    v30 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v31 = 0;
    v32 = 0;
    v33 = v5;
    v34 = -1;
    v35 = 640;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  LOBYTE(phkResult[0]) = 0;
  phkResult[1] = (HKEY)RpcRevertToSelf;
  SubscriptionConfigWriter::DeleteAllPasswordEntries(a2);
  wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(phkResult);
  v6 = RpcImpersonateClient(0);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v6);
    }
    v15 = 0;
    v16 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v17 = 0;
    v18 = 0;
    v19 = v7;
    v20 = -1;
    v21 = 658;
    v14 = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&v14;
  }
  v23[0] = 0;
  v24 = RpcRevertToSelf;
  std::wstring::wstring(&pExceptionObject, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
  std::wstring::append(&pExceptionObject, L"\\Subscriptions");
  phkResult[0] = 0;
  p_pExceptionObject = (const WCHAR *)&pExceptionObject;
  if ( v31 >= 8 )
    p_pExceptionObject = (const WCHAR *)pExceptionObject;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, p_pExceptionObject, 0, 0x2001Fu, phkResult);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v9);
    }
    v15 = 0;
    v16 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v17 = 0;
    v18 = 0;
    v19 = v10;
    v20 = -1;
    v21 = 676;
    v14 = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&v14;
  }
  v11 = RegDeleteKeyRecursive(phkResult[0], a2);
  v12 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v11);
    }
    v15 = 0;
    v16 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v17 = 0;
    v18 = 0;
    v19 = v12;
    v20 = -1;
    v21 = 683;
    v14 = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&v14;
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)phkResult);
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(&pExceptionObject, v13, 0);
  wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v23);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  std::vector<std::wstring>::_Tidy(&v26);
  SubscriptionManager::RetractSubscription(*(SubscriptionManager **)this, a2);
}

```

## disassembly

```asm
0x180003f08  mov     [rsp-8+arg_10], rbx
0x180003f0d  mov     [rsp-8+arg_18], rsi
0x180003f12  push    rbp
0x180003f13  push    rdi
0x180003f14  push    r12
0x180003f16  push    r14
0x180003f18  push    r15
0x180003f1a  lea     rbp, [rsp-37h]
0x180003f1f  sub     rsp, 0F0h
0x180003f26  mov     rax, cs:__security_cookie
0x180003f2d  xor     rax, rsp
0x180003f30  mov     [rbp+57h+var_30], rax
0x180003f34  mov     rdi, rdx
0x180003f37  mov     r14, rcx
0x180003f3a  call    ?WaitForInit@CollectorService@@AEAAXXZ; CollectorService::WaitForInit(void)
0x180003f3f  xorps   xmm0, xmm0
0x180003f42  movdqu  [rbp+57h+var_80], xmm0
0x180003f47  xor     r12d, r12d
0x180003f4a  mov     [rbp+57h+var_70], r12
0x180003f4e  lea     r15, [r14+18h]
0x180003f52  mov     [rbp+57h+var_88], r15
0x180003f56  mov     rcx, r15; lpCriticalSection
0x180003f59  call    cs:__imp_EnterCriticalSection
0x180003f5f  nop
0x180003f60  xor     ecx, ecx; BindingHandle
0x180003f62  call    cs:__imp_RpcImpersonateClient
0x180003f68  mov     ebx, eax
0x180003f6a  test    eax, eax
0x180003f6c  jz      short loc_180003FEB
0x180003f6e  lea     rcx, WPP_GLOBAL_Control
0x180003f75  mov     r10, cs:WPP_GLOBAL_Control
0x180003f7c  cmp     r10, rcx
0x180003f7f  jz      short loc_180003FA7
0x180003f81  test    byte ptr [r10+1Ch], 10h
0x180003f86  jz      short loc_180003FA7
0x180003f88  cmp     byte ptr [r10+19h], 2
0x180003f8d  jb      short loc_180003FA7
0x180003f8f  lea     edx, [r12+14h]
0x180003f94  mov     r9d, eax
0x180003f97  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180003f9e  mov     rcx, [r10+10h]
0x180003fa2  call    WPP_SF_D
0x180003fa7  mov     [rbp+57h+var_60], r12b
0x180003fab  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180003fb2  mov     [rbp+57h+var_58], rax
0x180003fb6  mov     [rbp+57h+var_50], r12
0x180003fba  mov     [rbp+57h+var_48], r12
0x180003fbe  mov     [rbp+57h+var_40], ebx
0x180003fc1  mov     [rbp+57h+var_3C], 0FFFFFFFFh
0x180003fc8  mov     [rbp+57h+var_38], 280h
0x180003fcf  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180003fd6  mov     [rbp+57h+pExceptionObject], rax
0x180003fda  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180003fe1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180003fe5  call    _CxxThrowException_0
0x180003feb  mov     rsi, cs:__imp_RpcRevertToSelf
0x180003ff2  mov     byte ptr [rbp+57h+var_A8], r12b
0x180003ff6  mov     [rbp+57h+var_A0], rsi
0x180003ffa  mov     rcx, rdi; unsigned __int16 *
0x180003ffd  call    ?DeleteAllPasswordEntries@SubscriptionConfigWriter@@SAXPEBG@Z; SubscriptionConfigWriter::DeleteAllPasswordEntries(ushort const *)
0x180004002  nop
0x180004003  lea     rcx, [rbp+57h+var_A8]
0x180004007  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x18000400c  xor     ecx, ecx; BindingHandle
0x18000400e  call    cs:__imp_RpcImpersonateClient
0x180004014  mov     ebx, eax
0x180004016  test    eax, eax
0x180004018  jz      loc_18000409E
0x18000401e  lea     rcx, WPP_GLOBAL_Control
0x180004025  mov     r10, cs:WPP_GLOBAL_Control
0x18000402c  cmp     r10, rcx
0x18000402f  jz      short loc_180004057
0x180004031  test    byte ptr [r10+1Ch], 10h
0x180004036  jz      short loc_180004057
0x180004038  cmp     byte ptr [r10+19h], 2
0x18000403d  jb      short loc_180004057
0x18000403f  mov     edx, 15h
0x180004044  mov     r9d, eax
0x180004047  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x18000404e  mov     rcx, [r10+10h]
0x180004052  call    WPP_SF_D
0x180004057  mov     [rsp+110h+var_D8], r12b
0x18000405c  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180004063  mov     [rbp+57h+var_D0], rax
0x180004067  mov     [rbp+57h+var_C8], r12
0x18000406b  mov     [rbp+57h+var_C0], r12
0x18000406f  mov     [rbp+57h+var_B8], ebx
0x180004072  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x180004079  mov     [rbp+57h+var_B0], 292h
0x180004080  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004087  mov     [rsp+110h+var_E0], rax
0x18000408c  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180004093  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x180004098  call    _CxxThrowException_0
0x18000409e  mov     [rbp+57h+var_98], r12b
0x1800040a2  mov     [rbp+57h+var_90], rsi
0x1800040a6  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800040ad  lea     rcx, [rbp+57h+pExceptionObject]
0x1800040b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800040b6  nop
0x1800040b7  lea     rdx, aSubscriptions; "\\Subscriptions"
0x1800040be  lea     rcx, [rbp+57h+pExceptionObject]
0x1800040c2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800040c7  mov     [rbp+57h+var_A8], r12
0x1800040cb  lea     rdx, [rbp+57h+pExceptionObject]
0x1800040cf  cmp     [rbp+57h+var_50], 8
0x1800040d4  cmovnb  rdx, [rbp+57h+pExceptionObject]; lpSubKey
0x1800040d9  lea     rax, [rbp+57h+var_A8]
0x1800040dd  mov     [rsp+110h+phkResult], rax; phkResult
0x1800040e2  mov     r9d, 2001Fh; samDesired
0x1800040e8  xor     r8d, r8d; ulOptions
0x1800040eb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800040f2  call    cs:__imp_RegOpenKeyExW
0x1800040f8  mov     ebx, eax
0x1800040fa  test    eax, eax
0x1800040fc  jz      loc_180004182
0x180004102  lea     rcx, WPP_GLOBAL_Control
0x180004109  mov     r10, cs:WPP_GLOBAL_Control
0x180004110  cmp     r10, rcx
0x180004113  jz      short loc_18000413B
0x180004115  test    byte ptr [r10+1Ch], 10h
0x18000411a  jz      short loc_18000413B
0x18000411c  cmp     byte ptr [r10+19h], 2
0x180004121  jb      short loc_18000413B
0x180004123  mov     edx, 16h
0x180004128  mov     r9d, eax
0x18000412b  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180004132  mov     rcx, [r10+10h]
0x180004136  call    WPP_SF_D
0x18000413b  mov     [rsp+110h+var_D8], r12b
0x180004140  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180004147  mov     [rbp+57h+var_D0], rax
0x18000414b  mov     [rbp+57h+var_C8], r12
0x18000414f  mov     [rbp+57h+var_C0], r12
0x180004153  mov     [rbp+57h+var_B8], ebx
0x180004156  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x18000415d  mov     [rbp+57h+var_B0], 2A4h
0x180004164  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000416b  mov     [rsp+110h+var_E0], rax
0x180004170  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180004177  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x18000417c  call    _CxxThrowException_0
0x180004182  mov     rdx, rdi; unsigned __int16 *
0x180004185  mov     rcx, [rbp+57h+var_A8]; HKEY
0x180004189  call    ?RegDeleteKeyRecursive@@YAKPEAUHKEY__@@PEBG@Z; RegDeleteKeyRecursive(HKEY__ *,ushort const *)
0x18000418e  mov     ebx, eax
0x180004190  test    eax, eax
0x180004192  jz      loc_180004218
0x180004198  lea     rcx, WPP_GLOBAL_Control
0x18000419f  mov     r10, cs:WPP_GLOBAL_Control
0x1800041a6  cmp     r10, rcx
0x1800041a9  jz      short loc_1800041D1
0x1800041ab  test    byte ptr [r10+1Ch], 10h
0x1800041b0  jz      short loc_1800041D1
0x1800041b2  cmp     byte ptr [r10+19h], 2
0x1800041b7  jb      short loc_1800041D1
0x1800041b9  mov     edx, 17h
0x1800041be  mov     r9d, eax
0x1800041c1  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x1800041c8  mov     rcx, [r10+10h]
0x1800041cc  call    WPP_SF_D
0x1800041d1  mov     [rsp+110h+var_D8], r12b
0x1800041d6  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x1800041dd  mov     [rbp+57h+var_D0], rax
0x1800041e1  mov     [rbp+57h+var_C8], r12
0x1800041e5  mov     [rbp+57h+var_C0], r12
0x1800041e9  mov     [rbp+57h+var_B8], ebx
0x1800041ec  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x1800041f3  mov     [rbp+57h+var_B0], 2ABh
0x1800041fa  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004201  mov     [rsp+110h+var_E0], rax
0x180004206  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000420d  lea     rcx, [rsp+110h+var_E0]; pExceptionObject
0x180004212  call    _CxxThrowException_0
0x180004218  lea     rcx, [rbp+57h+var_A8]; this
0x18000421c  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x180004221  nop
0x180004222  xor     r8d, r8d
0x180004225  mov     dl, 1
0x180004227  lea     rcx, [rbp+57h+pExceptionObject]
0x18000422b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180004230  nop
0x180004231  lea     rcx, [rbp+57h+var_98]
0x180004235  call    ??1?$ScopeGuardImpl0@P6AJXZ@wmi@@QEAA@XZ; wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(void)
0x18000423a  nop
0x18000423b  mov     rcx, r15; lpCriticalSection
0x18000423e  call    cs:__imp_LeaveCriticalSection
0x180004244  nop
0x180004245  lea     rcx, [rbp+57h+var_80]
0x180004249  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000424e  mov     rdx, rdi; unsigned __int16 *
0x180004251  mov     rcx, [r14]; this
0x180004254  call    ?RetractSubscription@SubscriptionManager@@QEAAXPEBG@Z; SubscriptionManager::RetractSubscription(ushort const *)
0x180004259  mov     rcx, [rbp+57h+var_30]
0x18000425d  xor     rcx, rsp; StackCookie
0x180004260  call    __security_check_cookie
0x180004265  lea     r11, [rsp+110h+var_20]
0x18000426d  mov     rbx, [r11+40h]
0x180004271  mov     rsi, [r11+48h]
0x180004275  mov     rsp, r11
0x180004278  pop     r15
0x18000427a  pop     r14
0x18000427c  pop     r12
0x18000427e  pop     rdi
0x18000427f  pop     rbp
0x180004280  retn
```
