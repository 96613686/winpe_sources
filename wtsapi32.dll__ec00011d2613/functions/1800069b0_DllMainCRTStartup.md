# _DllMainCRTStartup

- ea: `0x1800069b0`
- end: `0x1800069ed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800069b0`
- `0x1800069f4`
- `0x180006ef0`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup((__int64)hinstDLL, fdwReason, (__int64)lpReserved);
}

```

## disassembly

```asm
0x1800069b0  mov     [rsp+arg_0], rbx
0x1800069b5  mov     [rsp+arg_8], rsi
0x1800069ba  push    rdi
0x1800069bb  sub     rsp, 20h
0x1800069bf  mov     rdi, r8
0x1800069c2  mov     ebx, edx
0x1800069c4  mov     rsi, rcx
0x1800069c7  cmp     edx, 1
0x1800069ca  jnz     short loc_1800069D1
0x1800069cc  call    __security_init_cookie
0x1800069d1  mov     r8, rdi
0x1800069d4  mov     edx, ebx
0x1800069d6  mov     rcx, rsi
0x1800069d9  mov     rbx, [rsp+28h+arg_0]
0x1800069de  mov     rsi, [rsp+28h+arg_8]
0x1800069e3  add     rsp, 20h
0x1800069e7  pop     rdi
0x1800069e8  jmp     __DllMainCRTStartup
```
