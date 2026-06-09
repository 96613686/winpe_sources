# DllMain

- ea: `0x18000a48c`
- end: `0x18000a4ce`
- name: `DllMain`
- size: `66`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180007734`

## callees

- `0x18000a48c`
- `0x18000da7c`
- `0x18000ef84`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000a4a6`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000a4a6`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      ThemeHeapStaticInitialize((int)hinstDLL);
      DisableThreadLibraryCalls(hinstDLL);
      return CThemeService::Main(1);
    }
  }
  else
  {
    CThemeService::Main(0);
  }
  return 1;
}

```

## disassembly

```asm
0x18000a48c  push    rbx
0x18000a48e  sub     rsp, 20h
0x18000a492  mov     rbx, rcx
0x18000a495  test    edx, edx
0x18000a497  jz      short loc_18000A4BC
0x18000a499  cmp     edx, 1
0x18000a49c  jnz     short loc_18000A4C3
0x18000a49e  call    ?ThemeHeapStaticInitialize@@YAXH@Z; ThemeHeapStaticInitialize(int)
0x18000a4a3  mov     rcx, rbx; hLibModule
0x18000a4a6  call    cs:__imp_DisableThreadLibraryCalls
0x18000a4ac  mov     ecx, 1; unsigned int
0x18000a4b1  call    ?Main@CThemeService@@SAHK@Z; CThemeService::Main(ulong)
0x18000a4b6  add     rsp, 20h
0x18000a4ba  pop     rbx
0x18000a4bb  retn
0x18000a4bc  xor     ecx, ecx; unsigned int
0x18000a4be  call    ?Main@CThemeService@@SAHK@Z; CThemeService::Main(ulong)
0x18000a4c3  mov     eax, 1
0x18000a4c8  add     rsp, 20h
0x18000a4cc  pop     rbx
0x18000a4cd  retn
```
