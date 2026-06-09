# _DllMainCRTStartup

- ea: `0x180001490`
- end: `0x1800014cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001354`
- `0x180001490`
- `0x180001520`

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
0x180001490  mov     [rsp+arg_0], rbx
0x180001495  mov     [rsp+arg_8], rsi
0x18000149a  push    rdi
0x18000149b  sub     rsp, 20h
0x18000149f  mov     rdi, r8
0x1800014a2  mov     ebx, edx
0x1800014a4  mov     rsi, rcx
0x1800014a7  cmp     edx, 1
0x1800014aa  jnz     short loc_1800014B1
0x1800014ac  call    __security_init_cookie
0x1800014b1  mov     r8, rdi; lpvReserved
0x1800014b4  mov     edx, ebx; fdwReason
0x1800014b6  mov     rcx, rsi; hinstDLL
0x1800014b9  mov     rbx, [rsp+28h+arg_0]
0x1800014be  mov     rsi, [rsp+28h+arg_8]
0x1800014c3  add     rsp, 20h
0x1800014c7  pop     rdi
0x1800014c8  jmp     dllmain_dispatch
```
