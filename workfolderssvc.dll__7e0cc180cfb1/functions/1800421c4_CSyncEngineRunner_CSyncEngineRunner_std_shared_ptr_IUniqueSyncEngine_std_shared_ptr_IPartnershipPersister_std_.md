# CSyncEngineRunner::CSyncEngineRunner(std::shared_ptr<IUniqueSyncEngine> &,std::shared_ptr<IPartnershipPersister> &,std::shared_ptr<IProtocolClientFactory> &,ISyncShareManagerProgressCallback *,long,std::shared_ptr<void> &,ushort const *)

- ea: `0x1800421c4`
- end: `0x18004259d`
- name: `??0CSyncEngineRunner@@QEAA@AEAV?$shared_ptr@VIUniqueSyncEngine@@@std@@AEAV?$shared_ptr@VIPartnershipPersister@@@2@AEAV?$shared_ptr@VIProtocolClientFactory@@@2@PEAUISyncShareManagerProgressCallback@@JAEAV?$shared_ptr@X@2@PEBG@Z`
- size: `985`
- prototype: `char *__fastcall(char *, _QWORD *, _QWORD *, _QWORD *, __int64, int, PTP_TIMER pExceptionObject, const WCHAR *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800360ac`

## callees

- `0x180002fa4`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180008bdc`
- `0x180011314`
- `0x1800421c4`
- `0x180043588`
- `0x18004414c`
- `0x180047cb0`
- `0x18004cb74`

## import_xrefs

- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800424d1`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x1800424d1`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800422ea`
- `KERNEL32!CreateThreadpoolTimer` at `0x1800422ea`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004223f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004229b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004223f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004229b`

## string_xrefs

- `0x1800424ba`: `CEcsThreadPool::SetMaximumThreadCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char *__fastcall CSyncEngineRunner::CSyncEngineRunner(
        char *a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        __int64 a5,
        int a6,
        PTP_TIMER pExceptionObject,
        const WCHAR *a8)
{
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // r15
  __int64 v16; // rax
  int v17; // edx
  const WCHAR *v18; // rdx
  _BYTE *v19; // rax
  char v20; // cl
  void (*v21)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *); // rdx
  int v23; // [rsp+20h] [rbp-40h] BYREF
  int v24; // [rsp+24h] [rbp-3Ch]
  char v25; // [rsp+28h] [rbp-38h]
  const char *v26; // [rsp+30h] [rbp-30h]
  __int64 v27; // [rsp+38h] [rbp-28h]
  _DWORD v28[2]; // [rsp+40h] [rbp-20h] BYREF
  char v29; // [rsp+48h] [rbp-18h]
  const char *v30; // [rsp+50h] [rbp-10h]
  __int64 v31; // [rsp+58h] [rbp-8h]

  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  v11 = a3[1];
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *((_QWORD *)a1 + 2) = *a3;
  *((_QWORD *)a1 + 3) = a3[1];
  *((_QWORD *)a1 + 4) = 0;
  *((_QWORD *)a1 + 5) = 0;
  v12 = a4[1];
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  *((_QWORD *)a1 + 4) = *a4;
  *((_QWORD *)a1 + 5) = a4[1];
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  *((_QWORD *)a1 + 11) = 0;
  *((_QWORD *)a1 + 12) = 0;
  v13 = a2[1];
  if ( v13 )
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
  *((_QWORD *)a1 + 11) = *a2;
  *((_QWORD *)a1 + 12) = a2[1];
  *((_QWORD *)a1 + 13) = 0;
  *((_QWORD *)a1 + 14) = 0;
  v14 = operator new(0x48u);
  *v14 = v14;
  v14[1] = v14;
  v14[2] = v14;
  *((_WORD *)v14 + 12) = 257;
  *((_QWORD *)a1 + 13) = v14;
  InitializeCriticalSection((LPCRITICAL_SECTION)a1 + 3);
  *((_QWORD *)a1 + 20) = 0;
  *((_QWORD *)a1 + 21) = 0;
  v15 = pExceptionObject;
  v16 = *((_QWORD *)pExceptionObject + 1);
  if ( v16 )
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
  *((_QWORD *)a1 + 20) = *v15;
  *((_QWORD *)a1 + 21) = v15[1];
  pExceptionObject = CreateThreadpoolTimer(CSyncEngineRunner::ErrorRetryTimerCallback, a1, 0);
  *((_QWORD *)a1 + 22) = 0;
  EcsUniqueHandle<_TP_TIMER *,Win32ThreadPoolTimerDeleter,0>::reset(a1 + 176, &pExceptionObject);
  *((_QWORD *)a1 + 23) = a5;
  *((_OWORD *)a1 + 12) = 0;
  *((_QWORD *)a1 + 26) = 0;
  *((_QWORD *)a1 + 27) = 7;
  *((_WORD *)a1 + 96) = 0;
  *((_QWORD *)a1 + 28) = 0;
  *((_QWORD *)a1 + 29) = 0;
  CBackoffTimerValueProvider::CBackoffTimerValueProvider((CBackoffTimerValueProvider *)(a1 + 240), v17, a6);
  *((_QWORD *)a1 + 32) = 0;
  *((_QWORD *)a1 + 33) = 0;
  *(_OWORD *)(a1 + 344) = 0;
  *(_OWORD *)(a1 + 360) = 0;
  *(_OWORD *)(a1 + 376) = 0;
  *(_OWORD *)(a1 + 392) = 0;
  *((_DWORD *)a1 + 68) = 3;
  *((_QWORD *)a1 + 35) = 0;
  *((_QWORD *)a1 + 36) = 0;
  *((_QWORD *)a1 + 37) = 0;
  *((_QWORD *)a1 + 38) = 0;
  *((_QWORD *)a1 + 39) = 0;
  *((_QWORD *)a1 + 40) = 0;
  *((_DWORD *)a1 + 82) = 0;
  *((_DWORD *)a1 + 83) = 1;
  *((_DWORD *)a1 + 84) = 72;
  v18 = a8;
  if ( !a8 )
    v18 = &Format;
  std::wstring::wstring(a1 + 416, v18);
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_17:
      v20 = 0;
      goto LABEL_18;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids);
      v19 = WPP_GLOBAL_Control;
    }
  }
  if ( (v19[68] & 8) == 0 )
    goto LABEL_17;
  v20 = 1;
  if ( v19[65] < 6u )
    goto LABEL_17;
LABEL_18:
  v24 = 29;
  v25 = v20;
  v26 = "CSyncEngineRunner::CSyncEngineRunner";
  v27 = 0;
  v23 = 0;
  if ( !*a2 )
  {
    v23 = -2147024809;
    HIWORD(v24) = 31;
    LODWORD(pExceptionObject) = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v24) = 31;
  v23 = 0;
  if ( !*a3 )
  {
    v23 = -2147024809;
    HIWORD(v24) = 32;
    LODWORD(pExceptionObject) = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v24) = 32;
  v23 = 0;
  if ( ((*v15 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v23 = -2147024809;
    HIWORD(v24) = 33;
    LODWORD(pExceptionObject) = -2147024809;
    throw (long *)&pExceptionObject;
  }
  LOWORD(v24) = 33;
  v23 = 0;
  if ( !*((_QWORD *)a1 + 22) )
  {
    HIWORD(v24) = 34;
    LODWORD(pExceptionObject) = EcsGetLastFailureAsHRESULT();
    throw (long *)&pExceptionObject;
  }
  v23 = 0;
  LOWORD(v24) = 34;
  CEcsThreadPool::Initialize((CEcsThreadPool *)(a1 + 256));
  v28[0] = 0;
  v28[1] = 208;
  v29 = 0;
  v30 = "CEcsThreadPool::SetMaximumThreadCount";
  v31 = 0;
  SetThreadpoolThreadMaximum(*((PTP_POOL *)a1 + 32), 1u);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)v28);
  a1[408] = CEcsThreadPool::CreateWork((CEcsThreadPool *)(a1 + 256), v21, a1);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v23);
  return a1;
}

```

## disassembly

```asm
0x1800421c4  mov     [rsp-38h+arg_10], rbx
0x1800421c9  mov     [rsp-38h+arg_0], rcx
0x1800421ce  push    rbp
0x1800421cf  push    rsi
0x1800421d0  push    rdi
0x1800421d1  push    r12
0x1800421d3  push    r13
0x1800421d5  push    r14
0x1800421d7  push    r15
0x1800421d9  mov     rbp, rsp
0x1800421dc  sub     rsp, 60h
0x1800421e0  mov     rsi, r8
0x1800421e3  mov     r14, rdx
0x1800421e6  mov     rdi, rcx
0x1800421e9  xor     r13d, r13d
0x1800421ec  mov     [rcx], r13
0x1800421ef  mov     [rcx+8], r13
0x1800421f3  mov     [rcx+10h], r13
0x1800421f7  mov     [rcx+18h], r13
0x1800421fb  mov     rax, [r8+8]
0x1800421ff  test    rax, rax
0x180042202  jz      short loc_180042208
0x180042204  lock inc dword ptr [rax+8]
0x180042208  mov     rax, [r8]
0x18004220b  mov     [rcx+10h], rax
0x18004220f  mov     rax, [r8+8]
0x180042213  mov     [rcx+18h], rax
0x180042217  mov     [rcx+20h], r13
0x18004221b  mov     [rcx+28h], r13
0x18004221f  mov     rax, [r9+8]
0x180042223  test    rax, rax
0x180042226  jz      short loc_18004222C
0x180042228  lock inc dword ptr [rax+8]
0x18004222c  mov     rax, [r9]
0x18004222f  mov     [rcx+20h], rax
0x180042233  mov     rax, [r9+8]
0x180042237  mov     [rcx+28h], rax
0x18004223b  add     rcx, 30h ; '0'; lpCriticalSection
0x18004223f  call    cs:__imp_InitializeCriticalSection
0x180042245  nop
0x180042246  mov     [rdi+58h], r13
0x18004224a  mov     [rdi+60h], r13
0x18004224e  mov     rax, [r14+8]
0x180042252  test    rax, rax
0x180042255  jz      short loc_18004225B
0x180042257  lock inc dword ptr [rax+8]
0x18004225b  mov     rax, [r14]
0x18004225e  mov     [rdi+58h], rax
0x180042262  mov     rax, [r14+8]
0x180042266  mov     [rdi+60h], rax
0x18004226a  lea     rbx, [rdi+68h]
0x18004226e  mov     [rbp+arg_8], rbx
0x180042272  mov     [rbx], r13
0x180042275  mov     [rbx+8], r13
0x180042279  mov     ecx, 48h ; 'H'; Size
0x18004227e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180042283  mov     [rax], rax
0x180042286  mov     [rax+8], rax
0x18004228a  mov     [rax+10h], rax
0x18004228e  mov     word ptr [rax+18h], 101h
0x180042294  mov     [rbx], rax
0x180042297  lea     rcx, [rdi+78h]; lpCriticalSection
0x18004229b  call    cs:__imp_InitializeCriticalSection
0x1800422a1  nop
0x1800422a2  mov     [rdi+0A0h], r13
0x1800422a9  mov     [rdi+0A8h], r13
0x1800422b0  mov     r15, [rbp+pExceptionObject]
0x1800422b4  mov     rax, [r15+8]
0x1800422b8  test    rax, rax
0x1800422bb  jz      short loc_1800422C1
0x1800422bd  lock inc dword ptr [rax+8]
0x1800422c1  mov     rax, [r15]
0x1800422c4  mov     [rdi+0A0h], rax
0x1800422cb  mov     rax, [r15+8]
0x1800422cf  mov     [rdi+0A8h], rax
0x1800422d6  lea     r12, [rdi+0B0h]
0x1800422dd  xor     r8d, r8d; pcbe
0x1800422e0  mov     rdx, rdi; pv
0x1800422e3  lea     rcx, ?ErrorRetryTimerCallback@CSyncEngineRunner@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800422ea  call    cs:__imp_CreateThreadpoolTimer
0x1800422f0  mov     [rbp+pExceptionObject], rax
0x1800422f4  mov     [r12], r13
0x1800422f8  lea     rdx, [rbp+pExceptionObject]
0x1800422fc  mov     rcx, r12
0x1800422ff  call    ?reset@?$EcsUniqueHandle@PEAU_TP_TIMER@@UWin32ThreadPoolTimerDeleter@@$0A@@@QEAAXAEBQEAU_TP_TIMER@@@Z; EcsUniqueHandle<_TP_TIMER *,Win32ThreadPoolTimerDeleter,0>::reset(_TP_TIMER * const &)
0x180042304  nop
0x180042305  mov     rax, [rbp+arg_20]
0x180042309  mov     [rdi+0B8h], rax
0x180042310  xorps   xmm0, xmm0
0x180042313  movups  xmmword ptr [rdi+0C0h], xmm0
0x18004231a  mov     [rdi+0D0h], r13
0x180042321  mov     qword ptr [rdi+0D8h], 7
0x18004232c  mov     [rdi+0C0h], r13w
0x180042334  mov     [rdi+0E0h], r13
0x18004233b  mov     [rdi+0E8h], r13
0x180042342  lea     rcx, [rdi+0F0h]; this
0x180042349  mov     r8d, [rbp+arg_28]; int
0x18004234d  call    ??0CBackoffTimerValueProvider@@QEAA@JJ@Z; CBackoffTimerValueProvider::CBackoffTimerValueProvider(long,long)
0x180042352  lea     rbx, [rdi+100h]
0x180042359  mov     [rbx], r13
0x18004235c  mov     [rbx+8], r13
0x180042360  xorps   xmm0, xmm0
0x180042363  movups  xmmword ptr [rbx+58h], xmm0
0x180042367  movups  xmmword ptr [rbx+68h], xmm0
0x18004236b  movups  xmmword ptr [rbx+78h], xmm0
0x18004236f  movups  xmmword ptr [rbx+88h], xmm0
0x180042376  mov     dword ptr [rbx+10h], 3
0x18004237d  mov     [rbx+18h], r13
0x180042381  mov     [rbx+20h], r13
0x180042385  mov     [rbx+28h], r13
0x180042389  mov     [rbx+30h], r13
0x18004238d  mov     [rbx+38h], r13
0x180042391  mov     [rbx+40h], r13
0x180042395  mov     [rbx+48h], r13d
0x180042399  mov     dword ptr [rbx+4Ch], 1
0x1800423a0  mov     dword ptr [rbx+50h], 48h ; 'H'
0x1800423a7  mov     rdx, [rbp+arg_38]
0x1800423ab  lea     rax, Format
0x1800423b2  test    rdx, rdx
0x1800423b5  cmovz   rdx, rax
0x1800423b9  lea     rcx, [rdi+1A0h]
0x1800423c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800423c5  nop
0x1800423c6  lea     rcx, WPP_GLOBAL_Control
0x1800423cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800423d4  cmp     rax, rcx
0x1800423d7  jz      short loc_180042401
0x1800423d9  test    byte ptr [rax+44h], 8
0x1800423dd  jz      short loc_18004240F
0x1800423df  cmp     byte ptr [rax+41h], 6
0x1800423e3  jb      short loc_180042401
0x1800423e5  mov     edx, 0Ah
0x1800423ea  lea     r8, WPP_dc9db4428004346aee7dbf67e68d245c_Traceguids
0x1800423f1  mov     rcx, [rax+38h]
0x1800423f5  call    WPP_SF_
0x1800423fa  mov     rax, cs:WPP_GLOBAL_Control
0x180042401  test    byte ptr [rax+44h], 8
0x180042405  jz      short loc_18004240F
0x180042407  cmp     byte ptr [rax+41h], 6
0x18004240b  mov     cl, 1
0x18004240d  jnb     short loc_180042412
0x18004240f  mov     cl, r13b
0x180042412  mov     [rbp+var_40], r13d
0x180042416  mov     [rbp+var_3C], 1Dh
0x18004241d  mov     [rbp+var_38], cl
0x180042420  lea     rax, aCsyncenginerun_5; "CSyncEngineRunner::CSyncEngineRunner"
0x180042427  mov     [rbp+var_30], rax
0x18004242b  mov     [rbp+var_28], r13
0x18004242f  mov     eax, [rbp+var_40]
0x180042432  mov     [rbp+var_40], eax
0x180042435  mov     ecx, 1Fh
0x18004243a  cmp     [r14], r13
0x18004243d  jz      loc_18004253D
0x180042443  mov     [rbp+var_40], r13d
0x180042447  mov     word ptr [rbp+var_3C], cx
0x18004244b  mov     [rbp+var_40], r13d
0x18004244f  mov     ecx, 20h ; ' '
0x180042454  cmp     [rsi], r13
0x180042457  jz      loc_18004255D
0x18004245d  mov     [rbp+var_40], r13d
0x180042461  mov     word ptr [rbp+var_3C], cx
0x180042465  mov     [rbp+var_40], r13d
0x180042469  mov     rax, [r15]
0x18004246c  inc     rax
0x18004246f  mov     ecx, 21h ; '!'
0x180042474  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004247a  jz      loc_18004257D
0x180042480  mov     [rbp+var_40], r13d
0x180042484  mov     word ptr [rbp+var_3C], cx
0x180042488  mov     [rbp+var_40], r13d
0x18004248c  cmp     [r12], r13
0x180042490  jz      loc_180042517
0x180042496  mov     [rbp+var_40], r13d
0x18004249a  mov     ecx, 22h ; '"'
0x18004249f  mov     word ptr [rbp+var_3C], cx
0x1800424a3  mov     rcx, rbx; this
0x1800424a6  call    ?Initialize@CEcsThreadPool@@QEAAXXZ; CEcsThreadPool::Initialize(void)
0x1800424ab  mov     [rbp+var_20], r13d
0x1800424af  mov     [rbp+var_1C], 0D0h
0x1800424b6  mov     [rbp+var_18], r13b
0x1800424ba  lea     rax, aCecsthreadpool_3; "CEcsThreadPool::SetMaximumThreadCount"
0x1800424c1  mov     [rbp+var_10], rax
0x1800424c5  mov     [rbp+var_8], r13
0x1800424c9  mov     edx, 1; cthrdMost
0x1800424ce  mov     rcx, [rbx]; ptpp
0x1800424d1  call    cs:__imp_SetThreadpoolThreadMaximum
0x1800424d7  nop
0x1800424d8  lea     rcx, [rbp+var_20]; this
0x1800424dc  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800424e1  mov     r8, rdi; void *
0x1800424e4  mov     rcx, rbx; this
0x1800424e7  call    ?CreateWork@CEcsThreadPool@@QEAAEP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z1@Z; CEcsThreadPool::CreateWork(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x1800424ec  mov     [rdi+198h], al
0x1800424f2  lea     rcx, [rbp+var_40]; this
0x1800424f6  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800424fb  nop
0x1800424fc  mov     rax, rdi
0x1800424ff  mov     rbx, [rsp+60h+arg_10]
0x180042507  add     rsp, 60h
0x18004250b  pop     r15
0x18004250d  pop     r14
0x18004250f  pop     r13
0x180042511  pop     r12
0x180042513  pop     rdi
0x180042514  pop     rsi
0x180042515  pop     rbp
0x180042516  retn
0x180042517  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18004251c  nop
0x18004251d  mov     [rbp+var_40], eax
0x180042520  mov     ecx, 22h ; '"'
0x180042525  mov     word ptr [rbp+var_3C+2], cx
0x180042529  mov     dword ptr [rbp+pExceptionObject], eax
0x18004252c  lea     rdx, _TI1J; pThrowInfo
0x180042533  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180042537  call    _CxxThrowException_0
0x18004253d  mov     eax, 80070057h
0x180042542  mov     [rbp+var_40], eax
0x180042545  mov     word ptr [rbp+var_3C+2], cx
0x180042549  mov     dword ptr [rbp+pExceptionObject], eax
0x18004254c  lea     rdx, _TI1J; pThrowInfo
0x180042553  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180042557  call    _CxxThrowException_0
0x18004255d  mov     eax, 80070057h
0x180042562  mov     [rbp+var_40], eax
0x180042565  mov     word ptr [rbp+var_3C+2], cx
0x180042569  mov     dword ptr [rbp+pExceptionObject], eax
0x18004256c  lea     rdx, _TI1J; pThrowInfo
0x180042573  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180042577  call    _CxxThrowException_0
0x18004257d  mov     eax, 80070057h
0x180042582  mov     [rbp+var_40], eax
0x180042585  mov     word ptr [rbp+var_3C+2], cx
0x180042589  mov     dword ptr [rbp+pExceptionObject], eax
0x18004258c  lea     rdx, _TI1J; pThrowInfo
0x180042593  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180042597  call    _CxxThrowException_0
```
