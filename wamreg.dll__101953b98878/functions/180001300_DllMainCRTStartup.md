# _DllMainCRTStartup

- ea: `0x180001300`
- end: `0x18000133d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001300`
- `0x180001344`
- `0x180001914`

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
0x180001300  mov     [rsp+arg_0], rbx
0x180001305  mov     [rsp+arg_8], rsi
0x18000130a  push    rdi
0x18000130b  sub     rsp, 20h
0x18000130f  mov     rdi, r8
0x180001312  mov     ebx, edx
0x180001314  mov     rsi, rcx
0x180001317  cmp     edx, 1
0x18000131a  jnz     short loc_180001321
0x18000131c  call    __security_init_cookie
0x180001321  mov     r8, rdi
0x180001324  mov     edx, ebx; fdwReason
0x180001326  mov     rcx, rsi; hinstDLL
0x180001329  mov     rbx, [rsp+28h+arg_0]
0x18000132e  mov     rsi, [rsp+28h+arg_8]
0x180001333  add     rsp, 20h
0x180001337  pop     rdi
0x180001338  jmp     __DllMainCRTStartup
```
