# UdmSvcImpl_GetEmailMailboxEnum

- ea: `0x18000c8e0`
- end: `0x18000cef3`
- name: `UdmSvcImpl_GetEmailMailboxEnum`
- size: `1555`
- prototype: `__int64 __usercall@<rax>(struct ServiceDataSession *@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180008380`
- `0x180008ee8`
- `0x180008f0c`
- `0x180008f58`
- `0x18000a780`
- `0x18000b620`
- `0x18000c740`
- `0x18000c8e0`
- `0x180021930`
- `0x180021aa4`
- `0x1800676b8`
- `0x18007f77c`
- `0x180082ac4`
- `0x1800977c4`
- `0x1800a5630`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x18000ca2c`
- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x18000ca2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c91f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c91f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c9e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c9e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd05`
- `CEMAPI!MAPILogonEx` at `0x18000ca96`
- `CEMAPI!MAPILogonEx` at `0x18000ca96`

## string_xrefs

- `0x18000ce36`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000cd56`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x18000cdec`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`

## pseudocode

```c
__int64 __fastcall UdmSvcImpl_GetEmailMailboxEnum(
        struct ServiceDataSession *a1,
        unsigned int a2,
        __int64 *a3,
        unsigned int a4,
        __int64 a5,
        _QWORD *a6)
{
  _QWORD *v6; // r12
  unsigned int v8; // esi
  unsigned __int64 v11; // rdx
  void **v12; // rcx
  int v13; // eax
  __int64 v14; // r8
  unsigned int v15; // ebx
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  int v19; // r14d
  ServiceDataSession *v20; // rsi
  int updated; // eax
  __int64 v22; // r8
  int v23; // eax
  _QWORD *v25; // rbx
  __int64 v26; // r8
  unsigned int v27; // esi
  __int64 v28; // r8
  __int64 v29; // xmm0_8
  __int64 v30; // r9
  int v31; // eax
  __int64 v32; // r8
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r8
  int v36; // r9d
  __int64 v37; // r9
  __int64 v38; // r9
  __int64 v39; // rcx
  __int64 v40; // [rsp+30h] [rbp-49h] BYREF
  int v41; // [rsp+38h] [rbp-41h]
  _QWORD v42[2]; // [rsp+40h] [rbp-39h] BYREF
  void **v43; // [rsp+50h] [rbp-29h] BYREF
  ServiceDataSession *v44; // [rsp+58h] [rbp-21h]
  int v45; // [rsp+70h] [rbp-9h]
  __int64 v46; // [rsp+78h] [rbp-1h]
  __int64 v47; // [rsp+80h] [rbp+7h] BYREF
  _QWORD v48[7]; // [rsp+88h] [rbp+Fh] BYREF
  struct ServiceDataSession *v49; // [rsp+D0h] [rbp+57h] BYREF
  unsigned int v50; // [rsp+E8h] [rbp+6Fh]

  v50 = a4;
  v6 = a6;
  v8 = a4;
  *a6 = 0;
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
LABEL_46:
    LeaveCriticalSection(&g_sessionListLock);
    Log_HREvent_27(2147942406LL, 1, v33, 2450);
    return 2147942406LL;
  }
  while ( 1 )
  {
    if ( v12 == **((void ****)xmmword_18015D790 + 2 * (v11 & ((8LL << word_18015D7A0) - 1)) + 1) )
      goto LABEL_46;
    if ( (unsigned __int64)v12[2] >= v11 )
    {
      if ( (unsigned __int64)v12[2] > v11 )
        goto LABEL_46;
      if ( a1 == v12[3] )
        break;
    }
    v12 = (void **)*v12;
  }
  if ( v12 == &g_sessionList )
    goto LABEL_46;
  if ( a1 )
    (*(void (__fastcall **)(struct ServiceDataSession *))(*(_QWORD *)a1 + 8LL))(a1);
  v49 = a1;
  LeaveCriticalSection(&g_sessionListLock);
  v44 = 0;
  v43 = &EmailOperationContext::`vftable';
  v46 = 0;
  v45 = 0;
  v47 = 0;
  v48[0] = 0;
  v13 = UnistoreOperationContext::Initialize((UnistoreOperationContext *)&v43, a1);
  v15 = v13;
  if ( v13 < 0 )
  {
    Log_HREvent_16((unsigned int)v13, 1, v14, 13);
LABEL_50:
    Log_HREvent(
      v15,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
      13);
    goto LABEL_51;
  }
  a6 = 0;
  v16 = POutlookAppManager_CreateInstance(&a6);
  v15 = v16;
  if ( v16 < 0 )
  {
    v34 = 16;
LABEL_48:
    Log_HREvent_16((unsigned int)v16, 1, v17, v34);
    if ( a6 )
      (*(void (__fastcall **)(_QWORD *))(*a6 + 16LL))(a6);
    goto LABEL_50;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*a6 + 32LL))(a6, &v47);
  v15 = v16;
  if ( v16 < 0 )
  {
    v34 = 17;
    goto LABEL_48;
  }
  v45 = 1;
  if ( a6 )
    (*(void (__fastcall **)(_QWORD *))(*a6 + 16LL))(a6);
  if ( !v48[0] )
  {
    a6 = 0;
    v18 = MAPILogonEx(0, 0, 0, 0x200000, &a6);
    v15 = v18;
    if ( v18 < 0 )
    {
      v37 = 18;
    }
    else
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*a6)(
              a6,
              &GUID_5675594b_0e92_4117_ae35_434774ec0810,
              v48);
      v15 = v18;
      if ( v18 >= 0 )
      {
        if ( a6 )
          (*(void (__fastcall **)(_QWORD *))(*a6 + 16LL))(a6);
        goto LABEL_21;
      }
      v37 = 20;
    }
    Log_HREvent(
      (unsigned int)v18,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
      v37);
    if ( a6 )
      (*(void (__fastcall **)(_QWORD *))(*a6 + 16LL))(a6);
LABEL_51:
    Log_HREvent_27(v15, 1, v35, 2453);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(v48);
    PoomOperationContext::~PoomOperationContext((PoomOperationContext *)&v43);
LABEL_37:
    if ( a1 )
      (*(void (__fastcall **)(struct ServiceDataSession *))(*(_QWORD *)a1 + 16LL))(a1);
    return v15;
  }
LABEL_21:
  if ( !v44 )
    goto LABEL_41;
  v19 = ((__int64 (__fastcall *)(void ***, bool))v43[9])(&v43, a2 != 0);
  if ( !v19 )
    goto LABEL_41;
  v20 = v44;
  updated = ServiceDataSession::EnsureIntializedSecurityAndAppInfo(v44);
  v15 = updated;
  if ( updated < 0 )
  {
    v38 = 1255;
    goto LABEL_63;
  }
  v23 = *((_DWORD *)v20 + 447);
  if ( (v23 & v19) == 0 )
  {
    v15 = -2147024891;
    goto LABEL_28;
  }
  if ( !a2 || (v19 & v23 & *((_DWORD *)v20 + 449)) != 0 )
    goto LABEL_27;
  updated = ServiceDataSession::_UpdateSecurityFlagsForPrivacy(v20, 0, v19);
  v15 = updated;
  if ( updated < 0 )
  {
    v38 = 1265;
LABEL_63:
    Log_HREvent(
      (unsigned int)updated,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      v38);
    goto LABEL_28;
  }
  v36 = *((_DWORD *)v20 + 447);
  if ( (v36 & *((_DWORD *)v20 + 449) & v19) == 0 )
  {
    if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x80u) != 0 )
      McTemplateU0qqq_EventWriteTransfer(
        *((_DWORD *)v20 + 449),
        (unsigned int)ClientPrivacyCapabilityFailed,
        v19,
        v36,
        *((_DWORD *)v20 + 449));
    v15 = -2147467260;
    goto LABEL_28;
  }
LABEL_27:
  v15 = 0;
LABEL_28:
  if ( (v15 & 0x80000000) != 0 )
  {
    Log_HREvent_27(v15, 1, v22, 2454);
    if ( v48[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v48[0] + 16LL))(v48[0]);
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    if ( v46 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    if ( v44 )
      (*(void (__fastcall **)(ServiceDataSession *))(*(_QWORD *)v44 + 16LL))(v44);
    goto LABEL_37;
  }
  v8 = v50;
LABEL_41:
  a6 = 0;
  v25 = operator new(0xD8u);
  if ( !v25 )
  {
    v27 = -2147024882;
    Log_HREvent_27(2147942414LL, 0, v26, 21);
LABEL_43:
    Log_HREvent_27(v27, 1, v28, 2463);
    tlx::auto_xxx<ChatEnumBase *,void (*)(ChatEnumBase *),&void tlx::_delete<ChatEnumBase>(ChatEnumBase *),0>::_Delete(&a6);
    EmailOperationContext::~EmailOperationContext((EmailOperationContext *)&v43);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v49);
    return v27;
  }
  v29 = *a3;
  v42[1] = &s_EmailMailbox_PropMap;
  v41 = *((_DWORD *)a3 + 2);
  v42[0] = 37;
  v40 = v29;
  StoreEnumeratorBase::StoreEnumeratorBase(v25, a2, &v40, v42);
  v30 = a5;
  *v25 = &EmailMailboxEnum::`vftable';
  v25[20] = 0;
  v25[24] = 0;
  *((_DWORD *)v25 + 46) = 0;
  v25[25] = 0;
  v25[19] = &EmailOperationContext::`vftable';
  v25[26] = 0;
  v31 = (*(__int64 (__fastcall **)(_QWORD *, struct ServiceDataSession *, _QWORD, __int64))(*v25 + 152LL))(
          v25,
          a1,
          v8,
          v30);
  v27 = v31;
  if ( v31 < 0 )
  {
    Log_HREvent_27((unsigned int)v31, 1, v32, 22);
    tlx::_delete<AggregateComponentEnum>((__int64)v25);
    goto LABEL_43;
  }
  v39 = v48[0];
  *v6 = v25;
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v47 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v44 )
    (*(void (__fastcall **)(ServiceDataSession *))(*(_QWORD *)v44 + 16LL))(v44);
  if ( a1 )
    (*(void (__fastcall **)(struct ServiceDataSession *))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18000c8e0  mov     [rsp-8+arg_8], rbx
0x18000c8e5  mov     [rsp-8+arg_18], r9d
0x18000c8ea  push    rbp
0x18000c8eb  push    rsi
0x18000c8ec  push    rdi
0x18000c8ed  push    r12
0x18000c8ef  push    r13
0x18000c8f1  push    r14
0x18000c8f3  push    r15
0x18000c8f5  lea     rbp, [rsp-17h]
0x18000c8fa  sub     rsp, 90h
0x18000c901  mov     r12, [rbp+47h+arg_28]
0x18000c905  mov     rdi, rcx
0x18000c908  xor     r14d, r14d
0x18000c90b  lea     rcx, ?g_sessionListLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000c912  mov     esi, r9d
0x18000c915  mov     r13, r8
0x18000c918  mov     r15d, edx
0x18000c91b  mov     [r12], r14
0x18000c91f  call    cs:__imp_EnterCriticalSection
0x18000c925  mov     r10, qword ptr cs:xmmword_18015D790
0x18000c92c  test    r10, r10
0x18000c92f  jz      loc_18000CCFE
0x18000c935  mov     rcx, 0FF51AFD7ED558CCDh
0x18000c93f  mov     rax, rdi
0x18000c942  shr     rax, 21h
0x18000c946  xor     rax, rdi
0x18000c949  imul    rax, rcx
0x18000c94d  mov     rcx, rax
0x18000c950  shr     rcx, 21h
0x18000c954  xor     rcx, rax
0x18000c957  mov     rax, 0C4CEB9FE1A85EC53h
0x18000c961  imul    rcx, rax
0x18000c965  lea     eax, [r14+8]
0x18000c969  mov     rdx, rcx
0x18000c96c  shr     rdx, 21h
0x18000c970  xor     rdx, rcx
0x18000c973  mov     cl, byte ptr cs:word_18015D7A0
0x18000c979  shl     rax, cl
0x18000c97c  dec     rax
0x18000c97f  and     rax, rdx
0x18000c982  add     rax, rax
0x18000c985  mov     rcx, [r10+rax*8]
0x18000c989  test    rcx, rcx
0x18000c98c  jz      loc_18000CCFE
0x18000c992  mov     rax, [r10+rax*8+8]
0x18000c997  mov     r8, [rax]
0x18000c99a  cmp     rcx, r8
0x18000c99d  jz      loc_18000CCFE
0x18000c9a3  cmp     [rcx+10h], rdx
0x18000c9a7  jb      short loc_18000C9B5
0x18000c9a9  ja      loc_18000CCFE
0x18000c9af  cmp     rdi, [rcx+18h]
0x18000c9b3  jz      short loc_18000C9BA
0x18000c9b5  mov     rcx, [rcx]
0x18000c9b8  jmp     short loc_18000C99A
0x18000c9ba  lea     rax, ?g_sessionList@@3V?$unordered_set@PEAVServiceDataSession@@U?$hash@PEAVServiceDataSession@@@utl@@U?$equal_to@PEAVServiceDataSession@@@3@V?$allocator@PEAVServiceDataSession@@@3@@utl@@A; utl::unordered_set<ServiceDataSession *,utl::hash<ServiceDataSession *>,utl::equal_to<ServiceDataSession *>,utl::allocator<ServiceDataSession *>> g_sessionList
0x18000c9c1  cmp     rcx, rax
0x18000c9c4  jz      loc_18000CCFE
0x18000c9ca  test    rdi, rdi
0x18000c9cd  jz      short loc_18000C9DE
0x18000c9cf  mov     rax, [rdi]
0x18000c9d2  mov     rcx, rdi
0x18000c9d5  mov     rax, [rax+8]
0x18000c9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9de  lea     rcx, ?g_sessionListLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000c9e5  mov     [rbp+47h+arg_0], rdi
0x18000c9e9  call    cs:__imp_LeaveCriticalSection
0x18000c9ef  lea     rax, ??_7EmailOperationContext@@6B@; const EmailOperationContext::`vftable'
0x18000c9f6  mov     [rbp+47h+var_68], r14
0x18000c9fa  mov     rdx, rdi; struct ServiceDataSession *
0x18000c9fd  mov     [rbp+47h+var_70], rax
0x18000ca01  lea     rcx, [rbp+47h+var_70]; this
0x18000ca05  mov     [rbp+47h+var_48], r14
0x18000ca09  mov     [rbp+47h+var_50], r14d
0x18000ca0d  mov     [rbp+47h+var_40], r14
0x18000ca11  mov     [rbp+47h+var_38], r14
0x18000ca15  call    ?Initialize@UnistoreOperationContext@@UEAAJPEAVServiceDataSession@@@Z; UnistoreOperationContext::Initialize(ServiceDataSession *)
0x18000ca1a  mov     ebx, eax
0x18000ca1c  test    eax, eax
0x18000ca1e  js      loc_18000CED4
0x18000ca24  lea     rcx, [rbp+47h+arg_28]
0x18000ca28  mov     [rbp+47h+arg_28], r14
0x18000ca2c  call    cs:__imp_POutlookAppManager_CreateInstance
0x18000ca32  mov     ebx, eax
0x18000ca34  test    eax, eax
0x18000ca36  js      loc_18000CE1D
0x18000ca3c  mov     rcx, [rbp+47h+arg_28]
0x18000ca40  lea     rdx, [rbp+47h+var_40]
0x18000ca44  mov     rax, [rcx]
0x18000ca47  mov     rax, [rax+20h]
0x18000ca4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca50  mov     ebx, eax
0x18000ca52  test    eax, eax
0x18000ca54  js      loc_18000CD29
0x18000ca5a  mov     rcx, [rbp+47h+arg_28]
0x18000ca5e  mov     [rbp+47h+var_50], 1
0x18000ca65  test    rcx, rcx
0x18000ca68  jz      short loc_18000CA76
0x18000ca6a  mov     rax, [rcx]
0x18000ca6d  mov     rax, [rax+10h]
0x18000ca71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca76  cmp     [rbp+47h+var_38], r14
0x18000ca7a  jnz     short loc_18000CADF
0x18000ca7c  lea     rax, [rbp+47h+arg_28]
0x18000ca80  mov     [rbp+47h+arg_28], r14
0x18000ca84  mov     r9d, 200000h
0x18000ca8a  mov     [rsp+0C0h+var_A0], rax
0x18000ca8f  xor     r8d, r8d
0x18000ca92  xor     edx, edx
0x18000ca94  xor     ecx, ecx
0x18000ca96  call    cs:__imp_MAPILogonEx
0x18000ca9c  mov     ebx, eax
0x18000ca9e  test    eax, eax
0x18000caa0  js      loc_18000CE51
0x18000caa6  mov     rcx, [rbp+47h+arg_28]
0x18000caaa  lea     r8, [rbp+47h+var_38]
0x18000caae  lea     rdx, _GUID_5675594b_0e92_4117_ae35_434774ec0810
0x18000cab5  mov     rax, [rcx]
0x18000cab8  mov     rax, [rax]
0x18000cabb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cac0  mov     ebx, eax
0x18000cac2  test    eax, eax
0x18000cac4  js      loc_18000CDE6
0x18000caca  mov     rcx, [rbp+47h+arg_28]
0x18000cace  test    rcx, rcx
0x18000cad1  jz      short loc_18000CADF
0x18000cad3  mov     rax, [rcx]
0x18000cad6  mov     rax, [rax+10h]
0x18000cada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cadf  test    r15d, r15d
0x18000cae2  mov     edx, r14d
0x18000cae5  setnz   dl
0x18000cae8  cmp     [rbp+47h+var_68], r14
0x18000caec  jz      loc_18000CBEF
0x18000caf2  mov     rax, [rbp+47h+var_70]
0x18000caf6  lea     rcx, [rbp+47h+var_70]
0x18000cafa  mov     rax, [rax+48h]
0x18000cafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb03  mov     r14d, eax
0x18000cb06  test    eax, eax
0x18000cb08  jz      loc_18000CE28
0x18000cb0e  mov     rsi, [rbp+47h+var_68]
0x18000cb12  mov     rcx, rsi; this
0x18000cb15  call    ?EnsureIntializedSecurityAndAppInfo@ServiceDataSession@@AEAAJXZ; ServiceDataSession::EnsureIntializedSecurityAndAppInfo(void)
0x18000cb1a  mov     ebx, eax
0x18000cb1c  test    eax, eax
0x18000cb1e  js      loc_18000CE59
0x18000cb24  mov     eax, [rsi+6FCh]
0x18000cb2a  test    r14d, eax
0x18000cb2d  jz      loc_18000CEE9
0x18000cb33  test    r15d, r15d
0x18000cb36  jz      short loc_18000CB47
0x18000cb38  and     eax, r14d
0x18000cb3b  test    [rsi+704h], eax
0x18000cb41  jz      loc_18000CD91
0x18000cb47  xor     r14d, r14d
0x18000cb4a  mov     ebx, r14d
0x18000cb4d  test    ebx, ebx
0x18000cb4f  jns     loc_18000CBEC
0x18000cb55  mov     edx, 1
0x18000cb5a  mov     r9d, 996h
0x18000cb60  mov     ecx, ebx
0x18000cb62  call    Log_HREvent_27
0x18000cb67  mov     rcx, [rbp+47h+var_38]
0x18000cb6b  test    rcx, rcx
0x18000cb6e  jz      short loc_18000CB7C
0x18000cb70  mov     rax, [rcx]
0x18000cb73  mov     rax, [rax+10h]
0x18000cb77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb7c  mov     rcx, [rbp+47h+var_40]
0x18000cb80  test    rcx, rcx
0x18000cb83  jz      short loc_18000CB91
0x18000cb85  mov     rax, [rcx]
0x18000cb88  mov     rax, [rax+10h]
0x18000cb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb91  mov     rcx, [rbp+47h+var_48]
0x18000cb95  test    rcx, rcx
0x18000cb98  jz      short loc_18000CBA6
0x18000cb9a  mov     rax, [rcx]
0x18000cb9d  mov     rax, [rax+10h]
0x18000cba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cba6  mov     rcx, [rbp+47h+var_68]
0x18000cbaa  test    rcx, rcx
0x18000cbad  jz      short loc_18000CBBB
0x18000cbaf  mov     rax, [rcx]
0x18000cbb2  mov     rax, [rax+10h]
0x18000cbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbbb  test    rdi, rdi
0x18000cbbe  jz      short loc_18000CBCF
0x18000cbc0  mov     rcx, [rdi]
0x18000cbc3  mov     rax, [rcx+10h]
0x18000cbc7  mov     rcx, rdi
0x18000cbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbcf  mov     eax, ebx
0x18000cbd1  mov     rbx, [rsp+0C0h+arg_8]
0x18000cbd9  add     rsp, 90h
0x18000cbe0  pop     r15
0x18000cbe2  pop     r14
0x18000cbe4  pop     r13
0x18000cbe6  pop     r12
0x18000cbe8  pop     rdi
0x18000cbe9  pop     rsi
0x18000cbea  pop     rbp
0x18000cbeb  retn
0x18000cbec  mov     esi, [rbp+47h+arg_18]
0x18000cbef  mov     ecx, 0D8h; Size
0x18000cbf4  mov     [rbp+47h+arg_28], r14
0x18000cbf8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cbfd  mov     rbx, rax
0x18000cc00  test    rax, rax
0x18000cc03  jnz     short loc_18000CC48
0x18000cc05  mov     esi, 8007000Eh
0x18000cc0a  lea     r9d, [rax+15h]
0x18000cc0e  mov     ecx, esi
0x18000cc10  xor     edx, edx
0x18000cc12  call    Log_HREvent_27
0x18000cc17  mov     edx, 1
0x18000cc1c  mov     r9d, 99Fh
0x18000cc22  mov     ecx, esi
0x18000cc24  call    Log_HREvent_27
0x18000cc29  lea     rcx, [rbp+47h+arg_28]
0x18000cc2d  call    ?_Delete@?$auto_xxx@PEAVChatEnumBase@@P6AXPEAV1@@Z$1??$_delete@VChatEnumBase@@@tlx@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ChatEnumBase *,void (*)(ChatEnumBase *),&tlx::_delete<ChatEnumBase>(ChatEnumBase *),0>::_Delete(void)
0x18000cc32  lea     rcx, [rbp+47h+var_70]; this
0x18000cc36  call    ??1EmailOperationContext@@QEAA@XZ; EmailOperationContext::~EmailOperationContext(void)
0x18000cc3b  lea     rcx, [rbp+47h+arg_0]
0x18000cc3f  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000cc44  mov     eax, esi
0x18000cc46  jmp     short loc_18000CBD1
0x18000cc48  movsd   xmm0, qword ptr [r13+0]
0x18000cc4e  lea     rax, ?s_EmailMailbox_PropMap@@3QBUUdmPoomPropIdMap@@B; UdmPoomPropIdMap const near * const s_EmailMailbox_PropMap
0x18000cc55  mov     [rbp+47h+var_78], rax
0x18000cc59  lea     r9, [rbp+47h+var_80]
0x18000cc5d  mov     eax, [r13+8]
0x18000cc61  lea     r8, [rbp+47h+var_90]
0x18000cc65  mov     edx, r15d
0x18000cc68  mov     [rbp+47h+var_88], eax
0x18000cc6b  mov     rcx, rbx
0x18000cc6e  mov     [rbp+47h+var_80], 25h ; '%'
0x18000cc76  movsd   [rbp+47h+var_90], xmm0
0x18000cc7b  call    ??0StoreEnumeratorBase@@IEAA@HUUdmObjectId@@AEBV?$Vector@$$CBUUdmPoomPropIdMap@@@Udm@@@Z; StoreEnumeratorBase::StoreEnumeratorBase(int,UdmObjectId,Udm::Vector<UdmPoomPropIdMap const> const &)
0x18000cc80  mov     r9, [rbp+47h+arg_20]
0x18000cc84  lea     rdx, ??_7EmailMailboxEnum@@6B@; const EmailMailboxEnum::`vftable'
0x18000cc8b  mov     [rbx], rdx
0x18000cc8e  lea     rax, ??_7EmailOperationContext@@6B@; const EmailOperationContext::`vftable'
0x18000cc95  mov     [rbx+0A0h], r14
0x18000cc9c  mov     r8d, esi
0x18000cc9f  mov     [rbx+0C0h], r14
0x18000cca6  mov     rdx, rdi
0x18000cca9  mov     [rbx+0B8h], r14d
0x18000ccb0  mov     rcx, rbx
0x18000ccb3  mov     [rbx+0C8h], r14
0x18000ccba  mov     [rbx+98h], rax
0x18000ccc1  mov     [rbx+0D0h], r14
0x18000ccc8  mov     rax, [rbx]
0x18000cccb  mov     rax, [rax+98h]
0x18000ccd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccd7  mov     esi, eax
0x18000ccd9  test    eax, eax
0x18000ccdb  jns     loc_18000CE61
0x18000cce1  mov     edx, 1
0x18000cce6  mov     ecx, eax
0x18000cce8  lea     r9d, [rdx+15h]
0x18000ccec  call    Log_HREvent_27
0x18000ccf1  mov     rcx, rbx
0x18000ccf4  call    ??$_delete@VAggregateComponentEnum@@@tlx@@YAXPEAVAggregateComponentEnum@@@Z; tlx::_delete<AggregateComponentEnum>(AggregateComponentEnum *)
0x18000ccf9  jmp     loc_18000CC17
0x18000ccfe  lea     rcx, ?g_sessionListLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000cd05  call    cs:__imp_LeaveCriticalSection
0x18000cd0b  mov     edi, 80070006h
0x18000cd10  mov     edx, 1
0x18000cd15  mov     ecx, edi
0x18000cd17  mov     r9d, 992h
0x18000cd1d  call    Log_HREvent_27
0x18000cd22  mov     eax, edi
0x18000cd24  jmp     loc_18000CBD1
0x18000cd29  mov     r9d, 11h
0x18000cd2f  mov     edx, 1
0x18000cd34  mov     ecx, eax
0x18000cd36  call    Log_HREvent_16
0x18000cd3b  mov     rcx, [rbp+47h+arg_28]
0x18000cd3f  test    rcx, rcx
0x18000cd42  jz      short loc_18000CD50
0x18000cd44  mov     rax, [rcx]
0x18000cd47  mov     rax, [rax+10h]
0x18000cd4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd50  mov     r9d, 0Dh
0x18000cd56  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000cd5d  mov     ecx, ebx
0x18000cd5f  lea     edx, [r9-0Ch]
0x18000cd63  call    Log_HREvent
0x18000cd68  mov     edx, 1
0x18000cd6d  mov     r9d, 995h
0x18000cd73  mov     ecx, ebx
0x18000cd75  call    Log_HREvent_27
0x18000cd7a  lea     rcx, [rbp+47h+var_38]
0x18000cd7e  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x18000cd83  lea     rcx, [rbp+47h+var_70]; this
0x18000cd87  call    ??1PoomOperationContext@@QEAA@XZ; PoomOperationContext::~PoomOperationContext(void)
0x18000cd8c  jmp     loc_18000CBBB
  ... truncated ...
```
