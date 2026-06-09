# VmMetricRepositoryUtilities::WriteMetric(VmRepository *,IVmMetricValue *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14008b6c0`
- end: `0x14008bd8f`
- name: `?WriteMetric@VmMetricRepositoryUtilities@@SAXPEAVVmRepository@@PEAUIVmMetricValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1743`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14008cd10`
- `0x1400a3798`
- `0x1400a3ab0`
- `0x14029d918`

## callees

- `0x14003c108`
- `0x14003d828`
- `0x140078628`
- `0x14008b6c0`
- `0x14008bd98`
- `0x14008be74`
- `0x14011ea40`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008ba04`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14008ba04`

## string_xrefs

- `0x14008b769`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b799`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b7c9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b7f9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b829`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b859`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b889`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b8b9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b8e9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b91c`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b976`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008b9de`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008ba60`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008bac3`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008bb26`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008bb89`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008bbec`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008bc4f`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008bcc9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008bd31`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14008bb4f`: `/lastcomputedtime`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall VmMetricRepositoryUtilities::WriteMetric(__int64 a1, __int64 a2, void *a3)
{
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 (__fastcall *v16)(__int64, _QWORD *, __int64); // r14
  __int64 v17; // rbx
  _QWORD *v18; // rax
  int v19; // eax
  __int64 (__fastcall *v20)(__int64, _QWORD *, BOOL); // r14
  BOOL v21; // ebx
  _QWORD *v22; // rax
  int v23; // eax
  __int64 (__fastcall *v24)(__int64, _QWORD *, __int64); // r14
  __int64 v25; // rbx
  _QWORD *v26; // rax
  int v27; // eax
  __int64 (__fastcall *v28)(__int64, _QWORD *, __int64); // r14
  __int64 v29; // rbx
  _QWORD *v30; // rax
  int v31; // eax
  __int64 (__fastcall *v32)(__int64, _QWORD *, __int64); // r14
  __int64 v33; // rbx
  _QWORD *v34; // rax
  int v35; // eax
  __int64 (__fastcall *v36)(__int64, _QWORD *, __int64); // r14
  __int64 v37; // rbx
  _QWORD *v38; // rax
  int v39; // eax
  __int64 (__fastcall *v40)(__int64, _QWORD *, __int64); // r14
  __int64 v41; // rbx
  _QWORD *v42; // rax
  int v43; // eax
  __int64 (__fastcall *v44)(__int64, _QWORD *, __int64); // r14
  __int64 v45; // rbx
  _QWORD *v46; // rax
  int v47; // eax
  __int64 (__fastcall *v48)(__int64, _QWORD *, unsigned __int16 *); // r14
  unsigned __int16 *v49; // rbx
  _QWORD *v50; // rax
  int v51; // eax
  __int64 (__fastcall *v52)(__int64, _QWORD *, __int64); // r14
  __int64 v53; // rbx
  _QWORD *v54; // rax
  int v55; // eax
  int v56[8]; // [rsp+20h] [rbp-69h] BYREF
  int v57; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v58; // [rsp+44h] [rbp-45h] BYREF
  __int64 v59; // [rsp+48h] [rbp-41h] BYREF
  __int64 v60; // [rsp+50h] [rbp-39h] BYREF
  __int64 v61; // [rsp+58h] [rbp-31h] BYREF
  __int64 v62; // [rsp+60h] [rbp-29h] BYREF
  __int64 v63; // [rsp+68h] [rbp-21h] BYREF
  __int64 v64; // [rsp+70h] [rbp-19h] BYREF
  __int64 v65; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int16 v66[8]; // [rsp+80h] [rbp-9h] BYREF
  __m128i si128; // [rsp+90h] [rbp+7h]
  struct _GUID v68; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v62 = 0;
  v57 = 0;
  v59 = 0;
  v61 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v60 = 0;
  v68 = 0;
  *(_OWORD *)v66 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v66[0] = 0;
  v58 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 32LL))(a2, &v62);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v6,
      v56[0]);
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 48LL))(a2, &v57);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v7,
      v56[0]);
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 56LL))(a2, &v59);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v8,
      v56[0]);
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v61);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v9,
      v56[0]);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v63);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v10,
      v56[0]);
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 80LL))(a2, &v64);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v11,
      v56[0]);
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 88LL))(a2, &v65);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v12,
      v56[0]);
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 104LL))(a2, &v60);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v13,
      v56[0]);
  v14 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)a2 + 120LL))(a2, &v68);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v14,
      v56[0]);
  v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 152LL))(a2, &v58);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v15,
      v56[0]);
  v16 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL);
  v17 = v62;
  v18 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/value");
  if ( v18[3] > 7u )
    v18 = (_QWORD *)*v18;
  v19 = v16(a1, v18, v17);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v19,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  v20 = *(__int64 (__fastcall **)(__int64, _QWORD *, BOOL))(*(_QWORD *)a1 + 176LL);
  v21 = v57 == 2;
  v22 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/enabled");
  if ( v22[3] > 7u )
    v22 = (_QWORD *)*v22;
  v23 = v20(a1, v22, v21);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v23,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  if ( (unsigned int)_o__wcsicmp(v59, &qword_1402EDF50) )
  {
    v24 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 152LL);
    v25 = v59;
    v26 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/breakdowndimension");
    if ( v26[3] > 7u )
      v26 = (_QWORD *)*v26;
    v27 = v24(a1, v26, v25);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
        (const char *)(unsigned int)v27,
        v56[0]);
    std::wstring::_Tidy_deallocate(v56);
    v28 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 152LL);
    v29 = v61;
    v30 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/breakdownvalue");
    if ( v30[3] > 7u )
      v30 = (_QWORD *)*v30;
    v31 = v28(a1, v30, v29);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
        (const char *)(unsigned int)v31,
        v56[0]);
    std::wstring::_Tidy_deallocate(v56);
  }
  v32 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL);
  v33 = v63;
  v34 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/starttime");
  if ( v34[3] > 7u )
    v34 = (_QWORD *)*v34;
  v35 = v32(a1, v34, v33);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x202,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v35,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  v36 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL);
  v37 = v64;
  v38 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/lastcomputedtime");
  if ( v38[3] > 7u )
    v38 = (_QWORD *)*v38;
  v39 = v36(a1, v38, v37);
  if ( v39 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v39,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  v40 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL);
  v41 = v65;
  v42 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/peaktime");
  if ( v42[3] > 7u )
    v42 = (_QWORD *)*v42;
  v43 = v40(a1, v42, v41);
  if ( v43 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v43,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  v44 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 152LL);
  v45 = v60;
  v46 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/poolid");
  if ( v46[3] > 7u )
    v46 = (_QWORD *)*v46;
  v47 = v44(a1, v46, v45);
  if ( v47 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20E,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v47,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  Vml::VmGuid::ToString(&v68, v66);
  v48 = *(__int64 (__fastcall **)(__int64, _QWORD *, unsigned __int16 *))(*(_QWORD *)a1 + 152LL);
  v49 = v66;
  if ( si128.m128i_i64[1] > 7uLL )
    v49 = *(unsigned __int16 **)v66;
  v50 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/resourcetypeid");
  if ( v50[3] > 7u )
    v50 = (_QWORD *)*v50;
  v51 = v48(a1, v50, v49);
  if ( v51 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
      (const char *)(unsigned int)v51,
      v56[0]);
  std::wstring::_Tidy_deallocate(v56);
  if ( v58 )
  {
    v52 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 160LL);
    v53 = v58;
    v54 = (_QWORD *)std::operator+<unsigned short>(v56, a3, (void *)L"/weight");
    if ( v54[3] > 7u )
      v54 = (_QWORD *)*v54;
    v55 = v52(a1, v54, v53);
    if ( v55 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x219,
        (unsigned int)"onecore\\vm\\common\\metrics\\vmmetricrepositoryutilities.cpp",
        (const char *)(unsigned int)v55,
        v56[0]);
    std::wstring::_Tidy_deallocate(v56);
  }
  std::wstring::_Tidy_deallocate(v66);
  Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v60);
  Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v61);
  Vml::VmBstr::~VmBstr((Vml::VmBstr *)&v59);
}

```

## disassembly

```asm
0x14008b6c0  push    rbp
0x14008b6c2  push    rbx
0x14008b6c3  push    rsi
0x14008b6c4  push    rdi
0x14008b6c5  push    r14
0x14008b6c7  lea     rbp, [rsp-37h]
0x14008b6cc  sub     rsp, 0C0h
0x14008b6d3  mov     rax, cs:__security_cookie
0x14008b6da  xor     rax, rsp
0x14008b6dd  mov     [rbp+57h+var_30], rax
0x14008b6e1  mov     rsi, r8
0x14008b6e4  mov     rbx, rdx
0x14008b6e7  mov     rdi, rcx
0x14008b6ea  mov     [rbp+57h+var_80], 0
0x14008b6f2  mov     [rbp+57h+var_A0], 0
0x14008b6f9  mov     [rbp+57h+var_98], 0
0x14008b701  mov     [rbp+57h+var_88], 0
0x14008b709  mov     [rbp+57h+var_78], 0
0x14008b711  mov     [rbp+57h+var_70], 0
0x14008b719  mov     [rbp+57h+var_68], 0
0x14008b721  mov     [rbp+57h+var_90], 0
0x14008b729  xorps   xmm0, xmm0
0x14008b72c  movdqa  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x14008b731  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14008b735  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14008b73d  movdqu  [rbp+57h+var_50], xmm1
0x14008b742  xor     eax, eax
0x14008b744  mov     [rbp+57h+var_60], ax
0x14008b748  mov     [rbp+57h+var_9C], eax
0x14008b74b  mov     rax, [rdx]
0x14008b74e  lea     rdx, [rbp+57h+var_80]
0x14008b752  mov     rcx, rbx
0x14008b755  mov     rax, [rax+20h]
0x14008b759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b75e  mov     rcx, [rbp+5Fh]; this
0x14008b762  test    eax, eax
0x14008b764  jns     short loc_14008B77B
0x14008b766  mov     r9d, eax; char *
0x14008b769  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b770  mov     edx, 1DEh; void *
0x14008b775  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b77b  mov     rax, [rbx]
0x14008b77e  lea     rdx, [rbp+57h+var_A0]
0x14008b782  mov     rcx, rbx
0x14008b785  mov     rax, [rax+30h]
0x14008b789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b78e  mov     rcx, [rbp+5Fh]; this
0x14008b792  test    eax, eax
0x14008b794  jns     short loc_14008B7AB
0x14008b796  mov     r9d, eax; char *
0x14008b799  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b7a0  mov     edx, 1DFh; void *
0x14008b7a5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b7ab  mov     rax, [rbx]
0x14008b7ae  lea     rdx, [rbp+57h+var_98]
0x14008b7b2  mov     rcx, rbx
0x14008b7b5  mov     rax, [rax+38h]
0x14008b7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b7be  mov     rcx, [rbp+5Fh]; this
0x14008b7c2  test    eax, eax
0x14008b7c4  jns     short loc_14008B7DB
0x14008b7c6  mov     r9d, eax; char *
0x14008b7c9  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b7d0  mov     edx, 1E0h; void *
0x14008b7d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b7db  mov     rax, [rbx]
0x14008b7de  lea     rdx, [rbp+57h+var_88]
0x14008b7e2  mov     rcx, rbx
0x14008b7e5  mov     rax, [rax+40h]
0x14008b7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b7ee  mov     rcx, [rbp+5Fh]; this
0x14008b7f2  test    eax, eax
0x14008b7f4  jns     short loc_14008B80B
0x14008b7f6  mov     r9d, eax; char *
0x14008b7f9  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b800  mov     edx, 1E1h; void *
0x14008b805  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b80b  mov     rax, [rbx]
0x14008b80e  lea     rdx, [rbp+57h+var_78]
0x14008b812  mov     rcx, rbx
0x14008b815  mov     rax, [rax+48h]
0x14008b819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b81e  mov     rcx, [rbp+5Fh]; this
0x14008b822  test    eax, eax
0x14008b824  jns     short loc_14008B83B
0x14008b826  mov     r9d, eax; char *
0x14008b829  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b830  mov     edx, 1E2h; void *
0x14008b835  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b83b  mov     rax, [rbx]
0x14008b83e  lea     rdx, [rbp+57h+var_70]
0x14008b842  mov     rcx, rbx
0x14008b845  mov     rax, [rax+50h]
0x14008b849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b84e  mov     rcx, [rbp+5Fh]; this
0x14008b852  test    eax, eax
0x14008b854  jns     short loc_14008B86B
0x14008b856  mov     r9d, eax; char *
0x14008b859  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b860  mov     edx, 1E3h; void *
0x14008b865  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b86b  mov     rax, [rbx]
0x14008b86e  lea     rdx, [rbp+57h+var_68]
0x14008b872  mov     rcx, rbx
0x14008b875  mov     rax, [rax+58h]
0x14008b879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b87e  mov     rcx, [rbp+5Fh]; this
0x14008b882  test    eax, eax
0x14008b884  jns     short loc_14008B89B
0x14008b886  mov     r9d, eax; char *
0x14008b889  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b890  mov     edx, 1E4h; void *
0x14008b895  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b89b  mov     rax, [rbx]
0x14008b89e  lea     rdx, [rbp+57h+var_90]
0x14008b8a2  mov     rcx, rbx
0x14008b8a5  mov     rax, [rax+68h]
0x14008b8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b8ae  mov     rcx, [rbp+5Fh]; this
0x14008b8b2  test    eax, eax
0x14008b8b4  jns     short loc_14008B8CB
0x14008b8b6  mov     r9d, eax; char *
0x14008b8b9  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b8c0  mov     edx, 1E5h; void *
0x14008b8c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b8cb  mov     rax, [rbx]
0x14008b8ce  lea     rdx, [rbp+57h+var_40]
0x14008b8d2  mov     rcx, rbx
0x14008b8d5  mov     rax, [rax+78h]
0x14008b8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b8de  mov     rcx, [rbp+5Fh]; this
0x14008b8e2  test    eax, eax
0x14008b8e4  jns     short loc_14008B8FB
0x14008b8e6  mov     r9d, eax; char *
0x14008b8e9  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b8f0  mov     edx, 1E6h; void *
0x14008b8f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b8fb  mov     rax, [rbx]
0x14008b8fe  lea     rdx, [rbp+57h+var_9C]
0x14008b902  mov     rcx, rbx
0x14008b905  mov     rax, [rax+98h]
0x14008b90c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b911  mov     rcx, [rbp+5Fh]; this
0x14008b915  test    eax, eax
0x14008b917  jns     short loc_14008B92E
0x14008b919  mov     r9d, eax; char *
0x14008b91c  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b923  mov     edx, 1E7h; void *
0x14008b928  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b92e  mov     rax, [rdi]
0x14008b931  mov     r14, [rax+0A0h]
0x14008b938  mov     rbx, [rbp+57h+var_80]
0x14008b93c  lea     r8, ?METRIC_VALUE_RELATIVE@@3QBGB; "/value"
0x14008b943  mov     rdx, rsi; Src
0x14008b946  lea     rcx, [rbp+57h+var_C0]; void *
0x14008b94a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14008b94f  nop
0x14008b950  cmp     qword ptr [rax+18h], 7
0x14008b955  jbe     short loc_14008B95A
0x14008b957  mov     rax, [rax]
0x14008b95a  mov     r8, rbx
0x14008b95d  mov     rdx, rax
0x14008b960  mov     rcx, rdi
0x14008b963  mov     rax, r14
0x14008b966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b96b  mov     rcx, [rbp+5Fh]; this
0x14008b96f  test    eax, eax
0x14008b971  jns     short loc_14008B988
0x14008b973  mov     r9d, eax; char *
0x14008b976  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b97d  mov     edx, 1EBh; void *
0x14008b982  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b988  lea     rcx, [rbp+57h+var_C0]
0x14008b98c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008b991  mov     rax, [rdi]
0x14008b994  mov     r14, [rax+0B0h]
0x14008b99b  xor     ebx, ebx
0x14008b99d  cmp     [rbp+57h+var_A0], 2
0x14008b9a1  setz    bl
0x14008b9a4  lea     r8, ?METRIC_ENABLED_RELATIVE@@3QBGB; "/enabled"
0x14008b9ab  mov     rdx, rsi; Src
0x14008b9ae  lea     rcx, [rbp+57h+var_C0]; void *
0x14008b9b2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14008b9b7  nop
0x14008b9b8  cmp     qword ptr [rax+18h], 7
0x14008b9bd  jbe     short loc_14008B9C2
0x14008b9bf  mov     rax, [rax]
0x14008b9c2  mov     r8d, ebx
0x14008b9c5  mov     rdx, rax
0x14008b9c8  mov     rcx, rdi
0x14008b9cb  mov     rax, r14
0x14008b9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b9d3  mov     rcx, [rbp+5Fh]; this
0x14008b9d7  test    eax, eax
0x14008b9d9  jns     short loc_14008B9F0
0x14008b9db  mov     r9d, eax; char *
0x14008b9de  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008b9e5  mov     edx, 1EFh; void *
0x14008b9ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008b9f0  lea     rcx, [rbp+57h+var_C0]
0x14008b9f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008b9f9  lea     rdx, qword_1402EDF50
0x14008ba00  mov     rcx, [rbp+57h+var_98]
0x14008ba04  call    cs:__imp__o__wcsicmp
0x14008ba0b  nop     dword ptr [rax+rax+00h]
0x14008ba10  test    eax, eax
0x14008ba12  jz      loc_14008BADE
0x14008ba18  mov     rax, [rdi]
0x14008ba1b  mov     r14, [rax+98h]
0x14008ba22  mov     rbx, [rbp+57h+var_98]
0x14008ba26  lea     r8, ?METRIC_BREAKDOWNDIMENSION_RELATIVE@@3QBGB; "/breakdowndimension"
0x14008ba2d  mov     rdx, rsi; Src
0x14008ba30  lea     rcx, [rbp+57h+var_C0]; void *
0x14008ba34  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14008ba39  nop
0x14008ba3a  cmp     qword ptr [rax+18h], 7
0x14008ba3f  jbe     short loc_14008BA44
0x14008ba41  mov     rax, [rax]
0x14008ba44  mov     r8, rbx
0x14008ba47  mov     rdx, rax
0x14008ba4a  mov     rcx, rdi
0x14008ba4d  mov     rax, r14
0x14008ba50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008ba55  mov     rcx, [rbp+5Fh]; this
0x14008ba59  test    eax, eax
0x14008ba5b  jns     short loc_14008BA72
0x14008ba5d  mov     r9d, eax; char *
0x14008ba60  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008ba67  mov     edx, 1F9h; void *
0x14008ba6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008ba72  lea     rcx, [rbp+57h+var_C0]
0x14008ba76  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008ba7b  mov     rax, [rdi]
0x14008ba7e  mov     r14, [rax+98h]
0x14008ba85  mov     rbx, [rbp+57h+var_88]
0x14008ba89  lea     r8, ?METRIC_BREAKDOWNVALUE_RELATIVE@@3QBGB; "/breakdownvalue"
0x14008ba90  mov     rdx, rsi; Src
0x14008ba93  lea     rcx, [rbp+57h+var_C0]; void *
0x14008ba97  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14008ba9c  nop
0x14008ba9d  cmp     qword ptr [rax+18h], 7
0x14008baa2  jbe     short loc_14008BAA7
0x14008baa4  mov     rax, [rax]
0x14008baa7  mov     r8, rbx
0x14008baaa  mov     rdx, rax
0x14008baad  mov     rcx, rdi
0x14008bab0  mov     rax, r14
0x14008bab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bab8  mov     rcx, [rbp+5Fh]; this
0x14008babc  test    eax, eax
0x14008babe  jns     short loc_14008BAD5
0x14008bac0  mov     r9d, eax; char *
0x14008bac3  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008baca  mov     edx, 1FDh; void *
0x14008bacf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008bad5  lea     rcx, [rbp+57h+var_C0]
0x14008bad9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008bade  mov     rax, [rdi]
0x14008bae1  mov     r14, [rax+0A0h]
0x14008bae8  mov     rbx, [rbp+57h+var_78]
0x14008baec  lea     r8, ?METRIC_STARTTIME_RELATIVE@@3QBGB; "/starttime"
0x14008baf3  mov     rdx, rsi; Src
0x14008baf6  lea     rcx, [rbp+57h+var_C0]; void *
0x14008bafa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14008baff  nop
0x14008bb00  cmp     qword ptr [rax+18h], 7
0x14008bb05  jbe     short loc_14008BB0A
0x14008bb07  mov     rax, [rax]
0x14008bb0a  mov     r8, rbx
0x14008bb0d  mov     rdx, rax
0x14008bb10  mov     rcx, rdi
0x14008bb13  mov     rax, r14
0x14008bb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bb1b  mov     rcx, [rbp+5Fh]; this
0x14008bb1f  test    eax, eax
0x14008bb21  jns     short loc_14008BB38
0x14008bb23  mov     r9d, eax; char *
0x14008bb26  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14008bb2d  mov     edx, 202h; void *
0x14008bb32  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14008bb38  lea     rcx, [rbp+57h+var_C0]
0x14008bb3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14008bb41  mov     rax, [rdi]
0x14008bb44  mov     r14, [rax+0A0h]
0x14008bb4b  mov     rbx, [rbp+57h+var_70]
0x14008bb4f  lea     r8, ?METRIC_LASTCOMPUTEDTIME_RELATIVE@@3QBGB; "/lastcomputedtime"
0x14008bb56  mov     rdx, rsi; Src
0x14008bb59  lea     rcx, [rbp+57h+var_C0]; void *
0x14008bb5d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14008bb62  nop
0x14008bb63  cmp     qword ptr [rax+18h], 7
0x14008bb68  jbe     short loc_14008BB6D
0x14008bb6a  mov     rax, [rax]
0x14008bb6d  mov     r8, rbx
0x14008bb70  mov     rdx, rax
0x14008bb73  mov     rcx, rdi
0x14008bb76  mov     rax, r14
0x14008bb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008bb7e  mov     rcx, [rbp+5Fh]; this
0x14008bb82  test    eax, eax
  ... truncated ...
```
