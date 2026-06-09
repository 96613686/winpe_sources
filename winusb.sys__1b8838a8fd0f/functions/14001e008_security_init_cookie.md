# __security_init_cookie

- ea: `0x14001e008`
- end: `0x14001e036`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140010100`

## callees

- `0x14001e008`

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
0x14001e008  mov     rax, cs:__security_cookie
0x14001e00f  test    rax, rax
0x14001e012  jz      short loc_14001E02F
0x14001e014  mov     rcx, 2B992DDFA232h
0x14001e01e  cmp     rax, rcx
0x14001e021  jz      short loc_14001E02F
0x14001e023  not     rax
0x14001e026  mov     cs:__security_cookie_complement, rax
0x14001e02d  retn
0x14001e02f  mov     ecx, 6
0x14001e034  int     29h; Win8: RtlFailFast(ecx)
```
