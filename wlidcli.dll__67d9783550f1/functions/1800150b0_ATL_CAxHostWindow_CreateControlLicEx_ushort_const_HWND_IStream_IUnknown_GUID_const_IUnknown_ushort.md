# ATL::CAxHostWindow::CreateControlLicEx(ushort const *,HWND__ *,IStream *,IUnknown * *,_GUID const &,IUnknown *,ushort *)

- ea: `0x1800150b0`
- end: `0x180015560`
- name: `?CreateControlLicEx@CAxHostWindow@ATL@@UEAAJPEBGPEAUHWND__@@PEAUIStream@@PEAPEAUIUnknown@@AEBU_GUID@@PEAU5@PEAG@Z`
- size: `1200`
- prototype: `int(ATL::CAxHostWindow *__hidden this, const unsigned __int16 *, HWND, struct IStream *, struct IUnknown **, const struct _GUID *, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180002da0`
- `0x18000a1a8`
- `0x18000ac9c`
- `0x18000ade0`
- `0x18000bea0`
- `0x1800131e4`
- `0x180013638`
- `0x1800139ec`
- `0x1800140bc`
- `0x1800150b0`
- `0x18001585c`
- `0x180018ec0`
- `0x18001916c`
- `0x180019a38`
- `0x180063010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180015463`
- `OLEAUT32!__imp_SysAllocString` at `0x180015463`
- `OLEAUT32!__imp_VariantInit` at `0x180015442`
- `OLEAUT32!__imp_VariantInit` at `0x180015442`
- `OLEAUT32!__imp_VariantClear` at `0x180015451`
- `OLEAUT32!__imp_VariantClear` at `0x1800154df`
- `OLEAUT32!__imp_VariantClear` at `0x1800154e9`
- `OLEAUT32!__imp_VariantClear` at `0x180015451`
- `OLEAUT32!__imp_VariantClear` at `0x1800154df`
- `OLEAUT32!__imp_VariantClear` at `0x1800154e9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180015362`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180015362`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800153af`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800153af`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001537b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001537b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001539d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001539d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800151bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800151bd`
- `USER32!IsWindow` at `0x180015148`
- `USER32!IsWindow` at `0x180015148`
- `USER32!GetClassNameW` at `0x1800151a8`
- `USER32!GetClassNameW` at `0x1800151a8`
- `USER32!GetSysColor` at `0x1800151d1`
- `USER32!GetSysColor` at `0x1800151d1`
- `USER32!SetWindowPos` at `0x1800152c2`
- `USER32!SetWindowPos` at `0x1800152c2`
- `USER32!RedrawWindow` at `0x180015137`
- `USER32!RedrawWindow` at `0x180015527`
- `USER32!RedrawWindow` at `0x180015137`
- `USER32!RedrawWindow` at `0x180015527`
- `USER32!GetParent` at `0x180015195`
- `USER32!GetParent` at `0x180015195`
- `USER32!SetWindowLongW` at `0x18001529e`
- `USER32!SetWindowLongW` at `0x18001529e`
- `USER32!GetWindowLongW` at `0x180015268`
- `USER32!GetWindowLongW` at `0x180015287`
- `USER32!GetWindowLongW` at `0x180015268`
- `USER32!GetWindowLongW` at `0x180015287`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::CreateControlLicEx(
        ATL::CAxHostWindow *this,
        unsigned __int16 *a2,
        HWND a3,
        struct IStream *a4,
        struct IUnknown **a5,
        const struct _GUID *a6,
        struct IUnknown *a7,
        unsigned __int16 *a8)
{
  ATL::CAxHostWindow *v12; // r13
  int NormalizedObject; // ebx
  HWND v14; // rcx
  __int64 v15; // rdx
  char v16; // al
  char v17; // r15
  HWND Parent; // rax
  int v19; // eax
  int v20; // ecx
  LONG WindowLongW; // eax
  SIZE_T v22; // r14
  HGLOBAL v23; // rax
  void *v24; // rbx
  void *v25; // rax
  errno_t v26; // eax
  HWND v27; // rcx
  _BYTE v28[8]; // [rsp+40h] [rbp-61h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-59h] BYREF
  BSTR pbstr; // [rsp+50h] [rbp-51h] BYREF
  VARIANTARG v31; // [rsp+58h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp-31h] BYREF
  WCHAR ClassName[4]; // [rsp+88h] [rbp-19h] BYREF

  ppstm = a4;
  pbstr = a8;
  if ( !a5 )
    return 2147500035LL;
  v12 = (ATL::CAxHostWindow *)((char *)this - 72);
  *a5 = 0;
  NormalizedObject = 1;
  ATL::CAxHostWindow::ReleaseAll((ATL::CAxHostWindow *)((char *)this - 72));
  v14 = (HWND)*((_QWORD *)this - 8);
  if ( v14 && v14 != a3 )
  {
    RedrawWindow(v14, 0, 0, 0x507u);
    ATL::CAxHostWindow::ReleaseWindow(v12);
  }
  if ( IsWindow(a3) )
  {
    if ( *((HWND *)this - 8) == a3 )
    {
      v17 = 0;
    }
    else
    {
      v16 = ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::SubclassWindow((size_t)v12, a3);
      v17 = 1;
      *((_DWORD *)v12 + 84) ^= ((unsigned __int8)*((_DWORD *)v12 + 84) ^ (unsigned __int8)(16 * v16)) & 0x10;
    }
    if ( !*((_DWORD *)this + 67) )
    {
      Parent = GetParent(*((HWND *)this - 8));
      if ( !GetClassNameW(Parent, ClassName, 8) || (v19 = lstrcmpW(ClassName, L"#32770"), v20 = 15, v19) )
        v20 = 5;
      *((_DWORD *)this + 67) = GetSysColor(v20);
    }
    v28[0] = 0;
    NormalizedObject = ATL::CreateNormalizedObject(a2, v15, (LPVOID *)a5, v28, pbstr);
    if ( NormalizedObject >= 0 )
      NormalizedObject = ATL::CAxHostWindow::ActivateAx(v12, *a5, 0, ppstm);
    *(struct _GUID *)((char *)this + 184) = *a6;
    if ( NormalizedObject < 0 )
      goto LABEL_47;
    if ( *a5 && a7 )
      ATL::AtlAdvise(*a5, a7, (const struct _GUID *)((char *)this + 184), (unsigned int *)this + 51);
    if ( v28[0] && *a5 )
    {
      if ( (GetWindowLongW(*((HWND *)this - 8), -16) & 0x300000) != 0 )
      {
        WindowLongW = GetWindowLongW(*((HWND *)this - 8), -16);
        SetWindowLongW(*((HWND *)this - 8), -16, WindowLongW & 0xFFCFFFFF);
        SetWindowPos(*((HWND *)this - 8), 0, 0, 0, 0, 0, 0x37u);
      }
      else
      {
        *((_DWORD *)this + 74) |= 8u;
      }
      ATL::CComPtrBase<IUnknown>::CComPtrBase<IUnknown>(&pbstr, (__int64)*a5);
      if ( ((*a2 - 77) & 0xFFDF) != 0
        || ((a2[1] - 83) & 0xFFDF) != 0
        || ((a2[2] - 72) & 0xFFDF) != 0
        || ((a2[3] - 84) & 0xFFDF) != 0
        || ((a2[4] - 77) & 0xFFDF) != 0
        || ((a2[5] - 76) & 0xFFDF) != 0
        || a2[6] != 58 )
      {
        *(_QWORD *)ClassName = 0;
        (**(void (__fastcall ***)(BSTR, GUID *, WCHAR *))pbstr)(
          pbstr,
          &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
          ClassName);
        if ( *(_QWORD *)ClassName )
        {
          VariantInit(&pvarg);
          v31.vt = 0;
          VariantClear(&v31);
          v31.vt = 8;
          v31.llVal = (LONGLONG)SysAllocString(a2);
          if ( !v31.llVal )
          {
            v31.vt = 10;
            v31.lVal = -2147024882;
            ATL::AtlThrowImpl(-2147024882);
          }
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)ClassName + 328LL))(*(_QWORD *)ClassName, 0xFFFFFFFFLL);
          (*(void (__fastcall **)(_QWORD, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(**(_QWORD **)ClassName + 416LL))(
            *(_QWORD *)ClassName,
            &v31,
            &pvarg,
            &pvarg,
            &pvarg,
            &pvarg);
          VariantClear(&v31);
          VariantClear(&pvarg);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)ClassName);
      }
      else
      {
        v22 = 2 * (unsigned int)ocslen(a2) - 14;
        v23 = GlobalAlloc(0x42u, v22);
        v24 = v23;
        if ( v23 )
        {
          ppstm = 0;
          v25 = GlobalLock(v23);
          v26 = memcpy_s_0(v25, (unsigned int)v22, a2 + 7, (unsigned int)v22);
          ATL::AtlCrtErrorCheck(v26);
          GlobalUnlock(v24);
          NormalizedObject = CreateStreamOnHGlobal(v24, 1, &ppstm);
          if ( NormalizedObject >= 0 )
          {
            *(_QWORD *)ClassName = 0;
            NormalizedObject = (**(__int64 (__fastcall ***)(BSTR, GUID *, WCHAR *))pbstr)(
                                 pbstr,
                                 &GUID_7fd52380_4e07_101b_ae2d_08002b2ec713,
                                 ClassName);
            if ( NormalizedObject >= 0 )
              NormalizedObject = (*(__int64 (__fastcall **)(_QWORD, LPSTREAM))(**(_QWORD **)ClassName + 40LL))(
                                   *(_QWORD *)ClassName,
                                   ppstm);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)ClassName);
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppstm);
        }
        else
        {
          NormalizedObject = -2147024882;
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&pbstr);
      if ( NormalizedObject < 0 )
        goto LABEL_47;
    }
    if ( !*((_QWORD *)this + 15) )
    {
LABEL_47:
      ATL::CAxHostWindow::ReleaseAll(v12);
      v27 = (HWND)*((_QWORD *)this - 8);
      if ( v27 )
      {
        RedrawWindow(v27, 0, 0, 0x507u);
        if ( NormalizedObject < 0 )
        {
          if ( v17 )
            ATL::CAxHostWindow::ReleaseWindow(v12);
        }
      }
    }
  }
  return (unsigned int)NormalizedObject;
}

```

## disassembly

```asm
0x1800150b0  push    rbp
0x1800150b2  push    rbx
0x1800150b3  push    rsi
0x1800150b4  push    rdi
0x1800150b5  push    r12
0x1800150b7  push    r13
0x1800150b9  push    r14
0x1800150bb  push    r15
0x1800150bd  lea     rbp, [rsp-7]
0x1800150c2  sub     rsp, 0A8h
0x1800150c9  mov     rax, cs:__security_cookie
0x1800150d0  xor     rax, rsp
0x1800150d3  mov     [rbp+3Fh+var_48], rax
0x1800150d7  mov     r14, [rbp+3Fh+arg_20]
0x1800150db  mov     r15, r8
0x1800150de  mov     rax, [rbp+3Fh+arg_38]
0x1800150e5  mov     rsi, rdx
0x1800150e8  mov     r12, [rbp+3Fh+arg_30]
0x1800150ec  mov     rdi, rcx
0x1800150ef  mov     [rbp+3Fh+ppstm], r9
0x1800150f3  mov     [rbp+3Fh+var_90], rax
0x1800150f7  test    r14, r14
0x1800150fa  jnz     short loc_180015106
0x1800150fc  mov     eax, 80004003h
0x180015101  jmp     loc_180015540
0x180015106  lea     r13, [rcx-48h]
0x18001510a  mov     qword ptr [r14], 0
0x180015111  mov     rcx, r13; this
0x180015114  mov     ebx, 1
0x180015119  call    ?ReleaseAll@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseAll(void)
0x18001511e  mov     rcx, [rdi-40h]; hWnd
0x180015122  test    rcx, rcx
0x180015125  jz      short loc_180015145
0x180015127  cmp     rcx, r15
0x18001512a  jz      short loc_180015145
0x18001512c  mov     r9d, 507h; flags
0x180015132  xor     r8d, r8d; hrgnUpdate
0x180015135  xor     edx, edx; lprcUpdate
0x180015137  call    cs:__imp_RedrawWindow
0x18001513d  mov     rcx, r13; this
0x180015140  call    ?ReleaseWindow@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseWindow(void)
0x180015145  mov     rcx, r15; hWnd
0x180015148  call    cs:__imp_IsWindow
0x18001514e  test    eax, eax
0x180015150  jz      loc_18001553E
0x180015156  xor     ebx, ebx
0x180015158  cmp     [rdi-40h], r15
0x18001515c  jz      short loc_180015186
0x18001515e  mov     rdx, r15; hWnd
0x180015161  mov     rcx, r13; FirstParameter
0x180015164  call    ?SubclassWindow@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@ATL@@QEAAHPEAUHWND__@@@Z; ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1442840576,0>>::SubclassWindow(HWND__ *)
0x180015169  mov     ecx, [r13+150h]
0x180015170  mov     r15b, 1
0x180015173  shl     eax, 4
0x180015176  xor     eax, ecx
0x180015178  and     eax, 10h
0x18001517b  xor     eax, ecx
0x18001517d  mov     [r13+150h], eax
0x180015184  jmp     short loc_180015189
0x180015186  mov     r15b, bl
0x180015189  cmp     [rdi+10Ch], ebx
0x18001518f  jnz     short loc_1800151DD
0x180015191  mov     rcx, [rdi-40h]; hWnd
0x180015195  call    cs:__imp_GetParent
0x18001519b  mov     r8d, 8; nMaxCount
0x1800151a1  lea     rdx, [rbp+3Fh+ClassName]; lpClassName
0x1800151a5  mov     rcx, rax; hWnd
0x1800151a8  call    cs:__imp_GetClassNameW
0x1800151ae  test    eax, eax
0x1800151b0  jz      short loc_1800151CC
0x1800151b2  lea     rdx, String2; "#32770"
0x1800151b9  lea     rcx, [rbp+3Fh+ClassName]; lpString1
0x1800151bd  call    cs:__imp_lstrcmpW
0x1800151c3  mov     ecx, 0Fh
0x1800151c8  test    eax, eax
0x1800151ca  jz      short loc_1800151D1
0x1800151cc  mov     ecx, 5; nIndex
0x1800151d1  call    cs:__imp_GetSysColor
0x1800151d7  mov     [rdi+10Ch], eax
0x1800151dd  mov     rax, [rbp+3Fh+var_90]
0x1800151e1  lea     r9, [rbp+3Fh+var_A0]
0x1800151e5  mov     r8, r14
0x1800151e8  mov     [rsp+0E0h+pbstr], rax; pbstr
0x1800151ed  mov     rcx, rsi; unsigned __int16 *
0x1800151f0  mov     [rbp+3Fh+var_A0], bl
0x1800151f3  call    ATL__CreateNormalizedObject
0x1800151f8  mov     ebx, eax
0x1800151fa  test    eax, eax
0x1800151fc  js      short loc_180015212
0x1800151fe  mov     r9, [rbp+3Fh+ppstm]; struct IStream *
0x180015202  xor     r8d, r8d; bool
0x180015205  mov     rdx, [r14]; struct IUnknown *
0x180015208  mov     rcx, r13; this
0x18001520b  call    ?ActivateAx@CAxHostWindow@ATL@@QEAAJPEAUIUnknown@@_NPEAUIStream@@@Z; ATL::CAxHostWindow::ActivateAx(IUnknown *,bool,IStream *)
0x180015210  mov     ebx, eax
0x180015212  mov     rax, [rbp+3Fh+arg_28]
0x180015216  lea     r8, [rdi+0B8h]; struct _GUID *
0x18001521d  movups  xmm0, xmmword ptr [rax]
0x180015220  movdqu  xmmword ptr [r8], xmm0
0x180015225  test    ebx, ebx
0x180015227  js      loc_18001550B
0x18001522d  mov     rcx, [r14]; struct IUnknown *
0x180015230  test    rcx, rcx
0x180015233  jz      short loc_180015249
0x180015235  test    r12, r12
0x180015238  jz      short loc_180015249
0x18001523a  lea     r9, [rdi+0CCh]; unsigned int *
0x180015241  mov     rdx, r12; struct IUnknown *
0x180015244  call    ?AtlAdvise@ATL@@YAJPEAUIUnknown@@0AEBU_GUID@@PEAK@Z; ATL::AtlAdvise(IUnknown *,IUnknown *,_GUID const &,ulong *)
0x180015249  xor     r12d, r12d
0x18001524c  cmp     [rbp+3Fh+var_A0], r12b
0x180015250  jz      loc_180015505
0x180015256  cmp     [r14], r12
0x180015259  jz      loc_180015505
0x18001525f  mov     rcx, [rdi-40h]; hWnd
0x180015263  lea     edx, [r12-10h]; nIndex
0x180015268  call    cs:__imp_GetWindowLongW
0x18001526e  test    eax, 300000h
0x180015273  jnz     short loc_18001527E
0x180015275  or      dword ptr [rdi+128h], 8
0x18001527c  jmp     short loc_1800152C8
0x18001527e  mov     rcx, [rdi-40h]; hWnd
0x180015282  mov     edx, 0FFFFFFF0h; nIndex
0x180015287  call    cs:__imp_GetWindowLongW
0x18001528d  mov     rcx, [rdi-40h]; hWnd
0x180015291  mov     edx, 0FFFFFFF0h; nIndex
0x180015296  and     eax, 0FFCFFFFFh
0x18001529b  mov     r8d, eax; dwNewLong
0x18001529e  call    cs:__imp_SetWindowLongW
0x1800152a4  mov     rcx, [rdi-40h]; hWnd
0x1800152a8  xor     r9d, r9d; Y
0x1800152ab  mov     [rsp+0E0h+uFlags], 37h ; '7'; uFlags
0x1800152b3  xor     r8d, r8d; X
0x1800152b6  mov     [rsp+0E0h+cy], r12d; cy
0x1800152bb  xor     edx, edx; hWndInsertAfter
0x1800152bd  mov     dword ptr [rsp+0E0h+pbstr], r12d; cx
0x1800152c2  call    cs:__imp_SetWindowPos
0x1800152c8  mov     rdx, [r14]
0x1800152cb  lea     rcx, [rbp+3Fh+var_90]
0x1800152cf  call    ??0?$CComPtrBase@UIUnknown@@@ATL@@IEAA@PEAUIUnknown@@@Z; ATL::CComPtrBase<IUnknown>::CComPtrBase<IUnknown>(IUnknown *)
0x1800152d4  movzx   eax, word ptr [rsi]
0x1800152d7  mov     ecx, 0FFDFh
0x1800152dc  sub     ax, 4Dh ; 'M'
0x1800152e0  test    cx, ax
0x1800152e3  jnz     loc_180015416
0x1800152e9  movzx   eax, word ptr [rsi+2]
0x1800152ed  sub     ax, 53h ; 'S'
0x1800152f1  test    cx, ax
0x1800152f4  jnz     loc_180015416
0x1800152fa  movzx   eax, word ptr [rsi+4]
0x1800152fe  sub     ax, 48h ; 'H'
0x180015302  test    cx, ax
0x180015305  jnz     loc_180015416
0x18001530b  movzx   eax, word ptr [rsi+6]
0x18001530f  sub     ax, 54h ; 'T'
0x180015313  test    cx, ax
0x180015316  jnz     loc_180015416
0x18001531c  movzx   eax, word ptr [rsi+8]
0x180015320  sub     ax, 4Dh ; 'M'
0x180015324  test    cx, ax
0x180015327  jnz     loc_180015416
0x18001532d  movzx   eax, word ptr [rsi+0Ah]
0x180015331  sub     ax, 4Ch ; 'L'
0x180015335  test    cx, ax
0x180015338  jnz     loc_180015416
0x18001533e  cmp     word ptr [rsi+0Ch], 3Ah ; ':'
0x180015343  jnz     loc_180015416
0x180015349  mov     rcx, rsi; unsigned __int16 *
0x18001534c  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x180015351  mov     ecx, 42h ; 'B'; uFlags
0x180015356  lea     eax, ds:0FFFFFFFFFFFFFFF2h[rax*2]
0x18001535d  mov     edx, eax; dwBytes
0x18001535f  mov     r14d, eax
0x180015362  call    cs:__imp_GlobalAlloc
0x180015368  mov     rbx, rax
0x18001536b  test    rax, rax
0x18001536e  jz      loc_18001540C
0x180015374  mov     rcx, rax; hMem
0x180015377  mov     [rbp+3Fh+ppstm], r12
0x18001537b  call    cs:__imp_GlobalLock
0x180015381  lea     r8, [rsi+0Eh]; Source
0x180015385  mov     r9d, r14d; SourceSize
0x180015388  mov     rcx, rax; Destination
0x18001538b  mov     edx, r14d; DestinationSize
0x18001538e  call    memcpy_s_0
0x180015393  mov     ecx, eax; int
0x180015395  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001539a  mov     rcx, rbx; hMem
0x18001539d  call    cs:__imp_GlobalUnlock
0x1800153a3  lea     r8, [rbp+3Fh+ppstm]; ppstm
0x1800153a7  mov     edx, 1; fDeleteOnRelease
0x1800153ac  mov     rcx, rbx; hGlobal
0x1800153af  call    cs:__imp_CreateStreamOnHGlobal
0x1800153b5  mov     ebx, eax
0x1800153b7  test    eax, eax
0x1800153b9  js      short loc_1800153FE
0x1800153bb  mov     rcx, [rbp+3Fh+var_90]
0x1800153bf  lea     r8, [rbp+3Fh+ClassName]
0x1800153c3  mov     qword ptr [rbp+3Fh+ClassName], r12
0x1800153c7  lea     rdx, _GUID_7fd52380_4e07_101b_ae2d_08002b2ec713
0x1800153ce  mov     rax, [rcx]
0x1800153d1  mov     rax, [rax]
0x1800153d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153d9  mov     ebx, eax
0x1800153db  test    eax, eax
0x1800153dd  js      short loc_1800153F5
0x1800153df  mov     rcx, qword ptr [rbp+3Fh+ClassName]
0x1800153e3  mov     rdx, [rbp+3Fh+ppstm]
0x1800153e7  mov     rax, [rcx]
0x1800153ea  mov     rax, [rax+28h]
0x1800153ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153f3  mov     ebx, eax
0x1800153f5  lea     rcx, [rbp+3Fh+ClassName]
0x1800153f9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800153fe  lea     rcx, [rbp+3Fh+ppstm]
0x180015402  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015407  jmp     loc_1800154F8
0x18001540c  mov     ebx, 8007000Eh
0x180015411  jmp     loc_1800154F8
0x180015416  mov     rcx, [rbp+3Fh+var_90]
0x18001541a  lea     r8, [rbp+3Fh+ClassName]
0x18001541e  mov     qword ptr [rbp+3Fh+ClassName], r12
0x180015422  lea     rdx, _GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e
0x180015429  mov     rax, [rcx]
0x18001542c  mov     rax, [rax]
0x18001542f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015434  cmp     qword ptr [rbp+3Fh+ClassName], r12
0x180015438  jz      loc_1800154EF
0x18001543e  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x180015442  call    cs:__imp_VariantInit
0x180015448  lea     rcx, [rbp+3Fh+var_88]; pvarg
0x18001544c  mov     word ptr [rbp+3Fh+var_88], r12w
0x180015451  call    cs:__imp_VariantClear
0x180015457  mov     eax, 8
0x18001545c  mov     rcx, rsi; psz
0x18001545f  mov     word ptr [rbp+3Fh+var_88], ax
0x180015463  call    cs:__imp_SysAllocString
0x180015469  mov     rcx, rax
0x18001546c  mov     dword ptr [rbp+3Fh+var_88+8], eax
0x18001546f  sar     rcx, 20h
0x180015473  mov     dword ptr [rbp+3Fh+var_88+0Ch], ecx
0x180015476  test    rax, rax
0x180015479  jnz     short loc_180015494
0x18001547b  mov     ebx, 8007000Eh
0x180015480  mov     eax, 0Ah
0x180015485  mov     ecx, ebx; int
0x180015487  mov     word ptr [rbp+3Fh+var_88], ax
0x18001548b  mov     dword ptr [rbp+3Fh+var_88+8], ebx
0x18001548e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180015494  mov     rcx, qword ptr [rbp+3Fh+ClassName]
0x180015498  or      edx, 0FFFFFFFFh
0x18001549b  mov     rax, [rcx]
0x18001549e  mov     rax, [rax+148h]
0x1800154a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154aa  mov     rcx, qword ptr [rbp+3Fh+ClassName]
0x1800154ae  lea     rdx, [rbp+3Fh+pvarg]
0x1800154b2  mov     qword ptr [rsp+0E0h+cy], rdx
0x1800154b7  lea     r9, [rbp+3Fh+pvarg]
0x1800154bb  lea     rdx, [rbp+3Fh+pvarg]
0x1800154bf  mov     [rsp+0E0h+pbstr], rdx
0x1800154c4  lea     r8, [rbp+3Fh+pvarg]
0x1800154c8  mov     rax, [rcx]
0x1800154cb  lea     rdx, [rbp+3Fh+var_88]
0x1800154cf  mov     rax, [rax+1A0h]
0x1800154d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154db  lea     rcx, [rbp+3Fh+var_88]; pvarg
0x1800154df  call    cs:__imp_VariantClear
0x1800154e5  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x1800154e9  call    cs:__imp_VariantClear
0x1800154ef  lea     rcx, [rbp+3Fh+ClassName]
0x1800154f3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800154f8  lea     rcx, [rbp+3Fh+var_90]
0x1800154fc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015501  test    ebx, ebx
0x180015503  js      short loc_18001550B
0x180015505  cmp     [rdi+78h], r12
0x180015509  jnz     short loc_18001553E
0x18001550b  mov     rcx, r13; this
0x18001550e  call    ?ReleaseAll@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseAll(void)
0x180015513  mov     rcx, [rdi-40h]; hWnd
0x180015517  test    rcx, rcx
0x18001551a  jz      short loc_18001553E
0x18001551c  mov     r9d, 507h; flags
0x180015522  xor     r8d, r8d; hrgnUpdate
0x180015525  xor     edx, edx; lprcUpdate
0x180015527  call    cs:__imp_RedrawWindow
0x18001552d  test    ebx, ebx
0x18001552f  jns     short loc_18001553E
0x180015531  test    r15b, r15b
0x180015534  jz      short loc_18001553E
0x180015536  mov     rcx, r13; this
0x180015539  call    ?ReleaseWindow@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseWindow(void)
0x18001553e  mov     eax, ebx
0x180015540  mov     rcx, [rbp+3Fh+var_48]
0x180015544  xor     rcx, rsp; StackCookie
0x180015547  call    __security_check_cookie
0x18001554c  add     rsp, 0A8h
0x180015553  pop     r15
0x180015555  pop     r14
0x180015557  pop     r13
  ... truncated ...
```
