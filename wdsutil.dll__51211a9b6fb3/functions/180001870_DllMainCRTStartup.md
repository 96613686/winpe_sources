# _DllMainCRTStartup

- ea: `0x180001870`
- end: `0x1800018ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001870`
- `0x1800018b4`
- `0x180001ea4`

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
0x180001870  mov     [rsp+arg_0], rbx
0x180001875  mov     [rsp+arg_8], rsi
0x18000187a  push    rdi
0x18000187b  sub     rsp, 20h
0x18000187f  mov     rdi, r8
0x180001882  mov     ebx, edx
0x180001884  mov     rsi, rcx
0x180001887  cmp     edx, 1
0x18000188a  jnz     short loc_180001891
0x18000188c  call    __security_init_cookie
0x180001891  mov     r8, rdi
0x180001894  mov     edx, ebx; fdwReason
0x180001896  mov     rcx, rsi; hinstDLL
0x180001899  mov     rbx, [rsp+28h+arg_0]
0x18000189e  mov     rsi, [rsp+28h+arg_8]
0x1800018a3  add     rsp, 20h
0x1800018a7  pop     rdi
0x1800018a8  jmp     __DllMainCRTStartup
```
