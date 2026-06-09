# _DllMainCRTStartup

- ea: `0x180001620`
- end: `0x18000165d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001620`
- `0x180001664`
- `0x180001994`

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
0x180001620  mov     [rsp+arg_0], rbx
0x180001625  mov     [rsp+arg_8], rsi
0x18000162a  push    rdi
0x18000162b  sub     rsp, 20h
0x18000162f  mov     rdi, r8
0x180001632  mov     ebx, edx
0x180001634  mov     rsi, rcx
0x180001637  cmp     edx, 1
0x18000163a  jnz     short loc_180001641
0x18000163c  call    __security_init_cookie
0x180001641  mov     r8, rdi
0x180001644  mov     edx, ebx; fdwReason
0x180001646  mov     rcx, rsi; hinstDLL
0x180001649  mov     rbx, [rsp+28h+arg_0]
0x18000164e  mov     rsi, [rsp+28h+arg_8]
0x180001653  add     rsp, 20h
0x180001657  pop     rdi
0x180001658  jmp     __DllMainCRTStartup
```
