# _DllMainCRTStartup

- ea: `0x18000c1f0`
- end: `0x18000c22d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c0b4`
- `0x18000c1f0`
- `0x18000c270`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x18000c1f0  mov     [rsp+arg_0], rbx
0x18000c1f5  mov     [rsp+arg_8], rsi
0x18000c1fa  push    rdi
0x18000c1fb  sub     rsp, 20h
0x18000c1ff  mov     rdi, r8
0x18000c202  mov     ebx, edx
0x18000c204  mov     rsi, rcx
0x18000c207  cmp     edx, 1
0x18000c20a  jnz     short loc_18000C211
0x18000c20c  call    __security_init_cookie
0x18000c211  mov     r8, rdi; lpvReserved
0x18000c214  mov     edx, ebx; fdwReason
0x18000c216  mov     rcx, rsi; hinstDLL
0x18000c219  mov     rbx, [rsp+28h+arg_0]
0x18000c21e  mov     rsi, [rsp+28h+arg_8]
0x18000c223  add     rsp, 20h
0x18000c227  pop     rdi
0x18000c228  jmp     dllmain_dispatch
```
