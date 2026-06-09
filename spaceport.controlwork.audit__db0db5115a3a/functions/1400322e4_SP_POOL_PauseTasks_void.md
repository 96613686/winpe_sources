# SP_POOL::PauseTasks(void)

- ea: `0x1400322e4`
- end: `0x140032586`
- name: `?PauseTasks@SP_POOL@@QEAAXXZ`
- size: `674`
- prototype: `void __fastcall(SP_POOL *__hidden this)`
- caller_count: `14`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14002f610`
- `0x14002f6cc`
- `0x140033840`
- `0x14003b610`
- `0x14003bc50`
- `0x14009cbe0`
- `0x14009cd30`
- `0x14009d910`
- `0x14009df3c`
- `0x14009e3e4`
- `0x14009e9d0`
- `0x14009ee20`
- `0x1400a0e0c`
- `0x1400a402c`

## callees

- `0x14000200c`
- `0x140002c94`
- `0x14002c3ec`
- `0x1400322e4`
- `0x140032964`
- `0x140067fc0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14003239c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003239c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003233c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003233c`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003242b`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003242b`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400324f4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400324f4`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140032322`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140032358`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140032322`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140032358`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140032378`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140032378`

## pseudocode

```c
void __fastcall SP_POOL::PauseTasks(KSPIN_LOCK *this)
{
  ULONGLONG UnbiasedInterruptTime; // rsi
  ULONGLONG *v3; // rbx
  int v4; // r15d
  unsigned __int64 v5; // rbx
  __int64 v6; // rcx
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // r14
  int v9; // r8d
  __int64 i; // rcx
  char *v11; // rax
  char *v12; // rax
  __int64 v13; // rcx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  int v17; // [rsp+70h] [rbp-59h] BYREF
  int v18; // [rsp+74h] [rbp-55h] BYREF
  int v19; // [rsp+78h] [rbp-51h] BYREF
  int v20; // [rsp+7Ch] [rbp-4Dh] BYREF
  int v21; // [rsp+80h] [rbp-49h] BYREF
  char *v22; // [rsp+88h] [rbp-41h] BYREF
  unsigned __int64 v23; // [rsp+90h] [rbp-39h] BYREF
  __int64 ActivityIdThread; // [rsp+98h] [rbp-31h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-29h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A8h] [rbp-21h] BYREF
  PVOID BackTrace[2]; // [rsp+C0h] [rbp-9h] BYREF
  __int128 v28; // [rsp+D0h] [rbp+7h]

  *(_OWORD *)BackTrace = 0;
  v28 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  KeAcquireInStackQueuedSpinLock(this + 24, &LockHandle);
  v3 = this + 25;
  if ( !*((_DWORD *)this + 46) )
    *v3 = KeQueryUnbiasedInterruptTime();
  v4 = ++*((_DWORD *)this + 46);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  KeWaitForSingleObject(this + 20, Executive, 0, 0, 0);
  v5 = (*v3 - UnbiasedInterruptTime) / 0x2710;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_e9af277499653a079df361eadb276992_Traceguids, v5);
  }
  if ( v5 > 0x7530 )
  {
    v6 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
    v7 = *(_QWORD *)(v6 + 24);
    v8 = v7 + *(unsigned int *)(v6 + 32);
    RtlCaptureStackBackTrace(1u, 4u, BackTrace, 0);
    for ( i = 0; i != 4; ++i )
    {
      v11 = (char *)BackTrace[i];
      if ( (unsigned __int64)v11 < v7 || (unsigned __int64)v11 >= v8 )
        v12 = 0;
      else
        v12 = &v11[-v7];
      BackTrace[i] = v12;
    }
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
      McTemplateK0xjddddd_EtwWriteTransfer(
        (_DWORD)this + 108,
        (unsigned int)PoolTasksPause,
        v9,
        v5,
        (__int64)this + 108,
        v4,
        (char)BackTrace[0],
        (char)BackTrace[1],
        v28,
        SBYTE8(v28));
    if ( (unsigned int)dword_14007F050 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
      {
        v17 = DWORD2(v28);
        v18 = v28;
        v19 = (int)BackTrace[1];
        v20 = (int)BackTrace[0];
        v22 = (char *)this + 108;
        v21 = v4;
        v23 = v5;
        v25 = 0x1000000;
        ActivityIdThread = IoGetActivityIdThread(v13);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)byte_140075841,
          v15,
          v16,
          (__int64)&v25,
          (__int64)&ActivityIdThread,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)&v18,
          (__int64)&v17);
      }
    }
  }
}

```

## disassembly

```asm
0x1400322e4  push    rbp
0x1400322e6  push    rbx
0x1400322e7  push    rsi
0x1400322e8  push    rdi
0x1400322e9  push    r14
0x1400322eb  push    r15
0x1400322ed  lea     rbp, [rsp-2Fh]
0x1400322f2  sub     rsp, 0F8h
0x1400322f9  mov     rax, cs:__security_cookie
0x140032300  xor     rax, rsp
0x140032303  mov     [rbp+57h+var_40], rax
0x140032307  xorps   xmm0, xmm0
0x14003230a  xorps   xmm1, xmm1
0x14003230d  xor     eax, eax
0x14003230f  mov     rdi, rcx
0x140032312  movups  xmmword ptr [rbp+57h+BackTrace], xmm0
0x140032316  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14003231a  movups  [rbp+57h+var_50], xmm0
0x14003231e  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm1
0x140032322  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140032329  nop     dword ptr [rax+rax+00h]
0x14003232e  lea     rcx, [rdi+0C0h]; SpinLock
0x140032335  mov     rsi, rax
0x140032338  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14003233c  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140032343  nop     dword ptr [rax+rax+00h]
0x140032348  cmp     dword ptr [rdi+0B8h], 0
0x14003234f  lea     rbx, [rdi+0C8h]
0x140032356  jnz     short loc_140032367
0x140032358  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14003235f  nop     dword ptr [rax+rax+00h]
0x140032364  mov     [rbx], rax
0x140032367  inc     dword ptr [rdi+0B8h]
0x14003236d  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140032371  mov     r15d, [rdi+0B8h]
0x140032378  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003237f  nop     dword ptr [rax+rax+00h]
0x140032384  lea     rcx, [rdi+0A0h]; Object
0x14003238b  mov     [rsp+120h+Timeout], 0; Timeout
0x140032394  xor     r9d, r9d; Alertable
0x140032397  xor     r8d, r8d; WaitMode
0x14003239a  xor     edx, edx; WaitReason
0x14003239c  call    cs:__imp_KeWaitForSingleObject
0x1400323a3  nop     dword ptr [rax+rax+00h]
0x1400323a8  mov     rcx, [rbx]
0x1400323ab  mov     rax, 346DC5D63886594Bh
0x1400323b5  sub     rcx, rsi
0x1400323b8  mul     rcx
0x1400323bb  mov     rbx, rdx
0x1400323be  shr     rbx, 0Bh
0x1400323c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400323c9  lea     rax, WPP_GLOBAL_Control
0x1400323d0  cmp     rcx, rax
0x1400323d3  jz      short loc_1400323FA
0x1400323d5  mov     eax, [rcx+2Ch]
0x1400323d8  test    al, 1
0x1400323da  jz      short loc_1400323FA
0x1400323dc  cmp     byte ptr [rcx+29h], 3
0x1400323e0  jb      short loc_1400323FA
0x1400323e2  mov     rcx, [rcx+18h]
0x1400323e6  lea     r8, WPP_e9af277499653a079df361eadb276992_Traceguids
0x1400323ed  mov     edx, 20h ; ' '
0x1400323f2  mov     r9, rbx
0x1400323f5  call    WPP_SF_i
0x1400323fa  cmp     rbx, 7530h
0x140032401  jbe     loc_140032569
0x140032407  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003240e  lea     r8, [rbp+57h+BackTrace]; BackTrace
0x140032412  xor     r9d, r9d; BackTraceHash
0x140032415  mov     rcx, [rax+8]
0x140032419  lea     edx, [r9+4]; FramesToCapture
0x14003241d  mov     rsi, [rcx+18h]
0x140032421  mov     r14d, [rcx+20h]
0x140032425  lea     ecx, [rdx-3]; FramesToSkip
0x140032428  add     r14, rsi
0x14003242b  call    cs:__imp_RtlCaptureStackBackTrace
0x140032432  nop     dword ptr [rax+rax+00h]
0x140032437  xor     ecx, ecx
0x140032439  mov     rax, [rbp+rcx*8+57h+BackTrace]
0x14003243e  cmp     rax, rsi
0x140032441  jb      short loc_14003244D
0x140032443  cmp     rax, r14
0x140032446  jnb     short loc_14003244D
0x140032448  sub     rax, rsi
0x14003244b  jmp     short loc_14003244F
0x14003244d  xor     eax, eax
0x14003244f  mov     [rbp+rcx*8+57h+BackTrace], rax
0x140032454  inc     rcx
0x140032457  cmp     rcx, 4
0x14003245b  jnz     short loc_140032439
0x14003245d  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x140032464  jz      short loc_14003249F
0x140032466  mov     eax, dword ptr [rbp+57h+var_50+8]
0x140032469  lea     rcx, [rdi+6Ch]
0x14003246d  mov     dword ptr [rsp+120h+var_D8], eax
0x140032471  lea     rdx, PoolTasksPause
0x140032478  mov     eax, dword ptr [rbp+57h+var_50]
0x14003247b  mov     r9, rbx
0x14003247e  mov     dword ptr [rsp+120h+var_E0], eax
0x140032482  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x140032485  mov     dword ptr [rsp+120h+var_E8], eax
0x140032489  mov     eax, dword ptr [rbp+57h+BackTrace]
0x14003248c  mov     dword ptr [rsp+120h+var_F0], eax
0x140032490  mov     dword ptr [rsp+120h+var_F8], r15d
0x140032495  mov     [rsp+120h+Timeout], rcx
0x14003249a  call    McTemplateK0xjddddd_EtwWriteTransfer
0x14003249f  mov     eax, cs:dword_14007F050
0x1400324a5  cmp     eax, 5
0x1400324a8  jbe     loc_140032569
0x1400324ae  mov     rdx, 400000000000h
0x1400324b8  lea     rcx, dword_14007F050
0x1400324bf  call    _tlgKeywordOn
0x1400324c4  test    al, al
0x1400324c6  jz      loc_140032569
0x1400324cc  mov     eax, dword ptr [rbp+57h+var_50+8]
0x1400324cf  mov     [rbp+57h+var_B0], eax
0x1400324d2  mov     eax, dword ptr [rbp+57h+var_50]
0x1400324d5  mov     [rbp+57h+var_AC], eax
0x1400324d8  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x1400324db  mov     [rbp+57h+var_A8], eax
0x1400324de  mov     eax, dword ptr [rbp+57h+BackTrace]
0x1400324e1  mov     [rbp+57h+var_A4], eax
0x1400324e4  lea     rax, [rdi+6Ch]
0x1400324e8  mov     [rbp+57h+var_98], rax
0x1400324ec  mov     [rbp+57h+var_A0], r15d
0x1400324f0  mov     [rbp+57h+var_90], rbx
0x1400324f4  call    cs:__imp_IoGetActivityIdThread
0x1400324fb  nop     dword ptr [rax+rax+00h]
0x140032500  lea     rdx, byte_140075841
0x140032507  mov     [rbp+57h+var_80], 1000000h
0x14003250f  mov     [rbp+57h+var_88], rax
0x140032513  lea     rax, [rbp+57h+var_B0]
0x140032517  mov     [rsp+120h+var_C0], rax
0x14003251c  lea     rax, [rbp+57h+var_AC]
0x140032520  mov     [rsp+120h+var_C8], rax
0x140032525  lea     rax, [rbp+57h+var_A8]
0x140032529  mov     [rsp+120h+var_D0], rax
0x14003252e  lea     rax, [rbp+57h+var_A4]
0x140032532  mov     [rsp+120h+var_D8], rax
0x140032537  lea     rax, [rbp+57h+var_A0]
0x14003253b  mov     [rsp+120h+var_E0], rax
0x140032540  lea     rax, [rbp+57h+var_98]
0x140032544  mov     [rsp+120h+var_E8], rax
0x140032549  lea     rax, [rbp+57h+var_90]
0x14003254d  mov     [rsp+120h+var_F0], rax
0x140032552  lea     rax, [rbp+57h+var_88]
0x140032556  mov     [rsp+120h+var_F8], rax
0x14003255b  lea     rax, [rbp+57h+var_80]
0x14003255f  mov     [rsp+120h+Timeout], rax
0x140032564  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U1@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@34AEBU?$_tlgWrapperByVal@$03@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140032569  mov     rcx, [rbp+57h+var_40]
0x14003256d  xor     rcx, rsp; StackCookie
0x140032570  call    __security_check_cookie
0x140032575  add     rsp, 0F8h
0x14003257c  pop     r15
0x14003257e  pop     r14
0x140032580  pop     rdi
0x140032581  pop     rsi
0x140032582  pop     rbx
0x140032583  pop     rbp
0x140032584  retn
```
