# OncRpcConnMgrpStandardSynchronousCompletionCallback

- ea: `0x1400066f0`
- end: `0x140006718`
- name: `OncRpcConnMgrpStandardSynchronousCompletionCallback`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140006706`
- `ntoskrnl!KeSetEvent` at `0x140006706`

## pseudocode

```c
LONG __fastcall OncRpcConnMgrpStandardSynchronousCompletionCallback(int a1, __int64 a2, __int64 a3)
{
  *(_DWORD *)a3 = a1;
  *(_QWORD *)(a3 + 8) = a2;
  return KeSetEvent((PRKEVENT)(a3 + 16), 2, 0);
}

```

## disassembly

```asm
0x1400066f0  sub     rsp, 28h
0x1400066f4  mov     [r8], ecx
0x1400066f7  lea     rcx, [r8+10h]; Event
0x1400066fb  mov     [r8+8], rdx
0x1400066ff  xor     r8d, r8d; Wait
0x140006702  lea     edx, [r8+2]; Increment
0x140006706  call    cs:__imp_KeSetEvent
0x14000670d  nop     dword ptr [rax+rax+00h]
0x140006712  add     rsp, 28h
0x140006716  retn
```
