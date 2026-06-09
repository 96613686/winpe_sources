# _DllMainCRTStartup

- ea: `0x180003830`
- end: `0x18000386d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003830`
- `0x180003874`
- `0x1800040a4`

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
0x180003830  mov     [rsp+arg_0], rbx
0x180003835  mov     [rsp+arg_8], rsi
0x18000383a  push    rdi
0x18000383b  sub     rsp, 20h
0x18000383f  mov     rdi, r8
0x180003842  mov     ebx, edx
0x180003844  mov     rsi, rcx
0x180003847  cmp     edx, 1
0x18000384a  jnz     short loc_180003851
0x18000384c  call    __security_init_cookie
0x180003851  mov     r8, rdi
0x180003854  mov     edx, ebx; fdwReason
0x180003856  mov     rcx, rsi; hinstDLL
0x180003859  mov     rbx, [rsp+28h+arg_0]
0x18000385e  mov     rsi, [rsp+28h+arg_8]
0x180003863  add     rsp, 20h
0x180003867  pop     rdi
0x180003868  jmp     __DllMainCRTStartup
```
