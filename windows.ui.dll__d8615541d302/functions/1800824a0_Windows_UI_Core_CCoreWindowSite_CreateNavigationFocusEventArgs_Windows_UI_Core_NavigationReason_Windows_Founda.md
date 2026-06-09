# Windows::UI::Core::CCoreWindowSite::CreateNavigationFocusEventArgs(Windows::UI::Core::NavigationReason,Windows::Foundation::Rect,Windows::UI::Core::INavigationFocusEventArgs * *)

- ea: `0x1800824a0`
- end: `0x180082869`
- name: `?CreateNavigationFocusEventArgs@CCoreWindowSite@Core@UI@Windows@@UEAAJW4NavigationReason@234@URect@Foundation@4@PEAPEAUINavigationFocusEventArgs@234@@Z`
- size: `969`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x1800038e0`
- `0x18000f048`
- `0x180014754`
- `0x18001edd0`
- `0x1800390a8`
- `0x18003c374`
- `0x180044a44`
- `0x18005187c`
- `0x1800543b4`
- `0x1800723c8`
- `0x180072b2c`
- `0x18007fa64`
- `0x1800824a0`
- `0x1800877dc`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180082629`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180082629`

## string_xrefs

- `0x180082511`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180082560`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180082667`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x1800826aa`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x180082796`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x1800827f2`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\site.cpp`
- `0x1800824c7`: `CoreWindowSite::CreateNavigationFocusEventArgs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::CCoreWindowSite::CreateNavigationFocusEventArgs(
        __int64 a1,
        unsigned int a2,
        __int128 *a3,
        __int64 a4)
{
  int ComponentViewInstanceId; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  __int64 v16; // rdx
  __m128i v17; // xmm6
  __int64 v18; // rbx
  int v19; // eax
  unsigned int v20; // edi
  int v21; // eax
  int v23; // [rsp+20h] [rbp-E0h]
  unsigned int v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v27; // [rsp+40h] [rbp-C0h] BYREF
  struct Windows::UI::Core::ICoreWindow *v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  HWND v30; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v33[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v34[2]; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A4h] [rbp-5Ch]
  __int64 v37; // [rsp+ACh] [rbp-54h]
  int v38; // [rsp+B4h] [rbp-4Ch]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  int v40; // [rsp+C0h] [rbp-40h]
  __int64 v41; // [rsp+C4h] [rbp-3Ch]
  int v42; // [rsp+CCh] [rbp-34h]
  char v43; // [rsp+D0h] [rbp-30h]
  char v44; // [rsp+D4h] [rbp-2Ch]
  __m128i v45; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v46[80]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  CUITelemetry::WatchCurrentThread(v46, "CoreWindowSite::CreateNavigationFocusEventArgs");
  v27 = 0;
  ComponentViewInstanceId = Windows::UI::Core::CCoreWindowSite::get_ComponentViewInstanceId(
                              (Windows::UI::Core::CCoreWindowSite *)(a1 - 32),
                              &v27);
  v9 = ComponentViewInstanceId;
  if ( ComponentViewInstanceId < 0 )
  {
    v10 = (unsigned int)ComponentViewInstanceId;
    v11 = 1865;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)v10,
      v23);
    goto LABEL_39;
  }
  if ( !v27 )
  {
    v9 = -2147418113;
    v10 = 2147549183LL;
    v11 = 1869;
    goto LABEL_5;
  }
  v30 = 0;
  v26 = 0;
  v25 = 0;
  v12 = Microsoft::WRL::WeakRef::As<Windows::Foundation::Private::IComponentSite>(a1 + 80, &v25);
  v9 = v12;
  if ( v12 < 0 )
  {
    v13 = 1876;
LABEL_8:
    v14 = (unsigned int)v12;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)v14,
      v23);
LABEL_10:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v26);
    goto LABEL_39;
  }
  if ( !v25 )
  {
    v9 = -2147418113;
    v14 = 2147549183LL;
    v13 = 1877;
    goto LABEL_9;
  }
  v12 = Microsoft::WRL::ComPtr<Windows::Foundation::Private::IComponentSite>::As<IComponentSitePrivate>(&v25, &v26);
  v9 = v12;
  if ( v12 < 0 )
  {
    v13 = 1878;
    goto LABEL_8;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v26 + 56LL))(v26, &v30);
  v9 = v12;
  if ( v12 < 0 )
  {
    v13 = 1879;
    goto LABEL_8;
  }
  v33[0] = 0;
  v33[1] = 0;
  v43 = 0;
  v42 = 1065353216;
  v39 = 1065353216;
  v36 = 1065353216;
  v34[0] = 1065353216;
  v34[1] = 0;
  v37 = 0;
  v35 = 0;
  v38 = 0;
  v41 = 0;
  v40 = 0;
  v44 = 0;
  if ( (unsigned int)IsOneCoreTransformMode() )
  {
    v28 = 0;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
    if ( !(unsigned int)Windows::UI::Core::WindowServer::GetWindowForThread(&v28) )
    {
      v9 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75F,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)0x8000FFFFLL,
        v23);
LABEL_20:
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
      goto LABEL_10;
    }
    v29 = 0;
    v15 = Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::ICoordinateConversion>(
            &v28,
            &v29);
    v9 = v15;
    if ( v15 < 0 )
    {
      v16 = 1890;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
        (const char *)(unsigned int)v15,
        v23);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
      goto LABEL_20;
    }
    v31 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL))(v29, &v31);
    v9 = v15;
    if ( v15 < 0 )
    {
      v16 = 1893;
      goto LABEL_23;
    }
    v33[0] = v31;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v28);
  }
  else
  {
    v44 = 1;
    CInputTransform::LegacyTransforms_InferTransformFromWindow((__int64)v34, v30, 1);
  }
  v32 = *a3;
  v17 = _mm_loadu_si128((const __m128i *)CIslandTransform::VisualRectToScreen(v33, &v45, &v32));
  Microsoft::WRL::Details::Make<CNavigationFocusEventArgs,>(&v32);
  v18 = v32;
  v45 = v17;
  v24 = v27;
  v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __m128i *, HWND))(*(_QWORD *)v32 + 96LL))(v32, a2, &v45, v30);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x771,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)(unsigned int)v19,
      v24);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
LABEL_31:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v26);
    v9 = v20;
    goto LABEL_39;
  }
  v21 = Microsoft::WRL::ComPtr<CNavigationFocusEventArgs>::CopyTo<Windows::UI::Core::INavigationFocusEventArgs>(
          &v32,
          a4);
  v20 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x772,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\site.cpp",
      (const char *)(unsigned int)v21,
      v24);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    goto LABEL_31;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v26);
  v9 = 0;
LABEL_39:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v46);
  return v9;
}

```

## disassembly

```asm
0x1800824a0  mov     rax, rsp
0x1800824a3  push    rbp
0x1800824a4  push    rbx
0x1800824a5  push    rsi
0x1800824a6  push    rdi
0x1800824a7  push    r14
0x1800824a9  push    r15
0x1800824ab  lea     rbp, [rsp-58h]
0x1800824b0  sub     rsp, 158h
0x1800824b7  movaps  xmmword ptr [rax-48h], xmm6
0x1800824bb  mov     rsi, r9
0x1800824be  mov     r15, r8
0x1800824c1  mov     r14d, edx
0x1800824c4  mov     rdi, rcx
0x1800824c7  lea     rdx, aCorewindowsite_40; "CoreWindowSite::CreateNavigationFocusEv"...
0x1800824ce  lea     rcx, [rbp+80h+var_90]
0x1800824d2  call    ?WatchCurrentThread@CUITelemetry@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; CUITelemetry::WatchCurrentThread(char const *)
0x1800824d7  mov     [rsp+180h+var_140], 0
0x1800824df  lea     rcx, [rdi-20h]; this
0x1800824e3  lea     rdx, [rsp+180h+var_140]; unsigned int *
0x1800824e8  call    ?get_ComponentViewInstanceId@CCoreWindowSite@Core@UI@Windows@@AEAAJPEAI@Z; Windows::UI::Core::CCoreWindowSite::get_ComponentViewInstanceId(uint *)
0x1800824ed  mov     ebx, eax
0x1800824ef  test    eax, eax
0x1800824f1  jns     short loc_1800824FD
0x1800824f3  mov     r9d, eax
0x1800824f6  mov     edx, 749h
0x1800824fb  jmp     short loc_180082511
0x1800824fd  cmp     [rsp+180h+var_140], 0
0x180082502  jnz     short loc_180082529
0x180082504  mov     ebx, 8000FFFFh
0x180082509  mov     r9d, ebx; char *
0x18008250c  mov     edx, 74Dh; void *
0x180082511  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180082518  mov     rcx, [rbp+88h]; this
0x18008251f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082524  jmp     loc_180082846
0x180082529  mov     [rsp+180h+var_128], 0
0x180082532  mov     [rsp+180h+var_148], 0
0x18008253b  mov     [rsp+180h+var_150], 0
0x180082544  lea     rcx, [rdi+50h]
0x180082548  lea     rdx, [rsp+180h+var_150]
0x18008254d  call    ??$As@UIComponentSite@Private@Foundation@Windows@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIComponentSite@Private@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<Windows::Foundation::Private::IComponentSite>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Private::IComponentSite>>)
0x180082552  mov     ebx, eax
0x180082554  test    eax, eax
0x180082556  jns     short loc_18008258C
0x180082558  mov     edx, 754h; void *
0x18008255d  mov     r9d, eax; char *
0x180082560  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180082567  mov     rcx, [rbp+88h]; this
0x18008256e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082573  lea     rcx, [rsp+180h+var_150]
0x180082578  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008257d  lea     rcx, [rsp+180h+var_148]
0x180082582  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180082587  jmp     loc_180082846
0x18008258c  cmp     [rsp+180h+var_150], 0
0x180082592  jnz     short loc_1800825A3
0x180082594  mov     ebx, 8000FFFFh
0x180082599  mov     r9d, ebx
0x18008259c  mov     edx, 755h
0x1800825a1  jmp     short loc_180082560
0x1800825a3  lea     rdx, [rsp+180h+var_148]
0x1800825a8  lea     rcx, [rsp+180h+var_150]
0x1800825ad  call    ??$As@UIComponentSitePrivate@@@?$ComPtr@UIComponentSite@Private@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIComponentSitePrivate@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Private::IComponentSite>::As<IComponentSitePrivate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IComponentSitePrivate>>)
0x1800825b2  mov     ebx, eax
0x1800825b4  test    eax, eax
0x1800825b6  jns     short loc_1800825BF
0x1800825b8  mov     edx, 756h
0x1800825bd  jmp     short loc_18008255D
0x1800825bf  mov     rcx, [rsp+180h+var_148]
0x1800825c4  mov     rax, [rcx]
0x1800825c7  lea     rdx, [rsp+180h+var_128]
0x1800825cc  mov     rax, [rax+38h]
0x1800825d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800825d5  mov     ebx, eax
0x1800825d7  test    eax, eax
0x1800825d9  jns     short loc_1800825E5
0x1800825db  mov     edx, 757h
0x1800825e0  jmp     loc_18008255D
0x1800825e5  xor     eax, eax
0x1800825e7  mov     [rbp+80h+var_100], rax
0x1800825eb  mov     [rbp+80h+var_F8], rax
0x1800825ef  mov     [rbp+80h+var_B0], al
0x1800825f2  mov     [rbp+80h+var_B4], 3F800000h
0x1800825f9  mov     [rbp+80h+var_C8], 3F800000h
0x180082601  mov     [rbp+80h+var_DC], 3F800000h
0x180082609  mov     [rbp+80h+var_F0], 3F800000h
0x180082611  mov     [rbp+80h+var_E8], rax
0x180082615  mov     [rbp+80h+var_D4], rax
0x180082619  mov     [rbp+80h+var_E0], eax
0x18008261c  mov     [rbp+80h+var_CC], eax
0x18008261f  mov     [rbp+80h+var_BC], rax
0x180082623  mov     [rbp+80h+var_C0], eax
0x180082626  mov     [rbp+80h+var_AC], al
0x180082629  call    cs:__imp_IsOneCoreTransformMode
0x18008262f  test    eax, eax
0x180082631  jz      loc_180082717
0x180082637  mov     [rsp+180h+var_138], 0
0x180082640  lea     rcx, [rsp+180h+var_138]
0x180082645  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008264a  lea     rcx, [rsp+180h+var_138]; struct Windows::UI::Core::ICoreWindow **
0x18008264f  call    ?GetWindowForThread@WindowServer@Core@UI@Windows@@SAHPEAPEAUICoreWindow@234@@Z; Windows::UI::Core::WindowServer::GetWindowForThread(Windows::UI::Core::ICoreWindow * *)
0x180082654  test    eax, eax
0x180082656  jnz     short loc_180082687
0x180082658  mov     rcx, [rbp+88h]; this
0x18008265f  mov     ebx, 8000FFFFh
0x180082664  mov     r9d, ebx; char *
0x180082667  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18008266e  mov     edx, 75Fh; void *
0x180082673  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082678  lea     rcx, [rsp+180h+var_138]
0x18008267d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180082682  jmp     loc_180082573
0x180082687  mov     [rsp+180h+var_130], 0
0x180082690  lea     rdx, [rsp+180h+var_130]
0x180082695  lea     rcx, [rsp+180h+var_138]
0x18008269a  call    ??$As@UICoordinateConversion@Core@UI@Windows@@@?$ComPtr@UICoreWindow@Core@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UICoordinateConversion@Core@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Core::ICoreWindow>::As<Windows::UI::Core::ICoordinateConversion>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Core::ICoordinateConversion>>)
0x18008269f  mov     ebx, eax
0x1800826a1  test    eax, eax
0x1800826a3  jns     short loc_1800826CC
0x1800826a5  mov     edx, 762h; void *
0x1800826aa  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800826b1  mov     r9d, eax; char *
0x1800826b4  mov     rcx, [rbp+88h]; this
0x1800826bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800826c0  lea     rcx, [rsp+180h+var_130]
0x1800826c5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800826ca  jmp     short loc_180082678
0x1800826cc  mov     [rsp+180h+var_120], 0
0x1800826d5  mov     rcx, [rsp+180h+var_130]
0x1800826da  mov     rax, [rcx]
0x1800826dd  lea     rdx, [rsp+180h+var_120]
0x1800826e2  mov     rax, [rax+30h]
0x1800826e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800826eb  mov     ebx, eax
0x1800826ed  test    eax, eax
0x1800826ef  jns     short loc_1800826F8
0x1800826f1  mov     edx, 765h
0x1800826f6  jmp     short loc_1800826AA
0x1800826f8  mov     rax, [rsp+180h+var_120]
0x1800826fd  mov     [rbp+80h+var_100], rax
0x180082701  lea     rcx, [rsp+180h+var_130]
0x180082706  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008270b  lea     rcx, [rsp+180h+var_138]
0x180082710  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180082715  jmp     short loc_18008272F
0x180082717  mov     [rbp+80h+var_AC], 1
0x18008271b  mov     r8d, 1
0x180082721  mov     rdx, [rsp+180h+var_128]
0x180082726  lea     rcx, [rbp+80h+var_F0]
0x18008272a  call    ?LegacyTransforms_InferTransformFromWindow@CInputTransform@@QEAAXPEAUHWND__@@W4Inference@1@@Z; CInputTransform::LegacyTransforms_InferTransformFromWindow(HWND__ *,CInputTransform::Inference)
0x18008272f  movups  xmm0, xmmword ptr [r15]
0x180082733  movdqu  [rsp+180h+var_110], xmm0
0x180082739  lea     r8, [rsp+180h+var_110]
0x18008273e  lea     rdx, [rbp+80h+var_A0]
0x180082742  lea     rcx, [rbp+80h+var_100]
0x180082746  call    ?VisualRectToScreen@CIslandTransform@@QEAA?AURect@Foundation@Windows@@U234@@Z; CIslandTransform::VisualRectToScreen(Windows::Foundation::Rect)
0x18008274b  movdqu  xmm6, xmmword ptr [rax]
0x18008274f  lea     rcx, [rsp+180h+var_110]
0x180082754  call    ??$Make@VCNavigationFocusEventArgs@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCNavigationFocusEventArgs@@@12@XZ; Microsoft::WRL::Details::Make<CNavigationFocusEventArgs,>(void)
0x180082759  mov     rbx, qword ptr [rsp+180h+var_110]
0x18008275e  mov     ecx, [rsp+180h+var_140]
0x180082762  movdqa  [rbp+80h+var_A0], xmm6
0x180082767  mov     rax, [rbx]
0x18008276a  mov     [rsp+180h+var_160], ecx; int
0x18008276e  mov     r9, [rsp+180h+var_128]
0x180082773  lea     r8, [rbp+80h+var_A0]
0x180082777  mov     edx, r14d
0x18008277a  mov     rcx, rbx
0x18008277d  mov     rax, [rax+60h]
0x180082781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082786  mov     edi, eax
0x180082788  test    eax, eax
0x18008278a  jns     short loc_1800827D5
0x18008278c  mov     rcx, [rbp+88h]; this
0x180082793  mov     r9d, eax; char *
0x180082796  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18008279d  mov     edx, 771h; void *
0x1800827a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800827a7  nop
0x1800827a8  test    rbx, rbx
0x1800827ab  jz      short loc_1800827BD
0x1800827ad  mov     rax, [rbx]
0x1800827b0  mov     rcx, rbx
0x1800827b3  mov     rax, [rax+10h]
0x1800827b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800827bc  nop
0x1800827bd  lea     rcx, [rsp+180h+var_150]
0x1800827c2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800827c7  lea     rcx, [rsp+180h+var_148]
0x1800827cc  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800827d1  mov     ebx, edi
0x1800827d3  jmp     short loc_180082846
0x1800827d5  mov     rdx, rsi
0x1800827d8  lea     rcx, [rsp+180h+var_110]
0x1800827dd  call    ??$CopyTo@UINavigationFocusEventArgs@Core@UI@Windows@@@?$ComPtr@VCNavigationFocusEventArgs@@@WRL@Microsoft@@QEBAJPEAPEAUINavigationFocusEventArgs@Core@UI@Windows@@@Z; Microsoft::WRL::ComPtr<CNavigationFocusEventArgs>::CopyTo<Windows::UI::Core::INavigationFocusEventArgs>(Windows::UI::Core::INavigationFocusEventArgs * *)
0x1800827e2  mov     edi, eax
0x1800827e4  test    eax, eax
0x1800827e6  jns     short loc_18008281B
0x1800827e8  mov     rcx, [rbp+88h]; this
0x1800827ef  mov     r9d, eax; char *
0x1800827f2  lea     r8, aOnecoreuapWind_23; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800827f9  mov     edx, 772h; void *
0x1800827fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082803  nop
0x180082804  test    rbx, rbx
0x180082807  jz      short loc_180082819
0x180082809  mov     rax, [rbx]
0x18008280c  mov     rcx, rbx
0x18008280f  mov     rax, [rax+10h]
0x180082813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082818  nop
0x180082819  jmp     short loc_1800827BD
0x18008281b  test    rbx, rbx
0x18008281e  jz      short loc_180082830
0x180082820  mov     rax, [rbx]
0x180082823  mov     rcx, rbx
0x180082826  mov     rax, [rax+10h]
0x18008282a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008282f  nop
0x180082830  lea     rcx, [rsp+180h+var_150]
0x180082835  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18008283a  lea     rcx, [rsp+180h+var_148]
0x18008283f  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180082844  xor     ebx, ebx
0x180082846  lea     rcx, [rbp+80h+var_90]; this
0x18008284a  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18008284f  mov     eax, ebx
0x180082851  movaps  xmm6, [rsp+180h+var_40]
0x180082859  add     rsp, 158h
0x180082860  pop     r15
0x180082862  pop     r14
0x180082864  pop     rdi
0x180082865  pop     rsi
0x180082866  pop     rbx
0x180082867  pop     rbp
0x180082868  retn
```
