# MTX_BITIO_Create

- ea: `0x18000e788`
- end: `0x18000e7cb`
- name: `MTX_BITIO_Create`
- size: `67`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006548`
- `0x18000e2d4`

## callees

- `0x180006400`

## pseudocode

```c
__int64 __fastcall MTX_BITIO_Create(__int64 a1, __int64 a2, int a3, char a4)
{
  __int64 result; // rax

  result = MTX_mem_malloc(a1, 48);
  *(_QWORD *)(result + 40) = a1;
  *(_QWORD *)result = a2;
  *(_DWORD *)(result + 8) = 0;
  *(_DWORD *)(result + 12) = a3;
  *(_BYTE *)(result + 32) = a4;
  *(_QWORD *)(result + 16) = 0;
  *(_QWORD *)(result + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x18000e788  push    rbx
0x18000e78a  push    rbp
0x18000e78b  push    rsi
0x18000e78c  push    rdi
0x18000e78d  sub     rsp, 28h
0x18000e791  mov     rdi, rdx
0x18000e794  mov     bpl, r9b
0x18000e797  mov     edx, 30h ; '0'
0x18000e79c  mov     esi, r8d
0x18000e79f  mov     rbx, rcx
0x18000e7a2  call    MTX_mem_malloc
0x18000e7a7  xor     edx, edx
0x18000e7a9  mov     [rax+28h], rbx
0x18000e7ad  mov     [rax], rdi
0x18000e7b0  mov     [rax+8], edx
0x18000e7b3  mov     [rax+0Ch], esi
0x18000e7b6  mov     [rax+20h], bpl
0x18000e7ba  mov     [rax+10h], rdx
0x18000e7be  mov     [rax+18h], rdx
0x18000e7c2  add     rsp, 28h
0x18000e7c6  pop     rdi
0x18000e7c7  pop     rsi
0x18000e7c8  pop     rbp
0x18000e7c9  pop     rbx
0x18000e7ca  retn
```
