# _lambda_1beeb3f5b12b17edc670c5c4fb163e90_::operator()

- ea: `0x140101b30`
- end: `0x14010200b`
- name: `_lambda_1beeb3f5b12b17edc670c5c4fb163e90_::operator()`
- size: `1243`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14027e790`

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
- `0x140101ab8`
- `0x140101b30`
- `0x140132960`
- `0x14013361c`
- `0x140281088`
- `0x140282d3c`
- `0x140283790`
- `0x140283f54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101c2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101cf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101c2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101cf1`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101c5e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101f16`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101f90`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101c5e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101f16`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101f90`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140101dc6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140101dc6`

## pseudocode

```c
__int64 __fastcall lambda_1beeb3f5b12b17edc670c5c4fb163e90_::operator()(__int64 a1, __int64 *a2)
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
    v18 = lambda_ae232efc167169ec614a6d5435ac4ed5_::operator()(v15 + 48, v32, v17, v16);
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
0x140101b30  push    rbx
0x140101b32  push    rsi
0x140101b33  push    rdi
0x140101b34  push    r13
0x140101b36  push    r14
0x140101b38  push    r15
0x140101b3a  sub     rsp, 398h
0x140101b41  mov     rax, cs:__security_cookie
0x140101b48  xor     rax, rsp
0x140101b4b  mov     [rsp+3C8h+var_48], rax
0x140101b53  mov     [rsp+3C8h+var_394], 0
0x140101b5b  mov     rax, [rdx]
0x140101b5e  mov     [rsp+3C8h+var_218], rax
0x140101b66  test    rax, rax
0x140101b69  jnz     short loc_140101B75
0x140101b6b  mov     eax, 8000FFFFh
0x140101b70  jmp     loc_140101FE9
0x140101b75  mov     [rsp+3C8h+var_398], 0
0x140101b7d  mov     r14, [rdx+8]
0x140101b81  mov     r13d, 1
0x140101b87  lock add [rax+28h], r13d
0x140101b8c  lea     rdi, [rsp+3C8h+var_218]
0x140101b94  mov     [rsp+3C8h+var_388], rdi
0x140101b99  mov     [rsp+3C8h+var_380], r13b
0x140101b9e  xor     edx, edx; Val
0x140101ba0  mov     r8d, 150h; Size
0x140101ba6  lea     rcx, [rsp+3C8h+var_198]; void *
0x140101bae  call    memset_0
0x140101bb3  mov     rdx, [rsp+3C8h+var_218]
0x140101bbb  lea     r8, [rdx+60h]
0x140101bbf  add     rdx, 50h ; 'P'
0x140101bc3  lea     rcx, [rsp+3C8h+var_198]; this
0x140101bcb  call    VmPerf__StartRelatedActivity_VmWorkerTrace__VDevWorkerThread__GUID___
0x140101bd0  nop
0x140101bd1  mov     rdx, [rsp+3C8h+var_218]
0x140101bd9  lea     r9, [rdx+50h]; struct _GUID *
0x140101bdd  lea     r8, [rdx+60h]; struct _GUID *
0x140101be1  mov     rdx, [rdx+10h]; struct Vml::VmPerfTraceComponent *
0x140101be5  lea     rcx, [rsp+3C8h+var_208]; this
0x140101bed  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x140101bf2  nop
0x140101bf3  xor     esi, esi
0x140101bf5  mov     byte ptr [rsp+3C8h+var_3A8+1], 0
0x140101bfa  xor     r15b, r15b
0x140101bfd  mov     [rsp+3C8h+var_3A0], 0
0x140101c06  mov     rdx, [rsp+3C8h+var_218]
0x140101c0e  add     rdx, 40h ; '@'
0x140101c12  lea     rcx, [rsp+3C8h+var_3A0]
0x140101c17  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x140101c1c  mov     rax, [rsp+3C8h+var_218]
0x140101c24  cmp     dword ptr [rax+20h], 0
0x140101c28  jnz     short loc_140101C4B
0x140101c2a  call    cs:__imp_GetCurrentThreadId
0x140101c31  nop     dword ptr [rax+rax+00h]
0x140101c36  mov     ecx, eax
0x140101c38  mov     rax, [rsp+3C8h+var_218]
0x140101c40  mov     [rax+20h], ecx
0x140101c43  mov     rax, [rsp+3C8h+var_218]
0x140101c4b  mov     al, [rax+8]
0x140101c4e  mov     rcx, [rsp+3C8h+var_218]
0x140101c56  test    al, al
0x140101c58  jz      short loc_140101CA5
0x140101c5a  add     rcx, 48h ; 'H'; ConditionVariable
0x140101c5e  call    cs:__imp_WakeAllConditionVariable
0x140101c65  nop     dword ptr [rax+rax+00h]
0x140101c6a  lea     rcx, [rsp+3C8h+var_3A0]
0x140101c6f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101c74  nop
0x140101c75  lea     rcx, [rsp+3C8h+var_1E0]
0x140101c7d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101c82  nop
0x140101c83  lea     rcx, [rsp+3C8h+var_198]; this
0x140101c8b  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140101c90  nop
0x140101c91  mov     [rsp+3C8h+var_380], 0
0x140101c96  mov     rax, [rdi]
0x140101c99  lock dec dword ptr [rax+28h]
0x140101c9d  or      eax, 0FFFFFFFFh
0x140101ca0  jmp     loc_140101FE9
0x140101ca5  mov     rax, [rcx+38h]
0x140101ca9  mov     rbx, [rax]
0x140101cac  xor     dl, dl
0x140101cae  mov     byte ptr [rsp+3C8h+var_3A8], dl; int
0x140101cb2  mov     rbx, [rbx]
0x140101cb5  mov     rax, [rcx+38h]
0x140101cb9  cmp     rbx, [rax]
0x140101cbc  jz      loc_140101D5B
0x140101cc2  cmp     dword ptr [rbx+34h], 0
0x140101cc6  jnz     short loc_140101D13
0x140101cc8  cmp     byte ptr [rbx+3Fh], 0
0x140101ccc  jnz     short loc_140101CB2
0x140101cce  mov     r15b, r13b
0x140101cd1  mov     byte ptr [rsp+3C8h+var_3A8+2], r13b
0x140101cd6  cmp     dword ptr [rcx+70h], 0
0x140101cda  jz      short loc_140101D22
0x140101cdc  mov     eax, [rbx+38h]
0x140101cdf  and     eax, [rcx+70h]
0x140101ce2  cmp     eax, [rcx+70h]
0x140101ce5  jnz     short loc_140101D22
0x140101ce7  cmp     dword ptr [rcx+20h], 0
0x140101ceb  jz      short loc_140101D1D
0x140101ced  mov     r15d, [rcx+20h]
0x140101cf1  call    cs:__imp_GetCurrentThreadId
0x140101cf8  nop     dword ptr [rax+rax+00h]
0x140101cfd  cmp     r15d, eax
0x140101d00  jz      short loc_140101D18
0x140101d02  xor     r15b, r15b
0x140101d05  mov     rcx, [rsp+3C8h+var_218]
0x140101d0d  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x140101d11  jmp     short loc_140101CB2
0x140101d13  mov     dl, r13b
0x140101d16  jmp     short loc_140101CAE
0x140101d18  mov     r15b, byte ptr [rsp+3C8h+var_3A8+2]
0x140101d1d  mov     byte ptr [rsp+3C8h+var_3A8+1], r13b
0x140101d22  mov     rax, [rbx+10h]
0x140101d26  add     rax, 40h ; '@'
0x140101d2a  cmp     qword ptr [rax+18h], 7
0x140101d2f  jbe     short loc_140101D34
0x140101d31  mov     rax, [rax]
0x140101d34  mov     [rsp+3C8h+var_390], rax
0x140101d39  lea     rdx, [rsp+3C8h+var_3A8+1]
0x140101d3e  lea     rcx, [rsp+3C8h+var_390]
0x140101d43  call    ??$FoundNodeToProcess@PEBGAEA_N@VmWorkerTrace@@SAX$$QEAPEBGAEA_N@Z; VmWorkerTrace::FoundNodeToProcess<ushort const *,bool &>(ushort const * &&,bool &)
0x140101d48  mov     rsi, rbx
0x140101d4b  mov     [rbx+3Fh], r13b
0x140101d4f  mov     rcx, [rsp+3C8h+var_218]
0x140101d57  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x140101d5b  test    dl, dl
0x140101d5d  jz      loc_140101DEE
0x140101d63  test    r15b, r15b
0x140101d66  jnz     loc_140101DEE
0x140101d6c  lock dec dword ptr [rcx+28h]
0x140101d70  mov     rax, [rsp+3C8h+var_218]
0x140101d78  mov     ecx, [rax+28h]
0x140101d7b  nop
0x140101d7c  test    ecx, ecx
0x140101d7e  mov     rcx, [rsp+3C8h+var_218]
0x140101d86  jnz     short loc_140101DB7
0x140101d88  mov     eax, 8007046Bh
0x140101d8d  xchg    eax, [rcx+1Ch]
0x140101d90  mov     rcx, [rsp+3C8h+var_218]
0x140101d98  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____TraceDeviceGraph
0x140101d9d  mov     rcx, [rsp+3C8h]; this
0x140101da5  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x140101dac  mov     edx, 100h; void *
0x140101db1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140101db7  lea     rdx, [rcx+40h]; SRWLock
0x140101dbb  add     rcx, 48h ; 'H'; ConditionVariable
0x140101dbf  xor     r9d, r9d; Flags
0x140101dc2  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x140101dc6  call    cs:__imp_SleepConditionVariableSRW
0x140101dcd  nop     dword ptr [rax+rax+00h]
0x140101dd2  mov     rax, [rsp+3C8h+var_218]
0x140101dda  lock add [rax+28h], r13d
0x140101ddf  lea     rcx, [rsp+3C8h+var_3A0]
0x140101de4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101de9  jmp     loc_140101BFD
0x140101dee  lea     rcx, [rsp+3C8h+var_3A0]
0x140101df3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101df8  test    r15b, r15b
0x140101dfb  jnz     short loc_140101E02
0x140101dfd  jmp     loc_140101FAB
0x140101e02  mov     rax, [rsi+10h]
0x140101e06  mov     [rsp+3C8h+var_390], rax
0x140101e0b  lea     r8, [rsp+3C8h+var_208]
0x140101e13  lea     rdx, [rsp+3C8h+var_390]
0x140101e18  lea     rcx, [rsp+3C8h+var_288]
0x140101e20  call    ??$make_tuple@PEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@std@@YA?AV?$tuple@PEAUVirtualDeviceInformation@@VVmPerfTraceOperation@Vml@@@0@$$QEAPEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@Z; std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(VirtualDeviceInformation * &&,Vml::VmPerfTraceOperation &)
0x140101e25  mov     rbx, rax
0x140101e28  mov     [rsp+3C8h+var_378], r14
0x140101e2d  mov     rdx, rax; struct Vml::VmPerfTraceOperation *
0x140101e30  lea     rcx, [rsp+3C8h+var_370]; this
0x140101e35  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x140101e3a  mov     rax, [rbx+68h]
0x140101e3e  mov     [rsp+3C8h+var_308], rax
0x140101e46  mov     rbx, [rsp+3C8h+var_218]
0x140101e4e  mov     rax, [rsp+3C8h+var_378]
0x140101e53  mov     r15d, [rax]
0x140101e56  lea     rdx, [rsp+3C8h+var_370]; struct Vml::VmPerfTraceOperation *
0x140101e5b  lea     rcx, [rsp+3C8h+var_2F8]; this
0x140101e63  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x140101e68  mov     r9d, r15d
0x140101e6b  mov     r8, rax
0x140101e6e  mov     rdx, [rsp+3C8h+var_308]
0x140101e76  lea     rcx, [rbx+30h]
0x140101e7a  call    _lambda_ae232efc167169ec614a6d5435ac4ed5___operator__
0x140101e7f  mov     ebx, eax
0x140101e81  lea     rcx, [rsp+3C8h+var_348]
0x140101e89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101e8e  nop
0x140101e8f  lea     rcx, [rsp+3C8h+var_260]
0x140101e97  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101e9c  mov     edx, ebx
0x140101e9e  mov     rcx, [rsp+3C8h+var_218]
0x140101ea6  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140101eab  mov     rdx, [rsp+3C8h+var_218]
0x140101eb3  test    ebx, ebx
0x140101eb5  jns     short loc_140101EC2
0x140101eb7  cmp     byte ptr [rdx+9], 0
0x140101ebb  jz      short loc_140101EC2
0x140101ebd  mov     al, r13b
0x140101ec0  jmp     short loc_140101EC4
0x140101ec2  xor     al, al
0x140101ec4  mov     rcx, [rsp+3C8h]; this
0x140101ecc  test    al, al
0x140101ece  jz      short loc_140101EE4
0x140101ed0  mov     r9d, ebx; char *
0x140101ed3  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x140101eda  mov     edx, 11Eh; void *
0x140101edf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140101ee4  mov     [rsp+3C8h+var_3A0], 0
0x140101eed  add     rdx, 40h ; '@'
0x140101ef1  lea     rcx, [rsp+3C8h+var_3A0]
0x140101ef6  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x140101efb  mov     rax, [rsp+3C8h+var_218]
0x140101f03  mov     cl, [rax+8]
0x140101f06  test    cl, cl
0x140101f08  jz      short loc_140101F5D
0x140101f0a  mov     rcx, [rsp+3C8h+var_218]
0x140101f12  add     rcx, 48h ; 'H'; ConditionVariable
0x140101f16  call    cs:__imp_WakeAllConditionVariable
0x140101f1d  nop     dword ptr [rax+rax+00h]
0x140101f22  lea     rcx, [rsp+3C8h+var_3A0]
0x140101f27  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101f2c  nop
0x140101f2d  lea     rcx, [rsp+3C8h+var_1E0]
0x140101f35  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101f3a  nop
0x140101f3b  lea     rcx, [rsp+3C8h+var_198]; this
0x140101f43  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140101f48  nop
0x140101f49  mov     [rsp+3C8h+var_380], 0
0x140101f4e  mov     rax, [rdi]
0x140101f51  lock dec dword ptr [rax+28h]
0x140101f55  or      eax, 0FFFFFFFFh
0x140101f58  jmp     loc_140101FE9
0x140101f5d  or      [rsp+3C8h+var_394], 3
0x140101f62  mov     rcx, [rsi+20h]
0x140101f66  mov     rax, [rcx]
0x140101f69  cmp     rax, rcx
0x140101f6c  jz      short loc_140101F7A
0x140101f6e  mov     rdx, [rax+10h]
0x140101f72  dec     dword ptr [rdx+34h]
0x140101f75  mov     rax, [rax]
0x140101f78  jmp     short loc_140101F69
0x140101f7a  lea     rcx, [rsp+3C8h+var_3A0]
0x140101f7f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101f84  mov     rcx, [rsp+3C8h+var_218]
0x140101f8c  add     rcx, 48h ; 'H'; ConditionVariable
0x140101f90  call    cs:__imp_WakeAllConditionVariable
0x140101f97  nop     dword ptr [rax+rax+00h]
0x140101f9c  jmp     loc_140101BF5
0x140101fa1  mov     r13b, [rsp+3C8h+var_380]
0x140101fa6  mov     rdi, [rsp+3C8h+var_388]
0x140101fab  mov     ebx, [rsp+3C8h+var_398]
0x140101faf  mov     edx, ebx
0x140101fb1  lea     rcx, [rsp+3C8h+var_198]
0x140101fb9  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140101fbe  nop
0x140101fbf  lea     rcx, [rsp+3C8h+var_1E0]
0x140101fc7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101fcc  nop
0x140101fcd  lea     rcx, [rsp+3C8h+var_198]; this
0x140101fd5  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140101fda  nop
0x140101fdb  test    r13b, r13b
0x140101fde  jz      short loc_140101FE7
0x140101fe0  mov     rcx, [rdi]
0x140101fe3  lock dec dword ptr [rcx+28h]
0x140101fe7  mov     eax, ebx
0x140101fe9  mov     rcx, [rsp+3C8h+var_48]
0x140101ff1  xor     rcx, rsp; StackCookie
0x140101ff4  call    __security_check_cookie
0x140101ff9  add     rsp, 398h
0x140102000  pop     r15
0x140102002  pop     r14
0x140102004  pop     r13
0x140102006  pop     rdi
0x140102007  pop     rsi
0x140102008  pop     rbx
0x140102009  retn
```
