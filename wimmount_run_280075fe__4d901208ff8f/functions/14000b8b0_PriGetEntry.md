# PriGetEntry

- ea: `0x14000b8b0`
- end: `0x14000b8fa`
- name: `PriGetEntry`
- size: `74`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140009f60`
- `0x14000a880`
- `0x14000b938`
- `0x14000b9bc`

## callees

- `0x140002c90`
- `0x14000b8b0`

## pseudocode

```c
PVOID *__fastcall PriGetEntry(unsigned __int8 (__fastcall *a1)(PVOID *, __int64), __int64 a2)
{
  PVOID *i; // rbx

  for ( i = (PVOID *)g_CommList; ; i = (PVOID *)*i )
  {
    if ( i == &g_CommList )
      return 0;
    if ( a1(i, a2) )
      break;
  }
  return i;
}

```

## disassembly

```asm
0x14000b8b0  push    rbx
0x14000b8b2  push    rbp
0x14000b8b3  push    rsi
0x14000b8b4  push    rdi
0x14000b8b5  sub     rsp, 28h
0x14000b8b9  mov     rbx, cs:g_CommList
0x14000b8c0  lea     rbp, g_CommList
0x14000b8c7  mov     rdi, rdx
0x14000b8ca  mov     rsi, rcx
0x14000b8cd  jmp     short loc_14000B8E4
0x14000b8cf  mov     rdx, rdi
0x14000b8d2  mov     rcx, rbx
0x14000b8d5  mov     rax, rsi
0x14000b8d8  call    _guard_dispatch_icall
0x14000b8dd  test    al, al
0x14000b8df  jnz     short loc_14000B8F5
0x14000b8e1  mov     rbx, [rbx]
0x14000b8e4  cmp     rbx, rbp
0x14000b8e7  jnz     short loc_14000B8CF
0x14000b8e9  xor     eax, eax
0x14000b8eb  add     rsp, 28h
0x14000b8ef  pop     rdi
0x14000b8f0  pop     rsi
0x14000b8f1  pop     rbp
0x14000b8f2  pop     rbx
0x14000b8f3  retn
0x14000b8f5  mov     rax, rbx
0x14000b8f8  jmp     short loc_14000B8EB
```
