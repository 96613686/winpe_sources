# __security_init_cookie

- ea: `0x14000d008`
- end: `0x14000d036`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004210`

## callees

- `0x14000d008`

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
0x14000d008  mov     rax, cs:__security_cookie
0x14000d00f  test    rax, rax
0x14000d012  jz      short loc_14000D02F
0x14000d014  mov     rcx, 2B992DDFA232h
0x14000d01e  cmp     rax, rcx
0x14000d021  jz      short loc_14000D02F
0x14000d023  not     rax
0x14000d026  mov     cs:__security_cookie_complement, rax
0x14000d02d  retn
0x14000d02f  mov     ecx, 6
0x14000d034  int     29h; Win8: RtlFailFast(ecx)
```
