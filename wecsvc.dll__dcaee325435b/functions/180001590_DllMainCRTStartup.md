# _DllMainCRTStartup

- ea: `0x180001590`
- end: `0x1800015cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001590`
- `0x1800015d4`
- `0x180001a84`

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
0x180001590  mov     [rsp+arg_0], rbx
0x180001595  mov     [rsp+arg_8], rsi
0x18000159a  push    rdi
0x18000159b  sub     rsp, 20h
0x18000159f  mov     rdi, r8
0x1800015a2  mov     ebx, edx
0x1800015a4  mov     rsi, rcx
0x1800015a7  cmp     edx, 1
0x1800015aa  jnz     short loc_1800015B1
0x1800015ac  call    __security_init_cookie
0x1800015b1  mov     r8, rdi
0x1800015b4  mov     edx, ebx; fdwReason
0x1800015b6  mov     rcx, rsi; hinstDLL
0x1800015b9  mov     rbx, [rsp+28h+arg_0]
0x1800015be  mov     rsi, [rsp+28h+arg_8]
0x1800015c3  add     rsp, 20h
0x1800015c7  pop     rdi
0x1800015c8  jmp     __DllMainCRTStartup
```
