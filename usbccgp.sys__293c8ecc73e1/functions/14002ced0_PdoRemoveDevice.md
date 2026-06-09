# PdoRemoveDevice

- ea: `0x14002ced0`
- end: `0x14002cf9d`
- name: `PdoRemoveDevice`
- size: `205`
- prototype: `__int64 __fastcall(PVOID PeekContext)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140010650`

## callees

- `0x140006430`
- `0x140006f58`
- `0x140007b3c`
- `0x1400083c8`
- `0x14000d81c`
- `0x140014060`
- `0x14002ced0`

## pseudocode

```c
__int64 __fastcall PdoRemoveDevice(_QWORD *PeekContext)
{
  __int64 v1; // rdi

  v1 = PeekContext[29];
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      PeekContext[49],
      4,
      2,
      40,
      (__int64)WPP_54beca300c4a353e079921b0991edb26_Traceguids,
      PeekContext[28]);
  *((_DWORD *)PeekContext + 6) = *((_DWORD *)PeekContext + 5);
  *((_DWORD *)PeekContext + 5) = 8;
  CompleteFunctionIdleIrp((char *)PeekContext, -1073741536);
  CompletePdoWaitWakeIrp((char *)PeekContext, -1073741536);
  if ( *((_DWORD *)PeekContext + 6) != 9 )
  {
    if ( *(_BYTE *)(v1 + 1362) )
      LockSyncSendSetFeatureControlRequestForFunctionSuspend(v1, PeekContext, 0);
    SetPdoIdle(v1, (__int64)PeekContext, 1, 1u, 1);
    ResumeIdleTimer(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x14002ced0  mov     [rsp+arg_0], rbx
0x14002ced5  push    rdi
0x14002ced6  sub     rsp, 30h
0x14002ceda  mov     rdi, [rcx+0E8h]
0x14002cee1  mov     rbx, rcx
0x14002cee4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002ceeb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002cef2  jnz     short loc_14002CF2F
0x14002cef4  mov     eax, [rbx+14h]
0x14002cef7  mov     edx, 0C0000120h
0x14002cefc  mov     rcx, rbx; PeekContext
0x14002ceff  mov     [rbx+18h], eax
0x14002cf02  mov     dword ptr [rbx+14h], 8
0x14002cf09  call    CompleteFunctionIdleIrp
0x14002cf0e  mov     edx, 0C0000120h
0x14002cf13  mov     rcx, rbx; PeekContext
0x14002cf16  call    CompletePdoWaitWakeIrp
0x14002cf1b  cmp     dword ptr [rbx+18h], 9
0x14002cf1f  jnz     short loc_14002CF61
0x14002cf21  mov     rbx, [rsp+38h+arg_0]
0x14002cf26  xor     eax, eax
0x14002cf28  add     rsp, 30h
0x14002cf2c  pop     rdi
0x14002cf2d  retn
0x14002cf2f  mov     rax, [rcx+0E0h]
0x14002cf36  mov     r9d, 28h ; '('
0x14002cf3c  mov     rcx, [rcx+188h]
0x14002cf43  mov     dl, 4
0x14002cf45  mov     [rsp+38h+var_10], rax
0x14002cf4a  lea     rax, WPP_54beca300c4a353e079921b0991edb26_Traceguids
0x14002cf51  mov     [rsp+38h+var_18], rax
0x14002cf56  lea     r8d, [r9-26h]
0x14002cf5a  call    WPP_RECORDER_SF_q
0x14002cf5f  jmp     short loc_14002CEF4
0x14002cf61  cmp     byte ptr [rdi+552h], 0
0x14002cf68  jnz     short loc_14002CF8D
0x14002cf6a  mov     r9b, 1
0x14002cf6d  mov     byte ptr [rsp+38h+var_18], 1
0x14002cf72  mov     r8d, 1
0x14002cf78  mov     rdx, rbx
0x14002cf7b  mov     rcx, rdi
0x14002cf7e  call    SetPdoIdle
0x14002cf83  mov     rcx, rdi
0x14002cf86  call    ResumeIdleTimer
0x14002cf8b  jmp     short loc_14002CF21
0x14002cf8d  xor     r8d, r8d
0x14002cf90  mov     rdx, rbx
0x14002cf93  mov     rcx, rdi
0x14002cf96  call    LockSyncSendSetFeatureControlRequestForFunctionSuspend
0x14002cf9b  jmp     short loc_14002CF6A
```
