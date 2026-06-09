# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x180003430`
- end: `0x180003488`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `88`
- prototype: `void __fastcall(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003430`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000344f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000344f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000345f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000345f`

## string_xrefs

- `0x180003445`: `kernelbase.dll`

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
0x180003430  mov     [rsp+arg_0], rbx
0x180003435  mov     [rsp+arg_8], rsi
0x18000343a  push    rdi
0x18000343b  sub     rsp, 20h
0x18000343f  mov     rsi, rcx
0x180003442  mov     ebx, r8d
0x180003445  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000344c  mov     rdi, rdx
0x18000344f  call    cs:__imp_GetModuleHandleW
0x180003455  mov     rcx, rax; hModule
0x180003458  lea     rdx, aRaisefailfaste; "RaiseFailFastException"
0x18000345f  call    cs:__imp_GetProcAddress
0x180003465  test    rax, rax
0x180003468  jz      short loc_180003478
0x18000346a  mov     r8d, ebx
0x18000346d  mov     rdx, rdi
0x180003470  mov     rcx, rsi
0x180003473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003478  mov     rbx, [rsp+28h+arg_0]
0x18000347d  mov     rsi, [rsp+28h+arg_8]
0x180003482  add     rsp, 20h
0x180003486  pop     rdi
0x180003487  retn
```
