# DllRegisterServer

- ea: `0x180015c50`
- end: `0x180015d10`
- name: `DllRegisterServer`
- size: `192`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180013004`
- `0x180013514`
- `0x180015c50`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180015c66`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180015cff`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180015c66`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x180015cff`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180015c59`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x180015c59`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  const unsigned __int16 *v1; // rdx
  __int64 *v2; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // rdi
  struct ATL::_ATL_OBJMAP_ENTRY30 *v4; // rsi
  HRESULT v5; // ebx
  const struct ATL::_ATL_CATMAP_ENTRY *v6; // rax

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v2 = off_18002B298;
  for ( i = off_18002B290; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v2; ++i )
  {
    v4 = *i;
    if ( *i )
    {
      v5 = (*((__int64 (__fastcall **)(__int64))v4 + 1))(1);
      if ( v5 < 0 )
        goto LABEL_8;
      v6 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v4 + 7))();
      v5 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v6, 1);
      if ( v5 < 0 )
        goto LABEL_8;
      v2 = off_18002B298;
    }
  }
  v5 = ATL::AtlRegisterTypeLib(off_18002B288, v1);
LABEL_8:
  if ( v5 >= 0 && ATL::_pPerfRegFunc )
    v5 = ATL::_pPerfRegFunc(hInstance);
  SetThreadLocale(ThreadLocale);
  return v5;
}

```

## disassembly

```asm
0x180015c50  push    rbx
0x180015c52  push    rbp
0x180015c53  push    rsi
0x180015c54  push    rdi
0x180015c55  sub     rsp, 28h
0x180015c59  call    cs:__imp_GetThreadLocale
0x180015c5f  mov     ecx, 800h; Locale
0x180015c64  mov     ebp, eax
0x180015c66  call    cs:__imp_SetThreadLocale
0x180015c6c  mov     rcx, cs:off_18002B298
0x180015c73  xor     ebx, ebx
0x180015c75  mov     rdi, cs:off_18002B290
0x180015c7c  cmp     rdi, rcx
0x180015c7f  jnb     short loc_180015CD1
0x180015c81  mov     rsi, [rdi]
0x180015c84  test    rsi, rsi
0x180015c87  jz      short loc_180015CC4
0x180015c89  mov     rax, [rsi+8]
0x180015c8d  mov     ecx, 1
0x180015c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c97  mov     ebx, eax
0x180015c99  test    eax, eax
0x180015c9b  js      short loc_180015CDF
0x180015c9d  mov     rax, [rsi+38h]
0x180015ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ca6  mov     rcx, [rsi]; rguid
0x180015ca9  mov     r8d, 1; int
0x180015caf  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180015cb2  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180015cb7  mov     ebx, eax
0x180015cb9  test    eax, eax
0x180015cbb  js      short loc_180015CDF
0x180015cbd  mov     rcx, cs:off_18002B298
0x180015cc4  add     rdi, 8
0x180015cc8  cmp     rdi, rcx
0x180015ccb  jb      short loc_180015C81
0x180015ccd  test    ebx, ebx
0x180015ccf  js      short loc_180015CFD
0x180015cd1  mov     rcx, cs:off_18002B288; HINSTANCE
0x180015cd8  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180015cdd  mov     ebx, eax
0x180015cdf  test    ebx, ebx
0x180015ce1  js      short loc_180015CFD
0x180015ce3  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180015cea  test    rax, rax
0x180015ced  jz      short loc_180015CFD
0x180015cef  mov     rcx, cs:hInstance
0x180015cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cfb  mov     ebx, eax
0x180015cfd  mov     ecx, ebp; Locale
0x180015cff  call    cs:__imp_SetThreadLocale
0x180015d05  mov     eax, ebx
0x180015d07  add     rsp, 28h
0x180015d0b  pop     rdi
0x180015d0c  pop     rsi
0x180015d0d  pop     rbp
0x180015d0e  pop     rbx
0x180015d0f  retn
```
