# Windows::UI::Core::WindowServer::OnVisibleBoundsChangeEvent(void)

- ea: `0x180012fb0`
- end: `0x18001382a`
- name: `?OnVisibleBoundsChangeEvent@WindowServer@Core@UI@Windows@@UEAAJXZ`
- size: `2170`
- prototype: `__int64 __fastcall(Windows::UI::Core::WindowServer *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180012534`
- `0x180012fb0`
- `0x180014754`
- `0x180017a60`
- `0x180017a90`
- `0x18001bb4c`
- `0x18001cd84`
- `0x18004e5cc`
- `0x180056a14`
- `0x180058584`
- `0x1800c731e`
- `0x1800c737e`
- `0x1800c7396`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013061`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013061`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001303f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001303f`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180013013`
- `api-ms-win-rtcore-ntuser-private-l1-1-7!IsOneCoreTransformMode` at `0x180013013`

## string_xrefs

- `0x18001307b`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x1800132c6`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x18001337e`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x18001347d`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x1800135af`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x1800137fa`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Core::WindowServer::OnVisibleBoundsChangeEvent(Windows::UI::Core::WindowServer *this)
{
  char *v2; // r14
  int v3; // edi
  __int64 v4; // rbx
  RTL_SRWLOCK *v5; // rsi
  volatile int *v6; // rdx
  __int64 v7; // r8
  int v9; // eax
  float v10; // xmm12_4
  float v11; // xmm14_4
  float v12; // xmm15_4
  float v13; // xmm13_4
  float v14; // xmm11_4
  float v15; // xmm10_4
  float v16; // xmm0_4
  float v17; // xmm9_4
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, Windows::UI::Core::WindowServer ***); // rbx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64 **); // rbx
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rdi
  __int64 (__fastcall *v29)(__int64, Windows::UI::Core::WindowServer ***, __int64, __int64 *); // rbx
  int v30; // eax
  __int64 v31; // rdx
  float v32; // xmm6_4
  float v33; // xmm7_4
  float v34; // xmm0_4
  float v35; // xmm12_4
  float v36; // xmm13_4
  float v37; // xmm3_4
  float v38; // xmm1_4
  float v39; // xmm5_4
  float v40; // xmm4_4
  int v41; // eax
  __int64 v42; // rdx
  int v43; // [rsp+28h] [rbp-E0h]
  __int64 *v44; // [rsp+38h] [rbp-D0h] BYREF
  Windows::UI::Core::WindowServer **v45; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v46; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B8h] BYREF
  float v48; // [rsp+58h] [rbp-B0h]
  int v49; // [rsp+5Ch] [rbp-ACh]
  int v50; // [rsp+60h] [rbp-A8h]
  int v51; // [rsp+64h] [rbp-A4h]
  int v52; // [rsp+68h] [rbp-A0h]
  int v53; // [rsp+6Ch] [rbp-9Ch]
  int v54; // [rsp+70h] [rbp-98h]
  int v55; // [rsp+74h] [rbp-94h]
  int v56; // [rsp+78h] [rbp-90h]
  Windows::UI::Core::WindowServer **v57; // [rsp+88h] [rbp-80h] BYREF
  __int64 *v58; // [rsp+90h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]
  Windows::UI::Core::WindowServer *v60; // [rsp+168h] [rbp+60h] BYREF
  __int64 v61; // [rsp+170h] [rbp+68h] BYREF
  float v62; // [rsp+178h] [rbp+70h]
  float v63; // [rsp+180h] [rbp+78h]

  if ( !*((_DWORD *)this + 538) )
    Windows::UI::Core::WindowServer::OnLayoutBoundsChange(this);
  if ( (unsigned int)IsOneCoreTransformMode() || (v9 = *((_DWORD *)this + 688), (v9 & 2) == 0) )
  {
    v2 = (char *)this + 1632;
    v61 = 0;
    v60 = this;
    v3 = 0;
    v4 = 0;
    v5 = (RTL_SRWLOCK *)((char *)this + 1640);
    AcquireSRWLockExclusive(v5);
    if ( *(_QWORD *)v2 )
    {
      Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(*(_QWORD *)v2 + 12LL), v6);
      v4 = v7;
    }
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    if ( v4 )
    {
      v57 = &v60;
      v58 = &v61;
      v3 = Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_20f494fe0baa1532db1c50100a579e9f_,Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowOcclusionChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
             &v57,
             v4,
             v2);
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v4);
    }
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B00,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v3,
        v43);
      return (unsigned int)v3;
    }
  }
  else
  {
    *((_DWORD *)this + 688) = v9 & 0xFFFFFFFD;
    *(_OWORD *)((char *)this + 2876) = *(_OWORD *)((char *)this + 2776);
    *(_OWORD *)((char *)this + 2892) = *(_OWORD *)((char *)this + 2792);
    *(_OWORD *)((char *)this + 2908) = *(_OWORD *)((char *)this + 2808);
    *(_OWORD *)((char *)this + 2924) = *(_OWORD *)((char *)this + 2824);
    *(_OWORD *)((char *)this + 2940) = *(_OWORD *)((char *)this + 2840);
    *(_OWORD *)((char *)this + 2956) = *(_OWORD *)((char *)this + 2856);
    *((_DWORD *)this + 743) = *((_DWORD *)this + 718);
    v10 = *((float *)this + 719);
    v11 = *((float *)this + 720);
    v49 = *((_DWORD *)this + 721);
    v50 = *((_DWORD *)this + 722);
    v12 = *((float *)this + 723);
    v13 = *((float *)this + 724);
    v51 = *((_DWORD *)this + 725);
    v52 = *((_DWORD *)this + 726);
    v62 = *((float *)this + 727);
    LODWORD(v61) = *((_DWORD *)this + 728);
    v53 = *((_DWORD *)this + 729);
    v54 = *((_DWORD *)this + 730);
    v48 = *((float *)this + 731);
    v63 = *((float *)this + 732);
    v55 = *((_DWORD *)this + 733);
    v56 = *((_DWORD *)this + 734);
    v14 = *((float *)this + 739);
    v15 = sqrtf_0((float)(v11 * v11) + (float)(v10 * v10));
    v16 = sqrtf_0((float)(v13 * v13) + (float)(v12 * v12));
    v17 = v16;
    if ( v15 == 0.0 )
      v15 = FLOAT_1_0;
    if ( v16 == 0.0 )
      v17 = FLOAT_1_0;
    v18 = Windows::UI::Core::WindowServer::InitializeGlobalCoreAppDCompDevice(this);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AA6,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v18,
        v43);
      return v19;
    }
    v20 = *((_QWORD *)this + 341);
    if ( v20 && *((_QWORD *)this + 340) )
    {
      if ( !*((_DWORD *)this + 745) )
      {
        v45 = 0;
        v21 = *(__int64 (__fastcall **)(__int64, Windows::UI::Core::WindowServer ***))(*(_QWORD *)v20 + 88LL);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v45);
        v22 = v21(v20, &v45);
        v19 = v22;
        if ( v22 < 0 )
        {
          v23 = 6831;
LABEL_28:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v23,
            (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
            (const char *)(unsigned int)v22,
            v43);
LABEL_51:
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v45);
          return v19;
        }
        v22 = (*((__int64 (__fastcall **)(Windows::UI::Core::WindowServer **))*v45 + 4))(v45);
        v19 = v22;
        if ( v22 < 0 )
        {
          v23 = 6832;
          goto LABEL_28;
        }
        v22 = (*((__int64 (__fastcall **)(Windows::UI::Core::WindowServer **))*v45 + 6))(v45);
        v19 = v22;
        if ( v22 < 0 )
        {
          v23 = 6833;
          goto LABEL_28;
        }
        v22 = (*((__int64 (__fastcall **)(Windows::UI::Core::WindowServer **))*v45 + 8))(v45);
        v19 = v22;
        if ( v22 < 0 )
        {
          v23 = 6834;
          goto LABEL_28;
        }
        v22 = (*((__int64 (__fastcall **)(Windows::UI::Core::WindowServer **))*v45 + 10))(v45);
        v19 = v22;
        if ( v22 < 0 )
        {
          v23 = 6835;
          goto LABEL_28;
        }
        v44 = 0;
        v24 = *((_QWORD *)this + 341);
        v25 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v24 + 96LL);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v44);
        v26 = v25(v24, &v44);
        v19 = v26;
        if ( v26 < 0 )
        {
          v27 = 6852;
LABEL_37:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
            (const char *)(unsigned int)v26,
            v43);
LABEL_50:
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v44);
          goto LABEL_51;
        }
        v26 = (*(__int64 (__fastcall **)(__int64 *))(*v44 + 32))(v44);
        v19 = v26;
        if ( v26 < 0 )
        {
          v27 = 6853;
          goto LABEL_37;
        }
        v26 = (*(__int64 (__fastcall **)(__int64 *))(*v44 + 48))(v44);
        v19 = v26;
        if ( v26 < 0 )
        {
          v27 = 6854;
          goto LABEL_37;
        }
        v26 = (*(__int64 (__fastcall **)(__int64 *))(*v44 + 64))(v44);
        v19 = v26;
        if ( v26 < 0 )
        {
          v27 = 6855;
          goto LABEL_37;
        }
        v46 = 0;
        v57 = v45;
        v58 = v44;
        v28 = *((_QWORD *)this + 341);
        v29 = *(__int64 (__fastcall **)(__int64, Windows::UI::Core::WindowServer ***, __int64, __int64 *))(*(_QWORD *)v28 + 120LL);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v46);
        v30 = v29(v28, &v57, 2, &v46);
        v19 = v30;
        if ( v30 < 0 )
        {
          v31 = 6860;
LABEL_49:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v31,
            (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
            (const char *)(unsigned int)v30,
            v43);
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v46);
          goto LABEL_50;
        }
        v30 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 340) + 56LL))(
                *((_QWORD *)this + 340),
                v46);
        v19 = v30;
        if ( v30 < 0 )
        {
          v31 = 6861;
          goto LABEL_49;
        }
        v30 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 341) + 24LL))(*((_QWORD *)this + 341));
        v19 = v30;
        if ( v30 < 0 )
        {
          v31 = 6862;
          goto LABEL_49;
        }
        v32 = (float)(v14 * 3.1415927) / 180.0;
        v33 = sinf_0(v32);
        v34 = cosf_0(v32);
        v35 = (float)(v10 / v15) * v34;
        v36 = (float)(v13 / v17) * v33;
        v37 = v33 * *(float *)&v61;
        v38 = v34 * v62;
        v39 = v63 * v33;
        v40 = v34 * v48;
        *((float *)this + 719) = v35 - (float)(v33 * v11);
        *((float *)this + 720) = v35 + (float)(v33 * v11);
        *((_DWORD *)this + 721) = v49;
        *((_DWORD *)this + 722) = v50;
        *((float *)this + 723) = (float)(v34 * v12) - v36;
        *((float *)this + 724) = v36 + (float)(v34 * v12);
        *((_DWORD *)this + 725) = v51;
        *((_DWORD *)this + 726) = v52;
        *((float *)this + 727) = v38 - v37;
        *((float *)this + 728) = v38 + v37;
        *((_DWORD *)this + 729) = v53;
        *((_DWORD *)this + 730) = v54;
        *((float *)this + 731) = v40 - v39;
        *((float *)this + 732) = v40 + v39;
        *((_DWORD *)this + 733) = v55;
        *((_DWORD *)this + 734) = v56;
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v46);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v44);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v45);
      }
      *((float *)this + 691) = v14;
      *((float *)this + 689) = v15;
      *((float *)this + 690) = v17;
    }
    v47 = 0;
    v41 = Microsoft::WRL::Details::MakeAndInitialize<CComponentDisplayInformationChangedEventArgs,CComponentDisplayInformationChangedEventArgs,>(&v47);
    v19 = v41;
    if ( v41 < 0 )
    {
      v42 = 6899;
LABEL_63:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
        (const char *)(unsigned int)v41,
        v43);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v47);
      return v19;
    }
    v41 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::ComponentDisplayInformationChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::UI::Core::WindowServer *,CComponentDisplayInformationChangedEventArgs *>(
            (char *)this + 2040,
            this,
            v47);
    v19 = v41;
    if ( v41 < 0 )
    {
      v42 = 6900;
      goto LABEL_63;
    }
    LOBYTE(v60) = 0;
    v41 = (*(__int64 (__fastcall **)(__int64, Windows::UI::Core::WindowServer **))(*(_QWORD *)(v47 + 16) + 48LL))(
            v47 + 16,
            &v60);
    v19 = v41;
    if ( v41 < 0 )
    {
      v42 = 6904;
      goto LABEL_63;
    }
    if ( !(_BYTE)v60 )
    {
      v41 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<Windows::UI::Core::WindowServer *,std::nullptr_t>(
              (char *)this + 1632,
              this);
      v19 = v41;
      if ( v41 < 0 )
      {
        v42 = 6907;
        goto LABEL_63;
      }
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v47);
  }
  return 0;
}

```

## disassembly

```asm
0x180012fb0  mov     rax, rsp
0x180012fb3  push    rbp
0x180012fb4  push    rbx
0x180012fb5  push    rsi
0x180012fb6  push    rdi
0x180012fb7  push    r14
0x180012fb9  lea     rbp, [rax-58h]
0x180012fbd  sub     rsp, 130h
0x180012fc4  movaps  xmmword ptr [rax-38h], xmm6
0x180012fc8  movaps  xmmword ptr [rax-48h], xmm7
0x180012fcc  movaps  xmmword ptr [rax-58h], xmm8
0x180012fd1  movaps  xmmword ptr [rax-68h], xmm9
0x180012fd6  movaps  xmmword ptr [rax-78h], xmm10
0x180012fdb  movaps  xmmword ptr [rax-88h], xmm11
0x180012fe3  movaps  xmmword ptr [rax-98h], xmm12
0x180012feb  movaps  xmmword ptr [rax-0A8h], xmm13
0x180012ff3  movaps  xmmword ptr [rax-0B8h], xmm14
0x180012ffb  movaps  xmmword ptr [rax-0C8h], xmm15
0x180013003  mov     rsi, rcx
0x180013006  cmp     dword ptr [rcx+868h], 0
0x18001300d  jz      loc_180013106
0x180013013  call    cs:__imp_IsOneCoreTransformMode
0x180013019  test    eax, eax
0x18001301b  jz      loc_180013110
0x180013021  lea     r14, [rsi+660h]
0x180013028  mov     [rbp+50h+arg_8], 0
0x180013030  mov     [rbp+50h+arg_0], rsi
0x180013034  xor     edi, edi
0x180013036  xor     ebx, ebx
0x180013038  lea     rsi, [r14+8]
0x18001303c  mov     rcx, rsi; SRWLock
0x18001303f  call    cs:__imp_AcquireSRWLockExclusive
0x180013045  mov     r8, [r14]
0x180013048  test    r8, r8
0x18001304b  jz      short loc_180013059
0x18001304d  lea     rcx, [r8+0Ch]; this
0x180013051  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180013056  mov     rbx, r8
0x180013059  test    rsi, rsi
0x18001305c  jz      short loc_180013067
0x18001305e  mov     rcx, rsi; SRWLock
0x180013061  call    cs:__imp_ReleaseSRWLockExclusive
0x180013067  test    rbx, rbx
0x18001306a  jnz     short loc_1800130D8
0x18001306c  test    edi, edi
0x18001306e  jns     loc_180013823
0x180013074  mov     rcx, [rbp+58h]; this
0x180013078  mov     r9d, edi; char *
0x18001307b  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180013082  mov     edx, 1B00h; void *
0x180013087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001308c  mov     eax, edi
0x18001308e  lea     r11, [rsp+150h+var_20]
0x180013096  movaps  xmm6, xmmword ptr [r11-10h]
0x18001309b  movaps  xmm7, xmmword ptr [r11-20h]
0x1800130a0  movaps  xmm8, xmmword ptr [r11-30h]
0x1800130a5  movaps  xmm9, xmmword ptr [r11-40h]
0x1800130aa  movaps  xmm10, xmmword ptr [r11-50h]
0x1800130af  movaps  xmm11, xmmword ptr [r11-60h]
0x1800130b4  movaps  xmm12, xmmword ptr [r11-70h]
0x1800130b9  movaps  xmm13, xmmword ptr [r11-80h]
0x1800130be  movaps  xmm14, xmmword ptr [r11-90h]
0x1800130c6  movaps  xmm15, xmmword ptr [r11-0A0h]
0x1800130ce  mov     rsp, r11
0x1800130d1  pop     r14
0x1800130d3  pop     rdi
0x1800130d4  pop     rsi
0x1800130d5  pop     rbx
0x1800130d6  pop     rbp
0x1800130d7  retn
0x1800130d8  lea     rax, [rbp+50h+arg_0]
0x1800130dc  mov     [rbp+50h+var_D0], rax
0x1800130e0  lea     rax, [rbp+50h+arg_8]
0x1800130e4  mov     [rbp+50h+var_C8], rax
0x1800130e8  mov     r8, r14
0x1800130eb  mov     rdx, rbx
0x1800130ee  lea     rcx, [rbp+50h+var_D0]
0x1800130f2  call    ??$InvokeDelegates@V_lambda_20f494fe0baa1532db1c50100a579e9f_@@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowOcclusionChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_20f494fe0baa1532db1c50100a579e9f_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowOcclusionChangedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_20f494fe0baa1532db1c50100a579e9f_,Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowOcclusionChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_20f494fe0baa1532db1c50100a579e9f_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowOcclusionChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x1800130f7  mov     edi, eax
0x1800130f9  mov     rcx, rbx
0x1800130fc  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180013101  jmp     loc_18001306C
0x180013106  call    ?OnLayoutBoundsChange@WindowServer@Core@UI@Windows@@QEAAJXZ; Windows::UI::Core::WindowServer::OnLayoutBoundsChange(void)
0x18001310b  jmp     loc_180013013
0x180013110  mov     eax, [rsi+0AC0h]
0x180013116  test    al, 2
0x180013118  jz      loc_180013021
0x18001311e  and     eax, 0FFFFFFFDh
0x180013121  mov     [rsi+0AC0h], eax
0x180013127  movups  xmm0, xmmword ptr [rsi+0AD8h]
0x18001312e  movups  xmmword ptr [rsi+0B3Ch], xmm0
0x180013135  movups  xmm1, xmmword ptr [rsi+0AE8h]
0x18001313c  movups  xmmword ptr [rsi+0B4Ch], xmm1
0x180013143  movups  xmm0, xmmword ptr [rsi+0AF8h]
0x18001314a  movups  xmmword ptr [rsi+0B5Ch], xmm0
0x180013151  movups  xmm1, xmmword ptr [rsi+0B08h]
0x180013158  movups  xmmword ptr [rsi+0B6Ch], xmm1
0x18001315f  movups  xmm0, xmmword ptr [rsi+0B18h]
0x180013166  movups  xmmword ptr [rsi+0B7Ch], xmm0
0x18001316d  movups  xmm1, xmmword ptr [rsi+0B28h]
0x180013174  movups  xmmword ptr [rsi+0B8Ch], xmm1
0x18001317b  mov     eax, [rsi+0B38h]
0x180013181  mov     [rsi+0B9Ch], eax
0x180013187  movss   xmm12, dword ptr [rsi+0B3Ch]
0x180013190  movss   xmm14, dword ptr [rsi+0B40h]
0x180013199  movss   xmm0, dword ptr [rsi+0B44h]
0x1800131a1  movss   [rsp+150h+var_FC], xmm0
0x1800131a7  movss   xmm0, dword ptr [rsi+0B48h]
0x1800131af  movss   [rsp+150h+var_F8], xmm0
0x1800131b5  movss   xmm15, dword ptr [rsi+0B4Ch]
0x1800131be  movss   xmm13, dword ptr [rsi+0B50h]
0x1800131c7  movss   xmm0, dword ptr [rsi+0B54h]
0x1800131cf  movss   [rsp+150h+var_F4], xmm0
0x1800131d5  movss   xmm0, dword ptr [rsi+0B58h]
0x1800131dd  movss   [rsp+150h+var_F0], xmm0
0x1800131e3  movss   xmm0, dword ptr [rsi+0B5Ch]
0x1800131eb  movss   [rbp+50h+arg_10], xmm0
0x1800131f0  movss   xmm0, dword ptr [rsi+0B60h]
0x1800131f8  movss   dword ptr [rbp+50h+arg_8], xmm0
0x1800131fd  movss   xmm0, dword ptr [rsi+0B64h]
0x180013205  movss   [rsp+150h+var_EC], xmm0
0x18001320b  movss   xmm0, dword ptr [rsi+0B68h]
0x180013213  movss   [rsp+150h+var_E8], xmm0
0x180013219  movss   xmm0, dword ptr [rsi+0B6Ch]
0x180013221  movss   [rsp+150h+var_100], xmm0
0x180013227  movss   xmm0, dword ptr [rsi+0B70h]
0x18001322f  movss   [rbp+50h+arg_18], xmm0
0x180013234  movss   xmm0, dword ptr [rsi+0B74h]
0x18001323c  movss   [rsp+150h+var_E4], xmm0
0x180013242  movss   xmm0, dword ptr [rsi+0B78h]
0x18001324a  movss   [rsp+150h+var_E0], xmm0
0x180013250  movss   xmm11, dword ptr [rsi+0B8Ch]
0x180013259  movaps  xmm0, xmm14
0x18001325d  mulss   xmm0, xmm14
0x180013262  movaps  xmm1, xmm12
0x180013266  mulss   xmm1, xmm12
0x18001326b  addss   xmm0, xmm1; X
0x18001326f  call    sqrtf_0
0x180013274  movaps  xmm10, xmm0
0x180013278  movaps  xmm0, xmm13
0x18001327c  mulss   xmm0, xmm13
0x180013281  movaps  xmm1, xmm15
0x180013285  mulss   xmm1, xmm15
0x18001328a  addss   xmm0, xmm1; X
0x18001328e  call    sqrtf_0
0x180013293  movaps  xmm9, xmm0
0x180013297  xorps   xmm7, xmm7
0x18001329a  movss   xmm6, cs:__real@3f800000
0x1800132a2  ucomiss xmm10, xmm7
0x1800132a6  jp      short loc_1800132AA
0x1800132a8  jz      short loc_1800132DE
0x1800132aa  ucomiss xmm0, xmm7
0x1800132ad  jp      short loc_1800132B1
0x1800132af  jz      short loc_1800132E4
0x1800132b1  mov     rcx, rsi; this
0x1800132b4  call    ?InitializeGlobalCoreAppDCompDevice@WindowServer@Core@UI@Windows@@AEAAJXZ; Windows::UI::Core::WindowServer::InitializeGlobalCoreAppDCompDevice(void)
0x1800132b9  mov     ebx, eax
0x1800132bb  test    eax, eax
0x1800132bd  jns     short loc_1800132EA
0x1800132bf  mov     rcx, [rbp+58h]; this
0x1800132c3  mov     r9d, eax; char *
0x1800132c6  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800132cd  mov     edx, 1AA6h; void *
0x1800132d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800132d7  mov     eax, ebx
0x1800132d9  jmp     loc_18001308E
0x1800132de  movaps  xmm10, xmm6
0x1800132e2  jmp     short loc_1800132AA
0x1800132e4  movaps  xmm9, xmm6
0x1800132e8  jmp     short loc_1800132B1
0x1800132ea  mov     rdi, [rsi+0AA8h]
0x1800132f1  test    rdi, rdi
0x1800132f4  jz      loc_18001376C
0x1800132fa  cmp     qword ptr [rsi+0AA0h], 0
0x180013302  jz      loc_18001376C
0x180013308  cmp     dword ptr [rsi+0BA4h], 0
0x18001330f  jnz     loc_180013751
0x180013315  mov     [rsp+150h+var_118], 0
0x18001331e  mov     rax, [rdi]
0x180013321  mov     rbx, [rax+58h]
0x180013325  lea     rcx, [rsp+150h+var_118]
0x18001332a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18001332f  lea     rdx, [rsp+150h+var_118]
0x180013334  mov     rcx, rdi
0x180013337  mov     rax, rbx
0x18001333a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001333f  mov     ebx, eax
0x180013341  test    eax, eax
0x180013343  jns     short loc_18001334C
0x180013345  mov     edx, 1AAFh
0x18001334a  jmp     short loc_180013377
0x18001334c  mov     rcx, [rsp+150h+var_118]
0x180013351  mov     rax, [rcx]
0x180013354  movaps  xmm1, xmm6
0x180013357  divss   xmm1, xmm10
0x18001335c  mov     rax, [rax+20h]
0x180013360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013365  mov     ebx, eax
0x180013367  test    eax, eax
0x180013369  jns     short loc_18001338F
0x18001336b  mov     edx, 1AB0h
0x180013370  jmp     short loc_180013377
0x180013372  mov     edx, 1AB3h; void *
0x180013377  mov     rcx, [rbp+58h]; this
0x18001337b  mov     r9d, eax; char *
0x18001337e  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180013385  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001338a  jmp     loc_1800135D3
0x18001338f  mov     rcx, [rsp+150h+var_118]
0x180013394  mov     rax, [rcx]
0x180013397  divss   xmm6, xmm9
0x18001339c  movaps  xmm1, xmm6
0x18001339f  mov     rax, [rax+30h]
0x1800133a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133a8  mov     ebx, eax
0x1800133aa  test    eax, eax
0x1800133ac  jns     short loc_1800133B5
0x1800133ae  mov     edx, 1AB1h
0x1800133b3  jmp     short loc_180013377
0x1800133b5  mov     rcx, [rsp+150h+var_118]
0x1800133ba  mov     rax, [rcx]
0x1800133bd  xorps   xmm1, xmm1
0x1800133c0  mov     rax, [rax+40h]
0x1800133c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c9  mov     ebx, eax
0x1800133cb  test    eax, eax
0x1800133cd  jns     short loc_1800133D6
0x1800133cf  mov     edx, 1AB2h
0x1800133d4  jmp     short loc_180013377
0x1800133d6  mov     rcx, [rsp+150h+var_118]
0x1800133db  mov     rax, [rcx]
0x1800133de  xorps   xmm1, xmm1
0x1800133e1  mov     rax, [rax+50h]
0x1800133e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133ea  mov     ebx, eax
0x1800133ec  test    eax, eax
0x1800133ee  js      short loc_180013372
0x1800133f0  cvttss2si r8d, xmm11
0x1800133f5  mov     eax, 0B60B60B7h
0x1800133fa  imul    r8d
0x1800133fd  add     edx, r8d
0x180013400  sar     edx, 8
0x180013403  mov     eax, edx
0x180013405  shr     eax, 1Fh
0x180013408  add     edx, eax
0x18001340a  imul    eax, edx, 168h
0x180013410  sub     r8d, eax
0x180013413  mov     r9d, 0B98h
0x180013419  mov     eax, r9d
0x18001341c  lea     ecx, [r9+4]
0x180013420  mov     edx, 0B4h
0x180013425  cmp     r8d, edx
0x180013428  cmovnz  eax, ecx
0x18001342b  movss   xmm8, dword ptr [rax+rsi]
0x180013431  cmovnz  ecx, r9d
0x180013435  movss   xmm6, dword ptr [rcx+rsi]
0x18001343a  mov     [rsp+150h+var_120], 0
0x180013443  mov     rdi, [rsi+0AA8h]
0x18001344a  mov     rax, [rdi]
0x18001344d  mov     rbx, [rax+60h]
0x180013451  lea     rcx, [rsp+150h+var_120]
0x180013456  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18001345b  lea     rdx, [rsp+150h+var_120]
0x180013460  mov     rcx, rdi
0x180013463  mov     rax, rbx
0x180013466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001346b  mov     ebx, eax
0x18001346d  test    eax, eax
0x18001346f  jns     short loc_180013495
0x180013471  mov     edx, 1AC4h
0x180013476  jmp     short loc_18001347D
0x180013478  mov     edx, 1AC7h; void *
0x18001347d  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180013484  mov     r9d, eax; char *
0x180013487  mov     rcx, [rbp+58h]; this
0x18001348b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013490  jmp     loc_1800135C9
0x180013495  mov     rcx, [rsp+150h+var_120]
0x18001349a  mov     rax, [rcx]
0x18001349d  movaps  xmm1, xmm11
0x1800134a1  xorps   xmm1, cs:__xmm@80000000800000008000000080000000
0x1800134a8  mov     rax, [rax+20h]
0x1800134ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134b1  mov     ebx, eax
0x1800134b3  test    eax, eax
0x1800134b5  jns     short loc_1800134BE
0x1800134b7  mov     edx, 1AC5h
0x1800134bc  jmp     short loc_18001347D
0x1800134be  mov     rcx, [rsp+150h+var_120]
0x1800134c3  mov     rax, [rcx]
0x1800134c6  movss   xmm7, cs:__real@3f000000
0x1800134ce  mulss   xmm6, xmm7
0x1800134d2  movaps  xmm1, xmm6
0x1800134d5  mov     rax, [rax+30h]
0x1800134d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134de  mov     ebx, eax
0x1800134e0  test    eax, eax
0x1800134e2  jns     short loc_1800134EB
0x1800134e4  mov     edx, 1AC6h
0x1800134e9  jmp     short loc_18001347D
  ... truncated ...
```
