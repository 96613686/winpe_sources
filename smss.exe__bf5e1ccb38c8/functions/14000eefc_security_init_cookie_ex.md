# __security_init_cookie_ex

- ea: `0x14000eefc`
- end: `0x14000ef5a`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000eeb0`

## callees

- `0x14000eefc`

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
0x14000eefc  mov     [rsp+arg_0], rcx
0x14000ef01  rdtsc
0x14000ef03  shl     rdx, 20h
0x14000ef07  or      rax, rdx
0x14000ef0a  shr     rax, 4
0x14000ef0e  xor     rax, [rsp+arg_0]
0x14000ef13  mov     rcx, 0FFFFFFFFFFFFh
0x14000ef1d  and     rax, rcx
0x14000ef20  mov     rcx, [rsp+arg_0]
0x14000ef25  mov     [rcx], rax
0x14000ef28  mov     rax, [rsp+arg_0]
0x14000ef2d  cmp     qword ptr [rax], 0
0x14000ef31  jz      short loc_14000EF47
0x14000ef33  mov     rax, [rsp+arg_0]
0x14000ef38  mov     rcx, 2B992DDFA232h
0x14000ef42  cmp     [rax], rcx
0x14000ef45  jnz     short locret_14000EF59
0x14000ef47  mov     rax, [rsp+arg_0]
0x14000ef4c  mov     rcx, 2B992DDFA233h
0x14000ef56  mov     [rax], rcx
0x14000ef59  retn
```
