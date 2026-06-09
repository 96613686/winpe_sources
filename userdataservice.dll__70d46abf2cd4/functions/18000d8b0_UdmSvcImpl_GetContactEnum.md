# UdmSvcImpl_GetContactEnum

- ea: `0x18000d8b0`
- end: `0x18000def3`
- name: `UdmSvcImpl_GetContactEnum`
- size: `1603`
- prototype: `__int64 __fastcall(struct ServiceDataSession *, struct UdmContactQueryOptions *, unsigned int, unsigned int *, __int64, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800054c0`
- `0x180008380`
- `0x180008ee8`
- `0x180008f0c`
- `0x180008f58`
- `0x18000a530`
- `0x18000a780`
- `0x18000b620`
- `0x18000c740`
- `0x18000d8b0`
- `0x18001f648`
- `0x180021aa4`
- `0x18006194c`
- `0x1800669a8`
- `0x18007f77c`
- `0x1800810a8`
- `0x1800977c4`
- `0x1800a5630`
- `0x180123d80`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x18000da05`
- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x18000da05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d8fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d8fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dc77`

## string_xrefs

- `0x18000de33`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000dc22`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x18000dc40`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x18000dc82`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x18000dcdf`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x18000ddd8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x18000ddfe`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`

## pseudocode

```c
__int64 __fastcall UdmSvcImpl_GetContactEnum(
        struct ServiceDataSession *a1,
        struct UdmContactQueryOptions *a2,
        unsigned int a3,
        unsigned int *a4,
        struct ServiceGenericEnumBase **a5,
        unsigned int *a6)
{
  struct ServiceGenericEnumBase **v6; // r14
  unsigned __int64 v11; // rdx
  void **v12; // rcx
  int v13; // eax
  __int64 v14; // r8
  unsigned int v15; // ebx
  int v16; // eax
  __int64 v17; // r8
  bool v18; // zf
  int v19; // r14d
  ServiceDataSession *v20; // rsi
  int updated; // eax
  int v22; // eax
  struct ServiceGenericEnumBase *v23; // rsi
  __int64 v24; // xmm0_8
  int v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // r9
  __int64 v32; // r8
  int v33; // r9d
  __int64 *v34; // rax
  int v35; // eax
  __int64 v36; // r9
  struct ServiceGenericEnumBase *v37; // [rsp+30h] [rbp-49h] BYREF
  __int64 v38; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v39[2]; // [rsp+40h] [rbp-39h] BYREF
  void **v40; // [rsp+50h] [rbp-29h] BYREF
  ServiceDataSession *v41; // [rsp+58h] [rbp-21h] BYREF
  int v42; // [rsp+70h] [rbp-9h]
  __int64 v43; // [rsp+78h] [rbp-1h] BYREF
  __int64 v44; // [rsp+80h] [rbp+7h] BYREF
  struct ServiceDataSession *v45; // [rsp+88h] [rbp+Fh] BYREF

  v6 = a5;
  v39[0] = a5;
  *a5 = 0;
  *a6 = -1;
  EnterCriticalSection(&g_sessionListLock);
  if ( !xmmword_18015D790
    || (v11 = (0xC4CEB9FE1A85EC53uLL
             * ((0xFF51AFD7ED558CCDuLL * ((unsigned __int64)a1 ^ ((unsigned __int64)a1 >> 33)))
              ^ ((0xFF51AFD7ED558CCDuLL * ((unsigned __int64)a1 ^ ((unsigned __int64)a1 >> 33))) >> 33)))
            ^ ((0xC4CEB9FE1A85EC53uLL
              * ((0xFF51AFD7ED558CCDuLL * ((unsigned __int64)a1 ^ ((unsigned __int64)a1 >> 33)))
               ^ ((0xFF51AFD7ED558CCDuLL * ((unsigned __int64)a1 ^ ((unsigned __int64)a1 >> 33))) >> 33))) >> 33),
        (v12 = (void **)*((_QWORD *)xmmword_18015D790 + 2 * (v11 & ((8LL << word_18015D7A0) - 1)))) == 0) )
  {
LABEL_40:
    LeaveCriticalSection(&g_sessionListLock);
    Log_HREvent(
      2147942406LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      2282);
    return 2147942406LL;
  }
  while ( 1 )
  {
    if ( v12 == **((void ****)xmmword_18015D790 + 2 * (v11 & ((8LL << word_18015D7A0) - 1)) + 1) )
      goto LABEL_40;
    if ( (unsigned __int64)v12[2] >= v11 )
    {
      if ( (unsigned __int64)v12[2] > v11 )
        goto LABEL_40;
      if ( a1 == v12[3] )
        break;
    }
    v12 = (void **)*v12;
  }
  if ( v12 == &g_sessionList )
    goto LABEL_40;
  if ( a1 )
    (*(void (__fastcall **)(struct ServiceDataSession *))(*(_QWORD *)a1 + 8LL))(a1);
  v45 = a1;
  LeaveCriticalSection(&g_sessionListLock);
  v41 = 0;
  v40 = &ContactOperationContext::`vftable';
  v43 = 0;
  v42 = 0;
  v44 = 0;
  v13 = UnistoreOperationContext::Initialize((UnistoreOperationContext *)&v40, a1);
  v15 = v13;
  if ( v13 < 0 )
  {
    Log_HREvent_16((unsigned int)v13, 1, v14, 13);
LABEL_44:
    Log_HREvent_17(v15, 1, v32, 9);
    Log_HREvent(
      v15,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      2285);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v44);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v43);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v41);
    goto LABEL_45;
  }
  v38 = 0;
  v16 = POutlookAppManager_CreateInstance(&v38);
  v15 = v16;
  if ( v16 < 0 )
  {
    v31 = 16;
LABEL_42:
    Log_HREvent_16((unsigned int)v16, 1, v17, v31);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    goto LABEL_44;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 32LL))(v38, &v44);
  v15 = v16;
  if ( v16 < 0 )
  {
    v31 = 17;
    goto LABEL_42;
  }
  v42 = 1;
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  v18 = *((_DWORD *)a2 + 1) == 458754;
  v37 = 0;
  if ( !v18 )
  {
    if ( *((_DWORD *)a2 + 2) || *(_DWORD *)a2 || *((_DWORD *)a2 + 1) )
    {
      v34 = tlx::replace<ServiceGenericEnumBase,&void tlx::_delete<ServiceGenericEnumBase>(ServiceGenericEnumBase *)>((__int64 *)&v37);
      v35 = ContactEnum::Create(a1, a2, a3, a4, a6, (struct ServiceGenericEnumBase **)v34);
      v15 = v35;
      if ( v35 >= 0 )
      {
LABEL_65:
        v23 = v37;
        goto LABEL_27;
      }
      v29 = 2319;
    }
    else
    {
      v35 = UnistoreOperationContext::ValidateCallerSecurity(&v40, 1, 0);
      v15 = v35;
      if ( v35 < 0 )
      {
        v29 = 2301;
      }
      else
      {
        v37 = 0;
        v35 = AggregateEnum::Create(a1, a2, a3, a4, &v37);
        v15 = v35;
        if ( v35 >= 0 )
          goto LABEL_65;
        v29 = 2308;
      }
    }
    v30 = (unsigned int)v35;
    goto LABEL_38;
  }
  if ( !v41 )
    goto LABEL_25;
  v19 = ((__int64 (__fastcall *)(void ***, __int64))v40[9])(&v40, 1);
  if ( v19 )
  {
    v20 = v41;
    updated = ServiceDataSession::EnsureIntializedSecurityAndAppInfo(v41);
    v15 = updated;
    if ( updated < 0 )
    {
      v36 = 1255;
    }
    else
    {
      v22 = *((_DWORD *)v20 + 447);
      if ( (v22 & v19) == 0 )
      {
        v15 = -2147024891;
        goto LABEL_23;
      }
      if ( (*((_DWORD *)v20 + 449) & v22 & v19) != 0 )
        goto LABEL_22;
      updated = ServiceDataSession::_UpdateSecurityFlagsForPrivacy(v20, 0, v19);
      v15 = updated;
      if ( updated >= 0 )
      {
        v33 = *((_DWORD *)v20 + 447);
        if ( (v33 & *((_DWORD *)v20 + 449) & v19) == 0 )
        {
          if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x80u) != 0 )
            McTemplateU0qqq_EventWriteTransfer(
              *((_DWORD *)v20 + 449),
              (unsigned int)ClientPrivacyCapabilityFailed,
              v19,
              v33,
              *((_DWORD *)v20 + 449));
          v15 = -2147467260;
          goto LABEL_23;
        }
LABEL_22:
        v15 = 0;
LABEL_23:
        if ( (v15 & 0x80000000) == 0 )
          goto LABEL_24;
        Log_HREvent(
          v15,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
          2290);
        PoomOperationContext::~PoomOperationContext((PoomOperationContext *)&v40);
LABEL_45:
        if ( a1 )
          (*(void (__fastcall **)(struct ServiceDataSession *))(*(_QWORD *)a1 + 16LL))(a1);
        return v15;
      }
      v36 = 1265;
    }
    Log_HREvent(
      (unsigned int)updated,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      v36);
    goto LABEL_23;
  }
LABEL_24:
  v6 = (struct ServiceGenericEnumBase **)v39[0];
LABEL_25:
  v37 = 0;
  v23 = (struct ServiceGenericEnumBase *)operator new(0xF8u);
  if ( !v23 )
  {
    v15 = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      1476);
LABEL_37:
    v29 = 2297;
    v30 = v15;
LABEL_38:
    Log_HREvent(
      v30,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      v29);
    tlx::auto_xxx<ChatEnumBase *,void (*)(ChatEnumBase *),&void tlx::_delete<ChatEnumBase>(ChatEnumBase *),0>::_Delete(&v37);
    PoomOperationContext::~PoomOperationContext((PoomOperationContext *)&v40);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v45);
    return v15;
  }
  v39[0] = 29;
  v39[1] = &s_Contact_PropMap;
  PoomEnumeratorBase::PoomEnumeratorBase(v23, v39);
  *((_QWORD *)v23 + 17) = 0;
  *((_QWORD *)v23 + 21) = 0;
  *((_DWORD *)v23 + 40) = 0;
  *((_QWORD *)v23 + 22) = 0;
  *((_QWORD *)v23 + 16) = &ContactOperationContext::`vftable';
  *(_QWORD *)v23 = &AggregateComponentEnum::`vftable';
  utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>((char *)v23 + 184);
  v24 = *(_QWORD *)a2;
  v25 = *((_DWORD *)a2 + 2);
  *((_QWORD *)v23 + 28) = 0;
  *((_QWORD *)v23 + 29) = v24;
  *((_DWORD *)v23 + 60) = v25;
  v26 = (*(__int64 (__fastcall **)(struct ServiceGenericEnumBase *, struct ServiceDataSession *, _QWORD, unsigned int *))(*(_QWORD *)v23 + 152LL))(
          v23,
          a1,
          a3,
          a4);
  v15 = v26;
  if ( v26 < 0 )
  {
    Log_HREvent(
      (unsigned int)v26,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      1477);
    tlx::_delete<AggregateComponentEnum>((__int64)v23);
    goto LABEL_37;
  }
LABEL_27:
  v27 = v44;
  v37 = 0;
  *v6 = v23;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  if ( v41 )
    (*(void (__fastcall **)(ServiceDataSession *))(*(_QWORD *)v41 + 16LL))(v41);
  if ( a1 )
    (*(void (__fastcall **)(struct ServiceDataSession *))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18000d8b0  mov     [rsp-8+arg_0], rbx
0x18000d8b5  push    rbp
0x18000d8b6  push    rsi
0x18000d8b7  push    rdi
0x18000d8b8  push    r12
0x18000d8ba  push    r13
0x18000d8bc  push    r14
0x18000d8be  push    r15
0x18000d8c0  lea     rbp, [rsp-17h]
0x18000d8c5  sub     rsp, 90h
0x18000d8cc  mov     r14, [rbp+47h+arg_20]
0x18000d8d0  mov     rdi, rcx
0x18000d8d3  mov     rsi, [rbp+47h+arg_28]
0x18000d8d7  lea     rcx, ?g_sessionListLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000d8de  mov     r13, r9
0x18000d8e1  mov     [rbp+47h+var_80], r14
0x18000d8e5  mov     r12d, r8d
0x18000d8e8  mov     r15, rdx
0x18000d8eb  mov     qword ptr [r14], 0
0x18000d8f2  xor     ebx, ebx
0x18000d8f4  mov     dword ptr [rsi], 0FFFFFFFFh
0x18000d8fa  call    cs:__imp_EnterCriticalSection
0x18000d900  mov     r8, qword ptr cs:xmmword_18015D790
0x18000d907  test    r8, r8
0x18000d90a  jz      loc_18000DC70
0x18000d910  mov     rcx, 0FF51AFD7ED558CCDh
0x18000d91a  mov     rax, rdi
0x18000d91d  shr     rax, 21h
0x18000d921  xor     rax, rdi
0x18000d924  imul    rax, rcx
0x18000d928  mov     rcx, rax
0x18000d92b  shr     rcx, 21h
0x18000d92f  xor     rcx, rax
0x18000d932  mov     rax, 0C4CEB9FE1A85EC53h
0x18000d93c  imul    rcx, rax
0x18000d940  lea     eax, [rbx+8]
0x18000d943  mov     rdx, rcx
0x18000d946  shr     rdx, 21h
0x18000d94a  xor     rdx, rcx
0x18000d94d  mov     cl, byte ptr cs:word_18015D7A0
0x18000d953  shl     rax, cl
0x18000d956  dec     rax
0x18000d959  and     rax, rdx
0x18000d95c  add     rax, rax
0x18000d95f  mov     rcx, [r8+rax*8]
0x18000d963  test    rcx, rcx
0x18000d966  jz      loc_18000DC70
0x18000d96c  mov     rax, [r8+rax*8+8]
0x18000d971  mov     r8, [rax]
0x18000d974  cmp     rcx, r8
0x18000d977  jz      loc_18000DC70
0x18000d97d  cmp     [rcx+10h], rdx
0x18000d981  jb      short loc_18000D98F
0x18000d983  ja      loc_18000DC70
0x18000d989  cmp     rdi, [rcx+18h]
0x18000d98d  jz      short loc_18000D994
0x18000d98f  mov     rcx, [rcx]
0x18000d992  jmp     short loc_18000D974
0x18000d994  lea     rax, ?g_sessionList@@3V?$unordered_set@PEAVServiceDataSession@@U?$hash@PEAVServiceDataSession@@@utl@@U?$equal_to@PEAVServiceDataSession@@@3@V?$allocator@PEAVServiceDataSession@@@3@@utl@@A; utl::unordered_set<ServiceDataSession *,utl::hash<ServiceDataSession *>,utl::equal_to<ServiceDataSession *>,utl::allocator<ServiceDataSession *>> g_sessionList
0x18000d99b  cmp     rcx, rax
0x18000d99e  jz      loc_18000DC70
0x18000d9a4  test    rdi, rdi
0x18000d9a7  jz      short loc_18000D9B8
0x18000d9a9  mov     rax, [rdi]
0x18000d9ac  mov     rcx, rdi
0x18000d9af  mov     rax, [rax+8]
0x18000d9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9b8  lea     rcx, ?g_sessionListLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000d9bf  mov     [rbp+47h+var_38], rdi
0x18000d9c3  call    cs:__imp_LeaveCriticalSection
0x18000d9c9  lea     rax, ??_7ContactOperationContext@@6B@; const ContactOperationContext::`vftable'
0x18000d9d0  mov     [rbp+47h+var_68], rbx
0x18000d9d4  mov     rdx, rdi; struct ServiceDataSession *
0x18000d9d7  mov     [rbp+47h+var_70], rax
0x18000d9db  lea     rcx, [rbp+47h+var_70]; this
0x18000d9df  mov     [rbp+47h+var_48], rbx
0x18000d9e3  mov     [rbp+47h+var_50], ebx
0x18000d9e6  mov     [rbp+47h+var_40], rbx
0x18000d9ea  call    ?Initialize@UnistoreOperationContext@@UEAAJPEAVServiceDataSession@@@Z; UnistoreOperationContext::Initialize(ServiceDataSession *)
0x18000d9ef  mov     ebx, eax
0x18000d9f1  test    eax, eax
0x18000d9f3  js      loc_18000DEBE
0x18000d9f9  lea     rcx, [rbp+47h+var_88]
0x18000d9fd  mov     [rbp+47h+var_88], 0
0x18000da05  call    cs:__imp_POutlookAppManager_CreateInstance
0x18000da0b  mov     ebx, eax
0x18000da0d  test    eax, eax
0x18000da0f  js      loc_18000DD82
0x18000da15  mov     rcx, [rbp+47h+var_88]
0x18000da19  lea     rdx, [rbp+47h+var_40]
0x18000da1d  mov     rax, [rcx]
0x18000da20  mov     rax, [rax+20h]
0x18000da24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da29  mov     ebx, eax
0x18000da2b  test    eax, eax
0x18000da2d  js      loc_18000DCA2
0x18000da33  mov     rcx, [rbp+47h+var_88]
0x18000da37  xor     ebx, ebx
0x18000da39  mov     [rbp+47h+var_50], 1
0x18000da40  test    rcx, rcx
0x18000da43  jz      short loc_18000DA51
0x18000da45  mov     rax, [rcx]
0x18000da48  mov     rax, [rax+10h]
0x18000da4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da51  cmp     dword ptr [r15+4], 70002h
0x18000da59  mov     rcx, rbx
0x18000da5c  mov     [rbp+47h+var_90], rbx
0x18000da60  jnz     loc_18000DD8D
0x18000da66  cmp     [rbp+47h+var_68], rbx
0x18000da6a  jz      short loc_18000DAD1
0x18000da6c  mov     rax, [rbp+47h+var_70]
0x18000da70  lea     rcx, [rbp+47h+var_70]
0x18000da74  mov     edx, 1
0x18000da79  mov     rax, [rax+48h]
0x18000da7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da82  mov     r14d, eax
0x18000da85  test    eax, eax
0x18000da87  jz      short loc_18000DAC9
0x18000da89  mov     rsi, [rbp+47h+var_68]
0x18000da8d  mov     rcx, rsi; this
0x18000da90  call    ?EnsureIntializedSecurityAndAppInfo@ServiceDataSession@@AEAAJXZ; ServiceDataSession::EnsureIntializedSecurityAndAppInfo(void)
0x18000da95  mov     ebx, eax
0x18000da97  test    eax, eax
0x18000da99  js      loc_18000DEB3
0x18000da9f  mov     eax, [rsi+6FCh]
0x18000daa5  test    r14d, eax
0x18000daa8  jz      loc_18000DED3
0x18000daae  and     eax, [rsi+704h]
0x18000dab4  test    r14d, eax
0x18000dab7  jz      loc_18000DD2A
0x18000dabd  xor     ebx, ebx
0x18000dabf  test    ebx, ebx
0x18000dac1  js      loc_18000DDF8
0x18000dac7  xor     ebx, ebx
0x18000dac9  mov     rcx, [rbp+47h+var_90]
0x18000dacd  mov     r14, [rbp+47h+var_80]
0x18000dad1  test    rcx, rcx
0x18000dad4  jz      short loc_18000DAE7
0x18000dad6  mov     rax, [rcx]
0x18000dad9  mov     edx, 1
0x18000dade  mov     rax, [rax+18h]
0x18000dae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dae7  mov     ecx, 0F8h; Size
0x18000daec  mov     [rbp+47h+var_90], rbx
0x18000daf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000daf5  mov     rsi, rax
0x18000daf8  test    rax, rax
0x18000dafb  jz      loc_18000DC1D
0x18000db01  lea     rax, ?s_Contact_PropMap@@3QBUUdmPoomPropIdMap@@B; UdmPoomPropIdMap const near * const s_Contact_PropMap
0x18000db08  mov     [rbp+47h+var_80], 1Dh
0x18000db10  lea     rdx, [rbp+47h+var_80]
0x18000db14  mov     [rbp+47h+var_78], rax
0x18000db18  mov     rcx, rsi
0x18000db1b  call    ??0PoomEnumeratorBase@@IEAA@AEBV?$Vector@$$CBUUdmPoomPropIdMap@@@Udm@@@Z; PoomEnumeratorBase::PoomEnumeratorBase(Udm::Vector<UdmPoomPropIdMap const> const &)
0x18000db20  mov     [rsi+88h], rbx
0x18000db27  lea     rax, ??_7ContactOperationContext@@6B@; const ContactOperationContext::`vftable'
0x18000db2e  mov     [rsi+0A8h], rbx
0x18000db35  lea     rcx, [rsi+0B8h]
0x18000db3c  mov     [rsi+0A0h], ebx
0x18000db42  mov     [rsi+0B0h], rbx
0x18000db49  mov     [rsi+80h], rax
0x18000db50  lea     rax, ??_7AggregateComponentEnum@@6B@; const AggregateComponentEnum::`vftable'
0x18000db57  mov     [rsi], rax
0x18000db5a  call    ??0?$unordered_map@W4_SebiEventType@@U_GUID@@U?$hash@W4_SebiEventType@@@utl@@U?$equal_to@W4_SebiEventType@@@4@V?$allocator@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@@4@@utl@@QEAA@XZ; utl::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>(void)
0x18000db5f  movsd   xmm0, qword ptr [r15]
0x18000db64  mov     r9, r13
0x18000db67  mov     eax, [r15+8]
0x18000db6b  mov     r8d, r12d
0x18000db6e  mov     [rsi+0E0h], rbx
0x18000db75  mov     rdx, rdi
0x18000db78  movsd   qword ptr [rsi+0E8h], xmm0
0x18000db80  mov     rcx, rsi
0x18000db83  mov     [rsi+0F0h], eax
0x18000db89  mov     rax, [rsi]
0x18000db8c  mov     rax, [rax+98h]
0x18000db93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db98  mov     ebx, eax
0x18000db9a  test    eax, eax
0x18000db9c  js      loc_18000DDD2
0x18000dba2  mov     rcx, [rbp+47h+var_40]
0x18000dba6  mov     [rbp+47h+var_90], 0
0x18000dbae  mov     [r14], rsi
0x18000dbb1  test    rcx, rcx
0x18000dbb4  jz      short loc_18000DBC2
0x18000dbb6  mov     rax, [rcx]
0x18000dbb9  mov     rax, [rax+10h]
0x18000dbbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc2  mov     rcx, [rbp+47h+var_48]
0x18000dbc6  test    rcx, rcx
0x18000dbc9  jz      short loc_18000DBD7
0x18000dbcb  mov     rax, [rcx]
0x18000dbce  mov     rax, [rax+10h]
0x18000dbd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbd7  mov     rcx, [rbp+47h+var_68]
0x18000dbdb  test    rcx, rcx
0x18000dbde  jz      short loc_18000DBEC
0x18000dbe0  mov     rax, [rcx]
0x18000dbe3  mov     rax, [rax+10h]
0x18000dbe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbec  test    rdi, rdi
0x18000dbef  jz      short loc_18000DC00
0x18000dbf1  mov     rax, [rdi]
0x18000dbf4  mov     rcx, rdi
0x18000dbf7  mov     rax, [rax+10h]
0x18000dbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc00  xor     eax, eax
0x18000dc02  mov     rbx, [rsp+0C0h+arg_0]
0x18000dc0a  add     rsp, 90h
0x18000dc11  pop     r15
0x18000dc13  pop     r14
0x18000dc15  pop     r13
0x18000dc17  pop     r12
0x18000dc19  pop     rdi
0x18000dc1a  pop     rsi
0x18000dc1b  pop     rbp
0x18000dc1c  retn
0x18000dc1d  mov     ebx, 8007000Eh
0x18000dc22  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000dc29  mov     ecx, ebx
0x18000dc2b  mov     r9d, 5C4h
0x18000dc31  xor     edx, edx
0x18000dc33  call    Log_HREvent
0x18000dc38  mov     r9d, 8F9h
0x18000dc3e  mov     ecx, ebx
0x18000dc40  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000dc47  mov     edx, 1
0x18000dc4c  call    Log_HREvent
0x18000dc51  lea     rcx, [rbp+47h+var_90]
0x18000dc55  call    ?_Delete@?$auto_xxx@PEAVChatEnumBase@@P6AXPEAV1@@Z$1??$_delete@VChatEnumBase@@@tlx@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ChatEnumBase *,void (*)(ChatEnumBase *),&tlx::_delete<ChatEnumBase>(ChatEnumBase *),0>::_Delete(void)
0x18000dc5a  lea     rcx, [rbp+47h+var_70]; this
0x18000dc5e  call    ??1PoomOperationContext@@QEAA@XZ; PoomOperationContext::~PoomOperationContext(void)
0x18000dc63  lea     rcx, [rbp+47h+var_38]
0x18000dc67  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000dc6c  mov     eax, ebx
0x18000dc6e  jmp     short loc_18000DC02
0x18000dc70  lea     rcx, ?g_sessionListLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000dc77  call    cs:__imp_LeaveCriticalSection
0x18000dc7d  mov     edi, 80070006h
0x18000dc82  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000dc89  mov     ecx, edi
0x18000dc8b  mov     r9d, 8EAh
0x18000dc91  mov     edx, 1
0x18000dc96  call    Log_HREvent
0x18000dc9b  mov     eax, edi
0x18000dc9d  jmp     loc_18000DC02
0x18000dca2  mov     r9d, 11h
0x18000dca8  mov     edx, 1
0x18000dcad  mov     ecx, eax
0x18000dcaf  call    Log_HREvent_16
0x18000dcb4  mov     rcx, [rbp+47h+var_88]
0x18000dcb8  test    rcx, rcx
0x18000dcbb  jz      short loc_18000DCC9
0x18000dcbd  mov     rax, [rcx]
0x18000dcc0  mov     rax, [rax+10h]
0x18000dcc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcc9  mov     edx, 1
0x18000dcce  mov     ecx, ebx
0x18000dcd0  lea     r9d, [rdx+8]
0x18000dcd4  call    Log_HREvent_17
0x18000dcd9  mov     r9d, 8EDh
0x18000dcdf  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000dce6  mov     edx, 1
0x18000dceb  mov     ecx, ebx
0x18000dced  call    Log_HREvent
0x18000dcf2  lea     rcx, [rbp+47h+var_40]
0x18000dcf6  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000dcfb  lea     rcx, [rbp+47h+var_48]
0x18000dcff  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000dd04  lea     rcx, [rbp+47h+var_68]
0x18000dd08  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000dd0d  test    rdi, rdi
0x18000dd10  jz      loc_18000DC6C
0x18000dd16  mov     rcx, [rdi]
0x18000dd19  mov     rax, [rcx+10h]
0x18000dd1d  mov     rcx, rdi
0x18000dd20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd25  jmp     loc_18000DC6C
0x18000dd2a  mov     r8d, r14d; unsigned int
0x18000dd2d  xor     edx, edx; unsigned int
0x18000dd2f  mov     rcx, rsi; this
0x18000dd32  call    ?_UpdateSecurityFlagsForPrivacy@ServiceDataSession@@AEAAJKK@Z; ServiceDataSession::_UpdateSecurityFlagsForPrivacy(ulong,ulong)
0x18000dd37  mov     ebx, eax
0x18000dd39  test    eax, eax
0x18000dd3b  js      loc_18000DE2D
0x18000dd41  mov     ecx, [rsi+704h]
0x18000dd47  mov     eax, ecx
0x18000dd49  mov     r9d, [rsi+6FCh]
0x18000dd50  and     eax, r9d
0x18000dd53  test    r14d, eax
0x18000dd56  jnz     loc_18000DABD
0x18000dd5c  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 80h
0x18000dd63  jz      short loc_18000DD78
0x18000dd65  mov     r8d, r14d
0x18000dd68  mov     dword ptr [rsp+0C0h+var_A0], ecx
0x18000dd6c  lea     rdx, ClientPrivacyCapabilityFailed
0x18000dd73  call    McTemplateU0qqq_EventWriteTransfer
0x18000dd78  mov     ebx, 80004004h
0x18000dd7d  jmp     loc_18000DABF
0x18000dd82  mov     r9d, 10h
0x18000dd88  jmp     loc_18000DCA8
  ... truncated ...
```
