# CDWriteText::CreateTextFormat(void)

- ea: `0x1800094f4`
- end: `0x180009e56`
- name: `?CreateTextFormat@CDWriteText@@AEAAJXZ`
- size: `2402`
- prototype: `__int64 __fastcall(CDWriteText *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180008d68`

## callees

- `0x1800028f4`
- `0x1800090a4`
- `0x1800094f4`
- `0x180009e5c`
- `0x180009ea0`
- `0x180009f4c`
- `0x180009f64`
- `0x180009f94`
- `0x18006102c`
- `0x180081a68`
- `0x180083ba8`
- `0x18008703c`
- `0x180095130`
- `0x1800b7b74`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180009588`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLocaleName` at `0x180009588`

## string_xrefs

- `0x1800099e7`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x180009a26`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x180009b00`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x180009bf8`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x180009cd5`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x180009d9c`: `clientcore\windows\dwm\udwm\dwritetext.cpp`
- `0x180009e00`: `clientcore\windows\dwm\udwm\dwritetext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CDWriteText::CreateTextFormat(CDWriteText *this)
{
  CDWriteText *v1; // r13
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, __int64 *); // rbx
  int v4; // eax
  unsigned int v5; // ebx
  int UserDefaultLocaleName; // esi
  __int64 v7; // rdx
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, char *, __int64 *); // rbx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  int v19; // eax
  const char *v20; // rcx
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rdi
  unsigned __int64 v23; // rsi
  unsigned __int64 v24; // r14
  __int64 v25; // r13
  __int64 v26; // r15
  __int128 *v27; // r8
  unsigned int v28; // r14d
  int v29; // r12d
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, __int128 *, _QWORD, _QWORD); // rdi
  __int128 *v32; // rdx
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v39; // rbx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int128 *v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int128 *v58; // r9
  __int64 v59; // r9
  int v60; // [rsp+28h] [rbp-E0h]
  __int64 v61; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v62; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v63; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v65; // [rsp+78h] [rbp-90h] BYREF
  int v66; // [rsp+7Ch] [rbp-8Ch] BYREF
  unsigned int v67; // [rsp+80h] [rbp-88h] BYREF
  CDWriteText *v68; // [rsp+88h] [rbp-80h] BYREF
  __int128 v69; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v70; // [rsp+A0h] [rbp-68h]
  unsigned __int64 v71; // [rsp+A8h] [rbp-60h]
  __int128 v72; // [rsp+B0h] [rbp-58h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-48h]
  __int128 v74; // [rsp+D0h] [rbp-38h] BYREF
  int v75; // [rsp+E0h] [rbp-28h]
  WCHAR LocaleName[88]; // [rsp+E8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+200h] [rbp+F8h]

  v1 = this;
  v68 = this;
  v63 = 0;
  v2 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 31);
  v3 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 136LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v63);
  v4 = v3(v2, &v63);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)v4,
      v60);
    v40 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return v5;
  }
  v61 = 0;
  v64 = 0;
  v62 = 0;
  UserDefaultLocaleName = GetUserDefaultLocaleName(LocaleName, 85);
  v72 = 0;
  si128 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v72, v7, 8);
  v8 = v63;
  v9 = *(int (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v63 + 24LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v61);
  if ( v9(v8, (char *)v1 + 264, &v61) < 0 )
  {
    v28 = 400;
    v29 = 0;
  }
  else
  {
    v10 = v61;
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v64);
    v12 = v11(v10, &v64);
    v5 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
        (const char *)(unsigned int)v12,
        v60);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v72, 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v72) = 0;
      v54 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
      }
      v55 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      v56 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
      }
      v57 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      }
      return v5;
    }
    v13 = v64;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v64 + 48LL);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v62);
    v15 = v14(v13, &v62);
    v5 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x112,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
        (const char *)(unsigned int)v15,
        v60);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v72, 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v72) = 0;
      v50 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      }
      v51 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      }
      v52 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      }
      v53 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      }
      return v5;
    }
    v65 = 0;
    v66 = 0;
    if ( UserDefaultLocaleName )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, WCHAR *, unsigned int *, int *))(*(_QWORD *)v62 + 32LL))(
              v62,
              LocaleName,
              &v65,
              &v66);
      v5 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11A,
          (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
          (const char *)(unsigned int)v18,
          v60);
LABEL_103:
        std::wstring::~wstring(&v72);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v62);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v64);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v61);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v63);
        return v5;
      }
      if ( v66 )
        goto LABEL_11;
    }
    v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, int *))(*(_QWORD *)v62 + 32LL))(
            v62,
            L"en-us",
            &v65,
            &v66);
    v5 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
        (const char *)(unsigned int)v16,
        v60);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v72, 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v72) = 0;
      v46 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      }
      v47 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
      }
      v48 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      }
      v49 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      return v5;
    }
    if ( v66 )
    {
LABEL_11:
      v17 = v65;
    }
    else
    {
      v17 = 0;
      v65 = 0;
    }
    v67 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v62 + 56LL))(v62, v17, &v67);
    v5 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
        (const char *)(unsigned int)v19,
        v60);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v72, 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v72) = 0;
      v41 = v62;
      if ( v62 )
      {
        v62 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      }
      v42 = v64;
      if ( v64 )
      {
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      v43 = v61;
      if ( v61 )
      {
        v61 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
      }
      v44 = v63;
      if ( v63 )
      {
        v63 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      }
      return v5;
    }
    v69 = 0;
    v70 = 0;
    v71 = 0;
    std::wstring::_Construct_empty(&v69);
    if ( v67 )
    {
      v21 = v67;
      v22 = v70;
      if ( v67 <= v70 )
      {
        v70 = v67;
        v45 = &v69;
        if ( v71 > 7 )
          v45 = (__int128 *)v69;
        *((_WORD *)v45 + v67) = 0;
      }
      else
      {
        v23 = v67 - v70;
        v24 = v71;
        if ( v23 <= v71 - v70 )
        {
          v70 = v67;
          v58 = &v69;
          if ( v71 > 7 )
            v58 = (__int128 *)v69;
          std::_WChar_traits<unsigned short>::assign((char *)v58 + 2 * v22, v23);
          *(_WORD *)(v59 + 2 * v21) = 0;
        }
        else
        {
          if ( 0x7FFFFFFFFFFFFFFELL - v70 < v23 )
            std::_Dwm_Xlength_error(v20);
          v25 = std::wstring::_Calculate_growth(v67, v71);
          if ( (unsigned __int64)(v25 + 1) > 0x7FFFFFFFFFFFFFFFLL )
            std::_Throw_bad_array_new_length();
          v26 = std::_Allocate<16,std::_Default_allocate_traits>(2 * (v25 + 1));
          v70 = v21;
          v71 = v25;
          if ( v24 > 7 )
          {
            v39 = v69;
            `std::wstring::append'::`2'::_lambda_1_::operator()(v26, v69, v22, v23);
            std::_Deallocate<16>(v39, 2 * v24 + 2);
          }
          else
          {
            `std::wstring::append'::`2'::_lambda_1_::operator()(v26, &v69, v22, v23);
          }
          v1 = v68;
          *(_QWORD *)&v69 = v26;
        }
      }
      v27 = &v69;
      if ( v71 > 7 )
        v27 = (__int128 *)v69;
      (*(void (__fastcall **)(__int64, _QWORD, __int128 *, _QWORD))(*(_QWORD *)v62 + 64LL))(v62, v65, v27, v67 + 1);
    }
    v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v61 + 32LL))(v61);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 40LL))(v61);
    v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v61 + 48LL))(v61);
    if ( *((_DWORD *)v1 + 66) && (float)*((int *)v1 + 66) >= 0.0 )
    {
      v74 = 0;
      v75 = 0;
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v61 + 88LL))(v61, &v74);
    }
    if ( v71 > 7 )
      std::_Deallocate<16>(v69, 2 * v71 + 2);
    v70 = 0;
    v71 = 7;
    LOWORD(v69) = 0;
  }
  v68 = 0;
  v30 = *((_QWORD *)CDesktopManager::s_pDesktopManagerInstance + 31);
  v31 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v30 + 120LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)v1 + 216);
  v32 = &v72;
  if ( si128.m128i_i64[1] > 7uLL )
    v32 = (__int128 *)v72;
  v33 = v31(v30, v32, 0, v28);
  v5 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"clientcore\\windows\\dwm\\udwm\\dwritetext.cpp",
      (const char *)(unsigned int)v33,
      v29);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v68);
    goto LABEL_103;
  }
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v72, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v72) = 0;
  v34 = v62;
  if ( v62 )
  {
    v62 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v64;
  if ( v64 )
  {
    v64 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v37 = v63;
  if ( v63 )
  {
    v63 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  return 0;
}

```

## disassembly

```asm
0x1800094f4  mov     rax, rsp
0x1800094f7  push    rbp
0x1800094f8  push    rbx
0x1800094f9  push    rsi
0x1800094fa  push    rdi
0x1800094fb  push    r12
0x1800094fd  push    r13
0x1800094ff  push    r14
0x180009501  push    r15
0x180009503  lea     rbp, [rax-0F8h]
0x18000950a  sub     rsp, 1B8h
0x180009511  movaps  xmmword ptr [rax-58h], xmm6
0x180009515  mov     rax, cs:__security_cookie
0x18000951c  xor     rax, rsp
0x18000951f  mov     [rbp+0F0h+var_60], rax
0x180009526  mov     r13, rcx
0x180009529  mov     [rbp+0F0h+var_170], rcx
0x18000952d  xor     r15d, r15d
0x180009530  mov     [rsp+1F0h+var_190], r15
0x180009535  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18000953c  mov     rdi, [rax+0F8h]
0x180009543  mov     rax, [rdi]
0x180009546  mov     rbx, [rax+88h]
0x18000954d  lea     rcx, [rsp+1F0h+var_190]
0x180009552  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180009557  lea     rdx, [rsp+1F0h+var_190]
0x18000955c  mov     rcx, rdi
0x18000955f  mov     rax, rbx
0x180009562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009567  mov     ebx, eax
0x180009569  test    eax, eax
0x18000956b  js      loc_1800099DD
0x180009571  mov     [rsp+1F0h+var_1A0], r15
0x180009576  mov     qword ptr [rsp+1F0h+var_188], r15
0x18000957b  mov     [rsp+1F0h+var_198], r15
0x180009580  lea     edx, [r15+55h]; cchLocaleName
0x180009584  lea     rcx, [rbp+0F0h+LocaleName]; lpLocaleName
0x180009588  call    cs:__imp_GetUserDefaultLocaleName
0x18000958e  mov     esi, eax
0x180009590  xorps   xmm0, xmm0
0x180009593  movups  [rbp+0F0h+var_148], xmm0
0x180009597  xorps   xmm1, xmm1
0x18000959a  movdqu  [rbp+0F0h+var_138], xmm1
0x18000959f  lea     r8d, [r15+8]
0x1800095a3  lea     rcx, [rbp+0F0h+var_148]
0x1800095a7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800095ac  nop
0x1800095ad  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800095b4  movsd   xmm6, qword ptr [rcx+1A0h]
0x1800095bc  cvtpd2ps xmm6, xmm6
0x1800095c0  mulss   xmm6, cs:__real@41400000
0x1800095c8  mov     rdi, [rsp+1F0h+var_190]
0x1800095cd  mov     rax, [rdi]
0x1800095d0  mov     rbx, [rax+18h]
0x1800095d4  lea     rcx, [rsp+1F0h+var_1A0]
0x1800095d9  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800095de  lea     rdx, [r13+108h]
0x1800095e5  lea     r8, [rsp+1F0h+var_1A0]
0x1800095ea  mov     rcx, rdi
0x1800095ed  mov     rax, rbx
0x1800095f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095f5  test    eax, eax
0x1800095f7  js      loc_180009DE2
0x1800095fd  mov     rdi, [rsp+1F0h+var_1A0]
0x180009602  mov     rax, [rdi]
0x180009605  mov     rbx, [rax+18h]
0x180009609  lea     rcx, [rsp+1F0h+var_188]
0x18000960e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180009613  lea     rdx, [rsp+1F0h+var_188]
0x180009618  mov     rcx, rdi
0x18000961b  mov     rax, rbx
0x18000961e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009623  mov     ebx, eax
0x180009625  test    eax, eax
0x180009627  js      loc_180009CCB
0x18000962d  mov     rdi, qword ptr [rsp+1F0h+var_188]
0x180009632  mov     rax, [rdi]
0x180009635  mov     rbx, [rax+30h]
0x180009639  lea     rcx, [rsp+1F0h+var_198]
0x18000963e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180009643  lea     rdx, [rsp+1F0h+var_198]
0x180009648  mov     rcx, rdi
0x18000964b  mov     rax, rbx
0x18000964e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009653  mov     ebx, eax
0x180009655  test    eax, eax
0x180009657  js      loc_180009BEE
0x18000965d  mov     [rsp+1F0h+var_180], r15d
0x180009662  mov     [rsp+1F0h+var_17C], r15d
0x180009667  test    esi, esi
0x180009669  jnz     short loc_1800096A7
0x18000966b  mov     rcx, [rsp+1F0h+var_198]
0x180009670  mov     rax, [rcx]
0x180009673  lea     r9, [rsp+1F0h+var_17C]
0x180009678  lea     r8, [rsp+1F0h+var_180]
0x18000967d  lea     rdx, aEnUs; "en-us"
0x180009684  mov     rax, [rax+20h]
0x180009688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000968d  mov     ebx, eax
0x18000968f  test    eax, eax
0x180009691  js      loc_180009AF6
0x180009697  cmp     [rsp+1F0h+var_17C], r15d
0x18000969c  jnz     short loc_1800096D7
0x18000969e  mov     edx, r15d
0x1800096a1  mov     [rsp+1F0h+var_180], edx
0x1800096a5  jmp     short loc_1800096DB
0x1800096a7  mov     rcx, [rsp+1F0h+var_198]
0x1800096ac  mov     rax, [rcx]
0x1800096af  lea     r9, [rsp+1F0h+var_17C]
0x1800096b4  lea     r8, [rsp+1F0h+var_180]
0x1800096b9  lea     rdx, [rbp+0F0h+LocaleName]
0x1800096bd  mov     rax, [rax+20h]
0x1800096c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c6  mov     ebx, eax
0x1800096c8  test    eax, eax
0x1800096ca  js      loc_180009D92
0x1800096d0  cmp     [rsp+1F0h+var_17C], r15d
0x1800096d5  jz      short loc_18000966B
0x1800096d7  mov     edx, [rsp+1F0h+var_180]
0x1800096db  mov     [rsp+1F0h+var_178], r15d
0x1800096e0  mov     rcx, [rsp+1F0h+var_198]
0x1800096e5  mov     rax, [rcx]
0x1800096e8  lea     r8, [rsp+1F0h+var_178]
0x1800096ed  mov     rax, [rax+38h]
0x1800096f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096f6  mov     ebx, eax
0x1800096f8  test    eax, eax
0x1800096fa  js      loc_180009A1C
0x180009700  xorps   xmm0, xmm0
0x180009703  movups  [rbp+0F0h+var_168], xmm0
0x180009707  mov     [rbp+0F0h+var_158], r15
0x18000970b  mov     [rbp+0F0h+var_150], r15
0x18000970f  lea     rcx, [rbp+0F0h+var_168]
0x180009713  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180009718  nop
0x180009719  mov     eax, [rsp+1F0h+var_178]
0x18000971d  test    eax, eax
0x18000971f  jz      loc_1800097EB
0x180009725  mov     ebx, eax
0x180009727  mov     rdi, [rbp+0F0h+var_158]
0x18000972b  cmp     rax, rdi
0x18000972e  jbe     loc_180009ADA
0x180009734  mov     esi, eax
0x180009736  sub     rsi, rdi
0x180009739  mov     r14, [rbp+0F0h+var_150]
0x18000973d  mov     rax, r14
0x180009740  sub     rax, rdi
0x180009743  cmp     rsi, rax
0x180009746  jbe     loc_180009DAF
0x18000974c  mov     r8, 7FFFFFFFFFFFFFFEh
0x180009756  mov     rax, r8
0x180009759  sub     rax, rdi
0x18000975c  cmp     rax, rsi
0x18000975f  jb      loc_180009DD6
0x180009765  mov     rdx, r14
0x180009768  mov     ecx, ebx
0x18000976a  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18000976f  mov     r13, rax
0x180009772  lea     rcx, [rax+1]
0x180009776  mov     rax, 7FFFFFFFFFFFFFFFh
0x180009780  cmp     rcx, rax
0x180009783  ja      loc_180009DDC
0x180009789  add     rcx, rcx
0x18000978c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180009791  mov     r15, rax
0x180009794  mov     [rbp+0F0h+var_158], rbx
0x180009798  mov     [rbp+0F0h+var_150], r13
0x18000979c  mov     r9, rsi
0x18000979f  mov     r8, rdi
0x1800097a2  mov     rcx, rax
0x1800097a5  cmp     r14, 7
0x1800097a9  ja      loc_1800099BC
0x1800097af  lea     rdx, [rbp+0F0h+var_168]
0x1800097b3  call    ??R_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV23@_KG@Z@SA@QEAGQEBG00G@Z; `std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_::operator()(ushort * const,ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1800097b8  mov     r13, [rbp+0F0h+var_170]
0x1800097bc  mov     qword ptr [rbp+0F0h+var_168], r15
0x1800097c0  mov     rcx, [rsp+1F0h+var_198]
0x1800097c5  mov     rax, [rcx]
0x1800097c8  mov     r9d, [rsp+1F0h+var_178]
0x1800097cd  inc     r9d
0x1800097d0  lea     r8, [rbp+0F0h+var_168]
0x1800097d4  cmp     [rbp+0F0h+var_150], 7
0x1800097d9  cmova   r8, qword ptr [rbp+0F0h+var_168]
0x1800097de  mov     edx, [rsp+1F0h+var_180]
0x1800097e2  mov     rax, [rax+40h]
0x1800097e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097eb  mov     rcx, [rsp+1F0h+var_1A0]
0x1800097f0  mov     rax, [rcx]
0x1800097f3  mov     rax, [rax+20h]
0x1800097f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097fc  mov     r14d, eax
0x1800097ff  mov     rcx, [rsp+1F0h+var_1A0]
0x180009804  mov     rdx, [rcx]
0x180009807  mov     rax, [rdx+28h]
0x18000980b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009810  mov     r15d, eax
0x180009813  mov     rcx, [rsp+1F0h+var_1A0]
0x180009818  mov     rdx, [rcx]
0x18000981b  mov     rax, [rdx+30h]
0x18000981f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009824  mov     r12d, eax
0x180009827  lea     rax, [r13+108h]
0x18000982e  cmp     dword ptr [rax], 0
0x180009831  jz      short loc_18000984D
0x180009833  movd    xmm6, dword ptr [rax]
0x180009837  cvtdq2ps xmm6, xmm6
0x18000983a  xorps   xmm0, xmm0
0x18000983d  comiss  xmm0, xmm6
0x180009840  jbe     loc_180009BA7
0x180009846  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x18000984d  mov     rdx, [rbp+0F0h+var_150]
0x180009851  cmp     rdx, 7
0x180009855  jbe     short loc_180009868
0x180009857  lea     rdx, ds:2[rdx*2]
0x18000985f  mov     rcx, qword ptr [rbp+0F0h+var_168]
0x180009863  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180009868  mov     [rbp+0F0h+var_158], 0
0x180009870  mov     [rbp+0F0h+var_150], 7
0x180009878  xor     eax, eax
0x18000987a  mov     word ptr [rbp+0F0h+var_168], ax
0x18000987e  mov     [rbp+0F0h+var_170], 0
0x180009886  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18000988d  mov     rsi, [rax+0F8h]
0x180009894  mov     rax, [rsi]
0x180009897  mov     rdi, [rax+78h]
0x18000989b  lea     rbx, [r13+0D8h]
0x1800098a2  mov     rcx, rbx
0x1800098a5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800098aa  lea     rdx, [rbp+0F0h+var_148]
0x1800098ae  cmp     qword ptr [rbp+0F0h+var_138+8], 7
0x1800098b3  cmova   rdx, qword ptr [rbp+0F0h+var_148]
0x1800098b8  mov     [rsp+40h], rbx
0x1800098bd  lea     rax, [rbp+0F0h+LocaleName]
0x1800098c1  mov     [rsp+1F0h+var_1B8], rax
0x1800098c6  movss   dword ptr [rsp+1F0h+var_1C0], xmm6
0x1800098cc  mov     [rsp+1F0h+var_1C8], r15d
0x1800098d1  mov     [rsp+1F0h+var_1D0], r12d; int
0x1800098d6  mov     r9d, r14d
0x1800098d9  xor     r8d, r8d
0x1800098dc  mov     rcx, rsi
0x1800098df  mov     rax, rdi
0x1800098e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098e7  mov     ebx, eax
0x1800098e9  xor     edi, edi
0x1800098eb  test    eax, eax
0x1800098ed  js      loc_180009DF6
0x1800098f3  mov     rdx, qword ptr [rbp+0F0h+var_138+8]
0x1800098f7  cmp     rdx, 7
0x1800098fb  jbe     short loc_18000990E
0x1800098fd  lea     rdx, ds:2[rdx*2]
0x180009905  mov     rcx, qword ptr [rbp+0F0h+var_148]
0x180009909  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000990e  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180009916  movdqu  [rbp+0F0h+var_138], xmm0
0x18000991b  mov     word ptr [rbp+0F0h+var_148], di
0x18000991f  mov     rcx, [rsp+1F0h+var_198]
0x180009924  test    rcx, rcx
0x180009927  jz      short loc_18000993B
0x180009929  mov     [rsp+1F0h+var_198], rdi
0x18000992e  mov     rax, [rcx]
0x180009931  mov     rax, [rax+10h]
0x180009935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000993a  nop
0x18000993b  mov     rcx, qword ptr [rsp+1F0h+var_188]
0x180009940  test    rcx, rcx
0x180009943  jz      short loc_180009957
0x180009945  mov     qword ptr [rsp+1F0h+var_188], rdi
0x18000994a  mov     rax, [rcx]
0x18000994d  mov     rax, [rax+10h]
0x180009951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009956  nop
0x180009957  mov     rcx, [rsp+1F0h+var_1A0]
0x18000995c  test    rcx, rcx
0x18000995f  jz      short loc_180009973
0x180009961  mov     [rsp+1F0h+var_1A0], rdi
0x180009966  mov     rax, [rcx]
0x180009969  mov     rax, [rax+10h]
0x18000996d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009972  nop
0x180009973  mov     rcx, [rsp+1F0h+var_190]
0x180009978  test    rcx, rcx
0x18000997b  jz      short loc_18000998F
0x18000997d  mov     [rsp+1F0h+var_190], rdi
0x180009982  mov     rax, [rcx]
0x180009985  mov     rax, [rax+10h]
0x180009989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000998e  nop
0x18000998f  xor     eax, eax
0x180009991  mov     rcx, [rbp+0F0h+var_60]
0x180009998  xor     rcx, rsp; StackCookie
0x18000999b  call    __security_check_cookie
0x1800099a0  movaps  xmm6, [rsp+1F0h+var_58+8]
0x1800099a8  add     rsp, 1B8h
0x1800099af  pop     r15
0x1800099b1  pop     r14
0x1800099b3  pop     r13
0x1800099b5  pop     r12
0x1800099b7  pop     rdi
0x1800099b8  pop     rsi
0x1800099b9  pop     rbx
  ... truncated ...
```
