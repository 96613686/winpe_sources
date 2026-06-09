# MrtHelper::ConvertFileUriToFilePath(ushort const *,ushort * *)

- ea: `0x18001ed80`
- end: `0x18001ef4a`
- name: `?ConvertFileUriToFilePath@MrtHelper@@AEAAJPEBGPEAPEAG@Z`
- size: `458`
- prototype: `int(MrtHelper *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ea90`
- `0x1800c5510`

## callees

- `0x180004e38`
- `0x18000de40`
- `0x180011618`
- `0x18001ed80`
- `0x18001ef74`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ee96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ee96`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ee6c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef02`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef0a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ee6c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef02`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ef0a`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18001edbb`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x18001edbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MrtHelper::ConvertFileUriToFilePath(MrtHelper *this, const unsigned __int16 *a2, LPVOID *a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  struct IUriVtbl *lpVtbl; // rax
  int v8; // eax
  IUri *v9; // rcx
  IUri *v11; // rcx
  IUri *v12; // rcx
  IUri *v13; // rcx
  LPVOID pv; // [rsp+20h] [rbp-20h] BYREF
  __int64 v15; // [rsp+28h] [rbp-18h] BYREF
  __int64 v16; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  IUri *ppURI; // [rsp+60h] [rbp+20h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+30h] BYREF

  *a3 = 0;
  ppURI = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppURI);
  v5 = CreateUri(a2, 0x8020u, 0, &ppURI);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
      (const char *)(unsigned int)v5,
      (int)pv);
    v13 = ppURI;
    if ( ppURI )
    {
      ppURI = 0;
      ((void (__fastcall *)(IUri *))v13->lpVtbl->Release)(v13);
    }
    return v6;
  }
  bstrString = 0;
  lpVtbl = ppURI->lpVtbl;
  pv = &bstrString;
  v15 = 0;
  LOBYTE(v16) = 1;
  v6 = ((__int64 (__fastcall *)(IUri *, __int64 *))lpVtbl->GetPath)(ppURI, &v15);
  if ( (_BYTE)v16 )
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      pv,
      v15);
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
      (const char *)v6,
      (int)pv);
    if ( bstrString )
      SysFreeString(bstrString);
    v12 = ppURI;
    if ( ppURI )
    {
      ppURI = 0;
      ((void (__fastcall *)(IUri *))v12->lpVtbl->Release)(v12);
    }
    return v6;
  }
  pv = 0;
  v15 = 0;
  v16 = 0;
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         (__int64)&pv,
         bstrString,
         0xFFFFFFFFFFFFFFFFuLL);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\mrthelper.cpp",
      (const char *)(unsigned int)v8,
      (int)pv);
    if ( pv )
      CoTaskMemFree(pv);
    if ( bstrString )
      SysFreeString(bstrString);
    v11 = ppURI;
    if ( ppURI )
    {
      ppURI = 0;
      ((void (__fastcall *)(IUri *))v11->lpVtbl->Release)(v11);
    }
    return v6;
  }
  *a3 = pv;
  if ( bstrString )
    SysFreeString(bstrString);
  v9 = ppURI;
  if ( ppURI )
  {
    ppURI = 0;
    ((void (__fastcall *)(IUri *))v9->lpVtbl->Release)(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ed80  mov     [rsp-18h+arg_8], rbx
0x18001ed85  mov     [rsp-18h+ppURI], rcx
0x18001ed8a  push    rbp
0x18001ed8b  push    rsi
0x18001ed8c  push    rdi
0x18001ed8d  mov     rbp, rsp
0x18001ed90  sub     rsp, 40h
0x18001ed94  mov     rdi, r8
0x18001ed97  mov     rbx, rdx
0x18001ed9a  xor     esi, esi
0x18001ed9c  mov     [r8], rsi
0x18001ed9f  mov     [rbp+ppURI], rsi
0x18001eda3  lea     rcx, [rbp+ppURI]
0x18001eda7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001edac  lea     r9, [rbp+ppURI]; ppURI
0x18001edb0  xor     r8d, r8d; dwReserved
0x18001edb3  mov     edx, 8020h; dwFlags
0x18001edb8  mov     rcx, rbx; pwzURI
0x18001edbb  call    cs:__imp_CreateUri
0x18001edc1  mov     ebx, eax
0x18001edc3  test    eax, eax
0x18001edc5  js      loc_18001EF12
0x18001edcb  mov     [rbp+bstrString], rsi
0x18001edcf  mov     rcx, [rbp+ppURI]
0x18001edd3  mov     rax, [rcx]
0x18001edd6  lea     rdx, [rbp+bstrString]
0x18001edda  mov     [rbp+pv], rdx
0x18001edde  mov     [rbp+var_18], rsi
0x18001ede2  mov     byte ptr [rbp+var_10], 1
0x18001ede6  lea     rdx, [rbp+var_18]
0x18001edea  mov     rax, [rax+78h]
0x18001edee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edf3  mov     ebx, eax
0x18001edf5  cmp     byte ptr [rbp+var_10], sil
0x18001edf9  jz      short loc_18001EE08
0x18001edfb  mov     rdx, [rbp+var_18]
0x18001edff  mov     rcx, [rbp+pv]
0x18001ee03  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001ee08  test    ebx, ebx
0x18001ee0a  js      loc_18001EEC4
0x18001ee10  mov     [rbp+pv], rsi
0x18001ee14  mov     [rbp+var_18], rsi
0x18001ee18  mov     [rbp+var_10], rsi
0x18001ee1c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001ee20  mov     rdx, [rbp+bstrString]
0x18001ee24  lea     rcx, [rbp+pv]
0x18001ee28  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001ee2d  mov     ebx, eax
0x18001ee2f  test    eax, eax
0x18001ee31  js      short loc_18001EE75
0x18001ee33  mov     rax, [rbp+pv]
0x18001ee37  mov     [rdi], rax
0x18001ee3a  mov     rcx, [rbp+bstrString]; bstrString
0x18001ee3e  test    rcx, rcx
0x18001ee41  jnz     short loc_18001EE6C
0x18001ee43  mov     rcx, [rbp+ppURI]
0x18001ee47  test    rcx, rcx
0x18001ee4a  jz      short loc_18001EE5D
0x18001ee4c  mov     [rbp+ppURI], rsi
0x18001ee50  mov     rax, [rcx]
0x18001ee53  mov     rax, [rax+10h]
0x18001ee57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee5c  nop
0x18001ee5d  xor     eax, eax
0x18001ee5f  mov     rbx, [rsp+40h+arg_8]
0x18001ee64  add     rsp, 40h
0x18001ee68  pop     rdi
0x18001ee69  pop     rsi
0x18001ee6a  pop     rbp
0x18001ee6b  retn
0x18001ee6c  call    cs:__imp_SysFreeString
0x18001ee72  nop
0x18001ee73  jmp     short loc_18001EE43
0x18001ee75  mov     rcx, [rbp+18h]; this
0x18001ee79  mov     r9d, ebx; char *
0x18001ee7c  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ee83  mov     edx, 99h; void *
0x18001ee88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ee8d  mov     rcx, [rbp+pv]; pv
0x18001ee91  test    rcx, rcx
0x18001ee94  jz      short loc_18001EE9D
0x18001ee96  call    cs:__imp_CoTaskMemFree
0x18001ee9c  nop
0x18001ee9d  mov     rcx, [rbp+bstrString]; bstrString
0x18001eea1  test    rcx, rcx
0x18001eea4  jnz     short loc_18001EF02
0x18001eea6  mov     rcx, [rbp+ppURI]
0x18001eeaa  test    rcx, rcx
0x18001eead  jz      short loc_18001EEC0
0x18001eeaf  mov     [rbp+ppURI], rsi
0x18001eeb3  mov     rax, [rcx]
0x18001eeb6  mov     rax, [rax+10h]
0x18001eeba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eebf  nop
0x18001eec0  mov     eax, ebx
0x18001eec2  jmp     short loc_18001EE5F
0x18001eec4  mov     rcx, [rbp+18h]; this
0x18001eec8  mov     r9d, ebx; char *
0x18001eecb  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001eed2  mov     edx, 96h; void *
0x18001eed7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eedc  nop
0x18001eedd  mov     rcx, [rbp+bstrString]; bstrString
0x18001eee1  test    rcx, rcx
0x18001eee4  jnz     short loc_18001EF0A
0x18001eee6  mov     rcx, [rbp+ppURI]
0x18001eeea  test    rcx, rcx
0x18001eeed  jz      short loc_18001EF00
0x18001eeef  mov     [rbp+ppURI], rsi
0x18001eef3  mov     rax, [rcx]
0x18001eef6  mov     rax, [rax+10h]
0x18001eefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eeff  nop
0x18001ef00  jmp     short loc_18001EEC0
0x18001ef02  call    cs:__imp_SysFreeString
0x18001ef08  jmp     short loc_18001EEA6
0x18001ef0a  call    cs:__imp_SysFreeString
0x18001ef10  jmp     short loc_18001EEE6
0x18001ef12  mov     rcx, [rbp+18h]; this
0x18001ef16  mov     r9d, ebx; char *
0x18001ef19  lea     r8, aOnecoreuapBase_131; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001ef20  mov     edx, 93h; void *
0x18001ef25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef2a  nop
0x18001ef2b  mov     rcx, [rbp+ppURI]
0x18001ef2f  test    rcx, rcx
0x18001ef32  jz      short loc_18001EF45
0x18001ef34  mov     [rbp+ppURI], rsi
0x18001ef38  mov     rax, [rcx]
0x18001ef3b  mov     rax, [rax+10h]
0x18001ef3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef44  nop
0x18001ef45  jmp     loc_18001EEC0
```
