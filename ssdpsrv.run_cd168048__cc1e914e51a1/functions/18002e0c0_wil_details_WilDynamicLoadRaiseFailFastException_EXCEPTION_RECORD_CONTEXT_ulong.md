# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18002e0c0`
- end: `0x18002e125`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `101`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002e0c0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e0df`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002e0df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e0f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002e0f5`

## string_xrefs

- `0x18002e0d5`: `kernelbase.dll`

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
0x18002e0c0  mov     [rsp+arg_0], rbx
0x18002e0c5  mov     [rsp+arg_8], rsi
0x18002e0ca  push    rdi
0x18002e0cb  sub     rsp, 20h
0x18002e0cf  mov     rsi, rcx
0x18002e0d2  mov     ebx, r8d
0x18002e0d5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18002e0dc  mov     rdi, rdx
0x18002e0df  call    cs:__imp_GetModuleHandleW
0x18002e0e6  nop     dword ptr [rax+rax+00h]
0x18002e0eb  mov     rcx, rax; hModule
0x18002e0ee  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18002e0f5  call    cs:__imp_GetProcAddress
0x18002e0fc  nop     dword ptr [rax+rax+00h]
0x18002e101  test    rax, rax
0x18002e104  jz      short loc_18002E114
0x18002e106  mov     r8d, ebx
0x18002e109  mov     rdx, rdi
0x18002e10c  mov     rcx, rsi
0x18002e10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e114  mov     rbx, [rsp+28h+arg_0]
0x18002e119  mov     rsi, [rsp+28h+arg_8]
0x18002e11e  add     rsp, 20h
0x18002e122  pop     rdi
0x18002e123  retn
```
