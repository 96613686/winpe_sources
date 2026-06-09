# BlbCreateNonWriterXML(ushort * *)

- ea: `0x14011ff3c`
- end: `0x140120438`
- name: `?BlbCreateNonWriterXML@@YAJPEAPEAG@Z`
- size: `1276`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14003b140`
- `0x140078f88`
- `0x140079b08`

## callees

- `0x140006a64`
- `0x140006ca8`
- `0x140007ad3`
- `0x14000bfd8`
- `0x14000c248`
- `0x14001358c`
- `0x140051e98`
- `0x14007007c`
- `0x1400889f0`
- `0x14008f020`
- `0x1400f7290`
- `0x14011ff3c`

## import_xrefs

- `msvcrt!free` at `0x140120278`
- `msvcrt!free` at `0x1401203ab`
- `msvcrt!free` at `0x140120278`
- `msvcrt!free` at `0x1401203ab`
- `ole32!CoTaskMemAlloc` at `0x14012006d`
- `ole32!CoTaskMemAlloc` at `0x14012012e`
- `ole32!CoTaskMemAlloc` at `0x140120158`
- `ole32!CoTaskMemAlloc` at `0x14012006d`
- `ole32!CoTaskMemAlloc` at `0x14012012e`
- `ole32!CoTaskMemAlloc` at `0x140120158`
- `ole32!CoTaskMemFree` at `0x140120000`
- `ole32!CoTaskMemFree` at `0x14012021e`
- `ole32!CoTaskMemFree` at `0x140120251`
- `ole32!CoTaskMemFree` at `0x140120335`
- `ole32!CoTaskMemFree` at `0x140120343`
- `ole32!CoTaskMemFree` at `0x140120351`
- `ole32!CoTaskMemFree` at `0x140120382`
- `ole32!CoTaskMemFree` at `0x1401203e8`
- `ole32!CoTaskMemFree` at `0x140120000`
- `ole32!CoTaskMemFree` at `0x14012021e`
- `ole32!CoTaskMemFree` at `0x140120251`
- `ole32!CoTaskMemFree` at `0x140120335`
- `ole32!CoTaskMemFree` at `0x140120343`
- `ole32!CoTaskMemFree` at `0x140120351`
- `ole32!CoTaskMemFree` at `0x140120382`
- `ole32!CoTaskMemFree` at `0x1401203e8`
- `OLEAUT32!__imp_SysFreeString` at `0x14012040a`
- `OLEAUT32!__imp_SysFreeString` at `0x14012040a`
- `OLEAUT32!__imp_SysStringLen` at `0x14011ffe0`
- `OLEAUT32!__imp_SysStringLen` at `0x140120031`
- `OLEAUT32!__imp_SysStringLen` at `0x140120102`
- `OLEAUT32!__imp_SysStringLen` at `0x140120113`
- `OLEAUT32!__imp_SysStringLen` at `0x14011ffe0`
- `OLEAUT32!__imp_SysStringLen` at `0x140120031`
- `OLEAUT32!__imp_SysStringLen` at `0x140120102`
- `OLEAUT32!__imp_SysStringLen` at `0x140120113`

## string_xrefs

- `0x1401200af`: `<IncludeFile FilePath="%ws" FileSpec="%ws" IsRecursive="%ws" />`
- `0x1401200a8`: `<ExcludeFile FilePath="%ws" FileSpec="%ws" IsRecursive="%ws" />`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BlbCreateNonWriterXML(unsigned __int16 **a1)
{
  unsigned __int16 *v2; // r14
  unsigned __int16 *v3; // r15
  OLECHAR *v4; // rbx
  __int64 v5; // rax
  struct _BLB_NONWRITER_COMPONENT near **v6; // rsi
  unsigned int v7; // r12d
  int v8; // edi
  UINT v9; // edx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  const unsigned __int16 *v13; // rax
  const unsigned __int16 *v14; // r8
  __int64 v15; // rdi
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // r13
  unsigned __int16 *v18; // rax
  unsigned int v19; // r12d
  unsigned __int64 v20; // rsi
  unsigned __int16 **v21; // rax
  unsigned int i; // edi
  LPVOID *v23; // rax
  unsigned int j; // ebx
  const unsigned __int16 **v25; // rax
  unsigned __int16 *v26; // r12
  unsigned int k; // r14d
  LPVOID *v28; // rax
  unsigned int m; // esi
  LPVOID *v30; // rax
  void *Block; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int64 v33; // [rsp+40h] [rbp-59h]
  __int64 v34; // [rsp+48h] [rbp-51h]
  int v35; // [rsp+50h] [rbp-49h]
  unsigned __int16 *v36; // [rsp+58h] [rbp-41h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int16 *v38; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int16 *v39; // [rsp+70h] [rbp-29h] BYREF
  void *v40; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v41; // [rsp+80h] [rbp-19h]
  __int64 v42; // [rsp+88h] [rbp-11h]
  int v43; // [rsp+90h] [rbp-9h]
  size_t Size; // [rsp+98h] [rbp-1h]
  unsigned __int64 v45; // [rsp+A0h] [rbp+7h]
  char v47; // [rsp+108h] [rbp+6Fh]
  UINT v48; // [rsp+108h] [rbp+6Fh]
  unsigned int v49; // [rsp+110h] [rbp+77h]
  unsigned __int64 v50; // [rsp+110h] [rbp+77h]
  int v51; // [rsp+118h] [rbp+7Fh]

  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  Block = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v2 = 0;
  v38 = 0;
  v3 = 0;
  v36 = 0;
  v4 = 0;
  bstrString = 0;
  if ( !a1 )
    BlbAssert("base\\stor\\blb\\wsbutil\\wsbsystemstateutils.cpp", 0x52u, "pwszOutputString");
  *a1 = 0;
  v5 = 0;
  v51 = 0;
  do
  {
    v49 = 0;
    v6 = &g_NonWriterComponentList + 98 * v5;
    v7 = 0;
    while ( SysStringLen((BSTR)v6[3 * v7 + 2]) )
    {
      v47 = (char)v6[3 * v7 + 4];
      if ( v3 )
      {
        CoTaskMemFree(v3);
        v36 = 0;
      }
      v8 = BlbutilExpandEnvironmentStrings((LPCWSTR)v6[3 * v7 + 2], &v36);
      if ( v8 < 0 )
      {
        v3 = v36;
        goto LABEL_40;
      }
      v9 = SysStringLen((BSTR)v6[3 * v7 + 3]);
      v3 = v36;
      v10 = -1;
      do
        ++v10;
      while ( v36[v10] );
      v49 += v9 + 5 - (v47 != 0) + v10 + 63;
      v45 = v49;
      Size = 2LL * v49;
      v11 = (unsigned __int16 *)CoTaskMemAlloc(Size);
      v12 = v11;
      v39 = v11;
      if ( !v11 )
        goto LABEL_39;
      memset_0(v11, 0, Size);
      v13 = L"true";
      if ( !v47 )
        v13 = L"false";
      v14 = L"<IncludeFile FilePath=\"%ws\" FileSpec=\"%ws\" IsRecursive=\"%ws\" />";
      if ( !*((_BYTE *)v6 + 8) )
        v14 = L"<ExcludeFile FilePath=\"%ws\" FileSpec=\"%ws\" IsRecursive=\"%ws\" />";
      v8 = StringCchPrintfW(v12, v45, v14, v3, v6[3 * v7 + 3], v13);
      if ( v8 < 0 )
        goto LABEL_40;
      ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(
        &Block,
        &v39);
      if ( ++v7 >= 0x20 )
        break;
    }
    v48 = SysStringLen((BSTR)*v6) + 5;
    v15 = SysStringLen((BSTR)*v6) + 6;
    v50 = v49 + (_DWORD)v15 + v48;
    v16 = (unsigned __int16 *)CoTaskMemAlloc(2 * v50);
    v17 = v16;
    v39 = v16;
    if ( !v16 || (memset_0(v16, 0, 2 * v50), v18 = (unsigned __int16 *)CoTaskMemAlloc(2 * v15), (v2 = v18) == 0) )
    {
LABEL_39:
      v8 = -2147024882;
LABEL_40:
      v20 = v33;
LABEL_41:
      v26 = 0;
      goto LABEL_42;
    }
    memset_0(v18, 0, 2 * v15);
    v8 = StringCchPrintfW(v2, (unsigned int)v15, L"</%ws>", *v6);
    if ( v8 < 0 )
      goto LABEL_40;
    v8 = StringCchPrintfW(v17, v48, L"<%ws>", *v6);
    if ( v8 < 0 )
      goto LABEL_40;
    v19 = 0;
    v20 = v33;
    if ( v33 )
    {
      do
      {
        v21 = (unsigned __int16 **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                     &Block,
                                     v19);
        v8 = StringCchCatW(v17, v50, *v21);
        if ( v8 < 0 )
          goto LABEL_41;
      }
      while ( ++v19 < v20 );
    }
    v8 = StringCchCatW(v17, v50, v2);
    if ( v8 < 0 )
      goto LABEL_41;
    ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(
      &v40,
      &v39);
    CoTaskMemFree(v2);
    v2 = 0;
    for ( i = 0; i < v20; ++i )
    {
      if ( *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                        &Block,
                        i) )
      {
        v23 = (LPVOID *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                          &Block,
                          i);
        CoTaskMemFree(*v23);
        *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                     &Block,
                     i) = 0;
      }
    }
    if ( Block )
    {
      free(Block);
      Block = 0;
    }
    v20 = 0;
    v33 = 0;
    v34 = 0;
    v5 = (unsigned int)(v51 + 1);
    v51 = v5;
  }
  while ( (unsigned int)v5 < 2 );
  ATL::CComBSTR::operator=(&bstrString, L"<AdditionalFiles>");
  for ( j = 0; j < v41; ++j )
  {
    v25 = (const unsigned __int16 **)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                                       &v40,
                                       j);
    ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, *v25);
  }
  ATL::CComBSTR::operator+=((ATL::CComBSTR *)&bstrString, L"</AdditionalFiles>");
  v4 = bstrString;
  v8 = BlbutilDuplicateString(bstrString, &v38, 0);
  if ( v8 < 0 )
  {
    v26 = v38;
  }
  else
  {
    *a1 = v38;
    v26 = 0;
  }
LABEL_42:
  if ( v3 )
    CoTaskMemFree(v3);
  if ( v26 )
    CoTaskMemFree(v26);
  if ( v2 )
    CoTaskMemFree(v2);
  for ( k = 0; k < v20; ++k )
  {
    if ( *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                      &Block,
                      k) )
    {
      v28 = (LPVOID *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                        &Block,
                        k);
      CoTaskMemFree(*v28);
      *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                   &Block,
                   k) = 0;
    }
  }
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  v33 = 0;
  v34 = 0;
  for ( m = 0; m < v41; ++m )
  {
    if ( *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                      &v40,
                      m) )
    {
      v30 = (LPVOID *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                        &v40,
                        m);
      CoTaskMemFree(*v30);
      *(_QWORD *)ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](
                   &v40,
                   m) = 0;
    }
  }
  SysFreeString(v4);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(&Block);
  ATL::CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>::~CAtlArray<_BLB_COMPONENT,ATL::CElementTraits<_BLB_COMPONENT>>(&v40);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14011ff3c  mov     [rsp-8+arg_0], rcx
0x14011ff41  push    rbp
0x14011ff42  push    rbx
0x14011ff43  push    rsi
0x14011ff44  push    rdi
0x14011ff45  push    r12
0x14011ff47  push    r13
0x14011ff49  push    r14
0x14011ff4b  push    r15
0x14011ff4d  lea     rbp, [rsp-1Fh]
0x14011ff52  sub     rsp, 0B8h
0x14011ff59  mov     rdi, rcx
0x14011ff5c  xor     r13d, r13d
0x14011ff5f  mov     [rbp+57h+var_78], r13
0x14011ff63  mov     [rbp+57h+var_70], r13
0x14011ff67  mov     [rbp+57h+var_68], r13
0x14011ff6b  mov     [rbp+57h+var_60], r13d
0x14011ff6f  mov     [rbp+57h+Block], r13
0x14011ff73  mov     [rbp+57h+var_B0], r13
0x14011ff77  mov     [rbp+57h+var_A8], r13
0x14011ff7b  mov     [rbp+57h+var_A0], r13d
0x14011ff7f  mov     r14d, r13d
0x14011ff82  mov     [rbp+57h+var_C0], r13
0x14011ff86  mov     [rbp+57h+var_88], r13
0x14011ff8a  mov     r15d, r13d
0x14011ff8d  mov     [rbp+57h+var_98], r13
0x14011ff91  mov     ebx, r13d
0x14011ff94  mov     [rbp+57h+bstrString], rbx
0x14011ff98  test    rcx, rcx
0x14011ff9b  jnz     short loc_14011FFB3
0x14011ff9d  lea     r8, aPwszoutputstri; "pwszOutputString"
0x14011ffa4  lea     edx, [rcx+52h]; unsigned int
0x14011ffa7  lea     rcx, aBaseStorBlbWsb_1; "base\\stor\\blb\\wsbutil\\wsbsystemstat"...
0x14011ffae  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14011ffb3  mov     [rdi], r13
0x14011ffb6  mov     eax, r13d
0x14011ffb9  mov     [rbp+57h+arg_18], eax
0x14011ffbc  mov     dword ptr [rbp+57h+arg_10], r13d
0x14011ffc0  imul    rsi, rax, 310h
0x14011ffc7  lea     rax, ?g_NonWriterComponentList@@3PAU_BLB_NONWRITER_COMPONENT@@A; _BLB_NONWRITER_COMPONENT near * g_NonWriterComponentList
0x14011ffce  add     rsi, rax
0x14011ffd1  mov     r12d, r13d
0x14011ffd4  mov     eax, r12d
0x14011ffd7  lea     r13, [rax+rax*2]
0x14011ffdb  mov     rcx, [rsi+r13*8+10h]; pbstr
0x14011ffe0  call    cs:__imp_SysStringLen
0x14011ffe6  xor     edi, edi
0x14011ffe8  test    eax, eax
0x14011ffea  jz      loc_1401200FF
0x14011fff0  mov     al, [rsi+r13*8+20h]
0x14011fff5  mov     byte ptr [rbp+57h+arg_8], al
0x14011fff8  test    r15, r15
0x14011fffb  jz      short loc_14012000A
0x14011fffd  mov     rcx, r15; pv
0x140120000  call    cs:__imp_CoTaskMemFree
0x140120006  mov     [rbp+57h+var_98], rdi
0x14012000a  lea     rdx, [rbp+57h+var_98]; unsigned __int16 **
0x14012000e  mov     rcx, [rsi+r13*8+10h]; lpSrc
0x140120013  call    ?BlbutilExpandEnvironmentStrings@@YAJPEBGPEAPEAG@Z; BlbutilExpandEnvironmentStrings(ushort const *,ushort * *)
0x140120018  mov     edi, eax
0x14012001a  test    eax, eax
0x14012001c  js      loc_140120311
0x140120022  mov     al, byte ptr [rbp+57h+arg_8]
0x140120025  neg     al
0x140120027  sbb     edi, edi
0x140120029  add     edi, 5
0x14012002c  mov     rcx, [rsi+r13*8+18h]; pbstr
0x140120031  call    cs:__imp_SysStringLen
0x140120037  mov     edx, eax
0x140120039  mov     r15, [rbp+57h+var_98]
0x14012003d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140120041  xor     eax, eax
0x140120043  inc     rcx
0x140120046  cmp     [r15+rcx*2], ax
0x14012004b  jnz     short loc_140120043
0x14012004d  lea     eax, [rdi+rcx]
0x140120050  add     eax, edx
0x140120052  mov     ecx, dword ptr [rbp+57h+arg_10]
0x140120055  add     ecx, 3Fh ; '?'
0x140120058  add     ecx, eax
0x14012005a  mov     dword ptr [rbp+57h+arg_10], ecx
0x14012005d  mov     eax, ecx
0x14012005f  mov     [rbp+57h+var_50], rax
0x140120063  add     rax, rax
0x140120066  mov     [rbp+57h+Size], rax
0x14012006a  mov     rcx, rax; cb
0x14012006d  call    cs:__imp_CoTaskMemAlloc
0x140120073  mov     rdi, rax
0x140120076  mov     [rbp+57h+var_80], rax
0x14012007a  test    rax, rax
0x14012007d  jz      loc_14012031D
0x140120083  mov     r8, [rbp+57h+Size]; Size
0x140120087  xor     edx, edx; Val
0x140120089  mov     rcx, rax; void *
0x14012008c  call    memset_0
0x140120091  lea     rcx, aFalse_0; "false"
0x140120098  lea     rax, aTrue; "true"
0x14012009f  xor     edx, edx
0x1401200a1  cmp     byte ptr [rbp+57h+arg_8], dl
0x1401200a4  cmovz   rax, rcx
0x1401200a8  lea     rcx, aExcludefileFil; "<ExcludeFile FilePath=\"%ws\" FileSpec="...
0x1401200af  lea     r8, aIncludefileFil; "<IncludeFile FilePath=\"%ws\" FileSpec="...
0x1401200b6  cmp     [rsi+8], dl
0x1401200b9  cmovz   r8, rcx; unsigned __int16 *
0x1401200bd  mov     [rsp+0F0h+var_C8], rax
0x1401200c2  mov     rax, [rsi+r13*8+18h]
0x1401200c7  mov     [rsp+0F0h+var_D0], rax
0x1401200cc  mov     r9, r15
0x1401200cf  mov     rdx, [rbp+57h+var_50]; unsigned __int64
0x1401200d3  mov     rcx, rdi; unsigned __int16 *
0x1401200d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401200db  mov     edi, eax
0x1401200dd  test    eax, eax
0x1401200df  js      loc_140120322
0x1401200e5  lea     rdx, [rbp+57h+var_80]
0x1401200e9  lea     rcx, [rbp+57h+Block]
0x1401200ed  call    ?Add@?$CAtlArray@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@@2@@ATL@@QEAA_KAEBQEAV?$CComObject@VCBlbComponentRestoreContext@@@2@@Z; ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(ATL::CComObject<CBlbComponentRestoreContext> * const &)
0x1401200f2  inc     r12d
0x1401200f5  cmp     r12d, 20h ; ' '
0x1401200f9  jb      loc_14011FFD4
0x1401200ff  mov     rcx, [rsi]; pbstr
0x140120102  call    cs:__imp_SysStringLen
0x140120108  lea     r12d, [rax+5]
0x14012010c  mov     dword ptr [rbp+57h+arg_8], r12d
0x140120110  mov     rcx, [rsi]; pbstr
0x140120113  call    cs:__imp_SysStringLen
0x140120119  lea     edi, [rax+6]
0x14012011c  lea     eax, [rdi+r12]
0x140120120  add     eax, dword ptr [rbp+57h+arg_10]
0x140120123  mov     [rbp+57h+arg_10], rax
0x140120127  lea     r12, [rax+rax]
0x14012012b  mov     rcx, r12; cb
0x14012012e  call    cs:__imp_CoTaskMemAlloc
0x140120134  mov     r13, rax
0x140120137  mov     [rbp+57h+var_80], rax
0x14012013b  test    rax, rax
0x14012013e  jz      loc_14012031D
0x140120144  mov     r8, r12; Size
0x140120147  xor     edx, edx; Val
0x140120149  mov     rcx, rax; void *
0x14012014c  call    memset_0
0x140120151  lea     r12, [rdi+rdi]
0x140120155  mov     rcx, r12; cb
0x140120158  call    cs:__imp_CoTaskMemAlloc
0x14012015e  mov     r14, rax
0x140120161  test    rax, rax
0x140120164  jz      loc_14012031D
0x14012016a  mov     r8, r12; Size
0x14012016d  xor     edx, edx; Val
0x14012016f  mov     rcx, rax; void *
0x140120172  call    memset_0
0x140120177  mov     r9, [rsi]
0x14012017a  lea     r8, aWs; "</%ws>"
0x140120181  mov     edx, edi; unsigned __int64
0x140120183  mov     rcx, r14; unsigned __int16 *
0x140120186  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14012018b  mov     edi, eax
0x14012018d  test    eax, eax
0x14012018f  js      loc_140120322
0x140120195  mov     edx, dword ptr [rbp+57h+arg_8]; unsigned __int64
0x140120198  mov     r9, [rsi]
0x14012019b  lea     r8, aWs_0; "<%ws>"
0x1401201a2  mov     rcx, r13; unsigned __int16 *
0x1401201a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401201aa  mov     edi, eax
0x1401201ac  xor     eax, eax
0x1401201ae  test    edi, edi
0x1401201b0  js      loc_140120322
0x1401201b6  mov     r12d, eax
0x1401201b9  mov     rsi, [rbp+57h+var_B0]
0x1401201bd  test    rsi, rsi
0x1401201c0  jz      short loc_1401201F2
0x1401201c2  mov     edx, r12d
0x1401201c5  lea     rcx, [rbp+57h+Block]
0x1401201c9  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1401201ce  mov     r8, [rax]; unsigned __int16 *
0x1401201d1  mov     rdx, [rbp+57h+arg_10]; unsigned __int64
0x1401201d5  mov     rcx, r13; unsigned __int16 *
0x1401201d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1401201dd  mov     edi, eax
0x1401201df  test    eax, eax
0x1401201e1  js      loc_140120326
0x1401201e7  inc     r12d
0x1401201ea  mov     eax, r12d
0x1401201ed  cmp     rax, rsi
0x1401201f0  jb      short loc_1401201C2
0x1401201f2  mov     r8, r14; unsigned __int16 *
0x1401201f5  mov     rdx, [rbp+57h+arg_10]; unsigned __int64
0x1401201f9  mov     rcx, r13; unsigned __int16 *
0x1401201fc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140120201  mov     edi, eax
0x140120203  xor     r13d, r13d
0x140120206  test    eax, eax
0x140120208  js      loc_140120326
0x14012020e  lea     rdx, [rbp+57h+var_80]
0x140120212  lea     rcx, [rbp+57h+var_78]
0x140120216  call    ?Add@?$CAtlArray@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCBlbComponentRestoreContext@@@ATL@@@2@@ATL@@QEAA_KAEBQEAV?$CComObject@VCBlbComponentRestoreContext@@@2@@Z; ATL::CAtlArray<ATL::CComObject<CBlbComponentRestoreContext> *,ATL::CElementTraits<ATL::CComObject<CBlbComponentRestoreContext> *>>::Add(ATL::CComObject<CBlbComponentRestoreContext> * const &)
0x14012021b  mov     rcx, r14; pv
0x14012021e  call    cs:__imp_CoTaskMemFree
0x140120224  mov     r14d, r13d
0x140120227  mov     edi, r13d
0x14012022a  test    rsi, rsi
0x14012022d  jz      short loc_14012026F
0x14012022f  mov     r12d, edi
0x140120232  mov     edx, edi
0x140120234  lea     rcx, [rbp+57h+Block]
0x140120238  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x14012023d  cmp     [rax], r13
0x140120240  jz      short loc_140120266
0x140120242  mov     edx, r12d
0x140120245  lea     rcx, [rbp+57h+Block]
0x140120249  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x14012024e  mov     rcx, [rax]; pv
0x140120251  call    cs:__imp_CoTaskMemFree
0x140120257  mov     edx, r12d
0x14012025a  lea     rcx, [rbp+57h+Block]
0x14012025e  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x140120263  mov     [rax], r13
0x140120266  inc     edi
0x140120268  mov     eax, edi
0x14012026a  cmp     rax, rsi
0x14012026d  jb      short loc_14012022F
0x14012026f  mov     rcx, [rbp+57h+Block]; Block
0x140120273  test    rcx, rcx
0x140120276  jz      short loc_140120282
0x140120278  call    cs:__imp_free
0x14012027e  mov     [rbp+57h+Block], r13
0x140120282  mov     rsi, r13
0x140120285  mov     [rbp+57h+var_B0], r13
0x140120289  mov     [rbp+57h+var_A8], r13
0x14012028d  mov     eax, [rbp+57h+arg_18]
0x140120290  inc     eax
0x140120292  mov     [rbp+57h+arg_18], eax
0x140120295  cmp     eax, 2
0x140120298  jb      loc_14011FFBC
0x14012029e  lea     rdx, aAdditionalfile; "<AdditionalFiles>"
0x1401202a5  lea     rcx, [rbp+57h+bstrString]
0x1401202a9  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x1401202ae  mov     ebx, r13d
0x1401202b1  cmp     [rbp+57h+var_70], r13
0x1401202b5  jbe     short loc_1401202D8
0x1401202b7  mov     edx, ebx
0x1401202b9  lea     rcx, [rbp+57h+var_78]
0x1401202bd  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x1401202c2  mov     rdx, [rax]
0x1401202c5  lea     rcx, [rbp+57h+bstrString]
0x1401202c9  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1401202ce  inc     ebx
0x1401202d0  mov     eax, ebx
0x1401202d2  cmp     rax, [rbp+57h+var_70]
0x1401202d6  jb      short loc_1401202B7
0x1401202d8  lea     rdx, aAdditionalfile_1; "</AdditionalFiles>"
0x1401202df  lea     rcx, [rbp+57h+bstrString]
0x1401202e3  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1401202e8  xor     r8d, r8d; unsigned __int64
0x1401202eb  lea     rdx, [rbp+57h+var_88]; unsigned __int16 **
0x1401202ef  mov     rbx, [rbp+57h+bstrString]
0x1401202f3  mov     rcx, rbx; unsigned __int16 *
0x1401202f6  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1401202fb  mov     edi, eax
0x1401202fd  test    eax, eax
0x1401202ff  js      short loc_140120317
0x140120301  mov     rax, [rbp+57h+var_88]
0x140120305  mov     rcx, [rbp+57h+arg_0]
0x140120309  mov     [rcx], rax
0x14012030c  mov     r12, r13
0x14012030f  jmp     short loc_14012032A
0x140120311  mov     r15, [rbp+57h+var_98]
0x140120315  jmp     short loc_140120322
0x140120317  mov     r12, [rbp+57h+var_88]
0x14012031b  jmp     short loc_14012032A
0x14012031d  mov     edi, 8007000Eh
0x140120322  mov     rsi, [rbp+57h+var_B0]
0x140120326  mov     r12, [rbp+57h+var_C0]
0x14012032a  xor     r13d, r13d
0x14012032d  test    r15, r15
0x140120330  jz      short loc_14012033B
0x140120332  mov     rcx, r15; pv
0x140120335  call    cs:__imp_CoTaskMemFree
0x14012033b  test    r12, r12
0x14012033e  jz      short loc_140120349
0x140120340  mov     rcx, r12; pv
0x140120343  call    cs:__imp_CoTaskMemFree
0x140120349  test    r14, r14
0x14012034c  jz      short loc_140120357
0x14012034e  mov     rcx, r14; pv
0x140120351  call    cs:__imp_CoTaskMemFree
0x140120357  mov     r14d, r13d
0x14012035a  test    rsi, rsi
0x14012035d  jz      short loc_1401203A2
0x14012035f  mov     r15d, r14d
0x140120362  mov     edx, r14d
0x140120365  lea     rcx, [rbp+57h+Block]
0x140120369  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x14012036e  cmp     [rax], r13
0x140120371  jz      short loc_140120397
0x140120373  mov     edx, r15d
0x140120376  lea     rcx, [rbp+57h+Block]
0x14012037a  call    ??A?$CAtlArray@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@V?$CElementTraits@PEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@@ATL@@@ATL@@QEAAAEAPEAU_BLB_VHD_CONTEXT@CBlbVhdHelper@@_K@Z; ATL::CAtlArray<CBlbVhdHelper::_BLB_VHD_CONTEXT *,ATL::CElementTraits<CBlbVhdHelper::_BLB_VHD_CONTEXT *>>::operator[](unsigned __int64)
0x14012037f  mov     rcx, [rax]; pv
  ... truncated ...
```
