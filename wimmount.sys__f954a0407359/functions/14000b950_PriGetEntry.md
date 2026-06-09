# PriGetEntry

- ea: `0x14000b950`
- end: `0x14000b99a`
- name: `PriGetEntry`
- size: `74`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140009f60`
- `0x14000a920`
- `0x14000b9d8`
- `0x14000ba5c`

## callees

- `0x140002c90`
- `0x14000b950`

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
0x14000b950  push    rbx
0x14000b952  push    rbp
0x14000b953  push    rsi
0x14000b954  push    rdi
0x14000b955  sub     rsp, 28h
0x14000b959  mov     rbx, cs:g_CommList
0x14000b960  lea     rbp, g_CommList
0x14000b967  mov     rdi, rdx
0x14000b96a  mov     rsi, rcx
0x14000b96d  jmp     short loc_14000B984
0x14000b96f  mov     rdx, rdi
0x14000b972  mov     rcx, rbx
0x14000b975  mov     rax, rsi
0x14000b978  call    _guard_dispatch_icall
0x14000b97d  test    al, al
0x14000b97f  jnz     short loc_14000B995
0x14000b981  mov     rbx, [rbx]
0x14000b984  cmp     rbx, rbp
0x14000b987  jnz     short loc_14000B96F
0x14000b989  xor     eax, eax
0x14000b98b  add     rsp, 28h
0x14000b98f  pop     rdi
0x14000b990  pop     rsi
0x14000b991  pop     rbp
0x14000b992  pop     rbx
0x14000b993  retn
0x14000b995  mov     rax, rbx
0x14000b998  jmp     short loc_14000B98B
```
