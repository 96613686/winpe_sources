# SafeSusComAllocArray(unsigned __int64,unsigned __int64)

- ea: `0x14000d598`
- end: `0x14000d5df`
- name: `?SafeSusComAllocArray@@YAPEAX_K0@Z`
- size: `71`
- prototype: `void *__fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000c980`

## callees

- `0x14000d4fc`
- `0x14000d598`
- `0x14001aa60`

## pseudocode

```c
void *__fastcall SafeSusComAllocArray(unsigned __int64 a1)
{
  if ( is_mul_ok(a1, 2u) )
    return SafeSusComAlloc(2 * a1);
  else
    return 0;
}

```

## disassembly

```asm
0x14000d598  sub     rsp, 38h
0x14000d59c  mov     rax, cs:__security_cookie
0x14000d5a3  xor     rax, rsp
0x14000d5a6  mov     [rsp+38h+var_10], rax
0x14000d5ab  mov     eax, 2
0x14000d5b0  mov     [rsp+38h+var_18], 0
0x14000d5b9  mul     rcx
0x14000d5bc  test    rdx, rdx
0x14000d5bf  jz      short loc_14000D5C5
0x14000d5c1  xor     eax, eax
0x14000d5c3  jmp     short loc_14000D5CD
0x14000d5c5  mov     rcx, rax; Size
0x14000d5c8  call    ?SafeSusComAlloc@@YAPEAX_KH@Z; SafeSusComAlloc(unsigned __int64,int)
0x14000d5cd  mov     rcx, [rsp+38h+var_10]
0x14000d5d2  xor     rcx, rsp; StackCookie
0x14000d5d5  call    __security_check_cookie
0x14000d5da  add     rsp, 38h
0x14000d5de  retn
```
