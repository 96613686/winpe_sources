# WaitWakeFinishCompletionWorker

- ea: `0x140014560`
- end: `0x1400145d7`
- name: `WaitWakeFinishCompletionWorker`
- size: `119`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140004b08`
- `0x1400083c8`
- `0x140013eb0`
- `0x140014560`

## pseudocode

```c
void __fastcall WaitWakeFinishCompletionWorker(char *Context)
{
  int v2; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      *((_QWORD *)Context + 171),
      4,
      3,
      25,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *((_QWORD *)Context + 4));
  if ( Context[1362] )
  {
    if ( *((_DWORD *)Context + 144) != 2 )
    {
      FinishWaitWakeCompletionForFunctionSuspend(Context);
      return;
    }
    v2 = -1073741536;
  }
  else
  {
    v2 = 0;
  }
  CompleteAllPdoWaitWakeIrps(Context, v2);
}

```

## disassembly

```asm
0x140014560  push    rbx
0x140014562  sub     rsp, 30h
0x140014566  mov     rbx, rcx
0x140014569  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140014570  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014577  jz      short loc_1400145A6
0x140014579  mov     rax, [rcx+20h]
0x14001457d  mov     r9d, 19h
0x140014583  mov     rcx, [rcx+558h]
0x14001458a  mov     dl, 4
0x14001458c  mov     [rsp+38h+var_10], rax
0x140014591  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140014598  mov     [rsp+38h+var_18], rax
0x14001459d  lea     r8d, [r9-16h]
0x1400145a1  call    WPP_RECORDER_SF_q
0x1400145a6  cmp     byte ptr [rbx+552h], 0
0x1400145ad  mov     rcx, rbx; Context
0x1400145b0  jz      short loc_1400145C9
0x1400145b2  cmp     dword ptr [rbx+240h], 2
0x1400145b9  jz      short loc_1400145C2
0x1400145bb  call    FinishWaitWakeCompletionForFunctionSuspend
0x1400145c0  jmp     short loc_1400145D0
0x1400145c2  mov     edx, 0C0000120h
0x1400145c7  jmp     short loc_1400145CB
0x1400145c9  xor     edx, edx
0x1400145cb  call    CompleteAllPdoWaitWakeIrps
0x1400145d0  add     rsp, 30h
0x1400145d4  pop     rbx
0x1400145d5  retn
```
