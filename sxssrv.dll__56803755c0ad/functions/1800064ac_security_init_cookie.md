# __security_init_cookie

- ea: `0x1800064ac`
- end: `0x1800064ef`
- name: `__security_init_cookie`
- size: `67`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800062f0`

## callees

- `0x1800064ac`
- `0x1800064f8`

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
0x1800064ac  sub     rsp, 28h
0x1800064b0  cmp     cs:__security_cookie, 0
0x1800064b8  jz      short loc_1800064CD
0x1800064ba  mov     rax, 2B992DDFA232h
0x1800064c4  cmp     cs:__security_cookie, rax
0x1800064cb  jnz     short loc_1800064D9
0x1800064cd  lea     rcx, __security_cookie
0x1800064d4  call    __security_init_cookie_ex
0x1800064d9  mov     rax, cs:__security_cookie
0x1800064e0  not     rax
0x1800064e3  mov     cs:__security_cookie_complement, rax
0x1800064ea  add     rsp, 28h
0x1800064ee  retn
```
