# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180005a50`
- end: `0x180005aae`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `94`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005a50`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005a77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005a77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005a8e`

## string_xrefs

- `0x180005a70`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  unsigned int v1; // ebx
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax

  v1 = (unsigned int)this;
  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v1);
  return result;
}

```

## disassembly

```asm
0x180005a50  push    rbx
0x180005a52  sub     rsp, 20h
0x180005a56  mov     ebx, ecx
0x180005a58  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180005a5f  test    rax, rax
0x180005a62  jnz     short loc_180005AA0
0x180005a64  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005a6b  test    rax, rax
0x180005a6e  jnz     short loc_180005A84
0x180005a70  lea     rcx, ModuleName; "ntdll.dll"
0x180005a77  call    cs:__imp_GetModuleHandleW
0x180005a7d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005a84  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180005a8b  mov     rcx, rax; hModule
0x180005a8e  call    cs:__imp_GetProcAddress
0x180005a94  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180005a9b  test    rax, rax
0x180005a9e  jz      short loc_180005AA8
0x180005aa0  mov     ecx, ebx
0x180005aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aa7  nop
0x180005aa8  add     rsp, 20h
0x180005aac  pop     rbx
0x180005aad  retn
```
