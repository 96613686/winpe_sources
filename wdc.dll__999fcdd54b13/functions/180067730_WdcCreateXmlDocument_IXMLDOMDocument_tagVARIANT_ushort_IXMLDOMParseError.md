# WdcCreateXmlDocument(IXMLDOMDocument * *,tagVARIANT *,ushort *,IXMLDOMParseError * *)

- ea: `0x180067730`
- end: `0x180067964`
- name: `?WdcCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@PEAUtagVARIANT@@PEAGPEAPEAUIXMLDOMParseError@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument **, struct tagVARIANT *, unsigned __int16 *, struct IXMLDOMParseError **)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002529c`
- `0x180026b48`
- `0x18002a7dc`
- `0x18002cd58`
- `0x18002e740`
- `0x1800376ac`
- `0x18006796c`

## callees

- `0x18000b854`
- `0x180067730`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800677f2`
- `OLEAUT32!__imp_VariantClear` at `0x180067843`
- `OLEAUT32!__imp_VariantClear` at `0x1800677f2`
- `OLEAUT32!__imp_VariantClear` at `0x180067843`
- `ole32!CoCreateInstance` at `0x180067778`
- `ole32!CoCreateInstance` at `0x180067778`

## string_xrefs

- `0x180067792`: `WdcCreateXmlDocument`

## pseudocode

```c
__int64 __fastcall WdcCreateXmlDocument(
        struct IXMLDOMDocument **a1,
        struct tagVARIANT *a2,
        unsigned __int16 *a3,
        struct IXMLDOMParseError **a4)
{
  HRESULT v8; // eax
  int v9; // ebx
  __int64 v10; // rax
  __int64 (__fastcall *v11)(LPVOID, const wchar_t *, __int128 *); // rax
  __int64 v12; // rax
  __int64 (__fastcall *v13)(LPVOID, const wchar_t *, __int128 *); // rax
  IRecordInfo *v14; // xmm1_8
  __int64 v15; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-60h]
  __int16 v18; // [rsp+30h] [rbp-50h] BYREF
  LPVOID v19; // [rsp+38h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-40h] BYREF
  __int128 v21; // [rsp+60h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+70h] [rbp-10h]

  v18 = 0;
  v19 = 0;
  v8 = CoCreateInstance(&CLSID_FreeThreadedDOMDocument, 0, 0x15u, &IID_IXMLDOMDocument, &v19);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_2;
  pRecInfo = pvarg.pRecInfo;
  v10 = *(_QWORD *)v19;
  pvarg.iVal = -1;
  pvarg.vt = 11;
  v11 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int128 *))(v10 + 640);
  v21 = *(_OWORD *)&pvarg.vt;
  v9 = v11(v19, L"ProhibitDTD", &v21);
  VariantClear(&pvarg);
  if ( v9 < 0 )
    goto LABEL_5;
  pRecInfo = pvarg.pRecInfo;
  v12 = *(_QWORD *)v19;
  pvarg.iVal = 0;
  pvarg.vt = 11;
  v13 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int128 *))(v12 + 640);
  v21 = *(_OWORD *)&pvarg.vt;
  v9 = v13(v19, L"AllowXsltScript", &v21);
  VariantClear(&pvarg);
  if ( v9 < 0 )
  {
LABEL_5:
    LODWORD(ppv) = v9;
    goto LABEL_3;
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v19 + 576LL))(v19, 0);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_2;
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v19 + 504LL))(v19, 0);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_2;
  if ( a3 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int16 *))(*(_QWORD *)v19 + 520LL))(v19, a3, &v18);
  }
  else
  {
    if ( !a2 )
    {
      v9 = -2147024809;
      goto LABEL_21;
    }
    v14 = a2->pRecInfo;
    v15 = *(_QWORD *)v19;
    v21 = *(_OWORD *)&a2->vt;
    pRecInfo = v14;
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int16 *))(v15 + 464))(v19, &v21, &v18);
  }
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_2;
  if ( !v18 )
  {
    if ( !a4
      || (v8 = (*(__int64 (__fastcall **)(LPVOID, struct IXMLDOMParseError **))(*(_QWORD *)v19 + 480LL))(v19, a4),
          v9 = v8,
          v8 >= 0) )
    {
      v9 = -2147467259;
      goto LABEL_21;
    }
LABEL_2:
    LODWORD(ppv) = v8;
LABEL_3:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\utils.cpp",
      "WdcCreateXmlDocument",
      0,
      L"FAILURE: 0x%08x",
      ppv);
    goto LABEL_21;
  }
  v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IXMLDOMDocument **))v19)(v19, &IID_IXMLDOMDocument, a1);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_2;
LABEL_21:
  if ( v19 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180067730  push    rbp
0x180067732  push    rbx
0x180067733  push    rsi
0x180067734  push    rdi
0x180067735  push    r12
0x180067737  push    r14
0x180067739  push    r15
0x18006773b  mov     rbp, rsp
0x18006773e  sub     rsp, 80h
0x180067745  xor     eax, eax
0x180067747  mov     rdi, rdx
0x18006774a  xor     edx, edx; pUnkOuter
0x18006774c  mov     [rbp+var_50], ax
0x180067750  mov     [rbp+var_48], rax
0x180067754  mov     rsi, r9
0x180067757  mov     r14, r8
0x18006775a  lea     rax, [rbp+var_48]
0x18006775e  mov     r15, rcx
0x180067761  mov     [rsp+80h+ppv], rax; ppv
0x180067766  lea     r8d, [rdx+15h]; dwClsContext
0x18006776a  lea     r9, IID_IXMLDOMDocument; riid
0x180067771  lea     rcx, CLSID_FreeThreadedDOMDocument; rclsid
0x180067778  call    cs:__imp_CoCreateInstance
0x18006777e  mov     ebx, eax
0x180067780  test    eax, eax
0x180067782  jns     short loc_1800677AA
0x180067784  mov     dword ptr [rsp+80h+ppv], eax
0x180067788  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18006778f  xor     r8d, r8d; int
0x180067792  lea     rdx, aWdccreatexmldo; "WdcCreateXmlDocument"
0x180067799  lea     rcx, aBaseDiagnosisP_13; "base\\diagnosis\\pdui\\perfmon\\mmc\\ut"...
0x1800677a0  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x1800677a5  jmp     loc_18006793B
0x1800677aa  mov     rcx, [rbp+var_48]
0x1800677ae  lea     r8, [rbp+var_20]
0x1800677b2  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800677b7  or      edx, 0FFFFFFFFh
0x1800677ba  mov     r12d, 0Bh
0x1800677c0  movsd   [rbp+var_10], xmm1
0x1800677c5  mov     rax, [rcx]
0x1800677c8  mov     word ptr [rbp+pvarg+8], dx
0x1800677cc  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x1800677d3  mov     word ptr [rbp+pvarg], r12w
0x1800677d8  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800677dc  mov     rax, [rax+280h]
0x1800677e3  movaps  [rbp+var_20], xmm0
0x1800677e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800677ec  lea     rcx, [rbp+pvarg]; pvarg
0x1800677f0  mov     ebx, eax
0x1800677f2  call    cs:__imp_VariantClear
0x1800677f8  test    ebx, ebx
0x1800677fa  jns     short loc_180067802
0x1800677fc  mov     dword ptr [rsp+80h+ppv], ebx
0x180067800  jmp     short loc_180067788
0x180067802  mov     rcx, [rbp+var_48]
0x180067806  lea     r8, [rbp+var_20]
0x18006780a  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18006780f  xor     edx, edx
0x180067811  movsd   [rbp+var_10], xmm1
0x180067816  mov     rax, [rcx]
0x180067819  mov     word ptr [rbp+pvarg+8], dx
0x18006781d  lea     rdx, aAllowxsltscrip; "AllowXsltScript"
0x180067824  mov     word ptr [rbp+pvarg], r12w
0x180067829  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18006782d  mov     rax, [rax+280h]
0x180067834  movaps  [rbp+var_20], xmm0
0x180067838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006783d  lea     rcx, [rbp+pvarg]; pvarg
0x180067841  mov     ebx, eax
0x180067843  call    cs:__imp_VariantClear
0x180067849  test    ebx, ebx
0x18006784b  js      short loc_1800677FC
0x18006784d  mov     rcx, [rbp+var_48]
0x180067851  xor     edx, edx
0x180067853  mov     rax, [rcx]
0x180067856  mov     rax, [rax+240h]
0x18006785d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067862  mov     ebx, eax
0x180067864  test    eax, eax
0x180067866  js      loc_180067784
0x18006786c  mov     rcx, [rbp+var_48]
0x180067870  xor     edx, edx
0x180067872  mov     rax, [rcx]
0x180067875  mov     rax, [rax+1F8h]
0x18006787c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067881  mov     ebx, eax
0x180067883  test    eax, eax
0x180067885  js      loc_180067784
0x18006788b  test    r14, r14
0x18006788e  jz      short loc_1800678E8
0x180067890  mov     rcx, [rbp+var_48]
0x180067894  mov     rdx, r14
0x180067897  mov     rax, [rcx]
0x18006789a  mov     rax, [rax+208h]
0x1800678a1  lea     r8, [rbp+var_50]
0x1800678a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800678aa  mov     ebx, eax
0x1800678ac  test    eax, eax
0x1800678ae  js      loc_180067784
0x1800678b4  xor     eax, eax
0x1800678b6  cmp     ax, [rbp+var_50]
0x1800678ba  jnz     short loc_180067912
0x1800678bc  test    rsi, rsi
0x1800678bf  jz      short loc_1800678E1
0x1800678c1  mov     rcx, [rbp+var_48]
0x1800678c5  mov     rdx, rsi
0x1800678c8  mov     rax, [rcx]
0x1800678cb  mov     rax, [rax+1E0h]
0x1800678d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800678d7  mov     ebx, eax
0x1800678d9  test    eax, eax
0x1800678db  js      loc_180067784
0x1800678e1  mov     ebx, 80004005h
0x1800678e6  jmp     short loc_18006793B
0x1800678e8  test    rdi, rdi
0x1800678eb  jz      short loc_180067936
0x1800678ed  mov     rcx, [rbp+var_48]
0x1800678f1  lea     rdx, [rbp+var_20]
0x1800678f5  movups  xmm0, xmmword ptr [rdi]
0x1800678f8  movsd   xmm1, qword ptr [rdi+10h]
0x1800678fd  mov     rax, [rcx]
0x180067900  movaps  [rbp+var_20], xmm0
0x180067904  movsd   [rbp+var_10], xmm1
0x180067909  mov     rax, [rax+1D0h]
0x180067910  jmp     short loc_1800678A1
0x180067912  mov     rcx, [rbp+var_48]
0x180067916  lea     rdx, IID_IXMLDOMDocument
0x18006791d  mov     r8, r15
0x180067920  mov     rax, [rcx]
0x180067923  mov     rax, [rax]
0x180067926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006792b  mov     ebx, eax
0x18006792d  test    eax, eax
0x18006792f  jns     short loc_18006793B
0x180067931  jmp     loc_180067784
0x180067936  mov     ebx, 80070057h
0x18006793b  mov     rcx, [rbp+var_48]
0x18006793f  test    rcx, rcx
0x180067942  jz      short loc_180067950
0x180067944  mov     rax, [rcx]
0x180067947  mov     rax, [rax+10h]
0x18006794b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067950  mov     eax, ebx
0x180067952  add     rsp, 80h
0x180067959  pop     r15
0x18006795b  pop     r14
0x18006795d  pop     r12
0x18006795f  pop     rdi
0x180067960  pop     rsi
0x180067961  pop     rbx
0x180067962  pop     rbp
0x180067963  retn
```
