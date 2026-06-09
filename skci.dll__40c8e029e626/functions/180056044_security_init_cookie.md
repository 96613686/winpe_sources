# __security_init_cookie

- ea: `0x180056044`
- end: `0x180056072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180056010`

## callees

- `0x180056044`

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
0x180056044  mov     rax, cs:__security_cookie
0x18005604b  test    rax, rax
0x18005604e  jz      short loc_18005606B
0x180056050  mov     rcx, 2B992DDFA232h
0x18005605a  cmp     rax, rcx
0x18005605d  jz      short loc_18005606B
0x18005605f  not     rax
0x180056062  mov     cs:__security_cookie_complement, rax
0x180056069  retn
0x18005606b  mov     ecx, 6
0x180056070  int     29h; Win8: RtlFailFast(ecx)
```
