# TouchKeyboardExperienceManager::ApplyRequestedRect(KBViewInfo *,tagRECT const *)

- ea: `0x180073ed4`
- end: `0x180074372`
- name: `?ApplyRequestedRect@TouchKeyboardExperienceManager@@AEAAJPEAUKBViewInfo@@PEBUtagRECT@@@Z`
- size: `1182`
- prototype: `int(TouchKeyboardExperienceManager *__hidden this, struct KBViewInfo *, const struct tagRECT *)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180073810`
- `0x18027ab70`
- `0x1802d06ac`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x180031c70`
- `0x1800732a4`
- `0x180073ed4`
- `0x180074640`
- `0x1800747e0`
- `0x1800752c8`
- `0x1800b0290`
- `0x1800d3cdc`
- `0x1801e1b2c`
- `0x1802e6648`
- `0x1804bcc20`
- `0x1806fa010`

## import_xrefs

- `ext-ms-win-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1800742c9`
- `ext-ms-win-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1806ef555`
- `ext-ms-win-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1800742c9`
- `ext-ms-win-gdi-rgn-l1-1-0!CreateRectRgn` at `0x1806ef555`
- `ext-ms-win-ntuser-draw-l1-1-0!SetWindowRgn` at `0x180073ff2`
- `ext-ms-win-ntuser-draw-l1-1-0!SetWindowRgn` at `0x18007423e`
- `ext-ms-win-ntuser-draw-l1-1-0!SetWindowRgn` at `0x180073ff2`
- `ext-ms-win-ntuser-draw-l1-1-0!SetWindowRgn` at `0x18007423e`
- `GDI32!DeleteObject` at `0x1800741e9`
- `GDI32!DeleteObject` at `0x180074216`
- `GDI32!DeleteObject` at `0x1800742f5`
- `GDI32!DeleteObject` at `0x180074303`
- `GDI32!DeleteObject` at `0x18007434f`
- `GDI32!DeleteObject` at `0x180074367`
- `GDI32!DeleteObject` at `0x1800741e9`
- `GDI32!DeleteObject` at `0x180074216`
- `GDI32!DeleteObject` at `0x1800742f5`
- `GDI32!DeleteObject` at `0x180074303`
- `GDI32!DeleteObject` at `0x18007434f`
- `GDI32!DeleteObject` at `0x180074367`
- `GDI32!CombineRgn` at `0x1806ef57f`
- `GDI32!CombineRgn` at `0x1806ef57f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TouchKeyboardExperienceManager::ApplyRequestedRect(
        TouchKeyboardExperienceManager *this,
        struct KBViewInfo *a2,
        const struct tagRECT *a3)
{
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, struct IApplicationFrame **); // rbx
  int v8; // eax
  TouchKeyboardExperienceManager *v9; // rcx
  unsigned int v10; // ebx
  struct IApplicationFrame *v11; // rcx
  int v13; // eax
  HRGN v14; // rbx
  int updated; // eax
  float v16; // xmm4_4
  float v17; // xmm1_4
  float v18; // xmm2_4
  float v19; // xmm3_4
  LONG left; // r8d
  LONG top; // r9d
  LONG right; // eax
  LONG bottom; // ecx
  int v24; // eax
  unsigned int v25; // edi
  struct IApplicationFrame *v26; // rcx
  int v27; // edi
  TouchKeyboardExperienceTelemetryLogger *v28; // rcx
  const __m128i *v29; // r14
  __int64 v30; // rdx
  __int64 v31; // rdx
  HRGN RectRgn; // rax
  const __m128i *v33; // r12
  __int64 v34; // rdx
  float v35; // xmm1_4
  HRGN v36; // rax
  HGDIOBJ v37; // rdi
  unsigned __int64 v38; // rdx
  unsigned __int8 v39; // cl
  struct IApplicationFrame *v40; // [rsp+20h] [rbp-30h] BYREF
  HRGN v41; // [rsp+28h] [rbp-28h] BYREF
  HWND hWnd; // [rsp+30h] [rbp-20h] BYREF
  HGDIOBJ ho; // [rsp+38h] [rbp-18h] BYREF
  __m128 v44; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  v40 = 0;
  v6 = *((_QWORD *)a2 + 1);
  v7 = *(__int64 (__fastcall **)(__int64, struct IApplicationFrame **))(*(_QWORD *)v6 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  v8 = v7(v6, &v40);
  v10 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1073,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v8,
      (int)v40);
    v11 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(struct IApplicationFrame *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v10;
  }
  v13 = TouchKeyboardExperienceManager::SetHostedPos(v9, *((struct IApplicationFrameWrapper **)a2 + 1), v40, a3);
  v10 = v13;
  if ( v13 < 0 )
  {
    v31 = 4219;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)v13,
      (int)v40);
LABEL_32:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
    return v10;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a2 + 2) + 32LL))(*((_QWORD *)a2 + 2), 0);
  v10 = v13;
  if ( v13 < 0 )
  {
    v31 = 4222;
    goto LABEL_46;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 2) + 80LL))(*((_QWORD *)a2 + 2));
  v10 = v13;
  if ( v13 < 0 )
  {
    v31 = 4223;
    goto LABEL_46;
  }
  hWnd = 0;
  v13 = (*(__int64 (__fastcall **)(struct IApplicationFrame *, HWND *))(*(_QWORD *)v40 + 24LL))(v40, &hWnd);
  v10 = v13;
  if ( v13 < 0 )
  {
    v31 = 4225;
    goto LABEL_46;
  }
  v14 = 0;
  v41 = 0;
  if ( (__int64)(*((_QWORD *)a2 + 24) - *((_QWORD *)a2 + 23)) >> 4 )
  {
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::reset(
      &v41,
      RectRgn);
    v29 = (const __m128i *)*((_QWORD *)a2 + 23);
    v33 = (const __m128i *)*((_QWORD *)a2 + 24);
    v14 = v41;
    while ( v29 != v33 )
    {
      v44 = (__m128)_mm_loadu_si128(v29);
      ho = 0;
      v35 = _mm_shuffle_ps(v44, v44, 85).m128_f32[0];
      v36 = CreateRectRgn(
              (int)v44.m128_f32[0],
              (int)v35,
              (int)(float)(_mm_shuffle_ps(v44, v44, 170).m128_f32[0] + v44.m128_f32[0]),
              (int)(float)(_mm_shuffle_ps(v44, v44, 255).m128_f32[0] + v35));
      wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::reset(
        &ho,
        v36);
      v37 = ho;
      if ( !ho )
      {
        v27 = -2147024890;
        v34 = 4243;
        goto LABEL_29;
      }
      if ( !CombineRgn(v14, v14, (HRGN)ho, 2) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1094,
          (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
          (const char *)0x8000FFFFLL,
          (int)v40);
        DeleteObject(v37);
        if ( v14 )
          DeleteObject(v14);
        v10 = -2147418113;
        goto LABEL_32;
      }
      if ( TouchKeyboardExperienceTelemetryLogger::IsEnabled(v39, v38) )
      {
        TouchKeyboardExperienceTelemetryLogger::Instance();
        TouchKeyboardExperienceTelemetryLogger::SetVisibleViewRect_(v28, (const struct Windows::Foundation::Rect *)&v44);
      }
      DeleteObject(v37);
      ++v29;
    }
    if ( !SetWindowRgn(hWnd, v14, 1) )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1098,
        (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
        (const char *)0x8000FFFFLL,
        (int)v40);
    LOBYTE(v30) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PATKTI>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_PATKTI>::GetImpl'::`2'::impl,
      v30);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&int DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>>::swap(
      (char *)this + 640,
      &v41);
    v14 = v41;
  }
  else if ( !SetWindowRgn(hWnd, 0, 1) )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x10A8,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)0x8000FFFFLL,
      (int)v40);
  }
  updated = TouchKeyboardExperienceManager::UpdateBorderStyle(this, hWnd, a2);
  if ( updated < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x10AB,
      (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
      (const char *)(unsigned int)updated,
      (int)v40);
  *(struct tagRECT *)((char *)a2 + 120) = *a3;
  v16 = *((float *)a2 + 42);
  v17 = *((float *)a2 + 43);
  v18 = *((float *)a2 + 44);
  v19 = *((float *)a2 + 45);
  left = a3->left;
  top = a3->top;
  if ( v16 == 0.0 && v17 == 0.0 && v18 == 0.0 && v19 == 0.0 )
  {
    right = a3->right;
    bottom = a3->bottom;
  }
  else
  {
    left += (int)v16;
    top += (int)v17;
    right = (int)(float)((float)left + v18);
    bottom = (int)(float)((float)top + v19);
  }
  *((_DWORD *)a2 + 34) = left;
  *((_DWORD *)a2 + 35) = top;
  *((_DWORD *)a2 + 36) = right;
  *((_DWORD *)a2 + 37) = bottom;
  v24 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)a2 + 344LL))(*(_QWORD *)a2, 4);
  v25 = v24;
  if ( v24 >= 0 )
  {
    KBViewInfo::BoostPriority(a2);
    v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 1) + 112LL))(*((_QWORD *)a2 + 1));
    if ( v27 < 0 )
    {
      v34 = 4280;
LABEL_29:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
        (const char *)(unsigned int)v27,
        (int)v40);
      if ( v14 )
        DeleteObject(v14);
      v10 = v27;
    }
    else
    {
      if ( v14 )
        DeleteObject(v14);
      v10 = 0;
    }
    goto LABEL_32;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x10B1,
    (unsigned int)"pcshell\\twinui\\touchkeyboardexperiencemanager\\lib\\touchkeyboardexperiencemanager.cpp",
    (const char *)(unsigned int)v24,
    (int)v40);
  if ( v14 )
    DeleteObject(v14);
  v26 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(struct IApplicationFrame *))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return v25;
}

```

## disassembly

```asm
0x180073ed4  mov     [rsp-38h+arg_18], rbx
0x180073ed9  push    rbp
0x180073eda  push    rsi
0x180073edb  push    rdi
0x180073edc  push    r12
0x180073ede  push    r13
0x180073ee0  push    r14
0x180073ee2  push    r15
0x180073ee4  mov     rbp, rsp
0x180073ee7  sub     rsp, 50h
0x180073eeb  mov     r15, r8
0x180073eee  mov     rsi, rdx
0x180073ef1  mov     r13, rcx
0x180073ef4  mov     [rbp+var_30], 0
0x180073efc  mov     rdi, [rdx+8]
0x180073f00  mov     rax, [rdi]
0x180073f03  mov     rbx, [rax+20h]
0x180073f07  lea     rcx, [rbp+var_30]
0x180073f0b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180073f10  lea     rdx, [rbp+var_30]
0x180073f14  mov     rcx, rdi
0x180073f17  mov     rax, rbx
0x180073f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073f1f  mov     ebx, eax
0x180073f21  test    eax, eax
0x180073f23  jns     loc_180074273
0x180073f29  mov     rcx, [rbp+38h]; this
0x180073f2d  mov     r9d, eax; char *
0x180073f30  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x180073f37  mov     edx, 1073h; void *
0x180073f3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073f41  nop
0x180073f42  mov     rcx, [rbp+var_30]
0x180073f46  test    rcx, rcx
0x180073f49  jz      short loc_180073F60
0x180073f4b  mov     [rbp+var_30], 0
0x180073f53  mov     rax, [rcx]
0x180073f56  mov     rax, [rax+10h]
0x180073f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073f5f  nop
0x180073f60  mov     eax, ebx
0x180073f62  jmp     loc_180074108
0x180073f67  mov     rcx, [rsi+10h]
0x180073f6b  mov     rax, [rcx]
0x180073f6e  xor     edx, edx
0x180073f70  mov     rax, [rax+20h]
0x180073f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073f79  mov     ebx, eax
0x180073f7b  test    eax, eax
0x180073f7d  js      loc_180074294
0x180073f83  mov     rcx, [rsi+10h]
0x180073f87  mov     rax, [rcx]
0x180073f8a  mov     rax, [rax+50h]
0x180073f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073f93  mov     ebx, eax
0x180073f95  test    eax, eax
0x180073f97  js      loc_1800742B8
0x180073f9d  mov     [rbp+hWnd], 0
0x180073fa5  mov     rcx, [rbp+var_30]
0x180073fa9  mov     rax, [rcx]
0x180073fac  lea     rdx, [rbp+hWnd]
0x180073fb0  mov     rax, [rax+18h]
0x180073fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073fb9  mov     ebx, eax
0x180073fbb  test    eax, eax
0x180073fbd  js      loc_18007429B
0x180073fc3  xor     ebx, ebx
0x180073fc5  mov     [rbp+var_28], rbx
0x180073fc9  mov     rax, [rsi+0C0h]
0x180073fd0  sub     rax, [rsi+0B8h]
0x180073fd7  sar     rax, 4
0x180073fdb  test    rax, rax
0x180073fde  jnz     loc_1800742BF
0x180073fe4  mov     rdi, [rbp+38h]
0x180073fe8  xor     edx, edx; hRgn
0x180073fea  lea     r8d, [rbx+1]; bRedraw
0x180073fee  mov     rcx, [rbp+hWnd]; hWnd
0x180073ff2  call    cs:__imp_SetWindowRgn
0x180073ff8  test    eax, eax
0x180073ffa  jz      loc_18007432D
0x180074000  mov     r8, rsi; struct KBViewInfo *
0x180074003  mov     rdx, [rbp+hWnd]; hwnd
0x180074007  mov     rcx, r13; this
0x18007400a  call    ?UpdateBorderStyle@TouchKeyboardExperienceManager@@AEAAJPEAUHWND__@@AEBUKBViewInfo@@@Z; TouchKeyboardExperienceManager::UpdateBorderStyle(HWND__ *,KBViewInfo const &)
0x18007400f  mov     rcx, [rbp+38h]; this
0x180074013  test    eax, eax
0x180074015  js      loc_18007415A
0x18007401b  movups  xmm0, xmmword ptr [r15]
0x18007401f  movdqu  xmmword ptr [rsi+78h], xmm0
0x180074024  movss   xmm4, dword ptr [rsi+0A8h]
0x18007402c  movss   xmm1, dword ptr [rsi+0ACh]
0x180074034  movss   xmm2, dword ptr [rsi+0B0h]
0x18007403c  movss   xmm3, dword ptr [rsi+0B4h]
0x180074044  mov     r8d, [r15]
0x180074047  mov     r9d, [r15+4]
0x18007404b  xorps   xmm0, xmm0
0x18007404e  ucomiss xmm4, xmm0
0x180074051  jp      short loc_180074059
0x180074053  jz      loc_180074120
0x180074059  cvttss2si ecx, xmm4
0x18007405d  add     ecx, r8d
0x180074060  mov     r8d, ecx
0x180074063  cvttss2si edx, xmm1
0x180074067  add     edx, r9d
0x18007406a  mov     r9d, edx
0x18007406d  movd    xmm0, ecx
0x180074071  cvtdq2ps xmm0, xmm0
0x180074074  addss   xmm0, xmm2
0x180074078  cvttss2si eax, xmm0
0x18007407c  movd    xmm1, edx
0x180074080  cvtdq2ps xmm1, xmm1
0x180074083  addss   xmm1, xmm3
0x180074087  cvttss2si ecx, xmm1
0x18007408b  mov     [rsi+88h], r8d
0x180074092  mov     [rsi+8Ch], r9d
0x180074099  mov     [rsi+90h], eax
0x18007409f  mov     [rsi+94h], ecx
0x1800740a5  mov     rcx, [rsi]
0x1800740a8  mov     rax, [rcx]
0x1800740ab  mov     edx, 4
0x1800740b0  mov     rax, [rax+158h]
0x1800740b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800740bc  mov     edi, eax
0x1800740be  test    eax, eax
0x1800740c0  jns     loc_180074173
0x1800740c6  mov     rcx, [rbp+38h]; this
0x1800740ca  mov     r9d, eax; char *
0x1800740cd  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800740d4  mov     edx, 10B1h; void *
0x1800740d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800740de  nop
0x1800740df  test    rbx, rbx
0x1800740e2  jnz     loc_18007434C
0x1800740e8  mov     rcx, [rbp+var_30]
0x1800740ec  test    rcx, rcx
0x1800740ef  jz      short loc_180074106
0x1800740f1  mov     [rbp+var_30], 0
0x1800740f9  mov     rax, [rcx]
0x1800740fc  mov     rax, [rax+10h]
0x180074100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074105  nop
0x180074106  mov     eax, edi
0x180074108  mov     rbx, [rsp+50h+arg_18]
0x180074110  add     rsp, 50h
0x180074114  pop     r15
0x180074116  pop     r14
0x180074118  pop     r13
0x18007411a  pop     r12
0x18007411c  pop     rdi
0x18007411d  pop     rsi
0x18007411e  pop     rbp
0x18007411f  retn
0x180074120  ucomiss xmm1, xmm0
0x180074123  jp      loc_180074059
0x180074129  jnz     loc_180074059
0x18007412f  ucomiss xmm2, xmm0
0x180074132  jp      loc_180074059
0x180074138  jnz     loc_180074059
0x18007413e  ucomiss xmm3, xmm0
0x180074141  jp      loc_180074059
0x180074147  jnz     loc_180074059
0x18007414d  mov     eax, [r15+8]
0x180074151  mov     ecx, [r15+0Ch]
0x180074155  jmp     loc_18007408B
0x18007415a  mov     r9d, eax; char *
0x18007415d  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x180074164  mov     edx, 10ABh; void *
0x180074169  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007416e  jmp     loc_18007401B
0x180074173  mov     rcx, rsi; this
0x180074176  call    ?BoostPriority@KBViewInfo@@QEAAXXZ; KBViewInfo::BoostPriority(void)
0x18007417b  mov     rcx, [rsi+8]
0x18007417f  mov     rax, [rcx]
0x180074182  mov     rax, [rax+70h]
0x180074186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007418b  mov     edi, eax
0x18007418d  test    eax, eax
0x18007418f  js      loc_18007435A
0x180074195  test    rbx, rbx
0x180074198  jnz     loc_180074364
0x18007419e  xor     ebx, ebx
0x1800741a0  jmp     short loc_1800741C1
0x1800741a2  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800741a9  mov     r9d, edi; char *
0x1800741ac  mov     rcx, [rbp+38h]; this
0x1800741b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800741b5  nop
0x1800741b6  test    rbx, rbx
0x1800741b9  jnz     loc_180074300
0x1800741bf  mov     ebx, edi
0x1800741c1  lea     rcx, [rbp+var_30]
0x1800741c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800741ca  jmp     loc_180073F60
0x1800741cf  call    ?IsEnabled@TouchKeyboardExperienceTelemetryLogger@@SA_NE_K@Z; TouchKeyboardExperienceTelemetryLogger::IsEnabled(uchar,unsigned __int64)
0x1800741d4  test    al, al
0x1800741d6  jz      short loc_1800741E6
0x1800741d8  call    ?Instance@TouchKeyboardExperienceTelemetryLogger@@KAPEAV1@XZ; TouchKeyboardExperienceTelemetryLogger::Instance(void)
0x1800741dd  lea     rdx, [rbp+var_10]; struct Windows::Foundation::Rect *
0x1800741e1  call    ?SetVisibleViewRect_@TouchKeyboardExperienceTelemetryLogger@@QEBAXAEBURect@Foundation@Windows@@@Z; TouchKeyboardExperienceTelemetryLogger::SetVisibleViewRect_(Windows::Foundation::Rect const &)
0x1800741e6  mov     rcx, rdi; ho
0x1800741e9  call    cs:__imp_DeleteObject
0x1800741ef  add     r14, 10h
0x1800741f3  jmp     loc_1806EF50C
0x1800741f8  mov     rcx, [rbp+38h]; this
0x1800741fc  mov     r9d, 8000FFFFh; char *
0x180074202  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x180074209  mov     edx, 1094h; void *
0x18007420e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074213  mov     rcx, rdi; ho
0x180074216  call    cs:__imp_DeleteObject
0x18007421c  nop
0x18007421d  test    rbx, rbx
0x180074220  jnz     loc_1800742F2
0x180074226  mov     ebx, 8000FFFFh
0x18007422b  jmp     short loc_1800741C1
0x18007422d  mov     rdi, [rbp+38h]
0x180074231  mov     r8d, 1; bRedraw
0x180074237  mov     rdx, rbx; hRgn
0x18007423a  mov     rcx, [rbp+hWnd]; hWnd
0x18007423e  call    cs:__imp_SetWindowRgn
0x180074244  test    eax, eax
0x180074246  jz      loc_18007430E
0x18007424c  mov     dl, 1
0x18007424e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PATKTI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PATKTI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PATKTI> `wil::Feature<__WilFeatureTraits_Feature_PATKTI>::GetImpl(void)'::`2'::impl
0x180074255  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_PATKTI@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PATKTI>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007425a  lea     rcx, [r13+280h]
0x180074261  lea     rdx, [rbp+var_28]
0x180074265  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHRGN__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>> &)
0x18007426a  mov     rbx, [rbp+var_28]
0x18007426e  jmp     loc_180074000
0x180074273  mov     r9, r15; struct tagRECT *
0x180074276  mov     r8, [rbp+var_30]; struct IApplicationFrame *
0x18007427a  mov     rdx, [rsi+8]; struct IApplicationFrameWrapper *
0x18007427e  call    ?SetHostedPos@TouchKeyboardExperienceManager@@AEAAJPEAUIApplicationFrameWrapper@@PEAUIApplicationFrame@@PEBUtagRECT@@@Z; TouchKeyboardExperienceManager::SetHostedPos(IApplicationFrameWrapper *,IApplicationFrame *,tagRECT const *)
0x180074283  mov     ebx, eax
0x180074285  test    eax, eax
0x180074287  jns     loc_180073F67
0x18007428d  mov     edx, 107Bh
0x180074292  jmp     short loc_1800742A0
0x180074294  mov     edx, 107Eh
0x180074299  jmp     short loc_1800742A0
0x18007429b  mov     edx, 1081h; void *
0x1800742a0  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x1800742a7  mov     r9d, eax; char *
0x1800742aa  mov     rcx, [rbp+38h]; this
0x1800742ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800742b3  jmp     loc_1800741C1
0x1800742b8  mov     edx, 107Fh
0x1800742bd  jmp     short loc_1800742A0
0x1800742bf  xor     r9d, r9d; y2
0x1800742c2  xor     r8d, r8d; x2
0x1800742c5  xor     edx, edx; y1
0x1800742c7  xor     ecx, ecx; x1
0x1800742c9  call    cs:__imp_CreateRectRgn
0x1800742cf  mov     rdx, rax
0x1800742d2  lea     rcx, [rbp+var_28]
0x1800742d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHRGN__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHRGN__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HRGN__ *,int (*)(void *),&DeleteObject(void *),wistd::integral_constant<unsigned __int64,0>,HRGN__ *,HRGN__ *,0,std::nullptr_t>>::reset(HRGN__ *)
0x1800742db  mov     r14, [rsi+0B8h]
0x1800742e2  mov     r12, [rsi+0C0h]
0x1800742e9  mov     rbx, [rbp+var_28]
0x1800742ed  jmp     loc_1806EF50C
0x1800742f2  mov     rcx, rbx; ho
0x1800742f5  call    cs:__imp_DeleteObject
0x1800742fb  jmp     loc_180074226
0x180074300  mov     rcx, rbx; ho
0x180074303  call    cs:__imp_DeleteObject
0x180074309  jmp     loc_1800741BF
0x18007430e  mov     r9d, 8000FFFFh; char *
0x180074314  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18007431b  mov     edx, 1098h; void *
0x180074320  mov     rcx, rdi; this
0x180074323  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180074328  jmp     loc_18007424C
0x18007432d  mov     r9d, 8000FFFFh; char *
0x180074333  lea     r8, aPcshellTwinuiT_50; "pcshell\\twinui\\touchkeyboardexperienc"...
0x18007433a  mov     edx, 10A8h; void *
0x18007433f  mov     rcx, rdi; this
0x180074342  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180074347  jmp     loc_180074000
0x18007434c  mov     rcx, rbx; ho
0x18007434f  call    cs:__imp_DeleteObject
0x180074355  jmp     loc_1800740E8
0x18007435a  mov     edx, 10B8h; void *
0x18007435f  jmp     loc_1800741A2
0x180074364  mov     rcx, rbx; ho
0x180074367  call    cs:__imp_DeleteObject
0x18007436d  jmp     loc_18007419E
0x1806ef50c  cmp     r14, r12
0x1806ef50f  jz      loc_18007422D
0x1806ef515  movdqu  xmm2, xmmword ptr [r14]
0x1806ef51a  movups  [rbp+var_10], xmm2
0x1806ef51e  mov     [rbp+ho], 0
0x1806ef526  movaps  xmm0, xmm2
0x1806ef529  shufps  xmm0, xmm2, 0FFh
0x1806ef52d  movaps  xmm1, xmm2
0x1806ef530  shufps  xmm1, xmm2, 55h ; 'U'
0x1806ef534  addss   xmm0, xmm1
0x1806ef538  cvttss2si r9d, xmm0; y2
0x1806ef53d  movaps  xmm0, xmm2
0x1806ef540  shufps  xmm0, xmm2, 0AAh
  ... truncated ...
```
