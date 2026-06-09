# _DllMainCRTStartup

- ea: `0x180001aa0`
- end: `0x180001add`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001aa0`
- `0x180001ae4`
- `0x180001e14`

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
0x180001aa0  mov     [rsp+arg_0], rbx
0x180001aa5  mov     [rsp+arg_8], rsi
0x180001aaa  push    rdi
0x180001aab  sub     rsp, 20h
0x180001aaf  mov     rdi, r8
0x180001ab2  mov     ebx, edx
0x180001ab4  mov     rsi, rcx
0x180001ab7  cmp     edx, 1
0x180001aba  jnz     short loc_180001AC1
0x180001abc  call    __security_init_cookie
0x180001ac1  mov     r8, rdi
0x180001ac4  mov     edx, ebx; fdwReason
0x180001ac6  mov     rcx, rsi; hinstDLL
0x180001ac9  mov     rbx, [rsp+28h+arg_0]
0x180001ace  mov     rsi, [rsp+28h+arg_8]
0x180001ad3  add     rsp, 20h
0x180001ad7  pop     rdi
0x180001ad8  jmp     __DllMainCRTStartup
```
