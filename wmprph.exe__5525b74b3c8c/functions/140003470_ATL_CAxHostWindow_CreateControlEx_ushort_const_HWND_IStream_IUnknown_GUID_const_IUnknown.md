# ATL::CAxHostWindow::CreateControlEx(ushort const *,HWND__ *,IStream *,IUnknown * *,_GUID const &,IUnknown *)

- ea: `0x140003470`
- end: `0x1400039a9`
- name: `?CreateControlEx@CAxHostWindow@ATL@@UEAAJPEBGPEAUHWND__@@PEAUIStream@@PEAPEAUIUnknown@@AEBU_GUID@@PEAU5@@Z`
- size: `1337`
- prototype: `int(ATL::CAxHostWindow *__hidden this, const unsigned __int16 *, HWND, struct IStream *, struct IUnknown **, const struct _GUID *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x140001390`
- `0x140002420`
- `0x140003470`
- `0x140003aa4`
- `0x140007c2c`
- `0x140007eec`
- `0x140008a74`
- `0x14000f010`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x140003545`
- `KERNEL32!lstrcmpW` at `0x140003545`
- `USER32!GetWindowLongW` at `0x140003675`
- `USER32!GetWindowLongW` at `0x140003696`
- `USER32!GetWindowLongW` at `0x140003675`
- `USER32!GetWindowLongW` at `0x140003696`
- `USER32!RedrawWindow` at `0x1400034d1`
- `USER32!RedrawWindow` at `0x140003975`
- `USER32!RedrawWindow` at `0x1400034d1`
- `USER32!RedrawWindow` at `0x140003975`
- `USER32!SetWindowPos` at `0x1400036ce`
- `USER32!SetWindowPos` at `0x1400036ce`
- `USER32!IsWindow` at `0x1400034e2`
- `USER32!IsWindow` at `0x1400034e2`
- `USER32!GetParent` at `0x140003521`
- `USER32!GetParent` at `0x140003521`
- `USER32!SetWindowLongW` at `0x1400036aa`
- `USER32!SetWindowLongW` at `0x1400036aa`
- `USER32!GetClassNameW` at `0x140003534`
- `USER32!GetClassNameW` at `0x140003534`
- `USER32!GetSysColor` at `0x140003559`
- `USER32!GetSysColor` at `0x140003559`
- `OLEAUT32!__imp_SysAllocString` at `0x1400037e5`
- `OLEAUT32!__imp_SysAllocString` at `0x14000388f`
- `OLEAUT32!__imp_SysAllocString` at `0x1400037e5`
- `OLEAUT32!__imp_SysAllocString` at `0x14000388f`
- `OLEAUT32!__imp_SysFreeString` at `0x140003801`
- `OLEAUT32!__imp_SysFreeString` at `0x140003801`
- `OLEAUT32!__imp_VariantClear` at `0x140003877`
- `OLEAUT32!__imp_VariantClear` at `0x140003911`
- `OLEAUT32!__imp_VariantClear` at `0x140003925`
- `OLEAUT32!__imp_VariantClear` at `0x140003877`
- `OLEAUT32!__imp_VariantClear` at `0x140003911`
- `OLEAUT32!__imp_VariantClear` at `0x140003925`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::CreateControlEx(
        ATL::CAxHostWindow *this,
        unsigned __int16 *a2,
        HWND a3,
        struct IStream *a4,
        struct IUnknown **a5,
        const struct _GUID *a6,
        struct IUnknown *a7)
{
  ATL::CAxHostWindow *v7; // r13
  int NormalizedObject; // edi
  HWND v12; // rcx
  __int64 v13; // rdx
  HWND Parent; // rax
  int v15; // eax
  int v16; // ecx
  int (__fastcall ***v17)(LPVOID, GUID *, VARIANTARG *); // rcx
  int (__fastcall **v18)(LPVOID, GUID *, VARIANTARG *); // rax
  LONG WindowLongW; // eax
  void (__fastcall ***v20)(LPVOID, GUID *, struct IStream **); // r15
  void (__fastcall **v21)(LPVOID, GUID *, struct IStream **); // rax
  __int64 (__fastcall **v22)(LPVOID, GUID *, struct IStream **); // rax
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, OLECHAR *); // rdi
  OLECHAR *v25; // rbx
  struct IStream *v26; // rcx
  void (__fastcall **v27)(LPVOID, GUID *, struct IStream **); // rax
  HRESULT v28; // eax
  LONG lVal; // edx
  HWND v30; // rcx
  char v32[8]; // [rsp+40h] [rbp-51h] BYREF
  struct IStream *v33; // [rsp+48h] [rbp-49h] BYREF
  struct IStream *v34; // [rsp+50h] [rbp-41h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-39h] BYREF
  VARIANTARG ClassName; // [rsp+70h] [rbp-21h] BYREF

  v7 = (ATL::CAxHostWindow *)((char *)this - 64);
  v34 = a4;
  NormalizedObject = 1;
  ATL::CAxHostWindow::ReleaseAll((ATL::CAxHostWindow *)((char *)this - 64));
  v12 = (HWND)*((_QWORD *)this - 7);
  if ( v12 )
  {
    RedrawWindow(v12, 0, 0, 0x507u);
    ATL::CAxHostWindow::ReleaseWindow(v7);
  }
  if ( IsWindow(a3) )
  {
    *((_DWORD *)v7 + 73) ^= ((unsigned __int8)*((_DWORD *)v7 + 73)
                           ^ (unsigned __int8)(16
                                             * ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::SubclassWindow(
                                                 (size_t)v7,
                                                 a3)))
                          & 0x10;
    if ( !*((_DWORD *)this + 58) )
    {
      Parent = GetParent(*((HWND *)this - 7));
      GetClassNameW(Parent, &ClassName.vt, 8);
      v15 = lstrcmpW(&ClassName.vt, L"#32770");
      v16 = 15;
      if ( v15 )
        v16 = 5;
      *((_DWORD *)this + 58) = GetSysColor(v16);
    }
    v32[0] = 0;
    NormalizedObject = ATL::CreateNormalizedObject(a2, v13, (LPVOID *)a5, v32);
    if ( NormalizedObject >= 0 )
      NormalizedObject = ATL::CAxHostWindow::ActivateAx(v7, *a5, NormalizedObject == 1, v34);
    *((struct _GUID *)this + 10) = *a6;
    if ( NormalizedObject < 0 )
      goto LABEL_56;
    v17 = (int (__fastcall ***)(LPVOID, GUID *, VARIANTARG *))*a5;
    if ( *a5 && a7 )
    {
      v18 = *v17;
      *(_QWORD *)&ClassName.vt = 0;
      v33 = 0;
      if ( (*v18)(v17, &IID_IConnectionPointContainer, &ClassName) >= 0
        && (*(int (__fastcall **)(_QWORD, char *, struct IStream **))(**(_QWORD **)&ClassName.vt + 32LL))(
             *(_QWORD *)&ClassName.vt,
             (char *)this + 160,
             &v33) >= 0 )
      {
        ((void (__fastcall *)(struct IStream *, struct IUnknown *, char *))v33->lpVtbl->Seek)(
          v33,
          a7,
          (char *)this + 180);
      }
      if ( v33 )
        ((void (__fastcall *)(struct IStream *))v33->lpVtbl->Release)(v33);
      if ( *(_QWORD *)&ClassName.vt )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&ClassName.vt + 16LL))(*(_QWORD *)&ClassName.vt);
    }
    if ( !v32[0] || !*a5 )
    {
LABEL_55:
      if ( *((_QWORD *)this + 12) )
        return (unsigned int)NormalizedObject;
      goto LABEL_56;
    }
    if ( (GetWindowLongW(*((HWND *)this - 7), -16) & 0x300000) != 0 )
    {
      WindowLongW = GetWindowLongW(*((HWND *)this - 7), -16);
      SetWindowLongW(*((HWND *)this - 7), -16, WindowLongW & 0xFFCFFFFF);
      SetWindowPos(*((HWND *)this - 7), 0, 0, 0, 0, 0, 0x37u);
    }
    else
    {
      *((_DWORD *)this + 66) |= 8u;
    }
    v20 = (void (__fastcall ***)(LPVOID, GUID *, struct IStream **))*a5;
    if ( *a5 )
      ((void (__fastcall *)(void (__fastcall ***)(LPVOID, GUID *, struct IStream **)))(*v20)[1])(v20);
    if ( ((*a2 - 77) & 0xFFDF) != 0
      || ((a2[1] - 83) & 0xFFDF) != 0
      || ((a2[2] - 72) & 0xFFDF) != 0
      || ((a2[3] - 84) & 0xFFDF) != 0
      || ((a2[4] - 77) & 0xFFDF) != 0
      || ((a2[5] - 76) & 0xFFDF) != 0
      || a2[6] != 58 )
    {
      v27 = *v20;
      v33 = 0;
      (*v27)(v20, &IID_IWebBrowser2, &v33);
      if ( !v33 )
        goto LABEL_54;
      ClassName.vt = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      v28 = VariantClear(&ClassName);
      lVal = ClassName.lVal;
      ClassName.vt = 8;
      if ( v28 < 0 )
        lVal = v28;
      ClassName.lVal = lVal;
      ClassName.llVal = (LONGLONG)SysAllocString(a2);
      if ( !ClassName.llVal )
      {
        ClassName.lVal = -2147024882;
        ClassName.vt = 10;
      }
      ((void (__fastcall *)(struct IStream *, __int64))v33->lpVtbl[2].Clone)(v33, 0xFFFFFFFFLL);
      ((void (__fastcall *)(struct IStream *, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))v33->lpVtbl[3].LockRegion)(
        v33,
        &ClassName,
        &pvarg,
        &pvarg,
        &pvarg,
        &pvarg);
      if ( ClassName.vt == 4095 )
        ClassName.vt = 8;
      VariantClear(&ClassName);
      if ( pvarg.vt == 4095 )
        pvarg.vt = 8;
      VariantClear(&pvarg);
      v26 = v33;
    }
    else
    {
      v21 = *v20;
      v34 = 0;
      (*v21)(v20, &IID_IPersistStreamInit, &v34);
      ((void (__fastcall *)(struct IStream *))v34->lpVtbl->Commit)(v34);
      v22 = (__int64 (__fastcall **)(LPVOID, GUID *, struct IStream **))*v20;
      v33 = 0;
      NormalizedObject = (*v22)(v20, &IID_IHTMLDocument2, &v33);
      if ( NormalizedObject >= 0 )
      {
        *(_QWORD *)&ClassName.vt = 0;
        NormalizedObject = ((__int64 (__fastcall *)(struct IStream *, VARIANTARG *))v33->lpVtbl->Revert)(
                             v33,
                             &ClassName);
        if ( NormalizedObject >= 0 )
        {
          v23 = *(_QWORD *)&ClassName.vt;
          v24 = *(__int64 (__fastcall **)(__int64, OLECHAR *))(**(_QWORD **)&ClassName.vt + 456LL);
          v25 = SysAllocString(a2 + 7);
          NormalizedObject = v24(v23, v25);
          SysFreeString(v25);
        }
        if ( *(_QWORD *)&ClassName.vt )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&ClassName.vt + 16LL))(*(_QWORD *)&ClassName.vt);
      }
      if ( v33 )
        ((void (__fastcall *)(struct IStream *))v33->lpVtbl->Release)(v33);
      v26 = v34;
    }
    if ( v26 )
      ((void (__fastcall *)(struct IStream *))v26->lpVtbl->Release)(v26);
LABEL_54:
    ((void (__fastcall *)(void (__fastcall ***)(LPVOID, GUID *, struct IStream **)))(*v20)[2])(v20);
    if ( NormalizedObject >= 0 )
      goto LABEL_55;
LABEL_56:
    ATL::CAxHostWindow::ReleaseAll(v7);
    v30 = (HWND)*((_QWORD *)this - 7);
    if ( v30 )
    {
      RedrawWindow(v30, 0, 0, 0x507u);
      if ( NormalizedObject < 0 )
        ATL::CAxHostWindow::ReleaseWindow(v7);
    }
  }
  return (unsigned int)NormalizedObject;
}

```

## disassembly

```asm
0x140003470  push    rbp
0x140003472  push    rbx
0x140003473  push    rsi
0x140003474  push    rdi
0x140003475  push    r12
0x140003477  push    r13
0x140003479  push    r14
0x14000347b  push    r15
0x14000347d  lea     rbp, [rsp-7]
0x140003482  sub     rsp, 98h
0x140003489  mov     rax, cs:__security_cookie
0x140003490  xor     rax, rsp
0x140003493  mov     [rbp+3Fh+var_48], rax
0x140003497  mov     r15, [rbp+3Fh+arg_20]
0x14000349b  lea     r13, [rcx-40h]
0x14000349f  mov     r12, [rbp+3Fh+arg_30]
0x1400034a3  mov     r14, rcx
0x1400034a6  mov     rcx, r13; this
0x1400034a9  mov     [rbp+3Fh+var_80], r9
0x1400034ad  mov     rsi, r8
0x1400034b0  mov     rbx, rdx
0x1400034b3  mov     edi, 1
0x1400034b8  call    ?ReleaseAll@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseAll(void)
0x1400034bd  mov     rcx, [r14-38h]; hWnd
0x1400034c1  test    rcx, rcx
0x1400034c4  jz      short loc_1400034DF
0x1400034c6  mov     r9d, 507h; flags
0x1400034cc  xor     r8d, r8d; hrgnUpdate
0x1400034cf  xor     edx, edx; lprcUpdate
0x1400034d1  call    cs:__imp_RedrawWindow
0x1400034d7  mov     rcx, r13; this
0x1400034da  call    ?ReleaseWindow@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseWindow(void)
0x1400034df  mov     rcx, rsi; hWnd
0x1400034e2  call    cs:__imp_IsWindow
0x1400034e8  test    eax, eax
0x1400034ea  jz      loc_140003987
0x1400034f0  mov     rdx, rsi; hWnd
0x1400034f3  mov     rcx, r13; FirstParameter
0x1400034f6  call    ?SubclassWindow@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAHPEAUHWND__@@@Z; ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::SubclassWindow(HWND__ *)
0x1400034fb  mov     ecx, [r13+124h]
0x140003502  shl     eax, 4
0x140003505  xor     eax, ecx
0x140003507  and     eax, 10h
0x14000350a  xor     eax, ecx
0x14000350c  mov     [r13+124h], eax
0x140003513  cmp     dword ptr [r14+0E8h], 0
0x14000351b  jnz     short loc_140003566
0x14000351d  mov     rcx, [r14-38h]; hWnd
0x140003521  call    cs:__imp_GetParent
0x140003527  mov     r8d, 8; nMaxCount
0x14000352d  lea     rdx, [rbp+3Fh+ClassName]; lpClassName
0x140003531  mov     rcx, rax; hWnd
0x140003534  call    cs:__imp_GetClassNameW
0x14000353a  lea     rdx, String2; "#32770"
0x140003541  lea     rcx, [rbp+3Fh+ClassName]; lpString1
0x140003545  call    cs:__imp_lstrcmpW
0x14000354b  mov     ecx, 0Fh
0x140003550  test    eax, eax
0x140003552  jz      short loc_140003559
0x140003554  mov     ecx, 5; nIndex
0x140003559  call    cs:__imp_GetSysColor
0x14000355f  mov     [r14+0E8h], eax
0x140003566  lea     r9, [rbp+3Fh+var_90]
0x14000356a  mov     [rbp+3Fh+var_90], 0
0x14000356e  mov     r8, r15
0x140003571  mov     rcx, rbx; lpszProgID
0x140003574  call    ATL__CreateNormalizedObject
0x140003579  cmp     eax, 1
0x14000357c  mov     edi, eax
0x14000357e  setz    r8b; bool
0x140003582  test    eax, eax
0x140003584  js      short loc_140003597
0x140003586  mov     r9, [rbp+3Fh+var_80]; struct IStream *
0x14000358a  mov     rcx, r13; this
0x14000358d  mov     rdx, [r15]; struct IUnknown *
0x140003590  call    ?ActivateAx@CAxHostWindow@ATL@@QEAAJPEAUIUnknown@@_NPEAUIStream@@@Z; ATL::CAxHostWindow::ActivateAx(IUnknown *,bool,IStream *)
0x140003595  mov     edi, eax
0x140003597  mov     rax, [rbp+3Fh+arg_28]
0x14000359b  lea     rsi, [r14+0A0h]
0x1400035a2  movups  xmm0, xmmword ptr [rax]
0x1400035a5  movdqu  xmmword ptr [rsi], xmm0
0x1400035a9  test    edi, edi
0x1400035ab  js      loc_140003959
0x1400035b1  mov     rcx, [r15]
0x1400035b4  test    rcx, rcx
0x1400035b7  jz      loc_140003654
0x1400035bd  test    r12, r12
0x1400035c0  jz      loc_140003654
0x1400035c6  mov     rax, [rcx]
0x1400035c9  lea     r8, [rbp+3Fh+ClassName]
0x1400035cd  lea     rdx, IID_IConnectionPointContainer
0x1400035d4  mov     qword ptr [rbp+3Fh+ClassName], 0
0x1400035dc  mov     [rbp+3Fh+var_88], 0
0x1400035e4  mov     rax, [rax]
0x1400035e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035ec  test    eax, eax
0x1400035ee  js      short loc_140003625
0x1400035f0  mov     rcx, qword ptr [rbp+3Fh+ClassName]
0x1400035f4  lea     r8, [rbp+3Fh+var_88]
0x1400035f8  mov     rdx, rsi
0x1400035fb  mov     rax, [rcx]
0x1400035fe  mov     rax, [rax+20h]
0x140003602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003607  test    eax, eax
0x140003609  js      short loc_140003625
0x14000360b  mov     rcx, [rbp+3Fh+var_88]
0x14000360f  lea     r8, [r14+0B4h]
0x140003616  mov     rdx, r12
0x140003619  mov     rax, [rcx]
0x14000361c  mov     rax, [rax+28h]
0x140003620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003625  mov     rcx, [rbp+3Fh+var_88]
0x140003629  xor     r12d, r12d
0x14000362c  test    rcx, rcx
0x14000362f  jz      short loc_14000363D
0x140003631  mov     rax, [rcx]
0x140003634  mov     rax, [rax+10h]
0x140003638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000363d  mov     rcx, qword ptr [rbp+3Fh+ClassName]
0x140003641  test    rcx, rcx
0x140003644  jz      short loc_140003657
0x140003646  mov     rax, [rcx]
0x140003649  mov     rax, [rax+10h]
0x14000364d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003652  jmp     short loc_140003657
0x140003654  xor     r12d, r12d
0x140003657  cmp     [rbp+3Fh+var_90], r12b
0x14000365b  jz      loc_140003953
0x140003661  cmp     [r15], r12
0x140003664  jz      loc_140003953
0x14000366a  mov     rcx, [r14-38h]; hWnd
0x14000366e  mov     esi, 0FFFFFFF0h
0x140003673  mov     edx, esi; nIndex
0x140003675  call    cs:__imp_GetWindowLongW
0x14000367b  test    eax, 300000h
0x140003680  jnz     short loc_140003690
0x140003682  mov     esi, 8
0x140003687  or      [r14+108h], esi
0x14000368e  jmp     short loc_1400036D9
0x140003690  mov     rcx, [r14-38h]; hWnd
0x140003694  mov     edx, esi; nIndex
0x140003696  call    cs:__imp_GetWindowLongW
0x14000369c  mov     rcx, [r14-38h]; hWnd
0x1400036a0  mov     edx, esi; nIndex
0x1400036a2  and     eax, 0FFCFFFFFh
0x1400036a7  mov     r8d, eax; dwNewLong
0x1400036aa  call    cs:__imp_SetWindowLongW
0x1400036b0  mov     rcx, [r14-38h]; hWnd
0x1400036b4  xor     r9d, r9d; Y
0x1400036b7  mov     [rsp+0D0h+uFlags], 37h ; '7'; uFlags
0x1400036bf  xor     r8d, r8d; X
0x1400036c2  mov     [rsp+0D0h+cy], r12d; cy
0x1400036c7  xor     edx, edx; hWndInsertAfter
0x1400036c9  mov     [rsp+0D0h+var_B0], r12d; cx
0x1400036ce  call    cs:__imp_SetWindowPos
0x1400036d4  mov     esi, 8
0x1400036d9  mov     r15, [r15]
0x1400036dc  test    r15, r15
0x1400036df  jz      short loc_1400036F0
0x1400036e1  mov     rax, [r15]
0x1400036e4  mov     rcx, r15
0x1400036e7  mov     rax, [rax+8]
0x1400036eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036f0  movzx   eax, word ptr [rbx]
0x1400036f3  mov     ecx, 0FFDFh
0x1400036f8  sub     ax, 4Dh ; 'M'
0x1400036fc  test    cx, ax
0x1400036ff  jnz     loc_14000383A
0x140003705  movzx   eax, word ptr [rbx+2]
0x140003709  sub     ax, 53h ; 'S'
0x14000370d  test    cx, ax
0x140003710  jnz     loc_14000383A
0x140003716  movzx   eax, word ptr [rbx+4]
0x14000371a  sub     ax, 48h ; 'H'
0x14000371e  test    cx, ax
0x140003721  jnz     loc_14000383A
0x140003727  movzx   eax, word ptr [rbx+6]
0x14000372b  sub     ax, 54h ; 'T'
0x14000372f  test    cx, ax
0x140003732  jnz     loc_14000383A
0x140003738  movzx   eax, word ptr [rbx+8]
0x14000373c  sub     ax, 4Dh ; 'M'
0x140003740  test    cx, ax
0x140003743  jnz     loc_14000383A
0x140003749  movzx   eax, word ptr [rbx+0Ah]
0x14000374d  sub     ax, 4Ch ; 'L'
0x140003751  test    cx, ax
0x140003754  jnz     loc_14000383A
0x14000375a  cmp     word ptr [rbx+0Ch], 3Ah ; ':'
0x14000375f  jnz     loc_14000383A
0x140003765  mov     rax, [r15]
0x140003768  lea     r8, [rbp+3Fh+var_80]
0x14000376c  lea     rdx, IID_IPersistStreamInit
0x140003773  mov     [rbp+3Fh+var_80], r12
0x140003777  mov     rcx, r15
0x14000377a  mov     rax, [rax]
0x14000377d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003782  mov     rcx, [rbp+3Fh+var_80]
0x140003786  mov     rax, [rcx]
0x140003789  mov     rax, [rax+40h]
0x14000378d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003792  mov     rax, [r15]
0x140003795  lea     r8, [rbp+3Fh+var_88]
0x140003799  lea     rdx, IID_IHTMLDocument2
0x1400037a0  mov     [rbp+3Fh+var_88], r12
0x1400037a4  mov     rcx, r15
0x1400037a7  mov     rax, [rax]
0x1400037aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037af  mov     edi, eax
0x1400037b1  test    eax, eax
0x1400037b3  js      short loc_14000381C
0x1400037b5  mov     rcx, [rbp+3Fh+var_88]
0x1400037b9  lea     rdx, [rbp+3Fh+ClassName]
0x1400037bd  mov     qword ptr [rbp+3Fh+ClassName], r12
0x1400037c1  mov     rax, [rcx]
0x1400037c4  mov     rax, [rax+48h]
0x1400037c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037cd  mov     edi, eax
0x1400037cf  test    eax, eax
0x1400037d1  js      short loc_140003807
0x1400037d3  mov     rsi, qword ptr [rbp+3Fh+ClassName]
0x1400037d7  lea     rcx, [rbx+0Eh]; psz
0x1400037db  mov     rax, [rsi]
0x1400037de  mov     rdi, [rax+1C8h]
0x1400037e5  call    cs:__imp_SysAllocString
0x1400037eb  mov     rbx, rax
0x1400037ee  mov     rdx, rax
0x1400037f1  mov     rax, rdi
0x1400037f4  mov     rcx, rsi
0x1400037f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037fc  mov     rcx, rbx; bstrString
0x1400037ff  mov     edi, eax
0x140003801  call    cs:__imp_SysFreeString
0x140003807  mov     rcx, qword ptr [rbp+3Fh+ClassName]
0x14000380b  test    rcx, rcx
0x14000380e  jz      short loc_14000381C
0x140003810  mov     rax, [rcx]
0x140003813  mov     rax, [rax+10h]
0x140003817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000381c  mov     rcx, [rbp+3Fh+var_88]
0x140003820  test    rcx, rcx
0x140003823  jz      short loc_140003831
0x140003825  mov     rax, [rcx]
0x140003828  mov     rax, [rax+10h]
0x14000382c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003831  mov     rcx, [rbp+3Fh+var_80]
0x140003835  jmp     loc_14000392F
0x14000383a  mov     rax, [r15]
0x14000383d  lea     r8, [rbp+3Fh+var_88]
0x140003841  lea     rdx, IID_IWebBrowser2
0x140003848  mov     [rbp+3Fh+var_88], r12
0x14000384c  mov     rcx, r15
0x14000384f  mov     rax, [rax]
0x140003852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003857  cmp     [rbp+3Fh+var_88], r12
0x14000385b  jz      loc_140003940
0x140003861  xorps   xmm0, xmm0
0x140003864  mov     [rbp+3Fh+ClassName], r12w
0x140003869  xor     eax, eax
0x14000386b  lea     rcx, [rbp+3Fh+ClassName]; pvarg
0x14000386f  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x140003873  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x140003877  call    cs:__imp_VariantClear
0x14000387d  mov     edx, dword ptr [rbp+3Fh+var_58]
0x140003880  mov     rcx, rbx; psz
0x140003883  test    eax, eax
0x140003885  mov     [rbp+3Fh+ClassName], si
0x140003889  cmovs   edx, eax
0x14000388c  mov     dword ptr [rbp+3Fh+var_58], edx
0x14000388f  call    cs:__imp_SysAllocString
0x140003895  mov     rcx, rax
0x140003898  mov     dword ptr [rbp+3Fh+var_58], eax
0x14000389b  sar     rcx, 20h
0x14000389f  mov     dword ptr [rbp+3Fh+var_58+4], ecx
0x1400038a2  test    rax, rax
0x1400038a5  jnz     short loc_1400038B7
0x1400038a7  mov     eax, 0Ah
0x1400038ac  mov     dword ptr [rbp+3Fh+var_58], 8007000Eh
0x1400038b3  mov     [rbp+3Fh+ClassName], ax
0x1400038b7  mov     rcx, [rbp+3Fh+var_88]
0x1400038bb  or      edx, 0FFFFFFFFh
0x1400038be  mov     rax, [rcx]
0x1400038c1  mov     rax, [rax+148h]
0x1400038c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038cd  mov     rcx, [rbp+3Fh+var_88]
0x1400038d1  lea     rdx, [rbp+3Fh+pvarg]
0x1400038d5  mov     qword ptr [rsp+0D0h+cy], rdx
0x1400038da  lea     r9, [rbp+3Fh+pvarg]
0x1400038de  lea     rdx, [rbp+3Fh+pvarg]
0x1400038e2  mov     qword ptr [rsp+0D0h+var_B0], rdx
0x1400038e7  lea     r8, [rbp+3Fh+pvarg]
0x1400038eb  mov     rax, [rcx]
0x1400038ee  lea     rdx, [rbp+3Fh+ClassName]
0x1400038f2  mov     rax, [rax+1A0h]
0x1400038f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038fe  mov     ebx, 0FFFh
0x140003903  cmp     [rbp+3Fh+ClassName], bx
0x140003907  jnz     short loc_14000390D
0x140003909  mov     [rbp+3Fh+ClassName], si
0x14000390d  lea     rcx, [rbp+3Fh+ClassName]; pvarg
  ... truncated ...
```
