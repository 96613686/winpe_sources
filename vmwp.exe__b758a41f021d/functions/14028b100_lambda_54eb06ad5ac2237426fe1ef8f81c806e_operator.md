# _lambda_54eb06ad5ac2237426fe1ef8f81c806e_::operator()

- ea: `0x14028b100`
- end: `0x14028b69e`
- name: `_lambda_54eb06ad5ac2237426fe1ef8f81c806e_::operator()`
- size: `1438`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140284ac0`

## callees

- `0x14003d144`
- `0x14003d828`
- `0x14003d86c`
- `0x140041498`
- `0x140064f4c`
- `0x140078628`
- `0x140087b34`
- `0x14008bdbc`
- `0x1400d2214`
- `0x1401134d8`
- `0x14011ea40`
- `0x14011f6fc`
- `0x140287210`
- `0x140287410`
- `0x1402890c4`
- `0x140289b18`
- `0x14028a014`
- `0x14028a020`
- `0x14028b078`
- `0x14028b100`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028b216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028b2da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028b216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028b2da`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028b24a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028b383`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028b54d`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028b5c7`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028b24a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028b383`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028b54d`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028b5c7`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14028b3e5`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14028b3e5`

## pseudocode

```c
__int64 __fastcall lambda_54eb06ad5ac2237426fe1ef8f81c806e_::operator()(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 *v4; // rsi
  _QWORD *v5; // r14
  int *v6; // r15
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 *v9; // rbx
  char v10; // dl
  int v11; // r12d
  _QWORD *v12; // rax
  unsigned int v13; // ebx
  const struct Vml::VmPerfTraceOperation *v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rax
  int v17; // ebx
  _QWORD *v19; // rcx
  _QWORD *i; // rax
  const char *v21; // r9
  int v22; // [rsp+20h] [rbp-3D8h]
  char v23; // [rsp+30h] [rbp-3C8h]
  char v24; // [rsp+31h] [rbp-3C7h]
  char v25[6]; // [rsp+32h] [rbp-3C6h] BYREF
  int v26[2]; // [rsp+38h] [rbp-3C0h] BYREF
  int v27; // [rsp+40h] [rbp-3B8h]
  _QWORD *v28; // [rsp+48h] [rbp-3B0h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-3A8h]
  __int64 *v30; // [rsp+58h] [rbp-3A0h]
  char v31; // [rsp+60h] [rbp-398h]
  int *v32; // [rsp+70h] [rbp-388h]
  _QWORD *v33; // [rsp+78h] [rbp-380h]
  _BYTE v34[40]; // [rsp+80h] [rbp-378h] BYREF
  _BYTE v35[64]; // [rsp+A8h] [rbp-350h] BYREF
  __int64 v36; // [rsp+E8h] [rbp-310h]
  _BYTE v37[112]; // [rsp+F0h] [rbp-308h] BYREF
  _BYTE v38[40]; // [rsp+160h] [rbp-298h] BYREF
  _BYTE v39[72]; // [rsp+188h] [rbp-270h] BYREF
  __int64 v40; // [rsp+1D0h] [rbp-228h] BYREF
  __int128 v41; // [rsp+1D8h] [rbp-220h]
  _BYTE v42[40]; // [rsp+1F0h] [rbp-208h] BYREF
  _BYTE v43[72]; // [rsp+218h] [rbp-1E0h] BYREF
  _BYTE v44[336]; // [rsp+260h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  v27 = 0;
  v41 = *(_OWORD *)(a2 + 1);
  v2 = *a2;
  v40 = v2;
  if ( !v2 )
    return 2147549183LL;
  v29 = 0;
  _InterlockedAdd((volatile signed __int32 *)(v2 + 40), 1u);
  v30 = &v40;
  v31 = 1;
  memset_0(v44, 0, sizeof(v44));
  VmPerf::StartRelatedActivity_VmWorkerTrace::VDevWorkerThread__GUID___((VmWorkerTrace::VDevWorkerThread *)v44);
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v42,
    *(struct Vml::VmPerfTraceComponent **)(v40 + 16),
    (const struct _GUID *)(v40 + 96),
    (const struct _GUID *)(v40 + 80));
  v4 = 0;
  v5 = (_QWORD *)*((_QWORD *)&v41 + 1);
  v6 = (int *)v41;
LABEL_4:
  v25[0] = 0;
  v23 = 0;
  while ( 1 )
  {
    *(_QWORD *)v26 = 0;
    wil::AcquireSRWLockExclusive(v26, v40 + 64);
    v7 = v40;
    if ( !*(_DWORD *)(v40 + 32) )
    {
      *(_DWORD *)(v40 + 32) = GetCurrentThreadId();
      v7 = v40;
    }
    v8 = v40;
    if ( *(_BYTE *)(v7 + 8) )
      break;
    v9 = **(__int64 ***)(v40 + 56);
    v10 = 0;
LABEL_9:
    v24 = v10;
    while ( 1 )
    {
      v9 = (__int64 *)*v9;
      if ( v9 == **(__int64 ***)(v8 + 56) )
        break;
      if ( *((_DWORD *)v9 + 13) )
      {
        v10 = 1;
        goto LABEL_9;
      }
      if ( !*((_BYTE *)v9 + 63) )
      {
        v23 = 1;
        if ( !*(_DWORD *)(v8 + 112) || (*(_DWORD *)(v8 + 112) & (_DWORD)v9[7]) != *(_DWORD *)(v8 + 112) )
          goto LABEL_20;
        if ( !*(_DWORD *)(v8 + 32) || (v11 = *(_DWORD *)(v8 + 32), v11 == GetCurrentThreadId()) )
        {
          v25[0] = 1;
LABEL_20:
          v12 = (_QWORD *)(v9[2] + 64);
          if ( *(_QWORD *)(v9[2] + 88) > 7u )
            v12 = (_QWORD *)*v12;
          v28 = v12;
          VmWorkerTrace::FoundNodeToProcess<unsigned short const *,bool &>(&v28, v25);
          v4 = v9;
          *((_BYTE *)v9 + 63) = 1;
          v8 = v40;
          v10 = v24;
          break;
        }
        v23 = 0;
        v8 = v40;
        v10 = v24;
      }
    }
    if ( !v10 || v23 )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
      if ( !v23 )
      {
        v13 = v29;
        wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44, v29);
        std::wstring::_Tidy_deallocate(v43);
        VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v44);
        _InterlockedDecrement((volatile signed __int32 *)(v40 + 40));
        return v13;
      }
      v28 = (_QWORD *)v4[2];
      v14 = (const struct Vml::VmPerfTraceOperation *)std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(
                                                        v38,
                                                        &v28,
                                                        v42);
      v32 = v6;
      v33 = v5;
      Vml::VmPerfTraceOperation::VmPerfTraceOperation((Vml::VmPerfTraceOperation *)v34, v14);
      v36 = *((_QWORD *)v14 + 13);
      v15 = v40;
      v26[0] = *v32;
      v28 = (_QWORD *)*v33;
      v16 = Vml::VmPerfTraceOperation::VmPerfTraceOperation(
              (Vml::VmPerfTraceOperation *)v37,
              (const struct Vml::VmPerfTraceOperation *)v34);
      v22 = v26[0];
      v17 = lambda_471742be78fc95ffa3bd838ab9f364e1_::operator()(v15 + 48, v36, v16, v28);
      std::wstring::_Tidy_deallocate(v35);
      std::wstring::_Tidy_deallocate(v39);
      ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(v40, (unsigned int)v17);
      if ( v17 < 0 && *(_BYTE *)(v40 + 9) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x126,
          (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
          (const char *)(unsigned int)v17,
          v22);
      *(_QWORD *)v26 = 0;
      wil::AcquireSRWLockExclusive(v26, v40 + 64);
      if ( !*(_BYTE *)(v40 + 8) )
      {
        v27 |= 3u;
        v19 = (_QWORD *)v4[4];
        for ( i = (_QWORD *)*v19; i != v19; i = (_QWORD *)*i )
          --*(_DWORD *)(i[2] + 52LL);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
        WakeAllConditionVariable((PCONDITION_VARIABLE)(v40 + 72));
        goto LABEL_4;
      }
      break;
    }
    if ( *(_DWORD *)(v8 + 40) == 1 )
    {
      if ( !*(_BYTE *)(v40 + 8) )
      {
        std::_Atomic_integral<int,4>::operator--(v40 + 40);
        std::atomic<long>::operator=(v40 + 28, 2147943531LL);
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::TraceDeviceGraph(v40);
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
          v21);
      }
      break;
    }
    _InterlockedDecrement((volatile signed __int32 *)(v40 + 40));
    SleepConditionVariableSRW((PCONDITION_VARIABLE)(v40 + 72), (PSRWLOCK)(v40 + 64), 0xFFFFFFFF, 0);
    _InterlockedAdd((volatile signed __int32 *)(v40 + 40), 1u);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
  }
  WakeAllConditionVariable((PCONDITION_VARIABLE)(v40 + 72));
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
  std::wstring::_Tidy_deallocate(v43);
  VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v44);
  v31 = 0;
  _InterlockedDecrement((volatile signed __int32 *)(v40 + 40));
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14028b100  push    rbx
0x14028b102  push    rsi
0x14028b103  push    rdi
0x14028b104  push    r12
0x14028b106  push    r14
0x14028b108  push    r15
0x14028b10a  sub     rsp, 3C8h
0x14028b111  mov     rax, cs:__security_cookie
0x14028b118  xor     rax, rsp
0x14028b11b  mov     [rsp+3F8h+var_48], rax
0x14028b123  mov     [rsp+3F8h+var_3B8], 0
0x14028b12b  movups  xmm0, xmmword ptr [rdx+8]
0x14028b12f  movdqu  [rsp+3F8h+var_220], xmm0
0x14028b138  mov     rax, [rdx]
0x14028b13b  mov     [rsp+3F8h+var_228], rax
0x14028b143  test    rax, rax
0x14028b146  jnz     short loc_14028B152
0x14028b148  mov     eax, 8000FFFFh
0x14028b14d  jmp     loc_14028B620
0x14028b152  mov     [rsp+3F8h+var_3A8], 0
0x14028b15a  mov     r12d, 1
0x14028b160  lock add [rax+28h], r12d
0x14028b165  lea     rdi, [rsp+3F8h+var_228]
0x14028b16d  mov     [rsp+3F8h+var_3A0], rdi
0x14028b172  mov     [rsp+3F8h+var_398], r12b
0x14028b177  xor     edx, edx; Val
0x14028b179  mov     r8d, 150h; Size
0x14028b17f  lea     rcx, [rsp+3F8h+var_198]; void *
0x14028b187  call    memset_0
0x14028b18c  mov     rdx, [rsp+3F8h+var_228]
0x14028b194  lea     r8, [rdx+60h]
0x14028b198  add     rdx, 50h ; 'P'
0x14028b19c  lea     rcx, [rsp+3F8h+var_198]; this
0x14028b1a4  call    VmPerf__StartRelatedActivity_VmWorkerTrace__VDevWorkerThread__GUID___
0x14028b1a9  nop
0x14028b1aa  mov     rdx, [rsp+3F8h+var_228]
0x14028b1b2  lea     r9, [rdx+50h]; struct _GUID *
0x14028b1b6  lea     r8, [rdx+60h]; struct _GUID *
0x14028b1ba  mov     rdx, [rdx+10h]; struct Vml::VmPerfTraceComponent *
0x14028b1be  lea     rcx, [rsp+3F8h+var_208]; this
0x14028b1c6  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14028b1cb  nop
0x14028b1cc  xor     esi, esi
0x14028b1ce  mov     r14, qword ptr [rsp+3F8h+var_220+8]
0x14028b1d6  mov     r15, qword ptr [rsp+3F8h+var_220]
0x14028b1de  mov     [rsp+3F8h+var_3C6], 0
0x14028b1e3  xor     bl, bl
0x14028b1e5  mov     [rsp+3F8h+var_3C8], bl
0x14028b1e9  mov     qword ptr [rsp+3F8h+var_3C0], 0
0x14028b1f2  mov     rdx, [rsp+3F8h+var_228]
0x14028b1fa  add     rdx, 40h ; '@'
0x14028b1fe  lea     rcx, [rsp+3F8h+var_3C0]
0x14028b203  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14028b208  mov     rax, [rsp+3F8h+var_228]
0x14028b210  cmp     dword ptr [rax+20h], 0
0x14028b214  jnz     short loc_14028B237
0x14028b216  call    cs:__imp_GetCurrentThreadId
0x14028b21d  nop     dword ptr [rax+rax+00h]
0x14028b222  mov     ecx, eax
0x14028b224  mov     rax, [rsp+3F8h+var_228]
0x14028b22c  mov     [rax+20h], ecx
0x14028b22f  mov     rax, [rsp+3F8h+var_228]
0x14028b237  mov     al, [rax+8]
0x14028b23a  mov     rcx, [rsp+3F8h+var_228]
0x14028b242  test    al, al
0x14028b244  jz      short loc_14028B291
0x14028b246  add     rcx, 48h ; 'H'; ConditionVariable
0x14028b24a  call    cs:__imp_WakeAllConditionVariable
0x14028b251  nop     dword ptr [rax+rax+00h]
0x14028b256  lea     rcx, [rsp+3F8h+var_3C0]
0x14028b25b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028b260  nop
0x14028b261  lea     rcx, [rsp+3F8h+var_1E0]
0x14028b269  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028b26e  nop
0x14028b26f  lea     rcx, [rsp+3F8h+var_198]; this
0x14028b277  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028b27c  nop
0x14028b27d  mov     [rsp+3F8h+var_398], 0
0x14028b282  mov     rax, [rdi]
0x14028b285  lock dec dword ptr [rax+28h]
0x14028b289  or      eax, 0FFFFFFFFh
0x14028b28c  jmp     loc_14028B620
0x14028b291  mov     rax, [rcx+38h]
0x14028b295  mov     rbx, [rax]
0x14028b298  xor     dl, dl
0x14028b29a  mov     [rsp+3F8h+var_3C7], dl
0x14028b29e  mov     rbx, [rbx]
0x14028b2a1  mov     rax, [rcx+38h]
0x14028b2a5  cmp     rbx, [rax]
0x14028b2a8  jz      loc_14028B347
0x14028b2ae  cmp     dword ptr [rbx+34h], 0
0x14028b2b2  jnz     short loc_14028B304
0x14028b2b4  cmp     byte ptr [rbx+3Fh], 0
0x14028b2b8  jnz     short loc_14028B29E
0x14028b2ba  mov     [rsp+3F8h+var_3C8], r12b
0x14028b2bf  cmp     dword ptr [rcx+70h], 0
0x14028b2c3  jz      short loc_14028B30E
0x14028b2c5  mov     eax, [rbx+38h]
0x14028b2c8  and     eax, [rcx+70h]
0x14028b2cb  cmp     eax, [rcx+70h]
0x14028b2ce  jnz     short loc_14028B30E
0x14028b2d0  cmp     dword ptr [rcx+20h], 0
0x14028b2d4  jz      short loc_14028B309
0x14028b2d6  mov     r12d, [rcx+20h]
0x14028b2da  call    cs:__imp_GetCurrentThreadId
0x14028b2e1  nop     dword ptr [rax+rax+00h]
0x14028b2e6  cmp     r12d, eax
0x14028b2e9  mov     r12d, 1
0x14028b2ef  jz      short loc_14028B309
0x14028b2f1  mov     [rsp+3F8h+var_3C8], 0
0x14028b2f6  mov     rcx, [rsp+3F8h+var_228]
0x14028b2fe  mov     dl, [rsp+3F8h+var_3C7]
0x14028b302  jmp     short loc_14028B29E
0x14028b304  mov     dl, r12b
0x14028b307  jmp     short loc_14028B29A
0x14028b309  mov     [rsp+3F8h+var_3C6], r12b
0x14028b30e  mov     rax, [rbx+10h]
0x14028b312  add     rax, 40h ; '@'
0x14028b316  cmp     qword ptr [rax+18h], 7
0x14028b31b  jbe     short loc_14028B320
0x14028b31d  mov     rax, [rax]
0x14028b320  mov     [rsp+3F8h+var_3B0], rax
0x14028b325  lea     rdx, [rsp+3F8h+var_3C6]
0x14028b32a  lea     rcx, [rsp+3F8h+var_3B0]
0x14028b32f  call    ??$FoundNodeToProcess@PEBGAEA_N@VmWorkerTrace@@SAX$$QEAPEBGAEA_N@Z; VmWorkerTrace::FoundNodeToProcess<ushort const *,bool &>(ushort const * &&,bool &)
0x14028b334  mov     rsi, rbx
0x14028b337  mov     [rbx+3Fh], r12b
0x14028b33b  mov     rcx, [rsp+3F8h+var_228]
0x14028b343  mov     dl, [rsp+3F8h+var_3C7]
0x14028b347  mov     bl, [rsp+3F8h+var_3C8]
0x14028b34b  test    dl, dl
0x14028b34d  jz      loc_14028B40D
0x14028b353  test    bl, bl
0x14028b355  jnz     loc_14028B40D
0x14028b35b  mov     eax, [rcx+28h]
0x14028b35e  nop
0x14028b35f  cmp     eax, r12d
0x14028b362  mov     rax, [rsp+3F8h+var_228]
0x14028b36a  jnz     short loc_14028B3CA
0x14028b36c  mov     cl, [rax+8]
0x14028b36f  test    cl, cl
0x14028b371  mov     rcx, [rsp+3F8h+var_228]
0x14028b379  jz      loc_14028B642
0x14028b37f  add     rcx, 48h ; 'H'; ConditionVariable
0x14028b383  call    cs:__imp_WakeAllConditionVariable
0x14028b38a  nop     dword ptr [rax+rax+00h]
0x14028b38f  lea     rcx, [rsp+3F8h+var_3C0]
0x14028b394  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028b399  nop
0x14028b39a  lea     rcx, [rsp+3F8h+var_1E0]
0x14028b3a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028b3a7  nop
0x14028b3a8  lea     rcx, [rsp+3F8h+var_198]; this
0x14028b3b0  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028b3b5  nop
0x14028b3b6  mov     [rsp+3F8h+var_398], 0
0x14028b3bb  mov     rax, [rdi]
0x14028b3be  lock dec dword ptr [rax+28h]
0x14028b3c2  or      eax, 0FFFFFFFFh
0x14028b3c5  jmp     loc_14028B620
0x14028b3ca  lock dec dword ptr [rax+28h]
0x14028b3ce  mov     rcx, [rsp+3F8h+var_228]
0x14028b3d6  lea     rdx, [rcx+40h]; SRWLock
0x14028b3da  add     rcx, 48h ; 'H'; ConditionVariable
0x14028b3de  xor     r9d, r9d; Flags
0x14028b3e1  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x14028b3e5  call    cs:__imp_SleepConditionVariableSRW
0x14028b3ec  nop     dword ptr [rax+rax+00h]
0x14028b3f1  mov     rax, [rsp+3F8h+var_228]
0x14028b3f9  lock add [rax+28h], r12d
0x14028b3fe  lea     rcx, [rsp+3F8h+var_3C0]
0x14028b403  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028b408  jmp     loc_14028B1E9
0x14028b40d  lea     rcx, [rsp+3F8h+var_3C0]
0x14028b412  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028b417  test    bl, bl
0x14028b419  jnz     short loc_14028B424
0x14028b41b  mov     ebx, [rsp+3F8h+var_3A8]
0x14028b41f  jmp     loc_14028B5E6
0x14028b424  mov     rax, [rsi+10h]
0x14028b428  mov     [rsp+3F8h+var_3B0], rax
0x14028b42d  lea     r8, [rsp+3F8h+var_208]
0x14028b435  lea     rdx, [rsp+3F8h+var_3B0]
0x14028b43a  lea     rcx, [rsp+3F8h+var_298]
0x14028b442  call    ??$make_tuple@PEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@std@@YA?AV?$tuple@PEAUVirtualDeviceInformation@@VVmPerfTraceOperation@Vml@@@0@$$QEAPEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@Z; std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(VirtualDeviceInformation * &&,Vml::VmPerfTraceOperation &)
0x14028b447  mov     rbx, rax
0x14028b44a  mov     [rsp+3F8h+var_388], r15
0x14028b44f  mov     [rsp+3F8h+var_380], r14
0x14028b454  mov     rdx, rax; struct Vml::VmPerfTraceOperation *
0x14028b457  lea     rcx, [rsp+3F8h+var_378]; this
0x14028b45f  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x14028b464  mov     rax, [rbx+68h]
0x14028b468  mov     [rsp+3F8h+var_310], rax
0x14028b470  mov     rbx, [rsp+3F8h+var_228]
0x14028b478  mov     rax, [rsp+3F8h+var_388]
0x14028b47d  mov     eax, [rax]
0x14028b47f  mov     [rsp+3F8h+var_3C0], eax
0x14028b483  mov     rax, [rsp+3F8h+var_380]
0x14028b488  mov     rax, [rax]
0x14028b48b  mov     [rsp+3F8h+var_3B0], rax
0x14028b490  lea     rdx, [rsp+3F8h+var_378]; struct Vml::VmPerfTraceOperation *
0x14028b498  lea     rcx, [rsp+3F8h+var_308]; this
0x14028b4a0  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x14028b4a5  mov     r8, rax
0x14028b4a8  mov     eax, [rsp+3F8h+var_3C0]
0x14028b4ac  mov     [rsp+3F8h+var_3D8], eax; int
0x14028b4b0  mov     r9, [rsp+3F8h+var_3B0]
0x14028b4b5  mov     rdx, [rsp+3F8h+var_310]
0x14028b4bd  lea     rcx, [rbx+30h]
0x14028b4c1  call    _lambda_471742be78fc95ffa3bd838ab9f364e1___operator__
0x14028b4c6  mov     ebx, eax
0x14028b4c8  lea     rcx, [rsp+3F8h+var_350]
0x14028b4d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028b4d5  nop
0x14028b4d6  lea     rcx, [rsp+3F8h+var_270]
0x14028b4de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028b4e3  mov     edx, ebx
0x14028b4e5  mov     rcx, [rsp+3F8h+var_228]
0x14028b4ed  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x14028b4f2  mov     rdx, [rsp+3F8h+var_228]
0x14028b4fa  test    ebx, ebx
0x14028b4fc  jns     short loc_14028B509
0x14028b4fe  cmp     byte ptr [rdx+9], 0
0x14028b502  jz      short loc_14028B509
0x14028b504  mov     al, r12b
0x14028b507  jmp     short loc_14028B50B
0x14028b509  xor     al, al
0x14028b50b  mov     rcx, [rsp+3F8h]; this
0x14028b513  test    al, al
0x14028b515  jnz     loc_14028B688
0x14028b51b  mov     qword ptr [rsp+3F8h+var_3C0], 0
0x14028b524  add     rdx, 40h ; '@'
0x14028b528  lea     rcx, [rsp+3F8h+var_3C0]
0x14028b52d  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14028b532  mov     rax, [rsp+3F8h+var_228]
0x14028b53a  mov     cl, [rax+8]
0x14028b53d  test    cl, cl
0x14028b53f  jz      short loc_14028B594
0x14028b541  mov     rcx, [rsp+3F8h+var_228]
0x14028b549  add     rcx, 48h ; 'H'; ConditionVariable
0x14028b54d  call    cs:__imp_WakeAllConditionVariable
0x14028b554  nop     dword ptr [rax+rax+00h]
0x14028b559  lea     rcx, [rsp+3F8h+var_3C0]
0x14028b55e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028b563  nop
0x14028b564  lea     rcx, [rsp+3F8h+var_1E0]
0x14028b56c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028b571  nop
0x14028b572  lea     rcx, [rsp+3F8h+var_198]; this
0x14028b57a  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028b57f  nop
0x14028b580  mov     [rsp+3F8h+var_398], 0
0x14028b585  mov     rax, [rdi]
0x14028b588  lock dec dword ptr [rax+28h]
0x14028b58c  or      eax, 0FFFFFFFFh
0x14028b58f  jmp     loc_14028B620
0x14028b594  or      [rsp+3F8h+var_3B8], 3
0x14028b599  mov     rcx, [rsi+20h]
0x14028b59d  mov     rax, [rcx]
0x14028b5a0  cmp     rax, rcx
0x14028b5a3  jz      short loc_14028B5B1
0x14028b5a5  mov     rdx, [rax+10h]
0x14028b5a9  dec     dword ptr [rdx+34h]
0x14028b5ac  mov     rax, [rax]
0x14028b5af  jmp     short loc_14028B5A0
0x14028b5b1  lea     rcx, [rsp+3F8h+var_3C0]
0x14028b5b6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028b5bb  mov     rcx, [rsp+3F8h+var_228]
0x14028b5c3  add     rcx, 48h ; 'H'; ConditionVariable
0x14028b5c7  call    cs:__imp_WakeAllConditionVariable
0x14028b5ce  nop     dword ptr [rax+rax+00h]
0x14028b5d3  jmp     loc_14028B1DE
0x14028b5d8  mov     ebx, [rsp+3F8h+var_3C0]
0x14028b5dc  mov     r12b, [rsp+3F8h+var_398]
0x14028b5e1  mov     rdi, [rsp+3F8h+var_3A0]
0x14028b5e6  mov     edx, ebx
0x14028b5e8  lea     rcx, [rsp+3F8h+var_198]
0x14028b5f0  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14028b5f5  nop
0x14028b5f6  lea     rcx, [rsp+3F8h+var_1E0]
0x14028b5fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028b603  nop
0x14028b604  lea     rcx, [rsp+3F8h+var_198]; this
0x14028b60c  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028b611  nop
0x14028b612  test    r12b, r12b
0x14028b615  jz      short loc_14028B61E
0x14028b617  mov     rcx, [rdi]
0x14028b61a  lock dec dword ptr [rcx+28h]
0x14028b61e  mov     eax, ebx
0x14028b620  mov     rcx, [rsp+3F8h+var_48]
0x14028b628  xor     rcx, rsp; StackCookie
0x14028b62b  call    __security_check_cookie
0x14028b630  add     rsp, 3C8h
0x14028b637  pop     r15
0x14028b639  pop     r14
0x14028b63b  pop     r12
0x14028b63d  pop     rdi
0x14028b63e  pop     rsi
  ... truncated ...
```
