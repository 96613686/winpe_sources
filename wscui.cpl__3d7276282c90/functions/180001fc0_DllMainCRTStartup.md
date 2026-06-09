# _DllMainCRTStartup

- ea: `0x180001fc0`
- end: `0x180001ffd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001fc0`
- `0x180002004`
- `0x180002944`

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
0x180001fc0  mov     [rsp+arg_0], rbx
0x180001fc5  mov     [rsp+arg_8], rsi
0x180001fca  push    rdi
0x180001fcb  sub     rsp, 20h
0x180001fcf  mov     rdi, r8
0x180001fd2  mov     ebx, edx
0x180001fd4  mov     rsi, rcx
0x180001fd7  cmp     edx, 1
0x180001fda  jnz     short loc_180001FE1
0x180001fdc  call    __security_init_cookie
0x180001fe1  mov     r8, rdi
0x180001fe4  mov     edx, ebx; fdwReason
0x180001fe6  mov     rcx, rsi; hinstDLL
0x180001fe9  mov     rbx, [rsp+28h+arg_0]
0x180001fee  mov     rsi, [rsp+28h+arg_8]
0x180001ff3  add     rsp, 20h
0x180001ff7  pop     rdi
0x180001ff8  jmp     __DllMainCRTStartup
```
