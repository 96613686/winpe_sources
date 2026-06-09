# _DllMainCRTStartup

- ea: `0x18000ddb0`
- end: `0x18000dded`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ddb0`
- `0x18000ddf4`
- `0x18000e454`

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
0x18000ddb0  mov     [rsp+arg_0], rbx
0x18000ddb5  mov     [rsp+arg_8], rsi
0x18000ddba  push    rdi
0x18000ddbb  sub     rsp, 20h
0x18000ddbf  mov     rdi, r8
0x18000ddc2  mov     ebx, edx
0x18000ddc4  mov     rsi, rcx
0x18000ddc7  cmp     edx, 1
0x18000ddca  jnz     short loc_18000DDD1
0x18000ddcc  call    __security_init_cookie
0x18000ddd1  mov     r8, rdi
0x18000ddd4  mov     edx, ebx; fdwReason
0x18000ddd6  mov     rcx, rsi; hinstDLL
0x18000ddd9  mov     rbx, [rsp+28h+arg_0]
0x18000ddde  mov     rsi, [rsp+28h+arg_8]
0x18000dde3  add     rsp, 20h
0x18000dde7  pop     rdi
0x18000dde8  jmp     __DllMainCRTStartup
```
