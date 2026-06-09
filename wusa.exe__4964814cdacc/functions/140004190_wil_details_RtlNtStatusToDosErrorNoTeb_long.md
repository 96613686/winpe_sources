# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140004190`
- end: `0x1400041f2`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140004190`
- `0x140015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1400041ce`
- `KERNEL32!GetProcAddress` at `0x1400041ce`
- `KERNEL32!GetModuleHandleW` at `0x1400041b7`
- `KERNEL32!GetModuleHandleW` at `0x1400041b7`

## string_xrefs

- `0x1400041b0`: `ntdll.dll`

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
0x140004190  push    rbx
0x140004192  sub     rsp, 20h
0x140004196  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x14000419d  mov     ebx, ecx
0x14000419f  test    rax, rax
0x1400041a2  jnz     short loc_1400041E6
0x1400041a4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400041ab  test    rax, rax
0x1400041ae  jnz     short loc_1400041C4
0x1400041b0  lea     rcx, ModuleName; "ntdll.dll"
0x1400041b7  call    cs:__imp_GetModuleHandleW
0x1400041bd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400041c4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x1400041cb  mov     rcx, rax; hModule
0x1400041ce  call    cs:__imp_GetProcAddress
0x1400041d4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x1400041db  test    rax, rax
0x1400041de  jnz     short loc_1400041E6
0x1400041e0  add     rsp, 20h
0x1400041e4  pop     rbx
0x1400041e5  retn
0x1400041e6  mov     ecx, ebx
0x1400041e8  add     rsp, 20h
0x1400041ec  pop     rbx
0x1400041ed  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
