# _lambda_664edb7134184b7e2576fb6f05eaacc8_::operator()

- ea: `0x1401015d4`
- end: `0x140101aaf`
- name: `_lambda_664edb7134184b7e2576fb6f05eaacc8_::operator()`
- size: `1243`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14027e7c0`

## callees

- `0x1400315c8`
- `0x140031ca8`
- `0x140031cec`
- `0x140043c98`
- `0x14006af58`
- `0x1400764c4`
- `0x14007a74c`
- `0x14009fa0c`
- `0x1400ca840`
- `0x1400e1964`
- `0x1401015d4`
- `0x140101ab8`
- `0x140132960`
- `0x14013361c`
- `0x140281088`
- `0x140282d3c`
- `0x140283790`
- `0x140283e34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401016ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101795`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401016ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101795`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101702`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1401019ba`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101a34`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101702`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1401019ba`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101a34`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14010186a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14010186a`

## pseudocode

```c
__int64 __fastcall lambda_664edb7134184b7e2576fb6f05eaacc8_::operator()(__int64 a1, __int64 *a2)
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
  const char *v13; // r9
  const struct Vml::VmPerfTraceOperation *v14; // rbx
  __int64 v15; // rbx
  unsigned int v16; // r15d
  __int64 v17; // rax
  int v18; // ebx
  _QWORD *v20; // rcx
  _QWORD *i; // rax
  unsigned int v22; // ebx
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
        goto LABEL_8;
      v9 = **(__int64 ***)(v36 + 56);
      v10 = 0;
LABEL_10:
      LOBYTE(v23) = v10;
      while ( 1 )
      {
        v9 = (__int64 *)*v9;
        if ( v9 == **(__int64 ***)(v8 + 56) )
          break;
        if ( *((_DWORD *)v9 + 13) )
        {
          v10 = 1;
          goto LABEL_10;
        }
        if ( !*((_BYTE *)v9 + 63) )
        {
          v6 = 1;
          BYTE2(v23) = 1;
          if ( !*(_DWORD *)(v8 + 112) || (*(_DWORD *)(v8 + 112) & (_DWORD)v9[7]) != *(_DWORD *)(v8 + 112) )
            goto LABEL_22;
          if ( !*(_DWORD *)(v8 + 32) )
            goto LABEL_21;
          v11 = *(_DWORD *)(v8 + 32);
          if ( v11 == GetCurrentThreadId() )
          {
            v6 = BYTE2(v23);
LABEL_21:
            BYTE1(v23) = 1;
LABEL_22:
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
      _InterlockedDecrement((volatile signed __int32 *)(v8 + 40));
      if ( !*(_DWORD *)(v36 + 40) )
      {
        _InterlockedExchange((volatile __int32 *)(v36 + 28), -2147023765);
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::TraceDeviceGraph(v36);
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
          v13);
      }
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(v36 + 72), (PSRWLOCK)(v36 + 64), 0xFFFFFFFF, 0);
      _InterlockedAdd((volatile signed __int32 *)(v36 + 40), 1u);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    if ( !v6 )
      break;
    v27[0] = v5[2];
    v14 = (const struct Vml::VmPerfTraceOperation *)std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(
                                                      v34,
                                                      v27,
                                                      v37);
    v29 = v4;
    Vml::VmPerfTraceOperation::VmPerfTraceOperation((Vml::VmPerfTraceOperation *)v30, v14);
    v32 = *((_QWORD *)v14 + 13);
    v15 = v36;
    v16 = *v29;
    v17 = Vml::VmPerfTraceOperation::VmPerfTraceOperation(
            (Vml::VmPerfTraceOperation *)v33,
            (const struct Vml::VmPerfTraceOperation *)v30);
    v18 = lambda_85c9e02f24e13dfa4db09b9da0195f41_::operator()(v15 + 48, v32, v17, v16);
    std::wstring::_Tidy_deallocate(v31);
    std::wstring::_Tidy_deallocate(v35);
    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(v36, (unsigned int)v18);
    if ( v18 < 0 && *(_BYTE *)(v36 + 9) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
        (const char *)(unsigned int)v18,
        v23);
    v24 = 0;
    wil::AcquireSRWLockExclusive(&v24, v36 + 64);
    if ( *(_BYTE *)(v36 + 8) )
    {
LABEL_8:
      WakeAllConditionVariable((PCONDITION_VARIABLE)(v36 + 72));
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
      std::wstring::_Tidy_deallocate(v38);
      VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v39);
      v28 = 0;
      _InterlockedDecrement((volatile signed __int32 *)(v36 + 40));
      return 0xFFFFFFFFLL;
    }
    v26 |= 3u;
    v20 = (_QWORD *)v5[4];
    for ( i = (_QWORD *)*v20; i != v20; i = (_QWORD *)*i )
      --*(_DWORD *)(i[2] + 52LL);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    WakeAllConditionVariable((PCONDITION_VARIABLE)(v36 + 72));
  }
  v22 = v25;
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v39, v25);
  std::wstring::_Tidy_deallocate(v38);
  VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v39);
  _InterlockedDecrement((volatile signed __int32 *)(v36 + 40));
  return v22;
}

```

## disassembly

```asm
0x1401015d4  push    rbx
0x1401015d6  push    rsi
0x1401015d7  push    rdi
0x1401015d8  push    r13
0x1401015da  push    r14
0x1401015dc  push    r15
0x1401015de  sub     rsp, 398h
0x1401015e5  mov     rax, cs:__security_cookie
0x1401015ec  xor     rax, rsp
0x1401015ef  mov     [rsp+3C8h+var_48], rax
0x1401015f7  mov     [rsp+3C8h+var_394], 0
0x1401015ff  mov     rax, [rdx]
0x140101602  mov     [rsp+3C8h+var_218], rax
0x14010160a  test    rax, rax
0x14010160d  jnz     short loc_140101619
0x14010160f  mov     eax, 8000FFFFh
0x140101614  jmp     loc_140101A8D
0x140101619  mov     [rsp+3C8h+var_398], 0
0x140101621  mov     r14, [rdx+8]
0x140101625  mov     r13d, 1
0x14010162b  lock add [rax+28h], r13d
0x140101630  lea     rdi, [rsp+3C8h+var_218]
0x140101638  mov     [rsp+3C8h+var_388], rdi
0x14010163d  mov     [rsp+3C8h+var_380], r13b
0x140101642  xor     edx, edx; Val
0x140101644  mov     r8d, 150h; Size
0x14010164a  lea     rcx, [rsp+3C8h+var_198]; void *
0x140101652  call    memset_0
0x140101657  mov     rdx, [rsp+3C8h+var_218]
0x14010165f  lea     r8, [rdx+60h]
0x140101663  add     rdx, 50h ; 'P'
0x140101667  lea     rcx, [rsp+3C8h+var_198]; this
0x14010166f  call    VmPerf__StartRelatedActivity_VmWorkerTrace__VDevWorkerThread__GUID___
0x140101674  nop
0x140101675  mov     rdx, [rsp+3C8h+var_218]
0x14010167d  lea     r9, [rdx+50h]; struct _GUID *
0x140101681  lea     r8, [rdx+60h]; struct _GUID *
0x140101685  mov     rdx, [rdx+10h]; struct Vml::VmPerfTraceComponent *
0x140101689  lea     rcx, [rsp+3C8h+var_208]; this
0x140101691  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x140101696  nop
0x140101697  xor     esi, esi
0x140101699  mov     byte ptr [rsp+3C8h+var_3A8+1], 0
0x14010169e  xor     r15b, r15b
0x1401016a1  mov     [rsp+3C8h+var_3A0], 0
0x1401016aa  mov     rdx, [rsp+3C8h+var_218]
0x1401016b2  add     rdx, 40h ; '@'
0x1401016b6  lea     rcx, [rsp+3C8h+var_3A0]
0x1401016bb  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1401016c0  mov     rax, [rsp+3C8h+var_218]
0x1401016c8  cmp     dword ptr [rax+20h], 0
0x1401016cc  jnz     short loc_1401016EF
0x1401016ce  call    cs:__imp_GetCurrentThreadId
0x1401016d5  nop     dword ptr [rax+rax+00h]
0x1401016da  mov     ecx, eax
0x1401016dc  mov     rax, [rsp+3C8h+var_218]
0x1401016e4  mov     [rax+20h], ecx
0x1401016e7  mov     rax, [rsp+3C8h+var_218]
0x1401016ef  mov     al, [rax+8]
0x1401016f2  mov     rcx, [rsp+3C8h+var_218]
0x1401016fa  test    al, al
0x1401016fc  jz      short loc_140101749
0x1401016fe  add     rcx, 48h ; 'H'; ConditionVariable
0x140101702  call    cs:__imp_WakeAllConditionVariable
0x140101709  nop     dword ptr [rax+rax+00h]
0x14010170e  lea     rcx, [rsp+3C8h+var_3A0]
0x140101713  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101718  nop
0x140101719  lea     rcx, [rsp+3C8h+var_1E0]
0x140101721  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101726  nop
0x140101727  lea     rcx, [rsp+3C8h+var_198]; this
0x14010172f  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140101734  nop
0x140101735  mov     [rsp+3C8h+var_380], 0
0x14010173a  mov     rax, [rdi]
0x14010173d  lock dec dword ptr [rax+28h]
0x140101741  or      eax, 0FFFFFFFFh
0x140101744  jmp     loc_140101A8D
0x140101749  mov     rax, [rcx+38h]
0x14010174d  mov     rbx, [rax]
0x140101750  xor     dl, dl
0x140101752  mov     byte ptr [rsp+3C8h+var_3A8], dl; int
0x140101756  mov     rbx, [rbx]
0x140101759  mov     rax, [rcx+38h]
0x14010175d  cmp     rbx, [rax]
0x140101760  jz      loc_1401017FF
0x140101766  cmp     dword ptr [rbx+34h], 0
0x14010176a  jnz     short loc_1401017B7
0x14010176c  cmp     byte ptr [rbx+3Fh], 0
0x140101770  jnz     short loc_140101756
0x140101772  mov     r15b, r13b
0x140101775  mov     byte ptr [rsp+3C8h+var_3A8+2], r13b
0x14010177a  cmp     dword ptr [rcx+70h], 0
0x14010177e  jz      short loc_1401017C6
0x140101780  mov     eax, [rbx+38h]
0x140101783  and     eax, [rcx+70h]
0x140101786  cmp     eax, [rcx+70h]
0x140101789  jnz     short loc_1401017C6
0x14010178b  cmp     dword ptr [rcx+20h], 0
0x14010178f  jz      short loc_1401017C1
0x140101791  mov     r15d, [rcx+20h]
0x140101795  call    cs:__imp_GetCurrentThreadId
0x14010179c  nop     dword ptr [rax+rax+00h]
0x1401017a1  cmp     r15d, eax
0x1401017a4  jz      short loc_1401017BC
0x1401017a6  xor     r15b, r15b
0x1401017a9  mov     rcx, [rsp+3C8h+var_218]
0x1401017b1  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x1401017b5  jmp     short loc_140101756
0x1401017b7  mov     dl, r13b
0x1401017ba  jmp     short loc_140101752
0x1401017bc  mov     r15b, byte ptr [rsp+3C8h+var_3A8+2]
0x1401017c1  mov     byte ptr [rsp+3C8h+var_3A8+1], r13b
0x1401017c6  mov     rax, [rbx+10h]
0x1401017ca  add     rax, 40h ; '@'
0x1401017ce  cmp     qword ptr [rax+18h], 7
0x1401017d3  jbe     short loc_1401017D8
0x1401017d5  mov     rax, [rax]
0x1401017d8  mov     [rsp+3C8h+var_390], rax
0x1401017dd  lea     rdx, [rsp+3C8h+var_3A8+1]
0x1401017e2  lea     rcx, [rsp+3C8h+var_390]
0x1401017e7  call    ??$FoundNodeToProcess@PEBGAEA_N@VmWorkerTrace@@SAX$$QEAPEBGAEA_N@Z; VmWorkerTrace::FoundNodeToProcess<ushort const *,bool &>(ushort const * &&,bool &)
0x1401017ec  mov     rsi, rbx
0x1401017ef  mov     [rbx+3Fh], r13b
0x1401017f3  mov     rcx, [rsp+3C8h+var_218]
0x1401017fb  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x1401017ff  test    dl, dl
0x140101801  jz      loc_140101892
0x140101807  test    r15b, r15b
0x14010180a  jnz     loc_140101892
0x140101810  lock dec dword ptr [rcx+28h]
0x140101814  mov     rax, [rsp+3C8h+var_218]
0x14010181c  mov     ecx, [rax+28h]
0x14010181f  nop
0x140101820  test    ecx, ecx
0x140101822  mov     rcx, [rsp+3C8h+var_218]
0x14010182a  jnz     short loc_14010185B
0x14010182c  mov     eax, 8007046Bh
0x140101831  xchg    eax, [rcx+1Ch]
0x140101834  mov     rcx, [rsp+3C8h+var_218]
0x14010183c  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____TraceDeviceGraph
0x140101841  mov     rcx, [rsp+3C8h]; this
0x140101849  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x140101850  mov     edx, 100h; void *
0x140101855  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14010185b  lea     rdx, [rcx+40h]; SRWLock
0x14010185f  add     rcx, 48h ; 'H'; ConditionVariable
0x140101863  xor     r9d, r9d; Flags
0x140101866  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x14010186a  call    cs:__imp_SleepConditionVariableSRW
0x140101871  nop     dword ptr [rax+rax+00h]
0x140101876  mov     rax, [rsp+3C8h+var_218]
0x14010187e  lock add [rax+28h], r13d
0x140101883  lea     rcx, [rsp+3C8h+var_3A0]
0x140101888  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14010188d  jmp     loc_1401016A1
0x140101892  lea     rcx, [rsp+3C8h+var_3A0]
0x140101897  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14010189c  test    r15b, r15b
0x14010189f  jnz     short loc_1401018A6
0x1401018a1  jmp     loc_140101A4F
0x1401018a6  mov     rax, [rsi+10h]
0x1401018aa  mov     [rsp+3C8h+var_390], rax
0x1401018af  lea     r8, [rsp+3C8h+var_208]
0x1401018b7  lea     rdx, [rsp+3C8h+var_390]
0x1401018bc  lea     rcx, [rsp+3C8h+var_288]
0x1401018c4  call    ??$make_tuple@PEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@std@@YA?AV?$tuple@PEAUVirtualDeviceInformation@@VVmPerfTraceOperation@Vml@@@0@$$QEAPEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@Z; std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(VirtualDeviceInformation * &&,Vml::VmPerfTraceOperation &)
0x1401018c9  mov     rbx, rax
0x1401018cc  mov     [rsp+3C8h+var_378], r14
0x1401018d1  mov     rdx, rax; struct Vml::VmPerfTraceOperation *
0x1401018d4  lea     rcx, [rsp+3C8h+var_370]; this
0x1401018d9  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x1401018de  mov     rax, [rbx+68h]
0x1401018e2  mov     [rsp+3C8h+var_308], rax
0x1401018ea  mov     rbx, [rsp+3C8h+var_218]
0x1401018f2  mov     rax, [rsp+3C8h+var_378]
0x1401018f7  mov     r15d, [rax]
0x1401018fa  lea     rdx, [rsp+3C8h+var_370]; struct Vml::VmPerfTraceOperation *
0x1401018ff  lea     rcx, [rsp+3C8h+var_2F8]; this
0x140101907  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x14010190c  mov     r9d, r15d
0x14010190f  mov     r8, rax
0x140101912  mov     rdx, [rsp+3C8h+var_308]
0x14010191a  lea     rcx, [rbx+30h]
0x14010191e  call    _lambda_85c9e02f24e13dfa4db09b9da0195f41___operator__
0x140101923  mov     ebx, eax
0x140101925  lea     rcx, [rsp+3C8h+var_348]
0x14010192d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101932  nop
0x140101933  lea     rcx, [rsp+3C8h+var_260]
0x14010193b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101940  mov     edx, ebx
0x140101942  mov     rcx, [rsp+3C8h+var_218]
0x14010194a  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x14010194f  mov     rdx, [rsp+3C8h+var_218]
0x140101957  test    ebx, ebx
0x140101959  jns     short loc_140101966
0x14010195b  cmp     byte ptr [rdx+9], 0
0x14010195f  jz      short loc_140101966
0x140101961  mov     al, r13b
0x140101964  jmp     short loc_140101968
0x140101966  xor     al, al
0x140101968  mov     rcx, [rsp+3C8h]; this
0x140101970  test    al, al
0x140101972  jz      short loc_140101988
0x140101974  mov     r9d, ebx; char *
0x140101977  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x14010197e  mov     edx, 11Eh; void *
0x140101983  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140101988  mov     [rsp+3C8h+var_3A0], 0
0x140101991  add     rdx, 40h ; '@'
0x140101995  lea     rcx, [rsp+3C8h+var_3A0]
0x14010199a  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14010199f  mov     rax, [rsp+3C8h+var_218]
0x1401019a7  mov     cl, [rax+8]
0x1401019aa  test    cl, cl
0x1401019ac  jz      short loc_140101A01
0x1401019ae  mov     rcx, [rsp+3C8h+var_218]
0x1401019b6  add     rcx, 48h ; 'H'; ConditionVariable
0x1401019ba  call    cs:__imp_WakeAllConditionVariable
0x1401019c1  nop     dword ptr [rax+rax+00h]
0x1401019c6  lea     rcx, [rsp+3C8h+var_3A0]
0x1401019cb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1401019d0  nop
0x1401019d1  lea     rcx, [rsp+3C8h+var_1E0]
0x1401019d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1401019de  nop
0x1401019df  lea     rcx, [rsp+3C8h+var_198]; this
0x1401019e7  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x1401019ec  nop
0x1401019ed  mov     [rsp+3C8h+var_380], 0
0x1401019f2  mov     rax, [rdi]
0x1401019f5  lock dec dword ptr [rax+28h]
0x1401019f9  or      eax, 0FFFFFFFFh
0x1401019fc  jmp     loc_140101A8D
0x140101a01  or      [rsp+3C8h+var_394], 3
0x140101a06  mov     rcx, [rsi+20h]
0x140101a0a  mov     rax, [rcx]
0x140101a0d  cmp     rax, rcx
0x140101a10  jz      short loc_140101A1E
0x140101a12  mov     rdx, [rax+10h]
0x140101a16  dec     dword ptr [rdx+34h]
0x140101a19  mov     rax, [rax]
0x140101a1c  jmp     short loc_140101A0D
0x140101a1e  lea     rcx, [rsp+3C8h+var_3A0]
0x140101a23  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101a28  mov     rcx, [rsp+3C8h+var_218]
0x140101a30  add     rcx, 48h ; 'H'; ConditionVariable
0x140101a34  call    cs:__imp_WakeAllConditionVariable
0x140101a3b  nop     dword ptr [rax+rax+00h]
0x140101a40  jmp     loc_140101699
0x140101a45  mov     r13b, [rsp+3C8h+var_380]
0x140101a4a  mov     rdi, [rsp+3C8h+var_388]
0x140101a4f  mov     ebx, [rsp+3C8h+var_398]
0x140101a53  mov     edx, ebx
0x140101a55  lea     rcx, [rsp+3C8h+var_198]
0x140101a5d  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140101a62  nop
0x140101a63  lea     rcx, [rsp+3C8h+var_1E0]
0x140101a6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101a70  nop
0x140101a71  lea     rcx, [rsp+3C8h+var_198]; this
0x140101a79  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140101a7e  nop
0x140101a7f  test    r13b, r13b
0x140101a82  jz      short loc_140101A8B
0x140101a84  mov     rcx, [rdi]
0x140101a87  lock dec dword ptr [rcx+28h]
0x140101a8b  mov     eax, ebx
0x140101a8d  mov     rcx, [rsp+3C8h+var_48]
0x140101a95  xor     rcx, rsp; StackCookie
0x140101a98  call    __security_check_cookie
0x140101a9d  add     rsp, 398h
0x140101aa4  pop     r15
0x140101aa6  pop     r14
0x140101aa8  pop     r13
0x140101aaa  pop     rdi
0x140101aab  pop     rsi
0x140101aac  pop     rbx
0x140101aad  retn
```
