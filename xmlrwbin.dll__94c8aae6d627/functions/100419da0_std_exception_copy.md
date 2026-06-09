# __std_exception_copy

- ea: `0x100419da0`
- end: `0x100419e2d`
- name: `__std_exception_copy`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1004194f8`
- `0x100419560`

## callees

- `0x100419da0`
- `0x10041b118`
- `0x10041b130`
- `0x10041b13c`

## pseudocode

```c
void __fastcall _std_exception_copy(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  char *v5; // rax
  char *v6; // rbx

  if ( *(_BYTE *)(a1 + 8) && *(_QWORD *)a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_BYTE *)(*(_QWORD *)a1 + v4) );
    v5 = (char *)malloc(v4 + 1);
    v6 = v5;
    if ( v5 )
    {
      strcpy_s(v5, v4 + 1, *(const char **)a1);
      *(_BYTE *)(a2 + 8) = 1;
      *(_QWORD *)a2 = v6;
      v6 = 0;
    }
    free(v6);
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
0x100419da0  mov     [rsp+arg_0], rbx
0x100419da5  mov     [rsp+arg_8], rsi
0x100419daa  mov     [rsp+arg_10], rdi
0x100419daf  push    r14
0x100419db1  sub     rsp, 20h
0x100419db5  cmp     byte ptr [rcx+8], 0
0x100419db9  mov     r14, rdx
0x100419dbc  mov     rsi, rcx
0x100419dbf  jz      short loc_100419E0D
0x100419dc1  mov     rax, [rcx]
0x100419dc4  test    rax, rax
0x100419dc7  jz      short loc_100419E0D
0x100419dc9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x100419dcd  inc     rdi
0x100419dd0  cmp     byte ptr [rax+rdi], 0
0x100419dd4  jnz     short loc_100419DCD
0x100419dd6  lea     rcx, [rdi+1]; Size
0x100419dda  call    malloc
0x100419ddf  mov     rbx, rax
0x100419de2  test    rax, rax
0x100419de5  jz      short loc_100419E03
0x100419de7  mov     r8, [rsi]; Source
0x100419dea  lea     rdx, [rdi+1]; SizeInBytes
0x100419dee  mov     rcx, rax; Destination
0x100419df1  call    strcpy_s
0x100419df6  mov     rax, rbx
0x100419df9  mov     byte ptr [r14+8], 1
0x100419dfe  mov     [r14], rax
0x100419e01  xor     ebx, ebx
0x100419e03  mov     rcx, rbx; Block
0x100419e06  call    free
0x100419e0b  jmp     short loc_100419E17
0x100419e0d  mov     rax, [rcx]
0x100419e10  mov     [rdx], rax
0x100419e13  mov     byte ptr [rdx+8], 0
0x100419e17  mov     rbx, [rsp+28h+arg_0]
0x100419e1c  mov     rsi, [rsp+28h+arg_8]
0x100419e21  mov     rdi, [rsp+28h+arg_10]
0x100419e26  add     rsp, 20h
0x100419e2a  pop     r14
0x100419e2c  retn
```
