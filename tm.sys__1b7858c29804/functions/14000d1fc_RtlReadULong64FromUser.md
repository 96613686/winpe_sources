# RtlReadULong64FromUser

- ea: `0x14000d1fc`
- end: `0x14000d230`
- name: `RtlReadULong64FromUser`
- size: `52`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x140003030`
- `0x140012cb0`
- `0x140012d80`
- `0x140012e50`
- `0x140012ff0`
- `0x140013270`
- `0x1400133b0`
- `0x140013480`
- `0x1400135c0`
- `0x140013950`
- `0x140013ab0`
- `0x140013b80`
- `0x140013f20`
- `0x140013ff0`
- `0x140014480`
- `0x1400145d0`
- `0x140016b10`
- `0x140016c00`
- `0x1400172f0`
- `0x1400175d0`
- `0x140017e20`
- `0x140017fd0`
- `0x140019d10`
- `0x140020450`

## callees

- `0x1400014bf`
- `0x14000d1fc`

## pseudocode

```c
__int64 __fastcall RtlReadULong64FromUser(volatile void *a1)
{
  ProbeForRead_0(a1, 8u, 1u);
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x14000d1fc  push    rbx
0x14000d1fe  sub     rsp, 20h
0x14000d202  mov     rax, cs:qword_14000A4A8
0x14000d209  mov     rbx, rcx
0x14000d20c  test    rax, rax
0x14000d20f  jz      short loc_14000D218
0x14000d211  call    rax ; qword_14000A4A8
0x14000d213  nop     dword ptr [rax]
0x14000d216  jmp     short loc_14000D229
0x14000d218  mov     edx, 8; Length
0x14000d21d  lea     r8d, [rdx-7]; Alignment
0x14000d221  call    ProbeForRead_0
0x14000d226  mov     rax, [rbx]
0x14000d229  add     rsp, 20h
0x14000d22d  pop     rbx
0x14000d22e  retn
```
