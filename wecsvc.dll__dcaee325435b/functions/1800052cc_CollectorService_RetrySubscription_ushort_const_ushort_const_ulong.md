# CollectorService::RetrySubscription(ushort const *,ushort const *,ulong)

- ea: `0x1800052cc`
- end: `0x180005aca`
- name: `?RetrySubscription@CollectorService@@QEAAXPEBG0K@Z`
- size: `2046`
- prototype: `void __fastcall(CollectorService *this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180003700`

## callees

- `0x180001260`
- `0x18000195c`
- `0x1800024f0`
- `0x1800032dc`
- `0x180003430`
- `0x180003a50`
- `0x180003be8`
- `0x180003cc8`
- `0x180003d10`
- `0x180003d48`
- `0x180003e6c`
- `0x180004288`
- `0x18000526c`
- `0x1800052cc`
- `0x180005d7c`
- `0x1800060e8`
- `0x1800062d4`
- `0x1800064e0`
- `0x18000669c`
- `0x180006910`
- `0x18000a938`
- `0x1800145cc`
- `0x18001483c`
- `0x180015f78`
- `0x1800161e4`
- `0x1800189e8`
- `0x18001fe50`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000595a`
- `msvcrt!_wcsicmp` at `0x18000595a`
- `RPCRT4!RpcRevertToSelf` at `0x1800058c4`
- `RPCRT4!RpcRevertToSelf` at `0x1800053a5`
- `RPCRT4!RpcRevertToSelf` at `0x1800058c4`
- `RPCRT4!RpcImpersonateClient` at `0x18000530c`
- `RPCRT4!RpcImpersonateClient` at `0x18000530c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800053d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800053d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800056c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800056c6`

## string_xrefs

- `0x180005359`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x18000544c`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x18000554e`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x180005714`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x1800057a5`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x180005858`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x1800059ec`: `admin\wmi\events\forwarding\collector\service\service.cpp`
- `0x180005a75`: `admin\wmi\events\forwarding\collector\service\service.cpp`

## pseudocode

```c
void __fastcall CollectorService::RetrySubscription(
        CollectorService *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HKEY v8; // r8
  const unsigned __int16 *v9; // r9
  SubscriptionConfigSnapshot *v10; // rax
  SubscriptionConfigSnapshot *v11; // rax
  char v12; // r14
  const char *v13; // r15
  void ***p_pExceptionObject; // rax
  void ***v15; // rcx
  const char *v16; // rdi
  void ***v17; // rax
  void ***v18; // rcx
  const WCHAR *v19; // rdx
  unsigned int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // rdx
  unsigned __int64 i; // rdi
  const wchar_t *v24; // rcx
  __int64 v25; // rax
  bool v26; // [rsp+40h] [rbp-C0h] BYREF
  void **v27; // [rsp+48h] [rbp-B8h] BYREF
  char v28; // [rsp+50h] [rbp-B0h]
  const char *v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  int v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+74h] [rbp-8Ch]
  int v34; // [rsp+78h] [rbp-88h]
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h] BYREF
  char v37[8]; // [rsp+90h] [rbp-70h] BYREF
  RPC_STATUS (__stdcall *v38)(); // [rsp+98h] [rbp-68h]
  HKEY v39[3]; // [rsp+A0h] [rbp-60h] BYREF
  char *v40; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v41; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v42[24]; // [rsp+E0h] [rbp-20h] BYREF
  char v43[24]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h]
  void **pExceptionObject; // [rsp+160h] [rbp+60h] BYREF
  char v47; // [rsp+168h] [rbp+68h]
  const char *v48; // [rsp+170h] [rbp+70h]
  unsigned __int64 v49; // [rsp+178h] [rbp+78h]
  __int64 v50; // [rsp+180h] [rbp+80h]
  unsigned int v51; // [rsp+188h] [rbp+88h]
  int v52; // [rsp+18Ch] [rbp+8Ch]
  int v53; // [rsp+190h] [rbp+90h]

  CollectorService::WaitForInit(this);
  v6 = RpcImpersonateClient(0);
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v6);
    }
    v47 = 0;
    v48 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v49 = 0;
    v50 = 0;
    v51 = v7;
    v52 = -1;
    v53 = 703;
    pExceptionObject = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v37[0] = 0;
  v38 = RpcRevertToSelf;
  v41 = 0;
  v36 = 0;
  _EventSources::_EventSources((_EventSources *)v42);
  v40 = (char *)this + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  SubscriptionConfigReader::SubscriptionConfigReader((SubscriptionConfigReader *)v39, a2, v8, v9);
  v26 = 1;
  SubscriptionConfigReader::GetEnabled((SubscriptionConfigReader *)v39, &v26);
  if ( !v26 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 4317);
    }
    v28 = 0;
    v29 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v30 = 0;
    v31 = 0;
    v32 = 4317;
    v33 = -1;
    v34 = 725;
    v27 = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&v27;
  }
  v10 = (SubscriptionConfigSnapshot *)operator new(0x20u);
  phkResult = (HKEY)v10;
  if ( v10 )
    v11 = SubscriptionConfigSnapshot::SubscriptionConfigSnapshot(
            v10,
            v39,
            a3,
            (struct tag_EcRpcMetadataPropertyList *)&v41,
            1,
            1,
            1);
  else
    v11 = 0;
  wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(&v36, v11);
  LODWORD(phkResult) = 0;
  if ( !ConfigBase::GetRegEnumValue(
          (ConfigBase *)v39,
          L"SubscriptionType",
          (struct _ENUM_NAMEVALUE_PAIR *)&EnumNameValueSubscriptionType,
          (unsigned int *)&phkResult)
    || (_DWORD)phkResult )
  {
    v12 = 0;
    if ( !a3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 87);
      }
      v28 = 0;
      v29 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
      v30 = 0;
      v31 = 0;
      v32 = 87;
      v33 = -1;
      v34 = 750;
      v27 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v27;
    }
  }
  else
  {
    if ( a3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 87);
      }
      v28 = 0;
      v29 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
      v30 = 0;
      v31 = 0;
      v32 = 87;
      v33 = -1;
      v34 = 743;
      v27 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v27;
    }
    v12 = 1;
  }
  v49 = 7;
  v48 = 0;
  LOWORD(pExceptionObject) = 0;
  std::wstring::reserve(&pExceptionObject, 48);
  std::wstring::assign(&pExceptionObject, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\EventCollector");
  if ( (unsigned __int64)(-1LL - (_QWORD)v48) <= 1 )
    goto LABEL_81;
  v13 = v48 + 1;
  if ( (unsigned __int8)std::wstring::_Grow(&pExceptionObject, v48 + 1, 0) )
  {
    p_pExceptionObject = &pExceptionObject;
    if ( v49 >= 8 )
      p_pExceptionObject = (void ***)pExceptionObject;
    *((_WORD *)p_pExceptionObject + (_QWORD)v48) = 92;
    v15 = &pExceptionObject;
    if ( v49 >= 8 )
      v15 = (void ***)pExceptionObject;
    v48 = v13;
    *((_WORD *)v15 + (_QWORD)v13) = 0;
  }
  std::wstring::append(&pExceptionObject, L"Subscriptions");
  if ( (unsigned __int64)(-1LL - (_QWORD)v48) <= 1 )
LABEL_81:
    std::_Xlength_error("string too long");
  v16 = v48 + 1;
  if ( (unsigned __int8)std::wstring::_Grow(&pExceptionObject, v48 + 1, 0) )
  {
    v17 = &pExceptionObject;
    if ( v49 >= 8 )
      v17 = (void ***)pExceptionObject;
    *((_WORD *)v17 + (_QWORD)v48) = 92;
    v18 = &pExceptionObject;
    if ( v49 >= 8 )
      v18 = (void ***)pExceptionObject;
    v48 = v16;
    *((_WORD *)v18 + (_QWORD)v16) = 0;
  }
  std::wstring::append(&pExceptionObject, a2);
  phkResult = 0;
  v19 = (const WCHAR *)&pExceptionObject;
  if ( v49 >= 8 )
    v19 = (const WCHAR *)pExceptionObject;
  v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x2001Fu, &phkResult);
  v21 = v20;
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, v20);
    }
    v28 = 0;
    v29 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v30 = 0;
    v31 = 0;
    v32 = v21;
    v33 = -1;
    v34 = 776;
    v27 = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&v27;
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
  if ( !v12
    && !SubscriptionConfigReader::GetEventSources((SubscriptionConfigReader *)v39, (struct _EventSources *)v42, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 1168);
    }
    v28 = 0;
    v29 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
    v30 = 0;
    v31 = 0;
    v32 = 1168;
    v33 = -1;
    v34 = 784;
    v27 = &wmi::GenericException::`vftable';
    throw (wmi::GenericException *)&v27;
  }
  LOBYTE(v22) = 1;
  std::wstring::_Tidy(&pExceptionObject, v22, 0);
  ConfigBase::~ConfigBase((ConfigBase *)v39);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  RpcRevertToSelf();
  v37[0] = 1;
  if ( v12 )
  {
    SubscriptionManager::AssertSubscription(
      *(SubscriptionManager **)this,
      a2,
      0,
      (const struct SubscriptionReadData *)(v36 + 16));
  }
  else
  {
    ValidateRegKeyName(a3);
    for ( i = 0; ; ++i )
    {
      if ( i >= v44 )
        goto LABEL_71;
      v24 = (const wchar_t *)(v45 + 32 * i);
      if ( *((_QWORD *)v24 + 3) >= 8u )
        v24 = *(const wchar_t **)v24;
      if ( !_wcsicmp(v24, a3) )
        break;
    }
    v25 = std::vector<bool>::operator[](v43, &v40, i);
    if ( ((1 << *(_QWORD *)(v25 + 8)) & **(_DWORD **)v25) == 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 4317);
      }
      v28 = 0;
      v29 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
      v30 = 0;
      v31 = 0;
      v32 = 4317;
      v33 = -1;
      v34 = 808;
      v27 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v27;
    }
    SubscriptionManager::AssertSubscription(
      *(SubscriptionManager **)this,
      a2,
      a3,
      (const struct SubscriptionReadData *)(v36 + 16));
    if ( i >= v44 )
    {
LABEL_71:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids, 1168);
      }
      v28 = 0;
      v29 = "admin\\wmi\\events\\forwarding\\collector\\service\\service.cpp";
      v30 = 0;
      v31 = 0;
      v32 = 1168;
      v33 = -1;
      v34 = 818;
      v27 = &wmi::GenericException::`vftable';
      throw (wmi::GenericException *)&v27;
    }
  }
  _EventSources::~_EventSources((_EventSources *)v42);
  wmi::AutoRef<AbstractEventProcessor>::Release(&v36);
  wmi::ScopeGuardImpl0<long (*)(void)>::~ScopeGuardImpl0<long (*)(void)>(v37);
}

```

## disassembly

```asm
0x1800052cc  mov     [rsp-8+arg_18], rbx
0x1800052d1  push    rbp
0x1800052d2  push    rsi
0x1800052d3  push    rdi
0x1800052d4  push    r12
0x1800052d6  push    r13
0x1800052d8  push    r14
0x1800052da  push    r15
0x1800052dc  lea     rbp, [rsp-0A0h]
0x1800052e4  sub     rsp, 1A0h
0x1800052eb  mov     rax, cs:__security_cookie
0x1800052f2  xor     rax, rsp
0x1800052f5  mov     [rbp+0D0h+var_38], rax
0x1800052fc  mov     rsi, r8
0x1800052ff  mov     r13, rdx
0x180005302  mov     r12, rcx
0x180005305  call    ?WaitForInit@CollectorService@@AEAAXXZ; CollectorService::WaitForInit(void)
0x18000530a  xor     ecx, ecx; BindingHandle
0x18000530c  call    cs:__imp_RpcImpersonateClient
0x180005312  mov     ebx, eax
0x180005314  xor     edi, edi
0x180005316  test    eax, eax
0x180005318  jz      loc_1800053A5
0x18000531e  lea     rcx, WPP_GLOBAL_Control
0x180005325  mov     r10, cs:WPP_GLOBAL_Control
0x18000532c  cmp     r10, rcx
0x18000532f  jz      short loc_180005355
0x180005331  test    byte ptr [r10+1Ch], 10h
0x180005336  jz      short loc_180005355
0x180005338  cmp     byte ptr [r10+19h], 2
0x18000533d  jb      short loc_180005355
0x18000533f  lea     edx, [rdi+18h]
0x180005342  mov     r9d, eax
0x180005345  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x18000534c  mov     rcx, [r10+10h]
0x180005350  call    WPP_SF_D
0x180005355  mov     [rbp+0D0h+var_68], dil
0x180005359  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180005360  mov     [rbp+0D0h+var_60], rax
0x180005364  mov     [rbp+0D0h+var_58], rdi
0x180005368  mov     [rbp+0D0h+var_50], rdi
0x18000536f  mov     [rbp+0D0h+var_48], ebx
0x180005375  mov     [rbp+0D0h+var_44], 0FFFFFFFFh
0x18000537f  mov     [rbp+0D0h+var_40], 2BFh
0x180005389  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180005390  mov     [rbp+0D0h+pExceptionObject], rax
0x180005394  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000539b  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x18000539f  call    _CxxThrowException_0
0x1800053a5  mov     rax, cs:__imp_RpcRevertToSelf
0x1800053ac  mov     [rbp+0D0h+var_140], dil
0x1800053b0  mov     [rbp+0D0h+var_138], rax
0x1800053b4  xorps   xmm0, xmm0
0x1800053b7  movups  [rbp+0D0h+var_108], xmm0
0x1800053bb  mov     [rbp+0D0h+var_148], rdi
0x1800053bf  lea     rcx, [rbp+0D0h+var_F0]; this
0x1800053c3  call    ??0_EventSources@@QEAA@XZ; _EventSources::_EventSources(void)
0x1800053c8  nop
0x1800053c9  lea     rax, [r12+18h]
0x1800053ce  mov     [rbp+0D0h+var_118], rax
0x1800053d2  mov     rcx, rax; lpCriticalSection
0x1800053d5  call    cs:__imp_EnterCriticalSection
0x1800053db  nop
0x1800053dc  mov     rdx, r13; unsigned __int16 *
0x1800053df  lea     rcx, [rbp+0D0h+var_130]; this
0x1800053e3  call    ??0SubscriptionConfigReader@@QEAA@PEBGPEAUHKEY__@@0@Z; SubscriptionConfigReader::SubscriptionConfigReader(ushort const *,HKEY__ *,ushort const *)
0x1800053e8  nop
0x1800053e9  mov     ebx, 1
0x1800053ee  mov     [rsp+1D0h+var_190], bl
0x1800053f2  lea     rdx, [rsp+1D0h+var_190]; bool *
0x1800053f7  lea     rcx, [rbp+0D0h+var_130]; this
0x1800053fb  call    ?GetEnabled@SubscriptionConfigReader@@QEBA_NAEA_N@Z; SubscriptionConfigReader::GetEnabled(bool &)
0x180005400  cmp     [rsp+1D0h+var_190], dil
0x180005405  jnz     loc_180005494
0x18000540b  lea     rcx, WPP_GLOBAL_Control
0x180005412  mov     ebx, 10DDh
0x180005417  mov     rax, cs:WPP_GLOBAL_Control
0x18000541e  cmp     rax, rcx
0x180005421  jz      short loc_180005447
0x180005423  test    byte ptr [rax+1Ch], 10h
0x180005427  jz      short loc_180005447
0x180005429  cmp     byte ptr [rax+19h], 2
0x18000542d  jb      short loc_180005447
0x18000542f  mov     edx, 19h
0x180005434  mov     r9d, ebx
0x180005437  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x18000543e  mov     rcx, [rax+10h]
0x180005442  call    WPP_SF_D
0x180005447  mov     [rsp+1D0h+var_180], dil
0x18000544c  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180005453  mov     [rsp+1D0h+var_178], rax
0x180005458  mov     [rsp+1D0h+var_170], rdi
0x18000545d  mov     [rsp+1D0h+var_168], rdi
0x180005462  mov     [rsp+1D0h+var_160], ebx
0x180005466  mov     [rsp+1D0h+var_15C], 0FFFFFFFFh
0x18000546e  mov     [rsp+1D0h+var_158], 2D5h
0x180005476  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000547d  mov     [rsp+1D0h+var_188], rax
0x180005482  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180005489  lea     rcx, [rsp+1D0h+var_188]; pExceptionObject
0x18000548e  call    _CxxThrowException_0
0x180005494  mov     ecx, 20h ; ' '; dwBytes
0x180005499  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000549e  mov     [rbp+0D0h+var_150], rax
0x1800054a2  test    rax, rax
0x1800054a5  jz      short loc_1800054C8
0x1800054a7  mov     [rsp+1D0h+var_1A0], bl; bool
0x1800054ab  mov     [rsp+1D0h+var_1A8], bl; bool
0x1800054af  mov     byte ptr [rsp+1D0h+phkResult], bl; bool
0x1800054b3  lea     r9, [rbp+0D0h+var_108]; struct tag_EcRpcMetadataPropertyList *
0x1800054b7  mov     r8, rsi; unsigned __int16 *
0x1800054ba  lea     rdx, [rbp+0D0h+var_130]; struct SubscriptionConfigReader *
0x1800054be  mov     rcx, rax; this
0x1800054c1  call    ??0SubscriptionConfigSnapshot@@QEAA@AEBVSubscriptionConfigReader@@PEBGAEAUtag_EcRpcMetadataPropertyList@@_N33@Z; SubscriptionConfigSnapshot::SubscriptionConfigSnapshot(SubscriptionConfigReader const &,ushort const *,tag_EcRpcMetadataPropertyList &,bool,bool,bool)
0x1800054c6  jmp     short loc_1800054CB
0x1800054c8  mov     rax, rdi
0x1800054cb  mov     rdx, rax
0x1800054ce  lea     rcx, [rbp+0D0h+var_148]
0x1800054d2  call    ??4?$AutoRef@VSubscriptionConfigSnapshot@@@wmi@@QEAAAEAV01@PEAVSubscriptionConfigSnapshot@@@Z; wmi::AutoRef<SubscriptionConfigSnapshot>::operator=(SubscriptionConfigSnapshot *)
0x1800054d7  mov     dword ptr [rbp+0D0h+var_150], edi
0x1800054da  lea     r9, [rbp+0D0h+var_150]; unsigned int *
0x1800054de  lea     r8, ?EnumNameValueSubscriptionType@@3PAU_ENUM_NAMEVALUE_PAIR@@A; struct _ENUM_NAMEVALUE_PAIR *
0x1800054e5  lea     rdx, aSubscriptionty; "SubscriptionType"
0x1800054ec  lea     rcx, [rbp+0D0h+var_130]; this
0x1800054f0  call    ?GetRegEnumValue@ConfigBase@@IEBA_NPEBGPEAU_ENUM_NAMEVALUE_PAIR@@AEAK@Z; ConfigBase::GetRegEnumValue(ushort const *,_ENUM_NAMEVALUE_PAIR *,ulong &)
0x1800054f5  test    al, al
0x1800054f7  jz      loc_18000575C
0x1800054fd  cmp     dword ptr [rbp+0D0h+var_150], edi
0x180005500  jnz     loc_18000575C
0x180005506  test    rsi, rsi
0x180005509  jz      loc_180005596
0x18000550f  lea     rcx, WPP_GLOBAL_Control
0x180005516  mov     ebx, 57h ; 'W'
0x18000551b  mov     rax, cs:WPP_GLOBAL_Control
0x180005522  cmp     rax, rcx
0x180005525  jz      short loc_180005549
0x180005527  test    byte ptr [rax+1Ch], 10h
0x18000552b  jz      short loc_180005549
0x18000552d  cmp     byte ptr [rax+19h], 2
0x180005531  jb      short loc_180005549
0x180005533  lea     edx, [rbx-3Dh]
0x180005536  mov     r9d, ebx
0x180005539  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180005540  mov     rcx, [rax+10h]
0x180005544  call    WPP_SF_D
0x180005549  mov     [rsp+1D0h+var_180], dil
0x18000554e  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x180005555  mov     [rsp+1D0h+var_178], rax
0x18000555a  mov     [rsp+1D0h+var_170], rdi
0x18000555f  mov     [rsp+1D0h+var_168], rdi
0x180005564  mov     [rsp+1D0h+var_160], ebx
0x180005568  mov     [rsp+1D0h+var_15C], 0FFFFFFFFh
0x180005570  mov     [rsp+1D0h+var_158], 2E7h
0x180005578  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000557f  mov     [rsp+1D0h+var_188], rax
0x180005584  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000558b  lea     rcx, [rsp+1D0h+var_188]; pExceptionObject
0x180005590  call    _CxxThrowException_0
0x180005596  mov     r14b, bl
0x180005599  mov     [rbp+0D0h+var_58], 7
0x1800055a1  mov     [rbp+0D0h+var_60], rdi
0x1800055a5  mov     word ptr [rbp+0D0h+pExceptionObject], di
0x1800055a9  mov     edx, 30h ; '0'
0x1800055ae  lea     rcx, [rbp+0D0h+pExceptionObject]
0x1800055b2  call    ?reserve@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::reserve(unsigned __int64)
0x1800055b7  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800055be  lea     rcx, [rbp+0D0h+pExceptionObject]
0x1800055c2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800055c7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800055cb  mov     rax, rdi
0x1800055ce  mov     rcx, [rbp+0D0h+var_60]
0x1800055d2  sub     rax, rcx
0x1800055d5  cmp     rax, rbx
0x1800055d8  jbe     loc_180005ABD
0x1800055de  lea     r15, [rcx+1]
0x1800055e2  xor     r8d, r8d
0x1800055e5  mov     rdx, r15
0x1800055e8  lea     rcx, [rbp+0D0h+pExceptionObject]
0x1800055ec  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800055f1  test    al, al
0x1800055f3  jz      short loc_180005626
0x1800055f5  mov     rcx, [rbp+0D0h+var_60]
0x1800055f9  lea     rax, [rbp+0D0h+pExceptionObject]
0x1800055fd  cmp     [rbp+0D0h+var_58], 8
0x180005602  cmovnb  rax, [rbp+0D0h+pExceptionObject]
0x180005607  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x18000560d  lea     rcx, [rbp+0D0h+pExceptionObject]
0x180005611  cmp     [rbp+0D0h+var_58], 8
0x180005616  cmovnb  rcx, [rbp+0D0h+pExceptionObject]
0x18000561b  mov     [rbp+0D0h+var_60], r15
0x18000561f  xor     eax, eax
0x180005621  mov     [rcx+r15*2], ax
0x180005626  lea     rdx, aSubscriptions_0; "Subscriptions"
0x18000562d  lea     rcx, [rbp+0D0h+pExceptionObject]
0x180005631  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180005636  mov     rax, [rbp+0D0h+var_60]
0x18000563a  sub     rdi, rax
0x18000563d  cmp     rdi, rbx
0x180005640  jbe     loc_180005ABD
0x180005646  lea     rdi, [rax+1]
0x18000564a  xor     r8d, r8d
0x18000564d  mov     rdx, rdi
0x180005650  lea     rcx, [rbp+0D0h+pExceptionObject]
0x180005654  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180005659  xor     r15d, r15d
0x18000565c  test    al, al
0x18000565e  jz      short loc_18000568F
0x180005660  mov     rcx, [rbp+0D0h+var_60]
0x180005664  lea     rax, [rbp+0D0h+pExceptionObject]
0x180005668  cmp     [rbp+0D0h+var_58], 8
0x18000566d  cmovnb  rax, [rbp+0D0h+pExceptionObject]
0x180005672  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x180005678  lea     rcx, [rbp+0D0h+pExceptionObject]
0x18000567c  cmp     [rbp+0D0h+var_58], 8
0x180005681  cmovnb  rcx, [rbp+0D0h+pExceptionObject]
0x180005686  mov     [rbp+0D0h+var_60], rdi
0x18000568a  mov     [rcx+rdi*2], r15w
0x18000568f  mov     rdx, r13
0x180005692  lea     rcx, [rbp+0D0h+pExceptionObject]
0x180005696  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000569b  mov     [rbp+0D0h+var_150], r15
0x18000569f  lea     rdx, [rbp+0D0h+pExceptionObject]
0x1800056a3  cmp     [rbp+0D0h+var_58], 8
0x1800056a8  cmovnb  rdx, [rbp+0D0h+pExceptionObject]; lpSubKey
0x1800056ad  lea     rax, [rbp+0D0h+var_150]
0x1800056b1  mov     [rsp+1D0h+phkResult], rax; phkResult
0x1800056b6  mov     r9d, 2001Fh; samDesired
0x1800056bc  xor     r8d, r8d; ulOptions
0x1800056bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800056c6  call    cs:__imp_RegOpenKeyExW
0x1800056cc  mov     edi, eax
0x1800056ce  test    eax, eax
0x1800056d0  jz      loc_1800057ED
0x1800056d6  lea     rcx, WPP_GLOBAL_Control
0x1800056dd  mov     r10, cs:WPP_GLOBAL_Control
0x1800056e4  cmp     r10, rcx
0x1800056e7  jz      short loc_18000570F
0x1800056e9  test    byte ptr [r10+1Ch], 10h
0x1800056ee  jz      short loc_18000570F
0x1800056f0  cmp     byte ptr [r10+19h], 2
0x1800056f5  jb      short loc_18000570F
0x1800056f7  mov     edx, 1Ch
0x1800056fc  mov     r9d, eax
0x1800056ff  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180005706  mov     rcx, [r10+10h]
0x18000570a  call    WPP_SF_D
0x18000570f  mov     [rsp+1D0h+var_180], r15b
0x180005714  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x18000571b  mov     [rsp+1D0h+var_178], rax
0x180005720  mov     [rsp+1D0h+var_170], r15
0x180005725  mov     [rsp+1D0h+var_168], r15
0x18000572a  mov     [rsp+1D0h+var_160], edi
0x18000572e  mov     [rsp+1D0h+var_15C], 0FFFFFFFFh
0x180005736  mov     [rsp+1D0h+var_158], 308h
0x18000573e  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180005745  mov     [rsp+1D0h+var_188], rax
0x18000574a  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180005751  lea     rcx, [rsp+1D0h+var_188]; pExceptionObject
0x180005756  call    _CxxThrowException_0
0x18000575c  mov     r14b, dil
0x18000575f  test    rsi, rsi
0x180005762  jnz     loc_180005599
0x180005768  lea     rcx, WPP_GLOBAL_Control
0x18000576f  lea     ebx, [rsi+57h]
0x180005772  mov     rax, cs:WPP_GLOBAL_Control
0x180005779  cmp     rax, rcx
0x18000577c  jz      short loc_1800057A0
0x18000577e  test    byte ptr [rax+1Ch], 10h
0x180005782  jz      short loc_1800057A0
0x180005784  cmp     byte ptr [rax+19h], 2
0x180005788  jb      short loc_1800057A0
0x18000578a  lea     edx, [rsi+1Bh]
0x18000578d  mov     r9d, ebx
0x180005790  lea     r8, WPP_5c18cd52a7b834922b5057affbfedb5e_Traceguids
0x180005797  mov     rcx, [rax+10h]
0x18000579b  call    WPP_SF_D
0x1800057a0  mov     [rsp+1D0h+var_180], dil
0x1800057a5  lea     rax, aAdminWmiEvents_3; "admin\\wmi\\events\\forwarding\\collect"...
0x1800057ac  mov     [rsp+1D0h+var_178], rax
0x1800057b1  mov     [rsp+1D0h+var_170], rdi
0x1800057b6  mov     [rsp+1D0h+var_168], rdi
0x1800057bb  mov     [rsp+1D0h+var_160], ebx
0x1800057bf  mov     [rsp+1D0h+var_15C], 0FFFFFFFFh
0x1800057c7  mov     [rsp+1D0h+var_158], 2EEh
0x1800057cf  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800057d6  mov     [rsp+1D0h+var_188], rax
0x1800057db  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x1800057e2  lea     rcx, [rsp+1D0h+var_188]; pExceptionObject
0x1800057e7  call    _CxxThrowException_0
0x1800057ed  lea     rcx, [rbp+0D0h+var_150]; this
0x1800057f1  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800057f6  test    r14b, r14b
0x1800057f9  jnz     loc_1800058A0
0x1800057ff  xor     r8d, r8d; bool
0x180005802  lea     rdx, [rbp+0D0h+var_F0]; struct _EventSources *
0x180005806  lea     rcx, [rbp+0D0h+var_130]; this
0x18000580a  call    ?GetEventSources@SubscriptionConfigReader@@QEBA_NAEAU_EventSources@@_N@Z; SubscriptionConfigReader::GetEventSources(_EventSources &,bool)
0x18000580f  test    al, al
0x180005811  jnz     loc_1800058A0
0x180005817  lea     rcx, WPP_GLOBAL_Control
  ... truncated ...
```
