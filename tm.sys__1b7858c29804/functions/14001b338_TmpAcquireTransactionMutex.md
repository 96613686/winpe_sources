# TmpAcquireTransactionMutex

- ea: `0x14001b338`
- end: `0x14001b388`
- name: `TmpAcquireTransactionMutex`
- size: `80`
- prototype: ``
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c718`
- `0x14000c9ac`
- `0x14000cccc`
- `0x14000fed0`
- `0x140010140`
- `0x140010220`
- `0x140010330`
- `0x140010500`
- `0x1400106c0`
- `0x140010c10`
- `0x140010c70`
- `0x14001102c`
- `0x1400110f4`
- `0x140011228`
- `0x1400114ac`
- `0x14001189c`
- `0x140013c50`
- `0x140016110`
- `0x1400161c0`
- `0x140016680`
- `0x140016f40`
- `0x140019460`
- `0x14001a000`
- `0x14001a2e0`
- `0x14001aa8c`
- `0x14001ab8c`
- `0x14001e120`
- `0x140020250`

## callees

- `0x14001b338`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001b357`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b357`
- `ntoskrnl!KeReleaseMutex` at `0x14001b376`
- `ntoskrnl!KeReleaseMutex` at `0x14001b376`

## pseudocode

```c
NTSTATUS __fastcall TmpAcquireTransactionMutex(__int64 a1)
{
  __int64 i; // rbx
  NTSTATUS result; // eax

  for ( i = *(_QWORD *)(a1 + 88); ; i = *(_QWORD *)(i + 88) )
  {
    result = KeWaitForSingleObject((PVOID)(i + 32), Executive, 0, 0, 0);
    if ( *(_QWORD *)(i + 88) == i )
      break;
    KeReleaseMutex((PRKMUTEX)(i + 32), 0);
  }
  return result;
}

```

## disassembly

```asm
0x14001b338  push    rbx
0x14001b33a  sub     rsp, 30h
0x14001b33e  mov     rbx, [rcx+58h]
0x14001b342  xor     r9d, r9d; Alertable
0x14001b345  mov     [rsp+38h+Timeout], 0; Timeout
0x14001b34e  xor     r8d, r8d; WaitMode
0x14001b351  lea     rcx, [rbx+20h]; Object
0x14001b355  xor     edx, edx; WaitReason
0x14001b357  call    cs:__imp_KeWaitForSingleObject
0x14001b35e  nop     dword ptr [rax+rax+00h]
0x14001b363  cmp     [rbx+58h], rbx
0x14001b367  jnz     short loc_14001B370
0x14001b369  add     rsp, 30h
0x14001b36d  pop     rbx
0x14001b36e  retn
0x14001b370  lea     rcx, [rbx+20h]; Mutex
0x14001b374  xor     edx, edx; Wait
0x14001b376  call    cs:__imp_KeReleaseMutex
0x14001b37d  nop     dword ptr [rax+rax+00h]
0x14001b382  mov     rbx, [rbx+58h]
0x14001b386  jmp     short loc_14001B342
```
