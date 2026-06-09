# RtlSetUserMemory

- ea: `0x14001443c`
- end: `0x140014496`
- name: `RtlSetUserMemory`
- size: `90`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140009040`
- `0x140015a70`
- `0x140015dc4`
- `0x140016734`
- `0x140016aa8`
- `0x14001771c`
- `0x14001a364`
- `0x140031e40`

## callees

- `0x14000403f`
- `0x140007cb0`
- `0x14001443c`

## pseudocode

```c
void *__fastcall RtlSetUserMemory(void *a1, unsigned __int8 a2, SIZE_T a3)
{
  int v4; // esi

  v4 = a2;
  ProbeForRead_0(a1, a3, 1u);
  return RtlSetVolatileMemory(a1, v4, a3);
}

```

## disassembly

```asm
0x14001443c  mov     [rsp+arg_0], rbx
0x140014441  mov     [rsp+arg_8], rsi
0x140014446  push    rdi
0x140014447  sub     rsp, 20h
0x14001444b  mov     rax, cs:qword_1400117D0
0x140014452  mov     rbx, r8
0x140014455  movzx   esi, dl
0x140014458  mov     rdi, rcx
0x14001445b  test    rax, rax
0x14001445e  jz      short loc_14001446A
0x140014460  mov     dl, sil
0x140014463  call    rax ; qword_1400117D0
0x140014465  nop     dword ptr [rax]
0x140014468  jmp     short loc_140014485
0x14001446a  mov     r8d, 1; Alignment
0x140014470  mov     rdx, rbx; Length
0x140014473  call    ProbeForRead_0
0x140014478  mov     edx, esi; Val
0x14001447a  mov     r8, rbx; Size
0x14001447d  mov     rcx, rdi; void *
0x140014480  call    RtlSetVolatileMemory
0x140014485  mov     rbx, [rsp+28h+arg_0]
0x14001448a  mov     rsi, [rsp+28h+arg_8]
0x14001448f  add     rsp, 20h
0x140014493  pop     rdi
0x140014494  retn
```
