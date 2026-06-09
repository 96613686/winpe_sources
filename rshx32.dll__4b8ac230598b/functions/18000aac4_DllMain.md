# DllMain

- ea: `0x18000aac4`
- end: `0x18000aaf1`
- name: `DllMain`
- size: `45`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001f74`

## callees

- `0x18000aac4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000aad9`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000aad9`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    g_hInstance = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
    hProxyDll = hinstDLL;
  }
  return 1;
}

```

## disassembly

```asm
0x18000aac4  push    rbx
0x18000aac6  sub     rsp, 20h
0x18000aaca  mov     rbx, rcx
0x18000aacd  cmp     edx, 1
0x18000aad0  jnz     short loc_18000AAE6
0x18000aad2  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInstance
0x18000aad9  call    cs:__imp_DisableThreadLibraryCalls
0x18000aadf  mov     cs:hProxyDll, rbx
0x18000aae6  mov     eax, 1
0x18000aaeb  add     rsp, 20h
0x18000aaef  pop     rbx
0x18000aaf0  retn
```
