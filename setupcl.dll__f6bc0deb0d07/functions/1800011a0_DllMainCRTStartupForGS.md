# _DllMainCRTStartupForGS

- ea: `0x1800011a0`
- end: `0x1800011c7`
- name: `_DllMainCRTStartupForGS`
- size: `39`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800011a0`
- `0x180001360`

## import_xrefs

- `ntdll!LdrDisableThreadCalloutsForDll` at `0x1800011b6`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x1800011b6`

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
0x1800011a0  push    rbx
0x1800011a2  sub     rsp, 20h
0x1800011a6  mov     rbx, rcx
0x1800011a9  cmp     edx, 1
0x1800011ac  jnz     short loc_1800011BC
0x1800011ae  call    __security_init_cookie
0x1800011b3  mov     rcx, rbx; BaseAddress
0x1800011b6  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x1800011bc  mov     eax, 1
0x1800011c1  add     rsp, 20h
0x1800011c5  pop     rbx
0x1800011c6  retn
```
