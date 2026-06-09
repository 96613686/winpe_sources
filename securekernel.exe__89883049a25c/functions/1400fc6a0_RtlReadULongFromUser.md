# RtlReadULongFromUser

- ea: `0x1400fc6a0`
- end: `0x1400fc6d3`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `48`
- callee_count: `2`
- tags: ``

## callers

- `0x1400134f4`
- `0x1400280b0`
- `0x14003fcfc`
- `0x14003ffbc`
- `0x140040250`
- `0x1400406a4`
- `0x140040e04`
- `0x14004145c`
- `0x140041da8`
- `0x140041f2c`
- `0x140041ff4`
- `0x140042200`
- `0x140042940`
- `0x140042a44`
- `0x140042aa0`
- `0x140043038`
- `0x140043654`
- `0x14004453c`
- `0x1400445b8`
- `0x14004491c`
- `0x140060bd4`
- `0x140065654`
- `0x1400839bc`
- `0x1400883a4`
- `0x140089b8c`
- `0x14009c610`
- `0x1400ad508`
- `0x1400ae17c`
- `0x1400ae76c`
- `0x1400aed8c`
- `0x1400aeeec`
- `0x1400af7f8`
- `0x1400af910`
- `0x1400afa98`
- `0x1400afc7c`
- `0x1400afd58`
- `0x1400afe90`
- `0x1400b0bc0`
- `0x1400b17a4`
- `0x1400b23c0`
- `0x1400b2690`
- `0x1400b6c24`
- `0x1400bb42c`
- `0x1400bdb3c`
- `0x1400be910`
- `0x1400e1bf4`
- `0x1400fee4c`
- `0x140107060`

## callees

- `0x1400442ac`
- `0x1400fc6a0`

## pseudocode

```c
__int64 __fastcall RtlReadULongFromUser(unsigned int *a1)
{
  ProbeForRead(a1, 4u, 1u);
  return *a1;
}

```

## disassembly

```asm
0x1400fc6a0  push    rbx
0x1400fc6a2  sub     rsp, 20h
0x1400fc6a6  mov     rax, cs:qword_14010C428
0x1400fc6ad  mov     rbx, rcx
0x1400fc6b0  test    rax, rax
0x1400fc6b3  jz      short loc_1400FC6BC
0x1400fc6b5  call    rax ; qword_14010C428
0x1400fc6b7  nop     dword ptr [rax]
0x1400fc6ba  jmp     short loc_1400FC6CC
0x1400fc6bc  mov     edx, 4; Length
0x1400fc6c1  lea     r8d, [rdx-3]; Alignment
0x1400fc6c5  call    ProbeForRead
0x1400fc6ca  mov     eax, [rbx]
0x1400fc6cc  add     rsp, 20h
0x1400fc6d0  pop     rbx
0x1400fc6d1  retn
```
