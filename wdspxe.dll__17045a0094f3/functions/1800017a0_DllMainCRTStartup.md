# _DllMainCRTStartup

- ea: `0x1800017a0`
- end: `0x1800017dd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x1800017e4`
- `0x180001e04`

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
0x1800017a0  mov     [rsp+arg_0], rbx
0x1800017a5  mov     [rsp+arg_8], rsi
0x1800017aa  push    rdi
0x1800017ab  sub     rsp, 20h
0x1800017af  mov     rdi, r8
0x1800017b2  mov     ebx, edx
0x1800017b4  mov     rsi, rcx
0x1800017b7  cmp     edx, 1
0x1800017ba  jnz     short loc_1800017C1
0x1800017bc  call    __security_init_cookie
0x1800017c1  mov     r8, rdi
0x1800017c4  mov     edx, ebx; fdwReason
0x1800017c6  mov     rcx, rsi; hinstDLL
0x1800017c9  mov     rbx, [rsp+28h+arg_0]
0x1800017ce  mov     rsi, [rsp+28h+arg_8]
0x1800017d3  add     rsp, 20h
0x1800017d7  pop     rdi
0x1800017d8  jmp     __DllMainCRTStartup
```
