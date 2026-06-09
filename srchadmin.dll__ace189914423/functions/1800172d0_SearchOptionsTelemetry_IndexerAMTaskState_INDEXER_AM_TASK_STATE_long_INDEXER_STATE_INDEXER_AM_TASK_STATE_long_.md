# SearchOptionsTelemetry::IndexerAMTaskState<INDEXER_AM_TASK_STATE,long &,INDEXER_STATE>(INDEXER_AM_TASK_STATE &&,long &,INDEXER_STATE &&)

- ea: `0x1800172d0`
- end: `0x180017546`
- name: `??$IndexerAMTaskState@W4INDEXER_AM_TASK_STATE@@AEAJW4INDEXER_STATE@@@SearchOptionsTelemetry@@SAX$$QEAW4INDEXER_AM_TASK_STATE@@AEAJ$$QEAW4INDEXER_STATE@@@Z`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018730`

## callees

- `0x180005cc0`
- `0x18000614c`
- `0x1800172d0`
- `0x180032010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180017524`
- `ntdll!EtwEventWriteTransfer` at `0x180017524`
- `ntdll!EtwEventSetInformation` at `0x1800173f3`
- `ntdll!EtwEventSetInformation` at `0x1800173f3`
- `ntdll!EtwEventRegister` at `0x1800173d8`
- `ntdll!EtwEventRegister` at `0x1800173d8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180017318`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180017318`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180017422`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180017422`

## pseudocode

```c
__int64 __fastcall SearchOptionsTelemetry::IndexerAMTaskState<enum INDEXER_AM_TASK_STATE,long &,enum INDEXER_STATE>(
        _DWORD *a1,
        _DWORD *a2,
        WINBOOL *a3)
{
  _QWORD *v6; // rbx
  __int64 v7; // r9
  unsigned int *v8; // rcx
  __int64 result; // rax
  WINBOOL fPending; // [rsp+30h] [rbp-69h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-61h] BYREF
  __int64 v12; // [rsp+40h] [rbp-59h] BYREF
  __int64 v13; // [rsp+48h] [rbp-51h] BYREF
  __int128 v14; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v15; // [rsp+60h] [rbp-39h] BYREF
  int v16; // [rsp+68h] [rbp-31h]
  int v17; // [rsp+6Ch] [rbp-2Dh]
  void *v18; // [rsp+70h] [rbp-29h]
  __int64 v19; // [rsp+78h] [rbp-21h]
  char *v20; // [rsp+80h] [rbp-19h]
  __int64 v21; // [rsp+88h] [rbp-11h]
  __int64 *v22; // [rsp+90h] [rbp-9h]
  __int64 v23; // [rsp+98h] [rbp-1h]
  WINBOOL *p_fPending; // [rsp+A0h] [rbp+7h]
  __int64 v25; // [rsp+A8h] [rbp+Fh]
  __int64 *v26; // [rsp+B0h] [rbp+17h]
  __int64 v27; // [rsp+B8h] [rbp+1Fh]

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`SearchOptionsLogging::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
  {
    Context = &qword_180041BA8;
    qword_180041BB0 = 0;
    byte_180041BB8 = 0;
    dword_180041BBC = 0;
    qword_180041BA8 = (__int64)&udk::CopilotPlusDetection::HardwareRequirementsTelemetryLogging::`vftable';
    qword_180041BC0 = (__int64)&`SearchOptionsLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_7f96684195f1828cecb0bb0d44a2a97f_::_lambda_invoker_cdecl_);
    v6 = (_QWORD *)qword_180041BC0;
    qword_180041BB0 = qword_180041BC0;
    byte_180041BB8 = 1;
    v14 = *(_OWORD *)(*(_QWORD *)(qword_180041BC0 + 8) - 16LL);
    if ( *(_QWORD *)(qword_180041BC0 + 32) )
      __fastfail(5u);
    v7 = qword_180041BC0 + 32;
    *(_QWORD *)(qword_180041BC0 + 40) = 0;
    v6[6] = 0;
    if ( !(unsigned int)EtwEventRegister(&v14, tlgEnableCallback, v6, v7) )
      EtwEventSetInformation(v6[4], 2, v6[1], *(unsigned __int16 *)v6[1]);
    dword_180041BBC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180041BA8 + 8))(&qword_180041BA8);
    InitOnceComplete(&`SearchOptionsLogging::Instance'::`2'::wrapper, 0, &qword_180041BA8);
  }
  v8 = (unsigned int *)*((_QWORD *)Context + 1);
  result = *v8;
  if ( (unsigned int)result > 5 )
  {
    fPending = *a3;
    LODWORD(v12) = *a2;
    HIDWORD(v12) = *a1;
    v26 = &v13;
    p_fPending = &fPending;
    v22 = &v12;
    v20 = (char *)&v12 + 4;
    v15 = (unsigned __int16 *)*((_QWORD *)v8 + 1);
    v13 = 0x1000000;
    v27 = 8;
    v25 = 4;
    v23 = 4;
    v21 = 4;
    v14 = 0x50B000000uLL;
    v16 = *v15;
    v18 = &unk_180039378;
    v17 = 2;
    v19 = 0x100000047LL;
    LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    return ((__int64 (__fastcall *)(_QWORD, __int128 *, _QWORD, _QWORD, int, unsigned __int16 **, WINBOOL, LPVOID, __int64, __int64))EtwEventWriteTransfer)(
             *((_QWORD *)v8 + 4),
             &v14,
             0,
             0,
             6,
             &v15,
             fPending,
             Context,
             v12,
             0x1000000);
  }
  return result;
}

```

## disassembly

```asm
0x1800172d0  push    rbp
0x1800172d2  push    rsi
0x1800172d3  push    r12
0x1800172d5  push    r14
0x1800172d7  push    r15
0x1800172d9  lea     rbp, [rsp-37h]
0x1800172de  sub     rsp, 0D0h
0x1800172e5  mov     rax, cs:__security_cookie
0x1800172ec  xor     rax, rsp
0x1800172ef  mov     [rbp+57h+var_30], rax
0x1800172f3  mov     rsi, r8
0x1800172f6  lea     r9, [rbp+57h+Context]; lpContext
0x1800172fa  mov     r14, rdx
0x1800172fd  lea     r8, [rbp+57h+fPending]; fPending
0x180017301  mov     r15, rcx
0x180017304  xor     r12d, r12d
0x180017307  xor     edx, edx; dwFlags
0x180017309  mov     [rbp+57h+Context], r12
0x18001730d  lea     rcx, ?wrapper@?1??Instance@SearchOptionsLogging@@KAPEAV2@XZ@4V?$static_lazy@VSearchOptionsLogging@@@details@wil@@A; lpInitOnce
0x180017314  mov     [rbp+57h+fPending], r12d
0x180017318  call    cs:__imp_InitOnceBeginInitialize
0x18001731e  test    eax, eax
0x180017320  jz      loc_180017440
0x180017326  cmp     [rbp+57h+fPending], r12d
0x18001732a  jz      loc_180017440
0x180017330  mov     [rsp+0F0h+arg_0], rbx
0x180017338  lea     rax, ??_7HardwareRequirementsTelemetryLogging@CopilotPlusDetection@udk@@6B@; const udk::CopilotPlusDetection::HardwareRequirementsTelemetryLogging::`vftable'
0x18001733f  mov     [rsp+0F0h+arg_8], rdi
0x180017347  mov     [rsp+0F0h+arg_10], r13
0x18001734f  lea     r13, qword_180041BA8
0x180017356  mov     [rbp+57h+Context], r13
0x18001735a  mov     cs:qword_180041BB0, r12
0x180017361  mov     cs:byte_180041BB8, r12b
0x180017368  mov     cs:dword_180041BBC, r12d
0x18001736f  mov     cs:qword_180041BA8, rax
0x180017376  lea     rax, ?__hInner@?1???0StaticHandle@SearchOptionsLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SearchOptionsLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001737d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_7f96684195f1828cecb0bb0d44a2a97f_@@CA@XZ; void (__cdecl *)()
0x180017384  mov     cs:qword_180041BC0, rax
0x18001738b  call    atexit
0x180017390  mov     rbx, cs:qword_180041BC0
0x180017397  mov     cs:qword_180041BB0, rbx
0x18001739e  mov     cs:byte_180041BB8, 1
0x1800173a5  mov     rax, [rbx+8]
0x1800173a9  movups  xmm0, xmmword ptr [rax-10h]
0x1800173ad  movups  [rbp+57h+var_A0], xmm0
0x1800173b1  cmp     [rbx+20h], r12
0x1800173b5  jz      short loc_1800173BE
0x1800173b7  mov     ecx, 5
0x1800173bc  int     29h; Win8: RtlFailFast(ecx)
0x1800173be  lea     r9, [rbx+20h]
0x1800173c2  mov     [rbx+28h], r12
0x1800173c6  mov     r8, rbx
0x1800173c9  mov     [rbx+30h], r12
0x1800173cd  lea     rdx, _tlgEnableCallback
0x1800173d4  lea     rcx, [rbp+57h+var_A0]
0x1800173d8  call    cs:__imp_EtwEventRegister
0x1800173de  test    eax, eax
0x1800173e0  jnz     short loc_1800173F9
0x1800173e2  mov     r8, [rbx+8]
0x1800173e6  mov     edx, 2
0x1800173eb  mov     rcx, [rbx+20h]
0x1800173ef  movzx   r9d, word ptr [r8]
0x1800173f3  call    cs:__imp_EtwEventSetInformation
0x1800173f9  mov     rax, cs:qword_180041BA8
0x180017400  mov     rcx, r13
0x180017403  mov     cs:dword_180041BBC, 1
0x18001740d  mov     rax, [rax+8]
0x180017411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017416  mov     r8, r13; lpContext
0x180017419  lea     rcx, ?wrapper@?1??Instance@SearchOptionsLogging@@KAPEAV2@XZ@4V?$static_lazy@VSearchOptionsLogging@@@details@wil@@A; lpInitOnce
0x180017420  xor     edx, edx; dwFlags
0x180017422  call    cs:__imp_InitOnceComplete
0x180017428  mov     r13, [rsp+0F0h+arg_10]
0x180017430  mov     rdi, [rsp+0F0h+arg_8]
0x180017438  mov     rbx, [rsp+0F0h+arg_0]
0x180017440  mov     rax, [rbp+57h+Context]
0x180017444  mov     rcx, [rax+8]
0x180017448  mov     eax, [rcx]
0x18001744a  cmp     eax, 5
0x18001744d  jbe     loc_18001752A
0x180017453  mov     eax, [rsi]
0x180017455  lea     rdx, _TraceLoggingMetadata
0x18001745c  mov     [rbp+57h+fPending], eax
0x18001745f  xor     r9d, r9d
0x180017462  mov     eax, [r14]
0x180017465  xor     r8d, r8d
0x180017468  mov     [rbp+57h+var_B0], eax
0x18001746b  mov     eax, [r15]
0x18001746e  mov     [rbp+57h+var_AC], eax
0x180017471  lea     rax, [rbp+57h+var_A8]
0x180017475  mov     [rbp+57h+var_40], rax
0x180017479  lea     rax, [rbp+57h+fPending]
0x18001747d  mov     [rbp+57h+var_50], rax
0x180017481  lea     rax, [rbp+57h+var_B0]
0x180017485  mov     [rbp+57h+var_60], rax
0x180017489  lea     rax, [rbp+57h+var_AC]
0x18001748d  mov     [rbp+57h+var_70], rax
0x180017491  movzx   eax, cs:word_18003936E
0x180017498  mov     dword ptr [rbp+57h+var_A0+4], eax
0x18001749b  mov     rax, [rcx+8]
0x18001749f  mov     [rbp+57h+var_90], rax
0x1800174a3  mov     [rbp+57h+var_A8], 1000000h
0x1800174ab  mov     [rbp+57h+var_38], 8
0x1800174b3  mov     [rbp+57h+var_48], 4
0x1800174bb  mov     [rbp+57h+var_58], 4
0x1800174c3  mov     [rbp+57h+var_68], 4
0x1800174cb  mov     dword ptr [rbp+57h+var_A0], 0B000000h
0x1800174d2  mov     qword ptr [rbp+57h+var_A0+8], r12
0x1800174d6  movzx   eax, word ptr [rax]
0x1800174d9  mov     [rbp+57h+var_88], eax
0x1800174dc  lea     rax, unk_180039378
0x1800174e3  mov     [rbp+57h+var_80], rax
0x1800174e7  lea     rax, _TraceLoggingMetadataEnd
0x1800174ee  sub     eax, edx
0x1800174f0  mov     [rbp+57h+var_84], 2
0x1800174f7  mov     dword ptr [rbp+57h+var_78], 47h ; 'G'
0x1800174fe  lea     rdx, [rbp+57h+var_A0]
0x180017502  mov     dword ptr [rbp+57h+var_78+4], 1
0x180017509  mov     dword ptr [rbp+57h+Context], eax
0x18001750c  mov     eax, dword ptr [rbp+57h+Context]
0x18001750f  mov     rcx, [rcx+20h]
0x180017513  lea     rax, [rbp+57h+var_90]
0x180017517  mov     [rsp+0F0h+var_C8], rax
0x18001751c  mov     [rsp+0F0h+var_D0], 6
0x180017524  call    cs:__imp_EtwEventWriteTransfer
0x18001752a  mov     rcx, [rbp+57h+var_30]
0x18001752e  xor     rcx, rsp; StackCookie
0x180017531  call    __security_check_cookie
0x180017536  add     rsp, 0D0h
0x18001753d  pop     r15
0x18001753f  pop     r14
0x180017541  pop     r12
0x180017543  pop     rsi
0x180017544  pop     rbp
0x180017545  retn
```
