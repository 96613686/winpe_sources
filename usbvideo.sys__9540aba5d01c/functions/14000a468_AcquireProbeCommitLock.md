# AcquireProbeCommitLock

- ea: `0x14000a468`
- end: `0x14000a4ad`
- name: `AcquireProbeCommitLock`
- size: `69`
- prototype: ``
- caller_count: `13`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140009f34`
- `0x14000b260`
- `0x140023934`
- `0x14002b340`
- `0x14002b5a0`
- `0x14002b690`
- `0x14002b7f0`
- `0x14002b8e0`
- `0x14002ba30`
- `0x14002bb20`
- `0x14002bc80`
- `0x14002bd60`
- `0x1400394cc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000a48e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a48e`

## pseudocode

```c
NTSTATUS __fastcall AcquireProbeCommitLock(__int64 a1)
{
  void *v1; // rcx
  NTSTATUS result; // eax
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(void **)(a1 + 424);
  Timeout.QuadPart = -5000000;
  result = KeWaitForSingleObject(v1, Executive, 0, 0, &Timeout);
  if ( result == 258 )
    return -1073741823;
  return result;
}

```

## disassembly

```asm
0x14000a468  sub     rsp, 38h
0x14000a46c  mov     rcx, [rcx+1A8h]; Object
0x14000a473  lea     rax, [rsp+38h+arg_0]
0x14000a478  xor     r9d, r9d; Alertable
0x14000a47b  mov     [rsp+38h+Timeout], rax; Timeout
0x14000a480  xor     r8d, r8d; WaitMode
0x14000a483  mov     qword ptr [rsp+38h+arg_0], 0FFFFFFFFFFB3B4C0h
0x14000a48c  xor     edx, edx; WaitReason
0x14000a48e  call    cs:__imp_KeWaitForSingleObject
0x14000a495  nop     dword ptr [rax+rax+00h]
0x14000a49a  cmp     eax, 102h
0x14000a49f  mov     ecx, 0C0000001h
0x14000a4a4  cmovz   eax, ecx
0x14000a4a7  add     rsp, 38h
0x14000a4ab  retn
```
