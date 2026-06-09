# __security_init_cookie

- ea: `0x140001190`
- end: `0x1400011d4`
- name: `__security_init_cookie`
- size: `68`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400015f0`

## callees

- `0x140001190`
- `0x1400011dc`

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
0x140001190  sub     rsp, 28h
0x140001194  cmp     cs:__security_cookie, 0
0x14000119c  jz      short loc_1400011B1
0x14000119e  mov     rax, 2B992DDFA232h
0x1400011a8  cmp     cs:__security_cookie, rax
0x1400011af  jnz     short loc_1400011BE
0x1400011b1  lea     rcx, __security_cookie
0x1400011b8  call    __security_init_cookie_ex
0x1400011bd  nop
0x1400011be  mov     rax, cs:__security_cookie
0x1400011c5  not     rax
0x1400011c8  mov     cs:__security_cookie_complement, rax
0x1400011cf  add     rsp, 28h
0x1400011d3  retn
```
