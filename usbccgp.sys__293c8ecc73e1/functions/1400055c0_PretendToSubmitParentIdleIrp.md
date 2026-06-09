# PretendToSubmitParentIdleIrp

- ea: `0x1400055c0`
- end: `0x140005740`
- name: `PretendToSubmitParentIdleIrp`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140004f50`

## callees

- `0x1400054a0`
- `0x1400055c0`
- `0x140005854`
- `0x140005940`
- `0x1400059e4`
- `0x1400083c8`
- `0x1400088b4`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000572f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000572f`
- `ntoskrnl!IoReuseIrp` at `0x1400055d6`
- `ntoskrnl!IoReuseIrp` at `0x1400055d6`

## pseudocode

```c
__int64 __fastcall PretendToSubmitParentIdleIrp(__int64 a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int v5; // edx
  int Worker; // esi
  int v7; // edx
  int v8; // edx

  IoReuseIrp(a2, 0);
  *(_QWORD *)(a1 + 680) = a1;
  *(_QWORD *)(a1 + 672) = ParentIdleNotificationCallback;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = (_NAMED_PIPE_CREATE_PARAMETERS *)(a1 + 672);
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228263;
  CurrentStackLocation[-1].Parameters.Create.Options = 16;
  Worker = UsbcAcquireRemoveLock(a1, 1883853651, a2);
  if ( Worker < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v5, 7, 16, (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids);
    }
  }
  else
  {
    SetCompletionRoutine(
      *(_QWORD *)(a1 + 1368),
      *(struct _DEVICE_OBJECT **)(a1 + 32),
      a2,
      (IO_COMPLETION_ROUTINE *)ParentIdleNotificationRequestComplete,
      (PVOID)a1);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 4;
      WPP_RECORDER_SF_q(
        *(_QWORD *)(a1 + 1368),
        v7,
        7,
        17,
        (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
        (char)a2);
    }
    Worker = AllocateWorker(a1, InvokeParentIdleCallbackWorker, a2);
    if ( Worker < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v8, 7, 18, (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids);
      }
      UsbcReleaseRemoveLock(a1, a2);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 200), a2, 0x20u);
    }
    else
    {
      return 259;
    }
  }
  return (unsigned int)Worker;
}

```

## disassembly

```asm
0x1400055c0  push    rbx
0x1400055c2  push    rbp
0x1400055c3  push    rsi
0x1400055c4  push    rdi
0x1400055c5  push    r14
0x1400055c7  sub     rsp, 40h
0x1400055cb  mov     rdi, rdx
0x1400055ce  mov     rbx, rcx
0x1400055d1  mov     rcx, rdi; Irp
0x1400055d4  xor     edx, edx; Iostatus
0x1400055d6  call    cs:__imp_IoReuseIrp
0x1400055dd  nop     dword ptr [rax+rax+00h]
0x1400055e2  mov     [rbx+2A8h], rbx
0x1400055e9  lea     r8, [rbx+2A0h]
0x1400055f0  lea     rax, ParentIdleNotificationCallback
0x1400055f7  mov     r14d, 10h
0x1400055fd  mov     [r8], rax
0x140005600  mov     edx, 70495353h
0x140005605  mov     rax, [rdi+0B8h]
0x14000560c  mov     rcx, rbx
0x14000560f  mov     [rax-28h], r8
0x140005613  mov     r8, rdi
0x140005616  mov     byte ptr [rax-48h], 0Fh
0x14000561a  mov     dword ptr [rax-30h], 220027h
0x140005621  mov     [rax-38h], r14d
0x140005625  call    UsbcAcquireRemoveLock
0x14000562a  mov     esi, eax
0x14000562c  test    eax, eax
0x14000562e  js      loc_1400056B9
0x140005634  mov     rdx, [rbx+20h]
0x140005638  lea     r9, ParentIdleNotificationRequestComplete
0x14000563f  mov     rcx, [rbx+558h]
0x140005646  mov     r8, rdi
0x140005649  mov     [rsp+68h+var_48], rbx
0x14000564e  call    SetCompletionRoutine
0x140005653  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000565a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x140005661  lea     r14, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x140005668  jnz     short loc_140005695
0x14000566a  mov     r8, rdi
0x14000566d  lea     rdx, InvokeParentIdleCallbackWorker
0x140005674  mov     rcx, rbx
0x140005677  call    AllocateWorker
0x14000567c  mov     esi, eax
0x14000567e  test    eax, eax
0x140005680  js      short loc_1400056EE
0x140005682  mov     esi, 103h
0x140005687  mov     eax, esi
0x140005689  add     rsp, 40h
0x14000568d  pop     r14
0x14000568f  pop     rdi
0x140005690  pop     rsi
0x140005691  pop     rbp
0x140005692  pop     rbx
0x140005693  retn
0x140005695  mov     rcx, [rbx+558h]
0x14000569c  mov     r9d, 11h
0x1400056a2  mov     [rsp+68h+var_40], rdi
0x1400056a7  mov     dl, 4
0x1400056a9  mov     [rsp+68h+var_48], r14
0x1400056ae  lea     r8d, [r9-0Ah]
0x1400056b2  call    WPP_RECORDER_SF_q
0x1400056b7  jmp     short loc_14000566A
0x1400056b9  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400056c0  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400056c7  jz      short loc_140005687
0x1400056c9  mov     rcx, [rbx+558h]
0x1400056d0  mov     r9d, r14d
0x1400056d3  lea     r14, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x1400056da  mov     r8d, 7
0x1400056e0  mov     dl, 2
0x1400056e2  mov     [rsp+68h+var_48], r14
0x1400056e7  call    WPP_RECORDER_SF_
0x1400056ec  jmp     short loc_140005687
0x1400056ee  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x1400056f5  jz      short loc_140005714
0x1400056f7  mov     rcx, [rbx+558h]
0x1400056fe  mov     r9d, 12h
0x140005704  mov     dl, 2
0x140005706  mov     [rsp+68h+var_48], r14
0x14000570b  lea     r8d, [r9-0Bh]
0x14000570f  call    WPP_RECORDER_SF_
0x140005714  mov     rdx, rdi
0x140005717  mov     rcx, rbx
0x14000571a  call    UsbcReleaseRemoveLock
0x14000571f  lea     rcx, [rbx+0C8h]; RemoveLock
0x140005726  mov     r8d, 20h ; ' '; RemlockSize
0x14000572c  mov     rdx, rdi; Tag
0x14000572f  call    cs:__imp_IoReleaseRemoveLockEx
0x140005736  nop     dword ptr [rax+rax+00h]
0x14000573b  jmp     loc_140005687
```
