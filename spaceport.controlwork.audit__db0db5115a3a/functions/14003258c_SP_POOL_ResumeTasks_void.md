# SP_POOL::ResumeTasks(void)

- ea: `0x14003258c`
- end: `0x1400327e3`
- name: `?ResumeTasks@SP_POOL@@QEAAXXZ`
- size: `599`
- prototype: `void __fastcall(SP_POOL *__hidden this)`
- caller_count: `13`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14002f610`
- `0x14002f6cc`
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
- `0x140002ad8`
- `0x140028bb0`
- `0x14002c3ec`
- `0x14003258c`
- `0x140032964`
- `0x140067fc0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400325ff`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400325ff`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140032699`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140032699`
- `ntoskrnl!IoGetActivityIdThread` at `0x140032762`
- `ntoskrnl!IoGetActivityIdThread` at `0x140032762`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400325ca`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400325ca`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140032624`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140032624`

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
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_e9af277499653a079df361eadb276992_Traceguids, v2);
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
0x14003258c  push    rbp
0x14003258e  push    rbx
0x14003258f  push    rsi
0x140032590  push    rdi
0x140032591  push    r14
0x140032593  push    r15
0x140032595  lea     rbp, [rsp-2Fh]
0x14003259a  sub     rsp, 0D8h
0x1400325a1  mov     rax, cs:__security_cookie
0x1400325a8  xor     rax, rsp
0x1400325ab  mov     [rbp+57h+var_38], rax
0x1400325af  xorps   xmm0, xmm0
0x1400325b2  xorps   xmm1, xmm1
0x1400325b5  xor     eax, eax
0x1400325b7  mov     rsi, rcx
0x1400325ba  movups  xmmword ptr [rbp+57h+BackTrace], xmm0
0x1400325be  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x1400325c2  movups  [rbp+57h+var_48], xmm0
0x1400325c6  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm1
0x1400325ca  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400325d1  nop     dword ptr [rax+rax+00h]
0x1400325d6  mov     rcx, rax
0x1400325d9  mov     rax, 346DC5D63886594Bh
0x1400325e3  sub     rcx, [rsi+0C8h]
0x1400325ea  mul     rcx
0x1400325ed  lea     rcx, [rsi+0C0h]; SpinLock
0x1400325f4  mov     rbx, rdx
0x1400325f7  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x1400325fb  shr     rbx, 0Bh
0x1400325ff  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140032606  nop     dword ptr [rax+rax+00h]
0x14003260b  dec     dword ptr [rsi+0B8h]
0x140032611  mov     rcx, rsi; this
0x140032614  mov     r15d, [rsi+0B8h]
0x14003261b  call    ?LaunchTasks@SP_POOL@@QEAAXXZ; SP_POOL::LaunchTasks(void)
0x140032620  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140032624  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003262b  nop     dword ptr [rax+rax+00h]
0x140032630  mov     rcx, cs:WPP_GLOBAL_Control
0x140032637  lea     rax, WPP_GLOBAL_Control
0x14003263e  cmp     rcx, rax
0x140032641  jz      short loc_140032668
0x140032643  mov     eax, [rcx+2Ch]
0x140032646  test    al, 1
0x140032648  jz      short loc_140032668
0x14003264a  cmp     byte ptr [rcx+29h], 3
0x14003264e  jb      short loc_140032668
0x140032650  mov     rcx, [rcx+18h]
0x140032654  lea     r8, WPP_e9af277499653a079df361eadb276992_Traceguids
0x14003265b  mov     edx, 21h ; '!'
0x140032660  mov     r9, rbx
0x140032663  call    WPP_SF_i
0x140032668  cmp     rbx, 7530h
0x14003266f  jbe     loc_1400327C6
0x140032675  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003267c  lea     r8, [rbp+57h+BackTrace]; BackTrace
0x140032680  xor     r9d, r9d; BackTraceHash
0x140032683  mov     rcx, [rax+8]
0x140032687  lea     edx, [r9+4]; FramesToCapture
0x14003268b  mov     rdi, [rcx+18h]
0x14003268f  mov     r14d, [rcx+20h]
0x140032693  lea     ecx, [rdx-3]; FramesToSkip
0x140032696  add     r14, rdi
0x140032699  call    cs:__imp_RtlCaptureStackBackTrace
0x1400326a0  nop     dword ptr [rax+rax+00h]
0x1400326a5  xor     ecx, ecx
0x1400326a7  mov     rax, [rbp+rcx*8+57h+BackTrace]
0x1400326ac  cmp     rax, rdi
0x1400326af  jb      short loc_1400326BB
0x1400326b1  cmp     rax, r14
0x1400326b4  jnb     short loc_1400326BB
0x1400326b6  sub     rax, rdi
0x1400326b9  jmp     short loc_1400326BD
0x1400326bb  xor     eax, eax
0x1400326bd  mov     [rbp+rcx*8+57h+BackTrace], rax
0x1400326c2  inc     rcx
0x1400326c5  cmp     rcx, 4
0x1400326c9  jnz     short loc_1400326A7
0x1400326cb  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x1400326d2  jz      short loc_14003270D
0x1400326d4  mov     eax, dword ptr [rbp+57h+var_48+8]
0x1400326d7  lea     rcx, [rsi+6Ch]
0x1400326db  mov     dword ptr [rsp+100h+var_B8], eax
0x1400326df  lea     rdx, PoolTasksResume
0x1400326e6  mov     eax, dword ptr [rbp+57h+var_48]
0x1400326e9  mov     r9, rbx
0x1400326ec  mov     dword ptr [rsp+100h+var_C0], eax
0x1400326f0  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x1400326f3  mov     dword ptr [rsp+100h+var_C8], eax
0x1400326f7  mov     eax, dword ptr [rbp+57h+BackTrace]
0x1400326fa  mov     dword ptr [rsp+100h+var_D0], eax
0x1400326fe  mov     dword ptr [rsp+100h+var_D8], r15d
0x140032703  mov     [rsp+100h+var_E0], rcx
0x140032708  call    McTemplateK0xjddddd_EtwWriteTransfer
0x14003270d  mov     eax, cs:dword_14007F050
0x140032713  cmp     eax, 5
0x140032716  jbe     loc_1400327C6
0x14003271c  mov     rdx, 400000000000h
0x140032726  lea     rcx, dword_14007F050
0x14003272d  call    _tlgKeywordOn
0x140032732  test    al, al
0x140032734  jz      loc_1400327C6
0x14003273a  mov     eax, dword ptr [rbp+57h+var_48+8]
0x14003273d  mov     [rbp+57h+var_A0], eax
0x140032740  mov     eax, dword ptr [rbp+57h+var_48]
0x140032743  mov     [rbp+57h+var_9C], eax
0x140032746  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x140032749  mov     [rbp+57h+var_98], eax
0x14003274c  mov     eax, dword ptr [rbp+57h+BackTrace]
0x14003274f  mov     [rbp+57h+var_94], eax
0x140032752  lea     rax, [rsi+6Ch]
0x140032756  mov     [rbp+57h+var_88], rax
0x14003275a  mov     [rbp+57h+var_90], r15d
0x14003275e  mov     [rbp+57h+var_80], rbx
0x140032762  call    cs:__imp_IoGetActivityIdThread
0x140032769  nop     dword ptr [rax+rax+00h]
0x14003276e  mov     [rbp+57h+var_78], rax
0x140032772  lea     rdx, dword_14007565C
0x140032779  lea     rax, [rbp+57h+var_A0]
0x14003277d  mov     [rsp+100h+var_A8], rax
0x140032782  lea     rax, [rbp+57h+var_9C]
0x140032786  mov     [rsp+100h+var_B0], rax
0x14003278b  lea     rax, [rbp+57h+var_98]
0x14003278f  mov     [rsp+100h+var_B8], rax
0x140032794  lea     rax, [rbp+57h+var_94]
0x140032798  mov     [rsp+100h+var_C0], rax
0x14003279d  lea     rax, [rbp+57h+var_90]
0x1400327a1  mov     [rsp+100h+var_C8], rax
0x1400327a6  lea     rax, [rbp+57h+var_88]
0x1400327aa  mov     [rsp+100h+var_D0], rax
0x1400327af  lea     rax, [rbp+57h+var_80]
0x1400327b3  mov     [rsp+100h+var_D8], rax
0x1400327b8  lea     rax, [rbp+57h+var_78]
0x1400327bc  mov     [rsp+100h+var_E0], rax
0x1400327c1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400327c6  mov     rcx, [rbp+57h+var_38]
0x1400327ca  xor     rcx, rsp; StackCookie
0x1400327cd  call    __security_check_cookie
0x1400327d2  add     rsp, 0D8h
0x1400327d9  pop     r15
0x1400327db  pop     r14
0x1400327dd  pop     rdi
0x1400327de  pop     rsi
0x1400327df  pop     rbx
0x1400327e0  pop     rbp
0x1400327e1  retn
```
