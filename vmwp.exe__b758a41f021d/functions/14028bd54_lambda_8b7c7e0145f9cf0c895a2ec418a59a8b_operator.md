# _lambda_8b7c7e0145f9cf0c895a2ec418a59a8b_::operator()

- ea: `0x14028bd54`
- end: `0x14028c2ab`
- name: `_lambda_8b7c7e0145f9cf0c895a2ec418a59a8b_::operator()`
- size: `1367`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140284ae0`

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
- `0x14028bd54`
- `0x14028c8b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028be4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028bf15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028be4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028bf15`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028be82`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028bfb8`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c15a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c1d4`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028be82`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028bfb8`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c15a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14028c1d4`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14028c01a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14028c01a`

## pseudocode

```c
__int64 __fastcall lambda_8b7c7e0145f9cf0c895a2ec418a59a8b_::operator()(__int64 a1, __int64 *a2)
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
    v17 = lambda_ae232efc167169ec614a6d5435ac4ed5_::operator()(v14 + 48, v32, v16, v15);
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
0x14028bd54  push    rbx
0x14028bd56  push    rsi
0x14028bd57  push    rdi
0x14028bd58  push    r13
0x14028bd5a  push    r14
0x14028bd5c  push    r15
0x14028bd5e  sub     rsp, 398h
0x14028bd65  mov     rax, cs:__security_cookie
0x14028bd6c  xor     rax, rsp
0x14028bd6f  mov     [rsp+3C8h+var_48], rax
0x14028bd77  mov     [rsp+3C8h+var_394], 0
0x14028bd7f  mov     rax, [rdx]
0x14028bd82  mov     [rsp+3C8h+var_218], rax
0x14028bd8a  test    rax, rax
0x14028bd8d  jnz     short loc_14028BD99
0x14028bd8f  mov     eax, 8000FFFFh
0x14028bd94  jmp     loc_14028C22D
0x14028bd99  mov     [rsp+3C8h+var_398], 0
0x14028bda1  mov     r14, [rdx+8]
0x14028bda5  mov     r13d, 1
0x14028bdab  lock add [rax+28h], r13d
0x14028bdb0  lea     rdi, [rsp+3C8h+var_218]
0x14028bdb8  mov     [rsp+3C8h+var_388], rdi
0x14028bdbd  mov     [rsp+3C8h+var_380], r13b
0x14028bdc2  xor     edx, edx; Val
0x14028bdc4  mov     r8d, 150h; Size
0x14028bdca  lea     rcx, [rsp+3C8h+var_198]; void *
0x14028bdd2  call    memset_0
0x14028bdd7  mov     rdx, [rsp+3C8h+var_218]
0x14028bddf  lea     r8, [rdx+60h]
0x14028bde3  add     rdx, 50h ; 'P'
0x14028bde7  lea     rcx, [rsp+3C8h+var_198]; this
0x14028bdef  call    VmPerf__StartRelatedActivity_VmWorkerTrace__VDevWorkerThread__GUID___
0x14028bdf4  nop
0x14028bdf5  mov     rdx, [rsp+3C8h+var_218]
0x14028bdfd  lea     r9, [rdx+50h]; struct _GUID *
0x14028be01  lea     r8, [rdx+60h]; struct _GUID *
0x14028be05  mov     rdx, [rdx+10h]; struct Vml::VmPerfTraceComponent *
0x14028be09  lea     rcx, [rsp+3C8h+var_208]; this
0x14028be11  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x14028be16  nop
0x14028be17  xor     esi, esi
0x14028be19  mov     byte ptr [rsp+3C8h+var_3A8+1], 0
0x14028be1e  xor     r15b, r15b
0x14028be21  mov     [rsp+3C8h+var_3A0], 0
0x14028be2a  mov     rdx, [rsp+3C8h+var_218]
0x14028be32  add     rdx, 40h ; '@'
0x14028be36  lea     rcx, [rsp+3C8h+var_3A0]
0x14028be3b  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14028be40  mov     rax, [rsp+3C8h+var_218]
0x14028be48  cmp     dword ptr [rax+20h], 0
0x14028be4c  jnz     short loc_14028BE6F
0x14028be4e  call    cs:__imp_GetCurrentThreadId
0x14028be55  nop     dword ptr [rax+rax+00h]
0x14028be5a  mov     ecx, eax
0x14028be5c  mov     rax, [rsp+3C8h+var_218]
0x14028be64  mov     [rax+20h], ecx
0x14028be67  mov     rax, [rsp+3C8h+var_218]
0x14028be6f  mov     al, [rax+8]
0x14028be72  mov     rcx, [rsp+3C8h+var_218]
0x14028be7a  test    al, al
0x14028be7c  jz      short loc_14028BEC9
0x14028be7e  add     rcx, 48h ; 'H'; ConditionVariable
0x14028be82  call    cs:__imp_WakeAllConditionVariable
0x14028be89  nop     dword ptr [rax+rax+00h]
0x14028be8e  lea     rcx, [rsp+3C8h+var_3A0]
0x14028be93  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028be98  nop
0x14028be99  lea     rcx, [rsp+3C8h+var_1E0]
0x14028bea1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028bea6  nop
0x14028bea7  lea     rcx, [rsp+3C8h+var_198]; this
0x14028beaf  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028beb4  nop
0x14028beb5  mov     [rsp+3C8h+var_380], 0
0x14028beba  mov     rax, [rdi]
0x14028bebd  lock dec dword ptr [rax+28h]
0x14028bec1  or      eax, 0FFFFFFFFh
0x14028bec4  jmp     loc_14028C22D
0x14028bec9  mov     rax, [rcx+38h]
0x14028becd  mov     rbx, [rax]
0x14028bed0  xor     dl, dl
0x14028bed2  mov     byte ptr [rsp+3C8h+var_3A8], dl; int
0x14028bed6  mov     rbx, [rbx]
0x14028bed9  mov     rax, [rcx+38h]
0x14028bedd  cmp     rbx, [rax]
0x14028bee0  jz      loc_14028BF7F
0x14028bee6  cmp     dword ptr [rbx+34h], 0
0x14028beea  jnz     short loc_14028BF37
0x14028beec  cmp     byte ptr [rbx+3Fh], 0
0x14028bef0  jnz     short loc_14028BED6
0x14028bef2  mov     r15b, r13b
0x14028bef5  mov     byte ptr [rsp+3C8h+var_3A8+2], r13b
0x14028befa  cmp     dword ptr [rcx+70h], 0
0x14028befe  jz      short loc_14028BF46
0x14028bf00  mov     eax, [rbx+38h]
0x14028bf03  and     eax, [rcx+70h]
0x14028bf06  cmp     eax, [rcx+70h]
0x14028bf09  jnz     short loc_14028BF46
0x14028bf0b  cmp     dword ptr [rcx+20h], 0
0x14028bf0f  jz      short loc_14028BF41
0x14028bf11  mov     r15d, [rcx+20h]
0x14028bf15  call    cs:__imp_GetCurrentThreadId
0x14028bf1c  nop     dword ptr [rax+rax+00h]
0x14028bf21  cmp     r15d, eax
0x14028bf24  jz      short loc_14028BF3C
0x14028bf26  xor     r15b, r15b
0x14028bf29  mov     rcx, [rsp+3C8h+var_218]
0x14028bf31  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x14028bf35  jmp     short loc_14028BED6
0x14028bf37  mov     dl, r13b
0x14028bf3a  jmp     short loc_14028BED2
0x14028bf3c  mov     r15b, byte ptr [rsp+3C8h+var_3A8+2]
0x14028bf41  mov     byte ptr [rsp+3C8h+var_3A8+1], r13b
0x14028bf46  mov     rax, [rbx+10h]
0x14028bf4a  add     rax, 40h ; '@'
0x14028bf4e  cmp     qword ptr [rax+18h], 7
0x14028bf53  jbe     short loc_14028BF58
0x14028bf55  mov     rax, [rax]
0x14028bf58  mov     [rsp+3C8h+var_390], rax
0x14028bf5d  lea     rdx, [rsp+3C8h+var_3A8+1]
0x14028bf62  lea     rcx, [rsp+3C8h+var_390]
0x14028bf67  call    ??$FoundNodeToProcess@PEBGAEA_N@VmWorkerTrace@@SAX$$QEAPEBGAEA_N@Z; VmWorkerTrace::FoundNodeToProcess<ushort const *,bool &>(ushort const * &&,bool &)
0x14028bf6c  mov     rsi, rbx
0x14028bf6f  mov     [rbx+3Fh], r13b
0x14028bf73  mov     rcx, [rsp+3C8h+var_218]
0x14028bf7b  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x14028bf7f  test    dl, dl
0x14028bf81  jz      loc_14028C042
0x14028bf87  test    r15b, r15b
0x14028bf8a  jnz     loc_14028C042
0x14028bf90  mov     eax, [rcx+28h]
0x14028bf93  nop
0x14028bf94  cmp     eax, r13d
0x14028bf97  mov     rax, [rsp+3C8h+var_218]
0x14028bf9f  jnz     short loc_14028BFFF
0x14028bfa1  mov     cl, [rax+8]
0x14028bfa4  test    cl, cl
0x14028bfa6  mov     rcx, [rsp+3C8h+var_218]
0x14028bfae  jz      loc_14028C24F
0x14028bfb4  add     rcx, 48h ; 'H'; ConditionVariable
0x14028bfb8  call    cs:__imp_WakeAllConditionVariable
0x14028bfbf  nop     dword ptr [rax+rax+00h]
0x14028bfc4  lea     rcx, [rsp+3C8h+var_3A0]
0x14028bfc9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028bfce  nop
0x14028bfcf  lea     rcx, [rsp+3C8h+var_1E0]
0x14028bfd7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028bfdc  nop
0x14028bfdd  lea     rcx, [rsp+3C8h+var_198]; this
0x14028bfe5  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028bfea  nop
0x14028bfeb  mov     [rsp+3C8h+var_380], 0
0x14028bff0  mov     rax, [rdi]
0x14028bff3  lock dec dword ptr [rax+28h]
0x14028bff7  or      eax, 0FFFFFFFFh
0x14028bffa  jmp     loc_14028C22D
0x14028bfff  lock dec dword ptr [rax+28h]
0x14028c003  mov     rcx, [rsp+3C8h+var_218]
0x14028c00b  lea     rdx, [rcx+40h]; SRWLock
0x14028c00f  add     rcx, 48h ; 'H'; ConditionVariable
0x14028c013  xor     r9d, r9d; Flags
0x14028c016  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x14028c01a  call    cs:__imp_SleepConditionVariableSRW
0x14028c021  nop     dword ptr [rax+rax+00h]
0x14028c026  mov     rax, [rsp+3C8h+var_218]
0x14028c02e  lock add [rax+28h], r13d
0x14028c033  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c038  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028c03d  jmp     loc_14028BE21
0x14028c042  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c047  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028c04c  test    r15b, r15b
0x14028c04f  jnz     short loc_14028C056
0x14028c051  jmp     loc_14028C1EF
0x14028c056  mov     rax, [rsi+10h]
0x14028c05a  mov     [rsp+3C8h+var_390], rax
0x14028c05f  lea     r8, [rsp+3C8h+var_208]
0x14028c067  lea     rdx, [rsp+3C8h+var_390]
0x14028c06c  lea     rcx, [rsp+3C8h+var_288]
0x14028c074  call    ??$make_tuple@PEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@std@@YA?AV?$tuple@PEAUVirtualDeviceInformation@@VVmPerfTraceOperation@Vml@@@0@$$QEAPEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@Z; std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(VirtualDeviceInformation * &&,Vml::VmPerfTraceOperation &)
0x14028c079  mov     rbx, rax
0x14028c07c  mov     [rsp+3C8h+var_378], r14
0x14028c081  mov     rdx, rax; struct Vml::VmPerfTraceOperation *
0x14028c084  lea     rcx, [rsp+3C8h+var_370]; this
0x14028c089  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x14028c08e  mov     rax, [rbx+68h]
0x14028c092  mov     [rsp+3C8h+var_308], rax
0x14028c09a  mov     rbx, [rsp+3C8h+var_218]
0x14028c0a2  mov     rax, [rsp+3C8h+var_378]
0x14028c0a7  mov     r15d, [rax]
0x14028c0aa  lea     rdx, [rsp+3C8h+var_370]; struct Vml::VmPerfTraceOperation *
0x14028c0af  lea     rcx, [rsp+3C8h+var_2F8]; this
0x14028c0b7  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x14028c0bc  mov     r9d, r15d
0x14028c0bf  mov     r8, rax
0x14028c0c2  mov     rdx, [rsp+3C8h+var_308]
0x14028c0ca  lea     rcx, [rbx+30h]
0x14028c0ce  call    _lambda_ae232efc167169ec614a6d5435ac4ed5___operator__
0x14028c0d3  mov     ebx, eax
0x14028c0d5  lea     rcx, [rsp+3C8h+var_348]
0x14028c0dd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028c0e2  nop
0x14028c0e3  lea     rcx, [rsp+3C8h+var_260]
0x14028c0eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028c0f0  mov     edx, ebx
0x14028c0f2  mov     rcx, [rsp+3C8h+var_218]
0x14028c0fa  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x14028c0ff  mov     rdx, [rsp+3C8h+var_218]
0x14028c107  test    ebx, ebx
0x14028c109  jns     short loc_14028C116
0x14028c10b  cmp     byte ptr [rdx+9], 0
0x14028c10f  jz      short loc_14028C116
0x14028c111  mov     al, r13b
0x14028c114  jmp     short loc_14028C118
0x14028c116  xor     al, al
0x14028c118  mov     rcx, [rsp+3C8h]; this
0x14028c120  test    al, al
0x14028c122  jnz     loc_14028C295
0x14028c128  mov     [rsp+3C8h+var_3A0], 0
0x14028c131  add     rdx, 40h ; '@'
0x14028c135  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c13a  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14028c13f  mov     rax, [rsp+3C8h+var_218]
0x14028c147  mov     cl, [rax+8]
0x14028c14a  test    cl, cl
0x14028c14c  jz      short loc_14028C1A1
0x14028c14e  mov     rcx, [rsp+3C8h+var_218]
0x14028c156  add     rcx, 48h ; 'H'; ConditionVariable
0x14028c15a  call    cs:__imp_WakeAllConditionVariable
0x14028c161  nop     dword ptr [rax+rax+00h]
0x14028c166  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c16b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028c170  nop
0x14028c171  lea     rcx, [rsp+3C8h+var_1E0]
0x14028c179  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028c17e  nop
0x14028c17f  lea     rcx, [rsp+3C8h+var_198]; this
0x14028c187  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028c18c  nop
0x14028c18d  mov     [rsp+3C8h+var_380], 0
0x14028c192  mov     rax, [rdi]
0x14028c195  lock dec dword ptr [rax+28h]
0x14028c199  or      eax, 0FFFFFFFFh
0x14028c19c  jmp     loc_14028C22D
0x14028c1a1  or      [rsp+3C8h+var_394], 3
0x14028c1a6  mov     rcx, [rsi+20h]
0x14028c1aa  mov     rax, [rcx]
0x14028c1ad  cmp     rax, rcx
0x14028c1b0  jz      short loc_14028C1BE
0x14028c1b2  mov     rdx, [rax+10h]
0x14028c1b6  dec     dword ptr [rdx+34h]
0x14028c1b9  mov     rax, [rax]
0x14028c1bc  jmp     short loc_14028C1AD
0x14028c1be  lea     rcx, [rsp+3C8h+var_3A0]
0x14028c1c3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14028c1c8  mov     rcx, [rsp+3C8h+var_218]
0x14028c1d0  add     rcx, 48h ; 'H'; ConditionVariable
0x14028c1d4  call    cs:__imp_WakeAllConditionVariable
0x14028c1db  nop     dword ptr [rax+rax+00h]
0x14028c1e0  jmp     loc_14028BE19
0x14028c1e5  mov     r13b, [rsp+3C8h+var_380]
0x14028c1ea  mov     rdi, [rsp+3C8h+var_388]
0x14028c1ef  mov     ebx, [rsp+3C8h+var_398]
0x14028c1f3  mov     edx, ebx
0x14028c1f5  lea     rcx, [rsp+3C8h+var_198]
0x14028c1fd  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14028c202  nop
0x14028c203  lea     rcx, [rsp+3C8h+var_1E0]
0x14028c20b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14028c210  nop
0x14028c211  lea     rcx, [rsp+3C8h+var_198]; this
0x14028c219  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14028c21e  nop
0x14028c21f  test    r13b, r13b
0x14028c222  jz      short loc_14028C22B
0x14028c224  mov     rcx, [rdi]
0x14028c227  lock dec dword ptr [rcx+28h]
0x14028c22b  mov     eax, ebx
0x14028c22d  mov     rcx, [rsp+3C8h+var_48]
0x14028c235  xor     rcx, rsp; StackCookie
0x14028c238  call    __security_check_cookie
0x14028c23d  add     rsp, 398h
0x14028c244  pop     r15
0x14028c246  pop     r14
0x14028c248  pop     r13
0x14028c24a  pop     rdi
0x14028c24b  pop     rsi
0x14028c24c  pop     rbx
0x14028c24d  retn
0x14028c24f  add     rcx, 28h ; '('
0x14028c253  call    ??F?$_Atomic_integral@H$03@std@@QEAAHH@Z; std::_Atomic_integral<int,4>::operator--(int)
0x14028c258  mov     rcx, [rsp+3C8h+var_218]
0x14028c260  add     rcx, 1Ch
0x14028c264  mov     edx, 8007046Bh
0x14028c269  call    ??4?$atomic@J@std@@QEAAJJ@Z; std::atomic<long>::operator=(long)
0x14028c26e  mov     rcx, [rsp+3C8h+var_218]
0x14028c276  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____TraceDeviceGraph
0x14028c27b  mov     rcx, [rsp+3C8h]; this
0x14028c283  lea     r8, aOnecoreVmWorke_46; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
  ... truncated ...
```
