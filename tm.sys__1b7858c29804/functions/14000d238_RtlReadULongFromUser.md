# RtlReadULongFromUser

- ea: `0x14000d238`
- end: `0x14000d26b`
- name: `RtlReadULongFromUser`
- size: `51`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140003040`
- `0x140013690`
- `0x140013ff0`
- `0x140014480`
- `0x1400147e0`
- `0x1400168d0`
- `0x1400172f0`
- `0x1400175d0`
- `0x140017950`
- `0x140017e20`
- `0x14001e120`
- `0x140020450`

## callees

- `0x1400014bf`
- `0x14000d238`

## pseudocode

```c
__int64 __fastcall RtlReadULongFromUser(unsigned int *a1)
{
  ProbeForRead_0(a1, 4u, 1u);
  return *a1;
}

```

## disassembly

```asm
0x14000d238  push    rbx
0x14000d23a  sub     rsp, 20h
0x14000d23e  mov     rax, cs:qword_14000A498
0x14000d245  mov     rbx, rcx
0x14000d248  test    rax, rax
0x14000d24b  jz      short loc_14000D254
0x14000d24d  call    rax ; qword_14000A498
0x14000d24f  nop     dword ptr [rax]
0x14000d252  jmp     short loc_14000D264
0x14000d254  mov     edx, 4; Length
0x14000d259  lea     r8d, [rdx-3]; Alignment
0x14000d25d  call    ProbeForRead_0
0x14000d262  mov     eax, [rbx]
0x14000d264  add     rsp, 20h
0x14000d268  pop     rbx
0x14000d269  retn
```
