# __std_exception_copy

- ea: `0x100429d30`
- end: `0x100429dbd`
- name: `__std_exception_copy`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x10042948c`
- `0x1004294f4`

## callees

- `0x100429d30`
- `0x10042b0a8`
- `0x10042b0c0`
- `0x10042b0cc`

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
0x100429d30  mov     [rsp+arg_0], rbx
0x100429d35  mov     [rsp+arg_8], rsi
0x100429d3a  mov     [rsp+arg_10], rdi
0x100429d3f  push    r14
0x100429d41  sub     rsp, 20h
0x100429d45  cmp     byte ptr [rcx+8], 0
0x100429d49  mov     r14, rdx
0x100429d4c  mov     rsi, rcx
0x100429d4f  jz      short loc_100429D9D
0x100429d51  mov     rax, [rcx]
0x100429d54  test    rax, rax
0x100429d57  jz      short loc_100429D9D
0x100429d59  or      rdi, 0FFFFFFFFFFFFFFFFh
0x100429d5d  inc     rdi
0x100429d60  cmp     byte ptr [rax+rdi], 0
0x100429d64  jnz     short loc_100429D5D
0x100429d66  lea     rcx, [rdi+1]; Size
0x100429d6a  call    malloc
0x100429d6f  mov     rbx, rax
0x100429d72  test    rax, rax
0x100429d75  jz      short loc_100429D93
0x100429d77  mov     r8, [rsi]; Source
0x100429d7a  lea     rdx, [rdi+1]; SizeInBytes
0x100429d7e  mov     rcx, rax; Destination
0x100429d81  call    strcpy_s
0x100429d86  mov     rax, rbx
0x100429d89  mov     byte ptr [r14+8], 1
0x100429d8e  mov     [r14], rax
0x100429d91  xor     ebx, ebx
0x100429d93  mov     rcx, rbx; Block
0x100429d96  call    free
0x100429d9b  jmp     short loc_100429DA7
0x100429d9d  mov     rax, [rcx]
0x100429da0  mov     [rdx], rax
0x100429da3  mov     byte ptr [rdx+8], 0
0x100429da7  mov     rbx, [rsp+28h+arg_0]
0x100429dac  mov     rsi, [rsp+28h+arg_8]
0x100429db1  mov     rdi, [rsp+28h+arg_10]
0x100429db6  add     rsp, 20h
0x100429dba  pop     r14
0x100429dbc  retn
```
