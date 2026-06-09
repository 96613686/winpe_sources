# ExitIrpThreadAndQueue

- ea: `0x140010020`
- end: `0x14001010c`
- name: `ExitIrpThreadAndQueue`
- size: `236`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400112c0`
- `0x140011354`

## callees

- `0x140010020`
- `0x140010114`
- `0x14001b15c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400100e9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400100e9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400100ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400100ac`
- `ntoskrnl!KeReleaseSemaphore` at `0x140010057`
- `ntoskrnl!KeReleaseSemaphore` at `0x140010057`

## pseudocode

```c
__int64 __fastcall ExitIrpThreadAndQueue(__int64 a1)
{
  __int64 result; // rax

  result = CleanupPendingIrpQ(a1);
  if ( *(_QWORD *)(a1 + 368) )
  {
    *(_BYTE *)(a1 + 356) = 1;
    KeReleaseSemaphore((PRKSEMAPHORE)(a1 + 608), 0, 1, 1u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, a1);
    KeWaitForSingleObject(*(PVOID *)(a1 + 368), Executive, 0, 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids, a1);
    result = ObfDereferenceObject(*(PVOID *)(a1 + 368));
    *(_QWORD *)(a1 + 368) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140010020  mov     [rsp+arg_0], rbx
0x140010025  push    rsi
0x140010026  sub     rsp, 30h
0x14001002a  mov     rbx, rcx
0x14001002d  call    CleanupPendingIrpQ
0x140010032  cmp     qword ptr [rbx+170h], 0
0x14001003a  jz      loc_140010100
0x140010040  xor     edx, edx; Increment
0x140010042  mov     byte ptr [rbx+164h], 1
0x140010049  lea     rcx, [rbx+260h]; Semaphore
0x140010050  mov     r9b, 1; Wait
0x140010053  lea     r8d, [rdx+1]; Adjustment
0x140010057  call    cs:__imp_KeReleaseSemaphore
0x14001005e  nop     dword ptr [rax+rax+00h]
0x140010063  mov     rcx, cs:WPP_GLOBAL_Control
0x14001006a  lea     rsi, WPP_GLOBAL_Control
0x140010071  cmp     rcx, rsi
0x140010074  jz      short loc_140010094
0x140010076  cmp     byte ptr [rcx+29h], 4
0x14001007a  jb      short loc_140010094
0x14001007c  mov     rcx, [rcx+18h]
0x140010080  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x140010087  mov     edx, 0Fh
0x14001008c  mov     r9, rbx
0x14001008f  call    WPP_SF_q
0x140010094  mov     rcx, [rbx+170h]; Object
0x14001009b  xor     r9d, r9d; Alertable
0x14001009e  xor     r8d, r8d; WaitMode
0x1400100a1  mov     [rsp+38h+Timeout], 0; Timeout
0x1400100aa  xor     edx, edx; WaitReason
0x1400100ac  call    cs:__imp_KeWaitForSingleObject
0x1400100b3  nop     dword ptr [rax+rax+00h]
0x1400100b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400100bf  cmp     rcx, rsi
0x1400100c2  jz      short loc_1400100E2
0x1400100c4  cmp     byte ptr [rcx+29h], 4
0x1400100c8  jb      short loc_1400100E2
0x1400100ca  mov     rcx, [rcx+18h]
0x1400100ce  lea     r8, WPP_09c2b4238c9a3e2e7be06e4e5c67ccea_Traceguids
0x1400100d5  mov     edx, 10h
0x1400100da  mov     r9, rbx
0x1400100dd  call    WPP_SF_q
0x1400100e2  mov     rcx, [rbx+170h]; Object
0x1400100e9  call    cs:__imp_ObfDereferenceObject
0x1400100f0  nop     dword ptr [rax+rax+00h]
0x1400100f5  mov     qword ptr [rbx+170h], 0
0x140010100  mov     rbx, [rsp+38h+arg_0]
0x140010105  add     rsp, 30h
0x140010109  pop     rsi
0x14001010a  retn
```
