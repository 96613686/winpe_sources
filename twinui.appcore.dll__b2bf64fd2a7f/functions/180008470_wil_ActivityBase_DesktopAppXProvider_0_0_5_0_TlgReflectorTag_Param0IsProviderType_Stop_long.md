# wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180008470`
- end: `0x18000872e`
- name: `?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `702`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006f30`
- `0x1800079e4`
- `0x180024c0c`

## callees

- `0x180008470`
- `0x180015548`
- `0x1800166e4`
- `0x180016be8`
- `0x18002b1b0`
- `0x18002b590`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800085cf`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800085cf`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000855a`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000855a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800084b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800084b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000851f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800084e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000851f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800086c1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800086c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800085e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800085e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        const struct wil::FailureInfo *a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  __int64 v5; // rax
  int v6; // esi
  int v7; // esi
  void (*v8)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  _QWORD *Ptr; // rbx
  const GUID *v10; // r8
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v18; // [rsp+70h] [rbp-90h]
  __int128 v19; // [rsp+80h] [rbp-80h]
  __int128 v20; // [rsp+90h] [rbp-70h]
  __int128 v21; // [rsp+A0h] [rbp-60h]
  __int128 v22; // [rsp+B0h] [rbp-50h]
  __int128 v23; // [rsp+C0h] [rbp-40h]
  __int128 v24; // [rsp+D0h] [rbp-30h]
  __int128 v25; // [rsp+E0h] [rbp-20h]
  __int64 v26; // [rsp+F0h] [rbp-10h]

  v3 = (RTL_SRWLOCK *)a1[35];
  if ( v3 )
  {
    v4 = v3 + 33;
    AcquireSRWLockExclusive(v4);
    SRWLock = 0;
  }
  else
  {
    v14 = 0;
    v4 = 0;
  }
  v5 = a1[34];
  v6 = *(_DWORD *)(v5 + 248);
  if ( v6 < 1 )
  {
    UserData = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    wil::details::WilFailFast((wil::details *)&UserData, a2);
  }
  if ( *(int *)(v5 + 72) >= 0 )
    *(_DWORD *)(v5 + 72) = 0;
  v7 = v6 - 1;
  *(_DWORD *)(v5 + 248) = v7;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  if ( v7 )
  {
    SRWLock = 0;
    fPending = 0;
    if ( InitOnceBeginInitialize(&`DesktopAppXProvider::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
      && fPending )
    {
      SRWLock = (PSRWLOCK)&qword_1800B3460;
      qword_1800B3468 = 0;
      byte_1800B3470 = 0;
      dword_1800B3474 = 0;
      qword_1800B3460 = &PickerTelemetryProvider::`vftable';
      qword_1800B3478 = (struct _tlgProvider_t *)&`DesktopAppXProvider::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(_lambda_7d47696adb3c506dad77b6b0f3bb8e0c_::_lambda_invoker_cdecl_);
      wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800B3460, qword_1800B3478, v8);
      InitOnceComplete(&`DesktopAppXProvider::Instance'::`2'::wrapper, 0, &qword_1800B3460);
    }
    Ptr = SRWLock[1].Ptr;
    if ( *(_DWORD *)Ptr > 5u )
    {
      fPending = GetCurrentThreadId();
      LODWORD(v14) = 0;
      v15 = 0x1000000;
      v10 = (const GUID *)(a1[34] + 8LL);
      *(_QWORD *)&v21 = &fPending;
      *((_QWORD *)&v21 + 1) = 4;
      *(_QWORD *)&v20 = &v14;
      *((_QWORD *)&v20 + 1) = 4;
      *(_QWORD *)&v19 = &v15;
      *((_QWORD *)&v19 + 1) = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = Ptr[1];
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      *(_QWORD *)&v18 = byte_18009F153;
      *((_QWORD *)&v18 + 1) = 0x10000004DLL;
      LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(Ptr[4], &EventDescriptor, v10, 0, 5u, &UserData);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  return wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180008470  mov     [rsp-8+arg_8], rbx
0x180008475  mov     [rsp-8+arg_10], rsi
0x18000847a  push    rbp
0x18000847b  push    rdi
0x18000847c  push    r14
0x18000847e  lea     rbp, [rsp-10h]
0x180008483  sub     rsp, 110h
0x18000848a  mov     rax, cs:__security_cookie
0x180008491  xor     rax, rsp
0x180008494  mov     [rbp+20h+var_20], rax
0x180008498  mov     rdi, rcx
0x18000849b  xor     r14d, r14d
0x18000849e  mov     rbx, [rcx+118h]
0x1800084a5  test    rbx, rbx
0x1800084a8  jz      short loc_1800084D4
0x1800084aa  add     rbx, 108h
0x1800084b1  mov     rcx, rbx; SRWLock
0x1800084b4  call    cs:__imp_AcquireSRWLockExclusive
0x1800084ba  lea     rax, [rsp+120h+SRWLock]
0x1800084bf  mov     [rax], r14
0x1800084c2  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x1800084c7  test    rcx, rcx
0x1800084ca  jz      short loc_1800084EF
0x1800084cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800084d2  jmp     short loc_1800084EF
0x1800084d4  lea     rax, [rsp+120h+var_E0]
0x1800084d9  mov     [rax], r14
0x1800084dc  mov     rcx, [rsp+120h+var_E0]; SRWLock
0x1800084e1  test    rcx, rcx
0x1800084e4  jz      short loc_1800084EC
0x1800084e6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800084ec  mov     rbx, r14
0x1800084ef  mov     rax, [rdi+110h]
0x1800084f6  mov     esi, [rax+0F8h]
0x1800084fc  cmp     esi, 1
0x1800084ff  jl      loc_1800086F4
0x180008505  cmp     dword ptr [rax+48h], 0
0x180008509  jl      short loc_18000850F
0x18000850b  mov     [rax+48h], r14d
0x18000850f  dec     esi
0x180008511  mov     [rax+0F8h], esi
0x180008517  test    rbx, rbx
0x18000851a  jz      short loc_180008525
0x18000851c  mov     rcx, rbx; SRWLock
0x18000851f  call    cs:__imp_ReleaseSRWLockExclusive
0x180008525  test    esi, esi
0x180008527  jnz     short loc_18000853D
0x180008529  mov     rax, [rdi]
0x18000852c  mov     rcx, rdi
0x18000852f  mov     rax, [rax+8]
0x180008533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008538  jmp     loc_1800086C7
0x18000853d  mov     [rsp+120h+SRWLock], r14
0x180008542  mov     [rsp+120h+fPending], r14d
0x180008547  lea     r9, [rsp+120h+SRWLock]; lpContext
0x18000854c  lea     r8, [rsp+120h+fPending]; fPending
0x180008551  xor     edx, edx; dwFlags
0x180008553  lea     rcx, ?wrapper@?1??Instance@DesktopAppXProvider@@KAPEAV2@XZ@4V?$static_lazy@VDesktopAppXProvider@@@details@wil@@A; lpInitOnce
0x18000855a  call    cs:__imp_InitOnceBeginInitialize
0x180008560  test    eax, eax
0x180008562  jz      short loc_1800085D5
0x180008564  cmp     [rsp+120h+fPending], 0
0x180008569  jz      short loc_1800085D5
0x18000856b  lea     rbx, qword_1800B3460
0x180008572  mov     [rsp+120h+SRWLock], rbx
0x180008577  mov     cs:qword_1800B3468, r14
0x18000857e  mov     cs:byte_1800B3470, 0
0x180008585  mov     cs:dword_1800B3474, r14d
0x18000858c  lea     rax, ??_7PickerTelemetryProvider@@6B@; const PickerTelemetryProvider::`vftable'
0x180008593  mov     cs:qword_1800B3460, rax
0x18000859a  lea     rax, ?__hInner@?1???0StaticHandle@DesktopAppXProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DesktopAppXProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800085a1  mov     cs:qword_1800B3478, rax
0x1800085a8  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_7d47696adb3c506dad77b6b0f3bb8e0c_@@CA@XZ; void (__cdecl *)()
0x1800085af  call    atexit
0x1800085b4  mov     rdx, cs:qword_1800B3478; struct _tlgProvider_t *
0x1800085bb  mov     rcx, rbx; this
0x1800085be  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800085c3  mov     r8, rbx; lpContext
0x1800085c6  xor     edx, edx; dwFlags
0x1800085c8  lea     rcx, ?wrapper@?1??Instance@DesktopAppXProvider@@KAPEAV2@XZ@4V?$static_lazy@VDesktopAppXProvider@@@details@wil@@A; lpInitOnce
0x1800085cf  call    cs:__imp_InitOnceComplete
0x1800085d5  mov     rax, [rsp+120h+SRWLock]
0x1800085da  mov     rbx, [rax+8]
0x1800085de  mov     eax, [rbx]
0x1800085e0  cmp     eax, 5
0x1800085e3  jbe     loc_1800086C7
0x1800085e9  call    cs:__imp_GetCurrentThreadId
0x1800085ef  mov     [rsp+120h+fPending], eax
0x1800085f3  mov     dword ptr [rsp+120h+var_E0], r14d
0x1800085f8  mov     [rsp+120h+var_D8], 1000000h
0x180008601  mov     r8, [rdi+110h]
0x180008608  add     r8, 8; ActivityId
0x18000860c  lea     rax, [rsp+120h+fPending]
0x180008611  mov     qword ptr [rbp+20h+var_80], rax
0x180008615  mov     qword ptr [rbp+20h+var_80+8], 4
0x18000861d  lea     rax, [rsp+120h+var_E0]
0x180008622  mov     qword ptr [rbp+20h+var_90], rax
0x180008626  mov     qword ptr [rbp+20h+var_90+8], 4
0x18000862e  lea     rax, [rsp+120h+var_D8]
0x180008633  mov     qword ptr [rbp+20h+var_A0], rax
0x180008637  mov     qword ptr [rbp+20h+var_A0+8], 8
0x18000863f  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x180008647  movzx   eax, cs:word_18009F149
0x18000864e  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x180008652  mov     [rsp+120h+EventDescriptor.Keyword], r14
0x180008657  mov     rax, [rbx+8]
0x18000865b  mov     [rsp+120h+var_C0.Ptr], rax
0x180008660  movzx   eax, word ptr [rax]
0x180008663  mov     [rsp+120h+var_C0.Size], eax
0x180008667  mov     dword ptr [rsp+120h+var_C0.0Ch], 2
0x18000866f  lea     rax, byte_18009F153
0x180008676  mov     qword ptr [rsp+120h+var_B0], rax
0x18000867b  mov     dword ptr [rsp+120h+var_B0+8], 4Dh ; 'M'
0x180008683  mov     dword ptr [rsp+120h+var_B0+0Ch], 1
0x18000868b  lea     rax, _TraceLoggingMetadataEnd
0x180008692  lea     rcx, _TraceLoggingMetadata
0x180008699  sub     eax, ecx
0x18000869b  mov     dword ptr [rsp+120h+SRWLock], eax
0x18000869f  mov     eax, dword ptr [rsp+120h+SRWLock]
0x1800086a3  lea     rax, [rsp+120h+var_C0]
0x1800086a8  mov     [rsp+120h+UserData], rax; UserData
0x1800086ad  mov     [rsp+120h+UserDataCount], 5; UserDataCount
0x1800086b5  xor     r9d, r9d; RelatedActivityId
0x1800086b8  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x1800086bd  mov     rcx, [rbx+20h]; RegHandle
0x1800086c1  call    cs:__imp_EventWriteTransfer
0x1800086c7  mov     rcx, rdi
0x1800086ca  call    ?IgnoreCurrentThread@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800086cf  nop
0x1800086d0  mov     rcx, [rbp+20h+var_20]
0x1800086d4  xor     rcx, rsp; StackCookie
0x1800086d7  call    __security_check_cookie
0x1800086dc  lea     r11, [rsp+120h+var_10]
0x1800086e4  mov     rbx, [r11+28h]
0x1800086e8  mov     rsi, [r11+30h]
0x1800086ec  mov     rsp, r11
0x1800086ef  pop     r14
0x1800086f1  pop     rdi
0x1800086f2  pop     rbp
0x1800086f3  retn
0x1800086f4  xorps   xmm0, xmm0
0x1800086f7  xor     eax, eax
0x1800086f9  movups  xmmword ptr [rsp+120h+var_C0.Ptr], xmm0
0x1800086fe  movups  [rsp+120h+var_B0], xmm0
0x180008703  movups  [rbp+20h+var_A0], xmm0
0x180008707  movups  [rbp+20h+var_90], xmm0
0x18000870b  movups  [rbp+20h+var_80], xmm0
0x18000870f  movups  [rbp+20h+var_70], xmm0
0x180008713  movups  [rbp+20h+var_60], xmm0
0x180008717  movups  [rbp+20h+var_50], xmm0
0x18000871b  movups  [rbp+20h+var_40], xmm0
0x18000871f  mov     [rbp+20h+var_30], rax
0x180008723  lea     rcx, [rsp+120h+var_C0]; this
0x180008728  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
