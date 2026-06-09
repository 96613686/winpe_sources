# SmLogFailureInt

- ea: `0x140003114`
- end: `0x14000319c`
- name: `SmLogFailureInt`
- size: `136`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x140001630`
- `0x1400027a0`
- `0x140002bb0`
- `0x1400031b0`
- `0x1400053e0`
- `0x140005ac4`
- `0x14000eb40`
- `0x14000fa74`
- `0x14000fed0`
- `0x1400151e0`
- `0x1400168b8`
- `0x140017e28`
- `0x140018154`

## callees

- `0x140005998`
- `0x14001cc29`
- `0x14001cc40`

## pseudocode

```c
__int64 __fastcall SmLogFailureInt(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, unsigned int a5)
{
  _BYTE v10[200]; // [rsp+20h] [rbp-108h] BYREF
  __int64 v11; // [rsp+E8h] [rbp-40h]
  __int64 v12; // [rsp+F0h] [rbp-38h]

  memset_0(v10, 0, 0xE0u);
  v11 = a3;
  v12 = a4;
  return SmpInternalLogFailure(a1, a2, a5, v10);
}

```

## disassembly

```asm
0x140003114  mov     [rsp+arg_8], rbx
0x140003119  push    rbp
0x14000311a  push    rsi
0x14000311b  push    rdi
0x14000311c  sub     rsp, 110h
0x140003123  mov     rax, cs:__security_cookie
0x14000312a  xor     rax, rsp
0x14000312d  mov     [rsp+128h+var_28], rax
0x140003135  mov     rbx, r8
0x140003138  mov     esi, edx
0x14000313a  mov     rbp, rcx
0x14000313d  xor     edx, edx; Val
0x14000313f  mov     r8d, 0E0h; Size
0x140003145  lea     rcx, [rsp+128h+var_108]; void *
0x14000314a  mov     rdi, r9
0x14000314d  call    memset_0
0x140003152  mov     r8d, [rsp+128h+arg_20]
0x14000315a  lea     r9, [rsp+128h+var_108]
0x14000315f  mov     edx, esi
0x140003161  mov     [rsp+128h+var_40], rbx
0x140003169  mov     rcx, rbp
0x14000316c  mov     [rsp+128h+var_38], rdi
0x140003174  call    SmpInternalLogFailure
0x140003179  mov     rcx, [rsp+128h+var_28]
0x140003181  xor     rcx, rsp; StackCookie
0x140003184  call    __security_check_cookie
0x140003189  mov     rbx, [rsp+128h+arg_8]
0x140003191  add     rsp, 110h
0x140003198  pop     rdi
0x140003199  pop     rsi
0x14000319a  pop     rbp
0x14000319b  retn
```
