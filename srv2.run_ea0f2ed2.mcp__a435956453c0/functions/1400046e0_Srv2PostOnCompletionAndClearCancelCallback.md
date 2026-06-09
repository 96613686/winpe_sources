# Srv2PostOnCompletionAndClearCancelCallback

- ea: `0x1400046e0`
- end: `0x14000480b`
- name: `Srv2PostOnCompletionAndClearCancelCallback`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400046e0`
- `0x1400051dc`
- `0x1400384d0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14003a535`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003a535`
- `ntoskrnl!RtlInitAnsiString` at `0x1400047b8`
- `ntoskrnl!RtlInitAnsiString` at `0x1400047b8`
- `HAL!KeQueryPerformanceCounter` at `0x14000475b`
- `HAL!KeQueryPerformanceCounter` at `0x14000475b`

## string_xrefs

- `0x14000479e`: `Srv2PostOnCompletionAndClearCancelCallback`

## pseudocode

```c
__int64 __fastcall Srv2PostOnCompletionAndClearCancelCallback(__int64 a1)
{
  __int64 (__fastcall **v1)(__int64); // rdi
  __int64 v3; // rax
  __int64 v4; // rsi
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // edx
  int v10; // ecx
  struct _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp+8h] BYREF

  v1 = (__int64 (__fastcall **)(__int64))(a1 + 48);
  *(_QWORD *)(a1 + 48) = *(_QWORD *)(a1 + 88);
  *(_QWORD *)(a1 + 88) = Srv2ProcPostToCallback;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 476), 0, 1) == 2 )
  {
    Interval.QuadPart = -10000;
    do
      KeDelayExecutionThread(0, 0, &Interval);
    while ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 476), 0, 0) );
    v1 = (__int64 (__fastcall **)(__int64))(a1 + 48);
  }
  v3 = *(_QWORD *)(a1 + 120);
  v4 = a1 + 584;
  DestinationString = 0;
  *(_BYTE *)(v3 + 68) = 0;
  if ( *(_BYTE *)(a1 + 600) )
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v7 = *(unsigned __int8 *)(a1 + 712);
    if ( (_BYTE)v7 != 0xFF && (_BYTE)v7 )
    {
      v8 = *(_QWORD *)(a1 + 720);
      if ( PerformanceCounter.QuadPart > v8 )
        *(_QWORD *)(v4 + 8 * v7 + 40) += PerformanceCounter.QuadPart - v8;
      ++*(_WORD *)(v4 + 2 * v7 + 18);
      v1 = (__int64 (__fastcall **)(__int64))(a1 + 48);
    }
    *(_BYTE *)(a1 + 712) = 0;
    *(LARGE_INTEGER *)(a1 + 720) = PerformanceCounter;
    RtlInitAnsiString(&DestinationString, "Srv2PostOnCompletionAndClearCancelCallback");
    if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
      McTemplateK0qqhsr2_EtwWriteTransfer(
        v10,
        v9,
        a1 + 584,
        0,
        209,
        DestinationString.Length,
        (__int64)DestinationString.Buffer);
  }
  return (*v1)(a1);
}

```

## disassembly

```asm
0x1400046e0  mov     [rsp+arg_8], rbx
0x1400046e5  mov     [rsp+arg_10], rsi
0x1400046ea  push    rdi
0x1400046eb  sub     rsp, 50h
0x1400046ef  mov     rax, [rcx+58h]
0x1400046f3  lea     rdi, [rcx+30h]
0x1400046f7  mov     [rdi], rax
0x1400046fa  mov     rbx, rcx
0x1400046fd  lea     rax, Srv2ProcPostToCallback
0x140004704  mov     [rcx+58h], rax
0x140004708  xor     ecx, ecx
0x14000470a  mov     eax, 1
0x14000470f  lock cmpxchg [rbx+1DCh], ecx
0x140004717  cmp     eax, 2
0x14000471a  jz      loc_1400047FD
0x140004720  mov     rax, [rbx+78h]
0x140004724  lea     rsi, [rbx+248h]
0x14000472b  xorps   xmm0, xmm0
0x14000472e  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140004733  mov     byte ptr [rax+44h], 0
0x140004737  cmp     byte ptr [rsi+10h], 0
0x14000473b  jnz     short loc_140004759
0x14000473d  mov     rax, [rdi]
0x140004740  mov     rcx, rbx
0x140004743  call    _guard_dispatch_icall
0x140004748  mov     rbx, [rsp+58h+arg_8]
0x14000474d  mov     rsi, [rsp+58h+arg_10]
0x140004752  add     rsp, 50h
0x140004756  pop     rdi
0x140004757  retn
0x140004759  xor     ecx, ecx; PerformanceFrequency
0x14000475b  call    cs:__imp_KeQueryPerformanceCounter
0x140004762  nop     dword ptr [rax+rax+00h]
0x140004767  movzx   r8d, byte ptr [rsi+80h]
0x14000476f  cmp     r8b, 0FFh
0x140004773  jz      short loc_14000479E
0x140004775  test    r8b, r8b
0x140004778  jz      short loc_14000479E
0x14000477a  mov     r9, [rsi+88h]
0x140004781  cmp     rax, r9
0x140004784  jle     short loc_140004794
0x140004786  mov     rcx, rax
0x140004789  lea     rdx, [rsi+r8*8]
0x14000478d  sub     rcx, r9
0x140004790  add     [rdx+28h], rcx
0x140004794  inc     word ptr [rsi+r8*2+12h]
0x14000479a  lea     rdi, [rbx+30h]
0x14000479e  lea     rdx, aSrv2postoncomp; "Srv2PostOnCompletionAndClearCancelCallb"...
0x1400047a5  mov     byte ptr [rsi+80h], 0
0x1400047ac  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400047b1  mov     [rsi+88h], rax
0x1400047b8  call    cs:__imp_RtlInitAnsiString
0x1400047bf  nop     dword ptr [rax+rax+00h]
0x1400047c4  test    cs:Microsoft_Windows_SMBServerEnableBits, 4
0x1400047cb  jz      loc_14000473D
0x1400047d1  mov     rax, [rsp+58h+DestinationString.Buffer]
0x1400047d6  xor     r9d, r9d
0x1400047d9  mov     [rsp+58h+var_28], rax
0x1400047de  mov     r8, rsi
0x1400047e1  movzx   eax, [rsp+58h+DestinationString.Length]
0x1400047e6  mov     [rsp+58h+var_30], ax
0x1400047eb  mov     [rsp+58h+var_38], 8D1h
0x1400047f3  call    McTemplateK0qqhsr2_EtwWriteTransfer
0x1400047f8  jmp     loc_14000473D
0x1400047fd  mov     qword ptr [rsp+58h+Interval], 0FFFFFFFFFFFFD8F0h
0x140004806  jmp     loc_14003A52C
0x14003a52c  lea     r8, [rsp+58h+Interval]; Interval
0x14003a531  xor     edx, edx; Alertable
0x14003a533  xor     ecx, ecx; WaitMode
0x14003a535  call    cs:__imp_KeDelayExecutionThread
0x14003a53c  nop     dword ptr [rax+rax+00h]
0x14003a541  xor     ecx, ecx
0x14003a543  xor     eax, eax
0x14003a545  lock cmpxchg [rbx+1DCh], ecx
0x14003a54d  jnz     short loc_14003A52C
0x14003a54f  lea     rdi, [rbx+30h]
0x14003a553  jmp     loc_140004720
```
