# CFusionActCtxScope::Win32Activate(void *)

- ea: `0x18005d620`
- end: `0x18005d6b1`
- name: `?Win32Activate@CFusionActCtxScope@@QEAAHPEAX@Z`
- size: `145`
- prototype: `__int64 __fastcall(CFusionActCtxScope *__hidden this, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004f220`
- `0x18004fa50`
- `0x180050010`

## callees

- `0x18000a804`
- `0x18005d620`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005d643`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005d643`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d65e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005d65e`

## string_xrefs

- `0x18005d63c`: `Kernel32.dll`

## pseudocode

```c
FARPROC __fastcall CFusionActCtxScope::Win32Activate(CFusionActCtxScope *this, void *a2)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax
  char **v6; // rcx

  result = (FARPROC)`CFusionActCtxScope::Win32Activate'::`2'::pfn;
  if ( !`CFusionActCtxScope::Win32Activate'::`2'::pfn )
  {
    ModuleHandleW = GetModuleHandleW(L"Kernel32.dll");
    if ( !ModuleHandleW )
    {
      v6 = `CFusionActCtxScope::Win32Activate'::`16'::__callsite;
LABEL_6:
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)v6);
      result = (FARPROC)`CFusionActCtxScope::Win32Activate'::`2'::pfn;
      if ( !`CFusionActCtxScope::Win32Activate'::`2'::pfn )
        return result;
      goto LABEL_7;
    }
    result = GetProcAddress(ModuleHandleW, "ActivateActCtx");
    `CFusionActCtxScope::Win32Activate'::`2'::pfn = (__int64)result;
    if ( !result )
    {
      v6 = `CFusionActCtxScope::Win32Activate'::`12'::__callsite;
      goto LABEL_6;
    }
  }
LABEL_7:
  result = (FARPROC)((__int64 (__fastcall *)(void *, char *))result)(a2, (char *)this + 8);
  *(_DWORD *)this = (_DWORD)result;
  return result;
}

```

## disassembly

```asm
0x18005d620  mov     [rsp+arg_0], rbx
0x18005d625  push    rdi
0x18005d626  sub     rsp, 20h
0x18005d62a  mov     rax, cs:?pfn@?1??Win32Activate@CFusionActCtxScope@@QEAAHPEAX@Z@4P6AH0PEA_K@ZEA; int (*`CFusionActCtxScope::Win32Activate(void *)'::`2'::pfn)(void *,unsigned __int64 *)
0x18005d631  mov     rdi, rdx
0x18005d634  mov     rbx, rcx
0x18005d637  test    rax, rax
0x18005d63a  jnz     short loc_18005D697
0x18005d63c  lea     rcx, ModuleName; "Kernel32.dll"
0x18005d643  call    cs:__imp_GetModuleHandleW
0x18005d64a  nop     dword ptr [rax+rax+00h]
0x18005d64f  test    rax, rax
0x18005d652  jz      short loc_18005D67F
0x18005d654  lea     rdx, aActivateactctx; "ActivateActCtx"
0x18005d65b  mov     rcx, rax; hModule
0x18005d65e  call    cs:__imp_GetProcAddress
0x18005d665  nop     dword ptr [rax+rax+00h]
0x18005d66a  mov     cs:?pfn@?1??Win32Activate@CFusionActCtxScope@@QEAAHPEAX@Z@4P6AH0PEA_K@ZEA, rax; int (*`CFusionActCtxScope::Win32Activate(void *)'::`2'::pfn)(void *,unsigned __int64 *)
0x18005d671  test    rax, rax
0x18005d674  jnz     short loc_18005D697
0x18005d676  lea     rcx, ?__callsite@?M@??Win32Activate@CFusionActCtxScope@@QEAAHPEAX@Z@4U_CALL_SITE_INFO@@B; _CALL_SITE_INFO const `CFusionActCtxScope::Win32Activate(void *)'::`12'::__callsite
0x18005d67d  jmp     short loc_18005D686
0x18005d67f  lea     rcx, ?__callsite@?BA@??Win32Activate@CFusionActCtxScope@@QEAAHPEAX@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x18005d686  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18005d68b  mov     rax, cs:?pfn@?1??Win32Activate@CFusionActCtxScope@@QEAAHPEAX@Z@4P6AH0PEA_K@ZEA; int (*`CFusionActCtxScope::Win32Activate(void *)'::`2'::pfn)(void *,unsigned __int64 *)
0x18005d692  test    rax, rax
0x18005d695  jz      short loc_18005D6A5
0x18005d697  lea     rdx, [rbx+8]
0x18005d69b  mov     rcx, rdi
0x18005d69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d6a3  mov     [rbx], eax
0x18005d6a5  mov     rbx, [rsp+28h+arg_0]
0x18005d6aa  add     rsp, 20h
0x18005d6ae  pop     rdi
0x18005d6af  retn
```
