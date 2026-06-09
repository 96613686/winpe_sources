# RtlReadUShortFromUser

- ea: `0x1400fc6dc`
- end: `0x1400fc710`
- name: `RtlReadUShortFromUser`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400280b0`
- `0x140041878`
- `0x140041da8`
- `0x140041f2c`
- `0x1400aeeec`
- `0x1400af1cc`
- `0x1400fee4c`
- `0x140107070`

## callees

- `0x1400442ac`
- `0x1400fc6dc`

## pseudocode

```c
__int64 __fastcall RtlReadUShortFromUser(unsigned __int16 *a1)
{
  ProbeForRead(a1, 2u, 1u);
  return *a1;
}

```

## disassembly

```asm
0x1400fc6dc  push    rbx
0x1400fc6de  sub     rsp, 20h
0x1400fc6e2  mov     rax, cs:qword_14010C418
0x1400fc6e9  mov     rbx, rcx
0x1400fc6ec  test    rax, rax
0x1400fc6ef  jz      short loc_1400FC6F8
0x1400fc6f1  call    rax ; qword_14010C418
0x1400fc6f3  nop     dword ptr [rax]
0x1400fc6f6  jmp     short loc_1400FC709
0x1400fc6f8  mov     edx, 2; Length
0x1400fc6fd  lea     r8d, [rdx-1]; Alignment
0x1400fc701  call    ProbeForRead
0x1400fc706  movzx   eax, word ptr [rbx]
0x1400fc709  add     rsp, 20h
0x1400fc70d  pop     rbx
0x1400fc70e  retn
```
