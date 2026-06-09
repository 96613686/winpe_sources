# SP_POOL::PauseTasks(void)

- ea: `0x140032354`
- end: `0x1400325f6`
- name: `?PauseTasks@SP_POOL@@QEAAXXZ`
- size: `674`
- prototype: `void __fastcall(SP_POOL *__hidden this)`
- caller_count: `14`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14002f680`
- `0x14002f73c`
- `0x1400338f0`
- `0x14003b6d0`
- `0x14003bd10`
- `0x14009cc00`
- `0x14009cd50`
- `0x14009d930`
- `0x14009df5c`
- `0x14009e404`
- `0x14009e9e4`
- `0x14009ee34`
- `0x1400a0f3c`
- `0x1400a415c`

## callees

- `0x14000200c`
- `0x140002c94`
- `0x14002c3ec`
- `0x140032354`
- `0x140032a18`
- `0x140068110`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14003240c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003240c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400323ac`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400323ac`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003249b`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003249b`
- `ntoskrnl!IoGetActivityIdThread` at `0x140032564`
- `ntoskrnl!IoGetActivityIdThread` at `0x140032564`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140032392`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400323c8`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140032392`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400323c8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400323e8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400323e8`

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
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_1644b770679031712b2a7d57a047b861_Traceguids, v5);
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
          (unsigned int)&byte_14007578F,
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
0x140032354  push    rbp
0x140032356  push    rbx
0x140032357  push    rsi
0x140032358  push    rdi
0x140032359  push    r14
0x14003235b  push    r15
0x14003235d  lea     rbp, [rsp-2Fh]
0x140032362  sub     rsp, 0F8h
0x140032369  mov     rax, cs:__security_cookie
0x140032370  xor     rax, rsp
0x140032373  mov     [rbp+57h+var_40], rax
0x140032377  xorps   xmm0, xmm0
0x14003237a  xorps   xmm1, xmm1
0x14003237d  xor     eax, eax
0x14003237f  mov     rdi, rcx
0x140032382  movups  xmmword ptr [rbp+57h+BackTrace], xmm0
0x140032386  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14003238a  movups  [rbp+57h+var_50], xmm0
0x14003238e  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm1
0x140032392  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140032399  nop     dword ptr [rax+rax+00h]
0x14003239e  lea     rcx, [rdi+0C0h]; SpinLock
0x1400323a5  mov     rsi, rax
0x1400323a8  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x1400323ac  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400323b3  nop     dword ptr [rax+rax+00h]
0x1400323b8  cmp     dword ptr [rdi+0B8h], 0
0x1400323bf  lea     rbx, [rdi+0C8h]
0x1400323c6  jnz     short loc_1400323D7
0x1400323c8  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400323cf  nop     dword ptr [rax+rax+00h]
0x1400323d4  mov     [rbx], rax
0x1400323d7  inc     dword ptr [rdi+0B8h]
0x1400323dd  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1400323e1  mov     r15d, [rdi+0B8h]
0x1400323e8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400323ef  nop     dword ptr [rax+rax+00h]
0x1400323f4  lea     rcx, [rdi+0A0h]; Object
0x1400323fb  mov     [rsp+120h+Timeout], 0; Timeout
0x140032404  xor     r9d, r9d; Alertable
0x140032407  xor     r8d, r8d; WaitMode
0x14003240a  xor     edx, edx; WaitReason
0x14003240c  call    cs:__imp_KeWaitForSingleObject
0x140032413  nop     dword ptr [rax+rax+00h]
0x140032418  mov     rcx, [rbx]
0x14003241b  mov     rax, 346DC5D63886594Bh
0x140032425  sub     rcx, rsi
0x140032428  mul     rcx
0x14003242b  mov     rbx, rdx
0x14003242e  shr     rbx, 0Bh
0x140032432  mov     rcx, cs:WPP_GLOBAL_Control
0x140032439  lea     rax, WPP_GLOBAL_Control
0x140032440  cmp     rcx, rax
0x140032443  jz      short loc_14003246A
0x140032445  mov     eax, [rcx+2Ch]
0x140032448  test    al, 1
0x14003244a  jz      short loc_14003246A
0x14003244c  cmp     byte ptr [rcx+29h], 3
0x140032450  jb      short loc_14003246A
0x140032452  mov     rcx, [rcx+18h]
0x140032456  lea     r8, WPP_1644b770679031712b2a7d57a047b861_Traceguids
0x14003245d  mov     edx, 20h ; ' '
0x140032462  mov     r9, rbx
0x140032465  call    WPP_SF_i
0x14003246a  cmp     rbx, 7530h
0x140032471  jbe     loc_1400325D9
0x140032477  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003247e  lea     r8, [rbp+57h+BackTrace]; BackTrace
0x140032482  xor     r9d, r9d; BackTraceHash
0x140032485  mov     rcx, [rax+8]
0x140032489  lea     edx, [r9+4]; FramesToCapture
0x14003248d  mov     rsi, [rcx+18h]
0x140032491  mov     r14d, [rcx+20h]
0x140032495  lea     ecx, [rdx-3]; FramesToSkip
0x140032498  add     r14, rsi
0x14003249b  call    cs:__imp_RtlCaptureStackBackTrace
0x1400324a2  nop     dword ptr [rax+rax+00h]
0x1400324a7  xor     ecx, ecx
0x1400324a9  mov     rax, [rbp+rcx*8+57h+BackTrace]
0x1400324ae  cmp     rax, rsi
0x1400324b1  jb      short loc_1400324BD
0x1400324b3  cmp     rax, r14
0x1400324b6  jnb     short loc_1400324BD
0x1400324b8  sub     rax, rsi
0x1400324bb  jmp     short loc_1400324BF
0x1400324bd  xor     eax, eax
0x1400324bf  mov     [rbp+rcx*8+57h+BackTrace], rax
0x1400324c4  inc     rcx
0x1400324c7  cmp     rcx, 4
0x1400324cb  jnz     short loc_1400324A9
0x1400324cd  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x1400324d4  jz      short loc_14003250F
0x1400324d6  mov     eax, dword ptr [rbp+57h+var_50+8]
0x1400324d9  lea     rcx, [rdi+6Ch]
0x1400324dd  mov     dword ptr [rsp+120h+var_D8], eax
0x1400324e1  lea     rdx, PoolTasksPause
0x1400324e8  mov     eax, dword ptr [rbp+57h+var_50]
0x1400324eb  mov     r9, rbx
0x1400324ee  mov     dword ptr [rsp+120h+var_E0], eax
0x1400324f2  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x1400324f5  mov     dword ptr [rsp+120h+var_E8], eax
0x1400324f9  mov     eax, dword ptr [rbp+57h+BackTrace]
0x1400324fc  mov     dword ptr [rsp+120h+var_F0], eax
0x140032500  mov     dword ptr [rsp+120h+var_F8], r15d
0x140032505  mov     [rsp+120h+Timeout], rcx
0x14003250a  call    McTemplateK0xjddddd_EtwWriteTransfer
0x14003250f  mov     eax, cs:dword_14007F050
0x140032515  cmp     eax, 5
0x140032518  jbe     loc_1400325D9
0x14003251e  mov     rdx, 400000000000h
0x140032528  lea     rcx, dword_14007F050
0x14003252f  call    _tlgKeywordOn
0x140032534  test    al, al
0x140032536  jz      loc_1400325D9
0x14003253c  mov     eax, dword ptr [rbp+57h+var_50+8]
0x14003253f  mov     [rbp+57h+var_B0], eax
0x140032542  mov     eax, dword ptr [rbp+57h+var_50]
0x140032545  mov     [rbp+57h+var_AC], eax
0x140032548  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x14003254b  mov     [rbp+57h+var_A8], eax
0x14003254e  mov     eax, dword ptr [rbp+57h+BackTrace]
0x140032551  mov     [rbp+57h+var_A4], eax
0x140032554  lea     rax, [rdi+6Ch]
0x140032558  mov     [rbp+57h+var_98], rax
0x14003255c  mov     [rbp+57h+var_A0], r15d
0x140032560  mov     [rbp+57h+var_90], rbx
0x140032564  call    cs:__imp_IoGetActivityIdThread
0x14003256b  nop     dword ptr [rax+rax+00h]
0x140032570  lea     rdx, byte_14007578F
0x140032577  mov     [rbp+57h+var_80], 1000000h
0x14003257f  mov     [rbp+57h+var_88], rax
0x140032583  lea     rax, [rbp+57h+var_B0]
0x140032587  mov     [rsp+120h+var_C0], rax
0x14003258c  lea     rax, [rbp+57h+var_AC]
0x140032590  mov     [rsp+120h+var_C8], rax
0x140032595  lea     rax, [rbp+57h+var_A8]
0x140032599  mov     [rsp+120h+var_D0], rax
0x14003259e  lea     rax, [rbp+57h+var_A4]
0x1400325a2  mov     [rsp+120h+var_D8], rax
0x1400325a7  lea     rax, [rbp+57h+var_A0]
0x1400325ab  mov     [rsp+120h+var_E0], rax
0x1400325b0  lea     rax, [rbp+57h+var_98]
0x1400325b4  mov     [rsp+120h+var_E8], rax
0x1400325b9  lea     rax, [rbp+57h+var_90]
0x1400325bd  mov     [rsp+120h+var_F0], rax
0x1400325c2  lea     rax, [rbp+57h+var_88]
0x1400325c6  mov     [rsp+120h+var_F8], rax
0x1400325cb  lea     rax, [rbp+57h+var_80]
0x1400325cf  mov     [rsp+120h+Timeout], rax
0x1400325d4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U1@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@34AEBU?$_tlgWrapperByVal@$03@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400325d9  mov     rcx, [rbp+57h+var_40]
0x1400325dd  xor     rcx, rsp; StackCookie
0x1400325e0  call    __security_check_cookie
0x1400325e5  add     rsp, 0F8h
0x1400325ec  pop     r15
0x1400325ee  pop     r14
0x1400325f0  pop     rdi
0x1400325f1  pop     rsi
0x1400325f2  pop     rbx
0x1400325f3  pop     rbp
0x1400325f4  retn
```
