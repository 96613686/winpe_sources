# SAL2::CSALCommitQueue::OpportunisticCheckPoint(SAL2::CSALCommitQueueClient *,SAL2::CSALPageList *)

- ea: `0x18009326c`
- end: `0x180093521`
- name: `?OpportunisticCheckPoint@CSALCommitQueue@SAL2@@QEAAJPEAVCSALCommitQueueClient@2@PEAVCSALPageList@2@@Z`
- size: `693`
- prototype: `__int64 __fastcall(SAL2::CSALCommitQueue *__hidden this, struct SAL2::CSALCommitQueueClient *, struct SAL2::CSALPageList *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18008f740`

## callees

- `0x180008330`
- `0x180062710`
- `0x1800627f0`
- `0x180086014`
- `0x180091ea4`
- `0x180092370`
- `0x18009326c`
- `0x180093528`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800934d3`
- `KERNEL32!LeaveCriticalSection` at `0x1800934d3`
- `KERNEL32!EnterCriticalSection` at `0x1800932c6`
- `KERNEL32!EnterCriticalSection` at `0x1800932c6`

## string_xrefs

- `0x1800932e7`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`
- `0x180093301`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`
- `0x18009331f`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`
- `0x180093348`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`
- `0x1800934b6`: `multimedia\dshow\filters\sbe\sal\salcommit.cpp`

## pseudocode

```c
__int64 __fastcall SAL2::CSALCommitQueue::OpportunisticCheckPoint(
        SAL2::CSALCommitQueue *this,
        struct SAL2::CSALCommitQueueClient *a2,
        struct SAL2::CSALPageList *a3)
{
  SAL2 *v6; // rcx
  int v7; // ebp
  struct CEhEventTracer *v8; // rcx
  unsigned int v9; // r9d
  unsigned int v10; // r8d
  unsigned int v11; // r9d
  int v12; // edi
  SAL2::CSALCommitQueue::PendingLoggedJob *v13; // rcx
  __int64 v14; // rcx
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  GUID v19; // [rsp+30h] [rbp-48h] BYREF
  int v20; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+10h] BYREF
  int v22; // [rsp+8Ch] [rbp+14h]

  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 40) + 24LL))(*((_QWORD *)this + 40));
  _InterlockedIncrement((volatile signed __int32 *)this + 68);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 36) + 104LL))(*((_QWORD *)this + 36));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  *((_QWORD *)this + 47) = SAL2::GetSystemTime(v6);
  if ( !a2 )
    SBEBasicTracers::EtwTraceAssert(
      (SAL2::CSALCommitQueue *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\sal\\salcommit.cpp",
      0x23Bu);
  if ( !a3 )
    SBEBasicTracers::EtwTraceAssert(
      (SAL2::CSALCommitQueue *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\sal\\salcommit.cpp",
      0x23Cu);
  if ( *((_DWORD *)this + 70) )
    SBEBasicTracers::EtwTraceAssert(
      (SAL2::CSALCommitQueue *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\sal\\salcommit.cpp",
      0x23Du);
  v7 = *((_DWORD *)this + 112);
  if ( v7 < 0 )
  {
    v8 = (SAL2::CSALCommitQueue *)((char *)this + 128);
    v9 = *((_DWORD *)this + 112);
    v10 = 581;
LABEL_9:
    SBEBasicTracers::EtwTraceError(v8, "multimedia\\dshow\\filters\\sbe\\sal\\salcommit.cpp", v10, v9);
    goto LABEL_32;
  }
  v11 = *((_DWORD *)a3 + 6);
  v12 = 0;
  if ( v11 )
  {
    if ( !*((_DWORD *)this + 82) )
    {
      v7 = -2147024891;
      v9 = -2147024891;
      v10 = 585;
LABEL_13:
      v8 = (SAL2::CSALCommitQueue *)((char *)this + 88);
      goto LABEL_9;
    }
    if ( v11 > *((_DWORD *)this + 117)
      || *((_QWORD *)a2 + 4)
      && *((_QWORD *)this + 47) - *((_QWORD *)a2 + 4) > (unsigned __int64)*((unsigned int *)this + 118) )
    {
      goto LABEL_19;
    }
    if ( *((_DWORD *)a2 + 10) != *((_DWORD *)this + 106) )
    {
      if ( *((_QWORD *)this + 55) )
      {
LABEL_19:
        v12 = 1;
        goto LABEL_23;
      }
      v13 = (SAL2::CSALCommitQueue::PendingLoggedJob *)*((_QWORD *)this + 54);
      if ( v13 && (unsigned int)SAL2::CSALCommitQueue::PendingLoggedJob::ICanDemote(v13) )
        v12 = 1;
    }
  }
LABEL_23:
  v14 = *((_QWORD *)this + 18);
  v21 = v11;
  v22 = v12;
  v20 = 0;
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 24LL))(v14, &v20);
    if ( v20 )
    {
      v15 = (__int64 *)*((_QWORD *)this + 18);
      v16 = *v15;
      v19 = GUID_d2377676_a024_4b7b_945b_33de83480f37;
      (*(void (__fastcall **)(__int64 *, GUID *, unsigned int *, __int64))(v16 + 32))(v15, &v19, &v21, 8);
    }
  }
  if ( v12 )
  {
    v17 = SAL2::CSALCommitQueue::INewLogJob(this, a3);
    v7 = v17;
    if ( v17 < 0 )
    {
      v9 = v17;
      v10 = 667;
      goto LABEL_13;
    }
    SAL2::CSALPageList::Purge(a3);
    *((_QWORD *)a2 + 4) = 0;
    *((_DWORD *)a2 + 10) = *((_DWORD *)this + 106);
  }
  else if ( !*((_QWORD *)a2 + 4) )
  {
    *((_QWORD *)a2 + 4) = *((_QWORD *)this + 47);
  }
LABEL_32:
  if ( !*((_QWORD *)this + 47) )
    SBEBasicTracers::EtwTraceAssert(
      (SAL2::CSALCommitQueue *)((char *)this + 88),
      "multimedia\\dshow\\filters\\sbe\\sal\\salcommit.cpp",
      0x14Bu);
  *((_QWORD *)this + 47) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 36) + 112LL))(*((_QWORD *)this + 36));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 40) + 32LL))(*((_QWORD *)this + 40));
  SBF2::CRefCounted::Release((SAL2::CSALCommitQueue *)((char *)this + 264));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18009326c  mov     [rsp+arg_10], rbx
0x180093271  push    rbp
0x180093272  push    rsi
0x180093273  push    rdi
0x180093274  push    r12
0x180093276  push    r13
0x180093278  push    r14
0x18009327a  push    r15
0x18009327c  sub     rsp, 40h
0x180093280  mov     rbx, rcx
0x180093283  mov     r15, r8
0x180093286  mov     rcx, [rcx+140h]
0x18009328d  mov     r14, rdx
0x180093290  mov     rax, [rcx]
0x180093293  mov     rax, [rax+18h]
0x180093297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009329c  lea     r12, [rbx+108h]
0x1800932a3  lock inc dword ptr [r12+8]
0x1800932a9  mov     rcx, [rbx+120h]
0x1800932b0  mov     rax, [rcx]
0x1800932b3  mov     rax, [rax+68h]
0x1800932b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800932bc  lea     r13, [rbx+150h]
0x1800932c3  mov     rcx, r13; lpCriticalSection
0x1800932c6  call    cs:__imp_EnterCriticalSection
0x1800932cc  call    ?GetSystemTime@SAL2@@YA_KXZ; SAL2::GetSystemTime(void)
0x1800932d1  mov     [rbx+178h], rax
0x1800932d8  lea     rsi, [rbx+58h]
0x1800932dc  test    r14, r14
0x1800932df  jnz     short loc_1800932F6
0x1800932e1  mov     r8d, 23Bh; unsigned int
0x1800932e7  lea     rdx, aMultimediaDsho_16; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x1800932ee  mov     rcx, rsi; struct CEhEventTracer *
0x1800932f1  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800932f6  test    r15, r15
0x1800932f9  jnz     short loc_180093310
0x1800932fb  mov     r8d, 23Ch; unsigned int
0x180093301  lea     rdx, aMultimediaDsho_16; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180093308  mov     rcx, rsi; struct CEhEventTracer *
0x18009330b  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x180093310  cmp     dword ptr [rbx+118h], 0
0x180093317  jz      short loc_18009332E
0x180093319  mov     r8d, 23Dh; unsigned int
0x18009331f  lea     rdx, aMultimediaDsho_16; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x180093326  mov     rcx, rsi; struct CEhEventTracer *
0x180093329  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x18009332e  mov     ebp, [rbx+1C0h]
0x180093334  test    ebp, ebp
0x180093336  jns     short loc_180093359
0x180093338  lea     rcx, [rbx+80h]; struct CEhEventTracer *
0x18009333f  mov     r9d, ebp; unsigned int
0x180093342  mov     r8d, 245h; unsigned int
0x180093348  lea     rdx, aMultimediaDsho_16; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x18009334f  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x180093354  jmp     loc_1800934A6
0x180093359  mov     r9d, [r15+18h]
0x18009335d  xor     edi, edi
0x18009335f  test    r9d, r9d
0x180093362  jz      short loc_1800933DE
0x180093364  cmp     [rbx+148h], edi
0x18009336a  jnz     short loc_180093382
0x18009336c  mov     ebp, 80070005h
0x180093371  mov     r9d, 80070005h
0x180093377  mov     r8d, 249h
0x18009337d  mov     rcx, rsi
0x180093380  jmp     short loc_180093348
0x180093382  cmp     r9d, [rbx+1D4h]
0x180093389  ja      short loc_1800933BC
0x18009338b  cmp     [r14+20h], rdi
0x18009338f  jz      short loc_1800933A7
0x180093391  mov     rcx, [rbx+178h]
0x180093398  sub     rcx, [r14+20h]
0x18009339c  mov     eax, [rbx+1D8h]
0x1800933a2  cmp     rcx, rax
0x1800933a5  ja      short loc_1800933BC
0x1800933a7  mov     eax, [rbx+1A8h]
0x1800933ad  cmp     [r14+28h], eax
0x1800933b1  jz      short loc_1800933DE
0x1800933b3  cmp     [rbx+1B8h], rdi
0x1800933ba  jz      short loc_1800933C3
0x1800933bc  mov     edi, 1
0x1800933c1  jmp     short loc_1800933DE
0x1800933c3  mov     rcx, [rbx+1B0h]; this
0x1800933ca  test    rcx, rcx
0x1800933cd  jz      short loc_1800933DE
0x1800933cf  call    ?ICanDemote@PendingLoggedJob@CSALCommitQueue@SAL2@@QEAAHXZ; SAL2::CSALCommitQueue::PendingLoggedJob::ICanDemote(void)
0x1800933d4  test    eax, eax
0x1800933d6  mov     eax, 1
0x1800933db  cmovnz  edi, eax
0x1800933de  mov     rcx, [rbx+90h]
0x1800933e5  mov     [rsp+78h+arg_8], r9d
0x1800933ed  mov     [rsp+78h+arg_C], edi
0x1800933f4  mov     [rsp+78h+arg_0], 0
0x1800933ff  test    rcx, rcx
0x180093402  jz      short loc_180093455
0x180093404  mov     rax, [rcx]
0x180093407  lea     rdx, [rsp+78h+arg_0]
0x18009340f  mov     rax, [rax+18h]
0x180093413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093418  cmp     [rsp+78h+arg_0], 0
0x180093420  jz      short loc_180093455
0x180093422  mov     rcx, [rbx+90h]
0x180093429  lea     r8, [rsp+78h+arg_8]
0x180093431  movups  xmm0, xmmword ptr cs:_GUID_d2377676_a024_4b7b_945b_33de83480f37.Data1
0x180093438  mov     r9d, 8
0x18009343e  lea     rdx, [rsp+78h+var_48]
0x180093443  mov     rax, [rcx]
0x180093446  movdqu  [rsp+78h+var_48], xmm0
0x18009344c  mov     rax, [rax+20h]
0x180093450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093455  test    edi, edi
0x180093457  jz      short loc_180093494
0x180093459  mov     rdx, r15; struct SAL2::CSALPageList *
0x18009345c  mov     rcx, rbx; this
0x18009345f  call    ?INewLogJob@CSALCommitQueue@SAL2@@AEAAJPEAVCSALPageList@2@@Z; SAL2::CSALCommitQueue::INewLogJob(SAL2::CSALPageList *)
0x180093464  mov     ebp, eax
0x180093466  test    eax, eax
0x180093468  jns     short loc_180093478
0x18009346a  mov     r9d, eax
0x18009346d  mov     r8d, 29Bh
0x180093473  jmp     loc_18009337D
0x180093478  mov     rcx, r15; this
0x18009347b  call    ?Purge@CSALPageList@SAL2@@QEAAXXZ; SAL2::CSALPageList::Purge(void)
0x180093480  mov     qword ptr [r14+20h], 0
0x180093488  mov     eax, [rbx+1A8h]
0x18009348e  mov     [r14+28h], eax
0x180093492  jmp     short loc_1800934A6
0x180093494  cmp     qword ptr [r14+20h], 0
0x180093499  jnz     short loc_1800934A6
0x18009349b  mov     rax, [rbx+178h]
0x1800934a2  mov     [r14+20h], rax
0x1800934a6  cmp     qword ptr [rbx+178h], 0
0x1800934ae  jnz     short loc_1800934C5
0x1800934b0  mov     r8d, 14Bh; unsigned int
0x1800934b6  lea     rdx, aMultimediaDsho_16; "multimedia\\dshow\\filters\\sbe\\sal\\s"...
0x1800934bd  mov     rcx, rsi; struct CEhEventTracer *
0x1800934c0  call    ?EtwTraceAssert@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDK@Z; SBEBasicTracers::EtwTraceAssert(CEhEventTracer &,char const *,ulong)
0x1800934c5  mov     rcx, r13; lpCriticalSection
0x1800934c8  mov     qword ptr [rbx+178h], 0
0x1800934d3  call    cs:__imp_LeaveCriticalSection
0x1800934d9  mov     rcx, [rbx+120h]
0x1800934e0  mov     rax, [rcx]
0x1800934e3  mov     rax, [rax+70h]
0x1800934e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800934ec  mov     rcx, [rbx+140h]
0x1800934f3  mov     rax, [rcx]
0x1800934f6  mov     rax, [rax+20h]
0x1800934fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800934ff  mov     rcx, r12; this
0x180093502  call    ?Release@CRefCounted@SBF2@@QEAAJXZ; SBF2::CRefCounted::Release(void)
0x180093507  mov     rbx, [rsp+78h+arg_10]
0x18009350f  mov     eax, ebp
0x180093511  add     rsp, 40h
0x180093515  pop     r15
0x180093517  pop     r14
0x180093519  pop     r13
0x18009351b  pop     r12
0x18009351d  pop     rdi
0x18009351e  pop     rsi
0x18009351f  pop     rbp
0x180093520  retn
```
