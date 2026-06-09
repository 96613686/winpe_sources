# Proximity::Initialize(void)

- ea: `0x18002a7b0`
- end: `0x18002a81c`
- name: `?Initialize@Proximity@@YAJXZ`
- size: `108`
- prototype: `__int64 __fastcall(Proximity *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18002a7b0`
- `0x18002a824`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a7cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a7ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a805`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a7cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a7ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a805`

## string_xrefs

- `0x18002a7f7`: `InitProximityService`

## pseudocode

```c
__int64 __fastcall Proximity::Initialize(Proximity *this)
{
  HMODULE ProximityLibrary; // rax
  void (*ProcAddress)(void); // rax

  ProximityLibrary = Proximity::LoadProximityLibrary(this);
  Proximity::g_hProximityDLL = ProximityLibrary;
  if ( ProximityLibrary )
  {
    Proximity::g_pfnSessionChanged = (void (*)(unsigned int, unsigned int))GetProcAddress(
                                                                             ProximityLibrary,
                                                                             "SessionChangedEvent");
    Proximity::g_pfnGetProximityClientCount = (unsigned int (*)(void))GetProcAddress(
                                                                        Proximity::g_hProximityDLL,
                                                                        "GetProximityClientCount");
    ProcAddress = (void (*)(void))GetProcAddress(Proximity::g_hProximityDLL, "InitProximityService");
    if ( ProcAddress )
      ProcAddress();
  }
  return 0;
}

```

## disassembly

```asm
0x18002a7b0  sub     rsp, 28h
0x18002a7b4  call    ?LoadProximityLibrary@Proximity@@YAPEAUHINSTANCE__@@XZ; Proximity::LoadProximityLibrary(void)
0x18002a7b9  mov     cs:?g_hProximityDLL@Proximity@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * Proximity::g_hProximityDLL
0x18002a7c0  test    rax, rax
0x18002a7c3  jz      short loc_18002A815
0x18002a7c5  lea     rdx, aSessionchanged; "SessionChangedEvent"
0x18002a7cc  mov     rcx, rax; hModule
0x18002a7cf  call    cs:__imp_GetProcAddress
0x18002a7d5  mov     rcx, cs:?g_hProximityDLL@Proximity@@3PEAUHINSTANCE__@@EA; hModule
0x18002a7dc  lea     rdx, aGetproximitycl; "GetProximityClientCount"
0x18002a7e3  mov     cs:?g_pfnSessionChanged@Proximity@@3P6AXKK@ZEA, rax; void (*Proximity::g_pfnSessionChanged)(ulong,ulong)
0x18002a7ea  call    cs:__imp_GetProcAddress
0x18002a7f0  mov     rcx, cs:?g_hProximityDLL@Proximity@@3PEAUHINSTANCE__@@EA; hModule
0x18002a7f7  lea     rdx, aInitproximitys; "InitProximityService"
0x18002a7fe  mov     cs:?g_pfnGetProximityClientCount@Proximity@@3P6AKXZEA, rax; ulong (*Proximity::g_pfnGetProximityClientCount)(void)
0x18002a805  call    cs:__imp_GetProcAddress
0x18002a80b  test    rax, rax
0x18002a80e  jz      short loc_18002A815
0x18002a810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a815  xor     eax, eax
0x18002a817  add     rsp, 28h
0x18002a81b  retn
```
