# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x1800393d0`
- end: `0x180039435`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800393d0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800393ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800393ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039405`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039405`

## string_xrefs

- `0x1800393e5`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "RaiseFailFastException");
  if ( ProcAddress )
    ((void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))ProcAddress)(this, a2, v4);
}

```

## disassembly

```asm
0x1800393d0  mov     [rsp+arg_0], rbx
0x1800393d5  mov     [rsp+arg_8], rsi
0x1800393da  push    rdi
0x1800393db  sub     rsp, 20h
0x1800393df  mov     rsi, rcx
0x1800393e2  mov     ebx, r8d
0x1800393e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800393ec  mov     rdi, rdx
0x1800393ef  call    cs:__imp_GetModuleHandleW
0x1800393f6  nop     dword ptr [rax+rax+00h]
0x1800393fb  mov     rcx, rax; hModule
0x1800393fe  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x180039405  call    cs:__imp_GetProcAddress
0x18003940c  nop     dword ptr [rax+rax+00h]
0x180039411  test    rax, rax
0x180039414  jz      short loc_180039424
0x180039416  mov     r8d, ebx
0x180039419  mov     rdx, rdi
0x18003941c  mov     rcx, rsi
0x18003941f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039424  mov     rbx, [rsp+28h+arg_0]
0x180039429  mov     rsi, [rsp+28h+arg_8]
0x18003942e  add     rsp, 20h
0x180039432  pop     rdi
0x180039433  retn
```
