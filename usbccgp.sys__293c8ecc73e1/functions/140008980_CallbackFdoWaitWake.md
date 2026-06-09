# CallbackFdoWaitWake

- ea: `0x140008980`
- end: `0x140008af8`
- name: `CallbackFdoWaitWake`
- size: `376`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140004b08`
- `0x1400059e4`
- `0x140007c38`
- `0x1400083c8`
- `0x140008980`
- `0x140013eb0`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400089f3`
- `ntoskrnl!KeReadStateEvent` at `0x1400089f3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400089dd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400089dd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008a12`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008a12`

## pseudocode

```c
void __fastcall CallbackFdoWaitWake(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        __int64 Context,
        PIO_STATUS_BLOCK IoStatus)
{
  int Status; // esi
  int v7; // edx
  char v8; // bl
  int v9; // eax
  int v10; // edx
  KIRQL v11; // bp
  int v12; // edx

  Status = IoStatus->Status;
  if ( IoStatus->Status >= 0 )
  {
    v8 = 1;
    if ( *(_DWORD *)(Context + 4) != 1 )
    {
      v9 = FdoSendSetPowerRequest((POWER_STATE)1, 0, 0, Context);
      Status = v9;
      if ( v9 == 259 || v9 == -2147483631 )
      {
        v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(Context + 344));
        if ( !KeReadStateEvent((PRKEVENT)(Context + 312)) )
        {
          *(_DWORD *)(Context + 1228) |= 8u;
          v8 = 0;
        }
        KeReleaseSpinLock((PKSPIN_LOCK)(Context + 344), v11);
        if ( !v8 )
          return;
        Status = AllocateWorker(Context, WaitWakeFinishCompletionWorker, 0);
        if ( Status >= 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = 4;
            WPP_RECORDER_SF_q(
              *(_QWORD *)(Context + 1368),
              v12,
              3,
              26,
              (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
              *(_QWORD *)(Context + 32));
          }
          return;
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_q(
          *(_QWORD *)(Context + 1368),
          v10,
          8,
          27,
          (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
          *(_QWORD *)(Context + 32));
      }
    }
  }
  if ( !*(_BYTE *)(Context + 1362) )
  {
    v7 = Status;
LABEL_4:
    CompleteAllPdoWaitWakeIrps((char *)Context, v7);
    return;
  }
  if ( *(_DWORD *)(Context + 576) == 2 )
  {
    v7 = -1073741536;
    goto LABEL_4;
  }
  FinishWaitWakeCompletionForFunctionSuspend((char *)Context);
}

```

## disassembly

```asm
0x140008980  push    rbx
0x140008982  push    rbp
0x140008983  push    rsi
0x140008984  push    rdi
0x140008985  sub     rsp, 38h
0x140008989  mov     rax, [rsp+58h+IoStatus]
0x140008991  mov     rdi, r9
0x140008994  mov     esi, [rax]
0x140008996  test    esi, esi
0x140008998  jns     short loc_1400089B3
0x14000899a  cmp     byte ptr [rdi+552h], 0
0x1400089a1  mov     rcx, rdi; Context
0x1400089a4  jnz     loc_140008ADB
0x1400089aa  mov     edx, esi
0x1400089ac  call    CompleteAllPdoWaitWakeIrps
0x1400089b1  jmp     short loc_140008A22
0x1400089b3  mov     ebx, 1
0x1400089b8  cmp     [r9+4], ebx
0x1400089bc  jz      short loc_14000899A
0x1400089be  xor     r8d, r8d
0x1400089c1  xor     edx, edx; CompletionFunction
0x1400089c3  mov     ecx, ebx; PowerState
0x1400089c5  call    FdoSendSetPowerRequest
0x1400089ca  mov     esi, eax
0x1400089cc  cmp     eax, 103h
0x1400089d1  jnz     short loc_140008A2C
0x1400089d3  lea     rsi, [rdi+158h]
0x1400089da  mov     rcx, rsi; SpinLock
0x1400089dd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400089e4  nop     dword ptr [rax+rax+00h]
0x1400089e9  lea     rcx, [rdi+138h]; Event
0x1400089f0  mov     bpl, al
0x1400089f3  call    cs:__imp_KeReadStateEvent
0x1400089fa  nop     dword ptr [rax+rax+00h]
0x1400089ff  test    eax, eax
0x140008a01  jnz     short loc_140008A0C
0x140008a03  or      dword ptr [rdi+4CCh], 8
0x140008a0a  xor     bl, bl
0x140008a0c  mov     dl, bpl; NewIrql
0x140008a0f  mov     rcx, rsi; SpinLock
0x140008a12  call    cs:__imp_KeReleaseSpinLock
0x140008a19  nop     dword ptr [rax+rax+00h]
0x140008a1e  test    bl, bl
0x140008a20  jnz     short loc_140008A79
0x140008a22  add     rsp, 38h
0x140008a26  pop     rdi
0x140008a27  pop     rsi
0x140008a28  pop     rbp
0x140008a29  pop     rbx
0x140008a2a  retn
0x140008a2c  cmp     eax, 80000011h
0x140008a31  jz      short loc_1400089D3
0x140008a33  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140008a3a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008a41  jz      loc_14000899A
0x140008a47  mov     rcx, [rdi+20h]
0x140008a4b  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140008a52  mov     [rsp+58h+var_30], rcx
0x140008a57  mov     r9d, 1Bh
0x140008a5d  mov     rcx, [rdi+558h]
0x140008a64  mov     dl, 2
0x140008a66  mov     [rsp+58h+var_38], rax
0x140008a6b  lea     r8d, [r9-13h]
0x140008a6f  call    WPP_RECORDER_SF_q
0x140008a74  jmp     loc_14000899A
0x140008a79  xor     r8d, r8d
0x140008a7c  lea     rdx, WaitWakeFinishCompletionWorker
0x140008a83  mov     rcx, rdi
0x140008a86  call    AllocateWorker
0x140008a8b  mov     esi, eax
0x140008a8d  test    eax, eax
0x140008a8f  js      loc_14000899A
0x140008a95  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140008a9c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008aa3  jz      loc_140008A22
0x140008aa9  mov     rax, [rdi+20h]
0x140008aad  mov     r9d, 1Ah
0x140008ab3  mov     rcx, [rdi+558h]
0x140008aba  mov     dl, 4
0x140008abc  mov     [rsp+58h+var_30], rax
0x140008ac1  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140008ac8  mov     [rsp+58h+var_38], rax
0x140008acd  lea     r8d, [r9-17h]
0x140008ad1  call    WPP_RECORDER_SF_q
0x140008ad6  jmp     loc_140008A22
0x140008adb  cmp     dword ptr [rdi+240h], 2
0x140008ae2  jz      short loc_140008AEE
0x140008ae4  call    FinishWaitWakeCompletionForFunctionSuspend
0x140008ae9  jmp     loc_140008A22
0x140008aee  mov     edx, 0C0000120h
0x140008af3  jmp     loc_1400089AC
```
