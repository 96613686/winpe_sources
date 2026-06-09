# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180005120`
- end: `0x180005182`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180005120`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000515e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000515e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005147`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180005147`

## string_xrefs

- `0x180005140`: `ntdll.dll`

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
0x180005120  push    rbx
0x180005122  sub     rsp, 20h
0x180005126  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000512d  mov     ebx, ecx
0x18000512f  test    rax, rax
0x180005132  jnz     short loc_180005176
0x180005134  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000513b  test    rax, rax
0x18000513e  jnz     short loc_180005154
0x180005140  lea     rcx, ModuleName; "ntdll.dll"
0x180005147  call    cs:__imp_GetModuleHandleW
0x18000514d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180005154  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000515b  mov     rcx, rax; hModule
0x18000515e  call    cs:__imp_GetProcAddress
0x180005164  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000516b  test    rax, rax
0x18000516e  jnz     short loc_180005176
0x180005170  add     rsp, 20h
0x180005174  pop     rbx
0x180005175  retn
0x180005176  mov     ecx, ebx
0x180005178  add     rsp, 20h
0x18000517c  pop     rbx
0x18000517d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
