# CancelParentWaitWakeArg

- ea: `0x140009368`
- end: `0x140009448`
- name: `CancelParentWaitWakeArg`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008d58`
- `0x14000a6ac`

## callees

- `0x1400083c8`
- `0x140008eac`
- `0x140009368`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400093ba`
- `ntoskrnl!IofCompleteRequest` at `0x1400093ba`
- `ntoskrnl!IoCancelIrp` at `0x14000939a`
- `ntoskrnl!IoCancelIrp` at `0x14000939a`

## pseudocode

```c
void __fastcall CancelParentWaitWakeArg(__int64 a1, int a2)
{
  IRP *v3; // rdi

  if ( a2 )
  {
    v3 = (IRP *)_InterlockedExchange64((volatile __int64 *)(a1 + 376), 0);
    if ( v3 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a2) = 4;
        WPP_RECORDER_SF_qq(
          *(_QWORD *)(a1 + 1368),
          a2,
          3,
          31,
          (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
          *(_QWORD *)(a1 + 32),
          (char)v3);
      }
      IoCancelIrp(v3);
      if ( _InterlockedExchange((volatile __int32 *)(a1 + 396), 1) )
        IofCompleteRequest(v3, 0);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_q(
      *(_QWORD *)(a1 + 1368),
      a2,
      3,
      32,
      (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
      *(_QWORD *)(a1 + 32));
  }
}

```

## disassembly

```asm
0x140009368  mov     [rsp+arg_0], rbx
0x14000936d  push    rdi
0x14000936e  sub     rsp, 40h
0x140009372  mov     rbx, rcx
0x140009375  test    edx, edx
0x140009377  jz      short loc_1400093D2
0x140009379  xor     edi, edi
0x14000937b  xchg    rdi, [rcx+178h]
0x140009382  test    rdi, rdi
0x140009385  jz      short loc_1400093C6
0x140009387  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000938e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140009395  jnz     short loc_140009411
0x140009397  mov     rcx, rdi; Irp
0x14000939a  call    cs:__imp_IoCancelIrp
0x1400093a1  nop     dword ptr [rax+rax+00h]
0x1400093a6  mov     eax, 1
0x1400093ab  xchg    eax, [rbx+18Ch]
0x1400093b1  test    eax, eax
0x1400093b3  jz      short loc_1400093C6
0x1400093b5  xor     edx, edx; PriorityBoost
0x1400093b7  mov     rcx, rdi; Irp
0x1400093ba  call    cs:__imp_IofCompleteRequest
0x1400093c1  nop     dword ptr [rax+rax+00h]
0x1400093c6  mov     rbx, [rsp+48h+arg_0]
0x1400093cb  add     rsp, 40h
0x1400093cf  pop     rdi
0x1400093d0  retn
0x1400093d2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400093d9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400093e0  jz      short loc_1400093C6
0x1400093e2  mov     rax, [rcx+20h]
0x1400093e6  mov     r9d, 20h ; ' '
0x1400093ec  mov     rcx, [rcx+558h]
0x1400093f3  mov     dl, 4
0x1400093f5  mov     [rsp+48h+var_20], rax
0x1400093fa  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140009401  mov     [rsp+48h+var_28], rax
0x140009406  lea     r8d, [r9-1Dh]
0x14000940a  call    WPP_RECORDER_SF_q
0x14000940f  jmp     short loc_1400093C6
0x140009411  mov     rax, [rcx+20h]
0x140009415  mov     r9d, 1Fh
0x14000941b  mov     rcx, [rcx+558h]
0x140009422  mov     dl, 4
0x140009424  mov     [rsp+48h+var_18], rdi
0x140009429  mov     [rsp+48h+var_20], rax
0x14000942e  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140009435  lea     r8d, [r9-1Ch]
0x140009439  mov     [rsp+48h+var_28], rax
0x14000943e  call    WPP_RECORDER_SF_qq
0x140009443  jmp     loc_140009397
```
