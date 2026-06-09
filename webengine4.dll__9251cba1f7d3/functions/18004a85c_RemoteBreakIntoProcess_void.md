# RemoteBreakIntoProcess(void *)

- ea: `0x18004a85c`
- end: `0x18004a8d8`
- name: `?RemoteBreakIntoProcess@@YAHPEAX@Z`
- size: `124`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001ca84`

## callees

- `0x18004a330`
- `0x18004a85c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18004a8c3`
- `KERNEL32!CloseHandle` at `0x18004a8c3`
- `KERNEL32!GetProcAddress` at `0x18004a88b`
- `KERNEL32!GetProcAddress` at `0x18004a88b`
- `KERNEL32!CreateRemoteThread` at `0x18004a8b5`
- `KERNEL32!CreateRemoteThread` at `0x18004a8b5`
- `KERNEL32!GetModuleHandleA` at `0x18004a876`
- `KERNEL32!GetModuleHandleA` at `0x18004a876`

## string_xrefs

- `0x18004a86f`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall RemoteBreakIntoProcess(HANDLE hProcess)
{
  HMODULE ModuleHandleA; // rax
  ULONG (__stdcall *ProcAddress)(PVOID); // rax
  HANDLE RemoteThread; // rax

  DebugPriv();
  if ( !hProcess )
    return 0;
  ModuleHandleA = GetModuleHandleA("ntdll.dll");
  if ( !ModuleHandleA )
    return 0;
  ProcAddress = (ULONG (__stdcall *)(PVOID))GetProcAddress(ModuleHandleA, "DbgBreakPoint");
  if ( !ProcAddress )
    return 0;
  RemoteThread = CreateRemoteThread(hProcess, 0, 0x8000u, ProcAddress, 0, 0, 0);
  if ( !RemoteThread )
    return 0;
  CloseHandle(RemoteThread);
  return 1;
}

```

## disassembly

```asm
0x18004a85c  push    rbx
0x18004a85e  sub     rsp, 40h
0x18004a862  mov     rbx, rcx
0x18004a865  call    ?DebugPriv@@YAXXZ; DebugPriv(void)
0x18004a86a  test    rbx, rbx
0x18004a86d  jz      short loc_18004A8D0
0x18004a86f  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18004a876  call    cs:__imp_GetModuleHandleA
0x18004a87c  test    rax, rax
0x18004a87f  jz      short loc_18004A8D0
0x18004a881  lea     rdx, aDbgbreakpoint; "DbgBreakPoint"
0x18004a888  mov     rcx, rax; hModule
0x18004a88b  call    cs:__imp_GetProcAddress
0x18004a891  test    rax, rax
0x18004a894  jz      short loc_18004A8D0
0x18004a896  and     [rsp+48h+var_18], 0
0x18004a89c  mov     r9, rax; lpStartAddress
0x18004a89f  and     [rsp+48h+var_20], 0
0x18004a8a4  xor     edx, edx; lpThreadAttributes
0x18004a8a6  and     [rsp+48h+var_28], 0
0x18004a8ac  mov     r8d, 8000h; dwStackSize
0x18004a8b2  mov     rcx, rbx; hProcess
0x18004a8b5  call    cs:__imp_CreateRemoteThread
0x18004a8bb  test    rax, rax
0x18004a8be  jz      short loc_18004A8D0
0x18004a8c0  mov     rcx, rax; hObject
0x18004a8c3  call    cs:__imp_CloseHandle
0x18004a8c9  mov     eax, 1
0x18004a8ce  jmp     short loc_18004A8D2
0x18004a8d0  xor     eax, eax
0x18004a8d2  add     rsp, 40h
0x18004a8d6  pop     rbx
0x18004a8d7  retn
```
