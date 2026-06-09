# _DllMainCRTStartup

- ea: `0x180001370`
- end: `0x1800013ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001370`
- `0x1800013b4`
- `0x1800017c4`

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
0x180001370  mov     [rsp+arg_0], rbx
0x180001375  mov     [rsp+arg_8], rsi
0x18000137a  push    rdi
0x18000137b  sub     rsp, 20h
0x18000137f  mov     rdi, r8
0x180001382  mov     ebx, edx
0x180001384  mov     rsi, rcx
0x180001387  cmp     edx, 1
0x18000138a  jnz     short loc_180001391
0x18000138c  call    __security_init_cookie
0x180001391  mov     r8, rdi
0x180001394  mov     edx, ebx; fdwReason
0x180001396  mov     rcx, rsi; hinstDLL
0x180001399  mov     rbx, [rsp+28h+arg_0]
0x18000139e  mov     rsi, [rsp+28h+arg_8]
0x1800013a3  add     rsp, 20h
0x1800013a7  pop     rdi
0x1800013a8  jmp     __DllMainCRTStartup
```
