# MTX_TTC_Create

- ea: `0x18001c574`
- end: `0x18001c5d3`
- name: `MTX_TTC_Create`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000de70`
- `0x18000e12c`

## callees

- `0x180006400`
- `0x18001c5dc`

## pseudocode

```c
__int64 __fastcall MTX_TTC_Create(__int64 a1, __int16 a2)
{
  __int64 v4; // rdi
  __int64 result; // rax

  v4 = MTX_mem_malloc(a1, 104);
  *(_QWORD *)(v4 + 96) = a1;
  InitCoordEncoding();
  *(_QWORD *)v4 = 0;
  *(_DWORD *)(v4 + 8) = 0;
  *(_QWORD *)(v4 + 32) = 0;
  *(_DWORD *)(v4 + 40) = 0;
  *(_QWORD *)(v4 + 48) = 0;
  *(_DWORD *)(v4 + 56) = 0;
  *(_QWORD *)(v4 + 64) = 0;
  *(_DWORD *)(v4 + 72) = 0;
  result = v4;
  *(_WORD *)(v4 + 88) = a2;
  return result;
}

```

## disassembly

```asm
0x18001c574  mov     [rsp+arg_0], rbx
0x18001c579  mov     [rsp+arg_8], rsi
0x18001c57e  push    rdi
0x18001c57f  sub     rsp, 20h
0x18001c583  movzx   esi, dx
0x18001c586  mov     rbx, rcx
0x18001c589  mov     edx, 68h ; 'h'
0x18001c58e  call    MTX_mem_malloc
0x18001c593  mov     rdi, rax
0x18001c596  mov     [rax+60h], rbx
0x18001c59a  call    InitCoordEncoding
0x18001c59f  mov     rbx, [rsp+28h+arg_0]
0x18001c5a4  xor     eax, eax
0x18001c5a6  mov     [rdi], rax
0x18001c5a9  mov     [rdi+8], eax
0x18001c5ac  mov     [rdi+20h], rax
0x18001c5b0  mov     [rdi+28h], eax
0x18001c5b3  mov     [rdi+30h], rax
0x18001c5b7  mov     [rdi+38h], eax
0x18001c5ba  mov     [rdi+40h], rax
0x18001c5be  mov     [rdi+48h], eax
0x18001c5c1  mov     rax, rdi
0x18001c5c4  mov     [rdi+58h], si
0x18001c5c8  mov     rsi, [rsp+28h+arg_8]
0x18001c5cd  add     rsp, 20h
0x18001c5d1  pop     rdi
0x18001c5d2  retn
```
