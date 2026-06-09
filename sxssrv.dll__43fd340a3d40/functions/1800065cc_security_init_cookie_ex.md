# __security_init_cookie_ex

- ea: `0x1800065cc`
- end: `0x18000662a`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006580`

## callees

- `0x1800065cc`

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
0x1800065cc  mov     [rsp+arg_0], rcx
0x1800065d1  rdtsc
0x1800065d3  shl     rdx, 20h
0x1800065d7  or      rax, rdx
0x1800065da  shr     rax, 4
0x1800065de  xor     rax, [rsp+arg_0]
0x1800065e3  mov     rcx, 0FFFFFFFFFFFFh
0x1800065ed  and     rax, rcx
0x1800065f0  mov     rcx, [rsp+arg_0]
0x1800065f5  mov     [rcx], rax
0x1800065f8  mov     rax, [rsp+arg_0]
0x1800065fd  cmp     qword ptr [rax], 0
0x180006601  jz      short loc_180006617
0x180006603  mov     rax, [rsp+arg_0]
0x180006608  mov     rcx, 2B992DDFA232h
0x180006612  cmp     [rax], rcx
0x180006615  jnz     short locret_180006629
0x180006617  mov     rax, [rsp+arg_0]
0x18000661c  mov     rcx, 2B992DDFA233h
0x180006626  mov     [rax], rcx
0x180006629  retn
```
