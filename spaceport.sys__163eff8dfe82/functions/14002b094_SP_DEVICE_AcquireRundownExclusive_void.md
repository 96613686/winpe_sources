# SP_DEVICE::AcquireRundownExclusive(void)

- ea: `0x14002b094`
- end: `0x14002b307`
- name: `?AcquireRundownExclusive@SP_DEVICE@@QEAAXXZ`
- size: `627`
- prototype: `void __fastcall(SP_DEVICE *__hidden this)`
- caller_count: `8`
- callee_count: `7`
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
- `0x140002260`
- `0x1400216f0`
- `0x14002b094`
- `0x14002c32c`
- `0x14002c3ec`
- `0x140068110`

## import_xrefs

- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14002b19c`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14002b19c`
- `ntoskrnl!KeClearEvent` at `0x14002b0e8`
- `ntoskrnl!KeClearEvent` at `0x14002b0e8`
- `ntoskrnl!IoGetActivityIdThread` at `0x14002b26d`
- `ntoskrnl!IoGetActivityIdThread` at `0x14002b26d`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002b0ca`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002b107`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002b0ca`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14002b107`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002b0fb`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x14002b0fb`

## pseudocode

```c
void __fastcall SP_DEVICE::AcquireRundownExclusive(SP_DEVICE *this)
{
  ULONGLONG UnbiasedInterruptTime; // rbx
  ULONGLONG v3; // rax
  unsigned __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rsi
  int v8; // r8d
  __int64 i; // rcx
  char *v10; // rax
  char *v11; // rax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // [rsp+70h] [rbp-19h] BYREF
  int v16; // [rsp+74h] [rbp-15h] BYREF
  int v17; // [rsp+78h] [rbp-11h] BYREF
  int v18; // [rsp+7Ch] [rbp-Dh] BYREF
  char *v19; // [rsp+80h] [rbp-9h] BYREF
  char *v20; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int64 v21; // [rsp+90h] [rbp+7h] BYREF
  __int64 ActivityIdThread; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+A0h] [rbp+17h] BYREF
  PVOID BackTrace[2]; // [rsp+A8h] [rbp+1Fh] BYREF
  __int128 v25; // [rsp+B8h] [rbp+2Fh]

  *(_OWORD *)BackTrace = 0;
  v25 = 0;
  UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
  SP_DEVICE::AcquireMutex(this);
  KeClearEvent((PRKEVENT)((char *)this + 256));
  ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)this + 30));
  v3 = KeQueryUnbiasedInterruptTime();
  *((_QWORD *)this + 31) = v3;
  v4 = (v3 - UnbiasedInterruptTime) / 0x2710;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_7f2ea8968a1c30cfdadfaeadae5d584a_Traceguids, v4);
  }
  if ( v4 > 0x7530 )
  {
    v5 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
    v6 = *(_QWORD *)(v5 + 24);
    v7 = v6 + *(unsigned int *)(v5 + 32);
    RtlCaptureStackBackTrace(1u, 4u, BackTrace, 0);
    for ( i = 0; i != 4; ++i )
    {
      v10 = (char *)BackTrace[i];
      if ( (unsigned __int64)v10 < v6 || (unsigned __int64)v10 >= v7 )
        v11 = 0;
      else
        v11 = &v10[-v6];
      BackTrace[i] = v11;
    }
    if ( (Microsoft_Windows_StorageSpaces_DriverEnableBits & 0x40) != 0 )
      McTemplateK0xjjdddd_EtwWriteTransfer(
        (_DWORD)this + 40,
        (unsigned int)RundownWait,
        v8,
        v4,
        (__int64)this + 24,
        (__int64)this + 40,
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
        v19 = (char *)this + 40;
        v20 = (char *)this + 24;
        v21 = v4;
        v23 = 0x1000000;
        ActivityIdThread = IoGetActivityIdThread((char *)this + 24);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v12,
          (unsigned int)byte_140074BE5,
          v13,
          v14,
          (__int64)&v23,
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
0x14002b094  mov     [rsp-8+arg_8], rbx
0x14002b099  mov     [rsp-8+arg_10], rsi
0x14002b09e  push    rbp
0x14002b09f  push    rdi
0x14002b0a0  push    r14
0x14002b0a2  lea     rbp, [rsp-47h]
0x14002b0a7  sub     rsp, 0D0h
0x14002b0ae  mov     rax, cs:__security_cookie
0x14002b0b5  xor     rax, rsp
0x14002b0b8  mov     [rbp+57h+var_18], rax
0x14002b0bc  xorps   xmm0, xmm0
0x14002b0bf  mov     r14, rcx
0x14002b0c2  movups  xmmword ptr [rbp+57h+BackTrace], xmm0
0x14002b0c6  movups  [rbp+57h+var_28], xmm0
0x14002b0ca  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14002b0d1  nop     dword ptr [rax+rax+00h]
0x14002b0d6  mov     rcx, r14; this
0x14002b0d9  mov     rbx, rax
0x14002b0dc  call    ?AcquireMutex@SP_DEVICE@@QEAAXXZ; SP_DEVICE::AcquireMutex(void)
0x14002b0e1  lea     rcx, [r14+100h]; Event
0x14002b0e8  call    cs:__imp_KeClearEvent
0x14002b0ef  nop     dword ptr [rax+rax+00h]
0x14002b0f4  mov     rcx, [r14+0F0h]; RunRef
0x14002b0fb  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14002b102  nop     dword ptr [rax+rax+00h]
0x14002b107  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14002b10e  nop     dword ptr [rax+rax+00h]
0x14002b113  mov     rcx, rax
0x14002b116  mov     [r14+0F8h], rax
0x14002b11d  sub     rcx, rbx
0x14002b120  mov     rax, 346DC5D63886594Bh
0x14002b12a  mul     rcx
0x14002b12d  mov     rbx, rdx
0x14002b130  shr     rbx, 0Bh
0x14002b134  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b13b  lea     rax, WPP_GLOBAL_Control
0x14002b142  cmp     rcx, rax
0x14002b145  jz      short loc_14002B16C
0x14002b147  mov     eax, [rcx+2Ch]
0x14002b14a  test    al, 1
0x14002b14c  jz      short loc_14002B16C
0x14002b14e  cmp     byte ptr [rcx+29h], 3
0x14002b152  jb      short loc_14002B16C
0x14002b154  mov     rcx, [rcx+18h]
0x14002b158  lea     r8, WPP_7f2ea8968a1c30cfdadfaeadae5d584a_Traceguids
0x14002b15f  mov     edx, 0Ch
0x14002b164  mov     r9, rbx
0x14002b167  call    WPP_SF_i
0x14002b16c  cmp     rbx, 7530h
0x14002b173  jbe     loc_14002B2E2
0x14002b179  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14002b180  lea     r8, [rbp+57h+BackTrace]; BackTrace
0x14002b184  xor     r9d, r9d; BackTraceHash
0x14002b187  mov     rcx, [rax+8]
0x14002b18b  lea     edx, [r9+4]; FramesToCapture
0x14002b18f  mov     rdi, [rcx+18h]
0x14002b193  mov     esi, [rcx+20h]
0x14002b196  lea     ecx, [rdx-3]; FramesToSkip
0x14002b199  add     rsi, rdi
0x14002b19c  call    cs:__imp_RtlCaptureStackBackTrace
0x14002b1a3  nop     dword ptr [rax+rax+00h]
0x14002b1a8  xor     ecx, ecx
0x14002b1aa  mov     rax, [rbp+rcx*8+57h+BackTrace]
0x14002b1af  cmp     rax, rdi
0x14002b1b2  jb      short loc_14002B1BE
0x14002b1b4  cmp     rax, rsi
0x14002b1b7  jnb     short loc_14002B1BE
0x14002b1b9  sub     rax, rdi
0x14002b1bc  jmp     short loc_14002B1C0
0x14002b1be  xor     eax, eax
0x14002b1c0  mov     [rbp+rcx*8+57h+BackTrace], rax
0x14002b1c5  inc     rcx
0x14002b1c8  cmp     rcx, 4
0x14002b1cc  jnz     short loc_14002B1AA
0x14002b1ce  test    cs:Microsoft_Windows_StorageSpaces_DriverEnableBits, 40h
0x14002b1d5  jz      short loc_14002B214
0x14002b1d7  mov     eax, dword ptr [rbp+57h+var_28+8]
0x14002b1da  lea     rdx, [r14+18h]
0x14002b1de  mov     dword ptr [rsp+0E0h+var_98], eax
0x14002b1e2  lea     rcx, [rdx+10h]
0x14002b1e6  mov     eax, dword ptr [rbp+57h+var_28]
0x14002b1e9  mov     r9, rbx
0x14002b1ec  mov     dword ptr [rsp+0E0h+var_A0], eax
0x14002b1f0  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x14002b1f3  mov     dword ptr [rsp+0E0h+var_A8], eax
0x14002b1f7  mov     eax, dword ptr [rbp+57h+BackTrace]
0x14002b1fa  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14002b1fe  mov     [rsp+0E0h+var_B8], rcx
0x14002b203  mov     [rsp+0E0h+var_C0], rdx
0x14002b208  lea     rdx, RundownWait
0x14002b20f  call    McTemplateK0xjjdddd_EtwWriteTransfer
0x14002b214  mov     eax, cs:dword_14007F050
0x14002b21a  cmp     eax, 5
0x14002b21d  jbe     loc_14002B2E2
0x14002b223  mov     rdx, 400000000000h
0x14002b22d  lea     rcx, dword_14007F050
0x14002b234  call    _tlgKeywordOn
0x14002b239  test    al, al
0x14002b23b  jz      loc_14002B2E2
0x14002b241  mov     eax, dword ptr [rbp+57h+var_28+8]
0x14002b244  lea     rcx, [r14+18h]
0x14002b248  mov     [rbp+57h+var_70], eax
0x14002b24b  mov     eax, dword ptr [rbp+57h+var_28]
0x14002b24e  mov     [rbp+57h+var_6C], eax
0x14002b251  mov     eax, dword ptr [rbp+57h+BackTrace+8]
0x14002b254  mov     [rbp+57h+var_68], eax
0x14002b257  mov     eax, dword ptr [rbp+57h+BackTrace]
0x14002b25a  mov     [rbp+57h+var_64], eax
0x14002b25d  lea     rax, [rcx+10h]
0x14002b261  mov     [rbp+57h+var_60], rax
0x14002b265  mov     [rbp+57h+var_58], rcx
0x14002b269  mov     [rbp+57h+var_50], rbx
0x14002b26d  call    cs:__imp_IoGetActivityIdThread
0x14002b274  nop     dword ptr [rax+rax+00h]
0x14002b279  lea     rdx, byte_140074BE5
0x14002b280  mov     [rbp+57h+var_40], 1000000h
0x14002b288  mov     [rbp+57h+var_48], rax
0x14002b28c  lea     rax, [rbp+57h+var_70]
0x14002b290  mov     [rsp+0E0h+var_80], rax
0x14002b295  lea     rax, [rbp+57h+var_6C]
0x14002b299  mov     [rsp+0E0h+var_88], rax
0x14002b29e  lea     rax, [rbp+57h+var_68]
0x14002b2a2  mov     [rsp+0E0h+var_90], rax
0x14002b2a7  lea     rax, [rbp+57h+var_64]
0x14002b2ab  mov     [rsp+0E0h+var_98], rax
0x14002b2b0  lea     rax, [rbp+57h+var_60]
0x14002b2b4  mov     [rsp+0E0h+var_A0], rax
0x14002b2b9  lea     rax, [rbp+57h+var_58]
0x14002b2bd  mov     [rsp+0E0h+var_A8], rax
0x14002b2c2  lea     rax, [rbp+57h+var_50]
0x14002b2c6  mov     [rsp+0E0h+var_B0], rax
0x14002b2cb  lea     rax, [rbp+57h+var_48]
0x14002b2cf  mov     [rsp+0E0h+var_B8], rax
0x14002b2d4  lea     rax, [rbp+57h+var_40]
0x14002b2d8  mov     [rsp+0E0h+var_C0], rax
0x14002b2dd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U1@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@344AEBU?$_tlgWrapperByVal@$03@@555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14002b2e2  mov     rcx, [rbp+57h+var_18]
0x14002b2e6  xor     rcx, rsp; StackCookie
0x14002b2e9  call    __security_check_cookie
0x14002b2ee  lea     r11, [rsp+0E0h+var_10]
0x14002b2f6  mov     rbx, [r11+28h]
0x14002b2fa  mov     rsi, [r11+30h]
0x14002b2fe  mov     rsp, r11
0x14002b301  pop     r14
0x14002b303  pop     rdi
0x14002b304  pop     rbp
0x14002b305  retn
```
