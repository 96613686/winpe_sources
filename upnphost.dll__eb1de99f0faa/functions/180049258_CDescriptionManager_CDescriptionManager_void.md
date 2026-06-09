# CDescriptionManager::~CDescriptionManager(void)

- ea: `0x180049258`
- end: `0x180049592`
- name: `??1CDescriptionManager@@QEAA@XZ`
- size: `826`
- prototype: `void __fastcall(CDescriptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003c72c`

## callees

- `0x180017230`
- `0x180018738`
- `0x180019970`
- `0x18001b960`
- `0x18001da24`
- `0x180029008`
- `0x18003850c`
- `0x18003a560`
- `0x18003a584`
- `0x1800491c4`
- `0x18004920c`
- `0x180049258`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180049288`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180049288`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800492f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800492f8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800494d8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800494e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800494ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004951f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800494d8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800494e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800494ee`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004951f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004933b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004933b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800492c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800492c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800492b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x1800492b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800492a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800492a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800492dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800492dd`
- `SSDPAPI!DeregisterService` at `0x18004943e`
- `SSDPAPI!DeregisterService` at `0x18004943e`
- `OLEAUT32!__imp_SysFreeString` at `0x180049355`
- `OLEAUT32!__imp_SysFreeString` at `0x180049355`

## pseudocode

```c
void __fastcall CDescriptionManager::~CDescriptionManager(CDescriptionManager *this)
{
  void *v2; // rcx
  struct _TP_CLEANUP_GROUP *v3; // rcx
  struct _TP_POOL *v4; // rcx
  void *v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  CDescriptionManager *v7; // rcx
  struct SSDP_SERVICE_REGISTRATION_PARAMS *v8; // rsi
  struct SSDP_SERVICE_REGISTRATION_PARAMS *v9; // rdi
  struct SSDP_SERVICE_REGISTRATION_PARAMS **v10; // rax
  int v11; // esi
  unsigned int i; // edi
  int v13; // edi
  int v14; // esi
  __int64 v15; // rcx
  unsigned int v16; // esi
  int v17; // eax
  int v18; // ebx
  _DWORD *v19; // rdi
  int v20; // r13d
  __int64 j; // r14
  struct _GUID v22; // [rsp+28h] [rbp-60h] BYREF

  v2 = (void *)*((_QWORD *)this + 60);
  if ( v2 != (void *)-1LL )
    SetEvent(v2);
  v3 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 59);
  if ( v3 )
  {
    CloseThreadpoolCleanupGroupMembers(v3, 1, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 59));
  }
  v4 = (struct _TP_POOL *)*((_QWORD *)this + 58);
  if ( v4 )
  {
    CloseThreadpool(v4);
    *((_QWORD *)this + 58) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 60);
  if ( v5 != (void *)-1LL )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 60) = -1;
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 488);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  v8 = (struct SSDP_SERVICE_REGISTRATION_PARAMS *)*((_QWORD *)this + 76);
  while ( v8 != (CDescriptionManager *)((char *)this + 608) )
  {
    v9 = v8;
    v10 = (struct SSDP_SERVICE_REGISTRATION_PARAMS **)*((_QWORD *)v8 + 1);
    v8 = *(struct SSDP_SERVICE_REGISTRATION_PARAMS **)v8;
    *v10 = v8;
    *((_QWORD *)v8 + 1) = v10;
    CDescriptionManager::PurgeRegistrationParams(v7, v9);
    operator delete(v9, 0x50u);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  v11 = *((_DWORD *)this + 24);
  for ( i = 0; (int)i < v11; ++i )
    SysFreeString(*(BSTR *)(*((_QWORD *)this + 11) + 8LL * i));
  operator delete(*((void **)this + 9));
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  operator delete(*((void **)this + 11));
  *((_QWORD *)this + 11) = 0;
  v13 = 0;
  *((_QWORD *)this + 12) = 0;
  v14 = *((_DWORD *)this + 32);
  if ( v14 > 0 )
  {
    do
    {
      v15 = *(_QWORD *)(*((_QWORD *)this + 15) + 8LL * (unsigned int)v13);
      if ( v15 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      ++v13;
    }
    while ( v13 < v14 );
  }
  operator delete(*((void **)this + 13));
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  operator delete(*((void **)this + 15));
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  v16 = 0;
  v17 = *((_DWORD *)this + 78);
  v22 = 0;
  if ( v17 > 0 )
  {
    v18 = v17;
    do
    {
      v22 = *(struct _GUID *)(*((_QWORD *)this + 36) + 16LL * v16);
      CDescriptionManager::Hr_DoStopUrlListening((CDescriptionManager *)(2LL * v16), &v22);
      v19 = *(_DWORD **)(*((_QWORD *)this + 38) + 8LL * v16);
      if ( v19 )
      {
        v20 = v19[2];
        for ( j = 0; (int)j < v20; j = (unsigned int)(j + 1) )
          DeregisterService(*(_QWORD *)(*(_QWORD *)v19 + 8 * j), 1);
        CUArray<void *>::`scalar deleting destructor'(v19);
      }
      ++v16;
    }
    while ( (int)v16 < v18 );
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 488);
  }
  operator delete(*((void **)this + 36));
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  operator delete(*((void **)this + 38));
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  CTable<_GUID,_TP_WORK *>::Clear((char *)this + 320);
  operator delete(*((void **)this + 44));
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  operator delete(*((void **)this + 46));
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 568));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  DeleteCriticalSection(v6);
  CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>((char *)this + 352);
  CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>((char *)this + 320);
  CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>((char *)this + 288);
  CTable<_GUID,CTable<CUString,CUString>>::~CTable<_GUID,CTable<CUString,CUString>>((char *)this + 256);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  operator delete(*((void **)this + 25));
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  CTable<_GUID,FileInfo>::~CTable<_GUID,FileInfo>((char *)this + 168);
  CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>((char *)this + 136);
  CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>((char *)this + 104);
  CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>((char *)this + 72);
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((__int64)this + 16);
}

```

## disassembly

```asm
0x180049258  push    rbx
0x18004925a  push    rbp
0x18004925b  push    rsi
0x18004925c  push    rdi
0x18004925d  push    r12
0x18004925f  push    r13
0x180049261  push    r14
0x180049263  push    r15
0x180049265  sub     rsp, 48h
0x180049269  mov     rax, cs:__security_cookie
0x180049270  xor     rax, rsp
0x180049273  mov     [rsp+88h+var_50], rax
0x180049278  mov     rbp, rcx
0x18004927b  mov     rcx, [rcx+1E0h]; hEvent
0x180049282  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180049286  jz      short loc_18004928E
0x180049288  call    cs:__imp_SetEvent
0x18004928e  mov     rcx, [rbp+1D8h]; ptpcg
0x180049295  xor     r13d, r13d
0x180049298  test    rcx, rcx
0x18004929b  jz      short loc_1800492B7
0x18004929d  xor     r8d, r8d; pvCleanupContext
0x1800492a0  lea     edx, [r13+1]; fCancelPendingCallbacks
0x1800492a4  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800492aa  mov     rcx, [rbp+1D8h]; ptpcg
0x1800492b1  call    cs:__imp_CloseThreadpoolCleanupGroup
0x1800492b7  mov     rcx, [rbp+1D0h]; ptpp
0x1800492be  test    rcx, rcx
0x1800492c1  jz      short loc_1800492D0
0x1800492c3  call    cs:__imp_CloseThreadpool
0x1800492c9  mov     [rbp+1D0h], r13
0x1800492d0  mov     rcx, [rbp+1E0h]; hObject
0x1800492d7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800492db  jz      short loc_1800492EE
0x1800492dd  call    cs:__imp_CloseHandle
0x1800492e3  mov     qword ptr [rbp+1E0h], 0FFFFFFFFFFFFFFFFh
0x1800492ee  lea     rbx, [rbp+1E8h]
0x1800492f5  mov     rcx, rbx; lpCriticalSection
0x1800492f8  call    cs:__imp_EnterCriticalSection
0x1800492fe  lea     r14, [rbp+260h]
0x180049305  mov     rsi, [r14]
0x180049308  jmp     short loc_180049333
0x18004930a  mov     rdx, [rsi]
0x18004930d  mov     rdi, rsi
0x180049310  mov     rax, [rsi+8]
0x180049314  mov     rsi, rdx
0x180049317  mov     [rax], rdx
0x18004931a  mov     [rdx+8], rax
0x18004931e  mov     rdx, rdi; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x180049321  call    ?PurgeRegistrationParams@CDescriptionManager@@AEAAXPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::PurgeRegistrationParams(SSDP_SERVICE_REGISTRATION_PARAMS *)
0x180049326  mov     edx, 50h ; 'P'; unsigned __int64
0x18004932b  mov     rcx, rdi; void *
0x18004932e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180049333  cmp     rsi, r14
0x180049336  jnz     short loc_18004930A
0x180049338  mov     rcx, rbx; lpCriticalSection
0x18004933b  call    cs:__imp_LeaveCriticalSection
0x180049341  mov     esi, [rbp+60h]
0x180049344  mov     edi, r13d
0x180049347  test    esi, esi
0x180049349  jle     short loc_180049361
0x18004934b  mov     rcx, [rbp+58h]
0x18004934f  mov     eax, edi
0x180049351  mov     rcx, [rcx+rax*8]; bstrString
0x180049355  call    cs:__imp_SysFreeString
0x18004935b  inc     edi
0x18004935d  cmp     edi, esi
0x18004935f  jl      short loc_18004934B
0x180049361  lea     r15, [rbp+48h]
0x180049365  mov     rcx, [r15]; void *
0x180049368  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004936d  mov     [r15], r13
0x180049370  mov     [r15+8], r13
0x180049374  mov     rcx, [r15+10h]; void *
0x180049378  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004937d  mov     [r15+10h], r13
0x180049381  mov     edi, r13d
0x180049384  mov     [r15+18h], r13
0x180049388  mov     esi, [rbp+80h]
0x18004938e  test    esi, esi
0x180049390  jle     short loc_1800493B3
0x180049392  mov     rax, [rbp+78h]
0x180049396  mov     ecx, edi
0x180049398  mov     rcx, [rax+rcx*8]
0x18004939c  test    rcx, rcx
0x18004939f  jz      short loc_1800493AD
0x1800493a1  mov     rax, [rcx]
0x1800493a4  mov     rax, [rax+10h]
0x1800493a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493ad  inc     edi
0x1800493af  cmp     edi, esi
0x1800493b1  jl      short loc_180049392
0x1800493b3  lea     r12, [rbp+68h]
0x1800493b7  mov     rcx, [r12]; void *
0x1800493bb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800493c0  mov     [r12], r13
0x1800493c4  mov     [r12+8], r13
0x1800493c9  mov     rcx, [r12+10h]; void *
0x1800493ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800493d3  mov     [r12+10h], r13
0x1800493d8  xorps   xmm0, xmm0
0x1800493db  mov     [r12+18h], r13
0x1800493e0  mov     esi, r13d
0x1800493e3  mov     eax, [rbp+138h]
0x1800493e9  movups  xmmword ptr [rsp+88h+var_60.Data1], xmm0
0x1800493ee  test    eax, eax
0x1800493f0  jle     short loc_180049464
0x1800493f2  mov     ebx, eax
0x1800493f4  mov     rax, [rbp+120h]
0x1800493fb  lea     rdx, [rsp+88h+var_60]; struct _GUID *
0x180049400  mov     ecx, esi
0x180049402  add     rcx, rcx; this
0x180049405  mov     edi, esi
0x180049407  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18004940b  movdqu  xmmword ptr [rsp+88h+var_60.Data1], xmm0
0x180049411  call    ?Hr_DoStopUrlListening@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::Hr_DoStopUrlListening(_GUID const &)
0x180049416  mov     rax, [rbp+130h]
0x18004941d  mov     rdi, [rax+rdi*8]
0x180049421  test    rdi, rdi
0x180049424  jz      short loc_180049457
0x180049426  mov     r13d, [rdi+8]
0x18004942a  xor     r14d, r14d
0x18004942d  test    r13d, r13d
0x180049430  jle     short loc_18004944C
0x180049432  mov     rcx, [rdi]
0x180049435  mov     edx, 1
0x18004943a  mov     rcx, [rcx+r14*8]
0x18004943e  call    cs:__imp_DeregisterService
0x180049444  inc     r14d
0x180049447  cmp     r14d, r13d
0x18004944a  jl      short loc_180049432
0x18004944c  mov     rcx, rdi; void *
0x18004944f  call    ??_G?$CUArray@PEAX@@QEAAPEAXI@Z; CUArray<void *>::`scalar deleting destructor'(uint)
0x180049454  xor     r13d, r13d
0x180049457  inc     esi
0x180049459  cmp     esi, ebx
0x18004945b  jl      short loc_1800493F4
0x18004945d  lea     rbx, [rbp+1E8h]
0x180049464  lea     r14, [rbp+120h]
0x18004946b  mov     rcx, [r14]; void *
0x18004946e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180049473  mov     [r14], r13
0x180049476  mov     qword ptr [r14+8], 0
0x18004947e  mov     rcx, [r14+10h]; void *
0x180049482  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180049487  lea     rsi, [rbp+140h]
0x18004948e  mov     [r14+10h], r13
0x180049492  mov     rcx, rsi
0x180049495  mov     qword ptr [r14+18h], 0
0x18004949d  call    ?Clear@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAXXZ; CTable<_GUID,_TP_WORK *>::Clear(void)
0x1800494a2  lea     rdi, [rbp+160h]
0x1800494a9  mov     rcx, [rdi]; void *
0x1800494ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800494b1  mov     [rdi], r13
0x1800494b4  mov     qword ptr [rdi+8], 0
0x1800494bc  mov     rcx, [rdi+10h]; void *
0x1800494c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800494c5  lea     rcx, [rbp+238h]; lpCriticalSection
0x1800494cc  mov     [rdi+10h], r13
0x1800494d0  mov     qword ptr [rdi+18h], 0
0x1800494d8  call    cs:__imp_DeleteCriticalSection
0x1800494de  lea     rcx, [rbp+210h]; lpCriticalSection
0x1800494e5  call    cs:__imp_DeleteCriticalSection
0x1800494eb  mov     rcx, rbx; lpCriticalSection
0x1800494ee  call    cs:__imp_DeleteCriticalSection
0x1800494f4  mov     rcx, rdi
0x1800494f7  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x1800494fc  mov     rcx, rsi
0x1800494ff  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x180049504  mov     rcx, r14
0x180049507  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x18004950c  lea     rcx, [rbp+100h]
0x180049513  call    ??1?$CTable@U_GUID@@V?$CTable@VCUString@@V1@@@@@QEAA@XZ; CTable<_GUID,CTable<CUString,CUString>>::~CTable<_GUID,CTable<CUString,CUString>>(void)
0x180049518  lea     rcx, [rbp+0D8h]; lpCriticalSection
0x18004951f  call    cs:__imp_DeleteCriticalSection
0x180049525  mov     rcx, [rbp+0C8h]; void *
0x18004952c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180049531  lea     rcx, [rbp+0A8h]
0x180049538  mov     [rbp+0C8h], r13
0x18004953f  mov     qword ptr [rbp+0D0h], 0
0x18004954a  call    ??1?$CTable@U_GUID@@UFileInfo@@@@QEAA@XZ; CTable<_GUID,FileInfo>::~CTable<_GUID,FileInfo>(void)
0x18004954f  lea     rcx, [rbp+88h]
0x180049556  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x18004955b  mov     rcx, r12
0x18004955e  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x180049563  mov     rcx, r15
0x180049566  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x18004956b  lea     rcx, [rbp+10h]
0x18004956f  call    ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x180049574  mov     rcx, [rsp+88h+var_50]
0x180049579  xor     rcx, rsp; StackCookie
0x18004957c  call    __security_check_cookie
0x180049581  add     rsp, 48h
0x180049585  pop     r15
0x180049587  pop     r14
0x180049589  pop     r13
0x18004958b  pop     r12
0x18004958d  pop     rdi
0x18004958e  pop     rsi
0x18004958f  pop     rbp
0x180049590  pop     rbx
0x180049591  retn
```
