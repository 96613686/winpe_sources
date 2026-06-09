# DllRegisterServer

- ea: `0x1800117f0`
- end: `0x1800118fe`
- name: `DllRegisterServer`
- size: `270`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x18000ce24`
- `0x180010cb8`
- `0x1800111dc`
- `0x1800117f0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x1800117f9`
- `KERNEL32!GetThreadLocale` at `0x1800117f9`
- `KERNEL32!SetThreadLocale` at `0x18001180c`
- `KERNEL32!SetThreadLocale` at `0x1800118e6`
- `KERNEL32!SetThreadLocale` at `0x18001180c`
- `KERNEL32!SetThreadLocale` at `0x1800118e6`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  unsigned int v1; // edx
  ATL::CAtlModule *v2; // rcx
  const unsigned __int16 *v3; // rdx
  HRESULT updated; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v5; // rdi
  __int64 *i; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v7; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v8; // rax
  _QWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v11; // [rsp+30h] [rbp-38h]

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v10[0] = L"APPID";
  v10[1] = L"{832701D5-B081-4790-93A7-5BCC7EE0755E}";
  v11 = 0;
  updated = ATL::CAtlModule::UpdateRegistryFromResourceS(v2, v1, 1, (struct ATL::_ATL_REGMAP_ENTRY *)v10);
  if ( updated >= 0 )
  {
    v5 = off_18001B540;
    for ( i = off_18001B548; v5 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)i; ++v5 )
    {
      v7 = *v5;
      if ( *v5 )
      {
        updated = (*((__int64 (__fastcall **)(__int64))v7 + 1))(1);
        if ( updated < 0 )
          goto LABEL_9;
        v8 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*((__int64 (**)(void))v7 + 7))();
        updated = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v7, v8, 1);
        if ( updated < 0 )
          goto LABEL_9;
        i = off_18001B548;
      }
    }
    updated = ATL::AtlRegisterTypeLib(off_18001B538, v3);
LABEL_9:
    if ( updated >= 0 && ATL::_pPerfRegFunc )
      updated = ATL::_pPerfRegFunc(hModule);
  }
  SetThreadLocale(ThreadLocale);
  return updated;
}

```

## disassembly

```asm
0x1800117f0  push    rbx
0x1800117f2  push    rbp
0x1800117f3  push    rsi
0x1800117f4  push    rdi
0x1800117f5  sub     rsp, 48h
0x1800117f9  call    cs:__imp_GetThreadLocale
0x180011800  nop     dword ptr [rax+rax+00h]
0x180011805  mov     ecx, 800h; Locale
0x18001180a  mov     ebp, eax
0x18001180c  call    cs:__imp_SetThreadLocale
0x180011813  nop     dword ptr [rax+rax+00h]
0x180011818  lea     rax, aAppid_0; "APPID"
0x18001181f  xorps   xmm0, xmm0
0x180011822  mov     [rsp+68h+var_48], rax
0x180011827  lea     r9, [rsp+68h+var_48]; struct ATL::_ATL_REGMAP_ENTRY *
0x18001182c  lea     rax, a832701d5B08147; "{832701D5-B081-4790-93A7-5BCC7EE0755E}"
0x180011833  mov     r8d, 1; int
0x180011839  mov     [rsp+68h+var_40], rax
0x18001183e  movdqu  [rsp+68h+var_38], xmm0
0x180011844  call    ?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJIHPEAU_ATL_REGMAP_ENTRY@2@@Z; ATL::CAtlModule::UpdateRegistryFromResourceS(uint,int,ATL::_ATL_REGMAP_ENTRY *)
0x180011849  mov     ebx, eax
0x18001184b  test    eax, eax
0x18001184d  js      loc_1800118E4
0x180011853  mov     rdi, cs:off_18001B540
0x18001185a  xor     ebx, ebx
0x18001185c  mov     rax, cs:off_18001B548
0x180011863  cmp     rdi, rax
0x180011866  jnb     short loc_1800118B8
0x180011868  mov     rsi, [rdi]
0x18001186b  test    rsi, rsi
0x18001186e  jz      short loc_1800118AB
0x180011870  mov     rax, [rsi+8]
0x180011874  mov     ecx, 1
0x180011879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001187e  mov     ebx, eax
0x180011880  test    eax, eax
0x180011882  js      short loc_1800118C6
0x180011884  mov     rax, [rsi+38h]
0x180011888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001188d  mov     rcx, [rsi]; rguid
0x180011890  mov     r8d, 1; int
0x180011896  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180011899  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x18001189e  mov     ebx, eax
0x1800118a0  test    eax, eax
0x1800118a2  js      short loc_1800118C6
0x1800118a4  mov     rax, cs:off_18001B548
0x1800118ab  add     rdi, 8
0x1800118af  cmp     rdi, rax
0x1800118b2  jb      short loc_180011868
0x1800118b4  test    ebx, ebx
0x1800118b6  js      short loc_1800118E4
0x1800118b8  mov     rcx, cs:off_18001B538; HINSTANCE
0x1800118bf  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x1800118c4  mov     ebx, eax
0x1800118c6  test    ebx, ebx
0x1800118c8  js      short loc_1800118E4
0x1800118ca  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x1800118d1  test    rax, rax
0x1800118d4  jz      short loc_1800118E4
0x1800118d6  mov     rcx, cs:hModule
0x1800118dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e2  mov     ebx, eax
0x1800118e4  mov     ecx, ebp; Locale
0x1800118e6  call    cs:__imp_SetThreadLocale
0x1800118ed  nop     dword ptr [rax+rax+00h]
0x1800118f2  mov     eax, ebx
0x1800118f4  add     rsp, 48h
0x1800118f8  pop     rdi
0x1800118f9  pop     rsi
0x1800118fa  pop     rbp
0x1800118fb  pop     rbx
0x1800118fc  retn
```
