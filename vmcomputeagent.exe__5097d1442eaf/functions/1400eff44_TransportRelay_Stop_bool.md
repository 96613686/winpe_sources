# TransportRelay::Stop(bool)

- ea: `0x1400eff44`
- end: `0x1400f017b`
- name: `?Stop@TransportRelay@@QEAAX_N@Z`
- size: `567`
- prototype: `void __fastcall(TransportRelay *__hidden this, bool)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400edfd0`
- `0x1400ee6d8`
- `0x1400f2350`

## callees

- `0x140005360`
- `0x140006098`
- `0x14000ea44`
- `0x1400d5c40`
- `0x1400ee350`
- `0x1400ee5b8`
- `0x1400eec70`
- `0x1400efe04`
- `0x1400eff44`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f0084`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400f0084`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f0051`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400f0051`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400f00a3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400f00a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1400f00c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1400f00c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f0057`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400f0057`

## string_xrefs

- `0x1400f0169`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall TransportRelay::Stop(TransportRelay *this, char a2)
{
  _QWORD *v4; // rax
  char v5; // r14
  const char *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rcx
  _QWORD *v9; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v10[8]; // [rsp+28h] [rbp-D8h] BYREF
  void **v11; // [rsp+30h] [rbp-D0h] BYREF
  int v12; // [rsp+38h] [rbp-C8h] BYREF
  char v13; // [rsp+3Ch] [rbp-C4h]
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  const char *v15; // [rsp+68h] [rbp-98h]
  __int64 v16; // [rsp+70h] [rbp-90h]
  char v17; // [rsp+78h] [rbp-88h]
  int v18; // [rsp+80h] [rbp-80h]
  _BYTE v19[152]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v20; // [rsp+120h] [rbp+20h]
  int v21; // [rsp+130h] [rbp+30h]
  __int64 v22; // [rsp+138h] [rbp+38h]
  int *v23; // [rsp+140h] [rbp+40h]
  __int64 v24; // [rsp+148h] [rbp+48h]
  __int64 v25; // [rsp+150h] [rbp+50h]
  void ***v26; // [rsp+158h] [rbp+58h]
  __int64 v27; // [rsp+160h] [rbp+60h]
  int v28; // [rsp+168h] [rbp+68h]
  int *v29; // [rsp+170h] [rbp+70h]
  char v30; // [rsp+178h] [rbp+78h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v10[0] = a2;
  memset_0(&v11, 0, 0x150u);
  v4 = (_QWORD *)((char *)this + 200);
  if ( *((_QWORD *)this + 28) > 7u )
    v4 = (_QWORD *)*v4;
  v9 = v4;
  v12 = 0;
  v13 = 0;
  v17 = 0;
  v14 = 0;
  v15 = "TransportRelay_Stop";
  v16 = 0;
  v18 = 0;
  v20 = 0;
  memset_0(v19, 0, sizeof(v19));
  v21 = 1;
  v22 = 0;
  v23 = &v12;
  v24 = 0;
  v25 = 0;
  v26 = &v11;
  v27 = 0;
  v28 = 0;
  v29 = &v14;
  v30 = 0;
  v11 = &ComputeService::Diagnostics::TraceProvider::TransportRelay_Stop::`vftable';
  ComputeService::Diagnostics::TraceProvider::TransportRelay_Stop::StartActivity<unsigned short const *,bool &>(
    &v11,
    &v9,
    v10);
  v5 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 15);
  *((_DWORD *)this + 32) = GetCurrentThreadId();
  if ( *((_DWORD *)this + 34) != 7 )
  {
    v5 = 1;
    *((_DWORD *)this + 34) = 7;
  }
  *((_DWORD *)this + 32) = 0;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 15);
  if ( v5 )
  {
    if ( *((_QWORD *)this + 22) )
    {
      if ( !SetEvent(*((HANDLE *)this + 23)) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v6);
      WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 22), 1);
    }
    if ( a2 && *(_BYTE *)(*((_QWORD *)this + 7) + 72LL) )
      ComputeService::Management::CancellationToken::Wait(
        (TransportRelay *)((char *)this + 72),
        *(void **)(*((_QWORD *)this + 7) + 56LL),
        0xFFFFFFFF);
    v7 = *((_QWORD *)this + 3);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 48LL))(v7);
    v8 = *((_QWORD *)this + 1);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8);
  }
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v11);
  v11 = &ComputeService::Diagnostics::TraceProvider::TransportRelay_Stop::`vftable';
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v11);
  wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>(&v11);
}

```

## disassembly

```asm
0x1400eff44  mov     [rsp-8+arg_10], rbx
0x1400eff49  mov     [rsp-8+arg_18], rsi
0x1400eff4e  push    rbp
0x1400eff4f  push    rdi
0x1400eff50  push    r13
0x1400eff52  push    r14
0x1400eff54  push    r15
0x1400eff56  lea     rbp, [rsp-90h]
0x1400eff5e  sub     rsp, 190h
0x1400eff65  mov     rax, cs:__security_cookie
0x1400eff6c  xor     rax, rsp
0x1400eff6f  mov     [rbp+0B0h+var_30], rax
0x1400eff76  mov     dil, dl
0x1400eff79  mov     rbx, rcx
0x1400eff7c  mov     [rsp+1B0h+var_188], dl
0x1400eff80  xor     edx, edx; Val
0x1400eff82  mov     r8d, 150h; Size
0x1400eff88  lea     rcx, [rsp+1B0h+var_180]; void *
0x1400eff8d  call    memset_0
0x1400eff92  lea     rax, [rbx+0C8h]
0x1400eff99  cmp     qword ptr [rax+18h], 7
0x1400eff9e  jbe     short loc_1400EFFA3
0x1400effa0  mov     rax, [rax]
0x1400effa3  mov     [rsp+1B0h+var_190], rax
0x1400effa8  xor     r15d, r15d
0x1400effab  mov     [rsp+1B0h+var_178], r15d
0x1400effb0  mov     [rsp+1B0h+var_174], r15b
0x1400effb5  mov     [rsp+1B0h+var_138], r15b
0x1400effba  mov     [rsp+1B0h+var_150], r15d
0x1400effbf  lea     rax, aTransportrelay; "TransportRelay_Stop"
0x1400effc6  mov     [rsp+1B0h+var_148], rax
0x1400effcb  mov     [rsp+1B0h+var_140], r15
0x1400effd0  mov     [rbp+0B0h+var_130], r15d
0x1400effd4  xorps   xmm0, xmm0
0x1400effd7  movdqa  [rbp+0B0h+var_90], xmm0
0x1400effdc  xor     edx, edx; Val
0x1400effde  mov     r8d, 98h; Size
0x1400effe4  lea     rcx, [rbp+0B0h+var_128]; void *
0x1400effe8  call    memset_0
0x1400effed  mov     [rbp+0B0h+var_80], 1
0x1400efff4  xor     eax, eax
0x1400efff6  mov     [rbp+0B0h+var_78], rax
0x1400efffa  lea     rax, [rsp+1B0h+var_178]
0x1400effff  mov     [rbp+0B0h+var_70], rax
0x1400f0003  mov     [rbp+0B0h+var_68], r15
0x1400f0007  mov     [rbp+0B0h+var_60], r15
0x1400f000b  lea     rax, [rsp+1B0h+var_180]
0x1400f0010  mov     [rbp+0B0h+var_58], rax
0x1400f0014  mov     [rbp+0B0h+var_50], r15
0x1400f0018  mov     [rbp+0B0h+var_48], r15d
0x1400f001c  lea     rax, [rsp+1B0h+var_150]
0x1400f0021  mov     [rbp+0B0h+var_40], rax
0x1400f0025  mov     [rbp+0B0h+var_38], r15b
0x1400f0029  lea     r13, ??_7TransportRelay_Stop@TraceProvider@Diagnostics@ComputeService@@6B@; const ComputeService::Diagnostics::TraceProvider::TransportRelay_Stop::`vftable'
0x1400f0030  mov     [rsp+1B0h+var_180], r13
0x1400f0035  lea     r8, [rsp+1B0h+var_188]
0x1400f003a  lea     rdx, [rsp+1B0h+var_190]
0x1400f003f  lea     rcx, [rsp+1B0h+var_180]
0x1400f0044  call    ??$StartActivity@PEBGAEA_N@TransportRelay_Stop@TraceProvider@Diagnostics@ComputeService@@QEAAX$$QEAPEBGAEA_N@Z; ComputeService::Diagnostics::TraceProvider::TransportRelay_Stop::StartActivity<ushort const *,bool &>(ushort const * &&,bool &)
0x1400f0049  nop
0x1400f004a  mov     r14b, r15b
0x1400f004d  lea     rcx, [rbx+78h]; SRWLock
0x1400f0051  call    cs:__imp_AcquireSRWLockExclusive
0x1400f0057  call    cs:__imp_GetCurrentThreadId
0x1400f005d  mov     [rbx+80h], eax
0x1400f0063  cmp     dword ptr [rbx+88h], 7
0x1400f006a  jz      short loc_1400F0079
0x1400f006c  mov     r14b, 1
0x1400f006f  mov     dword ptr [rbx+88h], 7
0x1400f0079  mov     [rbx+80h], r15d
0x1400f0080  lea     rcx, [rbx+78h]; SRWLock
0x1400f0084  call    cs:__imp_ReleaseSRWLockExclusive
0x1400f008a  test    r14b, r14b
0x1400f008d  jz      loc_1400F011A
0x1400f0093  cmp     [rbx+0B0h], r15
0x1400f009a  jz      short loc_1400F00CA
0x1400f009c  mov     rcx, [rbx+0B8h]; hEvent
0x1400f00a3  call    cs:__imp_SetEvent
0x1400f00a9  mov     rcx, [rbp+0B8h]; this
0x1400f00b0  test    eax, eax
0x1400f00b2  jz      loc_1400F0169
0x1400f00b8  mov     edx, 1; fCancelPendingCallbacks
0x1400f00bd  mov     rcx, [rbx+0B0h]; pwk
0x1400f00c4  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1400f00ca  test    dil, dil
0x1400f00cd  jz      short loc_1400F00F0
0x1400f00cf  mov     rax, [rbx+38h]
0x1400f00d3  mov     cl, [rax+48h]
0x1400f00d6  nop
0x1400f00d7  test    cl, cl
0x1400f00d9  jz      short loc_1400F00F0
0x1400f00db  mov     rdx, [rbx+38h]
0x1400f00df  lea     rcx, [rbx+48h]; this
0x1400f00e3  or      r8d, 0FFFFFFFFh; unsigned int
0x1400f00e7  mov     rdx, [rdx+38h]; void *
0x1400f00eb  call    ?Wait@CancellationToken@Management@ComputeService@@QEBAXPEAXK@Z; ComputeService::Management::CancellationToken::Wait(void *,ulong)
0x1400f00f0  mov     rcx, [rbx+18h]
0x1400f00f4  test    rcx, rcx
0x1400f00f7  jz      short loc_1400F0105
0x1400f00f9  mov     rax, [rcx]
0x1400f00fc  mov     rax, [rax+30h]
0x1400f0100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f0105  mov     rcx, [rbx+8]
0x1400f0109  test    rcx, rcx
0x1400f010c  jz      short loc_1400F011A
0x1400f010e  mov     rax, [rcx]
0x1400f0111  mov     rax, [rax+30h]
0x1400f0115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f011a  lea     rcx, [rsp+1B0h+var_180]
0x1400f011f  call    ?Stop@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400f0124  nop
0x1400f0125  mov     [rsp+1B0h+var_180], r13
0x1400f012a  lea     rcx, [rsp+1B0h+var_180]
0x1400f012f  call    ?Destroy@?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400f0134  lea     rcx, [rsp+1B0h+var_180]
0x1400f0139  call    ??1?$ActivityBase@VTraceProvider@Diagnostics@ComputeService@@$0A@$0IA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ComputeService::Diagnostics::TraceProvider,0,128,4,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400f013e  mov     rcx, [rbp+0B0h+var_30]
0x1400f0145  xor     rcx, rsp; StackCookie
0x1400f0148  call    __security_check_cookie
0x1400f014d  lea     r11, [rsp+1B0h+var_20]
0x1400f0155  mov     rbx, [r11+40h]
0x1400f0159  mov     rsi, [r11+48h]
0x1400f015d  mov     rsp, r11
0x1400f0160  pop     r15
0x1400f0162  pop     r14
0x1400f0164  pop     r13
0x1400f0166  pop     rdi
0x1400f0167  pop     rbp
0x1400f0168  retn
0x1400f0169  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400f0170  mov     edx, 0A01h; void *
0x1400f0175  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
