# CInputTransform::LegacyTransforms_InferTransformFromWindow(HWND__ *,CInputTransform::Inference)

- ea: `0x18001edd0`
- end: `0x18001f1ac`
- name: `?LegacyTransforms_InferTransformFromWindow@CInputTransform@@QEAAXPEAUHWND__@@W4Inference@1@@Z`
- size: `988`
- prototype: `void __high(HWND, enum CInputTransform::Inference)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e7f0`
- `0x180031f04`
- `0x180076330`
- `0x1800824a0`

## callees

- `0x18001edd0`
- `0x18006040c`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001f102`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001f149`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001f102`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18001f149`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x18001ef3e`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x18001f0b9`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x18001ef3e`
- `api-ms-win-shcore-scaling-l1-1-1!__imp_GetScaleFactorForWindow` at `0x18001f0b9`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x18001f0e4`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x18001f12e`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x18001f0e4`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x18001f12e`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x18001ef18`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x18001f097`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x18001ef18`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetAwarenessFromDpiAwarenessContext` at `0x18001f097`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18001ef0f`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18001f08e`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18001ef0f`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetThreadDpiAwarenessContext` at `0x18001f08e`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x18001f0ef`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x18001f136`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x18001f0ef`
- `ext-ms-win-rtcore-ntuser-dpi-l1-2-0!GetDpiForSystem` at `0x18001f136`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x18001ee6a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClientRect` at `0x18001ee6a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18001eea2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18001eec3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18001eea2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18001eec3`

## pseudocode

```c
int __fastcall CInputTransform::LegacyTransforms_InferTransformFromWindow(__int64 a1, HWND a2, int a3)
{
  int result; // eax
  float v6; // xmm9_4
  float left; // xmm11_4
  float top; // xmm10_4
  float v9; // xmm6_4
  float v10; // xmm7_4
  __int64 ThreadDpiAwarenessContext; // rax
  int ScaleFactorForDevice; // eax
  float v13; // xmm0_4
  float v14; // xmm7_4
  float v15; // xmm4_4
  float v16; // xmm11_4
  float v17; // xmm10_4
  float v18; // xmm6_4
  float x; // xmm2_4
  float y; // xmm1_4
  float v21; // xmm3_4
  float v22; // xmm0_4
  float v23; // xmm2_4
  float v24; // xmm1_4
  __int64 v25; // rax
  float v26; // xmm1_4
  int DpiForSystem; // eax
  int v28; // eax
  int v29; // [rsp+28h] [rbp-49h] BYREF
  struct tagPOINT Points; // [rsp+30h] [rbp-41h] BYREF
  struct tagPOINT v31; // [rsp+38h] [rbp-39h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-31h] BYREF

  *(_BYTE *)(a1 + 64) = 1;
  *(_DWORD *)(a1 + 60) = 1065353216;
  *(_QWORD *)(a1 + 40) = 1065353216;
  *(_QWORD *)(a1 + 20) = 1065353216;
  *(_QWORD *)a1 = 1065353216;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 28) = 0;
  *(_DWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 36) = 0;
  *(_QWORD *)(a1 + 52) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  if ( a3 == 1 )
  {
    Rect = 0;
    result = GetClientRect(a2, &Rect);
    v6 = FLOAT_1_0;
    if ( result )
    {
      Points.x = Rect.left;
      Points.y = Rect.top;
      MapWindowPoints(a2, 0, &Points, 1u);
      v31 = *(struct tagPOINT *)&Rect.right;
      MapWindowPoints(a2, 0, &v31, 1u);
      left = (float)Rect.left;
      top = (float)Rect.top;
      v9 = (float)(Rect.bottom - Rect.top);
      v10 = (float)(Rect.right - Rect.left);
      if ( !(unsigned __int8)IsTextInputClientWrapperCreatePresent()
        || (ThreadDpiAwarenessContext = GetThreadDpiAwarenessContext(),
            (unsigned int)GetAwarenessFromDpiAwarenessContext(ThreadDpiAwarenessContext) == 2)
        || (DpiForSystem = GetDpiForSystem(), v13 = (float)MulDiv(DpiForSystem, 100, 96) / 100.0, v13 == 0.0) )
      {
        v29 = 100;
        if ( a2 && (int)GetScaleFactorForWindow(a2, &v29) >= 0 )
          ScaleFactorForDevice = v29;
        else
          ScaleFactorForDevice = GetScaleFactorForDevice(1);
        v13 = (float)ScaleFactorForDevice / 100.0;
      }
      v14 = v10 / v13;
      v15 = (float)(v31.x - Points.x);
      result = v31.y - Points.y;
      v16 = left / v13;
      v17 = top / v13;
      v18 = v9 / v13;
      x = (float)Points.x;
      y = (float)Points.y;
      v21 = (float)(v31.y - Points.y);
      if ( v14 != 0.0 )
      {
        v22 = v15 / v14;
LABEL_11:
        *(float *)a1 = v22;
        if ( v18 != 0.0 )
          v6 = v21 / v18;
        *(float *)(a1 + 20) = v6;
        if ( v14 == 0.0 )
          v23 = x - v16;
        else
          v23 = (float)((float)((float)(v16 + v14) * x) - (float)((float)(x + v15) * v16)) / v14;
        *(float *)(a1 + 48) = v23;
        if ( v18 == 0.0 )
          v24 = y - v17;
        else
          v24 = (float)((float)((float)(v17 + v18) * y) - (float)((float)(y + v21) * v17)) / v18;
        *(float *)(a1 + 52) = v24;
        return result;
      }
    }
    else
    {
      v16 = 0.0;
      v17 = 0.0;
      v14 = 0.0;
      v18 = 0.0;
      x = 0.0;
      y = 0.0;
      v15 = 0.0;
      v21 = 0.0;
    }
    v22 = FLOAT_1_0;
    goto LABEL_11;
  }
  if ( !(unsigned __int8)IsTextInputClientWrapperCreatePresent()
    || (v25 = GetThreadDpiAwarenessContext(), (unsigned int)GetAwarenessFromDpiAwarenessContext(v25) == 2)
    || (v28 = GetDpiForSystem(), result = MulDiv(v28, 100, 96), v26 = (float)result / 100.0, v26 == 0.0) )
  {
    v29 = 100;
    if ( a2 && (int)GetScaleFactorForWindow(a2, &v29) >= 0 )
      result = v29;
    else
      result = GetScaleFactorForDevice(1);
    v26 = (float)result / 100.0;
  }
  *(float *)a1 = v26;
  *(float *)(a1 + 20) = v26;
  return result;
}

```

## disassembly

```asm
0x18001edd0  mov     r11, rsp
0x18001edd3  mov     [r11+18h], rbx
0x18001edd7  mov     [r11+20h], rdi
0x18001eddb  push    rbp
0x18001eddc  lea     rbp, [r11-5Fh]
0x18001ede0  sub     rsp, 0C0h
0x18001ede7  movaps  xmmword ptr [r11-18h], xmm6
0x18001edec  mov     rax, cs:__security_cookie
0x18001edf3  xor     rax, rsp
0x18001edf6  mov     qword ptr [rbp+57h+var_78], rax
0x18001edfa  xor     eax, eax
0x18001edfc  mov     byte ptr [rcx+40h], 1
0x18001ee00  mov     dword ptr [rcx+3Ch], 3F800000h
0x18001ee07  mov     rdi, rdx
0x18001ee0a  mov     qword ptr [rcx+28h], 3F800000h
0x18001ee12  mov     rbx, rcx
0x18001ee15  mov     qword ptr [rcx+14h], 3F800000h
0x18001ee1d  mov     qword ptr [rcx], 3F800000h
0x18001ee24  mov     [rcx+8], rax
0x18001ee28  mov     [rcx+1Ch], rax
0x18001ee2c  mov     [rcx+10h], eax
0x18001ee2f  mov     [rcx+24h], eax
0x18001ee32  mov     [rcx+34h], rax
0x18001ee36  mov     [rcx+30h], eax
0x18001ee39  cmp     r8d, 1
0x18001ee3d  jnz     loc_18001F07D
0x18001ee43  movaps  xmmword ptr [r11-28h], xmm7
0x18001ee48  lea     rdx, [rbp+57h+Rect]; lpRect
0x18001ee4c  movaps  xmmword ptr [r11-38h], xmm8
0x18001ee51  xorps   xmm0, xmm0
0x18001ee54  movaps  xmmword ptr [r11-48h], xmm9
0x18001ee59  mov     rcx, rdi; hWnd
0x18001ee5c  movaps  xmmword ptr [r11-58h], xmm10
0x18001ee61  movaps  xmmword ptr [r11-68h], xmm11
0x18001ee66  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18001ee6a  call    cs:__imp_GetClientRect
0x18001ee70  movss   xmm9, cs:__real@3f800000
0x18001ee79  test    eax, eax
0x18001ee7b  jz      loc_18001F171
0x18001ee81  mov     eax, [rbp+57h+Rect.left]
0x18001ee84  lea     r8, [rbp+57h+Points]; lpPoints
0x18001ee88  mov     [rbp+57h+Points.x], eax
0x18001ee8b  mov     r9d, 1; cPoints
0x18001ee91  mov     eax, [rbp+57h+Rect.top]
0x18001ee94  xor     edx, edx; hWndTo
0x18001ee96  mov     rcx, rdi; hWndFrom
0x18001ee99  mov     [rbp+57h+Points.y], eax
0x18001ee9c  movaps  [rsp+0C0h+var_78+8], xmm12
0x18001eea2  call    cs:__imp_MapWindowPoints
0x18001eea8  mov     eax, [rbp+57h+Rect.right]
0x18001eeab  lea     r8, [rbp+57h+var_90]; lpPoints
0x18001eeaf  mov     [rbp+57h+var_90.x], eax
0x18001eeb2  mov     r9d, 1; cPoints
0x18001eeb8  mov     eax, [rbp+57h+Rect.bottom]
0x18001eebb  xor     edx, edx; hWndTo
0x18001eebd  mov     rcx, rdi; hWndFrom
0x18001eec0  mov     [rbp+57h+var_90.y], eax
0x18001eec3  call    cs:__imp_MapWindowPoints
0x18001eec9  mov     ecx, [rbp+57h+Rect.left]
0x18001eecc  mov     edx, [rbp+57h+Rect.top]
0x18001eecf  mov     eax, [rbp+57h+Rect.right]
0x18001eed2  sub     eax, ecx
0x18001eed4  movd    xmm11, ecx
0x18001eed9  movd    xmm10, edx
0x18001eede  cvtdq2ps xmm11, xmm11
0x18001eee2  movd    xmm7, eax
0x18001eee6  mov     eax, [rbp+57h+Rect.bottom]
0x18001eee9  sub     eax, edx
0x18001eeeb  cvtdq2ps xmm10, xmm10
0x18001eeef  movd    xmm6, eax
0x18001eef3  cvtdq2ps xmm6, xmm6
0x18001eef6  cvtdq2ps xmm7, xmm7
0x18001eef9  call    IsTextInputClientWrapperCreatePresent
0x18001eefe  movss   xmm12, cs:__real@42c80000
0x18001ef07  xorps   xmm8, xmm8
0x18001ef0b  test    al, al
0x18001ef0d  jz      short loc_18001EF27
0x18001ef0f  call    cs:__imp_GetThreadDpiAwarenessContext
0x18001ef15  mov     rcx, rax
0x18001ef18  call    cs:__imp_GetAwarenessFromDpiAwarenessContext
0x18001ef1e  cmp     eax, 2
0x18001ef21  jnz     loc_18001F0EF
0x18001ef27  mov     [rbp+57h+var_A0], 64h ; 'd'
0x18001ef2e  test    rdi, rdi
0x18001ef31  jz      loc_18001F0DF
0x18001ef37  lea     rdx, [rbp+57h+var_A0]
0x18001ef3b  mov     rcx, rdi
0x18001ef3e  call    cs:__imp_GetScaleFactorForWindow
0x18001ef44  test    eax, eax
0x18001ef46  js      loc_18001F0DF
0x18001ef4c  mov     eax, [rbp+57h+var_A0]
0x18001ef4f  movd    xmm0, eax
0x18001ef53  cvtdq2ps xmm0, xmm0
0x18001ef56  divss   xmm0, xmm12
0x18001ef5b  mov     ecx, [rbp+57h+Points.x]
0x18001ef5e  xorps   xmm4, xmm4
0x18001ef61  mov     edx, [rbp+57h+Points.y]
0x18001ef64  xorps   xmm2, xmm2
0x18001ef67  mov     eax, [rbp+57h+var_90.x]
0x18001ef6a  xorps   xmm1, xmm1
0x18001ef6d  movaps  xmm12, [rsp+0C0h+var_78+8]
0x18001ef73  sub     eax, ecx
0x18001ef75  divss   xmm7, xmm0
0x18001ef79  cvtsi2ss xmm4, eax
0x18001ef7d  mov     eax, [rbp+57h+var_90.y]
0x18001ef80  sub     eax, edx
0x18001ef82  xorps   xmm3, xmm3
0x18001ef85  ucomiss xmm7, xmm8
0x18001ef89  divss   xmm11, xmm0
0x18001ef8e  divss   xmm10, xmm0
0x18001ef93  divss   xmm6, xmm0
0x18001ef97  cvtsi2ss xmm2, ecx
0x18001ef9b  cvtsi2ss xmm1, edx
0x18001ef9f  cvtsi2ss xmm3, eax
0x18001efa3  jp      short loc_18001EFAB
0x18001efa5  jz      loc_18001F18F
0x18001efab  movaps  xmm0, xmm4
0x18001efae  divss   xmm0, xmm7
0x18001efb2  ucomiss xmm6, xmm8
0x18001efb6  movss   dword ptr [rbx], xmm0
0x18001efba  jp      short loc_18001EFBE
0x18001efbc  jz      short loc_18001EFC9
0x18001efbe  movaps  xmm0, xmm3
0x18001efc1  divss   xmm0, xmm6
0x18001efc5  movaps  xmm9, xmm0
0x18001efc9  ucomiss xmm7, xmm8
0x18001efcd  movss   dword ptr [rbx+14h], xmm9
0x18001efd3  movaps  xmm9, [rsp+0C0h+var_48+8]
0x18001efdc  jp      short loc_18001EFE4
0x18001efde  jz      loc_18001F198
0x18001efe4  movaps  xmm0, xmm11
0x18001efe8  addss   xmm0, xmm7
0x18001efec  mulss   xmm0, xmm2
0x18001eff0  addss   xmm2, xmm4
0x18001eff4  mulss   xmm2, xmm11
0x18001eff9  subss   xmm0, xmm2
0x18001effd  divss   xmm0, xmm7
0x18001f001  movaps  xmm2, xmm0
0x18001f004  movaps  xmm11, [rsp+0C0h+var_68+8]
0x18001f00a  movaps  xmm7, [rsp+0C0h+var_28+8]
0x18001f012  ucomiss xmm6, xmm8
0x18001f016  movaps  xmm8, [rsp+0C0h+var_38+8]
0x18001f01f  movss   dword ptr [rbx+30h], xmm2
0x18001f024  jp      short loc_18001F02C
0x18001f026  jz      loc_18001F1A2
0x18001f02c  movaps  xmm0, xmm10
0x18001f030  addss   xmm0, xmm6
0x18001f034  mulss   xmm0, xmm1
0x18001f038  addss   xmm1, xmm3
0x18001f03c  mulss   xmm1, xmm10
0x18001f041  subss   xmm0, xmm1
0x18001f045  divss   xmm0, xmm6
0x18001f049  movaps  xmm1, xmm0
0x18001f04c  movaps  xmm10, [rsp+0C0h+var_58+8]
0x18001f052  movss   dword ptr [rbx+34h], xmm1
0x18001f057  mov     rcx, qword ptr [rbp+57h+var_78]
0x18001f05b  xor     rcx, rsp; StackCookie
0x18001f05e  call    __security_check_cookie
0x18001f063  lea     r11, [rsp+0C0h+var_s0]
0x18001f06b  mov     rbx, [r11+20h]
0x18001f06f  mov     rdi, [r11+28h]
0x18001f073  movaps  xmm6, xmmword ptr [r11-10h]
0x18001f078  mov     rsp, r11
0x18001f07b  pop     rbp
0x18001f07c  retn
0x18001f07d  call    IsTextInputClientWrapperCreatePresent
0x18001f082  movss   xmm6, cs:__real@42c80000
0x18001f08a  test    al, al
0x18001f08c  jz      short loc_18001F0A6
0x18001f08e  call    cs:__imp_GetThreadDpiAwarenessContext
0x18001f094  mov     rcx, rax
0x18001f097  call    cs:__imp_GetAwarenessFromDpiAwarenessContext
0x18001f09d  cmp     eax, 2
0x18001f0a0  jnz     loc_18001F136
0x18001f0a6  mov     [rbp+57h+var_A0], 64h ; 'd'
0x18001f0ad  test    rdi, rdi
0x18001f0b0  jz      short loc_18001F129
0x18001f0b2  lea     rdx, [rbp+57h+var_A0]
0x18001f0b6  mov     rcx, rdi
0x18001f0b9  call    cs:__imp_GetScaleFactorForWindow
0x18001f0bf  test    eax, eax
0x18001f0c1  js      short loc_18001F129
0x18001f0c3  mov     eax, [rbp+57h+var_A0]
0x18001f0c6  movd    xmm1, eax
0x18001f0ca  cvtdq2ps xmm1, xmm1
0x18001f0cd  divss   xmm1, xmm6
0x18001f0d1  movss   dword ptr [rbx], xmm1
0x18001f0d5  movss   dword ptr [rbx+14h], xmm1
0x18001f0da  jmp     loc_18001F057
0x18001f0df  mov     ecx, 1
0x18001f0e4  call    cs:__imp_GetScaleFactorForDevice
0x18001f0ea  jmp     loc_18001EF4F
0x18001f0ef  call    cs:__imp_GetDpiForSystem
0x18001f0f5  mov     edx, 64h ; 'd'; nNumerator
0x18001f0fa  mov     r8d, 60h ; '`'; nDenominator
0x18001f100  mov     ecx, eax; nNumber
0x18001f102  call    cs:__imp_MulDiv
0x18001f108  movd    xmm0, eax
0x18001f10c  cvtdq2ps xmm0, xmm0
0x18001f10f  divss   xmm0, xmm12
0x18001f114  ucomiss xmm0, xmm8
0x18001f118  jp      loc_18001EF5B
0x18001f11e  jz      loc_18001EF27
0x18001f124  jmp     loc_18001EF5B
0x18001f129  mov     ecx, 1
0x18001f12e  call    cs:__imp_GetScaleFactorForDevice
0x18001f134  jmp     short loc_18001F0C6
0x18001f136  call    cs:__imp_GetDpiForSystem
0x18001f13c  mov     edx, 64h ; 'd'; nNumerator
0x18001f141  mov     r8d, 60h ; '`'; nDenominator
0x18001f147  mov     ecx, eax; nNumber
0x18001f149  call    cs:__imp_MulDiv
0x18001f14f  xorps   xmm0, xmm0
0x18001f152  movd    xmm1, eax
0x18001f156  cvtdq2ps xmm1, xmm1
0x18001f159  divss   xmm1, xmm6
0x18001f15d  ucomiss xmm1, xmm0
0x18001f160  jp      loc_18001F0D1
0x18001f166  jz      loc_18001F0A6
0x18001f16c  jmp     loc_18001F0D1
0x18001f171  xorps   xmm8, xmm8
0x18001f175  xorps   xmm11, xmm11
0x18001f179  xorps   xmm10, xmm10
0x18001f17d  xorps   xmm7, xmm7
0x18001f180  xorps   xmm6, xmm6
0x18001f183  xorps   xmm2, xmm2
0x18001f186  xorps   xmm1, xmm1
0x18001f189  xorps   xmm4, xmm4
0x18001f18c  xorps   xmm3, xmm3
0x18001f18f  movaps  xmm0, xmm9
0x18001f193  jmp     loc_18001EFB2
0x18001f198  subss   xmm2, xmm11
0x18001f19d  jmp     loc_18001F004
0x18001f1a2  subss   xmm1, xmm10
0x18001f1a7  jmp     loc_18001F04C
```
