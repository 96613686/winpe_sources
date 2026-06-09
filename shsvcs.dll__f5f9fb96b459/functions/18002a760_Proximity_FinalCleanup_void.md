# Proximity::FinalCleanup(void)

- ea: `0x18002a760`
- end: `0x18002a7a6`
- name: `?FinalCleanup@Proximity@@YAJXZ`
- size: `70`
- prototype: `__int64 __fastcall(Proximity *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18002a760`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a78e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a78e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a777`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a777`

## string_xrefs

- `0x18002a770`: `CleanupProximityService`

## pseudocode

```c
__int64 __fastcall Proximity::FinalCleanup(Proximity *this)
{
  void (*ProcAddress)(void); // rax

  if ( Proximity::g_hProximityDLL )
  {
    ProcAddress = (void (*)(void))GetProcAddress(Proximity::g_hProximityDLL, "CleanupProximityService");
    if ( ProcAddress )
      ProcAddress();
    FreeLibrary(Proximity::g_hProximityDLL);
    Proximity::g_hProximityDLL = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002a760  sub     rsp, 28h
0x18002a764  mov     rcx, cs:?g_hProximityDLL@Proximity@@3PEAUHINSTANCE__@@EA; hModule
0x18002a76b  test    rcx, rcx
0x18002a76e  jz      short loc_18002A79F
0x18002a770  lea     rdx, aCleanupproximi; "CleanupProximityService"
0x18002a777  call    cs:__imp_GetProcAddress
0x18002a77d  test    rax, rax
0x18002a780  jz      short loc_18002A787
0x18002a782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a787  mov     rcx, cs:?g_hProximityDLL@Proximity@@3PEAUHINSTANCE__@@EA; hLibModule
0x18002a78e  call    cs:__imp_FreeLibrary
0x18002a794  mov     cs:?g_hProximityDLL@Proximity@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * Proximity::g_hProximityDLL
0x18002a79f  xor     eax, eax
0x18002a7a1  add     rsp, 28h
0x18002a7a5  retn
```
