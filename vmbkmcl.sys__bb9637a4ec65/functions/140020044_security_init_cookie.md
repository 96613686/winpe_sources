# __security_init_cookie

- ea: `0x140020044`
- end: `0x140020072`
- name: `__security_init_cookie`
- size: `46`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140020010`

## callees

- `0x140020044`

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
0x140020044  mov     rax, cs:__security_cookie
0x14002004b  test    rax, rax
0x14002004e  jz      short loc_14002006B
0x140020050  mov     rcx, 2B992DDFA232h
0x14002005a  cmp     rax, rcx
0x14002005d  jz      short loc_14002006B
0x14002005f  not     rax
0x140020062  mov     cs:__security_cookie_complement, rax
0x140020069  retn
0x14002006b  mov     ecx, 6
0x140020070  int     29h; Win8: RtlFailFast(ecx)
```
