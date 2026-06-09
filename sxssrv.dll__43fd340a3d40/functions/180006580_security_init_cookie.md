# __security_init_cookie

- ea: `0x180006580`
- end: `0x1800065c4`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800063c0`

## callees

- `0x180006580`
- `0x1800065cc`

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
0x180006580  sub     rsp, 28h
0x180006584  cmp     cs:__security_cookie, 0
0x18000658c  jz      short loc_1800065A1
0x18000658e  mov     rax, 2B992DDFA232h
0x180006598  cmp     cs:__security_cookie, rax
0x18000659f  jnz     short loc_1800065AE
0x1800065a1  lea     rcx, __security_cookie
0x1800065a8  call    __security_init_cookie_ex
0x1800065ad  nop
0x1800065ae  mov     rax, cs:__security_cookie
0x1800065b5  not     rax
0x1800065b8  mov     cs:__security_cookie_complement, rax
0x1800065bf  add     rsp, 28h
0x1800065c3  retn
```
