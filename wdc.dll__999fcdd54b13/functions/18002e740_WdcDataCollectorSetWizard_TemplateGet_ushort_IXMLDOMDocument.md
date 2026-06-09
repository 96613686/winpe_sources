# WdcDataCollectorSetWizard::TemplateGet(ushort *,IXMLDOMDocument * *)

- ea: `0x18002e740`
- end: `0x18002ea31`
- name: `?TemplateGet@WdcDataCollectorSetWizard@@AEAAJPEAGPEAPEAUIXMLDOMDocument@@@Z`
- size: `753`
- prototype: `int(WdcDataCollectorSetWizard *__hidden this, unsigned __int16 *, struct IXMLDOMDocument **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180025050`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18002aa2c`
- `0x18002e740`
- `0x180033058`
- `0x18005b4e0`
- `0x180067730`
- `0x180086010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002e7f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002e832`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002e7f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002e832`
- `KERNEL32!GetLastError` at `0x18002e80b`
- `KERNEL32!GetLastError` at `0x18002e8a5`
- `KERNEL32!GetLastError` at `0x18002e80b`
- `KERNEL32!GetLastError` at `0x18002e8a5`
- `KERNEL32!FreeLibrary` at `0x18002e9cb`
- `KERNEL32!FreeLibrary` at `0x18002e9cb`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e906`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e906`
- `OLEAUT32!__imp_VariantInit` at `0x18002e779`
- `OLEAUT32!__imp_VariantInit` at `0x18002e779`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8f5`
- `OLEAUT32!__imp_VariantClear` at `0x18002e9d5`
- `OLEAUT32!__imp_VariantClear` at `0x18002e8f5`
- `OLEAUT32!__imp_VariantClear` at `0x18002e9d5`

## string_xrefs

- `0x18002e7a6`: `WdcDataCollectorSetWizard::TemplateGet`
- `0x18002e8d9`: `WdcDataCollectorSetWizard::TemplateGet`
- `0x18002e9b0`: `WdcDataCollectorSetWizard::TemplateGet`

## pseudocode

```c
__int64 __fastcall WdcDataCollectorSetWizard::TemplateGet(
        WdcDataCollectorSetWizard *this,
        unsigned __int16 *a2,
        struct IXMLDOMDocument **a3)
{
  const char *v5; // rdx
  int v6; // r8d
  unsigned __int64 v7; // rdx
  unsigned __int16 *v8; // rdi
  signed int v9; // ebx
  int v10; // eax
  wchar_t *v11; // rax
  HMODULE LibraryW; // rax
  HINSTANCE v13; // rsi
  signed int LastError; // eax
  wchar_t *v15; // rax
  const unsigned __int16 *v16; // r8
  int v17; // eax
  VARTYPE v18; // ax
  signed int v19; // eax
  BSTR v20; // rax
  const char *v21; // rdx
  int v22; // r8d
  __int64 v24; // [rsp+20h] [rbp-30h]
  __int64 v25; // [rsp+20h] [rbp-30h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  struct IXMLDOMDocument *v27; // [rsp+70h] [rbp+20h] BYREF
  struct IStream *v28; // [rsp+88h] [rbp+38h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v28 = 0;
  v27 = 0;
  VariantInit(&pvarg);
  v8 = (unsigned __int16 *)WdcAlloc(0x800u, v5, v6);
  if ( !v8 )
    goto LABEL_2;
  *v8 = 0;
  v10 = WdcExpandVariables(v8, v7, a2);
  v9 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v24) = v10;
    goto LABEL_3;
  }
  if ( *v8 != 64 )
  {
    VariantClear(&pvarg);
    pvarg.llVal = 0;
    v20 = SysAllocString(v8);
    if ( !v20 )
    {
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
        "WdcAssignString",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      LODWORD(v25) = -2147024882;
      WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp", "WdcAssignString", 0, L"FAILURE: 0x%08x", v25);
LABEL_2:
      v9 = -2147024882;
      LODWORD(v24) = -2147024882;
LABEL_3:
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetwizard.cpp",
        "WdcDataCollectorSetWizard::TemplateGet",
        0,
        L"FAILURE: 0x%08x",
        v24);
      goto LABEL_35;
    }
    v13 = 0;
    pvarg.llVal = (LONGLONG)v20;
    v18 = 8;
    goto LABEL_30;
  }
  v11 = wcstok(v8, L"@, ", 0);
  LibraryW = IsolationAwareLoadLibraryW(v11);
  v13 = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( v9 >= 0 )
        goto LABEL_12;
    }
    else
    {
      v9 = -2147467259;
    }
    LODWORD(v24) = v9;
    goto LABEL_3;
  }
  if ( LibraryW != (HMODULE)-1LL )
  {
LABEL_12:
    v15 = wcstok(0, L", ", 0);
    if ( *v15 == 45 )
      *v15 = 35;
    v17 = WdcCreateStreamFromResource(v13, v15, v16, &v28);
    v9 = v17;
    if ( v17 < 0 )
      goto LABEL_32;
    v17 = (**(__int64 (__fastcall ***)(struct IStream *, GUID *, ULONG *))v28)(
            v28,
            &IID_IUnknown,
            (ULONG *)&pvarg.cyVal);
    v9 = v17;
    if ( v17 < 0 )
      goto LABEL_32;
    v18 = 13;
LABEL_30:
    pvarg.vt = v18;
    v17 = WdcCreateXmlDocument(&v27, &pvarg, 0, 0);
    v9 = v17;
    if ( v17 >= 0 )
    {
      v17 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, GUID *, struct IXMLDOMDocument **))v27->lpVtbl->QueryInterface)(
              v27,
              &IID_IXMLDOMDocument,
              a3);
      v9 = v17;
      if ( v17 >= 0 )
      {
LABEL_33:
        if ( !v13 )
          goto LABEL_35;
        goto LABEL_34;
      }
    }
LABEL_32:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetwizard.cpp",
      "WdcDataCollectorSetWizard::TemplateGet",
      0,
      L"FAILURE: 0x%08x",
      v17);
    goto LABEL_33;
  }
  v19 = GetLastError();
  v9 = v19;
  if ( v19 )
  {
    if ( v19 > 0 )
      v9 = (unsigned __int16)v19 | 0x80070000;
    if ( v9 >= 0 )
      goto LABEL_12;
  }
  else
  {
    v9 = -2147467259;
  }
  WdcDebugMessage(
    "base\\diagnosis\\pdui\\perfmon\\mmc\\datacollectorsetwizard.cpp",
    "WdcDataCollectorSetWizard::TemplateGet",
    0,
    L"FAILURE: 0x%08x",
    v9);
LABEL_34:
  FreeLibrary(v13);
LABEL_35:
  VariantClear(&pvarg);
  if ( v8 )
    WdcFree(v8, v21, v22);
  if ( v27 )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument *))v27->lpVtbl->Release)(v27);
    v27 = 0;
  }
  if ( v28 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v28 + 16LL))(v28);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002e740  mov     [rsp-18h+arg_8], rbx
0x18002e745  mov     [rsp-18h+arg_10], rsi
0x18002e74a  mov     [rsp-18h+arg_0], rcx
0x18002e74f  push    rbp
0x18002e750  push    rdi
0x18002e751  push    r14
0x18002e753  mov     rbp, rsp
0x18002e756  sub     rsp, 50h
0x18002e75a  xor     eax, eax
0x18002e75c  lea     rcx, [rbp+pvarg]; pvarg
0x18002e760  xorps   xmm0, xmm0
0x18002e763  mov     qword ptr [rbp+pvarg+10h], rax
0x18002e767  movups  xmmword ptr [rbp+pvarg], xmm0
0x18002e76b  mov     [rbp+arg_18], rax
0x18002e76f  mov     r14, r8
0x18002e772  mov     [rbp+arg_0], rax
0x18002e776  mov     rbx, rdx
0x18002e779  call    cs:__imp_VariantInit
0x18002e77f  mov     ecx, 800h; dwBytes
0x18002e784  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002e789  mov     rdi, rax
0x18002e78c  test    rax, rax
0x18002e78f  jnz     short loc_18002E7BE
0x18002e791  mov     esi, 8007000Eh
0x18002e796  mov     ebx, esi
0x18002e798  mov     [rsp+50h+var_30], esi
0x18002e79c  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002e7a3  xor     r8d, r8d; int
0x18002e7a6  lea     rdx, aWdcdatacollect_19; "WdcDataCollectorSetWizard::TemplateGet"
0x18002e7ad  lea     rcx, aBaseDiagnosisP_0; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18002e7b4  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002e7b9  jmp     loc_18002E9D1
0x18002e7be  xor     eax, eax
0x18002e7c0  mov     r8, rbx; unsigned __int16 *
0x18002e7c3  mov     rcx, rdi; unsigned __int16 *
0x18002e7c6  mov     [rdi], ax
0x18002e7c9  call    ?WdcExpandVariables@@YAJPEAG_KPEBG@Z; WdcExpandVariables(ushort *,unsigned __int64,ushort const *)
0x18002e7ce  mov     ebx, eax
0x18002e7d0  test    eax, eax
0x18002e7d2  jns     short loc_18002E7DA
0x18002e7d4  mov     [rsp+50h+var_30], eax
0x18002e7d8  jmp     short loc_18002E79C
0x18002e7da  cmp     word ptr [rdi], 40h ; '@'
0x18002e7de  jnz     loc_18002E8F1
0x18002e7e4  xor     r8d, r8d; Context
0x18002e7e7  lea     rdx, asc_180093780; "@, "
0x18002e7ee  mov     rcx, rdi; String
0x18002e7f1  call    cs:__imp_wcstok
0x18002e7f7  mov     rcx, rax; lpLibFileName
0x18002e7fa  call    IsolationAwareLoadLibraryW
0x18002e7ff  mov     rsi, rax
0x18002e802  test    rax, rax
0x18002e805  jnz     loc_18002E89F
0x18002e80b  call    cs:__imp_GetLastError
0x18002e811  mov     ebx, eax
0x18002e813  test    eax, eax
0x18002e815  jz      short loc_18002E891
0x18002e817  jle     short loc_18002E822
0x18002e819  movzx   ebx, ax
0x18002e81c  or      ebx, 80070000h
0x18002e822  test    ebx, ebx
0x18002e824  js      short loc_18002E896
0x18002e826  xor     r8d, r8d; Context
0x18002e829  lea     rdx, asc_180093788; ", "
0x18002e830  xor     ecx, ecx; String
0x18002e832  call    cs:__imp_wcstok
0x18002e838  mov     ecx, 2Dh ; '-'
0x18002e83d  cmp     cx, [rax]
0x18002e840  jnz     short loc_18002E84A
0x18002e842  mov     ecx, 23h ; '#'
0x18002e847  mov     [rax], cx
0x18002e84a  lea     r9, [rbp+arg_18]; struct IStream **
0x18002e84e  mov     rdx, rax; unsigned __int16 *
0x18002e851  mov     rcx, rsi; hModule
0x18002e854  call    ?WdcCreateStreamFromResource@@YAJPEAUHINSTANCE__@@PEBG1PEAPEAUIStream@@@Z; WdcCreateStreamFromResource(HINSTANCE__ *,ushort const *,ushort const *,IStream * *)
0x18002e859  mov     ebx, eax
0x18002e85b  test    eax, eax
0x18002e85d  js      loc_18002E9A2
0x18002e863  mov     rcx, [rbp+arg_18]
0x18002e867  lea     r8, [rbp+pvarg+8]
0x18002e86b  lea     rdx, IID_IUnknown
0x18002e872  mov     rax, [rcx]
0x18002e875  mov     rax, [rax]
0x18002e878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e87d  mov     ebx, eax
0x18002e87f  test    eax, eax
0x18002e881  js      loc_18002E9A2
0x18002e887  mov     eax, 0Dh
0x18002e88c  jmp     loc_18002E966
0x18002e891  mov     ebx, 80004005h
0x18002e896  mov     [rsp+50h+var_30], ebx
0x18002e89a  jmp     loc_18002E79C
0x18002e89f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002e8a3  jnz     short loc_18002E826
0x18002e8a5  call    cs:__imp_GetLastError
0x18002e8ab  mov     ebx, eax
0x18002e8ad  test    eax, eax
0x18002e8af  jz      short loc_18002E8C6
0x18002e8b1  jle     short loc_18002E8BC
0x18002e8b3  movzx   ebx, ax
0x18002e8b6  or      ebx, 80070000h
0x18002e8bc  test    ebx, ebx
0x18002e8be  jns     loc_18002E826
0x18002e8c4  jmp     short loc_18002E8CB
0x18002e8c6  mov     ebx, 80004005h
0x18002e8cb  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002e8d2  mov     [rsp+50h+var_30], ebx
0x18002e8d6  xor     r8d, r8d; int
0x18002e8d9  lea     rdx, aWdcdatacollect_19; "WdcDataCollectorSetWizard::TemplateGet"
0x18002e8e0  lea     rcx, aBaseDiagnosisP_0; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18002e8e7  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002e8ec  jmp     loc_18002E9C8
0x18002e8f1  lea     rcx, [rbp+pvarg]; pvarg
0x18002e8f5  call    cs:__imp_VariantClear
0x18002e8fb  mov     rcx, rdi; psz
0x18002e8fe  mov     qword ptr [rbp+pvarg+8], 0
0x18002e906  call    cs:__imp_SysAllocString
0x18002e90c  test    rax, rax
0x18002e90f  jnz     short loc_18002E95D
0x18002e911  mov     esi, 8007000Eh
0x18002e916  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002e91d  xor     r8d, r8d; int
0x18002e920  mov     [rsp+50h+var_30], esi
0x18002e924  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18002e92b  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18002e932  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002e937  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002e93e  mov     [rsp+50h+var_30], esi
0x18002e942  xor     r8d, r8d; int
0x18002e945  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x18002e94c  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x18002e953  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002e958  jmp     loc_18002E796
0x18002e95d  xor     esi, esi
0x18002e95f  mov     qword ptr [rbp+pvarg+8], rax
0x18002e963  lea     eax, [rsi+8]
0x18002e966  xor     r9d, r9d; struct IXMLDOMParseError **
0x18002e969  mov     word ptr [rbp+pvarg], ax
0x18002e96d  xor     r8d, r8d; unsigned __int16 *
0x18002e970  lea     rdx, [rbp+pvarg]; struct tagVARIANT *
0x18002e974  lea     rcx, [rbp+arg_0]; struct IXMLDOMDocument **
0x18002e978  call    ?WdcCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@PEAUtagVARIANT@@PEAGPEAPEAUIXMLDOMParseError@@@Z; WdcCreateXmlDocument(IXMLDOMDocument * *,tagVARIANT *,ushort *,IXMLDOMParseError * *)
0x18002e97d  mov     ebx, eax
0x18002e97f  test    eax, eax
0x18002e981  js      short loc_18002E9A2
0x18002e983  mov     rcx, [rbp+arg_0]
0x18002e987  lea     rdx, IID_IXMLDOMDocument
0x18002e98e  mov     r8, r14
0x18002e991  mov     rax, [rcx]
0x18002e994  mov     rax, [rax]
0x18002e997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e99c  mov     ebx, eax
0x18002e99e  test    eax, eax
0x18002e9a0  jns     short loc_18002E9C3
0x18002e9a2  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002e9a9  mov     [rsp+50h+var_30], eax
0x18002e9ad  xor     r8d, r8d; int
0x18002e9b0  lea     rdx, aWdcdatacollect_19; "WdcDataCollectorSetWizard::TemplateGet"
0x18002e9b7  lea     rcx, aBaseDiagnosisP_0; "base\\diagnosis\\pdui\\perfmon\\mmc\\da"...
0x18002e9be  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002e9c3  test    rsi, rsi
0x18002e9c6  jz      short loc_18002E9D1
0x18002e9c8  mov     rcx, rsi; hLibModule
0x18002e9cb  call    cs:__imp_FreeLibrary
0x18002e9d1  lea     rcx, [rbp+pvarg]; pvarg
0x18002e9d5  call    cs:__imp_VariantClear
0x18002e9db  test    rdi, rdi
0x18002e9de  jz      short loc_18002E9E8
0x18002e9e0  mov     rcx, rdi; void *
0x18002e9e3  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18002e9e8  mov     rcx, [rbp+arg_0]
0x18002e9ec  test    rcx, rcx
0x18002e9ef  jz      short loc_18002EA05
0x18002e9f1  mov     rax, [rcx]
0x18002e9f4  mov     rax, [rax+10h]
0x18002e9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9fd  mov     [rbp+arg_0], 0
0x18002ea05  mov     rcx, [rbp+arg_18]
0x18002ea09  test    rcx, rcx
0x18002ea0c  jz      short loc_18002EA1A
0x18002ea0e  mov     rax, [rcx]
0x18002ea11  mov     rax, [rax+10h]
0x18002ea15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea1a  lea     r11, [rsp+50h+var_s0]
0x18002ea1f  mov     eax, ebx
0x18002ea21  mov     rbx, [r11+28h]
0x18002ea25  mov     rsi, [r11+30h]
0x18002ea29  mov     rsp, r11
0x18002ea2c  pop     r14
0x18002ea2e  pop     rdi
0x18002ea2f  pop     rbp
0x18002ea30  retn
```
