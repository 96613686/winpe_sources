# _DllMainCRTStartup

- ea: `0x180001790`
- end: `0x1800017cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001790`
- `0x1800017d4`
- `0x180001f44`

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
0x180001790  mov     [rsp+arg_0], rbx
0x180001795  mov     [rsp+arg_8], rsi
0x18000179a  push    rdi
0x18000179b  sub     rsp, 20h
0x18000179f  mov     rdi, r8
0x1800017a2  mov     ebx, edx
0x1800017a4  mov     rsi, rcx
0x1800017a7  cmp     edx, 1
0x1800017aa  jnz     short loc_1800017B1
0x1800017ac  call    __security_init_cookie
0x1800017b1  mov     r8, rdi
0x1800017b4  mov     edx, ebx; fdwReason
0x1800017b6  mov     rcx, rsi; hinstDLL
0x1800017b9  mov     rbx, [rsp+28h+arg_0]
0x1800017be  mov     rsi, [rsp+28h+arg_8]
0x1800017c3  add     rsp, 20h
0x1800017c7  pop     rdi
0x1800017c8  jmp     __DllMainCRTStartup
```
