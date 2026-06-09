# _DllMainCRTStartupForGS

- ea: `0x1800063c0`
- end: `0x1800063e7`
- name: `_DllMainCRTStartupForGS`
- size: `39`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800063c0`
- `0x180006580`

## import_xrefs

- `ntdll!LdrDisableThreadCalloutsForDll` at `0x1800063d6`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x1800063d6`

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
0x1800063c0  push    rbx
0x1800063c2  sub     rsp, 20h
0x1800063c6  mov     rbx, rcx
0x1800063c9  cmp     edx, 1
0x1800063cc  jnz     short loc_1800063DC
0x1800063ce  call    __security_init_cookie
0x1800063d3  mov     rcx, rbx; BaseAddress
0x1800063d6  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x1800063dc  mov     eax, 1
0x1800063e1  add     rsp, 20h
0x1800063e5  pop     rbx
0x1800063e6  retn
```
