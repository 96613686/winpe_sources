# _DllMainCRTStartup

- ea: `0x1800154d4`
- end: `0x180015511`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012220`

## callees

- `0x1800153a4`
- `0x1800154d4`
- `0x180015530`

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
0x1800154d4  mov     [rsp+arg_0], rbx
0x1800154d9  mov     [rsp+arg_8], rsi
0x1800154de  push    rdi
0x1800154df  sub     rsp, 20h
0x1800154e3  mov     rdi, r8
0x1800154e6  mov     ebx, edx
0x1800154e8  mov     rsi, rcx
0x1800154eb  cmp     edx, 1
0x1800154ee  jnz     short loc_1800154F5
0x1800154f0  call    __security_init_cookie
0x1800154f5  mov     r8, rdi; lpvReserved
0x1800154f8  mov     edx, ebx; fdwReason
0x1800154fa  mov     rcx, rsi; hinstDLL
0x1800154fd  mov     rbx, [rsp+28h+arg_0]
0x180015502  mov     rsi, [rsp+28h+arg_8]
0x180015507  add     rsp, 20h
0x18001550b  pop     rdi
0x18001550c  jmp     dllmain_dispatch
```
