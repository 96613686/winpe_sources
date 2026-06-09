# __security_init_cookie_ex

- ea: `0x1400011dc`
- end: `0x14000123a`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: `unsigned __int64 *__fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001190`

## callees

- `0x1400011dc`

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
0x1400011dc  mov     [rsp+arg_0], rcx
0x1400011e1  rdtsc
0x1400011e3  shl     rdx, 20h
0x1400011e7  or      rax, rdx
0x1400011ea  shr     rax, 4
0x1400011ee  xor     rax, [rsp+arg_0]
0x1400011f3  mov     rcx, 0FFFFFFFFFFFFh
0x1400011fd  and     rax, rcx
0x140001200  mov     rcx, [rsp+arg_0]
0x140001205  mov     [rcx], rax
0x140001208  mov     rax, [rsp+arg_0]
0x14000120d  cmp     qword ptr [rax], 0
0x140001211  jz      short loc_140001227
0x140001213  mov     rax, [rsp+arg_0]
0x140001218  mov     rcx, 2B992DDFA232h
0x140001222  cmp     [rax], rcx
0x140001225  jnz     short locret_140001239
0x140001227  mov     rax, [rsp+arg_0]
0x14000122c  mov     rcx, 2B992DDFA233h
0x140001236  mov     [rax], rcx
0x140001239  retn
```
