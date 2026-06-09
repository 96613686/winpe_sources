# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x140005be0`
- end: `0x140005c42`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `98`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140005be0`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140005c1e`
- `KERNEL32!GetProcAddress` at `0x140005c1e`
- `KERNEL32!GetModuleHandleW` at `0x140005c07`
- `KERNEL32!GetModuleHandleW` at `0x140005c07`

## string_xrefs

- `0x140005c00`: `ntdll.dll`

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
0x140005be0  push    rbx
0x140005be2  sub     rsp, 20h
0x140005be6  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x140005bed  mov     ebx, ecx
0x140005bef  test    rax, rax
0x140005bf2  jnz     short loc_140005C36
0x140005bf4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005bfb  test    rax, rax
0x140005bfe  jnz     short loc_140005C14
0x140005c00  lea     rcx, ModuleName; "ntdll.dll"
0x140005c07  call    cs:__imp_GetModuleHandleW
0x140005c0d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA, rax; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140005c14  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x140005c1b  mov     rcx, rax; hModule
0x140005c1e  call    cs:__imp_GetProcAddress
0x140005c24  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x140005c2b  test    rax, rax
0x140005c2e  jnz     short loc_140005C36
0x140005c30  add     rsp, 20h
0x140005c34  pop     rbx
0x140005c35  retn
0x140005c36  mov     ecx, ebx
0x140005c38  add     rsp, 20h
0x140005c3c  pop     rbx
0x140005c3d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
