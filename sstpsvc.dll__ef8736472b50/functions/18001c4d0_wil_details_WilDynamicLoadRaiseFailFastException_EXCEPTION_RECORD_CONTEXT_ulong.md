# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18001c4d0`
- end: `0x18001c535`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001c4d0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c4ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c4ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c505`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c505`

## string_xrefs

- `0x18001c4e5`: `kernelbase.dll`

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
0x18001c4d0  mov     [rsp+arg_0], rbx
0x18001c4d5  mov     [rsp+arg_8], rsi
0x18001c4da  push    rdi
0x18001c4db  sub     rsp, 20h
0x18001c4df  mov     rsi, rcx
0x18001c4e2  mov     ebx, r8d
0x18001c4e5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18001c4ec  mov     rdi, rdx
0x18001c4ef  call    cs:__imp_GetModuleHandleW
0x18001c4f6  nop     dword ptr [rax+rax+00h]
0x18001c4fb  mov     rcx, rax; hModule
0x18001c4fe  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18001c505  call    cs:__imp_GetProcAddress
0x18001c50c  nop     dword ptr [rax+rax+00h]
0x18001c511  test    rax, rax
0x18001c514  jz      short loc_18001C524
0x18001c516  mov     r8d, ebx
0x18001c519  mov     rdx, rdi
0x18001c51c  mov     rcx, rsi
0x18001c51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c524  mov     rbx, [rsp+28h+arg_0]
0x18001c529  mov     rsi, [rsp+28h+arg_8]
0x18001c52e  add     rsp, 20h
0x18001c532  pop     rdi
0x18001c533  retn
```
