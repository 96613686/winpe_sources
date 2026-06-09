# DllRegisterServer

- ea: `0x180008980`
- end: `0x180008aaa`
- name: `DllRegisterServer`
- size: `298`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x1800050c8`
- `0x180007d28`
- `0x18000824c`
- `0x180008980`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180008994`
- `KERNEL32!GetThreadLocale` at `0x180008994`
- `KERNEL32!SetThreadLocale` at `0x1800089a7`
- `KERNEL32!SetThreadLocale` at `0x180008a86`
- `KERNEL32!SetThreadLocale` at `0x1800089a7`
- `KERNEL32!SetThreadLocale` at `0x180008a86`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  ATL::CAtlModule *v1; // rcx
  const unsigned __int16 *v2; // rdx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rdi
  __int64 *i; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v6; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v7; // rax
  _QWORD v9[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v10; // [rsp+30h] [rbp-18h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v9[0] = L"APPID";
  v9[1] = L"70F829DE-656F-4EA9-B6BD-7D092099429C";
  v10 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v1, 0xC9u, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v9);
  if ( updated >= 0 )
  {
    v4 = off_180012140;
    for ( i = off_180012148; v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v4 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        updated = (*((__int64 (__fastcall **)(__int64))v6 + 1))(1);
        if ( updated < 0 )
          goto LABEL_9;
        v7 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v6 + 7))();
        updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v6, v7, 1);
        if ( updated < 0 )
          goto LABEL_9;
        i = off_180012148;
      }
    }
    updated = ATL::AtlRegisterTypeLib(off_180012138, v2);
LABEL_9:
    if ( updated >= 0 && ATL::_pPerfRegFunc )
      updated = ATL::_pPerfRegFunc(hInstance);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x180008980  mov     [rsp+arg_0], rbx
0x180008985  mov     [rsp+arg_8], rbp
0x18000898a  mov     [rsp+arg_10], rsi
0x18000898f  push    rdi
0x180008990  sub     rsp, 40h
0x180008994  call    cs:__imp_GetThreadLocale
0x18000899b  nop     dword ptr [rax+rax+00h]
0x1800089a0  mov     ecx, 800h; Locale
0x1800089a5  mov     ebp, eax
0x1800089a7  call    cs:__imp_SetThreadLocale
0x1800089ae  nop     dword ptr [rax+rax+00h]
0x1800089b3  lea     rax, aAppid; "APPID"
0x1800089ba  xorps   xmm0, xmm0
0x1800089bd  mov     [rsp+48h+var_28], rax
0x1800089c2  lea     r9, [rsp+48h+var_28]; struct ATL::_ATL_REGMAP_ENTRY *
0x1800089c7  lea     rax, a70f829de656f4e; "70F829DE-656F-4EA9-B6BD-7D092099429C"
0x1800089ce  mov     edx, 0C9h; unsigned int
0x1800089d3  mov     r8d, 1; int
0x1800089d9  mov     [rsp+48h+var_20], rax
0x1800089de  movdqu  [rsp+48h+var_18], xmm0
0x1800089e4  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x1800089e9  mov     ebx, eax
0x1800089eb  test    eax, eax
0x1800089ed  js      loc_180008A84
0x1800089f3  mov     rdi, cs:off_180012140
0x1800089fa  xor     ebx, ebx
0x1800089fc  mov     rax, cs:off_180012148
0x180008a03  cmp     rdi, rax
0x180008a06  jnb     short loc_180008A58
0x180008a08  mov     rsi, [rdi]
0x180008a0b  test    rsi, rsi
0x180008a0e  jz      short loc_180008A4B
0x180008a10  mov     rax, [rsi+8]
0x180008a14  mov     ecx, 1
0x180008a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a1e  mov     ebx, eax
0x180008a20  test    eax, eax
0x180008a22  js      short loc_180008A66
0x180008a24  mov     rax, [rsi+38h]
0x180008a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a2d  mov     rcx, [rsi]; rguid
0x180008a30  mov     r8d, 1; int
0x180008a36  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180008a39  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180008a3e  mov     ebx, eax
0x180008a40  test    eax, eax
0x180008a42  js      short loc_180008A66
0x180008a44  mov     rax, cs:off_180012148
0x180008a4b  add     rdi, 8
0x180008a4f  cmp     rdi, rax
0x180008a52  jb      short loc_180008A08
0x180008a54  test    ebx, ebx
0x180008a56  js      short loc_180008A84
0x180008a58  mov     rcx, cs:off_180012138; HINSTANCE
0x180008a5f  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180008a64  mov     ebx, eax
0x180008a66  test    ebx, ebx
0x180008a68  js      short loc_180008A84
0x180008a6a  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180008a71  test    rax, rax
0x180008a74  jz      short loc_180008A84
0x180008a76  mov     rcx, cs:hInstance
0x180008a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a82  mov     ebx, eax
0x180008a84  mov     ecx, ebp; Locale
0x180008a86  call    cs:__imp_SetThreadLocale
0x180008a8d  nop     dword ptr [rax+rax+00h]
0x180008a92  mov     rbp, [rsp+48h+arg_8]
0x180008a97  mov     eax, ebx
0x180008a99  mov     rbx, [rsp+48h+arg_0]
0x180008a9e  mov     rsi, [rsp+48h+arg_10]
0x180008aa3  add     rsp, 40h
0x180008aa7  pop     rdi
0x180008aa8  retn
```
