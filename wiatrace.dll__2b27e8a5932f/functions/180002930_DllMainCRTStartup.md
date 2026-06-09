# _DllMainCRTStartup

- ea: `0x180002930`
- end: `0x18000296d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800027f4`
- `0x180002930`
- `0x1800029a4`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180002930  mov     [rsp+arg_0], rbx
0x180002935  mov     [rsp+arg_8], rsi
0x18000293a  push    rdi
0x18000293b  sub     rsp, 20h
0x18000293f  mov     rdi, r8
0x180002942  mov     ebx, edx
0x180002944  mov     rsi, rcx
0x180002947  cmp     edx, 1
0x18000294a  jnz     short loc_180002951
0x18000294c  call    __security_init_cookie
0x180002951  mov     r8, rdi; lpvReserved
0x180002954  mov     edx, ebx; fdwReason
0x180002956  mov     rcx, rsi; hinstDLL
0x180002959  mov     rbx, [rsp+28h+arg_0]
0x18000295e  mov     rsi, [rsp+28h+arg_8]
0x180002963  add     rsp, 20h
0x180002967  pop     rdi
0x180002968  jmp     dllmain_dispatch
```
