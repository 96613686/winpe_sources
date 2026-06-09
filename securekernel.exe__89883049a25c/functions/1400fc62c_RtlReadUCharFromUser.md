# RtlReadUCharFromUser

- ea: `0x1400fc62c`
- end: `0x1400fc65e`
- name: `RtlReadUCharFromUser`
- size: `50`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140041b84`
- `0x140041f2c`
- `0x1400442ec`
- `0x14006ad64`
- `0x1400aeeec`
- `0x1400e04c8`
- `0x1400e1000`
- `0x140107040`

## callees

- `0x1400442ac`
- `0x1400fc62c`

## pseudocode

```c
char __fastcall RtlReadUCharFromUser(volatile void *a1)
{
  ProbeForRead(a1, 1u, 1u);
  return *(_BYTE *)a1;
}

```

## disassembly

```asm
0x1400fc62c  push    rbx
0x1400fc62e  sub     rsp, 20h
0x1400fc632  mov     rax, cs:qword_14010C408
0x1400fc639  mov     rbx, rcx
0x1400fc63c  test    rax, rax
0x1400fc63f  jz      short loc_1400FC648
0x1400fc641  call    rax ; qword_14010C408
0x1400fc643  nop     dword ptr [rax]
0x1400fc646  jmp     short loc_1400FC657
0x1400fc648  mov     edx, 1; Length
0x1400fc64d  mov     r8d, edx; Alignment
0x1400fc650  call    ProbeForRead
0x1400fc655  mov     al, [rbx]
0x1400fc657  add     rsp, 20h
0x1400fc65b  pop     rbx
0x1400fc65c  retn
```
