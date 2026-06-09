# _lambda_9f59de74433dd7d8ff82dcfb6a7f49d9_::operator()

- ea: `0x14028c2b4`
- end: `0x14028c80b`
- name: `_lambda_9f59de74433dd7d8ff82dcfb6a7f49d9_::operator()`
- size: `1367`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140284af0`

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
- `0x14028c2b4`
- `0x14028c938`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028c3ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028c475`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028c3ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028c475`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c3e2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c518`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c6ba`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c734`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c3e2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c518`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c6ba`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c734`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14028c57a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14028c57a`

## pseudocode

```c
__int64 __fastcall lambda_9f59de74433dd7d8ff82dcfb6a7f49d9_::operator()(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  unsigned int *v4; // r14
  __int64 *v5; // rsi
  char v6; // r15
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 *v9; // rbx
  char v10; // dl
  int v11; // r15d
  _QWORD *v12; // rax
  const struct Vml::VmPerfTraceOperation *v13; // rbx
  __int64 v14; // rbx
  unsigned int v15; // r15d
  __int64 v16; // rax
  int v17; // ebx
  _QWORD *v19; // rcx
  _QWORD *i; // rax
  unsigned int v21; // ebx
  const char *v22; // r9
  int v23; // [rsp+20h] [rbp-3A8h] BYREF
  __int64 v24; // [rsp+28h] [rbp-3A0h] BYREF
  unsigned int v25; // [rsp+30h] [rbp-398h]
  int v26; // [rsp+34h] [rbp-394h]
  _QWORD v27[2]; // [rsp+38h] [rbp-390h] BYREF
  char v28; // [rsp+48h] [rbp-380h]
  unsigned int *v29; // [rsp+50h] [rbp-378h]
  _BYTE v30[40]; // [rsp+58h] [rbp-370h] BYREF
  _BYTE v31[64]; // [rsp+80h] [rbp-348h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-308h]
  _BYTE v33[112]; // [rsp+D0h] [rbp-2F8h] BYREF
  _BYTE v34[40]; // [rsp+140h] [rbp-288h] BYREF
  _BYTE v35[72]; // [rsp+168h] [rbp-260h] BYREF
  __int64 v36; // [rsp+1B0h] [rbp-218h] BYREF
  _BYTE v37[40]; // [rsp+1C0h] [rbp-208h] BYREF
  _BYTE v38[72]; // [rsp+1E8h] [rbp-1E0h] BYREF
  _BYTE v39[336]; // [rsp+230h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  v26 = 0;
  v2 = *a2;
  v36 = v2;
  if ( !v2 )
    return 2147549183LL;
  v25 = 0;
  v4 = (unsigned int *)a2[1];
  _InterlockedAdd((volatile signed __int32 *)(v2 + 40), 1u);
  v27[1] = &v36;
  v28 = 1;
  memset_0(v39, 0, sizeof(v39));
  VmPerf::StartRelatedActivity_VmWorkerTrace::VDevWorkerThread__GUID___((VmWorkerTrace::VDevWorkerThread *)v39);
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v37,
    *(struct Vml::VmPerfTraceComponent **)(v36 + 16),
    (const struct _GUID *)(v36 + 96),
    (const struct _GUID *)(v36 + 80));
  v5 = 0;
  while ( 1 )
  {
    BYTE1(v23) = 0;
    v6 = 0;
    while ( 1 )
    {
      v24 = 0;
      wil::AcquireSRWLockExclusive(&v24, v36 + 64);
      v7 = v36;
      if ( !*(_DWORD *)(v36 + 32) )
      {
        *(_DWORD *)(v36 + 32) = GetCurrentThreadId();
        v7 = v36;
      }
      v8 = v36;
      if ( *(_BYTE *)(v7 + 8) )
        goto LABEL_37;
      v9 = **(__int64 ***)(v36 + 56);
      v10 = 0;
LABEL_9:
      LOBYTE(v23) = v10;
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
          v6 = 1;
          BYTE2(v23) = 1;
          if ( !*(_DWORD *)(v8 + 112) || (*(_DWORD *)(v8 + 112) & (_DWORD)v9[7]) != *(_DWORD *)(v8 + 112) )
            goto LABEL_21;
          if ( !*(_DWORD *)(v8 + 32) )
            goto LABEL_20;
          v11 = *(_DWORD *)(v8 + 32);
          if ( v11 == GetCurrentThreadId() )
          {
            v6 = BYTE2(v23);
LABEL_20:
            BYTE1(v23) = 1;
LABEL_21:
            v12 = (_QWORD *)(v9[2] + 64);
            if ( *(_QWORD *)(v9[2] + 88) > 7u )
              v12 = (_QWORD *)*v12;
            v27[0] = v12;
            VmWorkerTrace::FoundNodeToProcess<unsigned short const *,bool &>(v27, (char *)&v23 + 1);
            v5 = v9;
            *((_BYTE *)v9 + 63) = 1;
            v8 = v36;
            v10 = v23;
            break;
          }
          v6 = 0;
          v8 = v36;
          v10 = v23;
        }
      }
      if ( !v10 || v6 )
        break;
      if ( *(_DWORD *)(v8 + 40) == 1 )
      {
        if ( !*(_BYTE *)(v36 + 8) )
        {
          std::_Atomic_integral<int,4>::operator--(v36 + 40);
          std::atomic<long>::operator=(v36 + 28, 2147943531LL);
          ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::TraceDeviceGraph(v36);
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x107,
            (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
            v22);
        }
LABEL_37:
        WakeAllConditionVariable((PCONDITION_VARIABLE)(v36 + 72));
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
        std::wstring::_Tidy_deallocate(v38);
        VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v39);
        v28 = 0;
        _InterlockedDecrement((volatile signed __int32 *)(v36 + 40));
        return 0xFFFFFFFFLL;
      }
      _InterlockedDecrement((volatile signed __int32 *)(v36 + 40));
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(v36 + 72), (PSRWLOCK)(v36 + 64), 0xFFFFFFFF, 0);
      _InterlockedAdd((volatile signed __int32 *)(v36 + 40), 1u);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    if ( !v6 )
      break;
    v27[0] = v5[2];
    v13 = (const struct Vml::VmPerfTraceOperation *)std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(
                                                      v34,
                                                      v27,
                                                      v37);
    v29 = v4;
    Vml::VmPerfTraceOperation::VmPerfTraceOperation((Vml::VmPerfTraceOperation *)v30, v13);
    v32 = *((_QWORD *)v13 + 13);
    v14 = v36;
    v15 = *v29;
    v16 = Vml::VmPerfTraceOperation::VmPerfTraceOperation(
            (Vml::VmPerfTraceOperation *)v33,
            (const struct Vml::VmPerfTraceOperation *)v30);
    v17 = lambda_b37d4be99a1b4a294a8337e4a985c351_::operator()(v14 + 48, v32, v16, v15);
    std::wstring::_Tidy_deallocate(v31);
    std::wstring::_Tidy_deallocate(v35);
    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(v36, (unsigned int)v17);
    if ( v17 < 0 && *(_BYTE *)(v36 + 9) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x126,
        (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
        (const char *)(unsigned int)v17,
        v23);
    v24 = 0;
    wil::AcquireSRWLockExclusive(&v24, v36 + 64);
    if ( *(_BYTE *)(v36 + 8) )
      goto LABEL_37;
    v26 |= 3u;
    v19 = (_QWORD *)v5[4];
    for ( i = (_QWORD *)*v19; i != v19; i = (_QWORD *)*i )
      --*(_DWORD *)(i[2] + 52LL);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    WakeAllConditionVariable((PCONDITION_VARIABLE)(v36 + 72));
  }
  v21 = v25;
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v39, v25);
  std::wstring::_Tidy_deallocate(v38);
  VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v39);
  _InterlockedDecrement((volatile signed __int32 *)(v36 + 40));
  return v21;
}

```

## disassembly

```asm
0x14028c2b4  push    rbx
0x14028c2b6  push    rsi
0x14028c2b7  push    rdi
0x14028c2b8  push    r13
0x14028c2ba  push    r14
0x14028c2bc  push    r15
0x14028c2be  sub     rsp, 398h
0x14028c2c5  mov     rax, cs:__security_cookie
0x14028c2cc  xor     rax, rsp
0x14028c2cf  mov     [rsp+3C8h+var_48], rax
0x14028c2d7  mov     [rsp+3C8h+var_394], 0
0x14028c2df  mov     rax, [rdx]
0x14028c2e2  mov     [rsp+3C8h+var_218], rax
0x14028c2ea  test    rax, rax
0x14028c2ed  jnz     short loc_14028C2F9
0x14028c2ef  mov     eax, 8000FFFFh
0x14028c2f4  jmp     loc_14028C78D
0x14028c2f9  mov     [rsp+3C8h+var_398], 0
0x14028c301  mov     r14, [rdx+8]
0x14028c305  mov     r13d, 1
0x14028c30b  lock add [rax+28h], r13d
0x14028c310  lea     rdi, [rsp+3C8h+var_218]
0x14028c318  mov     [rsp+3C8h+var_388], rdi
0x14028c31d  mov     [rsp+3C8h+var_380], r13b
0x14028c322  xor     edx, edx; Val
0x14028c324  mov     r8d, 150h; Size
0x14028c32a  lea     rcx, [rsp+3C8h+var_198]; void *
0x14028c332  call    memset_0
0x14028c337  mov     rdx, [rsp+3C8h+var_218]
0x14028c33f  lea     r8, [rdx+60h]
0x14028c343  add     rdx, 50h ; 'P'
0x14028c347  lea     rcx, [rsp+3C8h+var_198]; this
0x14028c34f  call    VmPerf__StartRelatedActivity_VmWorkerTrace__VDevWorkerThread__GUID___
0x14028c354  nop
0x14028c355  mov     rdx, [rsp+3C8h+var_218]
0x14028c35d  lea     r9, [rdx+50h]; struct _GUID *
0x14028c361  lea     r8, [rdx+60h]; struct _GUID *
0x14028c365  mov     rdx, [rdx+10h]; struct Vml::VmPerfTraceComponent *
0x14028c369  lea     rcx, [rsp+3C8h+var_208]; this
0x14028c371  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14028c376  nop
0x14028c377  xor     esi, esi
0x14028c379  mov     byte ptr [rsp+3C8h+var_3A8+1], 0
0x14028c37e  xor     r15b, r15b
0x14028c381  mov     [rsp+3C8h+var_3A0], 0
0x14028c38a  mov     rdx, [rsp+3C8h+var_218]
0x14028c392  add     rdx, 40h ; '@'
0x14028c396  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c39b  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14028c3a0  mov     rax, [rsp+3C8h+var_218]
0x14028c3a8  cmp     dword ptr [rax+20h], 0
0x14028c3ac  jnz     short loc_14028C3CF
0x14028c3ae  call    cs:__imp_GetCurrentThreadId
0x14028c3b5  nop     dword ptr [rax+rax+00h]
0x14028c3ba  mov     ecx, eax
0x14028c3bc  mov     rax, [rsp+3C8h+var_218]
0x14028c3c4  mov     [rax+20h], ecx
0x14028c3c7  mov     rax, [rsp+3C8h+var_218]
0x14028c3cf  mov     al, [rax+8]
0x14028c3d2  mov     rcx, [rsp+3C8h+var_218]
0x14028c3da  test    al, al
0x14028c3dc  jz      short loc_14028C429
0x14028c3de  add     rcx, 48h ; 'H'; ConditionVariable
0x14028c3e2  call    cs:__imp_WakeAllConditionVariable
0x14028c3e9  nop     dword ptr [rax+rax+00h]
0x14028c3ee  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c3f3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028c3f8  nop
0x14028c3f9  lea     rcx, [rsp+3C8h+var_1E0]
0x14028c401  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028c406  nop
0x14028c407  lea     rcx, [rsp+3C8h+var_198]; this
0x14028c40f  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028c414  nop
0x14028c415  mov     [rsp+3C8h+var_380], 0
0x14028c41a  mov     rax, [rdi]
0x14028c41d  lock dec dword ptr [rax+28h]
0x14028c421  or      eax, 0FFFFFFFFh
0x14028c424  jmp     loc_14028C78D
0x14028c429  mov     rax, [rcx+38h]
0x14028c42d  mov     rbx, [rax]
0x14028c430  xor     dl, dl
0x14028c432  mov     byte ptr [rsp+3C8h+var_3A8], dl; int
0x14028c436  mov     rbx, [rbx]
0x14028c439  mov     rax, [rcx+38h]
0x14028c43d  cmp     rbx, [rax]
0x14028c440  jz      loc_14028C4DF
0x14028c446  cmp     dword ptr [rbx+34h], 0
0x14028c44a  jnz     short loc_14028C497
0x14028c44c  cmp     byte ptr [rbx+3Fh], 0
0x14028c450  jnz     short loc_14028C436
0x14028c452  mov     r15b, r13b
0x14028c455  mov     byte ptr [rsp+3C8h+var_3A8+2], r13b
0x14028c45a  cmp     dword ptr [rcx+70h], 0
0x14028c45e  jz      short loc_14028C4A6
0x14028c460  mov     eax, [rbx+38h]
0x14028c463  and     eax, [rcx+70h]
0x14028c466  cmp     eax, [rcx+70h]
0x14028c469  jnz     short loc_14028C4A6
0x14028c46b  cmp     dword ptr [rcx+20h], 0
0x14028c46f  jz      short loc_14028C4A1
0x14028c471  mov     r15d, [rcx+20h]
0x14028c475  call    cs:__imp_GetCurrentThreadId
0x14028c47c  nop     dword ptr [rax+rax+00h]
0x14028c481  cmp     r15d, eax
0x14028c484  jz      short loc_14028C49C
0x14028c486  xor     r15b, r15b
0x14028c489  mov     rcx, [rsp+3C8h+var_218]
0x14028c491  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x14028c495  jmp     short loc_14028C436
0x14028c497  mov     dl, r13b
0x14028c49a  jmp     short loc_14028C432
0x14028c49c  mov     r15b, byte ptr [rsp+3C8h+var_3A8+2]
0x14028c4a1  mov     byte ptr [rsp+3C8h+var_3A8+1], r13b
0x14028c4a6  mov     rax, [rbx+10h]
0x14028c4aa  add     rax, 40h ; '@'
0x14028c4ae  cmp     qword ptr [rax+18h], 7
0x14028c4b3  jbe     short loc_14028C4B8
0x14028c4b5  mov     rax, [rax]
0x14028c4b8  mov     [rsp+3C8h+var_390], rax
0x14028c4bd  lea     rdx, [rsp+3C8h+var_3A8+1]
0x14028c4c2  lea     rcx, [rsp+3C8h+var_390]
0x14028c4c7  call    ??$FoundNodeToProcess@PEBGAEA_N@VmWorkerTrace@@SAX$$QEAPEBGAEA_N@Z; VmWorkerTrace::FoundNodeToProcess<ushort const *,bool &>(ushort const * &&,bool &)
0x14028c4cc  mov     rsi, rbx
0x14028c4cf  mov     [rbx+3Fh], r13b
0x14028c4d3  mov     rcx, [rsp+3C8h+var_218]
0x14028c4db  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x14028c4df  test    dl, dl
0x14028c4e1  jz      loc_14028C5A2
0x14028c4e7  test    r15b, r15b
0x14028c4ea  jnz     loc_14028C5A2
0x14028c4f0  mov     eax, [rcx+28h]
0x14028c4f3  nop
0x14028c4f4  cmp     eax, r13d
0x14028c4f7  mov     rax, [rsp+3C8h+var_218]
0x14028c4ff  jnz     short loc_14028C55F
0x14028c501  mov     cl, [rax+8]
0x14028c504  test    cl, cl
0x14028c506  mov     rcx, [rsp+3C8h+var_218]
0x14028c50e  jz      loc_14028C7AF
0x14028c514  add     rcx, 48h ; 'H'; ConditionVariable
0x14028c518  call    cs:__imp_WakeAllConditionVariable
0x14028c51f  nop     dword ptr [rax+rax+00h]
0x14028c524  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c529  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028c52e  nop
0x14028c52f  lea     rcx, [rsp+3C8h+var_1E0]
0x14028c537  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028c53c  nop
0x14028c53d  lea     rcx, [rsp+3C8h+var_198]; this
0x14028c545  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028c54a  nop
0x14028c54b  mov     [rsp+3C8h+var_380], 0
0x14028c550  mov     rax, [rdi]
0x14028c553  lock dec dword ptr [rax+28h]
0x14028c557  or      eax, 0FFFFFFFFh
0x14028c55a  jmp     loc_14028C78D
0x14028c55f  lock dec dword ptr [rax+28h]
0x14028c563  mov     rcx, [rsp+3C8h+var_218]
0x14028c56b  lea     rdx, [rcx+40h]; SRWLock
0x14028c56f  add     rcx, 48h ; 'H'; ConditionVariable
0x14028c573  xor     r9d, r9d; Flags
0x14028c576  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x14028c57a  call    cs:__imp_SleepConditionVariableSRW
0x14028c581  nop     dword ptr [rax+rax+00h]
0x14028c586  mov     rax, [rsp+3C8h+var_218]
0x14028c58e  lock add [rax+28h], r13d
0x14028c593  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c598  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028c59d  jmp     loc_14028C381
0x14028c5a2  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c5a7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028c5ac  test    r15b, r15b
0x14028c5af  jnz     short loc_14028C5B6
0x14028c5b1  jmp     loc_14028C74F
0x14028c5b6  mov     rax, [rsi+10h]
0x14028c5ba  mov     [rsp+3C8h+var_390], rax
0x14028c5bf  lea     r8, [rsp+3C8h+var_208]
0x14028c5c7  lea     rdx, [rsp+3C8h+var_390]
0x14028c5cc  lea     rcx, [rsp+3C8h+var_288]
0x14028c5d4  call    ??$make_tuple@PEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@std@@YA?AV?$tuple@PEAUVirtualDeviceInformation@@VVmPerfTraceOperation@Vml@@@0@$$QEAPEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@Z; std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(VirtualDeviceInformation * &&,Vml::VmPerfTraceOperation &)
0x14028c5d9  mov     rbx, rax
0x14028c5dc  mov     [rsp+3C8h+var_378], r14
0x14028c5e1  mov     rdx, rax; struct Vml::VmPerfTraceOperation *
0x14028c5e4  lea     rcx, [rsp+3C8h+var_370]; this
0x14028c5e9  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x14028c5ee  mov     rax, [rbx+68h]
0x14028c5f2  mov     [rsp+3C8h+var_308], rax
0x14028c5fa  mov     rbx, [rsp+3C8h+var_218]
0x14028c602  mov     rax, [rsp+3C8h+var_378]
0x14028c607  mov     r15d, [rax]
0x14028c60a  lea     rdx, [rsp+3C8h+var_370]; struct Vml::VmPerfTraceOperation *
0x14028c60f  lea     rcx, [rsp+3C8h+var_2F8]; this
0x14028c617  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x14028c61c  mov     r9d, r15d
0x14028c61f  mov     r8, rax
0x14028c622  mov     rdx, [rsp+3C8h+var_308]
0x14028c62a  lea     rcx, [rbx+30h]
0x14028c62e  call    _lambda_b37d4be99a1b4a294a8337e4a985c351___operator__
0x14028c633  mov     ebx, eax
0x14028c635  lea     rcx, [rsp+3C8h+var_348]
0x14028c63d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028c642  nop
0x14028c643  lea     rcx, [rsp+3C8h+var_260]
0x14028c64b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028c650  mov     edx, ebx
0x14028c652  mov     rcx, [rsp+3C8h+var_218]
0x14028c65a  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x14028c65f  mov     rdx, [rsp+3C8h+var_218]
0x14028c667  test    ebx, ebx
0x14028c669  jns     short loc_14028C676
0x14028c66b  cmp     byte ptr [rdx+9], 0
0x14028c66f  jz      short loc_14028C676
0x14028c671  mov     al, r13b
0x14028c674  jmp     short loc_14028C678
0x14028c676  xor     al, al
0x14028c678  mov     rcx, [rsp+3C8h]; this
0x14028c680  test    al, al
0x14028c682  jnz     loc_14028C7F5
0x14028c688  mov     [rsp+3C8h+var_3A0], 0
0x14028c691  add     rdx, 40h ; '@'
0x14028c695  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c69a  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14028c69f  mov     rax, [rsp+3C8h+var_218]
0x14028c6a7  mov     cl, [rax+8]
0x14028c6aa  test    cl, cl
0x14028c6ac  jz      short loc_14028C701
0x14028c6ae  mov     rcx, [rsp+3C8h+var_218]
0x14028c6b6  add     rcx, 48h ; 'H'; ConditionVariable
0x14028c6ba  call    cs:__imp_WakeAllConditionVariable
0x14028c6c1  nop     dword ptr [rax+rax+00h]
0x14028c6c6  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c6cb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028c6d0  nop
0x14028c6d1  lea     rcx, [rsp+3C8h+var_1E0]
0x14028c6d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028c6de  nop
0x14028c6df  lea     rcx, [rsp+3C8h+var_198]; this
0x14028c6e7  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028c6ec  nop
0x14028c6ed  mov     [rsp+3C8h+var_380], 0
0x14028c6f2  mov     rax, [rdi]
0x14028c6f5  lock dec dword ptr [rax+28h]
0x14028c6f9  or      eax, 0FFFFFFFFh
0x14028c6fc  jmp     loc_14028C78D
0x14028c701  or      [rsp+3C8h+var_394], 3
0x14028c706  mov     rcx, [rsi+20h]
0x14028c70a  mov     rax, [rcx]
0x14028c70d  cmp     rax, rcx
0x14028c710  jz      short loc_14028C71E
0x14028c712  mov     rdx, [rax+10h]
0x14028c716  dec     dword ptr [rdx+34h]
0x14028c719  mov     rax, [rax]
0x14028c71c  jmp     short loc_14028C70D
0x14028c71e  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c723  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028c728  mov     rcx, [rsp+3C8h+var_218]
0x14028c730  add     rcx, 48h ; 'H'; ConditionVariable
0x14028c734  call    cs:__imp_WakeAllConditionVariable
0x14028c73b  nop     dword ptr [rax+rax+00h]
0x14028c740  jmp     loc_14028C379
0x14028c745  mov     r13b, [rsp+3C8h+var_380]
0x14028c74a  mov     rdi, [rsp+3C8h+var_388]
0x14028c74f  mov     ebx, [rsp+3C8h+var_398]
0x14028c753  mov     edx, ebx
0x14028c755  lea     rcx, [rsp+3C8h+var_198]
0x14028c75d  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14028c762  nop
0x14028c763  lea     rcx, [rsp+3C8h+var_1E0]
0x14028c76b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028c770  nop
0x14028c771  lea     rcx, [rsp+3C8h+var_198]; this
0x14028c779  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028c77e  nop
0x14028c77f  test    r13b, r13b
0x14028c782  jz      short loc_14028C78B
0x14028c784  mov     rcx, [rdi]
0x14028c787  lock dec dword ptr [rcx+28h]
0x14028c78b  mov     eax, ebx
0x14028c78d  mov     rcx, [rsp+3C8h+var_48]
0x14028c795  xor     rcx, rsp; StackCookie
0x14028c798  call    __security_check_cookie
0x14028c79d  add     rsp, 398h
0x14028c7a4  pop     r15
0x14028c7a6  pop     r14
0x14028c7a8  pop     r13
0x14028c7aa  pop     rdi
0x14028c7ab  pop     rsi
0x14028c7ac  pop     rbx
0x14028c7ad  retn
0x14028c7af  add     rcx, 28h ; '('
0x14028c7b3  call    ??F?$_Atomic_integral@H$03@std@@QEAAHH@Z; std::_Atomic_integral<int,4>::operator--(int)
0x14028c7b8  mov     rcx, [rsp+3C8h+var_218]
0x14028c7c0  add     rcx, 1Ch
0x14028c7c4  mov     edx, 8007046Bh
0x14028c7c9  call    ??4?$atomic@J@std@@QEAAJJ@Z; std::atomic<long>::operator=(long)
0x14028c7ce  mov     rcx, [rsp+3C8h+var_218]
0x14028c7d6  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____TraceDeviceGraph
0x14028c7db  mov     rcx, [rsp+3C8h]; this
0x14028c7e3  lea     r8, aOnecoreVmWorke_46; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
  ... truncated ...
```
