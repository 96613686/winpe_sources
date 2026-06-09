# _DllMainCRTStartup

- ea: `0x180002350`
- end: `0x18000238d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002350`
- `0x180002394`
- `0x1800026d4`

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
0x180002350  mov     [rsp+arg_0], rbx
0x180002355  mov     [rsp+arg_8], rsi
0x18000235a  push    rdi
0x18000235b  sub     rsp, 20h
0x18000235f  mov     rdi, r8
0x180002362  mov     ebx, edx
0x180002364  mov     rsi, rcx
0x180002367  cmp     edx, 1
0x18000236a  jnz     short loc_180002371
0x18000236c  call    __security_init_cookie
0x180002371  mov     r8, rdi
0x180002374  mov     edx, ebx; fdwReason
0x180002376  mov     rcx, rsi; hinstDLL
0x180002379  mov     rbx, [rsp+28h+arg_0]
0x18000237e  mov     rsi, [rsp+28h+arg_8]
0x180002383  add     rsp, 20h
0x180002387  pop     rdi
0x180002388  jmp     __DllMainCRTStartup
```
