# _DllMainCRTStartup

- ea: `0x1800019c0`
- end: `0x1800019fd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800019c0`
- `0x180001a04`
- `0x1800020b4`

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
0x1800019c0  mov     [rsp+arg_0], rbx
0x1800019c5  mov     [rsp+arg_8], rsi
0x1800019ca  push    rdi
0x1800019cb  sub     rsp, 20h
0x1800019cf  mov     rdi, r8
0x1800019d2  mov     ebx, edx
0x1800019d4  mov     rsi, rcx
0x1800019d7  cmp     edx, 1
0x1800019da  jnz     short loc_1800019E1
0x1800019dc  call    __security_init_cookie
0x1800019e1  mov     r8, rdi
0x1800019e4  mov     edx, ebx; fdwReason
0x1800019e6  mov     rcx, rsi; hinstDLL
0x1800019e9  mov     rbx, [rsp+28h+arg_0]
0x1800019ee  mov     rsi, [rsp+28h+arg_8]
0x1800019f3  add     rsp, 20h
0x1800019f7  pop     rdi
0x1800019f8  jmp     __DllMainCRTStartup
```
