# _DllMainCRTStartup

- ea: `0x180001380`
- end: `0x1800013bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001380`
- `0x1800013c4`
- `0x1800016c4`

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
0x180001380  mov     [rsp+arg_0], rbx
0x180001385  mov     [rsp+arg_8], rsi
0x18000138a  push    rdi
0x18000138b  sub     rsp, 20h
0x18000138f  mov     rdi, r8
0x180001392  mov     ebx, edx
0x180001394  mov     rsi, rcx
0x180001397  cmp     edx, 1
0x18000139a  jnz     short loc_1800013A1
0x18000139c  call    __security_init_cookie
0x1800013a1  mov     r8, rdi
0x1800013a4  mov     edx, ebx; fdwReason
0x1800013a6  mov     rcx, rsi; hinstDLL
0x1800013a9  mov     rbx, [rsp+28h+arg_0]
0x1800013ae  mov     rsi, [rsp+28h+arg_8]
0x1800013b3  add     rsp, 20h
0x1800013b7  pop     rdi
0x1800013b8  jmp     __DllMainCRTStartup
```
