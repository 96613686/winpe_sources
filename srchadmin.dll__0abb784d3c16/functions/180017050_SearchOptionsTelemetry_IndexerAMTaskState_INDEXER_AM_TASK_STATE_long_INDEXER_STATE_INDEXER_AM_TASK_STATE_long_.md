# SearchOptionsTelemetry::IndexerAMTaskState<INDEXER_AM_TASK_STATE,long &,INDEXER_STATE &>(INDEXER_AM_TASK_STATE &&,long &,INDEXER_STATE &)

- ea: `0x180017050`
- end: `0x1800172c6`
- name: `??$IndexerAMTaskState@W4INDEXER_AM_TASK_STATE@@AEAJAEAW4INDEXER_STATE@@@SearchOptionsTelemetry@@SAX$$QEAW4INDEXER_AM_TASK_STATE@@AEAJAEAW4INDEXER_STATE@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, WINBOOL *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018730`

## callees

- `0x180005cc0`
- `0x18000614c`
- `0x180017050`
- `0x180032010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800172a4`
- `ntdll!EtwEventWriteTransfer` at `0x1800172a4`
- `ntdll!EtwEventSetInformation` at `0x180017173`
- `ntdll!EtwEventSetInformation` at `0x180017173`
- `ntdll!EtwEventRegister` at `0x180017158`
- `ntdll!EtwEventRegister` at `0x180017158`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180017098`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180017098`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800171a2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800171a2`

## pseudocode

```c
__int64 __fastcall SearchOptionsTelemetry::IndexerAMTaskState<enum INDEXER_AM_TASK_STATE,long &,enum INDEXER_STATE &>(
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
  char *v18; // [rsp+70h] [rbp-29h]
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
    v18 = byte_180039325;
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
0x180017050  push    rbp
0x180017052  push    rsi
0x180017053  push    r12
0x180017055  push    r14
0x180017057  push    r15
0x180017059  lea     rbp, [rsp-37h]
0x18001705e  sub     rsp, 0D0h
0x180017065  mov     rax, cs:__security_cookie
0x18001706c  xor     rax, rsp
0x18001706f  mov     [rbp+57h+var_30], rax
0x180017073  mov     rsi, r8
0x180017076  lea     r9, [rbp+57h+Context]; lpContext
0x18001707a  mov     r14, rdx
0x18001707d  lea     r8, [rbp+57h+fPending]; fPending
0x180017081  mov     r15, rcx
0x180017084  xor     r12d, r12d
0x180017087  xor     edx, edx; dwFlags
0x180017089  mov     [rbp+57h+Context], r12
0x18001708d  lea     rcx, ?wrapper@?1??Instance@SearchOptionsLogging@@KAPEAV2@XZ@4V?$static_lazy@VSearchOptionsLogging@@@details@wil@@A; lpInitOnce
0x180017094  mov     [rbp+57h+fPending], r12d
0x180017098  call    cs:__imp_InitOnceBeginInitialize
0x18001709e  test    eax, eax
0x1800170a0  jz      loc_1800171C0
0x1800170a6  cmp     [rbp+57h+fPending], r12d
0x1800170aa  jz      loc_1800171C0
0x1800170b0  mov     [rsp+0F0h+arg_0], rbx
0x1800170b8  lea     rax, ??_7HardwareRequirementsTelemetryLogging@CopilotPlusDetection@udk@@6B@; const udk::CopilotPlusDetection::HardwareRequirementsTelemetryLogging::`vftable'
0x1800170bf  mov     [rsp+0F0h+arg_8], rdi
0x1800170c7  mov     [rsp+0F0h+arg_10], r13
0x1800170cf  lea     r13, qword_180041BA8
0x1800170d6  mov     [rbp+57h+Context], r13
0x1800170da  mov     cs:qword_180041BB0, r12
0x1800170e1  mov     cs:byte_180041BB8, r12b
0x1800170e8  mov     cs:dword_180041BBC, r12d
0x1800170ef  mov     cs:qword_180041BA8, rax
0x1800170f6  lea     rax, ?__hInner@?1???0StaticHandle@SearchOptionsLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SearchOptionsLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800170fd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_7f96684195f1828cecb0bb0d44a2a97f_@@CA@XZ; void (__cdecl *)()
0x180017104  mov     cs:qword_180041BC0, rax
0x18001710b  call    atexit
0x180017110  mov     rbx, cs:qword_180041BC0
0x180017117  mov     cs:qword_180041BB0, rbx
0x18001711e  mov     cs:byte_180041BB8, 1
0x180017125  mov     rax, [rbx+8]
0x180017129  movups  xmm0, xmmword ptr [rax-10h]
0x18001712d  movups  [rbp+57h+var_A0], xmm0
0x180017131  cmp     [rbx+20h], r12
0x180017135  jz      short loc_18001713E
0x180017137  mov     ecx, 5
0x18001713c  int     29h; Win8: RtlFailFast(ecx)
0x18001713e  lea     r9, [rbx+20h]
0x180017142  mov     [rbx+28h], r12
0x180017146  mov     r8, rbx
0x180017149  mov     [rbx+30h], r12
0x18001714d  lea     rdx, _tlgEnableCallback
0x180017154  lea     rcx, [rbp+57h+var_A0]
0x180017158  call    cs:__imp_EtwEventRegister
0x18001715e  test    eax, eax
0x180017160  jnz     short loc_180017179
0x180017162  mov     r8, [rbx+8]
0x180017166  mov     edx, 2
0x18001716b  mov     rcx, [rbx+20h]
0x18001716f  movzx   r9d, word ptr [r8]
0x180017173  call    cs:__imp_EtwEventSetInformation
0x180017179  mov     rax, cs:qword_180041BA8
0x180017180  mov     rcx, r13
0x180017183  mov     cs:dword_180041BBC, 1
0x18001718d  mov     rax, [rax+8]
0x180017191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017196  mov     r8, r13; lpContext
0x180017199  lea     rcx, ?wrapper@?1??Instance@SearchOptionsLogging@@KAPEAV2@XZ@4V?$static_lazy@VSearchOptionsLogging@@@details@wil@@A; lpInitOnce
0x1800171a0  xor     edx, edx; dwFlags
0x1800171a2  call    cs:__imp_InitOnceComplete
0x1800171a8  mov     r13, [rsp+0F0h+arg_10]
0x1800171b0  mov     rdi, [rsp+0F0h+arg_8]
0x1800171b8  mov     rbx, [rsp+0F0h+arg_0]
0x1800171c0  mov     rax, [rbp+57h+Context]
0x1800171c4  mov     rcx, [rax+8]
0x1800171c8  mov     eax, [rcx]
0x1800171ca  cmp     eax, 5
0x1800171cd  jbe     loc_1800172AA
0x1800171d3  mov     eax, [rsi]
0x1800171d5  lea     rdx, _TraceLoggingMetadata
0x1800171dc  mov     [rbp+57h+fPending], eax
0x1800171df  xor     r9d, r9d
0x1800171e2  mov     eax, [r14]
0x1800171e5  xor     r8d, r8d
0x1800171e8  mov     [rbp+57h+var_B0], eax
0x1800171eb  mov     eax, [r15]
0x1800171ee  mov     [rbp+57h+var_AC], eax
0x1800171f1  lea     rax, [rbp+57h+var_A8]
0x1800171f5  mov     [rbp+57h+var_40], rax
0x1800171f9  lea     rax, [rbp+57h+fPending]
0x1800171fd  mov     [rbp+57h+var_50], rax
0x180017201  lea     rax, [rbp+57h+var_B0]
0x180017205  mov     [rbp+57h+var_60], rax
0x180017209  lea     rax, [rbp+57h+var_AC]
0x18001720d  mov     [rbp+57h+var_70], rax
0x180017211  movzx   eax, cs:word_18003931B
0x180017218  mov     dword ptr [rbp+57h+var_A0+4], eax
0x18001721b  mov     rax, [rcx+8]
0x18001721f  mov     [rbp+57h+var_90], rax
0x180017223  mov     [rbp+57h+var_A8], 1000000h
0x18001722b  mov     [rbp+57h+var_38], 8
0x180017233  mov     [rbp+57h+var_48], 4
0x18001723b  mov     [rbp+57h+var_58], 4
0x180017243  mov     [rbp+57h+var_68], 4
0x18001724b  mov     dword ptr [rbp+57h+var_A0], 0B000000h
0x180017252  mov     qword ptr [rbp+57h+var_A0+8], r12
0x180017256  movzx   eax, word ptr [rax]
0x180017259  mov     [rbp+57h+var_88], eax
0x18001725c  lea     rax, byte_180039325
0x180017263  mov     [rbp+57h+var_80], rax
0x180017267  lea     rax, _TraceLoggingMetadataEnd
0x18001726e  sub     eax, edx
0x180017270  mov     [rbp+57h+var_84], 2
0x180017277  mov     dword ptr [rbp+57h+var_78], 47h ; 'G'
0x18001727e  lea     rdx, [rbp+57h+var_A0]
0x180017282  mov     dword ptr [rbp+57h+var_78+4], 1
0x180017289  mov     dword ptr [rbp+57h+Context], eax
0x18001728c  mov     eax, dword ptr [rbp+57h+Context]
0x18001728f  mov     rcx, [rcx+20h]
0x180017293  lea     rax, [rbp+57h+var_90]
0x180017297  mov     [rsp+0F0h+var_C8], rax
0x18001729c  mov     [rsp+0F0h+var_D0], 6
0x1800172a4  call    cs:__imp_EtwEventWriteTransfer
0x1800172aa  mov     rcx, [rbp+57h+var_30]
0x1800172ae  xor     rcx, rsp; StackCookie
0x1800172b1  call    __security_check_cookie
0x1800172b6  add     rsp, 0D0h
0x1800172bd  pop     r15
0x1800172bf  pop     r14
0x1800172c1  pop     r12
0x1800172c3  pop     rsi
0x1800172c4  pop     rbp
0x1800172c5  retn
```
