# COperatorReleaseActCtx::operator()(void *)

- ea: `0x18005cd40`
- end: `0x18005cdc4`
- name: `??RCOperatorReleaseActCtx@@QEBAHPEAX@Z`
- size: `132`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001fe0`
- `0x18001e620`
- `0x1800504e8`

## callees

- `0x18000a804`
- `0x18005cd40`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005cd5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005cd5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cd77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005cd77`

## string_xrefs

- `0x18005cd55`: `Kernel32.dll`

## pseudocode

```c
FARPROC __fastcall COperatorReleaseActCtx::operator()(__int64 a1, __int64 a2)
{
  FARPROC result; // rax
  HMODULE ModuleHandleW; // rax
  char **v5; // rcx

  result = (FARPROC)`COperatorReleaseActCtx::operator()'::`2'::pfn;
  if ( !`COperatorReleaseActCtx::operator()'::`2'::pfn )
  {
    ModuleHandleW = GetModuleHandleW(L"Kernel32.dll");
    if ( !ModuleHandleW )
    {
      v5 = `COperatorReleaseActCtx::operator()'::`16'::__callsite;
LABEL_6:
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)v5);
      result = (FARPROC)`COperatorReleaseActCtx::operator()'::`2'::pfn;
      if ( !`COperatorReleaseActCtx::operator()'::`2'::pfn )
        return result;
      return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a2);
    }
    result = GetProcAddress(ModuleHandleW, "ReleaseActCtx");
    `COperatorReleaseActCtx::operator()'::`2'::pfn = (__int64)result;
    if ( !result )
    {
      v5 = `COperatorReleaseActCtx::operator()'::`12'::__callsite;
      goto LABEL_6;
    }
  }
  return (FARPROC)((__int64 (__fastcall *)(__int64))result)(a2);
}

```

## disassembly

```asm
0x18005cd40  push    rbx
0x18005cd42  sub     rsp, 20h
0x18005cd46  mov     rax, cs:?pfn@?1???RCOperatorReleaseActCtx@@QEBAHPEAX@Z@4P6AH0@ZEA; int (*`COperatorReleaseActCtx::operator()(void *)'::`2'::pfn)(void *)
0x18005cd4d  mov     rbx, rdx
0x18005cd50  test    rax, rax
0x18005cd53  jnz     short loc_18005CDB7
0x18005cd55  lea     rcx, ModuleName; "Kernel32.dll"
0x18005cd5c  call    cs:__imp_GetModuleHandleW
0x18005cd63  nop     dword ptr [rax+rax+00h]
0x18005cd68  test    rax, rax
0x18005cd6b  jz      short loc_18005CD98
0x18005cd6d  lea     rdx, aReleaseactctx; "ReleaseActCtx"
0x18005cd74  mov     rcx, rax; hModule
0x18005cd77  call    cs:__imp_GetProcAddress
0x18005cd7e  nop     dword ptr [rax+rax+00h]
0x18005cd83  mov     cs:?pfn@?1???RCOperatorReleaseActCtx@@QEBAHPEAX@Z@4P6AH0@ZEA, rax; int (*`COperatorReleaseActCtx::operator()(void *)'::`2'::pfn)(void *)
0x18005cd8a  test    rax, rax
0x18005cd8d  jnz     short loc_18005CDB7
0x18005cd8f  lea     rcx, ?__callsite@?M@???RCOperatorReleaseActCtx@@QEBAHPEAX@Z@4U_CALL_SITE_INFO@@B; _CALL_SITE_INFO const `COperatorReleaseActCtx::operator()(void *)'::`12'::__callsite
0x18005cd96  jmp     short loc_18005CD9F
0x18005cd98  lea     rcx, ?__callsite@?BA@???RCOperatorReleaseActCtx@@QEBAHPEAX@Z@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x18005cd9f  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x18005cda4  mov     rax, cs:?pfn@?1???RCOperatorReleaseActCtx@@QEBAHPEAX@Z@4P6AH0@ZEA; int (*`COperatorReleaseActCtx::operator()(void *)'::`2'::pfn)(void *)
0x18005cdab  test    rax, rax
0x18005cdae  jnz     short loc_18005CDB7
0x18005cdb0  add     rsp, 20h
0x18005cdb4  pop     rbx
0x18005cdb5  retn
0x18005cdb7  mov     rcx, rbx
0x18005cdba  add     rsp, 20h
0x18005cdbe  pop     rbx
0x18005cdbf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
