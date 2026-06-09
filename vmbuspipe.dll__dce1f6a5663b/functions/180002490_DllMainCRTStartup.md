# _DllMainCRTStartup

- ea: `0x180002490`
- end: `0x1800024cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002354`
- `0x180002490`
- `0x18000293c`

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
0x180002490  mov     [rsp+arg_0], rbx
0x180002495  mov     [rsp+arg_8], rsi
0x18000249a  push    rdi
0x18000249b  sub     rsp, 20h
0x18000249f  mov     rdi, r8
0x1800024a2  mov     ebx, edx
0x1800024a4  mov     rsi, rcx
0x1800024a7  cmp     edx, 1
0x1800024aa  jnz     short loc_1800024B1
0x1800024ac  call    __security_init_cookie
0x1800024b1  mov     r8, rdi; lpvReserved
0x1800024b4  mov     edx, ebx; fdwReason
0x1800024b6  mov     rcx, rsi; hinstDLL
0x1800024b9  mov     rbx, [rsp+28h+arg_0]
0x1800024be  mov     rsi, [rsp+28h+arg_8]
0x1800024c3  add     rsp, 20h
0x1800024c7  pop     rdi
0x1800024c8  jmp     dllmain_dispatch
```
