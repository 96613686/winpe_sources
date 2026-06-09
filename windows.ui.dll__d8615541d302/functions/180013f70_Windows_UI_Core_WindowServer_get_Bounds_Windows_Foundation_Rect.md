# Windows::UI::Core::WindowServer::get_Bounds(Windows::Foundation::Rect *)

- ea: `0x180013f70`
- end: `0x18001439a`
- name: `?get_Bounds@WindowServer@Core@UI@Windows@@UEAAJPEAURect@Foundation@4@@Z`
- size: `1066`
- prototype: `__int64 __fastcall(PVOID Parameter, struct Windows::Foundation::Rect *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180013ed8`
- `0x180013f70`
- `0x1800146a8`
- `0x1800146fc`
- `0x1800582ac`
- `0x18006040c`
- `0x18007d20c`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014082`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014082`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800141a9`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800141a9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001432c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001432c`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x18001420b`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x180014272`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x18001420b`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x180014272`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x180014310`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x180014310`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x1800141d8`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x1800141d8`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1800141cf`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1800141cf`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x18001431b`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x18001431b`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180013fe4`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180013ff2`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180014036`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x18001414f`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180013fe4`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180013ff2`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180014036`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x18001414f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x180014076`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x180014076`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18001409b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18001409b`

## string_xrefs

- `0x180014019`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180014056`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x18001416f`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::WindowServer::get_Bounds(char *Parameter, __m128i *a2)
{
  __int64 result; // rax
  unsigned __int8 Variant; // al
  unsigned __int8 v6; // al
  LONG left; // edx
  LONG top; // ecx
  DWORD LastError; // eax
  float v10; // xmm10_4
  float v11; // xmm11_4
  float v12; // xmm13_4
  float v13; // xmm12_4
  unsigned __int8 v14; // al
  Windows::UI::Core *v15; // rcx
  int v16; // eax
  float v17; // xmm7_4
  float v18; // xmm6_4
  __int64 v19; // rdi
  __int64 ThreadDpiAwarenessContext; // rax
  float v21; // xmm6_4
  __int64 v22; // rbx
  float DpiForThread; // xmm0_4
  int ScaleFactorForDevice; // eax
  __m128i v25; // xmm0
  int DpiForSystem; // eax
  const char *v27; // [rsp+30h] [rbp-71h]
  const char *v28; // [rsp+30h] [rbp-71h]
  const char *v29; // [rsp+30h] [rbp-71h]
  int v30; // [rsp+38h] [rbp-69h] BYREF
  __m128i v31; // [rsp+40h] [rbp-61h]
  __m128i v32; // [rsp+58h] [rbp-49h]
  struct tagRECT Rect; // [rsp+68h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  result = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)Parameter + 43) + 80LL))(Parameter + 344);
  if ( (int)result >= 0 )
  {
    if ( Parameter[2174] )
    {
      v25 = *((__m128i *)Parameter + 136);
    }
    else
    {
      v31 = 0;
      if ( !(unsigned int)IsOneCoreTransformMode() )
      {
        if ( !(unsigned int)IsOneCoreTransformMode()
          || (Variant = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_OneCoreTransforms>::GetImpl'::`2'::impl),
              Variant != 1) )
        {
          Variant = 0;
        }
        wil::details::in1diag3::FailFast_IfMsg(
          retaddr,
          (void *)0x15D,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
          (const char *)Variant,
          (bool)"This code branch should only run in Legacy mode, with OneCore Transforms off",
          v27);
        Rect = 0;
        if ( !(unsigned int)IsOneCoreTransformMode()
          || (v6 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_OneCoreTransforms>::GetImpl'::`2'::impl),
              v6 != 1) )
        {
          v6 = 0;
        }
        wil::details::in1diag3::FailFast_IfMsg(
          retaddr,
          (void *)0x15D,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
          (const char *)v6,
          (bool)"This code branch should only run in Legacy mode, with OneCore Transforms off",
          v28);
        if ( !GetClientRect(*((HWND *)Parameter + 433), &Rect)
          || (SetLastError(0), !MapWindowPoints(*((HWND *)Parameter + 433), 0, (LPPOINT)&Rect, 2u)) && GetLastError() )
        {
          left = 0;
          *(_QWORD *)&Rect.right = 0;
          *(_QWORD *)&Rect.left = 0;
          top = 0;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_16;
          }
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_850f2c403a353c03d19f0821ea469488_Traceguids, LastError);
        }
        left = Rect.left;
        top = Rect.top;
LABEL_16:
        v10 = (float)left;
        *(float *)v32.m128i_i32 = (float)left;
        v11 = (float)top;
        v12 = (float)(Rect.bottom - top);
        v13 = (float)(Rect.right - left);
        *(float *)&v32.m128i_i32[3] = v12;
        *(float *)&v32.m128i_i32[1] = (float)top;
        *(float *)&v32.m128i_i32[2] = v13;
        if ( !(unsigned int)IsOneCoreTransformMode()
          || (v14 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_OneCoreTransforms>::GetImpl'::`2'::impl),
              v14 != 1) )
        {
          v14 = 0;
        }
        wil::details::in1diag3::FailFast_IfMsg(
          retaddr,
          (void *)0x15D,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
          (const char *)v14,
          (bool)"This code branch should only run in Legacy mode, with OneCore Transforms off",
          v29);
        v16 = *((_DWORD *)Parameter + 744);
        if ( v16 == 2 )
        {
          v25 = v32;
        }
        else
        {
          v17 = v13;
          v18 = v12;
          if ( v16 == 1 && !(unsigned int)QuirkIsEnabled(589829) )
          {
            Windows::UI::Core::WindowServer::LegacyTransforms_InitializeComponentDisplayInformation(Parameter);
            v19 = *((_QWORD *)Parameter + 433);
            if ( (unsigned __int8)IsTextInputClientWrapperCreatePresent()
              && (ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext(),
                  (unsigned int)GetAwarenessFromDpiAwarenessContext(ThreadDpiAwarenessContext) != 2) )
            {
              DpiForSystem = GetDpiForSystem();
              v21 = (float)MulDiv(DpiForSystem, 100, 96) / 100.0;
            }
            else
            {
              v21 = 0.0;
            }
            if ( v21 == 0.0 )
            {
              v21 = FLOAT_1_0;
              v30 = 100;
              GetScaleFactorForWindow(v19, &v30);
              if ( v30 )
                v21 = (float)v30 / 100.0;
            }
            v17 = (float)(v21 / *((float *)Parameter + 735)) * v13;
            v18 = (float)(v21 / *((float *)Parameter + 736)) * v12;
          }
          v22 = *((_QWORD *)Parameter + 433);
          DpiForThread = Windows::UI::Core::GetDpiForThread(v15);
          if ( DpiForThread == 0.0 )
          {
            v30 = 100;
            if ( v22 && (int)GetScaleFactorForWindow(v22, &v30) >= 0 )
              ScaleFactorForDevice = v30;
            else
              ScaleFactorForDevice = GetScaleFactorForDevice(1);
            DpiForThread = (float)ScaleFactorForDevice / 100.0;
          }
          *(float *)v31.m128i_i32 = v10 / DpiForThread;
          *(float *)&v31.m128i_i32[1] = v11 / DpiForThread;
          *(float *)&v31.m128i_i32[2] = v17 / DpiForThread;
          *(float *)&v31.m128i_i32[3] = v18 / DpiForThread;
          v25 = v31;
        }
        goto LABEL_34;
      }
      v25 = _mm_loadu_si128((const __m128i *)Parameter + 202);
    }
LABEL_34:
    *a2 = v25;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180013f70  mov     rax, rsp
0x180013f73  mov     [rax+18h], rbx
0x180013f77  push    rbp
0x180013f78  push    rsi
0x180013f79  push    rdi
0x180013f7a  lea     rbp, [rax-5Fh]
0x180013f7e  sub     rsp, 0E0h
0x180013f85  movaps  xmmword ptr [rax-28h], xmm6
0x180013f89  movaps  xmmword ptr [rax-38h], xmm7
0x180013f8d  movaps  xmmword ptr [rax-48h], xmm10
0x180013f92  movaps  xmmword ptr [rax-58h], xmm11
0x180013f97  movaps  xmmword ptr [rax-68h], xmm12
0x180013f9c  movaps  xmmword ptr [rax-78h], xmm13
0x180013fa1  mov     rax, cs:__security_cookie
0x180013fa8  xor     rax, rsp
0x180013fab  mov     [rbp+57h+var_80], rax
0x180013faf  mov     rbx, rcx
0x180013fb2  mov     rsi, rdx
0x180013fb5  add     rcx, 158h
0x180013fbc  mov     rax, [rcx]
0x180013fbf  mov     rax, [rax+50h]
0x180013fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fc8  test    eax, eax
0x180013fca  js      loc_1800142C4
0x180013fd0  cmp     byte ptr [rbx+87Eh], 0
0x180013fd7  jnz     loc_18001434F
0x180013fdd  xorps   xmm0, xmm0
0x180013fe0  movups  [rbp+57h+var_B8], xmm0
0x180013fe4  call    cs:__imp_IsOneCoreTransformMode
0x180013fea  test    eax, eax
0x180013fec  jnz     loc_180014301
0x180013ff2  call    cs:__imp_IsOneCoreTransformMode
0x180013ff8  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneCoreTransforms@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneCoreTransforms@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms> `wil::Feature<__WilFeatureTraits_Feature_OneCoreTransforms>::GetImpl(void)'::`2'::impl
0x180013fff  test    eax, eax
0x180014001  jnz     loc_18001435B
0x180014007  xor     al, al
0x180014009  mov     rcx, [rbp+5Fh]; this
0x18001400d  lea     rdx, aThisCodeBranch; "This code branch should only run in Leg"...
0x180014014  mov     qword ptr [rsp+0F0h+var_D0], rdx; bool
0x180014019  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180014020  mov     edx, 15Dh; void *
0x180014025  movzx   r9d, al; char *
0x180014029  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x18001402e  xorps   xmm0, xmm0
0x180014031  movdqu  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180014036  call    cs:__imp_IsOneCoreTransformMode
0x18001403c  test    eax, eax
0x18001403e  jnz     loc_180014370
0x180014044  xor     al, al
0x180014046  mov     rcx, [rbp+5Fh]; this
0x18001404a  lea     rdx, aThisCodeBranch; "This code branch should only run in Leg"...
0x180014051  mov     qword ptr [rsp+0F0h+var_D0], rdx; bool
0x180014056  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18001405d  mov     edx, 15Dh; void *
0x180014062  movzx   r9d, al; char *
0x180014066  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x18001406b  mov     rcx, [rbx+0D88h]; hWnd
0x180014072  lea     rdx, [rbp+57h+Rect]; lpRect
0x180014076  call    cs:__imp_GetClientRect
0x18001407c  test    eax, eax
0x18001407e  jz      short loc_1800140AF
0x180014080  xor     ecx, ecx; dwErrCode
0x180014082  call    cs:__imp_SetLastError
0x180014088  mov     rcx, [rbx+0D88h]; hWndFrom
0x18001408f  lea     r8, [rbp+57h+Rect]; lpPoints
0x180014093  mov     r9d, 2; cPoints
0x180014099  xor     edx, edx; hWndTo
0x18001409b  call    cs:__imp_MapWindowPoints
0x1800140a1  test    eax, eax
0x1800140a3  jnz     short loc_180014103
0x1800140a5  call    cs:__imp_GetLastError
0x1800140ab  test    eax, eax
0x1800140ad  jz      short loc_180014103
0x1800140af  xor     edx, edx
0x1800140b1  mov     qword ptr [rbp+57h+Rect.right], 0
0x1800140b9  mov     qword ptr [rbp+57h+Rect.left], rdx
0x1800140bd  xor     ecx, ecx
0x1800140bf  mov     rax, cs:WPP_GLOBAL_Control
0x1800140c6  lea     r8, WPP_GLOBAL_Control
0x1800140cd  cmp     rax, r8
0x1800140d0  jz      short loc_180014109
0x1800140d2  test    byte ptr [rax+1Ch], 2
0x1800140d6  jz      short loc_180014109
0x1800140d8  cmp     byte ptr [rax+19h], 2
0x1800140dc  jb      short loc_180014109
0x1800140de  call    cs:__imp_GetLastError
0x1800140e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140eb  lea     r8, WPP_850f2c403a353c03d19f0821ea469488_Traceguids
0x1800140f2  mov     edx, 33h ; '3'
0x1800140f7  mov     r9d, eax
0x1800140fa  mov     rcx, [rcx+10h]
0x1800140fe  call    WPP_SF_d
0x180014103  mov     edx, [rbp+57h+Rect.left]
0x180014106  mov     ecx, [rbp+57h+Rect.top]
0x180014109  mov     eax, [rbp+57h+Rect.right]
0x18001410c  sub     eax, edx
0x18001410e  movd    xmm10, edx
0x180014113  movd    xmm11, ecx
0x180014118  cvtdq2ps xmm10, xmm10
0x18001411c  movd    xmm12, eax
0x180014121  mov     eax, [rbp+57h+Rect.bottom]
0x180014124  sub     eax, ecx
0x180014126  movss   dword ptr [rbp+57h+var_A0], xmm10
0x18001412c  cvtdq2ps xmm11, xmm11
0x180014130  movd    xmm13, eax
0x180014135  cvtdq2ps xmm13, xmm13
0x180014139  cvtdq2ps xmm12, xmm12
0x18001413d  movss   dword ptr [rbp+57h+var_A0+0Ch], xmm13
0x180014143  movss   dword ptr [rbp+57h+var_A0+4], xmm11
0x180014149  movss   dword ptr [rbp+57h+var_A0+8], xmm12
0x18001414f  call    cs:__imp_IsOneCoreTransformMode
0x180014155  test    eax, eax
0x180014157  jnz     loc_180014385
0x18001415d  xor     al, al
0x18001415f  mov     rcx, [rbp+5Fh]; this
0x180014163  lea     rdx, aThisCodeBranch; "This code branch should only run in Leg"...
0x18001416a  mov     qword ptr [rsp+0F0h+var_D0], rdx; bool
0x18001416f  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180014176  mov     edx, 15Dh; void *
0x18001417b  movzx   r9d, al; char *
0x18001417f  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x180014184  mov     eax, [rbx+0BA0h]
0x18001418a  cmp     eax, 2
0x18001418d  jz      loc_180014346
0x180014193  movaps  xmm7, xmm12
0x180014197  movaps  xmm6, xmm13
0x18001419b  cmp     eax, 1
0x18001419e  jnz     loc_180014244
0x1800141a4  mov     ecx, 90005h
0x1800141a9  call    cs:__imp_QuirkIsEnabled
0x1800141af  test    eax, eax
0x1800141b1  jnz     loc_180014244
0x1800141b7  mov     rcx, rbx; Parameter
0x1800141ba  call    ?LegacyTransforms_InitializeComponentDisplayInformation@WindowServer@Core@UI@Windows@@AEAAJXZ; Windows::UI::Core::WindowServer::LegacyTransforms_InitializeComponentDisplayInformation(void)
0x1800141bf  mov     rdi, [rbx+0D88h]
0x1800141c6  call    IsTextInputClientWrapperCreatePresent
0x1800141cb  test    al, al
0x1800141cd  jz      short loc_1800141E7
0x1800141cf  call    cs:__imp_GetThreadDpiAwarenessContext
0x1800141d5  mov     rcx, rax
0x1800141d8  call    cs:__imp_GetAwarenessFromDpiAwarenessContext
0x1800141de  cmp     eax, 2
0x1800141e1  jnz     loc_18001431B
0x1800141e7  xorps   xmm6, xmm6
0x1800141ea  ucomiss xmm6, cs:__real@00000000
0x1800141f1  jp      short loc_180014227
0x1800141f3  jnz     short loc_180014227
0x1800141f5  movss   xmm6, cs:__real@3f800000
0x1800141fd  lea     rdx, [rbp+57h+var_C0]
0x180014201  mov     rcx, rdi
0x180014204  mov     [rbp+57h+var_C0], 64h ; 'd'
0x18001420b  call    cs:__imp_GetScaleFactorForWindow
0x180014211  mov     eax, [rbp+57h+var_C0]
0x180014214  test    eax, eax
0x180014216  jz      short loc_180014227
0x180014218  movd    xmm6, eax
0x18001421c  cvtdq2ps xmm6, xmm6
0x18001421f  divss   xmm6, cs:__real@42c80000
0x180014227  movaps  xmm7, xmm6
0x18001422a  divss   xmm7, dword ptr [rbx+0B7Ch]
0x180014232  divss   xmm6, dword ptr [rbx+0B80h]
0x18001423a  mulss   xmm7, xmm12
0x18001423f  mulss   xmm6, xmm13
0x180014244  mov     rbx, [rbx+0D88h]
0x18001424b  call    ?GetDpiForThread@Core@UI@Windows@@YAMXZ; Windows::UI::Core::GetDpiForThread(void)
0x180014250  ucomiss xmm0, cs:__real@00000000
0x180014257  jp      short loc_180014292
0x180014259  jnz     short loc_180014292
0x18001425b  mov     [rbp+57h+var_C0], 64h ; 'd'
0x180014262  test    rbx, rbx
0x180014265  jz      loc_18001430B
0x18001426b  lea     rdx, [rbp+57h+var_C0]
0x18001426f  mov     rcx, rbx
0x180014272  call    cs:__imp_GetScaleFactorForWindow
0x180014278  test    eax, eax
0x18001427a  js      loc_18001430B
0x180014280  mov     eax, [rbp+57h+var_C0]
0x180014283  movd    xmm0, eax
0x180014287  cvtdq2ps xmm0, xmm0
0x18001428a  divss   xmm0, cs:__real@42c80000
0x180014292  divss   xmm10, xmm0
0x180014297  divss   xmm11, xmm0
0x18001429c  divss   xmm7, xmm0
0x1800142a0  divss   xmm6, xmm0
0x1800142a4  movss   dword ptr [rbp+57h+var_B8], xmm10
0x1800142aa  movss   dword ptr [rbp+57h+var_B8+4], xmm11
0x1800142b0  movss   dword ptr [rbp+57h+var_B8+8], xmm7
0x1800142b5  movss   dword ptr [rbp+57h+var_B8+0Ch], xmm6
0x1800142ba  movups  xmm0, [rbp+57h+var_B8]
0x1800142be  movdqu  xmmword ptr [rsi], xmm0
0x1800142c2  xor     eax, eax
0x1800142c4  mov     rcx, [rbp+57h+var_80]
0x1800142c8  xor     rcx, rsp; StackCookie
0x1800142cb  call    __security_check_cookie
0x1800142d0  lea     r11, [rsp+0F0h+var_10]
0x1800142d8  mov     rbx, [r11+30h]
0x1800142dc  movaps  xmm6, xmmword ptr [r11-10h]
0x1800142e1  movaps  xmm7, xmmword ptr [r11-20h]
0x1800142e6  movaps  xmm10, xmmword ptr [r11-30h]
0x1800142eb  movaps  xmm11, xmmword ptr [r11-40h]
0x1800142f0  movaps  xmm12, xmmword ptr [r11-50h]
0x1800142f5  movaps  xmm13, xmmword ptr [r11-60h]
0x1800142fa  mov     rsp, r11
0x1800142fd  pop     rdi
0x1800142fe  pop     rsi
0x1800142ff  pop     rbp
0x180014300  retn
0x180014301  movdqu  xmm0, xmmword ptr [rbx+0CA0h]
0x180014309  jmp     short loc_1800142BE
0x18001430b  mov     ecx, 1
0x180014310  call    cs:__imp_GetScaleFactorForDevice
0x180014316  jmp     loc_180014283
0x18001431b  call    cs:__imp_GetDpiForSystem
0x180014321  mov     edx, 64h ; 'd'; nNumerator
0x180014326  mov     ecx, eax; nNumber
0x180014328  lea     r8d, [rdx-4]; nDenominator
0x18001432c  call    cs:__imp_MulDiv
0x180014332  movd    xmm6, eax
0x180014336  cvtdq2ps xmm6, xmm6
0x180014339  divss   xmm6, cs:__real@42c80000
0x180014341  jmp     loc_1800141EA
0x180014346  movups  xmm0, [rbp+57h+var_A0]
0x18001434a  jmp     loc_1800142BE
0x18001434f  movups  xmm0, xmmword ptr [rbx+880h]
0x180014356  jmp     loc_1800142BE
0x18001435b  mov     rcx, rdi
0x18001435e  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_OneCoreTransforms@@@details@wil@@QEAA?AW4Variant_OneCoreTransforms@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180014363  cmp     al, 1
0x180014365  jnz     loc_180014007
0x18001436b  jmp     loc_180014009
0x180014370  mov     rcx, rdi
0x180014373  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_OneCoreTransforms@@@details@wil@@QEAA?AW4Variant_OneCoreTransforms@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180014378  cmp     al, 1
0x18001437a  jnz     loc_180014044
0x180014380  jmp     loc_180014046
0x180014385  mov     rcx, rdi
0x180014388  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_OneCoreTransforms@@@details@wil@@QEAA?AW4Variant_OneCoreTransforms@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms>::__private_GetVariant(wil::VariantReportingKind,bool)
0x18001438d  cmp     al, 1
0x18001438f  jnz     loc_18001415D
0x180014395  jmp     loc_18001415F
```
