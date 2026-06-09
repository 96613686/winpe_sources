# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180002780`
- end: `0x1800027e2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180002780`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800027be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800027be`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800027a7`

## string_xrefs

- `0x1800027a0`: `ntdll.dll`

## pseudocode

```c
FARPROC __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC result; // rax
  unsigned int v2; // ebx
  HMODULE ModuleHandleW; // rax

  result = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  result = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)result;
  if ( result )
    return (FARPROC)((__int64 (__fastcall *)(_QWORD))result)(v2);
  return result;
}

```

## disassembly

```asm
0x180002780  push    rbx
0x180002782  sub     rsp, 20h
0x180002786  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000278d  mov     ebx, ecx
0x18000278f  test    rax, rax
0x180002792  jnz     short loc_1800027D6
0x180002794  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000279b  test    rax, rax
0x18000279e  jnz     short loc_1800027B4
0x1800027a0  lea     rcx, ModuleName; "ntdll.dll"
0x1800027a7  call    cs:__imp_GetModuleHandleW
0x1800027ad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800027b4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1800027bb  mov     rcx, rax; hModule
0x1800027be  call    cs:__imp_GetProcAddress
0x1800027c4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1800027cb  test    rax, rax
0x1800027ce  jnz     short loc_1800027D6
0x1800027d0  add     rsp, 20h
0x1800027d4  pop     rbx
0x1800027d5  retn
0x1800027d6  mov     ecx, ebx
0x1800027d8  add     rsp, 20h
0x1800027dc  pop     rbx
0x1800027dd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
