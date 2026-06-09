# __security_init_cookie_ex

- ea: `0x1800013ac`
- end: `0x18000140a`
- name: `__security_init_cookie_ex`
- size: `94`
- prototype: `unsigned __int64 *__fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001360`

## callees

- `0x1800013ac`

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
0x1800013ac  mov     [rsp+arg_0], rcx
0x1800013b1  rdtsc
0x1800013b3  shl     rdx, 20h
0x1800013b7  or      rax, rdx
0x1800013ba  shr     rax, 4
0x1800013be  xor     rax, [rsp+arg_0]
0x1800013c3  mov     rcx, 0FFFFFFFFFFFFh
0x1800013cd  and     rax, rcx
0x1800013d0  mov     rcx, [rsp+arg_0]
0x1800013d5  mov     [rcx], rax
0x1800013d8  mov     rax, [rsp+arg_0]
0x1800013dd  cmp     qword ptr [rax], 0
0x1800013e1  jz      short loc_1800013F7
0x1800013e3  mov     rax, [rsp+arg_0]
0x1800013e8  mov     rcx, 2B992DDFA232h
0x1800013f2  cmp     [rax], rcx
0x1800013f5  jnz     short locret_180001409
0x1800013f7  mov     rax, [rsp+arg_0]
0x1800013fc  mov     rcx, 2B992DDFA233h
0x180001406  mov     [rax], rcx
0x180001409  retn
```
