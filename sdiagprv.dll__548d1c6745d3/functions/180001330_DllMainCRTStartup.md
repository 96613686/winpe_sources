# _DllMainCRTStartup

- ea: `0x180001330`
- end: `0x18000136d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001330`
- `0x180001374`
- `0x180001704`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180001330  mov     [rsp+arg_0], rbx
0x180001335  mov     [rsp+arg_8], rsi
0x18000133a  push    rdi
0x18000133b  sub     rsp, 20h
0x18000133f  mov     rdi, r8
0x180001342  mov     ebx, edx
0x180001344  mov     rsi, rcx
0x180001347  cmp     edx, 1
0x18000134a  jnz     short loc_180001351
0x18000134c  call    __security_init_cookie
0x180001351  mov     r8, rdi
0x180001354  mov     edx, ebx; fdwReason
0x180001356  mov     rcx, rsi; hinstDLL
0x180001359  mov     rbx, [rsp+28h+arg_0]
0x18000135e  mov     rsi, [rsp+28h+arg_8]
0x180001363  add     rsp, 20h
0x180001367  pop     rdi
0x180001368  jmp     __DllMainCRTStartup
```
