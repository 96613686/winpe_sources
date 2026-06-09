# __std_exception_copy

- ea: `0x140005450`
- end: `0x1400054ce`
- name: `__std_exception_copy`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140004554`
- `0x1400045c0`

## callees

- `0x140005450`
- `0x1400055f2`
- `0x1400056d6`
- `0x1400056e2`
- `0x1400056ee`

## pseudocode

```c
void __fastcall _std_exception_copy(__int64 a1, __int64 a2)
{
  const char *v4; // rcx
  size_t v5; // rbp
  char *v6; // rsi
  char *v7; // rcx

  if ( *(_BYTE *)(a1 + 8) && (v4 = *(const char **)a1) != 0 )
  {
    v5 = strlen_0(v4) + 1;
    v6 = (char *)o_malloc_0(v5);
    v7 = v6;
    if ( v6 )
    {
      strcpy_s(v6, v5, *(const char **)a1);
      v7 = 0;
      *(_QWORD *)a2 = v6;
      *(_BYTE *)(a2 + 8) = 1;
    }
    free(v7);
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
0x140005450  mov     [rsp+arg_0], rbx
0x140005455  mov     [rsp+arg_8], rbp
0x14000545a  mov     [rsp+arg_10], rsi
0x14000545f  push    rdi
0x140005460  sub     rsp, 20h
0x140005464  cmp     byte ptr [rcx+8], 0
0x140005468  mov     rdi, rdx
0x14000546b  mov     rbx, rcx
0x14000546e  jz      short loc_1400054AF
0x140005470  mov     rcx, [rcx]; Str
0x140005473  test    rcx, rcx
0x140005476  jz      short loc_1400054AF
0x140005478  call    strlen_0
0x14000547d  lea     rbp, [rax+1]
0x140005481  mov     rcx, rbp; Size
0x140005484  call    _o_malloc_0
0x140005489  mov     rsi, rax
0x14000548c  mov     rcx, rax; Destination
0x14000548f  test    rax, rax
0x140005492  jz      short loc_1400054A8
0x140005494  mov     r8, [rbx]; Source
0x140005497  mov     rdx, rbp; SizeInBytes
0x14000549a  call    strcpy_s
0x14000549f  xor     ecx, ecx; Block
0x1400054a1  mov     [rdi], rsi
0x1400054a4  mov     byte ptr [rdi+8], 1
0x1400054a8  call    free
0x1400054ad  jmp     short loc_1400054B9
0x1400054af  mov     rax, [rbx]
0x1400054b2  mov     [rdx], rax
0x1400054b5  mov     byte ptr [rdx+8], 0
0x1400054b9  mov     rbx, [rsp+28h+arg_0]
0x1400054be  mov     rbp, [rsp+28h+arg_8]
0x1400054c3  mov     rsi, [rsp+28h+arg_10]
0x1400054c8  add     rsp, 20h
0x1400054cc  pop     rdi
0x1400054cd  retn
```
