# wil::details::WilDynamicLoadRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x18000fb10`
- end: `0x18000fb60`
- name: `?WilDynamicLoadRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `80`
- prototype: `void __fastcall(wil::details *this, struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ef50`
- `0x18000fb10`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fb2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fb2f`

## string_xrefs

- `0x18000fb25`: `kernelbase.dll`

## pseudocode

```c
void __fastcall wil::details::WilDynamicLoadRaiseFailFastException(
        wil::details *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  unsigned int v4; // ebx
  HMODULE ModuleHandleW; // rax
  void (__fastcall *Proc)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD); // rax

  v4 = (unsigned int)a3;
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  Proc = (void (__fastcall *)(wil::details *, struct _EXCEPTION_RECORD *, _QWORD))wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,unsigned long)>(ModuleHandleW);
  if ( Proc )
    Proc(this, a2, v4);
}

```

## disassembly

```asm
0x18000fb10  mov     [rsp+arg_0], rbx
0x18000fb15  mov     [rsp+arg_8], rsi
0x18000fb1a  push    rdi
0x18000fb1b  sub     rsp, 20h
0x18000fb1f  mov     rsi, rcx
0x18000fb22  mov     ebx, r8d
0x18000fb25  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000fb2c  mov     rdi, rdx
0x18000fb2f  call    cs:__imp_GetModuleHandleW
0x18000fb35  mov     rcx, rax
0x18000fb38  call    ??$GetProcAddress@P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z@details@wil@@YAP6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZPEAUHINSTANCE__@@PEBD@Z; wil::details::GetProcAddress<void (*)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)>(HINSTANCE__ *,char const *)
0x18000fb3d  test    rax, rax
0x18000fb40  jz      short loc_18000FB50
0x18000fb42  mov     r8d, ebx
0x18000fb45  mov     rdx, rdi
0x18000fb48  mov     rcx, rsi
0x18000fb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb50  mov     rbx, [rsp+28h+arg_0]
0x18000fb55  mov     rsi, [rsp+28h+arg_8]
0x18000fb5a  add     rsp, 20h
0x18000fb5e  pop     rdi
0x18000fb5f  retn
```
