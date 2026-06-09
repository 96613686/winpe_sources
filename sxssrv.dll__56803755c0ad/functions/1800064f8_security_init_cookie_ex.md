# __security_init_cookie_ex

- ea: `0x1800064f8`
- end: `0x180006556`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: `unsigned __int64 *__fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800064ac`

## callees

- `0x1800064f8`

## pseudocode

```c
unsigned __int64 *__fastcall _security_init_cookie_ex(unsigned __int64 *a1)
{
  unsigned __int64 v1; // rax
  unsigned __int64 *result; // rax

  v1 = __rdtsc();
  *a1 = ((unsigned __int64)a1 ^ ((((unsigned __int64)HIDWORD(v1) << 32) | (unsigned int)v1) >> 4)) & 0xFFFFFFFFFFFFLL;
  if ( !*a1 || (result = a1, *a1 == 0x2B992DDFA232LL) )
  {
    result = a1;
    *a1 = 0x2B992DDFA233LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800064f8  mov     [rsp+arg_0], rcx
0x1800064fd  rdtsc
0x1800064ff  shl     rdx, 20h
0x180006503  or      rax, rdx
0x180006506  shr     rax, 4
0x18000650a  xor     rax, [rsp+arg_0]
0x18000650f  mov     rcx, 0FFFFFFFFFFFFh
0x180006519  and     rax, rcx
0x18000651c  mov     rcx, [rsp+arg_0]
0x180006521  mov     [rcx], rax
0x180006524  mov     rax, [rsp+arg_0]
0x180006529  cmp     qword ptr [rax], 0
0x18000652d  jz      short loc_180006543
0x18000652f  mov     rax, [rsp+arg_0]
0x180006534  mov     rcx, 2B992DDFA232h
0x18000653e  cmp     [rax], rcx
0x180006541  jnz     short locret_180006555
0x180006543  mov     rax, [rsp+arg_0]
0x180006548  mov     rcx, 2B992DDFA233h
0x180006552  mov     [rax], rcx
0x180006555  retn
```
