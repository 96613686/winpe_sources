# RequestUrl::Initialize(ushort const *)

- ea: `0x180015df0`
- end: `0x1800163de`
- name: `?Initialize@RequestUrl@@QEAAXPEBG@Z`
- size: `1518`
- prototype: `void __fastcall(IUri **ppURI, LPCWSTR pwzURI)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016ec0`
- `0x18001a480`
- `0x18001b428`

## callees

- `0x180015df0`
- `0x180016aa0`
- `0x180016b10`
- `0x18004f860`
- `0x18005616c`
- `0x180064ec8`
- `0x180066010`
- `0x180080fb0`
- `0x180084259`
- `0x1800c6010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180016027`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180016027`
- `OLEAUT32!__imp_SysFreeString` at `0x18001630d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001636a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001639d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001630d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001636a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001639d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016315`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016372`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800163a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016315`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016372`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800163a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001635f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016302`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001635f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016392`
- `iertutil!CreateUri` at `0x180015e3b`
- `iertutil!CreateUri` at `0x180015e3b`
- `iertutil!CreateIUriBuilder` at `0x18001607e`
- `iertutil!CreateIUriBuilder` at `0x18001607e`

## string_xrefs

- `0x180016227`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x18001624d`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x180016262`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x180016287`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x18001629c`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x1800162b1`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x1800162c6`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x1800162db`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x1800162f0`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x180016323`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x180016338`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x18001634d`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x180016380`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`
- `0x1800163b7`: `onecoreuap\inetcore\webplatstorageserver\cachestorage\requesturl.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall RequestUrl::Initialize(IUri **ppURI, LPCWSTR pwzURI)
{
  IUri *v4; // rcx
  HRESULT Uri; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  IUri *v9; // rsi
  HRESULT (__stdcall *GetAbsoluteUri)(IUri *, BSTR *); // r12
  OLECHAR *v11; // r15
  int v12; // eax
  __int64 v13; // rax
  IUri *v14; // rdi
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // r15
  void *v17; // r12
  __int128 *v18; // r8
  unsigned __int64 v19; // rdx
  unsigned __int64 i; // rax
  __int64 v21; // rcx
  HRESULT v22; // eax
  IUri *v23; // rsi
  HRESULT (__stdcall *GetQuery)(IUri *, BSTR *); // r12
  OLECHAR *v25; // r15
  int v26; // eax
  int v27; // eax
  struct IUriBuilderVtbl *lpVtbl; // rax
  int v29; // eax
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, IUri **); // r12
  OLECHAR *v32; // r15
  int v33; // eax
  IUri *v34; // rsi
  HRESULT (__stdcall *GetFragment)(IUri *, BSTR *); // rdi
  int v36; // eax
  int v37; // eax
  IUriBuilder *v38; // rdi
  HRESULT (__stdcall *CreateUriSimple)(IUriBuilder *, DWORD, DWORD_PTR, IUri **); // rbx
  int v40; // eax
  DWORD LastError; // ebx
  DWORD v42; // ebx
  DWORD v43; // ebx
  int v44; // [rsp+20h] [rbp-50h]
  IUriBuilder *ppIUriBuilder; // [rsp+30h] [rbp-40h] BYREF
  int v46; // [rsp+38h] [rbp-38h] BYREF
  int v47; // [rsp+3Ch] [rbp-34h] BYREF
  __int64 v48; // [rsp+40h] [rbp-30h] BYREF
  __int128 v49; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v50; // [rsp+58h] [rbp-18h]
  __int64 v51; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v4 = *ppURI;
  *ppURI = 0;
  if ( v4 )
    ((void (__fastcall *)(IUri *))v4->lpVtbl->Release)(v4);
  Uri = CreateUri(pwzURI, 0x3002B80u, 0, ppURI);
  if ( Uri < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
      (const char *)(unsigned int)Uri,
      v44);
  LODWORD(ppIUriBuilder) = 0;
  v6 = ((__int64 (__fastcall *)(_QWORD, IUriBuilder **))(*ppURI)->lpVtbl->GetScheme)(*ppURI, &ppIUriBuilder);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
      (const char *)(unsigned int)v6,
      v44);
  if ( (_DWORD)ppIUriBuilder != 11 && (_DWORD)ppIUriBuilder != 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
      (const char *)0x8070F005LL,
      v44);
  v46 = 0;
  v47 = 0;
  v7 = ((__int64 (__fastcall *)(_QWORD, __int64, int *))(*ppURI)->lpVtbl->HasProperty)(*ppURI, 5, &v46);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
      (const char *)(unsigned int)v7,
      v44);
  v8 = ((__int64 (__fastcall *)(_QWORD, __int64, int *))(*ppURI)->lpVtbl->HasProperty)(*ppURI, 10, &v47);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
      (const char *)(unsigned int)v8,
      v44);
  if ( v46 || v47 )
  {
    ppIUriBuilder = 0;
    v22 = CreateIUriBuilder(*ppURI, 0, 0, &ppIUriBuilder);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
        (const char *)(unsigned int)v22,
        v44);
    if ( v46 )
    {
      v34 = *ppURI;
      GetFragment = (*ppURI)->lpVtbl->GetFragment;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        ppURI + 4,
        0);
      v36 = ((__int64 (__fastcall *)(IUri *, IUri **))GetFragment)(v34, ppURI + 4);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
          (const char *)(unsigned int)v36,
          v44);
      v37 = ((__int64 (__fastcall *)(IUriBuilder *, __int64))ppIUriBuilder->lpVtbl->RemoveProperties)(ppIUriBuilder, 32);
      if ( v37 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2C,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
          (const char *)(unsigned int)v37,
          v44);
      wil::com_ptr_t<IUri,wil::err_exception_policy>::reset(ppURI);
      v38 = ppIUriBuilder;
      CreateUriSimple = ppIUriBuilder->lpVtbl->CreateUriSimple;
      wil::com_ptr_t<IUri,wil::err_exception_policy>::reset(ppURI);
      v40 = ((__int64 (__fastcall *)(IUriBuilder *, _QWORD, _QWORD, IUri **))CreateUriSimple)(v38, 0, 0, ppURI);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
          (const char *)(unsigned int)v40,
          v44);
    }
    if ( v47 )
    {
      v23 = *ppURI;
      GetQuery = (*ppURI)->lpVtbl->GetQuery;
      v25 = (OLECHAR *)ppURI[3];
      if ( v25 )
      {
        LastError = GetLastError();
        SysFreeString(v25);
        SetLastError(LastError);
      }
      ppURI[3] = 0;
      v26 = ((__int64 (__fastcall *)(IUri *, IUri **))GetQuery)(v23, ppURI + 3);
      if ( v26 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
          (const char *)(unsigned int)v26,
          v44);
      v27 = ((__int64 (__fastcall *)(IUriBuilder *, __int64))ppIUriBuilder->lpVtbl->RemoveProperties)(
              ppIUriBuilder,
              1024);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
          (const char *)(unsigned int)v27,
          v44);
      v48 = 0;
      lpVtbl = ppIUriBuilder->lpVtbl;
      v48 = 0;
      v29 = ((__int64 (__fastcall *)(IUriBuilder *, _QWORD, _QWORD, __int64 *))lpVtbl->CreateUriSimple)(
              ppIUriBuilder,
              0,
              0,
              &v48);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
          (const char *)(unsigned int)v29,
          v44);
      v30 = v48;
      v31 = *(__int64 (__fastcall **)(__int64, IUri **))(*(_QWORD *)v48 + 56LL);
      v32 = (OLECHAR *)ppURI[2];
      if ( v32 )
      {
        v42 = GetLastError();
        SysFreeString(v32);
        SetLastError(v42);
      }
      ppURI[2] = 0;
      v33 = v31(v30, ppURI + 2);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x38,
          (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
          (const char *)(unsigned int)v33,
          v44);
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    if ( ppIUriBuilder )
      ((void (__fastcall *)(IUriBuilder *))ppIUriBuilder->lpVtbl->Release)(ppIUriBuilder);
  }
  v9 = *ppURI;
  GetAbsoluteUri = (*ppURI)->lpVtbl->GetAbsoluteUri;
  v11 = (OLECHAR *)ppURI[1];
  if ( v11 )
  {
    v43 = GetLastError();
    SysFreeString(v11);
    SetLastError(v43);
  }
  ppURI[1] = 0;
  v12 = ((__int64 (__fastcall *)(IUri *, IUri **))GetAbsoluteUri)(v9, ppURI + 1);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\cachestorage\\requesturl.cxx",
      (const char *)(unsigned int)v12,
      v44);
  v13 = 1;
  if ( ppURI[3] )
    v13 = 2;
  v14 = ppURI[v13];
  v49 = 0;
  v15 = -1;
  do
    ++v15;
  while ( *((_WORD *)&v14->lpVtbl + v15) );
  if ( v15 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v15 > 7 )
  {
    v16 = std::wstring::_Calculate_growth(v15, 7, 0x7FFFFFFFFFFFFFFELL);
    v17 = (void *)std::allocator<unsigned short>::allocate(v21, v16 + 1);
    *(_QWORD *)&v49 = v17;
    v50 = v15;
    v51 = v16;
    memcpy_0(v17, v14, 2 * v15);
    *((_WORD *)v17 + v15) = 0;
  }
  else
  {
    v50 = v15;
    v51 = 7;
    memcpy_0(&v49, v14, 2 * v15);
    *((_WORD *)&v49 + v15) = 0;
    v16 = v51;
    v15 = v50;
    v17 = (void *)v49;
  }
  v18 = &v49;
  if ( v16 > 7 )
    v18 = (__int128 *)v17;
  v19 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 2 * v15; ++i )
    v19 = 0x100000001B3LL * (*((unsigned __int8 *)v18 + i) ^ v19);
  ppURI[6] = (IUri *)(v19 ^ HIDWORD(v19));
  if ( v16 > 7 )
    std::_Deallocate<16>(v17, 2 * v16 + 2);
}

```

## disassembly

```asm
0x180015df0  mov     [rsp-38h+arg_10], rbx
0x180015df5  push    rbp
0x180015df6  push    rsi
0x180015df7  push    rdi
0x180015df8  push    r12
0x180015dfa  push    r13
0x180015dfc  push    r14
0x180015dfe  push    r15
0x180015e00  mov     rbp, rsp
0x180015e03  sub     rsp, 70h
0x180015e07  mov     rax, cs:__security_cookie
0x180015e0e  xor     rax, rsp
0x180015e11  mov     [rbp+var_8], rax
0x180015e15  mov     rbx, rdx
0x180015e18  mov     r14, rcx
0x180015e1b  mov     rcx, [rcx]
0x180015e1e  xor     r13d, r13d
0x180015e21  mov     [r14], r13
0x180015e24  test    rcx, rcx
0x180015e27  jnz     loc_180016239
0x180015e2d  mov     r9, r14; ppURI
0x180015e30  xor     r8d, r8d; dwReserved
0x180015e33  mov     edx, 3002B80h; dwFlags
0x180015e38  mov     rcx, rbx; pwzURI
0x180015e3b  call    cs:__imp_CreateUri
0x180015e41  mov     rcx, [rbp+38h]; this
0x180015e45  test    eax, eax
0x180015e47  js      loc_18001624A
0x180015e4d  mov     dword ptr [rbp+ppIUriBuilder], r13d
0x180015e51  mov     rcx, [r14]
0x180015e54  mov     rax, [rcx]
0x180015e57  lea     rdx, [rbp+ppIUriBuilder]
0x180015e5b  mov     rax, [rax+0C0h]
0x180015e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e67  mov     rcx, [rbp+38h]; this
0x180015e6b  test    eax, eax
0x180015e6d  js      loc_18001625F
0x180015e73  mov     eax, dword ptr [rbp+ppIUriBuilder]
0x180015e76  cmp     eax, 0Bh
0x180015e79  jnz     loc_180016274
0x180015e7f  mov     [rbp+var_38], r13d
0x180015e83  mov     [rbp+var_34], r13d
0x180015e87  mov     rcx, [r14]
0x180015e8a  mov     rax, [rcx]
0x180015e8d  lea     r8, [rbp+var_38]
0x180015e91  mov     edx, 5
0x180015e96  mov     rax, [rax+30h]
0x180015e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e9f  mov     rcx, [rbp+38h]; this
0x180015ea3  test    eax, eax
0x180015ea5  js      loc_180016299
0x180015eab  mov     rcx, [r14]
0x180015eae  mov     rax, [rcx]
0x180015eb1  lea     r8, [rbp+var_34]
0x180015eb5  mov     edx, 0Ah
0x180015eba  mov     rax, [rax+30h]
0x180015ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ec3  mov     rcx, [rbp+38h]; this
0x180015ec7  test    eax, eax
0x180015ec9  js      loc_1800162AE
0x180015ecf  cmp     [rbp+var_38], 0
0x180015ed3  jnz     loc_18001606E
0x180015ed9  cmp     [rbp+var_34], 0
0x180015edd  jnz     loc_18001606E
0x180015ee3  mov     rsi, [r14]
0x180015ee6  mov     rax, [rsi]
0x180015ee9  mov     r12, [rax+38h]
0x180015eed  mov     r15, [r14+8]
0x180015ef1  test    r15, r15
0x180015ef4  jnz     loc_180016392
0x180015efa  mov     [r14+8], r13
0x180015efe  lea     rdx, [r14+8]
0x180015f02  mov     rcx, rsi
0x180015f05  mov     rax, r12
0x180015f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f0d  test    eax, eax
0x180015f0f  js      loc_1800163B0
0x180015f15  mov     eax, 8
0x180015f1a  mov     ecx, 10h
0x180015f1f  cmp     qword ptr [r14+18h], 0
0x180015f24  cmovnz  eax, ecx
0x180015f27  mov     rdi, [rax+r14]
0x180015f2b  xorps   xmm0, xmm0
0x180015f2e  movups  [rbp+var_28], xmm0
0x180015f32  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180015f39  nop     dword ptr [rax+00000000h]
0x180015f40  inc     rbx
0x180015f43  cmp     word ptr [rdi+rbx*2], 0
0x180015f48  jnz     short loc_180015F40
0x180015f4a  mov     r8, 7FFFFFFFFFFFFFFEh
0x180015f54  cmp     rbx, r8
0x180015f57  ja      loc_180016020
0x180015f5d  lea     rsi, [rbx+rbx]
0x180015f61  cmp     rbx, 7
0x180015f65  ja      loc_18001602E
0x180015f6b  mov     [rbp+var_18], rbx
0x180015f6f  mov     [rbp+var_10], 7
0x180015f77  mov     r8, rsi; Size
0x180015f7a  mov     rdx, rdi; Src
0x180015f7d  lea     rcx, [rbp+var_28]; void *
0x180015f81  call    memcpy_0
0x180015f86  mov     word ptr [rbp+rsi+var_28], r13w
0x180015f8c  mov     r15, [rbp+var_10]
0x180015f90  mov     rbx, [rbp+var_18]
0x180015f94  mov     r12, qword ptr [rbp+var_28]
0x180015f98  lea     r8, [rbp+var_28]
0x180015f9c  cmp     r15, 7
0x180015fa0  cmova   r8, r12
0x180015fa4  mov     rdx, 0CBF29CE484222325h
0x180015fae  lea     r9, [rbx+rbx]
0x180015fb2  mov     rax, r13
0x180015fb5  test    r9, r9
0x180015fb8  jz      short loc_180015FE4
0x180015fba  mov     r10, 100000001B3h
0x180015fc4  nop     dword ptr [rax+00h]
0x180015fc8  nop     dword ptr [rax+rax+00000000h]
0x180015fd0  movzx   ecx, byte ptr [r8+rax]
0x180015fd5  xor     rdx, rcx
0x180015fd8  imul    rdx, r10
0x180015fdc  inc     rax
0x180015fdf  cmp     rax, r9
0x180015fe2  jb      short loc_180015FD0
0x180015fe4  mov     rax, rdx
0x180015fe7  shr     rax, 20h
0x180015feb  xor     rax, rdx
0x180015fee  mov     [r14+30h], rax
0x180015ff2  cmp     r15, 7
0x180015ff6  ja      loc_1800163C9
0x180015ffc  mov     rcx, [rbp+var_8]
0x180016000  xor     rcx, rsp; StackCookie
0x180016003  call    __security_check_cookie
0x180016008  mov     rbx, [rsp+70h+arg_10]
0x180016010  add     rsp, 70h
0x180016014  pop     r15
0x180016016  pop     r14
0x180016018  pop     r13
0x18001601a  pop     r12
0x18001601c  pop     rdi
0x18001601d  pop     rsi
0x18001601e  pop     rbp
0x18001601f  retn
0x180016020  lea     rcx, aStringTooLong; "string too long"
0x180016027  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001602e  mov     edx, 7
0x180016033  mov     rcx, rbx
0x180016036  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18001603b  mov     r15, rax
0x18001603e  lea     rdx, [rax+1]
0x180016042  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180016047  mov     r12, rax
0x18001604a  mov     qword ptr [rbp+var_28], rax
0x18001604e  mov     [rbp+var_18], rbx
0x180016052  mov     [rbp+var_10], r15
0x180016056  mov     r8, rsi; Size
0x180016059  mov     rdx, rdi; Src
0x18001605c  mov     rcx, rax; void *
0x18001605f  call    memcpy_0
0x180016064  mov     [r12+rsi], r13w
0x180016069  jmp     loc_180015F98
0x18001606e  mov     [rbp+ppIUriBuilder], r13
0x180016072  lea     r9, [rbp+ppIUriBuilder]; ppIUriBuilder
0x180016076  xor     r8d, r8d; dwReserved
0x180016079  xor     edx, edx; dwFlags
0x18001607b  mov     rcx, [r14]; pIUri
0x18001607e  call    cs:__imp_CreateIUriBuilder
0x180016084  mov     rcx, [rbp+38h]; this
0x180016088  test    eax, eax
0x18001608a  js      loc_1800162C3
0x180016090  cmp     [rbp+var_38], 0
0x180016094  jnz     loc_180016196
0x18001609a  cmp     [rbp+var_34], 0
0x18001609e  jz      loc_18001617B
0x1800160a4  mov     rsi, [r14]
0x1800160a7  mov     rax, [rsi]
0x1800160aa  mov     r12, [rax+88h]
0x1800160b1  mov     r15, [r14+18h]
0x1800160b5  test    r15, r15
0x1800160b8  jnz     loc_180016302
0x1800160be  mov     [r14+18h], r13
0x1800160c2  lea     rdx, [r14+18h]
0x1800160c6  mov     rcx, rsi
0x1800160c9  mov     rax, r12
0x1800160cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160d1  mov     rcx, [rbp+38h]; this
0x1800160d5  test    eax, eax
0x1800160d7  js      loc_180016320
0x1800160dd  mov     rcx, [rbp+ppIUriBuilder]
0x1800160e1  mov     rax, [rcx]
0x1800160e4  mov     edx, 400h
0x1800160e9  mov     rax, [rax+0C0h]
0x1800160f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160f5  mov     rcx, [rbp+38h]; this
0x1800160f9  test    eax, eax
0x1800160fb  js      loc_180016335
0x180016101  mov     [rbp+var_30], r13
0x180016105  mov     rcx, [rbp+ppIUriBuilder]
0x180016109  mov     rax, [rcx]
0x18001610c  mov     [rbp+var_30], r13
0x180016110  lea     r9, [rbp+var_30]
0x180016114  xor     r8d, r8d
0x180016117  xor     edx, edx
0x180016119  mov     rax, [rax+18h]
0x18001611d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016122  mov     rcx, [rbp+38h]; this
0x180016126  test    eax, eax
0x180016128  js      loc_18001634A
0x18001612e  mov     rsi, [rbp+var_30]
0x180016132  mov     rax, [rsi]
0x180016135  mov     r12, [rax+38h]
0x180016139  mov     r15, [r14+10h]
0x18001613d  test    r15, r15
0x180016140  jnz     loc_18001635F
0x180016146  mov     [r14+10h], r13
0x18001614a  lea     rdx, [r14+10h]
0x18001614e  mov     rcx, rsi
0x180016151  mov     rax, r12
0x180016154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016159  mov     rcx, [rbp+38h]; this
0x18001615d  test    eax, eax
0x18001615f  js      loc_18001637D
0x180016165  mov     rcx, [rbp+var_30]
0x180016169  test    rcx, rcx
0x18001616c  jz      short loc_18001617B
0x18001616e  mov     rax, [rcx]
0x180016171  mov     rax, [rax+10h]
0x180016175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001617a  nop
0x18001617b  mov     rcx, [rbp+ppIUriBuilder]
0x18001617f  test    rcx, rcx
0x180016182  jz      short loc_180016191
0x180016184  mov     rax, [rcx]
0x180016187  mov     rax, [rax+10h]
0x18001618b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016190  nop
0x180016191  jmp     loc_180015EE3
0x180016196  mov     rsi, [r14]
0x180016199  mov     rax, [rsi]
0x18001619c  mov     rdi, [rax+60h]
0x1800161a0  xor     edx, edx
0x1800161a2  lea     rcx, [r14+20h]
0x1800161a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800161ab  lea     rdx, [r14+20h]
0x1800161af  mov     rcx, rsi
0x1800161b2  mov     rax, rdi
0x1800161b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161ba  mov     rcx, [rbp+38h]; this
0x1800161be  test    eax, eax
0x1800161c0  js      loc_1800162D8
0x1800161c6  mov     rcx, [rbp+ppIUriBuilder]
0x1800161ca  mov     rax, [rcx]
0x1800161cd  mov     edx, 20h ; ' '
0x1800161d2  mov     rax, [rax+0C0h]
0x1800161d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161de  mov     rcx, [rbp+38h]; this
0x1800161e2  test    eax, eax
0x1800161e4  js      loc_1800162ED
0x1800161ea  mov     rcx, r14
0x1800161ed  call    ?reset@?$com_ptr_t@UIUri@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUri,wil::err_exception_policy>::reset(void)
0x1800161f2  mov     rdi, [rbp+ppIUriBuilder]
0x1800161f6  mov     rax, [rdi]
0x1800161f9  mov     rbx, [rax+18h]
0x1800161fd  mov     rcx, r14
0x180016200  call    ?reset@?$com_ptr_t@UIUri@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUri,wil::err_exception_policy>::reset(void)
0x180016205  mov     r9, r14
0x180016208  xor     r8d, r8d
0x18001620b  xor     edx, edx
0x18001620d  mov     rcx, rdi
0x180016210  mov     rax, rbx
0x180016213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016218  mov     rcx, [rbp+38h]; this
0x18001621c  test    eax, eax
0x18001621e  jns     loc_18001609A
0x180016224  mov     r9d, eax; char *
0x180016227  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\webplatstorageser"...
0x18001622e  mov     edx, 2Eh ; '.'; void *
0x180016233  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016239  mov     rax, [rcx]
0x18001623c  mov     rax, [rax+10h]
0x180016240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016245  jmp     loc_180015E2D
0x18001624a  mov     r9d, eax; char *
0x18001624d  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\webplatstorageser"...
0x180016254  mov     edx, 1Ah; void *
0x180016259  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001625f  mov     r9d, eax; char *
0x180016262  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\webplatstorageser"...
0x180016269  mov     edx, 75h ; 'u'; void *
0x18001626e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016274  cmp     eax, 2
0x180016277  jz      loc_180015E7F
0x18001627d  mov     rcx, [rbp+38h]; this
0x180016281  mov     r9d, 8070F005h; char *
0x180016287  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\webplatstorageser"...
0x18001628e  mov     edx, 78h ; 'x'; void *
0x180016293  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180016299  mov     r9d, eax; char *
0x18001629c  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\webplatstorageser"...
0x1800162a3  mov     edx, 1Fh; void *
0x1800162a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800162ae  mov     r9d, eax; char *
  ... truncated ...
```
