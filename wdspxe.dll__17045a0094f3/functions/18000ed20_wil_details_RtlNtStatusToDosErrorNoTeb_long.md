# wil::details::RtlNtStatusToDosErrorNoTeb(long)

- ea: `0x18000ed20`
- end: `0x18000ed99`
- name: `?RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z`
- size: `121`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000ed20`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000ed6a`
- `KERNEL32!GetProcAddress` at `0x18000ed6a`
- `KERNEL32!GetModuleHandleW` at `0x18000ed4d`
- `KERNEL32!GetModuleHandleW` at `0x18000ed4d`

## string_xrefs

- `0x18000ed46`: `ntdll.dll`

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
0x18000ed20  mov     [rsp+arg_0], rbx
0x18000ed25  push    rdi
0x18000ed26  sub     rsp, 20h
0x18000ed2a  mov     rax, cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA
0x18000ed31  xor     ebx, ebx
0x18000ed33  mov     edi, ecx
0x18000ed35  test    rax, rax
0x18000ed38  jnz     short loc_18000ED82
0x18000ed3a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ed41  test    rax, rax
0x18000ed44  jnz     short loc_18000ED60
0x18000ed46  lea     rcx, ModuleName; "ntdll.dll"
0x18000ed4d  call    cs:__imp_GetModuleHandleW
0x18000ed54  nop     dword ptr [rax+rax+00h]
0x18000ed59  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ed60  lea     rdx, aRtlntstatustod; "RtlNtStatusToDosErrorNoTeb"
0x18000ed67  mov     rcx, rax; hModule
0x18000ed6a  call    cs:__imp_GetProcAddress
0x18000ed71  nop     dword ptr [rax+rax+00h]
0x18000ed76  mov     cs:?s_pfnRtlNtStatusToDosErrorNoTeb@?1??RtlNtStatusToDosErrorNoTeb@details@wil@@YAKJ@Z@4P6AKJ@_EEA, rax
0x18000ed7d  test    rax, rax
0x18000ed80  jz      short loc_18000ED8B
0x18000ed82  mov     ecx, edi
0x18000ed84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed89  mov     ebx, eax
0x18000ed8b  mov     eax, ebx
0x18000ed8d  mov     rbx, [rsp+28h+arg_0]
0x18000ed92  add     rsp, 20h
0x18000ed96  pop     rdi
0x18000ed97  retn
```
