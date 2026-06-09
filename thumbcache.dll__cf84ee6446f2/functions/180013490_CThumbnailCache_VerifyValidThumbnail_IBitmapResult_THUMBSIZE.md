# CThumbnailCache::_VerifyValidThumbnail(IBitmapResult *,THUMBSIZE)

- ea: `0x180013490`
- end: `0x180013720`
- name: `?_VerifyValidThumbnail@CThumbnailCache@@AEAAJPEAUIBitmapResult@@W4THUMBSIZE@@@Z`
- size: `656`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180008a70`
- `0x18001161c`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x180013490`
- `0x180013728`
- `0x18003470c`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `GDI32!GetObjectW` at `0x1800135b0`
- `GDI32!GetObjectW` at `0x1800135b0`

## string_xrefs

- `0x180013614`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x18001364f`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x18001368d`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x1800136a2`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`
- `0x180013700`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheobj.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CThumbnailCache::_VerifyValidThumbnail(__int64 a1, __int64 a2, unsigned int a3)
{
  int v6; // ebx
  __int64 (__fastcall *v7)(__int64, __int64, GUID *, __int64 *); // rbx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-60h]
  HANDLE h; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  int v19; // [rsp+40h] [rbp-40h] BYREF
  __int64 v20; // [rsp+48h] [rbp-38h] BYREF
  __int128 pv; // [rsp+50h] [rbp-30h] BYREF
  __int128 v22; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( a3 == 13 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v20 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v20);
  if ( v6 < 0 )
  {
    v14 = 2121;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v6,
      v16);
    return (unsigned int)v6;
  }
  if ( !(unsigned __int8)CThumbnailCache::ValidateThumbnailDimensions(a1, v20, a3) )
  {
    v6 = -2147024809;
    v14 = 2122;
    goto LABEL_21;
  }
  v19 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 64LL))(a2, &v19);
  if ( v6 < 0 )
  {
    v14 = 2125;
    goto LABEL_21;
  }
  if ( v19 != 2 )
    return 0;
  v18 = 0;
  v7 = *(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  v8 = v7(a2, 2, &GUID_091162a4_bc96_411f_aae8_c5122cd03363, &v18);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x851,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
      (const char *)(unsigned int)v8,
      v16);
    v13 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  else
  {
    h = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v18 + 24LL))(v18, &h);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x854,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
        (const char *)(unsigned int)v9,
        v16);
      v15 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    else
    {
      pv = 0;
      v22 = 0;
      if ( GetObjectW(h, 32, &pv) )
      {
        if ( WORD1(v22) == 32 )
        {
          v10 = v18;
          if ( v18 )
          {
            v18 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          }
          return 0;
        }
        v6 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x85A,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
          (const char *)0x80070057LL,
          v16);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
      }
      else
      {
        v6 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x857,
          (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheobj.cpp",
          (const char *)0x80070057LL,
          v16);
        v12 = v18;
        if ( v18 )
        {
          v18 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180013490  mov     [rsp-18h+arg_0], rbx
0x180013495  mov     [rsp-18h+arg_10], rsi
0x18001349a  push    rbp
0x18001349b  push    rdi
0x18001349c  push    r14
0x18001349e  mov     rbp, rsp
0x1800134a1  sub     rsp, 80h
0x1800134a8  mov     rax, cs:__security_cookie
0x1800134af  xor     rax, rsp
0x1800134b2  mov     [rbp+var_10], rax
0x1800134b6  mov     esi, r8d
0x1800134b9  mov     rdi, rdx
0x1800134bc  mov     r14, rcx
0x1800134bf  cmp     r8d, 0Dh
0x1800134c3  jz      loc_1800136D7
0x1800134c9  mov     [rbp+var_38], 0
0x1800134d1  mov     rax, [rdi]
0x1800134d4  lea     rdx, [rbp+var_38]
0x1800134d8  mov     rcx, rdi
0x1800134db  mov     rax, [rax+48h]
0x1800134df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134e4  mov     ebx, eax
0x1800134e6  test    eax, eax
0x1800134e8  js      loc_180013681
0x1800134ee  mov     r8d, esi
0x1800134f1  mov     rdx, [rbp+var_38]
0x1800134f5  mov     rcx, r14
0x1800134f8  call    ?ValidateThumbnailDimensions@CThumbnailCache@@AEAA_NUtagSIZE@@W4THUMBSIZE@@@Z; CThumbnailCache::ValidateThumbnailDimensions(tagSIZE,THUMBSIZE)
0x1800134fd  test    al, al
0x1800134ff  jz      loc_1800136E1
0x180013505  mov     [rbp+var_40], 0
0x18001350c  mov     rax, [rdi]
0x18001350f  lea     rdx, [rbp+var_40]
0x180013513  mov     rcx, rdi
0x180013516  mov     rax, [rax+40h]
0x18001351a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001351f  mov     ebx, eax
0x180013521  test    eax, eax
0x180013523  js      loc_1800136ED
0x180013529  cmp     [rbp+var_40], 2
0x18001352d  jnz     loc_1800135E2
0x180013533  mov     [rbp+var_48], 0
0x18001353b  mov     rax, [rdi]
0x18001353e  mov     rbx, [rax+30h]
0x180013542  lea     rcx, [rbp+var_48]
0x180013546  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001354b  lea     r9, [rbp+var_48]
0x18001354f  lea     r8, _GUID_091162a4_bc96_411f_aae8_c5122cd03363
0x180013556  mov     edx, 2
0x18001355b  mov     rcx, rdi
0x18001355e  mov     rax, rbx
0x180013561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013566  mov     ebx, eax
0x180013568  test    eax, eax
0x18001356a  js      loc_180013648
0x180013570  mov     [rbp+h], 0
0x180013578  mov     rcx, [rbp+var_48]
0x18001357c  mov     rax, [rcx]
0x18001357f  lea     rdx, [rbp+h]
0x180013583  mov     rax, [rax+18h]
0x180013587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001358c  mov     ebx, eax
0x18001358e  test    eax, eax
0x180013590  js      loc_18001369B
0x180013596  xorps   xmm0, xmm0
0x180013599  movups  [rbp+pv], xmm0
0x18001359d  movups  [rbp+var_20], xmm0
0x1800135a1  lea     r8, [rbp+pv]; pv
0x1800135a5  mov     ebx, 20h ; ' '
0x1800135aa  mov     edx, ebx; c
0x1800135ac  mov     rcx, [rbp+h]; h
0x1800135b0  call    cs:__imp_GetObjectW
0x1800135b6  test    eax, eax
0x1800135b8  jz      short loc_180013608
0x1800135ba  cmp     word ptr [rbp+var_20+2], bx
0x1800135be  jnz     loc_1800136F4
0x1800135c4  mov     rcx, [rbp+var_48]
0x1800135c8  test    rcx, rcx
0x1800135cb  jz      short loc_1800135E2
0x1800135cd  mov     [rbp+var_48], 0
0x1800135d5  mov     rax, [rcx]
0x1800135d8  mov     rax, [rax+10h]
0x1800135dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135e1  nop
0x1800135e2  xor     eax, eax
0x1800135e4  mov     rcx, [rbp+var_10]
0x1800135e8  xor     rcx, rsp; StackCookie
0x1800135eb  call    __security_check_cookie
0x1800135f0  lea     r11, [rsp+80h+var_s0]
0x1800135f8  mov     rbx, [r11+20h]
0x1800135fc  mov     rsi, [r11+30h]
0x180013600  mov     rsp, r11
0x180013603  pop     r14
0x180013605  pop     rdi
0x180013606  pop     rbp
0x180013607  retn
0x180013608  mov     rcx, [rbp+18h]; this
0x18001360c  mov     ebx, 80070057h
0x180013611  mov     r9d, ebx; char *
0x180013614  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18001361b  mov     edx, 857h; void *
0x180013620  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013625  nop
0x180013626  mov     rcx, [rbp+var_48]
0x18001362a  test    rcx, rcx
0x18001362d  jz      short loc_180013644
0x18001362f  mov     [rbp+var_48], 0
0x180013637  mov     rax, [rcx]
0x18001363a  mov     rax, [rax+10h]
0x18001363e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013643  nop
0x180013644  mov     eax, ebx
0x180013646  jmp     short loc_1800135E4
0x180013648  mov     rcx, [rbp+18h]; this
0x18001364c  mov     r9d, ebx; char *
0x18001364f  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180013656  mov     edx, 851h; void *
0x18001365b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013660  nop
0x180013661  mov     rcx, [rbp+var_48]
0x180013665  test    rcx, rcx
0x180013668  jz      short loc_18001367F
0x18001366a  mov     [rbp+var_48], 0
0x180013672  mov     rax, [rcx]
0x180013675  mov     rax, [rax+10h]
0x180013679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001367e  nop
0x18001367f  jmp     short loc_180013644
0x180013681  mov     edx, 849h; void *
0x180013686  mov     rcx, [rbp+18h]; this
0x18001368a  mov     r9d, ebx; char *
0x18001368d  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180013694  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013699  jmp     short loc_180013644
0x18001369b  mov     rcx, [rbp+18h]; this
0x18001369f  mov     r9d, ebx; char *
0x1800136a2  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x1800136a9  mov     edx, 854h; void *
0x1800136ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800136b3  nop
0x1800136b4  mov     rcx, [rbp+var_48]
0x1800136b8  test    rcx, rcx
0x1800136bb  jz      short loc_1800136D2
0x1800136bd  mov     [rbp+var_48], 0
0x1800136c5  mov     rax, [rcx]
0x1800136c8  mov     rax, [rax+10h]
0x1800136cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136d1  nop
0x1800136d2  jmp     loc_180013644
0x1800136d7  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "thumbSize != THUMBSIZE_CUSTOM_STREAM")
0x1800136dc  jmp     loc_1800134C9
0x1800136e1  mov     ebx, 80070057h
0x1800136e6  mov     edx, 84Ah
0x1800136eb  jmp     short loc_180013686
0x1800136ed  mov     edx, 84Dh
0x1800136f2  jmp     short loc_180013686
0x1800136f4  mov     rcx, [rbp+18h]; this
0x1800136f8  mov     ebx, 80070057h
0x1800136fd  mov     r9d, ebx; char *
0x180013700  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x180013707  mov     edx, 85Ah; void *
0x18001370c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013711  nop
0x180013712  lea     rcx, [rbp+var_48]
0x180013716  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001371b  jmp     loc_180013644
```
