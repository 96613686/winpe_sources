# CFusionActCtxScope::~CFusionActCtxScope(void)

- ea: `0x180050428`
- end: `0x1800504df`
- name: `??1CFusionActCtxScope@@QEAA@XZ`
- size: `183`
- prototype: `void __fastcall(CFusionActCtxScope *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18004f220`
- `0x18004fa50`
- `0x180050010`

## callees

- `0x18000a804`
- `0x180050428`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050446`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800504ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800504ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005046d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005046d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050488`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050488`

## string_xrefs

- `0x180050466`: `Kernel32.dll`

## pseudocode

```c
void __fastcall CFusionActCtxScope::~CFusionActCtxScope(CFusionActCtxScope *this)
{
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  char **v5; // rcx

  if ( *(_DWORD *)this )
  {
    LastError = GetLastError();
    *(_DWORD *)this = 0;
    ProcAddress = (FARPROC)`CFusionActCtxScope::~CFusionActCtxScope'::`5'::pfn;
    if ( !`CFusionActCtxScope::~CFusionActCtxScope'::`5'::pfn )
    {
      ModuleHandleW = GetModuleHandleW(L"Kernel32.dll");
      if ( ModuleHandleW )
      {
        ProcAddress = GetProcAddress(ModuleHandleW, "DeactivateActCtx");
        `CFusionActCtxScope::~CFusionActCtxScope'::`5'::pfn = (__int64)ProcAddress;
        if ( ProcAddress )
          goto LABEL_8;
        v5 = `CFusionActCtxScope::~CFusionActCtxScope'::`15'::__callsite;
      }
      else
      {
        v5 = `CFusionActCtxScope::~CFusionActCtxScope'::`19'::__callsite;
      }
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)v5);
      ProcAddress = (FARPROC)`CFusionActCtxScope::~CFusionActCtxScope'::`5'::pfn;
      if ( !`CFusionActCtxScope::~CFusionActCtxScope'::`5'::pfn )
      {
LABEL_9:
        SetLastError(LastError);
        return;
      }
    }
LABEL_8:
    ((void (__fastcall *)(_QWORD, _QWORD))ProcAddress)(0, *((_QWORD *)this + 1));
    goto LABEL_9;
  }
}

```

## disassembly

```asm
0x180050428  mov     [rsp+arg_0], rbx
0x18005042d  push    rdi
0x18005042e  sub     rsp, 20h
0x180050432  cmp     dword ptr [rcx], 0
0x180050435  mov     rdi, rcx
0x180050438  jnz     short loc_180050446
0x18005043a  mov     rbx, [rsp+28h+arg_0]
0x18005043f  add     rsp, 20h
0x180050443  pop     rdi
0x180050444  retn
0x180050446  call    cs:__imp_GetLastError
0x18005044d  nop     dword ptr [rax+rax+00h]
0x180050452  mov     ebx, eax
0x180050454  mov     dword ptr [rdi], 0
0x18005045a  mov     rax, cs:?pfn@?4???1CFusionActCtxScope@@QEAA@XZ@4P6AHK_K@ZEA; int (*`CFusionActCtxScope::~CFusionActCtxScope(void)'::`5'::pfn)(ulong,unsigned __int64)
0x180050461  test    rax, rax
0x180050464  jnz     short loc_1800504C1
0x180050466  lea     rcx, ModuleName; "Kernel32.dll"
0x18005046d  call    cs:__imp_GetModuleHandleW
0x180050474  nop     dword ptr [rax+rax+00h]
0x180050479  test    rax, rax
0x18005047c  jz      short loc_1800504A9
0x18005047e  lea     rdx, ProcName; "DeactivateActCtx"
0x180050485  mov     rcx, rax; hModule
0x180050488  call    cs:__imp_GetProcAddress
0x18005048f  nop     dword ptr [rax+rax+00h]
0x180050494  mov     cs:?pfn@?4???1CFusionActCtxScope@@QEAA@XZ@4P6AHK_K@ZEA, rax; int (*`CFusionActCtxScope::~CFusionActCtxScope(void)'::`5'::pfn)(ulong,unsigned __int64)
0x18005049b  test    rax, rax
0x18005049e  jnz     short loc_1800504C1
0x1800504a0  lea     rcx, ?__callsite@?P@???1CFusionActCtxScope@@QEAA@XZ@4U_CALL_SITE_INFO@@B; _CALL_SITE_INFO const `CFusionActCtxScope::~CFusionActCtxScope(void)'::`15'::__callsite
0x1800504a7  jmp     short loc_1800504B0
0x1800504a9  lea     rcx, ?__callsite@?BD@???1CFusionActCtxScope@@QEAA@XZ@4U_CALL_SITE_INFO@@B; struct _CALL_SITE_INFO *
0x1800504b0  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x1800504b5  mov     rax, cs:?pfn@?4???1CFusionActCtxScope@@QEAA@XZ@4P6AHK_K@ZEA; int (*`CFusionActCtxScope::~CFusionActCtxScope(void)'::`5'::pfn)(ulong,unsigned __int64)
0x1800504bc  test    rax, rax
0x1800504bf  jz      short loc_1800504CC
0x1800504c1  mov     rdx, [rdi+8]
0x1800504c5  xor     ecx, ecx
0x1800504c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504cc  mov     ecx, ebx; dwErrCode
0x1800504ce  call    cs:__imp_SetLastError
0x1800504d5  nop     dword ptr [rax+rax+00h]
0x1800504da  jmp     loc_18005043A
```
