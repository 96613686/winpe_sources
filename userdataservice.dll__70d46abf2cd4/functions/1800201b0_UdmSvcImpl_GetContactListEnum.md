# UdmSvcImpl_GetContactListEnum

- ea: `0x1800201b0`
- end: `0x18002069f`
- name: `UdmSvcImpl_GetContactListEnum`
- size: `1263`
- prototype: `__int64 __usercall@<rax>(struct ServiceDataSession *@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800049f0`
- `0x180008380`
- `0x180008ee8`
- `0x180008f0c`
- `0x180008f58`
- `0x18000a780`
- `0x18000b620`
- `0x18000c740`
- `0x1800201b0`
- `0x180021aa4`
- `0x18007f77c`
- `0x1800810a8`
- `0x1800977c4`
- `0x1800a5630`
- `0x18012e010`

## import_xrefs

- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x1800202f3`
- `PIMSTORE!POutlookAppManager_CreateInstance` at `0x1800202f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800201ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800201ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800204f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800202b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800204f4`

## string_xrefs

- `0x180020630`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x1800204ff`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x180020521`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x18002053d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x18002059a`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`
- `0x180020680`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\contactenum.cpp`

## pseudocode

```c
__int64 __fastcall UdmSvcImpl_GetContactListEnum(
        struct ServiceDataSession *a1,
        int a2,
        __int64 *a3,
        unsigned int a4,
        __int64 a5,
        char **a6)
{
  char **v6; // r12
  unsigned int v8; // esi
  unsigned __int64 v11; // rdx
  void **v12; // rcx
  int v13; // eax
  __int64 v14; // r8
  unsigned int v15; // ebx
  int v16; // eax
  __int64 v17; // r8
  int v18; // r14d
  ServiceDataSession *v19; // rsi
  int updated; // eax
  int v21; // ecx
  char *v22; // rbx
  __int64 v23; // xmm0_8
  __int64 v24; // r9
  int v25; // eax
  int v26; // eax
  unsigned int v27; // esi
  __int64 v29; // r9
  __int64 v30; // r8
  __int64 v31; // r9
  int v32; // r9d
  __int64 v33; // r9
  void **v34; // [rsp+30h] [rbp-40h] BYREF
  ServiceDataSession *v35; // [rsp+38h] [rbp-38h] BYREF
  int v36; // [rsp+50h] [rbp-20h]
  __int64 v37; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v38[2]; // [rsp+60h] [rbp-10h] BYREF
  struct ServiceDataSession *v39; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v40; // [rsp+C8h] [rbp+58h]

  v40 = a4;
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
LABEL_30:
    LeaveCriticalSection(&g_sessionListLock);
    Log_HREvent(
      2147942406LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      2250);
    return 2147942406LL;
  }
  while ( 1 )
  {
    if ( v12 == **((void ****)xmmword_18015D790 + 2 * (v11 & ((8LL << word_18015D7A0) - 1)) + 1) )
      goto LABEL_30;
    if ( (unsigned __int64)v12[2] >= v11 )
    {
      if ( (unsigned __int64)v12[2] > v11 )
        goto LABEL_30;
      if ( a1 == v12[3] )
        break;
    }
    v12 = (void **)*v12;
  }
  if ( v12 == &g_sessionList )
    goto LABEL_30;
  if ( a1 )
    (*(void (__fastcall **)(struct ServiceDataSession *))(*(_QWORD *)a1 + 8LL))(a1);
  v39 = a1;
  LeaveCriticalSection(&g_sessionListLock);
  v35 = 0;
  v34 = &ContactOperationContext::`vftable';
  v37 = 0;
  v36 = 0;
  v38[0] = 0;
  v13 = UnistoreOperationContext::Initialize((UnistoreOperationContext *)&v34, a1);
  v15 = v13;
  if ( v13 < 0 )
  {
    Log_HREvent_16((unsigned int)v13, 1, v14, 13);
LABEL_36:
    Log_HREvent_17(v15, 1, v30, 9);
    v31 = 2253;
    goto LABEL_37;
  }
  a6 = 0;
  v16 = POutlookAppManager_CreateInstance(&a6);
  v15 = v16;
  if ( v16 < 0 )
  {
    v29 = 16;
LABEL_34:
    Log_HREvent_16((unsigned int)v16, 1, v17, v29);
    if ( a6 )
      (*((void (__fastcall **)(char **))*a6 + 2))(a6);
    goto LABEL_36;
  }
  v16 = (*((__int64 (__fastcall **)(char **, _QWORD *))*a6 + 4))(a6, v38);
  v15 = v16;
  if ( v16 < 0 )
  {
    v29 = 17;
    goto LABEL_34;
  }
  v36 = 1;
  if ( a6 )
    (*((void (__fastcall **)(char **))*a6 + 2))(a6);
  if ( v35 )
  {
    v18 = ((__int64 (__fastcall *)(void ***, bool))v34[9])(&v34, a2 != 0);
    if ( v18 )
    {
      v19 = v35;
      updated = ServiceDataSession::EnsureIntializedSecurityAndAppInfo(v35);
      v15 = updated;
      if ( updated < 0 )
      {
        v33 = 1255;
      }
      else
      {
        v21 = *((_DWORD *)v19 + 447);
        if ( (v21 & v18) == 0 )
        {
          v15 = -2147024891;
          goto LABEL_23;
        }
        if ( !a2 || (v21 & *((_DWORD *)v19 + 449) & v18) != 0 )
          goto LABEL_22;
        updated = ServiceDataSession::_UpdateSecurityFlagsForPrivacy(v19, 0, v18);
        v15 = updated;
        if ( updated >= 0 )
        {
          v32 = *((_DWORD *)v19 + 447);
          if ( (v32 & *((_DWORD *)v19 + 449) & v18) == 0 )
          {
            if ( (Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits & 0x80u) != 0 )
              McTemplateU0qqq_EventWriteTransfer(
                *((_DWORD *)v19 + 449),
                (unsigned int)ClientPrivacyCapabilityFailed,
                v18,
                v32,
                *((_DWORD *)v19 + 449));
            v15 = -2147467260;
            goto LABEL_23;
          }
LABEL_22:
          v15 = 0;
LABEL_23:
          if ( (v15 & 0x80000000) == 0 )
          {
            v8 = v40;
            goto LABEL_25;
          }
          v31 = 2254;
LABEL_37:
          Log_HREvent(
            v15,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
            v31);
          goto LABEL_38;
        }
        v33 = 1265;
      }
      Log_HREvent(
        (unsigned int)updated,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        v33);
      goto LABEL_23;
    }
  }
LABEL_25:
  a6 = 0;
  v22 = (char *)operator new(0xD0u);
  if ( !v22 )
  {
    v27 = -2147024882;
    Log_HREvent(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      81);
LABEL_32:
    Log_HREvent(
      v27,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      2263);
    tlx::auto_xxx<ChatEnumBase *,void (*)(ChatEnumBase *),&void tlx::_delete<ChatEnumBase>(ChatEnumBase *),0>::_Delete(&a6);
    v15 = v27;
LABEL_38:
    PoomOperationContext::~PoomOperationContext((PoomOperationContext *)&v34);
    ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v39);
    return v15;
  }
  *(_QWORD *)v22 = &UnusedUnknown<IUnknown>::`vftable';
  *((_DWORD *)v22 + 2) = 1;
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v22 + 16);
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v22 + 40);
  utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v22 + 64);
  v23 = *a3;
  v24 = a5;
  *((_QWORD *)v22 + 12) = &s_ContactList_PropMap;
  v25 = *((_DWORD *)a3 + 2);
  *((_QWORD *)v22 + 11) = 40;
  *((_QWORD *)v22 + 13) = 0;
  *((_DWORD *)v22 + 28) = 1;
  *((_QWORD *)v22 + 15) = 0;
  *((_QWORD *)v22 + 16) = 0;
  *(_QWORD *)(v22 + 140) = v23;
  *((_DWORD *)v22 + 37) = v25;
  *(_QWORD *)v22 = &ContactListEnum::`vftable';
  *((_DWORD *)v22 + 34) = a2;
  *((_QWORD *)v22 + 20) = 0;
  *((_QWORD *)v22 + 24) = 0;
  *((_DWORD *)v22 + 46) = 0;
  *((_QWORD *)v22 + 25) = 0;
  *((_QWORD *)v22 + 19) = &ContactOperationContext::`vftable';
  v26 = (*(__int64 (__fastcall **)(char *, struct ServiceDataSession *, _QWORD, __int64))(*(_QWORD *)v22 + 152LL))(
          v22,
          a1,
          v8,
          v24);
  v27 = v26;
  if ( v26 < 0 )
  {
    Log_HREvent(
      (unsigned int)v26,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\contactenum.cpp",
      82);
    tlx::_delete<AggregateComponentEnum>((__int64)v22);
    goto LABEL_32;
  }
  *v6 = v22;
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(v38);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v37);
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v35);
  if ( a1 )
    (*(void (__fastcall **)(struct ServiceDataSession *))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x1800201b0  mov     [rsp-38h+arg_8], rbx
0x1800201b5  mov     [rsp-38h+arg_18], r9d
0x1800201ba  push    rbp
0x1800201bb  push    rsi
0x1800201bc  push    rdi
0x1800201bd  push    r12
0x1800201bf  push    r13
0x1800201c1  push    r14
0x1800201c3  push    r15
0x1800201c5  mov     rbp, rsp
0x1800201c8  sub     rsp, 70h
0x1800201cc  mov     r12, [rbp+arg_28]
0x1800201d0  mov     rdi, rcx
0x1800201d3  xor     r14d, r14d
0x1800201d6  lea     rcx, ?g_sessionListLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800201dd  mov     esi, r9d
0x1800201e0  mov     r13, r8
0x1800201e3  mov     r15d, edx
0x1800201e6  mov     [r12], r14
0x1800201ea  call    cs:__imp_EnterCriticalSection
0x1800201f0  mov     r10, qword ptr cs:xmmword_18015D790
0x1800201f7  test    r10, r10
0x1800201fa  jz      loc_1800204ED
0x180020200  mov     rcx, 0FF51AFD7ED558CCDh
0x18002020a  mov     rax, rdi
0x18002020d  shr     rax, 21h
0x180020211  xor     rax, rdi
0x180020214  imul    rax, rcx
0x180020218  mov     rcx, rax
0x18002021b  shr     rcx, 21h
0x18002021f  xor     rcx, rax
0x180020222  mov     rax, 0C4CEB9FE1A85EC53h
0x18002022c  imul    rcx, rax
0x180020230  lea     eax, [r14+8]
0x180020234  mov     rdx, rcx
0x180020237  shr     rdx, 21h
0x18002023b  xor     rdx, rcx
0x18002023e  mov     cl, byte ptr cs:word_18015D7A0
0x180020244  shl     rax, cl
0x180020247  dec     rax
0x18002024a  and     rax, rdx
0x18002024d  add     rax, rax
0x180020250  mov     rcx, [r10+rax*8]
0x180020254  test    rcx, rcx
0x180020257  jz      loc_1800204ED
0x18002025d  mov     rax, [r10+rax*8+8]
0x180020262  mov     r8, [rax]
0x180020265  cmp     rcx, r8
0x180020268  jz      loc_1800204ED
0x18002026e  cmp     [rcx+10h], rdx
0x180020272  jb      short loc_180020280
0x180020274  ja      loc_1800204ED
0x18002027a  cmp     rdi, [rcx+18h]
0x18002027e  jz      short loc_180020285
0x180020280  mov     rcx, [rcx]
0x180020283  jmp     short loc_180020265
0x180020285  lea     rax, ?g_sessionList@@3V?$unordered_set@PEAVServiceDataSession@@U?$hash@PEAVServiceDataSession@@@utl@@U?$equal_to@PEAVServiceDataSession@@@3@V?$allocator@PEAVServiceDataSession@@@3@@utl@@A; utl::unordered_set<ServiceDataSession *,utl::hash<ServiceDataSession *>,utl::equal_to<ServiceDataSession *>,utl::allocator<ServiceDataSession *>> g_sessionList
0x18002028c  cmp     rcx, rax
0x18002028f  jz      loc_1800204ED
0x180020295  test    rdi, rdi
0x180020298  jz      short loc_1800202A9
0x18002029a  mov     rax, [rdi]
0x18002029d  mov     rcx, rdi
0x1800202a0  mov     rax, [rax+8]
0x1800202a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202a9  lea     rcx, ?g_sessionListLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800202b0  mov     [rbp+arg_0], rdi
0x1800202b4  call    cs:__imp_LeaveCriticalSection
0x1800202ba  lea     rax, ??_7ContactOperationContext@@6B@; const ContactOperationContext::`vftable'
0x1800202c1  mov     [rbp+var_38], r14
0x1800202c5  mov     rdx, rdi; struct ServiceDataSession *
0x1800202c8  mov     [rbp+var_40], rax
0x1800202cc  lea     rcx, [rbp+var_40]; this
0x1800202d0  mov     [rbp+var_18], r14
0x1800202d4  mov     [rbp+var_20], r14d
0x1800202d8  mov     [rbp+var_10], r14
0x1800202dc  call    ?Initialize@UnistoreOperationContext@@UEAAJPEAVServiceDataSession@@@Z; UnistoreOperationContext::Initialize(ServiceDataSession *)
0x1800202e1  mov     ebx, eax
0x1800202e3  test    eax, eax
0x1800202e5  js      loc_180020653
0x1800202eb  lea     rcx, [rbp+arg_28]
0x1800202ef  mov     [rbp+arg_28], r14
0x1800202f3  call    cs:__imp_POutlookAppManager_CreateInstance
0x1800202f9  mov     ebx, eax
0x1800202fb  test    eax, eax
0x1800202fd  js      loc_180020617
0x180020303  mov     rcx, [rbp+arg_28]
0x180020307  lea     rdx, [rbp+var_10]
0x18002030b  mov     rax, [rcx]
0x18002030e  mov     rax, [rax+20h]
0x180020312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020317  mov     ebx, eax
0x180020319  test    eax, eax
0x18002031b  js      loc_18002055D
0x180020321  mov     rcx, [rbp+arg_28]
0x180020325  mov     [rbp+var_20], 1
0x18002032c  test    rcx, rcx
0x18002032f  jz      short loc_18002033D
0x180020331  mov     rax, [rcx]
0x180020334  mov     rax, [rax+10h]
0x180020338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002033d  test    r15d, r15d
0x180020340  mov     edx, r14d
0x180020343  setnz   dl
0x180020346  cmp     [rbp+var_38], r14
0x18002034a  jz      short loc_1800203B4
0x18002034c  mov     rax, [rbp+var_40]
0x180020350  lea     rcx, [rbp+var_40]
0x180020354  mov     rax, [rax+48h]
0x180020358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002035d  mov     r14d, eax
0x180020360  test    eax, eax
0x180020362  jz      loc_180020622
0x180020368  mov     rsi, [rbp+var_38]
0x18002036c  mov     rcx, rsi; this
0x18002036f  call    ?EnsureIntializedSecurityAndAppInfo@ServiceDataSession@@AEAAJXZ; ServiceDataSession::EnsureIntializedSecurityAndAppInfo(void)
0x180020374  mov     ebx, eax
0x180020376  test    eax, eax
0x180020378  js      loc_18002064B
0x18002037e  mov     ecx, [rsi+6FCh]
0x180020384  test    r14d, ecx
0x180020387  jz      loc_180020668
0x18002038d  test    r15d, r15d
0x180020390  jz      short loc_1800203A3
0x180020392  mov     eax, [rsi+704h]
0x180020398  and     eax, ecx
0x18002039a  test    r14d, eax
0x18002039d  jz      loc_1800205C6
0x1800203a3  xor     r14d, r14d
0x1800203a6  mov     ebx, r14d
0x1800203a9  test    ebx, ebx
0x1800203ab  js      loc_18002066F
0x1800203b1  mov     esi, [rbp+arg_18]
0x1800203b4  mov     ecx, 0D0h; Size
0x1800203b9  mov     [rbp+arg_28], r14
0x1800203bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800203c2  mov     rbx, rax
0x1800203c5  test    rax, rax
0x1800203c8  jz      loc_18002051C
0x1800203ce  lea     rax, ??_7?$UnusedUnknown@UIUnknown@@@@6B@; const UnusedUnknown<IUnknown>::`vftable'
0x1800203d5  mov     [rbx], rax
0x1800203d8  lea     rcx, [rbx+10h]
0x1800203dc  mov     dword ptr [rbx+8], 1
0x1800203e3  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800203e8  lea     rcx, [rbx+28h]
0x1800203ec  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800203f1  lea     rcx, [rbx+40h]
0x1800203f5  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800203fa  movsd   xmm0, qword ptr [r13+0]
0x180020400  lea     rax, ?s_ContactList_PropMap@@3QBUUdmPoomPropIdMap@@B; UdmPoomPropIdMap const near * const s_ContactList_PropMap
0x180020407  mov     r9, [rbp+arg_20]
0x18002040b  mov     r8d, esi
0x18002040e  mov     [rbx+60h], rax
0x180020412  mov     rdx, rdi
0x180020415  mov     eax, [r13+8]
0x180020419  mov     rcx, rbx
0x18002041c  mov     qword ptr [rbx+58h], 28h ; '('
0x180020424  mov     qword ptr [rbx+68h], 0
0x18002042c  mov     dword ptr [rbx+70h], 1
0x180020433  mov     [rbx+78h], r14
0x180020437  mov     [rbx+80h], r14
0x18002043e  movsd   qword ptr [rbx+8Ch], xmm0
0x180020446  mov     [rbx+94h], eax
0x18002044c  lea     rax, ??_7ContactListEnum@@6B@; const ContactListEnum::`vftable'
0x180020453  mov     [rbx], rax
0x180020456  lea     rax, ??_7ContactOperationContext@@6B@; const ContactOperationContext::`vftable'
0x18002045d  mov     [rbx+88h], r15d
0x180020464  mov     [rbx+0A0h], r14
0x18002046b  mov     [rbx+0C0h], r14
0x180020472  mov     [rbx+0B8h], r14d
0x180020479  mov     [rbx+0C8h], r14
0x180020480  mov     [rbx+98h], rax
0x180020487  mov     rax, [rbx]
0x18002048a  mov     rax, [rax+98h]
0x180020491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020496  mov     esi, eax
0x180020498  test    eax, eax
0x18002049a  js      loc_18002067A
0x1800204a0  lea     rcx, [rbp+var_10]
0x1800204a4  mov     [r12], rbx
0x1800204a8  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800204ad  lea     rcx, [rbp+var_18]
0x1800204b1  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800204b6  lea     rcx, [rbp+var_38]
0x1800204ba  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800204bf  test    rdi, rdi
0x1800204c2  jz      short loc_1800204D3
0x1800204c4  mov     rax, [rdi]
0x1800204c7  mov     rcx, rdi
0x1800204ca  mov     rax, [rax+10h]
0x1800204ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204d3  xor     eax, eax
0x1800204d5  mov     rbx, [rsp+70h+arg_8]
0x1800204dd  add     rsp, 70h
0x1800204e1  pop     r15
0x1800204e3  pop     r14
0x1800204e5  pop     r13
0x1800204e7  pop     r12
0x1800204e9  pop     rdi
0x1800204ea  pop     rsi
0x1800204eb  pop     rbp
0x1800204ec  retn
0x1800204ed  lea     rcx, ?g_sessionListLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800204f4  call    cs:__imp_LeaveCriticalSection
0x1800204fa  mov     edi, 80070006h
0x1800204ff  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180020506  mov     ecx, edi
0x180020508  mov     r9d, 8CAh
0x18002050e  mov     edx, 1
0x180020513  call    Log_HREvent
0x180020518  mov     eax, edi
0x18002051a  jmp     short loc_1800204D5
0x18002051c  mov     esi, 8007000Eh
0x180020521  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180020528  mov     ecx, esi
0x18002052a  mov     r9d, 51h ; 'Q'
0x180020530  xor     edx, edx
0x180020532  call    Log_HREvent
0x180020537  mov     r9d, 8D7h
0x18002053d  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180020544  mov     edx, 1
0x180020549  mov     ecx, esi
0x18002054b  call    Log_HREvent
0x180020550  lea     rcx, [rbp+arg_28]
0x180020554  call    ?_Delete@?$auto_xxx@PEAVChatEnumBase@@P6AXPEAV1@@Z$1??$_delete@VChatEnumBase@@@tlx@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ChatEnumBase *,void (*)(ChatEnumBase *),&tlx::_delete<ChatEnumBase>(ChatEnumBase *),0>::_Delete(void)
0x180020559  mov     ebx, esi
0x18002055b  jmp     short loc_1800205AD
0x18002055d  mov     r9d, 11h
0x180020563  mov     edx, 1
0x180020568  mov     ecx, eax
0x18002056a  call    Log_HREvent_16
0x18002056f  mov     rcx, [rbp+arg_28]
0x180020573  test    rcx, rcx
0x180020576  jz      short loc_180020584
0x180020578  mov     rax, [rcx]
0x18002057b  mov     rax, [rax+10h]
0x18002057f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020584  mov     edx, 1
0x180020589  mov     ecx, ebx
0x18002058b  lea     r9d, [rdx+8]
0x18002058f  call    Log_HREvent_17
0x180020594  mov     r9d, 8CDh
0x18002059a  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800205a1  mov     edx, 1
0x1800205a6  mov     ecx, ebx
0x1800205a8  call    Log_HREvent
0x1800205ad  lea     rcx, [rbp+var_40]; this
0x1800205b1  call    ??1PoomOperationContext@@QEAA@XZ; PoomOperationContext::~PoomOperationContext(void)
0x1800205b6  lea     rcx, [rbp+arg_0]
0x1800205ba  call    ??1?$CComPtrBase@UISODACompletionCallback@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(void)
0x1800205bf  mov     eax, ebx
0x1800205c1  jmp     loc_1800204D5
0x1800205c6  mov     r8d, r14d; unsigned int
0x1800205c9  xor     edx, edx; unsigned int
0x1800205cb  mov     rcx, rsi; this
0x1800205ce  call    ?_UpdateSecurityFlagsForPrivacy@ServiceDataSession@@AEAAJKK@Z; ServiceDataSession::_UpdateSecurityFlagsForPrivacy(ulong,ulong)
0x1800205d3  mov     ebx, eax
0x1800205d5  test    eax, eax
0x1800205d7  js      short loc_18002062A
0x1800205d9  mov     ecx, [rsi+704h]
0x1800205df  mov     eax, ecx
0x1800205e1  mov     r9d, [rsi+6FCh]
0x1800205e8  and     eax, r9d
0x1800205eb  test    r14d, eax
0x1800205ee  jnz     loc_1800203A3
0x1800205f4  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UserDataServiceEnableBits, 80h
0x1800205fb  jz      short loc_180020610
0x1800205fd  mov     r8d, r14d
0x180020600  mov     [rsp+70h+var_50], ecx
0x180020604  lea     rdx, ClientPrivacyCapabilityFailed
0x18002060b  call    McTemplateU0qqq_EventWriteTransfer
0x180020610  mov     ebx, 80004004h
0x180020615  jmp     short loc_180020643
0x180020617  mov     r9d, 10h
0x18002061d  jmp     loc_180020563
0x180020622  xor     r14d, r14d
0x180020625  jmp     loc_1800203B4
0x18002062a  mov     r9d, 4F1h
0x180020630  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180020637  mov     edx, 1
0x18002063c  mov     ecx, eax
0x18002063e  call    Log_HREvent
0x180020643  xor     r14d, r14d
0x180020646  jmp     loc_1800203A9
0x18002064b  mov     r9d, 4E7h
0x180020651  jmp     short loc_180020630
0x180020653  mov     edx, 1
0x180020658  mov     ecx, eax
0x18002065a  lea     r9d, [rdx+0Ch]
0x18002065e  call    Log_HREvent_16
0x180020663  jmp     loc_180020584
0x180020668  mov     ebx, 80070005h
0x18002066d  jmp     short loc_180020643
0x18002066f  mov     r9d, 8CEh
0x180020675  jmp     loc_18002059A
0x18002067a  mov     r9d, 52h ; 'R'
0x180020680  lea     r8, aOnecoreuapBase_77; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180020687  mov     ecx, eax
0x180020689  lea     edx, [r9-51h]
0x18002068d  call    Log_HREvent
  ... truncated ...
```
