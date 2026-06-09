# __security_init_cookie

- ea: `0x14000eeb0`
- end: `0x14000eef4`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005be0`

## callees

- `0x14000eeb0`
- `0x14000eefc`

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
0x14000eeb0  sub     rsp, 28h
0x14000eeb4  cmp     cs:__security_cookie, 0
0x14000eebc  jz      short loc_14000EED1
0x14000eebe  mov     rax, 2B992DDFA232h
0x14000eec8  cmp     cs:__security_cookie, rax
0x14000eecf  jnz     short loc_14000EEDE
0x14000eed1  lea     rcx, __security_cookie
0x14000eed8  call    __security_init_cookie_ex
0x14000eedd  nop
0x14000eede  mov     rax, cs:__security_cookie
0x14000eee5  not     rax
0x14000eee8  mov     cs:__security_cookie_complement, rax
0x14000eeef  add     rsp, 28h
0x14000eef3  retn
```
