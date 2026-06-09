# _DllMainCRTStartup

- ea: `0x180013850`
- end: `0x18001388d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180013850`
- `0x180013894`
- `0x180013bc4`

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
0x180013850  mov     [rsp+arg_0], rbx
0x180013855  mov     [rsp+arg_8], rsi
0x18001385a  push    rdi
0x18001385b  sub     rsp, 20h
0x18001385f  mov     rdi, r8
0x180013862  mov     ebx, edx
0x180013864  mov     rsi, rcx
0x180013867  cmp     edx, 1
0x18001386a  jnz     short loc_180013871
0x18001386c  call    __security_init_cookie
0x180013871  mov     r8, rdi
0x180013874  mov     edx, ebx; fdwReason
0x180013876  mov     rcx, rsi; hinstDLL
0x180013879  mov     rbx, [rsp+28h+arg_0]
0x18001387e  mov     rsi, [rsp+28h+arg_8]
0x180013883  add     rsp, 20h
0x180013887  pop     rdi
0x180013888  jmp     __DllMainCRTStartup
```
