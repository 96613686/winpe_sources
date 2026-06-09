# DllMain

- ea: `0x18001f7e8`
- end: `0x18001f939`
- name: `DllMain`
- size: `337`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180036dc4`

## callees

- `0x18001f7e8`
- `0x18001f940`
- `0x18001f9c4`
- `0x18001f9f4`
- `0x18001fb5c`
- `0x18001fcd0`
- `0x18003732c`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001f8b0`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001f8b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f860`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f860`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001f8bd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001f8fd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001f8bd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001f8fd`
- `KERNEL32!ReleaseActCtx` at `0x18001f876`
- `KERNEL32!ReleaseActCtx` at `0x18001f876`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v5; // ebx
  char *v6; // rdi

  if ( fdwReason == 1 )
  {
    SHFusionInitializeFromModuleID(hinstDLL);
    g_hmodThisDll = hinstDLL;
    DisableThreadLibraryCalls(hinstDLL);
    InitializeCriticalSection(&g_csZIP);
    McGenEventRegister_EventRegister();
    v5 = 0;
    v6 = (char *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      *(_QWORD *)v6 = &CTempFileNameArray::`vftable';
      *((_QWORD *)v6 + 6) = 0;
      *((_QWORD *)v6 + 7) = 0;
      *((_QWORD *)v6 + 8) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
      g_pCTFA = (CTempFileNameArray *)v6;
      g_hdsaEnumCache = DSA_Create(528, 1);
      LOBYTE(v5) = g_hdsaEnumCache != 0;
      return v5;
    }
    else
    {
      g_pCTFA = 0;
      return 0;
    }
  }
  else
  {
    if ( !fdwReason )
    {
      DSA_DestroyCallback(g_hdsaEnumCache, _ReleaseCache, 0);
      g_hdsaEnumCache = 0;
      if ( g_pCTFA )
      {
        (**(void (__fastcall ***)(CTempFileNameArray *, __int64))g_pCTFA)(g_pCTFA, 1);
        g_pCTFA = 0;
      }
      McGenEventUnregister_EventUnregister();
      DeleteCriticalSection(&g_csZIP);
      if ( g_hActCtx != (HANDLE)-1LL )
      {
        ReleaseActCtx(g_hActCtx);
        g_hActCtx = (HANDLE)-1LL;
      }
      if ( hModule )
        hModule = (HMODULE)-1LL;
    }
    return 1;
  }
}

```

## disassembly

```asm
0x18001f7e8  mov     [rsp+arg_0], rbx
0x18001f7ed  push    rdi
0x18001f7ee  sub     rsp, 20h
0x18001f7f2  mov     rbx, rcx
0x18001f7f5  cmp     edx, 1
0x18001f7f8  jz      loc_18001F89C
0x18001f7fe  xor     ebx, ebx
0x18001f800  test    edx, edx
0x18001f802  jz      short loc_18001F814
0x18001f804  mov     eax, 1
0x18001f809  mov     rbx, [rsp+28h+arg_0]
0x18001f80e  add     rsp, 20h
0x18001f812  pop     rdi
0x18001f813  retn
0x18001f814  mov     rcx, cs:?g_hdsaEnumCache@@3PEAU_DSA@@EA; hdsa
0x18001f81b  lea     rdx, ?_ReleaseCache@@YAHPEAX0@Z; pfnCB
0x18001f822  xor     r8d, r8d; pData
0x18001f825  call    DSA_DestroyCallback
0x18001f82a  mov     rcx, cs:?g_pCTFA@@3PEAVCTempFileNameArray@@EA; CTempFileNameArray * g_pCTFA
0x18001f831  mov     cs:?g_hdsaEnumCache@@3PEAU_DSA@@EA, rbx; _DSA * g_hdsaEnumCache
0x18001f838  test    rcx, rcx
0x18001f83b  jz      short loc_18001F854
0x18001f83d  mov     rax, [rcx]
0x18001f840  mov     edx, 1
0x18001f845  mov     rax, [rax]
0x18001f848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f84d  mov     cs:?g_pCTFA@@3PEAVCTempFileNameArray@@EA, rbx; CTempFileNameArray * g_pCTFA
0x18001f854  call    McGenEventUnregister_EventUnregister
0x18001f859  lea     rcx, g_csZIP; lpCriticalSection
0x18001f860  call    cs:__imp_DeleteCriticalSection
0x18001f866  mov     rcx, cs:g_hActCtx; hActCtx
0x18001f86d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001f871  cmp     rcx, rdi
0x18001f874  jz      short loc_18001F883
0x18001f876  call    cs:__imp_ReleaseActCtx
0x18001f87c  mov     cs:g_hActCtx, rdi
0x18001f883  cmp     cs:hModule, rbx
0x18001f88a  jz      loc_18001F804
0x18001f890  mov     cs:hModule, rdi
0x18001f897  jmp     loc_18001F804
0x18001f89c  mov     edx, 7Bh ; '{'
0x18001f8a1  call    SHFusionInitializeFromModuleID
0x18001f8a6  mov     rcx, rbx; hLibModule
0x18001f8a9  mov     cs:g_hmodThisDll, rbx
0x18001f8b0  call    cs:__imp_DisableThreadLibraryCalls
0x18001f8b6  lea     rcx, g_csZIP; lpCriticalSection
0x18001f8bd  call    cs:__imp_InitializeCriticalSection
0x18001f8c3  call    McGenEventRegister_EventRegister
0x18001f8c8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f8cf  mov     ecx, 48h ; 'H'; unsigned __int64
0x18001f8d4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f8d9  xor     ebx, ebx
0x18001f8db  mov     rdi, rax
0x18001f8de  test    rax, rax
0x18001f8e1  jz      short loc_18001F92B
0x18001f8e3  lea     rax, ??_7CTempFileNameArray@@6B@; const CTempFileNameArray::`vftable'
0x18001f8ea  mov     [rdi], rax
0x18001f8ed  lea     rcx, [rdi+8]; lpCriticalSection
0x18001f8f1  mov     [rdi+30h], rbx
0x18001f8f5  mov     [rdi+38h], rbx
0x18001f8f9  mov     [rdi+40h], rbx
0x18001f8fd  call    cs:__imp_InitializeCriticalSection
0x18001f903  lea     edx, [rbx+1]; cItemGrow
0x18001f906  mov     cs:?g_pCTFA@@3PEAVCTempFileNameArray@@EA, rdi; CTempFileNameArray * g_pCTFA
0x18001f90d  mov     ecx, 210h; cbItem
0x18001f912  call    DSA_Create
0x18001f917  test    rax, rax
0x18001f91a  mov     cs:?g_hdsaEnumCache@@3PEAU_DSA@@EA, rax; _DSA * g_hdsaEnumCache
0x18001f921  setnz   bl
0x18001f924  mov     eax, ebx
0x18001f926  jmp     loc_18001F809
0x18001f92b  mov     cs:?g_pCTFA@@3PEAVCTempFileNameArray@@EA, rbx; CTempFileNameArray * g_pCTFA
0x18001f932  xor     eax, eax
0x18001f934  jmp     loc_18001F809
```
