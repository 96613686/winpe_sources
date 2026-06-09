# BusChGpadlCreated

- ea: `0x140007140`
- end: `0x14000716a`
- name: `BusChGpadlCreated`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140007140`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140007158`
- `ntoskrnl!KeSetEvent` at `0x140007158`

## pseudocode

```c
LONG __fastcall BusChGpadlCreated(int a1, int a2, __int64 a3)
{
  *(_DWORD *)a3 = a1;
  if ( a1 >= 0 )
    *(_DWORD *)(a3 + 32) = a2;
  return KeSetEvent((PRKEVENT)(a3 + 8), 0, 0);
}

```

## disassembly

```asm
0x140007140  sub     rsp, 28h
0x140007144  mov     [r8], ecx
0x140007147  test    ecx, ecx
0x140007149  js      short loc_14000714F
0x14000714b  mov     [r8+20h], edx
0x14000714f  lea     rcx, [r8+8]; Event
0x140007153  xor     edx, edx; Increment
0x140007155  xor     r8d, r8d; Wait
0x140007158  call    cs:__imp_KeSetEvent
0x14000715f  nop     dword ptr [rax+rax+00h]
0x140007164  add     rsp, 28h
0x140007168  retn
```
