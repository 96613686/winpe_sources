# StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)

- ea: `0x180008eb0`
- end: `0x1800093e6`
- name: `?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z`
- size: `1334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800088c0`
- `0x1800093ec`

## callees

- `0x180008eb0`
- `0x1800164ec`
- `0x180017e48`
- `0x180018a54`
- `0x18001cc38`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180008fe6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800091d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800092c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000936a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180008fe6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800091d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x1800092c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000936a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180008ee9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180008ee9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009028`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009213`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009309`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800093ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009028`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009213`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009309`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800093ac`

## string_xrefs

- `0x180008f11`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008f5d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008f9f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180009036`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180009091`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800090d3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000912e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180009188`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180009221`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18000927e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180009317`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800093ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x180008ef9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180008ff6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800091e1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800092d7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000937a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800091c2`: `CurrentDirectoryPath`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(
        StateRepository::Cache::Context_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int Field_UInt32; // eax
  unsigned int v9; // edi
  int Field; // eax
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rcx
  int Field_String; // eax
  int v17; // edi
  unsigned __int16 *v18; // rcx
  int v19; // edi
  int v20; // eax
  unsigned int v21; // edi
  int v22; // edi
  int v23; // edi
  __int64 v24; // rcx
  int v25; // eax
  int v26; // edi
  unsigned __int16 *v27; // rcx
  int v28; // edi
  __int64 v29; // rcx
  int v30; // eax
  int v31; // edi
  unsigned __int16 *v32; // rcx
  __int64 v33; // rcx
  int v34; // eax
  int v35; // ebx
  unsigned __int16 *v36; // rcx
  unsigned __int16 **v37; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v38; // [rsp+28h] [rbp-18h] BYREF
  char v39; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  if ( a3 && (a3 & 1) == 0 )
    goto LABEL_6;
  Field_UInt32 = SRCacheContext_GetField_UInt32(*(_QWORD *)a1, L"Package", a2 + 8);
  v9 = Field_UInt32;
  if ( Field_UInt32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_UInt32,
      (int)v37);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x487,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)v9,
      (int)v37);
    return v9;
  }
  if ( a3 )
  {
LABEL_6:
    if ( (a3 & 2) == 0 )
      goto LABEL_10;
  }
  Field = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Index", (unsigned int *)(a2 + 16));
  v12 = Field;
  if ( Field < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)Field,
      (int)v37);
    return v12;
  }
  if ( a3 )
  {
LABEL_10:
    if ( (a3 & 4) == 0 )
      goto LABEL_14;
  }
  v13 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Flags", (unsigned int *)(a2 + 20));
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v13,
      (int)v37);
    return v14;
  }
  if ( a3 )
  {
LABEL_14:
    if ( (a3 & 8) == 0 )
      goto LABEL_24;
  }
  v15 = *(_QWORD *)a1;
  v37 = (unsigned __int16 **)(a2 + 24);
  v38 = 0;
  v39 = 1;
  Field_String = SRCacheContext_GetField_String(v15, L"PackageRelativeApplicationId", &v38);
  v17 = Field_String;
  if ( Field_String >= 0 )
    v17 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_String,
      (int)v37);
  if ( v39 )
  {
    v18 = *v37;
    *v37 = v38;
    if ( v18 )
      SRCache_Free();
  }
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x493,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v17,
      (int)v37);
    return (unsigned int)v17;
  }
  if ( a3 )
  {
LABEL_24:
    if ( (a3 & 0x10) == 0 )
      goto LABEL_28;
  }
  v38 = 0;
  v37 = (unsigned __int16 **)(a2 + 32);
  v39 = 1;
  v19 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"ApplicationUserModelId", &v38);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v37);
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x497,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v19,
      (int)v37);
    return (unsigned int)v19;
  }
  if ( a3 )
  {
LABEL_28:
    if ( (a3 & 0x20) == 0 )
      goto LABEL_32;
  }
  v20 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Activation", (unsigned int *)(a2 + 40));
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v20,
      (int)v37);
    return v21;
  }
  if ( a3 )
  {
LABEL_32:
    if ( (a3 & 0x40) == 0 )
      goto LABEL_36;
  }
  v38 = 0;
  v37 = (unsigned __int16 **)(a2 + 48);
  v39 = 1;
  v22 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"HostId", &v38);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v37);
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v22,
      (int)v37);
    return (unsigned int)v22;
  }
  if ( a3 )
  {
LABEL_36:
    if ( (a3 & 0x80u) == 0LL )
      goto LABEL_40;
  }
  v38 = 0;
  v37 = (unsigned __int16 **)(a2 + 56);
  v39 = 1;
  v23 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Parameters", &v38);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v37);
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v23,
      (int)v37);
    return (unsigned int)v23;
  }
  if ( a3 )
  {
LABEL_40:
    if ( (a3 & 0x100) == 0 )
      goto LABEL_50;
  }
  v24 = *(_QWORD *)a1;
  v37 = (unsigned __int16 **)(a2 + 64);
  v38 = 0;
  v39 = 1;
  v25 = SRCacheContext_GetField_String(v24, L"CurrentDirectoryPath", &v38);
  v26 = v25;
  if ( v25 >= 0 )
    v26 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v25,
      (int)v37);
  if ( v39 )
  {
    v27 = *v37;
    *v37 = v38;
    if ( v27 )
      SRCache_Free();
  }
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A7,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v26,
      (int)v37);
    return (unsigned int)v26;
  }
  if ( a3 )
  {
LABEL_50:
    if ( (a3 & 0x200) == 0 )
      goto LABEL_54;
  }
  v38 = 0;
  v37 = (unsigned __int16 **)(a2 + 72);
  v39 = 1;
  v28 = StateRepository::Cache::Context_NoThrow::GetField(a1, L"Executable", &v38);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v37);
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AB,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v28,
      (int)v37);
    return (unsigned int)v28;
  }
  if ( a3 )
  {
LABEL_54:
    if ( (a3 & 0x400) == 0 )
      goto LABEL_64;
  }
  v29 = *(_QWORD *)a1;
  v37 = (unsigned __int16 **)(a2 + 80);
  v38 = 0;
  v39 = 1;
  v30 = SRCacheContext_GetField_String(v29, L"Entrypoint", &v38);
  v31 = v30;
  if ( v30 >= 0 )
    v31 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v30,
      (int)v37);
  if ( v39 )
  {
    v32 = *v37;
    *v37 = v38;
    if ( v32 )
      SRCache_Free();
  }
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4AF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v31,
      (int)v37);
    return (unsigned int)v31;
  }
  if ( a3 )
  {
LABEL_64:
    if ( (a3 & 0x800) == 0 )
      goto LABEL_73;
  }
  v33 = *(_QWORD *)a1;
  v37 = (unsigned __int16 **)(a2 + 88);
  v38 = 0;
  v39 = 1;
  v34 = SRCacheContext_GetField_String(v33, L"StartPage", &v38);
  v35 = v34;
  if ( v34 >= 0 )
    v35 = 0;
  else
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v34,
      (int)v37);
  if ( v39 )
  {
    v36 = *v37;
    *v37 = v38;
    if ( v36 )
      SRCache_Free();
  }
  if ( v35 >= 0 )
  {
LABEL_73:
    *(_QWORD *)a2 = a4;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B3,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v35,
      (int)v37);
    return (unsigned int)v35;
  }
}

```

## disassembly

```asm
0x180008eb0  push    rbp
0x180008eb2  push    rbx
0x180008eb3  push    rsi
0x180008eb4  push    rdi
0x180008eb5  push    r12
0x180008eb7  push    r14
0x180008eb9  push    r15
0x180008ebb  mov     rbp, rsp
0x180008ebe  sub     rsp, 40h
0x180008ec2  xor     r12d, r12d
0x180008ec5  mov     r15, r9
0x180008ec8  mov     rbx, r8
0x180008ecb  mov     rsi, rdx
0x180008ece  mov     r14, rcx
0x180008ed1  test    r8, r8
0x180008ed4  jz      short loc_180008EDB
0x180008ed6  test    bl, 1
0x180008ed9  jz      short loc_180008F3B
0x180008edb  mov     rcx, [rcx]
0x180008ede  lea     r8, [rdx+8]
0x180008ee2  lea     rdx, aPackage; "Package"
0x180008ee9  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180008eef  mov     edi, eax
0x180008ef1  test    eax, eax
0x180008ef3  jns     short loc_180008F36
0x180008ef5  mov     rcx, [rbp+38h]; this
0x180008ef9  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008f00  mov     r9d, eax; char *
0x180008f03  mov     edx, 221h; void *
0x180008f08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f0d  mov     rcx, [rbp+38h]; this
0x180008f11  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008f18  mov     r9d, edi; char *
0x180008f1b  mov     edx, 487h; void *
0x180008f20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f25  mov     eax, edi
0x180008f27  add     rsp, 40h
0x180008f2b  pop     r15
0x180008f2d  pop     r14
0x180008f2f  pop     r12
0x180008f31  pop     rdi
0x180008f32  pop     rsi
0x180008f33  pop     rbx
0x180008f34  pop     rbp
0x180008f35  retn
0x180008f36  test    rbx, rbx
0x180008f39  jz      short loc_180008F40
0x180008f3b  test    bl, 2
0x180008f3e  jz      short loc_180008F7D
0x180008f40  lea     r8, [rsi+10h]; unsigned int *
0x180008f44  mov     rcx, r14; this
0x180008f47  lea     rdx, aIndex; "Index"
0x180008f4e  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180008f53  mov     edi, eax
0x180008f55  test    eax, eax
0x180008f57  jns     short loc_180008F78
0x180008f59  mov     rcx, [rbp+38h]; this
0x180008f5d  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008f64  mov     r9d, eax; char *
0x180008f67  mov     edx, 48Bh; void *
0x180008f6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f71  mov     eax, edi
0x180008f73  jmp     loc_1800093D7
0x180008f78  test    rbx, rbx
0x180008f7b  jz      short loc_180008F82
0x180008f7d  test    bl, 4
0x180008f80  jz      short loc_180008FBF
0x180008f82  lea     r8, [rsi+14h]; unsigned int *
0x180008f86  mov     rcx, r14; this
0x180008f89  lea     rdx, aFlags; "Flags"
0x180008f90  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180008f95  mov     edi, eax
0x180008f97  test    eax, eax
0x180008f99  jns     short loc_180008FBA
0x180008f9b  mov     rcx, [rbp+38h]; this
0x180008f9f  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008fa6  mov     r9d, eax; char *
0x180008fa9  mov     edx, 48Fh; void *
0x180008fae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008fb3  mov     eax, edi
0x180008fb5  jmp     loc_1800093D7
0x180008fba  test    rbx, rbx
0x180008fbd  jz      short loc_180008FC8
0x180008fbf  test    bl, 8
0x180008fc2  jz      loc_180009056
0x180008fc8  mov     rcx, [r14]
0x180008fcb  lea     rax, [rsi+18h]
0x180008fcf  lea     r8, [rbp+var_18]
0x180008fd3  mov     [rbp+var_20], rax
0x180008fd7  lea     rdx, aPackagerelativ; "PackageRelativeApplicationId"
0x180008fde  mov     [rbp+var_18], r12
0x180008fe2  mov     [rbp+var_10], 1
0x180008fe6  call    cs:__imp_SRCacheContext_GetField_String
0x180008fec  mov     edi, eax
0x180008fee  test    eax, eax
0x180008ff0  jns     short loc_18000900C
0x180008ff2  mov     rcx, [rbp+38h]; this
0x180008ff6  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008ffd  mov     r9d, eax; char *
0x180009000  mov     edx, 246h; void *
0x180009005  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000900a  jmp     short loc_18000900F
0x18000900c  mov     edi, r12d
0x18000900f  cmp     [rbp+var_10], r12b
0x180009013  jz      short loc_18000902E
0x180009015  mov     rdx, [rbp+var_20]
0x180009019  mov     rax, [rbp+var_18]
0x18000901d  mov     rcx, [rdx]
0x180009020  mov     [rdx], rax
0x180009023  test    rcx, rcx
0x180009026  jz      short loc_18000902E
0x180009028  call    cs:__imp_SRCache_Free
0x18000902e  test    edi, edi
0x180009030  jns     short loc_180009051
0x180009032  mov     rcx, [rbp+38h]; this
0x180009036  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000903d  mov     r9d, edi; char *
0x180009040  mov     edx, 493h; void *
0x180009045  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000904a  mov     eax, edi
0x18000904c  jmp     loc_1800093D7
0x180009051  test    rbx, rbx
0x180009054  jz      short loc_18000905B
0x180009056  test    bl, 10h
0x180009059  jz      short loc_1800090B1
0x18000905b  lea     rax, [rsi+20h]
0x18000905f  mov     [rbp+var_18], r12
0x180009063  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180009067  mov     [rbp+var_20], rax
0x18000906b  lea     rdx, aApplicationuse_0; "ApplicationUserModelId"
0x180009072  mov     [rbp+var_10], 1
0x180009076  mov     rcx, r14; this
0x180009079  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000907e  lea     rcx, [rbp+var_20]
0x180009082  mov     edi, eax
0x180009084  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180009089  test    edi, edi
0x18000908b  jns     short loc_1800090AC
0x18000908d  mov     rcx, [rbp+38h]; this
0x180009091  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009098  mov     r9d, edi; char *
0x18000909b  mov     edx, 497h; void *
0x1800090a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090a5  mov     eax, edi
0x1800090a7  jmp     loc_1800093D7
0x1800090ac  test    rbx, rbx
0x1800090af  jz      short loc_1800090B6
0x1800090b1  test    bl, 20h
0x1800090b4  jz      short loc_1800090F3
0x1800090b6  lea     r8, [rsi+28h]; unsigned int *
0x1800090ba  mov     rcx, r14; this
0x1800090bd  lea     rdx, aActivation_0; "Activation"
0x1800090c4  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x1800090c9  mov     edi, eax
0x1800090cb  test    eax, eax
0x1800090cd  jns     short loc_1800090EE
0x1800090cf  mov     rcx, [rbp+38h]; this
0x1800090d3  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800090da  mov     r9d, eax; char *
0x1800090dd  mov     edx, 49Bh; void *
0x1800090e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800090e7  mov     eax, edi
0x1800090e9  jmp     loc_1800093D7
0x1800090ee  test    rbx, rbx
0x1800090f1  jz      short loc_1800090F8
0x1800090f3  test    bl, 40h
0x1800090f6  jz      short loc_18000914E
0x1800090f8  lea     rax, [rsi+30h]
0x1800090fc  mov     [rbp+var_18], r12
0x180009100  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180009104  mov     [rbp+var_20], rax
0x180009108  lea     rdx, aHostid; "HostId"
0x18000910f  mov     [rbp+var_10], 1
0x180009113  mov     rcx, r14; this
0x180009116  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000911b  lea     rcx, [rbp+var_20]
0x18000911f  mov     edi, eax
0x180009121  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180009126  test    edi, edi
0x180009128  jns     short loc_180009149
0x18000912a  mov     rcx, [rbp+38h]; this
0x18000912e  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009135  mov     r9d, edi; char *
0x180009138  mov     edx, 49Fh; void *
0x18000913d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009142  mov     eax, edi
0x180009144  jmp     loc_1800093D7
0x180009149  test    rbx, rbx
0x18000914c  jz      short loc_180009152
0x18000914e  test    bl, bl
0x180009150  jns     short loc_1800091A8
0x180009152  lea     rax, [rsi+38h]
0x180009156  mov     [rbp+var_18], r12
0x18000915a  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18000915e  mov     [rbp+var_20], rax
0x180009162  lea     rdx, aParameters; "Parameters"
0x180009169  mov     [rbp+var_10], 1
0x18000916d  mov     rcx, r14; this
0x180009170  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x180009175  lea     rcx, [rbp+var_20]
0x180009179  mov     edi, eax
0x18000917b  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180009180  test    edi, edi
0x180009182  jns     short loc_1800091A3
0x180009184  mov     rcx, [rbp+38h]; this
0x180009188  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000918f  mov     r9d, edi; char *
0x180009192  mov     edx, 4A3h; void *
0x180009197  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000919c  mov     eax, edi
0x18000919e  jmp     loc_1800093D7
0x1800091a3  test    rbx, rbx
0x1800091a6  jz      short loc_1800091B3
0x1800091a8  bt      rbx, 8
0x1800091ad  jnb     loc_180009241
0x1800091b3  mov     rcx, [r14]
0x1800091b6  lea     rax, [rsi+40h]
0x1800091ba  lea     r8, [rbp+var_18]
0x1800091be  mov     [rbp+var_20], rax
0x1800091c2  lea     rdx, aCurrentdirecto; "CurrentDirectoryPath"
0x1800091c9  mov     [rbp+var_18], r12
0x1800091cd  mov     [rbp+var_10], 1
0x1800091d1  call    cs:__imp_SRCacheContext_GetField_String
0x1800091d7  mov     edi, eax
0x1800091d9  test    eax, eax
0x1800091db  jns     short loc_1800091F7
0x1800091dd  mov     rcx, [rbp+38h]; this
0x1800091e1  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800091e8  mov     r9d, eax; char *
0x1800091eb  mov     edx, 246h; void *
0x1800091f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091f5  jmp     short loc_1800091FA
0x1800091f7  mov     edi, r12d
0x1800091fa  cmp     [rbp+var_10], r12b
0x1800091fe  jz      short loc_180009219
0x180009200  mov     rdx, [rbp+var_20]
0x180009204  mov     rax, [rbp+var_18]
0x180009208  mov     rcx, [rdx]
0x18000920b  mov     [rdx], rax
0x18000920e  test    rcx, rcx
0x180009211  jz      short loc_180009219
0x180009213  call    cs:__imp_SRCache_Free
0x180009219  test    edi, edi
0x18000921b  jns     short loc_18000923C
0x18000921d  mov     rcx, [rbp+38h]; this
0x180009221  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009228  mov     r9d, edi; char *
0x18000922b  mov     edx, 4A7h; void *
0x180009230  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009235  mov     eax, edi
0x180009237  jmp     loc_1800093D7
0x18000923c  test    rbx, rbx
0x18000923f  jz      short loc_180009248
0x180009241  bt      rbx, 9
0x180009246  jnb     short loc_18000929E
0x180009248  lea     rax, [rsi+48h]
0x18000924c  mov     [rbp+var_18], r12
0x180009250  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180009254  mov     [rbp+var_20], rax
0x180009258  lea     rdx, aExecutable; "Executable"
0x18000925f  mov     [rbp+var_10], 1
0x180009263  mov     rcx, r14; this
0x180009266  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)
0x18000926b  lea     rcx, [rbp+var_20]
0x18000926f  mov     edi, eax
0x180009271  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x180009276  test    edi, edi
0x180009278  jns     short loc_180009299
0x18000927a  mov     rcx, [rbp+38h]; this
0x18000927e  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009285  mov     r9d, edi; char *
0x180009288  mov     edx, 4ABh; void *
0x18000928d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009292  mov     eax, edi
0x180009294  jmp     loc_1800093D7
0x180009299  test    rbx, rbx
0x18000929c  jz      short loc_1800092A9
0x18000929e  bt      rbx, 0Ah
0x1800092a3  jnb     loc_180009341
0x1800092a9  mov     rcx, [r14]
0x1800092ac  lea     rax, [rsi+50h]
0x1800092b0  lea     r8, [rbp+var_18]
0x1800092b4  mov     [rbp+var_20], rax
0x1800092b8  lea     rdx, aEntrypoint; "Entrypoint"
0x1800092bf  mov     [rbp+var_18], r12
0x1800092c3  mov     [rbp+var_10], 1
0x1800092c7  call    cs:__imp_SRCacheContext_GetField_String
0x1800092cd  mov     edi, eax
0x1800092cf  test    eax, eax
0x1800092d1  jns     short loc_1800092ED
0x1800092d3  mov     rcx, [rbp+38h]; this
0x1800092d7  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800092de  mov     r9d, eax; char *
0x1800092e1  mov     edx, 246h; void *
0x1800092e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800092eb  jmp     short loc_1800092F0
0x1800092ed  mov     edi, r12d
0x1800092f0  cmp     [rbp+var_10], r12b
0x1800092f4  jz      short loc_18000930F
0x1800092f6  mov     rdx, [rbp+var_20]
  ... truncated ...
```
