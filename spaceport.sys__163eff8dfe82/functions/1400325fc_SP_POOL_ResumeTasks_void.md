# SP_POOL::ResumeTasks(void)

- ea: `0x1400325fc`
- end: `0x140032853`
- name: `?ResumeTasks@SP_POOL@@QEAAXXZ`
- size: `599`
- prototype: `void __fastcall(SP_POOL *__hidden this)`
- caller_count: `13`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14002f680`
- `0x14002f73c`
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
- `0x140002ad8`
- `0x140028bb0`
- `0x14002c3ec`
- `0x1400325fc`
- `0x140032a18`
- `0x140068110`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003266f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003266f`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140032709`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140032709`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400327d2`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400327d2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14003263a`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14003263a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140032694`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140032694`

## pseudocode

```c
void __fastcall SP_POOL::ResumeTasks(SP_POOL *this)
{
  ULONGLONG v2; // rbx
  int v3; // r15d
  __int64 v4; // rcx
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r14
  int v7; // r8d
  __int64 i; // rcx
  char *v9; // rax
  char *v10; // rax
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // [rsp+60h] [rbp-49h] BYREF
  int v16; // [rsp+64h] [rbp-45h] BYREF
  int v17; // [rsp+68h] [rbp-41h] BYREF
  int v18; // [rsp+6Ch] [rbp-3Dh] BYREF
  int v19; // [rsp+70h] [rbp-39h] BYREF
  char *v20; // [rsp+78h] [rbp-31h] BYREF
  ULONGLONG v21; // [rsp+80h] [rbp-29h] BYREF
  __int64 ActivityIdThread; // [rsp+88h] [rbp-21h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+90h] [rbp-19h] BYREF
  PVOID BackTrace[2]; // [rsp+A8h] [rbp-1h] BYREF
  __int128 v25; // [rsp+B8h] [rbp+Fh]

  *(_OWORD *)BackTrace = 0;
  v25 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v2 = (KeQueryUnbiasedInterruptTime() - *((_QWORD *)this + 25)) / 0x2710;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this + 24, &LockHandle);
  v3 = --*((_DWORD *)this + 46);
  SP_POOL::LaunchTasks(this);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_1644b770679031712b2a7d57a047b861_Traceguids, v2);
  }
  if ( v2 > 0x7530 )
  {
    v4 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
    v5 = *(_QWORD *)(v4 + 24);
    v6 = v5 + *(unsigned int *)(v4 + 32);
    RtlCaptureStackBackTrace(1u, 4u, BackTrace, 0);
    for ( i = 0; i != 4; ++i )
    {
      v9 = (char *)BackTrace[i];
      if ( (unsigned __int64)v9 < v5 || (unsigned __int64)v9 >= v6 )
        v10 = 0;
      else
        v10 = &v9[-v5];
      BackTrace[i] = v10;
    }
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
      McTemplateK0xjddddd_EtwWriteTransfer(
        (_DWORD)this + 108,
        (unsigned int)PoolTasksResume,
        v7,
        v2,
        (__int64)this + 108,
        v3,
        (char)BackTrace[0],
        (char)BackTrace[1],
        v25,
        SBYTE8(v25));
    if ( (unsigned int)dword_14007F050 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
      {
        v15 = DWORD2(v25);
        v16 = v25;
        v17 = (int)BackTrace[1];
        v18 = (int)BackTrace[0];
        v20 = (char *)this + 108;
        v19 = v3;
        v21 = v2;
        ActivityIdThread = IoGetActivityIdThread(v11);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)&dword_14007565C,
          v13,
          v14,
          (__int64)&ActivityIdThread,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&v16,
          (__int64)&v15);
      }
    }
  }
}

```

## disassembly

```asm
0x1400325fc  push    rbp
0x1400325fe  push    rbx
0x1400325ff  push    rsi
0x140032600  push    rdi
0x140032601  push    r14
0x140032603  push    r15
0x140032605  lea     rbp, [rsp-2Fh]
0x14003260a  sub     rsp, 0D8h
0x140032611  mov     rax, cs:__security_cookie
0x140032618  xor     rax, rsp
0x14003261b  mov     [rbp+57h+var_38], rax
0x14003261f  xorps   xmm0, xmm0
0x140032622  xorps   xmm1, xmm1
0x140032625  xor     eax, eax
0x140032627  mov     rsi, rcx
0x14003262a  movups  xmmword ptr [rbp+57h+BackTrace], xmm0
0x14003262e  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140032632  movups  [rbp+57h+var_48], xmm0
0x140032636  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm1
0x14003263a  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140032641  nop     dword ptr [rax+rax+00h]
0x140032646  mov     rcx, rax
0x140032649  mov     rax, 346DC5D63886594Bh
0x140032653  sub     rcx, [rsi+0C8h]
0x14003265a  mul     rcx
0x14003265d  lea     rcx, [rsi+0C0h]; SpinLock
0x140032664  mov     rbx, rdx
0x140032667  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14003266b  shr     rbx, 0Bh
0x14003266f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140032676  nop     dword ptr [rax+rax+00h]
0x14003267b  dec     dword ptr [rsi+0B8h]
0x140032681  mov     rcx, rsi; this
0x140032684  mov     r15d, [rsi+0B8h]
0x14003268b  call    ?LaunchTasks@SP_POOL@@QEAAXXZ; SP_POOL::LaunchTasks(void)
0x140032690  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140032694  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003269b  nop     dword ptr [rax+rax+00h]
0x1400326a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400326a7  lea     rax, WPP_GLOBAL_Control
0x1400326ae  cmp     rcx, rax
0x1400326b1  jz      short loc_1400326D8
0x1400326b3  mov     eax, [rcx+2Ch]
0x1400326b6  test    al, 1
0x1400326b8  jz      short loc_1400326D8
0x1400326ba  cmp     byte ptr [rcx+29h], 3
0x1400326be  jb      short loc_1400326D8
0x1400326c0  mov     rcx, [rcx+18h]
0x1400326c4  lea     r8, WPP_1644b770679031712b2a7d57a047b861_Traceguids
0x1400326cb  mov     edx, 21h ; '!'
0x1400326d0  mov     r9, rbx
0x1400326d3  call    WPP_SF_i
0x1400326d8  cmp     rbx, 7530h
0x1400326df  jbe     loc_140032836
0x1400326e5  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400326ec  lea     r8, [rbp+57h+BackTrace]; BackTrace
0x1400326f0  xor     r9d, r9d; BackTraceHash
0x1400326f3  mov     rcx, [rax+8]
0x1400326f7  lea     edx, [r9+4]; FramesToCapture
0x1400326fb  mov     rdi, [rcx+18h]
0x1400326ff  mov     r14d, [rcx+20h]
0x140032703  lea     ecx, [rdx-3]; FramesToSkip
0x140032706  add     r14, rdi
0x140032709  call    cs:__imp_RtlCaptureStackBackTrace
0x140032710  nop     dword ptr [rax+rax+00h]
0x140032715  xor     ecx, ecx
0x140032717  mov     rax, [rbp+rcx*8+57h+BackTrace]
0x14003271c  cmp     rax, rdi
0x14003271f  jb      short loc_14003272B
0x140032721  cmp     rax, r14
0x140032724  jnb     short loc_14003272B
0x140032726  sub     rax, rdi
0x140032729  jmp     short loc_14003272D
0x14003272b  xor     eax, eax
0x14003272d  mov     [rbp+rcx*8+57h+BackTrace], rax
0x140032732  inc     rcx
0x140032735  cmp     rcx, 4
0x140032739  jnz     short loc_140032717
0x14003273b  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x140032742  jz      short loc_14003277D
0x140032744  mov     eax, dword ptr [rbp+57h+var_48+8]
0x140032747  lea     rcx, [rsi+6Ch]
0x14003274b  mov     dword ptr [rsp+100h+var_B8], eax
0x14003274f  lea     rdx, PoolTasksResume
0x140032756  mov     eax, dword ptr [rbp+57h+var_48]
0x140032759  mov     r9, rbx
0x14003275c  mov     dword ptr [rsp+100h+var_C0], eax
0x140032760  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x140032763  mov     dword ptr [rsp+100h+var_C8], eax
0x140032767  mov     eax, dword ptr [rbp+57h+BackTrace]
0x14003276a  mov     dword ptr [rsp+100h+var_D0], eax
0x14003276e  mov     dword ptr [rsp+100h+var_D8], r15d
0x140032773  mov     [rsp+100h+var_E0], rcx
0x140032778  call    McTemplateK0xjddddd_EtwWriteTransfer
0x14003277d  mov     eax, cs:dword_14007F050
0x140032783  cmp     eax, 5
0x140032786  jbe     loc_140032836
0x14003278c  mov     rdx, 400000000000h
0x140032796  lea     rcx, dword_14007F050
0x14003279d  call    _tlgKeywordOn
0x1400327a2  test    al, al
0x1400327a4  jz      loc_140032836
0x1400327aa  mov     eax, dword ptr [rbp+57h+var_48+8]
0x1400327ad  mov     [rbp+57h+var_A0], eax
0x1400327b0  mov     eax, dword ptr [rbp+57h+var_48]
0x1400327b3  mov     [rbp+57h+var_9C], eax
0x1400327b6  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x1400327b9  mov     [rbp+57h+var_98], eax
0x1400327bc  mov     eax, dword ptr [rbp+57h+BackTrace]
0x1400327bf  mov     [rbp+57h+var_94], eax
0x1400327c2  lea     rax, [rsi+6Ch]
0x1400327c6  mov     [rbp+57h+var_88], rax
0x1400327ca  mov     [rbp+57h+var_90], r15d
0x1400327ce  mov     [rbp+57h+var_80], rbx
0x1400327d2  call    cs:__imp_IoGetActivityIdThread
0x1400327d9  nop     dword ptr [rax+rax+00h]
0x1400327de  mov     [rbp+57h+var_78], rax
0x1400327e2  lea     rdx, dword_14007565C
0x1400327e9  lea     rax, [rbp+57h+var_A0]
0x1400327ed  mov     [rsp+100h+var_A8], rax
0x1400327f2  lea     rax, [rbp+57h+var_9C]
0x1400327f6  mov     [rsp+100h+var_B0], rax
0x1400327fb  lea     rax, [rbp+57h+var_98]
0x1400327ff  mov     [rsp+100h+var_B8], rax
0x140032804  lea     rax, [rbp+57h+var_94]
0x140032808  mov     [rsp+100h+var_C0], rax
0x14003280d  lea     rax, [rbp+57h+var_90]
0x140032811  mov     [rsp+100h+var_C8], rax
0x140032816  lea     rax, [rbp+57h+var_88]
0x14003281a  mov     [rsp+100h+var_D0], rax
0x14003281f  lea     rax, [rbp+57h+var_80]
0x140032823  mov     [rsp+100h+var_D8], rax
0x140032828  lea     rax, [rbp+57h+var_78]
0x14003282c  mov     [rsp+100h+var_E0], rax
0x140032831  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140032836  mov     rcx, [rbp+57h+var_38]
0x14003283a  xor     rcx, rsp; StackCookie
0x14003283d  call    __security_check_cookie
0x140032842  add     rsp, 0D8h
0x140032849  pop     r15
0x14003284b  pop     r14
0x14003284d  pop     rdi
0x14003284e  pop     rsi
0x14003284f  pop     rbx
0x140032850  pop     rbp
0x140032851  retn
```
