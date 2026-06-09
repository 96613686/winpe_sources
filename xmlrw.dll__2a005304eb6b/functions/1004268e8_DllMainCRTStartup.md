# _DllMainCRTStartup

- ea: `0x1004268e8`
- end: `0x100426925`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1004011b0`

## callees

- `0x1004267b0`
- `0x1004268e8`
- `0x100426bf4`

## pseudocode

```c
__int64 __fastcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpvReserved);
}

```

## disassembly

```asm
0x1004268e8  mov     [rsp+arg_0], rbx
0x1004268ed  mov     [rsp+arg_8], rsi
0x1004268f2  push    rdi
0x1004268f3  sub     rsp, 20h
0x1004268f7  mov     rdi, r8
0x1004268fa  mov     ebx, edx
0x1004268fc  mov     rsi, rcx
0x1004268ff  cmp     edx, 1
0x100426902  jnz     short loc_100426909
0x100426904  call    __security_init_cookie
0x100426909  mov     r8, rdi; lpvReserved
0x10042690c  mov     edx, ebx; fdwReason
0x10042690e  mov     rcx, rsi; hinstDLL
0x100426911  mov     rbx, [rsp+28h+arg_0]
0x100426916  mov     rsi, [rsp+28h+arg_8]
0x10042691b  add     rsp, 20h
0x10042691f  pop     rdi
0x100426920  jmp     dllmain_dispatch
```
