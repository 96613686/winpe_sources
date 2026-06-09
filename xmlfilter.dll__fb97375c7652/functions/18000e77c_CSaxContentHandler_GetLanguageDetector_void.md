# CSaxContentHandler::GetLanguageDetector(void)

- ea: `0x18000e77c`
- end: `0x18000e8f9`
- name: `?GetLanguageDetector@CSaxContentHandler@@AEAAPEAVCLanguageDetector@@XZ`
- size: `381`
- prototype: `struct CLanguageDetector *__fastcall(CSaxContentHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f7e0`

## callees

- `0x18000213c`
- `0x180002148`
- `0x180005f70`
- `0x18000e77c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e87d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000e87d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e7ea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e8b7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e7ea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e8b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e83e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e852`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e83e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e852`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000e825`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000e825`

## string_xrefs

- `0x18000e81e`: `kernelbase.dll`
- `0x18000e887`: `[XmlFilter Language Detector] CLanguageDetector():Could not load CLCIDToLocaleNameConverter object`
- `0x18000e893`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\languagedetector.cpp"`

## pseudocode

```c
struct CLanguageDetector *__fastcall CSaxContentHandler::GetLanguageDetector(CSaxContentHandler *this)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  HMODULE v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rdi
  HMODULE LibraryW; // rax
  const wchar_t *v8; // r9
  _QWORD *v9; // rdi
  HMODULE v10; // rcx
  __int64 v11; // rcx

  if ( !*((_QWORD *)this + 1) )
  {
    v2 = operator new(0x28u);
    *v2 = 0;
    v2[1] = 0;
    v2[2] = 0;
    v2[3] = 0;
    *((_BYTE *)v2 + 32) = 0;
    v3 = (_QWORD *)*((_QWORD *)this + 1);
    if ( v3 != v2 )
    {
      if ( *((_BYTE *)this + 16) && v3 )
      {
        v4 = (HMODULE)v3[3];
        if ( v4 )
          FreeLibrary(v4);
        v5 = v3[2];
        if ( v5 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        operator delete(v3);
      }
      *((_QWORD *)this + 1) = v2;
    }
    *((_BYTE *)this + 16) = 1;
    v6 = *((_QWORD *)this + 1);
    LibraryW = LoadLibraryW(L"kernelbase.dll");
    *(_QWORD *)(v6 + 24) = LibraryW;
    if ( LibraryW )
    {
      *(_QWORD *)v6 = GetProcAddress(LibraryW, "LocaleNameToLCID");
      *(_QWORD *)(v6 + 8) = GetProcAddress(*(HMODULE *)(v6 + 24), "LCIDToLocaleName");
    }
    *(_BYTE *)(v6 + 32) = 1;
    if ( CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a, (LPVOID *)(v6 + 16)) < 0 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\languagedetector.cpp\"",
        (const wchar_t *)0x36,
        (unsigned int)L"[XmlFilter Language Detector] CLanguageDetector():Could not load CLCIDToLocaleNameConverter object",
        v8);
      v9 = (_QWORD *)*((_QWORD *)this + 1);
      if ( v9 )
      {
        if ( *((_BYTE *)this + 16) )
        {
          v10 = (HMODULE)v9[3];
          if ( v10 )
            FreeLibrary(v10);
          v11 = v9[2];
          if ( v11 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          operator delete(v9);
        }
        *((_QWORD *)this + 1) = 0;
      }
      *((_BYTE *)this + 16) = 0;
    }
  }
  return (struct CLanguageDetector *)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x18000e77c  push    rbx
0x18000e77e  push    rsi
0x18000e77f  push    rdi
0x18000e780  push    r14
0x18000e782  sub     rsp, 38h
0x18000e786  mov     rbx, rcx
0x18000e789  cmp     qword ptr [rcx+8], 0
0x18000e78e  jnz     loc_18000E8EB
0x18000e794  mov     r14d, 28h ; '('
0x18000e79a  mov     ecx, r14d; Size
0x18000e79d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e7a2  mov     rdi, rax
0x18000e7a5  mov     [rsp+58h+arg_0], rax
0x18000e7aa  mov     qword ptr [rax], 0
0x18000e7b1  mov     qword ptr [rax+8], 0
0x18000e7b9  mov     qword ptr [rax+10h], 0
0x18000e7c1  mov     qword ptr [rax+18h], 0
0x18000e7c9  mov     byte ptr [rax+20h], 0
0x18000e7cd  mov     rsi, [rbx+8]
0x18000e7d1  cmp     rsi, rax
0x18000e7d4  jz      short loc_18000E816
0x18000e7d6  cmp     byte ptr [rbx+10h], 0
0x18000e7da  jz      short loc_18000E812
0x18000e7dc  test    rsi, rsi
0x18000e7df  jz      short loc_18000E812
0x18000e7e1  mov     rcx, [rsi+18h]; hLibModule
0x18000e7e5  test    rcx, rcx
0x18000e7e8  jz      short loc_18000E7F1
0x18000e7ea  call    cs:__imp_FreeLibrary
0x18000e7f0  nop
0x18000e7f1  mov     rcx, [rsi+10h]
0x18000e7f5  test    rcx, rcx
0x18000e7f8  jz      short loc_18000E807
0x18000e7fa  mov     rax, [rcx]
0x18000e7fd  mov     rax, [rax+10h]
0x18000e801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e806  nop
0x18000e807  mov     rdx, r14
0x18000e80a  mov     rcx, rsi; Block
0x18000e80d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e812  mov     [rbx+8], rdi
0x18000e816  mov     byte ptr [rbx+10h], 1
0x18000e81a  mov     rdi, [rbx+8]
0x18000e81e  lea     rcx, LibFileName; "kernelbase.dll"
0x18000e825  call    cs:__imp_LoadLibraryW
0x18000e82b  mov     [rdi+18h], rax
0x18000e82f  test    rax, rax
0x18000e832  jz      short loc_18000E85C
0x18000e834  lea     rdx, aLocalenametolc; "LocaleNameToLCID"
0x18000e83b  mov     rcx, rax; hModule
0x18000e83e  call    cs:__imp_GetProcAddress
0x18000e844  mov     [rdi], rax
0x18000e847  lea     rdx, aLcidtolocalena; "LCIDToLocaleName"
0x18000e84e  mov     rcx, [rdi+18h]; hModule
0x18000e852  call    cs:__imp_GetProcAddress
0x18000e858  mov     [rdi+8], rax
0x18000e85c  mov     byte ptr [rdi+20h], 1
0x18000e860  lea     rax, [rdi+10h]
0x18000e864  mov     [rsp+58h+ppv], rax; ppv
0x18000e869  lea     r9, _GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a; riid
0x18000e870  xor     edx, edx; pUnkOuter
0x18000e872  lea     r8d, [rdx+1]; dwClsContext
0x18000e876  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18000e87d  call    cs:__imp_CoCreateInstance
0x18000e883  test    eax, eax
0x18000e885  jns     short loc_18000E8EB
0x18000e887  lea     r8, aXmlfilterLangu; "[XmlFilter Language Detector] CLanguage"...
0x18000e88e  mov     edx, 36h ; '6'; wchar_t *
0x18000e893  lea     rcx, aOnecoreuapBase_7; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000e89a  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000e89f  mov     rdi, [rbx+8]
0x18000e8a3  test    rdi, rdi
0x18000e8a6  jz      short loc_18000E8E7
0x18000e8a8  cmp     byte ptr [rbx+10h], 0
0x18000e8ac  jz      short loc_18000E8DF
0x18000e8ae  mov     rcx, [rdi+18h]; hLibModule
0x18000e8b2  test    rcx, rcx
0x18000e8b5  jz      short loc_18000E8BE
0x18000e8b7  call    cs:__imp_FreeLibrary
0x18000e8bd  nop
0x18000e8be  mov     rcx, [rdi+10h]
0x18000e8c2  test    rcx, rcx
0x18000e8c5  jz      short loc_18000E8D4
0x18000e8c7  mov     rax, [rcx]
0x18000e8ca  mov     rax, [rax+10h]
0x18000e8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8d3  nop
0x18000e8d4  mov     rdx, r14
0x18000e8d7  mov     rcx, rdi; Block
0x18000e8da  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e8df  mov     qword ptr [rbx+8], 0
0x18000e8e7  mov     byte ptr [rbx+10h], 0
0x18000e8eb  mov     rax, [rbx+8]
0x18000e8ef  add     rsp, 38h
0x18000e8f3  pop     r14
0x18000e8f5  pop     rdi
0x18000e8f6  pop     rsi
0x18000e8f7  pop     rbx
0x18000e8f8  retn
```
