# _DllMainCRTStartupForGS

- ea: `0x1800062f0`
- end: `0x180006317`
- name: `_DllMainCRTStartupForGS`
- size: `39`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800062f0`
- `0x1800064ac`

## import_xrefs

- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180006306`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180006306`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartupForGS(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
  {
    _security_init_cookie();
    LdrDisableThreadCalloutsForDll(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x1800062f0  push    rbx
0x1800062f2  sub     rsp, 20h
0x1800062f6  mov     rbx, rcx
0x1800062f9  cmp     edx, 1
0x1800062fc  jnz     short loc_18000630C
0x1800062fe  call    __security_init_cookie
0x180006303  mov     rcx, rbx; BaseAddress
0x180006306  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x18000630c  mov     eax, 1
0x180006311  add     rsp, 20h
0x180006315  pop     rbx
0x180006316  retn
```
