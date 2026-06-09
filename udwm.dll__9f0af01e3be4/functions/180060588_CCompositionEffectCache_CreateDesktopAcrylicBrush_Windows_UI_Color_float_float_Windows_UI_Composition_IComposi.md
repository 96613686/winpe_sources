# CCompositionEffectCache::CreateDesktopAcrylicBrush(Windows::UI::Color,float,float,Windows::UI::Composition::ICompositionBrush * *)

- ea: `0x180060588`
- end: `0x180060674`
- name: `?CreateDesktopAcrylicBrush@CCompositionEffectCache@@CAJUColor@UI@Windows@@MMPEAPEAUICompositionBrush@Composition@34@@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180060080`

## callees

- `0x180060588`
- `0x180081a68`
- `0x180095130`

## import_xrefs

- `wuceffects!CreateAcrylicBrush` at `0x180060636`
- `wuceffects!CreateAcrylicBrush` at `0x180060636`

## string_xrefs

- `0x180060647`: `clientcore\windows\dwm\udwm\compositioneffectcache.cpp`

## pseudocode

```c
__int64 __fastcall CCompositionEffectCache::CreateDesktopAcrylicBrush(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  CDesktopManager *v4; // rax
  __int64 v5; // r9
  int AcrylicBrush; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-38h]
  float v10[4]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = CDesktopManager::s_pDesktopManagerInstance;
  *a4 = 0;
  v9 = (int)a4;
  v5 = *(_QWORD *)(*((_QWORD *)v4 + 6) + 40LL);
  v10[0] = (float)BYTE1(a1) / 255.0;
  v10[2] = (float)HIBYTE(a1) / 255.0;
  v10[1] = (float)BYTE2(a1) / 255.0;
  v10[3] = (float)(unsigned __int8)a1 / 255.0;
  AcrylicBrush = CreateAcrylicBrush(v5, v10);
  v7 = AcrylicBrush;
  if ( AcrylicBrush >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD8,
    (unsigned int)"clientcore\\windows\\dwm\\udwm\\compositioneffectcache.cpp",
    (const char *)(unsigned int)AcrylicBrush,
    v9);
  return v7;
}

```

## disassembly

```asm
0x180060588  push    rbx
0x18006058a  sub     rsp, 50h
0x18006058e  mov     rax, cs:__security_cookie
0x180060595  xor     rax, rsp
0x180060598  mov     [rsp+58h+var_18], rax
0x18006059d  movss   xmm4, cs:__real@437f0000
0x1800605a5  mov     r8d, ecx
0x1800605a8  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800605af  mov     r10d, ecx
0x1800605b2  mov     qword ptr [r9], 0
0x1800605b9  mov     rbx, r9
0x1800605bc  shr     r8d, 8
0x1800605c0  mov     r11d, ecx
0x1800605c3  shr     r10d, 10h
0x1800605c7  movaps  xmm3, xmm2
0x1800605ca  mov     rdx, [rax+30h]
0x1800605ce  movaps  xmm2, xmm1
0x1800605d1  movzx   eax, r8b
0x1800605d5  shr     r11d, 18h
0x1800605d9  mov     qword ptr [rsp+58h+var_38], rbx; int
0x1800605de  mov     r9, [rdx+28h]
0x1800605e2  lea     rdx, [rsp+58h+var_28]
0x1800605e7  movd    xmm0, eax
0x1800605eb  cvtdq2ps xmm0, xmm0
0x1800605ee  movzx   eax, r10b
0x1800605f2  movd    xmm1, r11d
0x1800605f7  divss   xmm0, xmm4
0x1800605fb  cvtdq2ps xmm1, xmm1
0x1800605fe  movss   [rsp+58h+var_28], xmm0
0x180060604  movd    xmm0, eax
0x180060608  cvtdq2ps xmm0, xmm0
0x18006060b  movzx   eax, cl
0x18006060e  mov     rcx, r9
0x180060611  divss   xmm1, xmm4
0x180060615  divss   xmm0, xmm4
0x180060619  movss   [rsp+58h+var_20], xmm1
0x18006061f  movss   [rsp+58h+var_24], xmm0
0x180060625  movd    xmm0, eax
0x180060629  cvtdq2ps xmm0, xmm0
0x18006062c  divss   xmm0, xmm4
0x180060630  movss   [rsp+58h+var_1C], xmm0
0x180060636  call    cs:__imp_CreateAcrylicBrush
0x18006063c  mov     ebx, eax
0x18006063e  test    eax, eax
0x180060640  jns     short loc_18006065F
0x180060642  mov     rcx, [rsp+58h]; this
0x180060647  lea     r8, aClientcoreWind_90; "clientcore\\windows\\dwm\\udwm\\composi"...
0x18006064e  mov     r9d, eax; char *
0x180060651  mov     edx, 0D8h; void *
0x180060656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006065b  mov     eax, ebx
0x18006065d  jmp     short loc_180060661
0x18006065f  xor     eax, eax
0x180060661  mov     rcx, [rsp+58h+var_18]
0x180060666  xor     rcx, rsp; StackCookie
0x180060669  call    __security_check_cookie
0x18006066e  add     rsp, 50h
0x180060672  pop     rbx
0x180060673  retn
```
