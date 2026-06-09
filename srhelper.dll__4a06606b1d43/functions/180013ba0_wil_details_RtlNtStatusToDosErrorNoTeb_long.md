# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x180013ba0`
- end: `0x180013c02`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `FARPROC __fastcall(wil::details *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180013ba0`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180013bde`
- `KERNEL32!GetProcAddress` at `0x180013bde`
- `KERNEL32!GetModuleHandleW` at `0x180013bc7`
- `KERNEL32!GetModuleHandleW` at `0x180013bc7`

## string_xrefs

- `0x180013bc0`: `ntdll.dll`

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
  ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x180013ba0  push    rbx
0x180013ba2  sub     rsp, 20h
0x180013ba6  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x180013bad  mov     ebx, ecx
0x180013baf  test    rax, rax
0x180013bb2  jnz     short loc_180013BF6
0x180013bb4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013bbb  test    rax, rax
0x180013bbe  jnz     short loc_180013BD4
0x180013bc0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180013bc7  call    cs:__imp_GetModuleHandleW
0x180013bcd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013bd4  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x180013bdb  mov     rcx, rax; hModule
0x180013bde  call    cs:__imp_GetProcAddress
0x180013be4  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x180013beb  test    rax, rax
0x180013bee  jnz     short loc_180013BF6
0x180013bf0  add     rsp, 20h
0x180013bf4  pop     rbx
0x180013bf5  retn
0x180013bf6  mov     ecx, ebx
0x180013bf8  add     rsp, 20h
0x180013bfc  pop     rbx
0x180013bfd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
