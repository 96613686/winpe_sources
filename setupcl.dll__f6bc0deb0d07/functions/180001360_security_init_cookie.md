# __security_init_cookie

- ea: `0x180001360`
- end: `0x1800013a4`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800011a0`

## callees

- `0x180001360`
- `0x1800013ac`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
    _security_init_cookie_ex(&_security_cookie);
  _security_cookie_complement = ~_security_cookie;
}

```

## disassembly

```asm
0x180001360  sub     rsp, 28h
0x180001364  cmp     cs:__security_cookie, 0
0x18000136c  jz      short loc_180001381
0x18000136e  mov     rax, 2B992DDFA232h
0x180001378  cmp     cs:__security_cookie, rax
0x18000137f  jnz     short loc_18000138E
0x180001381  lea     rcx, __security_cookie
0x180001388  call    __security_init_cookie_ex
0x18000138d  nop
0x18000138e  mov     rax, cs:__security_cookie
0x180001395  not     rax
0x180001398  mov     cs:__security_cookie_complement, rax
0x18000139f  add     rsp, 28h
0x1800013a3  retn
```
