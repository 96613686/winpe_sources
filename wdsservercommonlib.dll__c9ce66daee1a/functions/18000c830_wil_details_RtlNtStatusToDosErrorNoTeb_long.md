# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000c830`
- end: `0x18000c8a9`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `121`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000c830`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000c87a`
- `KERNEL32!GetProcAddress` at `0x18000c87a`
- `KERNEL32!GetModuleHandleW` at `0x18000c85d`
- `KERNEL32!GetModuleHandleW` at `0x18000c85d`

## string_xrefs

- `0x18000c856`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil::details::RtlNtStatusToDosErrorNoTeb(wil::details *this)
{
  FARPROC ProcAddress; // rax
  unsigned int v2; // ebx
  unsigned int v3; // edi
  HMODULE ModuleHandleW; // rax

  ProcAddress = (FARPROC)`wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb;
  v2 = 0;
  v3 = (unsigned int)this;
  if ( `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v3);
  ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
  if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlNtStatusToDosErrorNoTeb");
  `wil::details::RtlNtStatusToDosErrorNoTeb'::`2'::s_pfnRtlNtStatusToDosErrorNoTeb = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(v3);
  return v2;
}

```

## disassembly

```asm
0x18000c830  mov     [rsp+arg_0], rbx
0x18000c835  push    rdi
0x18000c836  sub     rsp, 20h
0x18000c83a  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000c841  xor     ebx, ebx
0x18000c843  mov     edi, ecx
0x18000c845  test    rax, rax
0x18000c848  jnz     short loc_18000C892
0x18000c84a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c851  test    rax, rax
0x18000c854  jnz     short loc_18000C870
0x18000c856  lea     rcx, ModuleName; "ntdll.dll"
0x18000c85d  call    cs:__imp_GetModuleHandleW
0x18000c864  nop     dword ptr [rax+rax+00h]
0x18000c869  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c870  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000c877  mov     rcx, rax; hModule
0x18000c87a  call    cs:__imp_GetProcAddress
0x18000c881  nop     dword ptr [rax+rax+00h]
0x18000c886  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000c88d  test    rax, rax
0x18000c890  jz      short loc_18000C89B
0x18000c892  mov     ecx, edi
0x18000c894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c899  mov     ebx, eax
0x18000c89b  mov     eax, ebx
0x18000c89d  mov     rbx, [rsp+28h+arg_0]
0x18000c8a2  add     rsp, 20h
0x18000c8a6  pop     rdi
0x18000c8a7  retn
```
