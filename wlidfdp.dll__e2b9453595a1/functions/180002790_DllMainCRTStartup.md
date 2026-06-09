# _DllMainCRTStartup

- ea: `0x180002790`
- end: `0x1800027cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002654`
- `0x180002790`
- `0x180002c94`

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
0x180002790  mov     [rsp+arg_0], rbx
0x180002795  mov     [rsp+arg_8], rsi
0x18000279a  push    rdi
0x18000279b  sub     rsp, 20h
0x18000279f  mov     rdi, r8
0x1800027a2  mov     ebx, edx
0x1800027a4  mov     rsi, rcx
0x1800027a7  cmp     edx, 1
0x1800027aa  jnz     short loc_1800027B1
0x1800027ac  call    __security_init_cookie
0x1800027b1  mov     r8, rdi; lpvReserved
0x1800027b4  mov     edx, ebx; fdwReason
0x1800027b6  mov     rcx, rsi; hinstDLL
0x1800027b9  mov     rbx, [rsp+28h+arg_0]
0x1800027be  mov     rsi, [rsp+28h+arg_8]
0x1800027c3  add     rsp, 20h
0x1800027c7  pop     rdi
0x1800027c8  jmp     dllmain_dispatch
```
