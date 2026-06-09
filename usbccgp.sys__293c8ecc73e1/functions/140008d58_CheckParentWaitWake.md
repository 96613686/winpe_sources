# CheckParentWaitWake

- ea: `0x140008d58`
- end: `0x140008ea4`
- name: `CheckParentWaitWake`
- size: `332`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140004b08`
- `0x140008b00`
- `0x140009210`
- `0x14000d81c`
- `0x140013eb0`

## callees

- `0x140004b08`
- `0x1400083c8`
- `0x140008d58`
- `0x140009368`
- `0x140009450`
- `0x14000a300`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008d92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008d92`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008dc9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008e45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008e89`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008dc9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008e45`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008e89`

## pseudocode

```c
void __fastcall CheckParentWaitWake(char *Context)
{
  __int64 *v2; // r14
  KIRQL v3; // al
  int v4; // ecx
  KIRQL v5; // bp
  int v6; // edx
  int v7; // eax
  int v8; // edi

  v2 = (__int64 *)(Context + 1368);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *v2,
      4u,
      3u,
      0x21u,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *((_QWORD *)Context + 4));
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 50);
  v4 = *((_DWORD *)Context + 102);
  v5 = v3;
  v6 = (unsigned __int8)Context[440];
  if ( !v4 )
  {
    if ( (_BYTE)v6 )
    {
      v8 = _InterlockedExchange((volatile __int32 *)Context + 98, 1);
      KeReleaseSpinLock((PKSPIN_LOCK)Context + 50, v3);
      CancelParentWaitWakeArg((__int64)Context, v8);
      return;
    }
    goto LABEL_5;
  }
  if ( (_BYTE)v6 )
  {
LABEL_5:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_qDD(
        *v2,
        v6,
        3,
        34,
        (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
        *((_QWORD *)Context + 4),
        Context[440],
        v4);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)Context + 50, v5);
    return;
  }
  Context[440] = 1;
  KeReleaseSpinLock((PKSPIN_LOCK)Context + 50, v3);
  v7 = SubmitParentWaitWakeIrp(Context);
  if ( v7 < 0 )
    CompleteAllPdoWaitWakeIrps(Context, v7);
}

```

## disassembly

```asm
0x140008d58  push    rbx
0x140008d5a  push    rbp
0x140008d5b  push    rsi
0x140008d5c  push    rdi
0x140008d5d  push    r13
0x140008d5f  push    r14
0x140008d61  push    r15
0x140008d63  sub     rsp, 40h
0x140008d67  mov     rbx, rcx
0x140008d6a  lea     r15, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140008d71  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140008d78  lea     r14, [rcx+558h]
0x140008d7f  lea     r13, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140008d86  jnz     short loc_140008DE5
0x140008d88  lea     rsi, [rbx+190h]
0x140008d8f  mov     rcx, rsi; SpinLock
0x140008d92  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008d99  nop     dword ptr [rax+rax+00h]
0x140008d9e  mov     ecx, [rbx+198h]
0x140008da4  mov     bpl, al
0x140008da7  movzx   edx, byte ptr [rbx+1B8h]
0x140008dae  test    ecx, ecx
0x140008db0  jz      loc_140008E70
0x140008db6  test    dl, dl
0x140008db8  jz      short loc_140008E38
0x140008dba  cmp     cs:WPP_RECORDER_INITIALIZED, r15; __annotation("TMF:",
0x140008dc1  jnz     short loc_140008E0C
0x140008dc3  mov     dl, bpl; NewIrql
0x140008dc6  mov     rcx, rsi; SpinLock
0x140008dc9  call    cs:__imp_KeReleaseSpinLock
0x140008dd0  nop     dword ptr [rax+rax+00h]
0x140008dd5  add     rsp, 40h
0x140008dd9  pop     r15
0x140008ddb  pop     r14
0x140008ddd  pop     r13
0x140008ddf  pop     rdi
0x140008de0  pop     rsi
0x140008de1  pop     rbp
0x140008de2  pop     rbx
0x140008de3  retn
0x140008de5  mov     rax, [rcx+20h]
0x140008de9  mov     r9d, 21h ; '!'
0x140008def  mov     rcx, [r14]
0x140008df2  mov     dl, 4
0x140008df4  mov     [rsp+78h+var_50], rax
0x140008df9  mov     [rsp+78h+var_58], r13
0x140008dfe  lea     r8d, [r9-1Eh]
0x140008e02  call    WPP_RECORDER_SF_q
0x140008e07  jmp     loc_140008D88
0x140008e0c  mov     rax, [rbx+20h]
0x140008e10  mov     r9d, 22h ; '"'
0x140008e16  mov     [rsp+78h+var_40], ecx
0x140008e1a  mov     rcx, [r14]
0x140008e1d  mov     [rsp+78h+var_48], edx
0x140008e21  mov     dl, 4
0x140008e23  mov     [rsp+78h+var_50], rax
0x140008e28  lea     r8d, [r9-1Fh]
0x140008e2c  mov     [rsp+78h+var_58], r13
0x140008e31  call    WPP_RECORDER_SF_qDD
0x140008e36  jmp     short loc_140008DC3
0x140008e38  mov     dl, bpl; NewIrql
0x140008e3b  mov     byte ptr [rbx+1B8h], 1
0x140008e42  mov     rcx, rsi; SpinLock
0x140008e45  call    cs:__imp_KeReleaseSpinLock
0x140008e4c  nop     dword ptr [rax+rax+00h]
0x140008e51  mov     rcx, rbx; Context
0x140008e54  call    SubmitParentWaitWakeIrp
0x140008e59  test    eax, eax
0x140008e5b  jns     loc_140008DD5
0x140008e61  mov     edx, eax
0x140008e63  mov     rcx, rbx
0x140008e66  call    CompleteAllPdoWaitWakeIrps
0x140008e6b  jmp     loc_140008DD5
0x140008e70  test    dl, dl
0x140008e72  jz      loc_140008DBA
0x140008e78  mov     edi, 1
0x140008e7d  mov     dl, bpl; NewIrql
0x140008e80  xchg    edi, [rbx+188h]
0x140008e86  mov     rcx, rsi; SpinLock
0x140008e89  call    cs:__imp_KeReleaseSpinLock
0x140008e90  nop     dword ptr [rax+rax+00h]
0x140008e95  mov     edx, edi
0x140008e97  mov     rcx, rbx
0x140008e9a  call    CancelParentWaitWakeArg
0x140008e9f  jmp     loc_140008DD5
```
