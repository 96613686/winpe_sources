# _DllMainCRTStartup

- ea: `0x1004168f8`
- end: `0x100416935`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x100401050`

## callees

- `0x1004167c0`
- `0x1004168f8`
- `0x100416c04`

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
0x1004168f8  mov     [rsp+arg_0], rbx
0x1004168fd  mov     [rsp+arg_8], rsi
0x100416902  push    rdi
0x100416903  sub     rsp, 20h
0x100416907  mov     rdi, r8
0x10041690a  mov     ebx, edx
0x10041690c  mov     rsi, rcx
0x10041690f  cmp     edx, 1
0x100416912  jnz     short loc_100416919
0x100416914  call    __security_init_cookie
0x100416919  mov     r8, rdi; lpvReserved
0x10041691c  mov     edx, ebx; fdwReason
0x10041691e  mov     rcx, rsi; hinstDLL
0x100416921  mov     rbx, [rsp+28h+arg_0]
0x100416926  mov     rsi, [rsp+28h+arg_8]
0x10041692b  add     rsp, 20h
0x10041692f  pop     rdi
0x100416930  jmp     dllmain_dispatch
```
