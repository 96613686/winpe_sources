# __security_init_cookie

- ea: `0x140025364`
- end: `0x140025392`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140025330`

## callees

- `0x140025364`

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
0x140025364  mov     rax, cs:__security_cookie
0x14002536b  test    rax, rax
0x14002536e  jz      short loc_14002538B
0x140025370  mov     rcx, 2B992DDFA232h
0x14002537a  cmp     rax, rcx
0x14002537d  jz      short loc_14002538B
0x14002537f  not     rax
0x140025382  mov     cs:__security_cookie_complement, rax
0x140025389  retn
0x14002538b  mov     ecx, 6
0x140025390  int     29h; Win8: RtlFailFast(ecx)
```
