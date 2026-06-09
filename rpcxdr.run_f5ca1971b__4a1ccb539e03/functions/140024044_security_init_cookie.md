# __security_init_cookie

- ea: `0x140024044`
- end: `0x140024072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140024010`

## callees

- `0x140024044`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
    __fastfail(6u);
  _security_cookie_complement = ~_security_cookie;
}

```

## disassembly

```asm
0x140024044  mov     rax, cs:__security_cookie
0x14002404b  test    rax, rax
0x14002404e  jz      short loc_14002406B
0x140024050  mov     rcx, 2B992DDFA232h
0x14002405a  cmp     rax, rcx
0x14002405d  jz      short loc_14002406B
0x14002405f  not     rax
0x140024062  mov     cs:__security_cookie_complement, rax
0x140024069  retn
0x14002406b  mov     ecx, 6
0x140024070  int     29h; Win8: RtlFailFast(ecx)
```
