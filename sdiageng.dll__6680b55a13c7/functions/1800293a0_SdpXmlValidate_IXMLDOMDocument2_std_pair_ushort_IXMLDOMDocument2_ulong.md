# SdpXmlValidate(IXMLDOMDocument2 *,std::pair<ushort *,IXMLDOMDocument2 *> *,ulong)

- ea: `0x1800293a0`
- end: `0x18002972c`
- name: `?SdpXmlValidate@@YAJPEAUIXMLDOMDocument2@@PEAU?$pair@PEAGPEAUIXMLDOMDocument2@@@std@@K@Z`
- size: `908`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800176dc`

## callees

- `0x180026efc`
- `0x180026fa0`
- `0x1800293a0`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180029448`
- `ole32!CoCreateInstance` at `0x180029448`
- `OLEAUT32!__imp_SysFreeString` at `0x18002969c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800296b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002969c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800296b3`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180029635`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180029635`

## string_xrefs

- `0x180029687`: `SdpXmlValidate`

## pseudocode

```c
__int64 __fastcall SdpXmlValidate(__int64 *a1, __int64 a2)
{
  unsigned int v4; // r8d
  int v5; // r9d
  int v6; // ebx
  HRESULT ErrorInfo; // eax
  __int64 v8; // xmm6_8
  unsigned int i; // r14d
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(LPVOID, __int64, __int128 *); // rax
  __int64 v12; // rax
  __int64 (__fastcall *v13)(__int64 *, __int128 *); // rax
  LPVOID *ppv; // [rsp+28h] [rbp-79h]
  BSTR bstrString; // [rsp+38h] [rbp-69h] BYREF
  LPVOID v17; // [rsp+40h] [rbp-61h] BYREF
  IErrorInfo *pperrinfo; // [rsp+48h] [rbp-59h] BYREF
  BSTR v19; // [rsp+50h] [rbp-51h] BYREF
  __int64 v20; // [rsp+58h] [rbp-49h]
  __int128 v21; // [rsp+60h] [rbp-41h]
  __int64 v22; // [rsp+70h] [rbp-31h]
  __int128 v23; // [rsp+78h] [rbp-29h] BYREF
  __int64 v24; // [rsp+88h] [rbp-19h]
  __int128 v25; // [rsp+98h] [rbp-9h]
  int v26; // [rsp+108h] [rbp+67h] BYREF
  int v27; // [rsp+118h] [rbp+77h] BYREF
  __int64 v28; // [rsp+120h] [rbp+7Fh] BYREF

  v17 = 0;
  v28 = 0;
  v20 = 0;
  bstrString = 0;
  v19 = 0;
  v26 = -1;
  v27 = -1;
  v22 = 0;
  pperrinfo = 0;
  v25 = 0;
  v21 = 0;
  if ( !a1 )
  {
    v4 = 1355;
LABEL_3:
    v5 = -2147024809;
    v6 = -2147024809;
    goto LABEL_33;
  }
  if ( !a2 )
  {
    v4 = 1356;
    goto LABEL_3;
  }
  ErrorInfo = CoCreateInstance(&CLSID_XMLSchemaCache60, 0, 0x15u, &IID_IXMLDOMSchemaCollection, &v17);
  v6 = ErrorInfo;
  if ( ErrorInfo >= 0 )
  {
    (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v17 + 120LL))(v17, 0xFFFFFFFFLL);
    v8 = v22;
    for ( i = 0; i < 2; ++i )
    {
      LOWORD(v21) = 13;
      v24 = v8;
      v10 = *(_QWORD *)(a2 + 16LL * i);
      *((_QWORD *)&v21 + 1) = *(_QWORD *)(a2 + 16LL * i + 8);
      v11 = *(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)v17 + 56LL);
      v23 = v21;
      v6 = v11(v17, v10, &v23);
      if ( v6 < 0 )
      {
        if ( pperrinfo )
        {
          ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
          pperrinfo = 0;
        }
        ErrorInfo = GetErrorInfo(0, &pperrinfo);
        if ( ErrorInfo < 0 )
        {
          v4 = 1387;
        }
        else
        {
          ErrorInfo = ((__int64 (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(
                        pperrinfo,
                        &bstrString);
          if ( ErrorInfo >= 0 )
          {
            SdpDebugPrint(1u, "Schema error: %ws\n", bstrString);
            v5 = v6;
            v4 = 1396;
            goto LABEL_33;
          }
          v4 = 1390;
        }
        goto LABEL_32;
      }
    }
    *((_QWORD *)&v25 + 1) = v17;
    v12 = *a1;
    LOWORD(v25) = 13;
    v13 = *(__int64 (__fastcall **)(__int64 *, __int128 *))(v12 + 624);
    v23 = v25;
    v24 = v20;
    ErrorInfo = v13(a1, &v23);
    v6 = ErrorInfo;
    if ( ErrorInfo < 0 )
    {
      v4 = 1403;
      goto LABEL_32;
    }
    ErrorInfo = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*a1 + 632))(a1, &v28);
    v6 = ErrorInfo;
    if ( ErrorInfo < 0 )
    {
      v4 = 1409;
      goto LABEL_32;
    }
    if ( ErrorInfo != 1 )
      goto LABEL_34;
    ErrorInfo = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 72LL))(v28, &bstrString);
    v6 = ErrorInfo;
    if ( ErrorInfo < 0 )
    {
      v4 = 1417;
      goto LABEL_32;
    }
    ErrorInfo = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 80LL))(v28, &v19);
    v6 = ErrorInfo;
    if ( ErrorInfo < 0 )
    {
      v4 = 1420;
      goto LABEL_32;
    }
    ErrorInfo = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 88LL))(v28, &v26);
    v6 = ErrorInfo;
    if ( ErrorInfo < 0 )
    {
      v4 = 1423;
      goto LABEL_32;
    }
    ErrorInfo = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 96LL))(v28, &v27);
    v6 = ErrorInfo;
    if ( ErrorInfo < 0 )
    {
      v4 = 1426;
      goto LABEL_32;
    }
    LODWORD(ppv) = v26;
    SdpDebugPrint(1u, "Document error: %ws in %ws on %d:%d\n", bstrString, v19, ppv, v27);
    v5 = -2147024809;
    v4 = 1440;
    v6 = -2147024809;
  }
  else
  {
    v4 = 1366;
LABEL_32:
    v5 = ErrorInfo;
  }
LABEL_33:
  SdpDebugTrace(1u, L"SdpXmlValidate", v4, v5);
LABEL_34:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v19 )
  {
    SysFreeString(v19);
    v19 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( pperrinfo )
    ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800293a0  mov     rax, rsp
0x1800293a3  mov     [rax+18h], r8d
0x1800293a7  push    rbp
0x1800293a8  push    rbx
0x1800293a9  push    rsi
0x1800293aa  push    rdi
0x1800293ab  push    r13
0x1800293ad  push    r14
0x1800293af  push    r15
0x1800293b1  lea     rbp, [rax-5Fh]
0x1800293b5  sub     rsp, 0C0h
0x1800293bc  or      edi, 0FFFFFFFFh
0x1800293bf  movaps  xmmword ptr [rax-48h], xmm6
0x1800293c3  xor     eax, eax
0x1800293c5  mov     [rbp+57h+var_B8], 0
0x1800293cd  mov     [rbp+57h+arg_18], 0
0x1800293d5  xorps   xmm0, xmm0
0x1800293d8  mov     [rbp+57h+var_A0], rax
0x1800293dc  mov     r15, rdx
0x1800293df  mov     [rbp+57h+bstrString], rax
0x1800293e3  mov     rsi, rcx
0x1800293e6  mov     [rbp+57h+var_A8], rax
0x1800293ea  mov     [rbp+57h+arg_0], edi
0x1800293ed  mov     [rbp+57h+arg_10], edi
0x1800293f0  mov     [rbp+57h+var_88], rax
0x1800293f4  mov     [rbp+57h+pperrinfo], rax
0x1800293f8  movups  [rbp+57h+var_60], xmm0
0x1800293fc  movups  [rbp+57h+var_98], xmm0
0x180029400  test    rcx, rcx
0x180029403  jnz     short loc_18002941E
0x180029405  mov     r8d, 54Bh
0x18002940b  mov     r9d, 80070057h
0x180029411  mov     ecx, 1
0x180029416  mov     ebx, r9d
0x180029419  jmp     loc_180029687
0x18002941e  test    r15, r15
0x180029421  jnz     short loc_18002942B
0x180029423  mov     r8d, 54Ch
0x180029429  jmp     short loc_18002940B
0x18002942b  xor     edx, edx; pUnkOuter
0x18002942d  lea     rax, [rbp+57h+var_B8]
0x180029431  lea     r9, IID_IXMLDOMSchemaCollection; riid
0x180029438  mov     [rsp+0F0h+ppv], rax; ppv
0x18002943d  lea     rcx, CLSID_XMLSchemaCache60; rclsid
0x180029444  lea     r8d, [rdx+15h]; dwClsContext
0x180029448  call    cs:__imp_CoCreateInstance
0x18002944e  mov     ebx, eax
0x180029450  test    eax, eax
0x180029452  jns     short loc_180029464
0x180029454  mov     r8d, 556h
0x18002945a  mov     ecx, 1
0x18002945f  jmp     loc_180029684
0x180029464  mov     rcx, [rbp+57h+var_B8]
0x180029468  mov     edx, edi
0x18002946a  mov     rax, [rcx]
0x18002946d  mov     rax, [rax+78h]
0x180029471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029476  movsd   xmm6, [rbp+57h+var_88]
0x18002947b  xor     r14d, r14d
0x18002947e  lea     edi, [r14+1]
0x180029482  lea     r13d, [r14+0Dh]
0x180029486  mov     rcx, [rbp+57h+var_B8]
0x18002948a  lea     r8, [rbp+57h+var_80]
0x18002948e  mov     edx, r14d
0x180029491  add     rdx, rdx
0x180029494  mov     word ptr [rbp+57h+var_98], r13w
0x180029499  movsd   [rbp+57h+var_70], xmm6
0x18002949e  mov     rax, [r15+rdx*8+8]
0x1800294a3  mov     rdx, [r15+rdx*8]
0x1800294a7  mov     qword ptr [rbp+57h+var_98+8], rax
0x1800294ab  mov     rax, [rcx]
0x1800294ae  movups  xmm0, [rbp+57h+var_98]
0x1800294b2  mov     rax, [rax+38h]
0x1800294b6  movaps  [rbp+57h+var_80], xmm0
0x1800294ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294bf  mov     ebx, eax
0x1800294c1  test    eax, eax
0x1800294c3  js      loc_180029612
0x1800294c9  add     r14d, edi
0x1800294cc  cmp     r14d, 2
0x1800294d0  jb      short loc_180029486
0x1800294d2  mov     rax, [rbp+57h+var_B8]
0x1800294d6  lea     rdx, [rbp+57h+var_80]
0x1800294da  movsd   xmm1, [rbp+57h+var_A0]
0x1800294df  mov     rcx, rsi
0x1800294e2  mov     qword ptr [rbp+57h+var_60+8], rax
0x1800294e6  mov     rax, [rsi]
0x1800294e9  mov     word ptr [rbp+57h+var_60], r13w
0x1800294ee  movups  xmm0, [rbp+57h+var_60]
0x1800294f2  mov     rax, [rax+270h]
0x1800294f9  movaps  [rbp+57h+var_80], xmm0
0x1800294fd  movsd   [rbp+57h+var_70], xmm1
0x180029502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029507  mov     ebx, eax
0x180029509  test    eax, eax
0x18002950b  jns     short loc_180029518
0x18002950d  mov     r8d, 57Bh
0x180029513  jmp     loc_180029682
0x180029518  mov     rax, [rsi]
0x18002951b  lea     rdx, [rbp+57h+arg_18]
0x18002951f  mov     rcx, rsi
0x180029522  mov     rax, [rax+278h]
0x180029529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002952e  mov     ebx, eax
0x180029530  test    eax, eax
0x180029532  jns     short loc_18002953F
0x180029534  mov     r8d, 581h
0x18002953a  jmp     loc_180029682
0x18002953f  cmp     eax, edi
0x180029541  jnz     loc_180029693
0x180029547  mov     rcx, [rbp+57h+arg_18]
0x18002954b  lea     rdx, [rbp+57h+bstrString]
0x18002954f  mov     rax, [rcx]
0x180029552  mov     rax, [rax+48h]
0x180029556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002955b  mov     ebx, eax
0x18002955d  test    eax, eax
0x18002955f  jns     short loc_18002956C
0x180029561  mov     r8d, 589h
0x180029567  jmp     loc_180029682
0x18002956c  mov     rcx, [rbp+57h+arg_18]
0x180029570  lea     rdx, [rbp+57h+var_A8]
0x180029574  mov     rax, [rcx]
0x180029577  mov     rax, [rax+50h]
0x18002957b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029580  mov     ebx, eax
0x180029582  test    eax, eax
0x180029584  jns     short loc_180029591
0x180029586  mov     r8d, 58Ch
0x18002958c  jmp     loc_180029682
0x180029591  mov     rcx, [rbp+57h+arg_18]
0x180029595  lea     rdx, [rbp+57h+arg_0]
0x180029599  mov     rax, [rcx]
0x18002959c  mov     rax, [rax+58h]
0x1800295a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295a5  mov     ebx, eax
0x1800295a7  test    eax, eax
0x1800295a9  jns     short loc_1800295B6
0x1800295ab  mov     r8d, 58Fh
0x1800295b1  jmp     loc_180029682
0x1800295b6  mov     rcx, [rbp+57h+arg_18]
0x1800295ba  lea     rdx, [rbp+57h+arg_10]
0x1800295be  mov     rax, [rcx]
0x1800295c1  mov     rax, [rax+60h]
0x1800295c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295ca  mov     ebx, eax
0x1800295cc  mov     ecx, edi; Level
0x1800295ce  test    eax, eax
0x1800295d0  jns     short loc_1800295DD
0x1800295d2  mov     r8d, 592h
0x1800295d8  jmp     loc_180029684
0x1800295dd  mov     eax, [rbp+57h+arg_10]
0x1800295e0  lea     rdx, aDocumentErrorW; "Document error: %ws in %ws on %d:%d\n"
0x1800295e7  mov     r9, [rbp+57h+var_A8]
0x1800295eb  mov     r8, [rbp+57h+bstrString]
0x1800295ef  mov     [rsp+28h], eax
0x1800295f3  mov     eax, [rbp+57h+arg_0]
0x1800295f6  mov     dword ptr [rsp+0F0h+ppv], eax
0x1800295fa  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1800295ff  mov     r9d, 80070057h
0x180029605  mov     r8d, 5A0h
0x18002960b  mov     ebx, r9d
0x18002960e  mov     ecx, edi
0x180029610  jmp     short loc_180029687
0x180029612  mov     rcx, [rbp+57h+pperrinfo]
0x180029616  test    rcx, rcx
0x180029619  jz      short loc_18002962F
0x18002961b  mov     rax, [rcx]
0x18002961e  mov     rax, [rax+10h]
0x180029622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029627  mov     [rbp+57h+pperrinfo], 0
0x18002962f  lea     rdx, [rbp+57h+pperrinfo]; pperrinfo
0x180029633  xor     ecx, ecx; dwReserved
0x180029635  call    cs:__imp_GetErrorInfo
0x18002963b  test    eax, eax
0x18002963d  js      short loc_18002967C
0x18002963f  mov     rcx, [rbp+57h+pperrinfo]
0x180029643  lea     rdx, [rbp+57h+bstrString]
0x180029647  mov     rax, [rcx]
0x18002964a  mov     rax, [rax+28h]
0x18002964e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029653  mov     ecx, edi; Level
0x180029655  test    eax, eax
0x180029657  js      short loc_180029674
0x180029659  mov     r8, [rbp+57h+bstrString]
0x18002965d  lea     rdx, aSchemaErrorWs; "Schema error: %ws\n"
0x180029664  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x180029669  mov     r9d, ebx
0x18002966c  mov     r8d, 574h
0x180029672  jmp     short loc_18002960E
0x180029674  mov     r8d, 56Eh
0x18002967a  jmp     short loc_180029684
0x18002967c  mov     r8d, 56Bh; int
0x180029682  mov     ecx, edi; Level
0x180029684  mov     r9d, eax; int
0x180029687  lea     rdx, aSdpxmlvalidate; "SdpXmlValidate"
0x18002968e  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180029693  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180029697  test    rcx, rcx
0x18002969a  jz      short loc_1800296AA
0x18002969c  call    cs:__imp_SysFreeString
0x1800296a2  mov     [rbp+57h+bstrString], 0
0x1800296aa  mov     rcx, [rbp+57h+var_A8]; bstrString
0x1800296ae  test    rcx, rcx
0x1800296b1  jz      short loc_1800296C1
0x1800296b3  call    cs:__imp_SysFreeString
0x1800296b9  mov     [rbp+57h+var_A8], 0
0x1800296c1  mov     rcx, [rbp+57h+var_B8]
0x1800296c5  test    rcx, rcx
0x1800296c8  jz      short loc_1800296DE
0x1800296ca  mov     rax, [rcx]
0x1800296cd  mov     rax, [rax+10h]
0x1800296d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296d6  mov     [rbp+57h+var_B8], 0
0x1800296de  mov     rcx, [rbp+57h+arg_18]
0x1800296e2  test    rcx, rcx
0x1800296e5  jz      short loc_1800296FB
0x1800296e7  mov     rax, [rcx]
0x1800296ea  mov     rax, [rax+10h]
0x1800296ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296f3  mov     [rbp+57h+arg_18], 0
0x1800296fb  mov     rcx, [rbp+57h+pperrinfo]
0x1800296ff  test    rcx, rcx
0x180029702  jz      short loc_180029710
0x180029704  mov     rax, [rcx]
0x180029707  mov     rax, [rax+10h]
0x18002970b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029710  movaps  xmm6, [rsp+0F0h+var_48+8]
0x180029718  mov     eax, ebx
0x18002971a  add     rsp, 0C0h
0x180029721  pop     r15
0x180029723  pop     r14
0x180029725  pop     r13
0x180029727  pop     rdi
0x180029728  pop     rsi
0x180029729  pop     rbx
0x18002972a  pop     rbp
0x18002972b  retn
```
