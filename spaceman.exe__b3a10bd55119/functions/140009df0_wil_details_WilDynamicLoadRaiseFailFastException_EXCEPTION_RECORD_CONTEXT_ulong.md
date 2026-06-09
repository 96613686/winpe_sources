# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140009df0`
- end: `0x140009e48`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009df0`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009e1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140009e1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009e0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140009e0f`

## string_xrefs

- `0x140009e05`: `kernelbase.dll`

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
0x140009df0  mov     [rsp+arg_0], rbx
0x140009df5  mov     [rsp+arg_8], rsi
0x140009dfa  push    rdi
0x140009dfb  sub     rsp, 20h
0x140009dff  mov     rsi, rcx
0x140009e02  mov     ebx, r8d
0x140009e05  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140009e0c  mov     rdi, rdx
0x140009e0f  call    cs:__imp_GetModuleHandleW
0x140009e15  mov     rcx, rax; hModule
0x140009e18  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x140009e1f  call    cs:__imp_GetProcAddress
0x140009e25  test    rax, rax
0x140009e28  jz      short loc_140009E38
0x140009e2a  mov     r8d, ebx
0x140009e2d  mov     rdx, rdi
0x140009e30  mov     rcx, rsi
0x140009e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e38  mov     rbx, [rsp+28h+arg_0]
0x140009e3d  mov     rsi, [rsp+28h+arg_8]
0x140009e42  add     rsp, 20h
0x140009e46  pop     rdi
0x140009e47  retn
```
