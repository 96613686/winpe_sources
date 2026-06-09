# CancelFdoIdleIrp

- ea: `0x140006d40`
- end: `0x140006f4f`
- name: `CancelFdoIdleIrp`
- size: `527`
- prototype: ``
- caller_count: `8`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140004078`
- `0x140004f50`
- `0x140006630`
- `0x140007170`
- `0x14000a448`
- `0x14000b670`
- `0x140010650`
- `0x140028800`

## callees

- `0x140006834`
- `0x140006af8`
- `0x140006d40`
- `0x14000773c`
- `0x1400083c8`
- `0x14000b4bc`
- `0x14000ba3c`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006d71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006d71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006db8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006dfd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006e4d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006db8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006dfd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006e4d`
- `ntoskrnl!IoCancelIrp` at `0x140006e75`
- `ntoskrnl!IoCancelIrp` at `0x140006e75`

## string_xrefs

- `0x140006ea9`: `idleCompleteEvent (Wait for our IDLE irp to complete and the FDO to return to D0)`
- `0x140006e27`: `idleCallbackBusyEvent (waiting for IdleCallback to run to completion)`

## pseudocode

```c
__int64 __fastcall CancelFdoIdleIrp(__int64 a1, __int64 a2)
{
  char v2; // r14
  _QWORD *v4; // rdi
  KIRQL v5; // bp
  int v6; // edx
  int v7; // edx
  int v8; // edx
  __int64 v9; // rdx
  int v11; // edx
  int v12; // edx

  v2 = a2;
  DisableIdleTimer(a1, a2, 1346586964);
  v4 = (_QWORD *)(a1 + 1368);
  while ( 1 )
  {
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 696));
    if ( *(_DWORD *)(a1 + 12) == 7 )
      break;
    v6 = *(_DWORD *)(a1 + 688);
    if ( !v6 )
      goto LABEL_6;
    v7 = v6 - 1;
    if ( !v7 )
      goto LABEL_13;
    v8 = v7 - 1;
    if ( !v8 || (v11 = v8 - 1) == 0 )
    {
LABEL_6:
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 696), v5);
      goto LABEL_7;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
LABEL_13:
      ChangeIdleState(a1, 2, 0);
      break;
    }
    if ( v12 != 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v4 = (_QWORD *)(a1 + 1368);
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_D(
          *(_QWORD *)(a1 + 1368),
          v12,
          8,
          49,
          (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
          *(_DWORD *)(a1 + 688));
      }
      break;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 696), v5);
    v4 = (_QWORD *)(a1 + 1368);
    if ( !*(_BYTE *)(a1 + 1376) )
      WaitForSignal((PVOID)(a1 + 872));
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 696), v5);
  if ( *(_QWORD *)(a1 + 656) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_q(*v4, v9, 7, 50, (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids, *(_QWORD *)(a1 + 656));
    }
    if ( !IoCancelIrp(*(PIRP *)(a1 + 656)) && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 4;
      WPP_RECORDER_SF_qD(
        *v4,
        v9,
        7,
        51,
        (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
        *(_QWORD *)(a1 + 656),
        0);
    }
  }
  if ( v2 && !*(_BYTE *)(a1 + 1376) )
    WaitForSignal((PVOID)(a1 + 960));
LABEL_7:
  LOBYTE(v9) = 1;
  return EnableIdleTimer(a1, v9, 1346586964);
}

```

## disassembly

```asm
0x140006d40  push    rbx
0x140006d42  push    rbp
0x140006d43  push    rsi
0x140006d44  push    rdi
0x140006d45  push    r12
0x140006d47  push    r13
0x140006d49  push    r14
0x140006d4b  sub     rsp, 40h
0x140006d4f  mov     r8d, 50434954h
0x140006d55  mov     r14b, dl
0x140006d58  mov     rbx, rcx
0x140006d5b  call    DisableIdleTimer
0x140006d60  lea     rsi, [rbx+2B8h]
0x140006d67  lea     rdi, [rbx+558h]
0x140006d6e  mov     rcx, rsi; SpinLock
0x140006d71  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006d78  nop     dword ptr [rax+rax+00h]
0x140006d7d  cmp     dword ptr [rbx+0Ch], 7
0x140006d81  lea     r12, WPP_RECORDER_INITIALIZED
0x140006d88  mov     bpl, al
0x140006d8b  lea     r13, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x140006d92  jz      loc_140006E47
0x140006d98  mov     eax, [rbx+2B0h]
0x140006d9e  mov     edx, eax
0x140006da0  test    eax, eax
0x140006da2  jz      short loc_140006DB2
0x140006da4  sub     edx, 1
0x140006da7  jz      loc_140006E38
0x140006dad  sub     edx, 1
0x140006db0  jnz     short loc_140006DE4
0x140006db2  mov     dl, bpl; NewIrql
0x140006db5  mov     rcx, rsi; SpinLock
0x140006db8  call    cs:__imp_KeReleaseSpinLock
0x140006dbf  nop     dword ptr [rax+rax+00h]
0x140006dc4  mov     r8d, 50434954h
0x140006dca  mov     dl, 1
0x140006dcc  mov     rcx, rbx
0x140006dcf  call    EnableIdleTimer
0x140006dd4  add     rsp, 40h
0x140006dd8  pop     r14
0x140006dda  pop     r13
0x140006ddc  pop     r12
0x140006dde  pop     rdi
0x140006ddf  pop     rsi
0x140006de0  pop     rbp
0x140006de1  pop     rbx
0x140006de2  retn
0x140006de4  sub     edx, 1
0x140006de7  jz      short loc_140006DB2
0x140006de9  sub     edx, 1
0x140006dec  jz      short loc_140006E38
0x140006dee  cmp     edx, 1
0x140006df1  jnz     loc_140006EDA
0x140006df7  mov     dl, bpl; NewIrql
0x140006dfa  mov     rcx, rsi; SpinLock
0x140006dfd  call    cs:__imp_KeReleaseSpinLock
0x140006e04  nop     dword ptr [rax+rax+00h]
0x140006e09  cmp     byte ptr [rbx+560h], 0
0x140006e10  lea     rdi, [rbx+558h]
0x140006e17  jnz     loc_140006D6E
0x140006e1d  mov     r8, [rdi]
0x140006e20  lea     rcx, [rbx+368h]; Object
0x140006e27  lea     rdx, aIdlecallbackbu; "idleCallbackBusyEvent (waiting for Idle"...
0x140006e2e  call    WaitForSignal
0x140006e33  jmp     loc_140006D6E
0x140006e38  xor     r8d, r8d
0x140006e3b  mov     rcx, rbx
0x140006e3e  lea     edx, [r8+2]
0x140006e42  call    ChangeIdleState
0x140006e47  mov     dl, bpl; NewIrql
0x140006e4a  mov     rcx, rsi; SpinLock
0x140006e4d  call    cs:__imp_KeReleaseSpinLock
0x140006e54  nop     dword ptr [rax+rax+00h]
0x140006e59  mov     rax, [rbx+290h]
0x140006e60  test    rax, rax
0x140006e63  jz      short loc_140006E89
0x140006e65  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140006e6c  jnz     short loc_140006EBA
0x140006e6e  mov     rcx, [rbx+290h]; Irp
0x140006e75  call    cs:__imp_IoCancelIrp
0x140006e7c  nop     dword ptr [rax+rax+00h]
0x140006e81  test    al, al
0x140006e83  jz      loc_140006F10
0x140006e89  test    r14b, r14b
0x140006e8c  jz      loc_140006DC4
0x140006e92  cmp     byte ptr [rbx+560h], 0
0x140006e99  jnz     loc_140006DC4
0x140006e9f  mov     r8, [rdi]
0x140006ea2  lea     rcx, [rbx+3C0h]; Object
0x140006ea9  lea     rdx, aIdlecompleteev_0; "idleCompleteEvent (Wait for our IDLE ir"...
0x140006eb0  call    WaitForSignal
0x140006eb5  jmp     loc_140006DC4
0x140006eba  mov     rcx, [rdi]
0x140006ebd  mov     r9d, 32h ; '2'
0x140006ec3  mov     [rsp+78h+var_50], rax
0x140006ec8  mov     dl, 4
0x140006eca  mov     [rsp+78h+var_58], r13
0x140006ecf  lea     r8d, [r9-2Bh]
0x140006ed3  call    WPP_RECORDER_SF_q
0x140006ed8  jmp     short loc_140006E6E
0x140006eda  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140006ee1  jz      loc_140006E47
0x140006ee7  mov     r9d, 31h ; '1'
0x140006eed  mov     dword ptr [rsp+78h+var_50], eax
0x140006ef1  lea     rdi, [rbx+558h]
0x140006ef8  mov     [rsp+78h+var_58], r13
0x140006efd  mov     rcx, [rdi]
0x140006f00  mov     dl, 2
0x140006f02  lea     r8d, [r9-29h]
0x140006f06  call    WPP_RECORDER_SF_D
0x140006f0b  jmp     loc_140006E47
0x140006f10  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140006f17  jz      loc_140006E89
0x140006f1d  mov     rax, [rbx+290h]
0x140006f24  mov     r9d, 33h ; '3'
0x140006f2a  mov     rcx, [rdi]
0x140006f2d  mov     dl, 4
0x140006f2f  mov     [rsp+78h+var_48], 0
0x140006f37  mov     [rsp+78h+var_50], rax
0x140006f3c  lea     r8d, [r9-2Ch]
0x140006f40  mov     [rsp+78h+var_58], r13
0x140006f45  call    WPP_RECORDER_SF_qD
0x140006f4a  jmp     loc_140006E89
```
