# SP_DEVICE::ReleaseRundownExclusive(void)

- ea: `0x14002bc90`
- end: `0x14002bf38`
- name: `?ReleaseRundownExclusive@SP_DEVICE@@QEAAXXZ`
- size: `680`
- prototype: `void __fastcall(SP_DEVICE *__hidden this)`
- caller_count: `8`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002f680`
- `0x1400320a8`
- `0x1400338f0`
- `0x14009cc00`
- `0x14009cd50`
- `0x14009e9e4`
- `0x14009ee34`
- `0x1400b85d0`

## callees

- `0x14000200c`
- `0x140002178`
- `0x140021a90`
- `0x14002952c`
- `0x14002bc90`
- `0x14002c32c`
- `0x14002c3ec`
- `0x140068110`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14002bd04`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x14002bd04`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002bd1b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002bd1b`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14002bdde`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14002bdde`
- `ntoskrnl!KeSetEvent` at `0x14002bd61`
- `ntoskrnl!KeSetEvent` at `0x14002bd61`
- `ntoskrnl!IoGetActivityIdThread` at `0x14002beaf`
- `ntoskrnl!IoGetActivityIdThread` at `0x14002beaf`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002bcd3`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002bcd3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002bd49`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002bd49`

## pseudocode

```c
void __fastcall SP_DEVICE::ReleaseRundownExclusive(SP_DEVICE *this)
{
  ULONGLONG v2; // rdi
  struct _LIST_ENTRY *v3; // rdx
  __int64 v4; // rcx
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // r14
  int v7; // r8d
  __int64 i; // rcx
  char *v9; // rax
  char *v10; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // [rsp+60h] [rbp-29h] BYREF
  int v15; // [rsp+64h] [rbp-25h] BYREF
  int v16; // [rsp+68h] [rbp-21h] BYREF
  int v17; // [rsp+6Ch] [rbp-1Dh] BYREF
  char *v18; // [rsp+70h] [rbp-19h] BYREF
  char *v19; // [rsp+78h] [rbp-11h] BYREF
  ULONGLONG v20; // [rsp+80h] [rbp-9h] BYREF
  __int64 ActivityIdThread; // [rsp+88h] [rbp-1h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+90h] [rbp+7h] BYREF
  PVOID BackTrace[2]; // [rsp+A8h] [rbp+1Fh] BYREF
  __int128 v24; // [rsp+B8h] [rbp+2Fh]

  *(_OWORD *)BackTrace = 0;
  v24 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v2 = (KeQueryUnbiasedInterruptTime() - *((_QWORD *)this + 31)) / 0x2710;
  ExReInitializeRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)this + 30));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this + 37, &LockHandle);
  v3 = (struct _LIST_ENTRY *)((char *)this + 280);
  if ( v3->Flink != v3 )
    SP_WORKITEM::InsertList((char *)this + 304, v3, 0, 0);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  KeSetEvent((PRKEVENT)((char *)this + 256), 0, 0);
  SP_DEVICE::ReleaseMutex(this);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_7f2ea8968a1c30cfdadfaeadae5d584a_Traceguids, v2);
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
      McTemplateK0xjjdddd_EtwWriteTransfer(
        (_DWORD)this + 40,
        (unsigned int)RundownHold,
        v7,
        v2,
        (__int64)this + 24,
        (__int64)this + 40,
        (char)BackTrace[0],
        (char)BackTrace[1],
        v24,
        SBYTE8(v24));
    if ( (unsigned int)dword_14007F050 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_14007F050, 0x400000000000LL) )
      {
        v14 = DWORD2(v24);
        v15 = v24;
        v16 = (int)BackTrace[1];
        v17 = (int)BackTrace[0];
        v18 = (char *)this + 40;
        v19 = (char *)this + 24;
        v20 = v2;
        ActivityIdThread = IoGetActivityIdThread((char *)this + 24);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v11,
          (unsigned int)byte_140074A8B,
          v12,
          v13,
          (__int64)&ActivityIdThread,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)&v18,
          (__int64)&v17,
          (__int64)&v16,
          (__int64)&v15,
          (__int64)&v14);
      }
    }
  }
}

```

## disassembly

```asm
0x14002bc90  mov     [rsp-8+arg_8], rbx
0x14002bc95  mov     [rsp-8+arg_10], rsi
0x14002bc9a  push    rbp
0x14002bc9b  push    rdi
0x14002bc9c  push    r14
0x14002bc9e  lea     rbp, [rsp-47h]
0x14002bca3  sub     rsp, 0D0h
0x14002bcaa  mov     rax, cs:__security_cookie
0x14002bcb1  xor     rax, rsp
0x14002bcb4  mov     [rbp+57h+var_18], rax
0x14002bcb8  xorps   xmm0, xmm0
0x14002bcbb  xorps   xmm1, xmm1
0x14002bcbe  xor     eax, eax
0x14002bcc0  mov     rbx, rcx
0x14002bcc3  movups  xmmword ptr [rbp+57h+BackTrace], xmm0
0x14002bcc7  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14002bccb  movups  [rbp+57h+var_28], xmm0
0x14002bccf  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm1
0x14002bcd3  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14002bcda  nop     dword ptr [rax+rax+00h]
0x14002bcdf  mov     rcx, rax
0x14002bce2  mov     rax, 346DC5D63886594Bh
0x14002bcec  sub     rcx, [rbx+0F8h]
0x14002bcf3  mul     rcx
0x14002bcf6  mov     rcx, [rbx+0F0h]; RunRefCacheAware
0x14002bcfd  mov     rdi, rdx
0x14002bd00  shr     rdi, 0Bh
0x14002bd04  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14002bd0b  nop     dword ptr [rax+rax+00h]
0x14002bd10  lea     rcx, [rbx+128h]; SpinLock
0x14002bd17  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14002bd1b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002bd22  nop     dword ptr [rax+rax+00h]
0x14002bd27  lea     rdx, [rbx+118h]; struct _LIST_ENTRY *
0x14002bd2e  cmp     [rdx], rdx
0x14002bd31  jz      short loc_14002BD45
0x14002bd33  lea     rcx, [rbx+130h]; Context
0x14002bd3a  xor     r9d, r9d; unsigned int
0x14002bd3d  xor     r8d, r8d; unsigned __int8
0x14002bd40  call    ?InsertList@SP_WORKITEM@@QEAAXPEAU_LIST_ENTRY@@EK@Z; SP_WORKITEM::InsertList(_LIST_ENTRY *,uchar,ulong)
0x14002bd45  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14002bd49  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002bd50  nop     dword ptr [rax+rax+00h]
0x14002bd55  lea     rcx, [rbx+100h]; Event
0x14002bd5c  xor     r8d, r8d; Wait
0x14002bd5f  xor     edx, edx; Increment
0x14002bd61  call    cs:__imp_KeSetEvent
0x14002bd68  nop     dword ptr [rax+rax+00h]
0x14002bd6d  mov     rcx, rbx; this
0x14002bd70  call    ?ReleaseMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::ReleaseMutex(void)
0x14002bd75  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bd7c  lea     rax, WPP_GLOBAL_Control
0x14002bd83  cmp     rcx, rax
0x14002bd86  jz      short loc_14002BDAD
0x14002bd88  mov     eax, [rcx+2Ch]
0x14002bd8b  test    al, 1
0x14002bd8d  jz      short loc_14002BDAD
0x14002bd8f  cmp     byte ptr [rcx+29h], 3
0x14002bd93  jb      short loc_14002BDAD
0x14002bd95  mov     rcx, [rcx+18h]
0x14002bd99  lea     r8, WPP_7f2ea8968a1c30cfdadfaeadae5d584a_Traceguids
0x14002bda0  mov     edx, 0Dh
0x14002bda5  mov     r9, rdi
0x14002bda8  call    WPP_SF_i
0x14002bdad  cmp     rdi, 7530h
0x14002bdb4  jbe     loc_14002BF13
0x14002bdba  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14002bdc1  lea     r8, [rbp+57h+BackTrace]; BackTrace
0x14002bdc5  xor     r9d, r9d; BackTraceHash
0x14002bdc8  mov     rcx, [rax+8]
0x14002bdcc  lea     edx, [r9+4]; FramesToCapture
0x14002bdd0  mov     rsi, [rcx+18h]
0x14002bdd4  mov     r14d, [rcx+20h]
0x14002bdd8  lea     ecx, [rdx-3]; FramesToSkip
0x14002bddb  add     r14, rsi
0x14002bdde  call    cs:__imp_RtlCaptureStackBackTrace
0x14002bde5  nop     dword ptr [rax+rax+00h]
0x14002bdea  xor     ecx, ecx
0x14002bdec  mov     rax, [rbp+rcx*8+57h+BackTrace]
0x14002bdf1  cmp     rax, rsi
0x14002bdf4  jb      short loc_14002BE00
0x14002bdf6  cmp     rax, r14
0x14002bdf9  jnb     short loc_14002BE00
0x14002bdfb  sub     rax, rsi
0x14002bdfe  jmp     short loc_14002BE02
0x14002be00  xor     eax, eax
0x14002be02  mov     [rbp+rcx*8+57h+BackTrace], rax
0x14002be07  inc     rcx
0x14002be0a  cmp     rcx, 4
0x14002be0e  jnz     short loc_14002BDEC
0x14002be10  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14002be17  jz      short loc_14002BE56
0x14002be19  mov     eax, dword ptr [rbp+57h+var_28+8]
0x14002be1c  lea     rdx, [rbx+18h]
0x14002be20  mov     dword ptr [rsp+0E0h+var_98], eax
0x14002be24  lea     rcx, [rdx+10h]
0x14002be28  mov     eax, dword ptr [rbp+57h+var_28]
0x14002be2b  mov     r9, rdi
0x14002be2e  mov     dword ptr [rsp+0E0h+var_A0], eax
0x14002be32  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x14002be35  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14002be39  mov     eax, dword ptr [rbp+57h+BackTrace]
0x14002be3c  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14002be40  mov     [rsp+0E0h+var_B8], rcx
0x14002be45  mov     [rsp+0E0h+var_C0], rdx
0x14002be4a  lea     rdx, RundownHold
0x14002be51  call    McTemplateK0xjjdddd_EtwWriteTransfer
0x14002be56  mov     eax, cs:dword_14007F050
0x14002be5c  cmp     eax, 5
0x14002be5f  jbe     loc_14002BF13
0x14002be65  mov     rdx, 400000000000h
0x14002be6f  lea     rcx, dword_14007F050
0x14002be76  call    _tlgKeywordOn
0x14002be7b  test    al, al
0x14002be7d  jz      loc_14002BF13
0x14002be83  mov     eax, dword ptr [rbp+57h+var_28+8]
0x14002be86  lea     rcx, [rbx+18h]
0x14002be8a  mov     [rbp+57h+var_80], eax
0x14002be8d  mov     eax, dword ptr [rbp+57h+var_28]
0x14002be90  mov     [rbp+57h+var_7C], eax
0x14002be93  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x14002be96  mov     [rbp+57h+var_78], eax
0x14002be99  mov     eax, dword ptr [rbp+57h+BackTrace]
0x14002be9c  mov     [rbp+57h+var_74], eax
0x14002be9f  lea     rax, [rcx+10h]
0x14002bea3  mov     [rbp+57h+var_70], rax
0x14002bea7  mov     [rbp+57h+var_68], rcx
0x14002beab  mov     [rbp+57h+var_60], rdi
0x14002beaf  call    cs:__imp_IoGetActivityIdThread
0x14002beb6  nop     dword ptr [rax+rax+00h]
0x14002bebb  mov     [rbp+57h+var_58], rax
0x14002bebf  lea     rdx, byte_140074A8B
0x14002bec6  lea     rax, [rbp+57h+var_80]
0x14002beca  mov     [rsp+0E0h+var_88], rax
0x14002becf  lea     rax, [rbp+57h+var_7C]
0x14002bed3  mov     [rsp+0E0h+var_90], rax
0x14002bed8  lea     rax, [rbp+57h+var_78]
0x14002bedc  mov     [rsp+0E0h+var_98], rax
0x14002bee1  lea     rax, [rbp+57h+var_74]
0x14002bee5  mov     [rsp+0E0h+var_A0], rax
0x14002beea  lea     rax, [rbp+57h+var_70]
0x14002beee  mov     [rsp+0E0h+var_A8], rax
0x14002bef3  lea     rax, [rbp+57h+var_68]
0x14002bef7  mov     [rsp+0E0h+var_B0], rax
0x14002befc  lea     rax, [rbp+57h+var_60]
0x14002bf00  mov     [rsp+0E0h+var_B8], rax
0x14002bf05  lea     rax, [rbp+57h+var_58]
0x14002bf09  mov     [rsp+0E0h+var_C0], rax
0x14002bf0e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002bf13  mov     rcx, [rbp+57h+var_18]
0x14002bf17  xor     rcx, rsp; StackCookie
0x14002bf1a  call    __security_check_cookie
0x14002bf1f  lea     r11, [rsp+0E0h+var_10]
0x14002bf27  mov     rbx, [r11+28h]
0x14002bf2b  mov     rsi, [r11+30h]
0x14002bf2f  mov     rsp, r11
0x14002bf32  pop     r14
0x14002bf34  pop     rdi
0x14002bf35  pop     rbp
0x14002bf36  retn
```
