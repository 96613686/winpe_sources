# _DllMainCRTStartup

- ea: `0x18000bea0`
- end: `0x18000bedd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000bea0`
- `0x18000bee4`
- `0x18000c444`

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
0x18000bea0  mov     [rsp+arg_0], rbx
0x18000bea5  mov     [rsp+arg_8], rsi
0x18000beaa  push    rdi
0x18000beab  sub     rsp, 20h
0x18000beaf  mov     rdi, r8
0x18000beb2  mov     ebx, edx
0x18000beb4  mov     rsi, rcx
0x18000beb7  cmp     edx, 1
0x18000beba  jnz     short loc_18000BEC1
0x18000bebc  call    __security_init_cookie
0x18000bec1  mov     r8, rdi
0x18000bec4  mov     edx, ebx; fdwReason
0x18000bec6  mov     rcx, rsi; hinstDLL
0x18000bec9  mov     rbx, [rsp+28h+arg_0]
0x18000bece  mov     rsi, [rsp+28h+arg_8]
0x18000bed3  add     rsp, 20h
0x18000bed7  pop     rdi
0x18000bed8  jmp     __DllMainCRTStartup
```
