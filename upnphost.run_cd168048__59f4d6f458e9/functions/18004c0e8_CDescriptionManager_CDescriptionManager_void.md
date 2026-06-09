# CDescriptionManager::~CDescriptionManager(void)

- ea: `0x18004c0e8`
- end: `0x18004c471`
- name: `??1CDescriptionManager@@QEAA@XZ`
- size: `905`
- prototype: `void __fastcall(CDescriptionManager *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003edc8`

## callees

- `0x18000b5c4`
- `0x18000c8e0`
- `0x18000e478`
- `0x180010780`
- `0x18001252c`
- `0x180033118`
- `0x18003a9a0`
- `0x18003cb60`
- `0x18003cb84`
- `0x18004c054`
- `0x18004c09c`
- `0x18004c0e8`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004c118`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004c118`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c1a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c1a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c39e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c3b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c3c0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c3f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c39e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c3b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c3c0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c3f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c1ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c1ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18004c165`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18004c165`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004c14d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18004c14d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004c13a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18004c13a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c185`
- `SSDPAPI!DeregisterService` at `0x18004c2fe`
- `SSDPAPI!DeregisterService` at `0x18004c2fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18004c20f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004c20f`

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
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>((char *)this + 16);
}

```

## disassembly

```asm
0x18004c0e8  push    rbx
0x18004c0ea  push    rbp
0x18004c0eb  push    rsi
0x18004c0ec  push    rdi
0x18004c0ed  push    r12
0x18004c0ef  push    r13
0x18004c0f1  push    r14
0x18004c0f3  push    r15
0x18004c0f5  sub     rsp, 48h
0x18004c0f9  mov     rax, cs:__security_cookie
0x18004c100  xor     rax, rsp
0x18004c103  mov     [rsp+88h+var_50], rax
0x18004c108  mov     rbp, rcx
0x18004c10b  mov     rcx, [rcx+1E0h]; hEvent
0x18004c112  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004c116  jz      short loc_18004C124
0x18004c118  call    cs:__imp_SetEvent
0x18004c11f  nop     dword ptr [rax+rax+00h]
0x18004c124  mov     rcx, [rbp+1D8h]; ptpcg
0x18004c12b  xor     r13d, r13d
0x18004c12e  test    rcx, rcx
0x18004c131  jz      short loc_18004C159
0x18004c133  xor     r8d, r8d; pvCleanupContext
0x18004c136  lea     edx, [r13+1]; fCancelPendingCallbacks
0x18004c13a  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18004c141  nop     dword ptr [rax+rax+00h]
0x18004c146  mov     rcx, [rbp+1D8h]; ptpcg
0x18004c14d  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18004c154  nop     dword ptr [rax+rax+00h]
0x18004c159  mov     rcx, [rbp+1D0h]; ptpp
0x18004c160  test    rcx, rcx
0x18004c163  jz      short loc_18004C178
0x18004c165  call    cs:__imp_CloseThreadpool
0x18004c16c  nop     dword ptr [rax+rax+00h]
0x18004c171  mov     [rbp+1D0h], r13
0x18004c178  mov     rcx, [rbp+1E0h]; hObject
0x18004c17f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004c183  jz      short loc_18004C19C
0x18004c185  call    cs:__imp_CloseHandle
0x18004c18c  nop     dword ptr [rax+rax+00h]
0x18004c191  mov     qword ptr [rbp+1E0h], 0FFFFFFFFFFFFFFFFh
0x18004c19c  lea     rbx, [rbp+1E8h]
0x18004c1a3  mov     rcx, rbx; lpCriticalSection
0x18004c1a6  call    cs:__imp_EnterCriticalSection
0x18004c1ad  nop     dword ptr [rax+rax+00h]
0x18004c1b2  lea     r14, [rbp+260h]
0x18004c1b9  mov     rsi, [r14]
0x18004c1bc  jmp     short loc_18004C1E7
0x18004c1be  mov     rdx, [rsi]
0x18004c1c1  mov     rdi, rsi
0x18004c1c4  mov     rax, [rsi+8]
0x18004c1c8  mov     rsi, rdx
0x18004c1cb  mov     [rax], rdx
0x18004c1ce  mov     [rdx+8], rax
0x18004c1d2  mov     rdx, rdi; struct SSDP_SERVICE_REGISTRATION_PARAMS *
0x18004c1d5  call    ?PurgeRegistrationParams@CDescriptionManager@@AEAAXPEAUSSDP_SERVICE_REGISTRATION_PARAMS@@@Z; CDescriptionManager::PurgeRegistrationParams(SSDP_SERVICE_REGISTRATION_PARAMS *)
0x18004c1da  mov     edx, 50h ; 'P'; unsigned __int64
0x18004c1df  mov     rcx, rdi; void *
0x18004c1e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004c1e7  cmp     rsi, r14
0x18004c1ea  jnz     short loc_18004C1BE
0x18004c1ec  mov     rcx, rbx; lpCriticalSection
0x18004c1ef  call    cs:__imp_LeaveCriticalSection
0x18004c1f6  nop     dword ptr [rax+rax+00h]
0x18004c1fb  mov     esi, [rbp+60h]
0x18004c1fe  mov     edi, r13d
0x18004c201  test    esi, esi
0x18004c203  jle     short loc_18004C221
0x18004c205  mov     rcx, [rbp+58h]
0x18004c209  mov     eax, edi
0x18004c20b  mov     rcx, [rcx+rax*8]; bstrString
0x18004c20f  call    cs:__imp_SysFreeString
0x18004c216  nop     dword ptr [rax+rax+00h]
0x18004c21b  inc     edi
0x18004c21d  cmp     edi, esi
0x18004c21f  jl      short loc_18004C205
0x18004c221  lea     r15, [rbp+48h]
0x18004c225  mov     rcx, [r15]; void *
0x18004c228  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c22d  mov     [r15], r13
0x18004c230  mov     [r15+8], r13
0x18004c234  mov     rcx, [r15+10h]; void *
0x18004c238  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c23d  mov     [r15+10h], r13
0x18004c241  mov     edi, r13d
0x18004c244  mov     [r15+18h], r13
0x18004c248  mov     esi, [rbp+80h]
0x18004c24e  test    esi, esi
0x18004c250  jle     short loc_18004C273
0x18004c252  mov     rax, [rbp+78h]
0x18004c256  mov     ecx, edi
0x18004c258  mov     rcx, [rax+rcx*8]
0x18004c25c  test    rcx, rcx
0x18004c25f  jz      short loc_18004C26D
0x18004c261  mov     rax, [rcx]
0x18004c264  mov     rax, [rax+10h]
0x18004c268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c26d  inc     edi
0x18004c26f  cmp     edi, esi
0x18004c271  jl      short loc_18004C252
0x18004c273  lea     r12, [rbp+68h]
0x18004c277  mov     rcx, [r12]; void *
0x18004c27b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c280  mov     [r12], r13
0x18004c284  mov     [r12+8], r13
0x18004c289  mov     rcx, [r12+10h]; void *
0x18004c28e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c293  mov     [r12+10h], r13
0x18004c298  xorps   xmm0, xmm0
0x18004c29b  mov     [r12+18h], r13
0x18004c2a0  mov     esi, r13d
0x18004c2a3  mov     eax, [rbp+138h]
0x18004c2a9  movups  xmmword ptr [rsp+88h+var_60.Data1], xmm0
0x18004c2ae  test    eax, eax
0x18004c2b0  jle     short loc_18004C32A
0x18004c2b2  mov     ebx, eax
0x18004c2b4  mov     rax, [rbp+120h]
0x18004c2bb  lea     rdx, [rsp+88h+var_60]; struct _GUID *
0x18004c2c0  mov     ecx, esi
0x18004c2c2  add     rcx, rcx; this
0x18004c2c5  mov     edi, esi
0x18004c2c7  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18004c2cb  movdqu  xmmword ptr [rsp+88h+var_60.Data1], xmm0
0x18004c2d1  call    ?Hr_DoStopUrlListening@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::Hr_DoStopUrlListening(_GUID const &)
0x18004c2d6  mov     rax, [rbp+130h]
0x18004c2dd  mov     rdi, [rax+rdi*8]
0x18004c2e1  test    rdi, rdi
0x18004c2e4  jz      short loc_18004C31D
0x18004c2e6  mov     r13d, [rdi+8]
0x18004c2ea  xor     r14d, r14d
0x18004c2ed  test    r13d, r13d
0x18004c2f0  jle     short loc_18004C312
0x18004c2f2  mov     rcx, [rdi]
0x18004c2f5  mov     edx, 1
0x18004c2fa  mov     rcx, [rcx+r14*8]
0x18004c2fe  call    cs:__imp_DeregisterService
0x18004c305  nop     dword ptr [rax+rax+00h]
0x18004c30a  inc     r14d
0x18004c30d  cmp     r14d, r13d
0x18004c310  jl      short loc_18004C2F2
0x18004c312  mov     rcx, rdi; void *
0x18004c315  call    ??_G?$CUArray@PEAX@@QEAAPEAXI@Z; CUArray<void *>::`scalar deleting destructor'(uint)
0x18004c31a  xor     r13d, r13d
0x18004c31d  inc     esi
0x18004c31f  cmp     esi, ebx
0x18004c321  jl      short loc_18004C2B4
0x18004c323  lea     rbx, [rbp+1E8h]
0x18004c32a  lea     r14, [rbp+120h]
0x18004c331  mov     rcx, [r14]; void *
0x18004c334  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c339  mov     [r14], r13
0x18004c33c  mov     qword ptr [r14+8], 0
0x18004c344  mov     rcx, [r14+10h]; void *
0x18004c348  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c34d  lea     rsi, [rbp+140h]
0x18004c354  mov     [r14+10h], r13
0x18004c358  mov     rcx, rsi
0x18004c35b  mov     qword ptr [r14+18h], 0
0x18004c363  call    ?Clear@?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAAXXZ; CTable<_GUID,_TP_WORK *>::Clear(void)
0x18004c368  lea     rdi, [rbp+160h]
0x18004c36f  mov     rcx, [rdi]; void *
0x18004c372  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c377  mov     [rdi], r13
0x18004c37a  mov     qword ptr [rdi+8], 0
0x18004c382  mov     rcx, [rdi+10h]; void *
0x18004c386  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c38b  lea     rcx, [rbp+238h]; lpCriticalSection
0x18004c392  mov     [rdi+10h], r13
0x18004c396  mov     qword ptr [rdi+18h], 0
0x18004c39e  call    cs:__imp_DeleteCriticalSection
0x18004c3a5  nop     dword ptr [rax+rax+00h]
0x18004c3aa  lea     rcx, [rbp+210h]; lpCriticalSection
0x18004c3b1  call    cs:__imp_DeleteCriticalSection
0x18004c3b8  nop     dword ptr [rax+rax+00h]
0x18004c3bd  mov     rcx, rbx; lpCriticalSection
0x18004c3c0  call    cs:__imp_DeleteCriticalSection
0x18004c3c7  nop     dword ptr [rax+rax+00h]
0x18004c3cc  mov     rcx, rdi
0x18004c3cf  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x18004c3d4  mov     rcx, rsi
0x18004c3d7  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x18004c3dc  mov     rcx, r14
0x18004c3df  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x18004c3e4  lea     rcx, [rbp+100h]
0x18004c3eb  call    ??1?$CTable@U_GUID@@V?$CTable@VCUString@@V1@@@@@QEAA@XZ; CTable<_GUID,CTable<CUString,CUString>>::~CTable<_GUID,CTable<CUString,CUString>>(void)
0x18004c3f0  lea     rcx, [rbp+0D8h]; lpCriticalSection
0x18004c3f7  call    cs:__imp_DeleteCriticalSection
0x18004c3fe  nop     dword ptr [rax+rax+00h]
0x18004c403  mov     rcx, [rbp+0C8h]; void *
0x18004c40a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c40f  lea     rcx, [rbp+0A8h]
0x18004c416  mov     [rbp+0C8h], r13
0x18004c41d  mov     qword ptr [rbp+0D0h], 0
0x18004c428  call    ??1?$CTable@U_GUID@@UFileInfo@@@@QEAA@XZ; CTable<_GUID,FileInfo>::~CTable<_GUID,FileInfo>(void)
0x18004c42d  lea     rcx, [rbp+88h]
0x18004c434  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x18004c439  mov     rcx, r12
0x18004c43c  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x18004c441  mov     rcx, r15
0x18004c444  call    ??1?$CTable@U_GUID@@PEAU_TP_WORK@@@@QEAA@XZ; CTable<_GUID,_TP_WORK *>::~CTable<_GUID,_TP_WORK *>(void)
0x18004c449  lea     rcx, [rbp+10h]
0x18004c44d  call    ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x18004c452  mov     rcx, [rsp+88h+var_50]
0x18004c457  xor     rcx, rsp; StackCookie
0x18004c45a  call    __security_check_cookie
0x18004c45f  add     rsp, 48h
0x18004c463  pop     r15
0x18004c465  pop     r14
0x18004c467  pop     r13
0x18004c469  pop     r12
0x18004c46b  pop     rdi
0x18004c46c  pop     rsi
0x18004c46d  pop     rbp
0x18004c46e  pop     rbx
0x18004c46f  retn
```
