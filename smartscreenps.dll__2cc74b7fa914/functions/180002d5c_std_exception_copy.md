# __std_exception_copy

- ea: `0x180002d5c`
- end: `0x180002dcb`
- name: `__std_exception_copy`
- size: `111`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180001ed0`
- `0x180001f3c`
- `0x1800055fc`
- `0x180007518`

## callees

- `0x180002d5c`
- `0x18000691a`
- `0x180006932`
- `0x18000694a`

## pseudocode

```c
void __fastcall _std_exception_copy(__int64 a1, __int64 a2)
{
  const char *v4; // rcx
  __int64 v5; // rax
  rsize_t v6; // rbp
  char *v7; // rax
  char *v8; // rsi

  if ( *(_BYTE *)(a1 + 8) && (v4 = *(const char **)a1) != 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    v6 = v5 + 1;
    v7 = (char *)malloc_0(v5 + 1);
    v8 = v7;
    if ( v7 )
    {
      strcpy_s_0(v7, v6, *(const char **)a1);
      *(_QWORD *)a2 = v8;
      *(_BYTE *)(a2 + 8) = 1;
    }
    free_0(0);
  }
  else
  {
    *(_QWORD *)a2 = *(_QWORD *)a1;
    *(_BYTE *)(a2 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180002d5c  push    rbx
0x180002d5e  push    rbp
0x180002d5f  push    rsi
0x180002d60  push    rdi
0x180002d61  sub     rsp, 28h
0x180002d65  cmp     byte ptr [rcx+8], 0
0x180002d69  mov     rdi, rdx
0x180002d6c  mov     rbx, rcx
0x180002d6f  jz      short loc_180002DB8
0x180002d71  mov     rcx, [rcx]
0x180002d74  test    rcx, rcx
0x180002d77  jz      short loc_180002DB8
0x180002d79  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002d7d  inc     rax
0x180002d80  cmp     byte ptr [rcx+rax], 0
0x180002d84  jnz     short loc_180002D7D
0x180002d86  lea     rbp, [rax+1]
0x180002d8a  mov     rcx, rbp; Size
0x180002d8d  call    malloc_0
0x180002d92  mov     rsi, rax
0x180002d95  test    rax, rax
0x180002d98  jz      short loc_180002DAF
0x180002d9a  mov     r8, [rbx]; Source
0x180002d9d  mov     rdx, rbp; SizeInBytes
0x180002da0  mov     rcx, rax; Destination
0x180002da3  call    strcpy_s_0
0x180002da8  mov     [rdi], rsi
0x180002dab  mov     byte ptr [rdi+8], 1
0x180002daf  xor     ecx, ecx; Block
0x180002db1  call    free_0
0x180002db6  jmp     short loc_180002DC2
0x180002db8  mov     rax, [rbx]
0x180002dbb  mov     [rdx], rax
0x180002dbe  mov     byte ptr [rdx+8], 0
0x180002dc2  add     rsp, 28h
0x180002dc6  pop     rdi
0x180002dc7  pop     rsi
0x180002dc8  pop     rbp
0x180002dc9  pop     rbx
0x180002dca  retn
```
