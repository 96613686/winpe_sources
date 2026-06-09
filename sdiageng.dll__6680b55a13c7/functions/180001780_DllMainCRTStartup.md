# _DllMainCRTStartup

- ea: `0x180001780`
- end: `0x1800017bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001780`
- `0x1800017c4`
- `0x180001de4`

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
0x180001780  mov     [rsp+arg_0], rbx
0x180001785  mov     [rsp+arg_8], rsi
0x18000178a  push    rdi
0x18000178b  sub     rsp, 20h
0x18000178f  mov     rdi, r8
0x180001792  mov     ebx, edx
0x180001794  mov     rsi, rcx
0x180001797  cmp     edx, 1
0x18000179a  jnz     short loc_1800017A1
0x18000179c  call    __security_init_cookie
0x1800017a1  mov     r8, rdi
0x1800017a4  mov     edx, ebx; fdwReason
0x1800017a6  mov     rcx, rsi; hinstDLL
0x1800017a9  mov     rbx, [rsp+28h+arg_0]
0x1800017ae  mov     rsi, [rsp+28h+arg_8]
0x1800017b3  add     rsp, 20h
0x1800017b7  pop     rdi
0x1800017b8  jmp     __DllMainCRTStartup
```
