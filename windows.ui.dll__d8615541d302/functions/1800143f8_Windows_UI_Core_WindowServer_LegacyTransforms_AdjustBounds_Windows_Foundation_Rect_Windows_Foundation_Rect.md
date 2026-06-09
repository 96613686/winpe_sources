# Windows::UI::Core::WindowServer::LegacyTransforms_AdjustBounds(Windows::Foundation::Rect,Windows::Foundation::Rect *)

- ea: `0x1800143f8`
- end: `0x1800146a2`
- name: `?LegacyTransforms_AdjustBounds@WindowServer@Core@UI@Windows@@AEAAJURect@Foundation@4@PEAU564@@Z`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013c70`

## callees

- `0x1800143f8`
- `0x1800146a8`
- `0x1800581b8`
- `0x18006040c`
- `0x18007d20c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800144bb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800144bb`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x18001446e`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x18001446e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001461f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001464a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001461f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001464a`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x180014517`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x1800145a6`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x180014517`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x1800145a6`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x180014606`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x180014606`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x1800144e2`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x180014574`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x1800144e2`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x180014574`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1800144d9`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18001456b`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x1800144d9`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18001456b`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x18001460e`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x180014639`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x18001460e`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x180014639`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180014418`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x18001447c`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180014418`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x18001447c`

## string_xrefs

- `0x18001442d`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::WindowServer::LegacyTransforms_AdjustBounds(__int64 a1, __m128 *a2, __m128 *a3)
{
  unsigned __int8 Variant; // al
  int v7; // eax
  unsigned __int8 v8; // al
  const char *v9; // r9
  __int64 v10; // rbp
  __int64 ThreadDpiAwarenessContext; // rax
  float v12; // xmm6_4
  float v13; // xmm0_4
  float v14; // xmm6_4
  __int64 v15; // rsi
  __int64 v16; // rax
  __m128 v17; // xmm2
  int ScaleFactorForDevice; // eax
  int v20; // eax
  int DpiForSystem; // eax
  const char *v22; // [rsp+28h] [rbp-30h]
  const char *v23; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v25; // [rsp+60h] [rbp+8h] BYREF

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
    v22);
  v7 = *(_DWORD *)(a1 + 2976);
  if ( v7 == 2 )
  {
    *a3 = *a2;
  }
  else
  {
    if ( v7 == 1 && !(unsigned int)QuirkIsEnabled(589829) )
    {
      if ( !(unsigned int)IsOneCoreTransformMode()
        || (v8 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms>::__private_GetVariant(`wil::Feature<__WilFeatureTraits_Feature_OneCoreTransforms>::GetImpl'::`2'::impl),
            v8 != 1) )
      {
        v8 = 0;
      }
      wil::details::in1diag3::FailFast_IfMsg(
        retaddr,
        (void *)0x15D,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)v8,
        (bool)"This code branch should only run in Legacy mode, with OneCore Transforms off",
        v23);
      if ( !InitOnceExecuteOnce(
              (PINIT_ONCE)(a1 + 3456),
              lambda_b47dd024c43b8dbdfe446eeb01170236_::_lambda_invoker_cdecl_,
              (PVOID)a1,
              0) )
        wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x22D7,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
          v9);
      v10 = *(_QWORD *)(a1 + 3464);
      if ( (unsigned __int8)IsTextInputClientWrapperCreatePresent()
        && (ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext(),
            (unsigned int)GetAwarenessFromDpiAwarenessContext(ThreadDpiAwarenessContext) != 2) )
      {
        DpiForSystem = GetDpiForSystem();
        v12 = (float)MulDiv(DpiForSystem, 100, 96) / 100.0;
      }
      else
      {
        v12 = 0.0;
      }
      if ( v12 == 0.0 )
      {
        v12 = FLOAT_1_0;
        v25 = 100;
        GetScaleFactorForWindow(v10, &v25);
        if ( v25 )
          v12 = (float)v25 / 100.0;
      }
      v13 = (float)(v12 / *(float *)(a1 + 2940)) * a2->m128_f32[2];
      v14 = (float)(v12 / *(float *)(a1 + 2944)) * a2->m128_f32[3];
      a2->m128_f32[2] = v13;
      a2->m128_f32[3] = v14;
    }
    v15 = *(_QWORD *)(a1 + 3464);
    if ( (unsigned __int8)IsTextInputClientWrapperCreatePresent()
      && (v16 = GetThreadDpiAwarenessContext(), (unsigned int)GetAwarenessFromDpiAwarenessContext(v16) != 2) )
    {
      v20 = GetDpiForSystem();
      v17 = (__m128)COERCE_UNSIGNED_INT((float)MulDiv(v20, 100, 96));
      v17.m128_f32[0] = v17.m128_f32[0] / 100.0;
    }
    else
    {
      v17 = 0;
    }
    if ( v17.m128_f32[0] == 0.0 )
    {
      v25 = 100;
      if ( v15 && (int)GetScaleFactorForWindow(v15, &v25) >= 0 )
        ScaleFactorForDevice = v25;
      else
        ScaleFactorForDevice = GetScaleFactorForDevice(1);
      v17 = (__m128)COERCE_UNSIGNED_INT((float)ScaleFactorForDevice);
      v17.m128_f32[0] = v17.m128_f32[0] / 100.0;
    }
    *a3 = _mm_div_ps(*a2, _mm_shuffle_ps(v17, v17, 0));
  }
  return 0;
}

```

## disassembly

```asm
0x1800143f8  mov     [rsp+arg_8], rbx
0x1800143fd  mov     [rsp+arg_10], rbp
0x180014402  push    rsi
0x180014403  push    rdi
0x180014404  push    r13
0x180014406  sub     rsp, 40h
0x18001440a  movaps  [rsp+58h+var_28], xmm6
0x18001440f  mov     rdi, r8
0x180014412  mov     rbx, rdx
0x180014415  mov     rsi, rcx
0x180014418  call    cs:__imp_IsOneCoreTransformMode
0x18001441e  test    eax, eax
0x180014420  jnz     loc_180014670
0x180014426  xor     al, al
0x180014428  mov     rcx, [rsp+58h]; this
0x18001442d  lea     rbp, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180014434  lea     r13, aThisCodeBranch; "This code branch should only run in Leg"...
0x18001443b  movzx   r9d, al; char *
0x18001443f  mov     r8, rbp; unsigned int
0x180014442  mov     qword ptr [rsp+58h+var_38], r13; bool
0x180014447  mov     edx, 15Dh; void *
0x18001444c  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x180014451  mov     eax, [rsi+0BA0h]
0x180014457  cmp     eax, 2
0x18001445a  jz      loc_180014664
0x180014460  cmp     eax, 1
0x180014463  jnz     loc_18001455B
0x180014469  mov     ecx, 90005h
0x18001446e  call    cs:__imp_QuirkIsEnabled
0x180014474  test    eax, eax
0x180014476  jnz     loc_18001455B
0x18001447c  call    cs:__imp_IsOneCoreTransformMode
0x180014482  test    eax, eax
0x180014484  jnz     loc_180014689
0x18001448a  xor     al, al
0x18001448c  mov     rcx, [rsp+58h]; this
0x180014491  mov     r8, rbp; unsigned int
0x180014494  movzx   r9d, al; char *
0x180014498  mov     edx, 15Dh; void *
0x18001449d  mov     qword ptr [rsp+58h+var_38], r13; bool
0x1800144a2  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x1800144a7  lea     rcx, [rsi+0D80h]; InitOnce
0x1800144ae  xor     r9d, r9d; Context
0x1800144b1  mov     r8, rsi; Parameter
0x1800144b4  lea     rdx, _lambda_b47dd024c43b8dbdfe446eeb01170236____lambda_invoker_cdecl_; InitFn
0x1800144bb  call    cs:__imp_InitOnceExecuteOnce
0x1800144c1  test    eax, eax
0x1800144c3  jz      loc_1800145EA
0x1800144c9  mov     rbp, [rsi+0D88h]
0x1800144d0  call    IsTextInputClientWrapperCreatePresent
0x1800144d5  test    al, al
0x1800144d7  jz      short loc_1800144F1
0x1800144d9  call    cs:__imp_GetThreadDpiAwarenessContext
0x1800144df  mov     rcx, rax
0x1800144e2  call    cs:__imp_GetAwarenessFromDpiAwarenessContext
0x1800144e8  cmp     eax, 2
0x1800144eb  jnz     loc_180014639
0x1800144f1  xorps   xmm6, xmm6
0x1800144f4  ucomiss xmm6, cs:__real@00000000
0x1800144fb  jp      short loc_180014534
0x1800144fd  jnz     short loc_180014534
0x1800144ff  movss   xmm6, cs:__real@3f800000
0x180014507  lea     rdx, [rsp+58h+arg_0]
0x18001450c  mov     rcx, rbp
0x18001450f  mov     [rsp+58h+arg_0], 64h ; 'd'
0x180014517  call    cs:__imp_GetScaleFactorForWindow
0x18001451d  mov     eax, [rsp+58h+arg_0]
0x180014521  test    eax, eax
0x180014523  jz      short loc_180014534
0x180014525  movd    xmm6, eax
0x180014529  cvtdq2ps xmm6, xmm6
0x18001452c  divss   xmm6, cs:__real@42c80000
0x180014534  movaps  xmm0, xmm6
0x180014537  divss   xmm0, dword ptr [rsi+0B7Ch]
0x18001453f  divss   xmm6, dword ptr [rsi+0B80h]
0x180014547  mulss   xmm0, dword ptr [rbx+8]
0x18001454c  mulss   xmm6, dword ptr [rbx+0Ch]
0x180014551  movss   dword ptr [rbx+8], xmm0
0x180014556  movss   dword ptr [rbx+0Ch], xmm6
0x18001455b  mov     rsi, [rsi+0D88h]
0x180014562  call    IsTextInputClientWrapperCreatePresent
0x180014567  test    al, al
0x180014569  jz      short loc_180014583
0x18001456b  call    cs:__imp_GetThreadDpiAwarenessContext
0x180014571  mov     rcx, rax
0x180014574  call    cs:__imp_GetAwarenessFromDpiAwarenessContext
0x18001457a  cmp     eax, 2
0x18001457d  jnz     loc_18001460E
0x180014583  xorps   xmm2, xmm2
0x180014586  ucomiss xmm2, cs:__real@00000000
0x18001458d  jp      short loc_1800145C3
0x18001458f  jnz     short loc_1800145C3
0x180014591  mov     [rsp+58h+arg_0], 64h ; 'd'
0x180014599  test    rsi, rsi
0x18001459c  jz      short loc_180014601
0x18001459e  lea     rdx, [rsp+58h+arg_0]
0x1800145a3  mov     rcx, rsi
0x1800145a6  call    cs:__imp_GetScaleFactorForWindow
0x1800145ac  test    eax, eax
0x1800145ae  js      short loc_180014601
0x1800145b0  mov     eax, [rsp+58h+arg_0]
0x1800145b4  movd    xmm2, eax
0x1800145b8  cvtdq2ps xmm2, xmm2
0x1800145bb  divss   xmm2, cs:__real@42c80000
0x1800145c3  movups  xmm0, xmmword ptr [rbx]
0x1800145c6  shufps  xmm2, xmm2, 0
0x1800145ca  divps   xmm0, xmm2
0x1800145cd  movups  xmmword ptr [rdi], xmm0
0x1800145d0  mov     rbx, [rsp+58h+arg_8]
0x1800145d5  xor     eax, eax
0x1800145d7  mov     rbp, [rsp+58h+arg_10]
0x1800145dc  movaps  xmm6, [rsp+58h+var_28]
0x1800145e1  add     rsp, 40h
0x1800145e5  pop     r13
0x1800145e7  pop     rdi
0x1800145e8  pop     rsi
0x1800145e9  retn
0x1800145ea  mov     rcx, [rsp+58h]; this
0x1800145ef  mov     r8, rbp; unsigned int
0x1800145f2  mov     edx, 22D7h; void *
0x1800145f7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800145fc  jmp     loc_1800144C9
0x180014601  mov     ecx, 1
0x180014606  call    cs:__imp_GetScaleFactorForDevice
0x18001460c  jmp     short loc_1800145B4
0x18001460e  call    cs:__imp_GetDpiForSystem
0x180014614  mov     edx, 64h ; 'd'; nNumerator
0x180014619  mov     ecx, eax; nNumber
0x18001461b  lea     r8d, [rdx-4]; nDenominator
0x18001461f  call    cs:__imp_MulDiv
0x180014625  movd    xmm2, eax
0x180014629  cvtdq2ps xmm2, xmm2
0x18001462c  divss   xmm2, cs:__real@42c80000
0x180014634  jmp     loc_180014586
0x180014639  call    cs:__imp_GetDpiForSystem
0x18001463f  mov     edx, 64h ; 'd'; nNumerator
0x180014644  mov     ecx, eax; nNumber
0x180014646  lea     r8d, [rdx-4]; nDenominator
0x18001464a  call    cs:__imp_MulDiv
0x180014650  movd    xmm6, eax
0x180014654  cvtdq2ps xmm6, xmm6
0x180014657  divss   xmm6, cs:__real@42c80000
0x18001465f  jmp     loc_1800144F4
0x180014664  movaps  xmm0, xmmword ptr [rbx]
0x180014667  movdqu  xmmword ptr [rdi], xmm0
0x18001466b  jmp     loc_1800145D0
0x180014670  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneCoreTransforms@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneCoreTransforms@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms> `wil::Feature<__WilFeatureTraits_Feature_OneCoreTransforms>::GetImpl(void)'::`2'::impl
0x180014677  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_OneCoreTransforms@@@details@wil@@QEAA?AW4Variant_OneCoreTransforms@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms>::__private_GetVariant(wil::VariantReportingKind,bool)
0x18001467c  cmp     al, 1
0x18001467e  jnz     loc_180014426
0x180014684  jmp     loc_180014428
0x180014689  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OneCoreTransforms@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OneCoreTransforms@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms> `wil::Feature<__WilFeatureTraits_Feature_OneCoreTransforms>::GetImpl(void)'::`2'::impl
0x180014690  call    ?__private_GetVariant@?$FeatureImpl@U__WilFeatureTraits_Feature_OneCoreTransforms@@@details@wil@@QEAA?AW4Variant_OneCoreTransforms@@W4VariantReportingKind@3@_N@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OneCoreTransforms>::__private_GetVariant(wil::VariantReportingKind,bool)
0x180014695  cmp     al, 1
0x180014697  jnz     loc_18001448A
0x18001469d  jmp     loc_18001448C
```
