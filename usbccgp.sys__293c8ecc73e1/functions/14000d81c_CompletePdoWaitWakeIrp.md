# CompletePdoWaitWakeIrp

- ea: `0x14000d81c`
- end: `0x14000d8f8`
- name: `CompletePdoWaitWakeIrp`
- size: `220`
- prototype: `__int64 __fastcall(PVOID PeekContext)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140005fc4`
- `0x14000d630`
- `0x14000e128`
- `0x14002ced0`

## callees

- `0x1400054a0`
- `0x140008d58`
- `0x140009f10`
- `0x14000d81c`
- `0x140010b00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000d8b4`
- `ntoskrnl!IofCompleteRequest` at `0x14000d8b4`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000d8db`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000d8db`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14000d838`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14000d838`

## pseudocode

```c
PIRP __fastcall CompletePdoWaitWakeIrp(char *PeekContext, int a2)
{
  __int64 v2; // rsi
  PIRP result; // rax
  int v6; // edx
  int v7; // r8d
  IRP *v8; // rbx

  v2 = *((_QWORD *)PeekContext + 29);
  result = IoCsqRemoveNextIrp((PIO_CSQ)(PeekContext + 32), PeekContext);
  v8 = result;
  if ( result )
  {
    result->IoStatus.Status = a2;
    if ( *(_BYTE *)(v2 + 1362) )
    {
      CancelRemoteWakeNotificationIrp(PeekContext, result);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qqqd(*(_QWORD *)(v2 + 1368), v6, v7, 21);
      IofCompleteRequest(v8, 0);
      UsbcReleaseRemoveLock(v2, v8);
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 200), v8, 0x20u);
    }
    return (PIRP)CheckParentWaitWake(*((PVOID *)PeekContext + 29));
  }
  return result;
}

```

## disassembly

```asm
0x14000d81c  push    rbx
0x14000d81e  push    rbp
0x14000d81f  push    rsi
0x14000d820  push    rdi
0x14000d821  sub     rsp, 58h
0x14000d825  mov     rsi, [rcx+0E8h]
0x14000d82c  mov     rdi, rcx
0x14000d82f  mov     ebp, edx
0x14000d831  add     rcx, 20h ; ' '; Csq
0x14000d835  mov     rdx, rdi; PeekContext
0x14000d838  call    cs:__imp_IoCsqRemoveNextIrp
0x14000d83f  nop     dword ptr [rax+rax+00h]
0x14000d844  mov     rbx, rax
0x14000d847  test    rax, rax
0x14000d84a  jnz     short loc_14000D856
0x14000d84c  add     rsp, 58h
0x14000d850  pop     rdi
0x14000d851  pop     rsi
0x14000d852  pop     rbp
0x14000d853  pop     rbx
0x14000d854  retn
0x14000d856  mov     [rax+30h], ebp
0x14000d859  cmp     byte ptr [rsi+552h], 0
0x14000d860  jz      short loc_14000D86F
0x14000d862  mov     rdx, rbx
0x14000d865  mov     rcx, rdi
0x14000d868  call    CancelRemoteWakeNotificationIrp
0x14000d86d  jmp     short loc_14000D8E7
0x14000d86f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d876  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d87d  jz      short loc_14000D8AF
0x14000d87f  mov     rax, [rdi+0E0h]
0x14000d886  mov     r9d, 15h
0x14000d88c  mov     rcx, [rsi+558h]
0x14000d893  mov     [rsp+78h+var_38], ebp
0x14000d897  mov     [rsp+78h+var_40], rax
0x14000d89c  mov     rax, [rsi+20h]
0x14000d8a0  mov     [rsp+78h+var_48], rbx
0x14000d8a5  mov     [rsp+78h+var_50], rax
0x14000d8aa  call    WPP_RECORDER_SF_qqqd
0x14000d8af  xor     edx, edx; PriorityBoost
0x14000d8b1  mov     rcx, rbx; Irp
0x14000d8b4  call    cs:__imp_IofCompleteRequest
0x14000d8bb  nop     dword ptr [rax+rax+00h]
0x14000d8c0  mov     rdx, rbx
0x14000d8c3  mov     rcx, rsi
0x14000d8c6  call    UsbcReleaseRemoveLock
0x14000d8cb  lea     rcx, [rsi+0C8h]; RemoveLock
0x14000d8d2  mov     r8d, 20h ; ' '; RemlockSize
0x14000d8d8  mov     rdx, rbx; Tag
0x14000d8db  call    cs:__imp_IoReleaseRemoveLockEx
0x14000d8e2  nop     dword ptr [rax+rax+00h]
0x14000d8e7  mov     rcx, [rdi+0E8h]; Context
0x14000d8ee  call    CheckParentWaitWake
0x14000d8f3  jmp     loc_14000D84C
```
