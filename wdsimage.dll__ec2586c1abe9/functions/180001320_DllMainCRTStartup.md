# _DllMainCRTStartup

- ea: `0x180001320`
- end: `0x18000135d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001320`
- `0x180001364`
- `0x1800017a4`

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
0x180001320  mov     [rsp+arg_0], rbx
0x180001325  mov     [rsp+arg_8], rsi
0x18000132a  push    rdi
0x18000132b  sub     rsp, 20h
0x18000132f  mov     rdi, r8
0x180001332  mov     ebx, edx
0x180001334  mov     rsi, rcx
0x180001337  cmp     edx, 1
0x18000133a  jnz     short loc_180001341
0x18000133c  call    __security_init_cookie
0x180001341  mov     r8, rdi
0x180001344  mov     edx, ebx; fdwReason
0x180001346  mov     rcx, rsi; hinstDLL
0x180001349  mov     rbx, [rsp+28h+arg_0]
0x18000134e  mov     rsi, [rsp+28h+arg_8]
0x180001353  add     rsp, 20h
0x180001357  pop     rdi
0x180001358  jmp     __DllMainCRTStartup
```
