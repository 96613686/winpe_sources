# _DllMainCRTStartup

- ea: `0x180001dc0`
- end: `0x180001dfd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180001e04`
- `0x180002654`

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
0x180001dc0  mov     [rsp+arg_0], rbx
0x180001dc5  mov     [rsp+arg_8], rsi
0x180001dca  push    rdi
0x180001dcb  sub     rsp, 20h
0x180001dcf  mov     rdi, r8
0x180001dd2  mov     ebx, edx
0x180001dd4  mov     rsi, rcx
0x180001dd7  cmp     edx, 1
0x180001dda  jnz     short loc_180001DE1
0x180001ddc  call    __security_init_cookie
0x180001de1  mov     r8, rdi
0x180001de4  mov     edx, ebx; fdwReason
0x180001de6  mov     rcx, rsi; hinstDLL
0x180001de9  mov     rbx, [rsp+28h+arg_0]
0x180001dee  mov     rsi, [rsp+28h+arg_8]
0x180001df3  add     rsp, 20h
0x180001df7  pop     rdi
0x180001df8  jmp     __DllMainCRTStartup
```
