# VmMetricRepositoryUtilities::WriteMetric(VmRepository *,IVmMetricValue *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14007a050`
- end: `0x14007a71f`
- name: `?WriteMetric@VmMetricRepositoryUtilities@@SAXPEAVVmRepository@@PEAUIVmMetricValue@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1743`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14007b700`
- `0x14011a5c0`
- `0x14011a8e0`
- `0x140294f08`

## callees

- `0x14002fba8`
- `0x140031ca8`
- `0x14006af58`
- `0x14007a050`
- `0x14007a728`
- `0x14007a804`
- `0x140132960`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007a394`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14007a394`

## string_xrefs

- `0x14007a0f9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a129`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a159`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a189`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a1b9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a1e9`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a219`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a249`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a279`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a2ac`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a306`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a36e`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a3f0`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a453`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a4b6`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a519`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a57c`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a5df`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a659`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a6c1`: `onecore\vm\common\metrics\vmmetricrepositoryutilities.cpp`
- `0x14007a4df`: `/lastcomputedtime`

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
  if ( (unsigned int)_o__wcsicmp(v59, &qword_1402E4D20) )
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
0x14007a050  push    rbp
0x14007a052  push    rbx
0x14007a053  push    rsi
0x14007a054  push    rdi
0x14007a055  push    r14
0x14007a057  lea     rbp, [rsp-37h]
0x14007a05c  sub     rsp, 0C0h
0x14007a063  mov     rax, cs:__security_cookie
0x14007a06a  xor     rax, rsp
0x14007a06d  mov     [rbp+57h+var_30], rax
0x14007a071  mov     rsi, r8
0x14007a074  mov     rbx, rdx
0x14007a077  mov     rdi, rcx
0x14007a07a  mov     [rbp+57h+var_80], 0
0x14007a082  mov     [rbp+57h+var_A0], 0
0x14007a089  mov     [rbp+57h+var_98], 0
0x14007a091  mov     [rbp+57h+var_88], 0
0x14007a099  mov     [rbp+57h+var_78], 0
0x14007a0a1  mov     [rbp+57h+var_70], 0
0x14007a0a9  mov     [rbp+57h+var_68], 0
0x14007a0b1  mov     [rbp+57h+var_90], 0
0x14007a0b9  xorps   xmm0, xmm0
0x14007a0bc  movdqa  xmmword ptr [rbp+57h+var_40.Data1], xmm0
0x14007a0c1  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14007a0c5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14007a0cd  movdqu  [rbp+57h+var_50], xmm1
0x14007a0d2  xor     eax, eax
0x14007a0d4  mov     [rbp+57h+var_60], ax
0x14007a0d8  mov     [rbp+57h+var_9C], eax
0x14007a0db  mov     rax, [rdx]
0x14007a0de  lea     rdx, [rbp+57h+var_80]
0x14007a0e2  mov     rcx, rbx
0x14007a0e5  mov     rax, [rax+20h]
0x14007a0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a0ee  mov     rcx, [rbp+5Fh]; this
0x14007a0f2  test    eax, eax
0x14007a0f4  jns     short loc_14007A10B
0x14007a0f6  mov     r9d, eax; char *
0x14007a0f9  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a100  mov     edx, 1DEh; void *
0x14007a105  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a10b  mov     rax, [rbx]
0x14007a10e  lea     rdx, [rbp+57h+var_A0]
0x14007a112  mov     rcx, rbx
0x14007a115  mov     rax, [rax+30h]
0x14007a119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a11e  mov     rcx, [rbp+5Fh]; this
0x14007a122  test    eax, eax
0x14007a124  jns     short loc_14007A13B
0x14007a126  mov     r9d, eax; char *
0x14007a129  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a130  mov     edx, 1DFh; void *
0x14007a135  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a13b  mov     rax, [rbx]
0x14007a13e  lea     rdx, [rbp+57h+var_98]
0x14007a142  mov     rcx, rbx
0x14007a145  mov     rax, [rax+38h]
0x14007a149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a14e  mov     rcx, [rbp+5Fh]; this
0x14007a152  test    eax, eax
0x14007a154  jns     short loc_14007A16B
0x14007a156  mov     r9d, eax; char *
0x14007a159  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a160  mov     edx, 1E0h; void *
0x14007a165  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a16b  mov     rax, [rbx]
0x14007a16e  lea     rdx, [rbp+57h+var_88]
0x14007a172  mov     rcx, rbx
0x14007a175  mov     rax, [rax+40h]
0x14007a179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a17e  mov     rcx, [rbp+5Fh]; this
0x14007a182  test    eax, eax
0x14007a184  jns     short loc_14007A19B
0x14007a186  mov     r9d, eax; char *
0x14007a189  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a190  mov     edx, 1E1h; void *
0x14007a195  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a19b  mov     rax, [rbx]
0x14007a19e  lea     rdx, [rbp+57h+var_78]
0x14007a1a2  mov     rcx, rbx
0x14007a1a5  mov     rax, [rax+48h]
0x14007a1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a1ae  mov     rcx, [rbp+5Fh]; this
0x14007a1b2  test    eax, eax
0x14007a1b4  jns     short loc_14007A1CB
0x14007a1b6  mov     r9d, eax; char *
0x14007a1b9  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a1c0  mov     edx, 1E2h; void *
0x14007a1c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a1cb  mov     rax, [rbx]
0x14007a1ce  lea     rdx, [rbp+57h+var_70]
0x14007a1d2  mov     rcx, rbx
0x14007a1d5  mov     rax, [rax+50h]
0x14007a1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a1de  mov     rcx, [rbp+5Fh]; this
0x14007a1e2  test    eax, eax
0x14007a1e4  jns     short loc_14007A1FB
0x14007a1e6  mov     r9d, eax; char *
0x14007a1e9  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a1f0  mov     edx, 1E3h; void *
0x14007a1f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a1fb  mov     rax, [rbx]
0x14007a1fe  lea     rdx, [rbp+57h+var_68]
0x14007a202  mov     rcx, rbx
0x14007a205  mov     rax, [rax+58h]
0x14007a209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a20e  mov     rcx, [rbp+5Fh]; this
0x14007a212  test    eax, eax
0x14007a214  jns     short loc_14007A22B
0x14007a216  mov     r9d, eax; char *
0x14007a219  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a220  mov     edx, 1E4h; void *
0x14007a225  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a22b  mov     rax, [rbx]
0x14007a22e  lea     rdx, [rbp+57h+var_90]
0x14007a232  mov     rcx, rbx
0x14007a235  mov     rax, [rax+68h]
0x14007a239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a23e  mov     rcx, [rbp+5Fh]; this
0x14007a242  test    eax, eax
0x14007a244  jns     short loc_14007A25B
0x14007a246  mov     r9d, eax; char *
0x14007a249  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a250  mov     edx, 1E5h; void *
0x14007a255  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a25b  mov     rax, [rbx]
0x14007a25e  lea     rdx, [rbp+57h+var_40]
0x14007a262  mov     rcx, rbx
0x14007a265  mov     rax, [rax+78h]
0x14007a269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a26e  mov     rcx, [rbp+5Fh]; this
0x14007a272  test    eax, eax
0x14007a274  jns     short loc_14007A28B
0x14007a276  mov     r9d, eax; char *
0x14007a279  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a280  mov     edx, 1E6h; void *
0x14007a285  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a28b  mov     rax, [rbx]
0x14007a28e  lea     rdx, [rbp+57h+var_9C]
0x14007a292  mov     rcx, rbx
0x14007a295  mov     rax, [rax+98h]
0x14007a29c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a2a1  mov     rcx, [rbp+5Fh]; this
0x14007a2a5  test    eax, eax
0x14007a2a7  jns     short loc_14007A2BE
0x14007a2a9  mov     r9d, eax; char *
0x14007a2ac  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a2b3  mov     edx, 1E7h; void *
0x14007a2b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a2be  mov     rax, [rdi]
0x14007a2c1  mov     r14, [rax+0A0h]
0x14007a2c8  mov     rbx, [rbp+57h+var_80]
0x14007a2cc  lea     r8, ?METRIC_VALUE_RELATIVE@@3QBGB; "/value"
0x14007a2d3  mov     rdx, rsi; Src
0x14007a2d6  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a2da  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a2df  nop
0x14007a2e0  cmp     qword ptr [rax+18h], 7
0x14007a2e5  jbe     short loc_14007A2EA
0x14007a2e7  mov     rax, [rax]
0x14007a2ea  mov     r8, rbx
0x14007a2ed  mov     rdx, rax
0x14007a2f0  mov     rcx, rdi
0x14007a2f3  mov     rax, r14
0x14007a2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a2fb  mov     rcx, [rbp+5Fh]; this
0x14007a2ff  test    eax, eax
0x14007a301  jns     short loc_14007A318
0x14007a303  mov     r9d, eax; char *
0x14007a306  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a30d  mov     edx, 1EBh; void *
0x14007a312  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a318  lea     rcx, [rbp+57h+var_C0]
0x14007a31c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a321  mov     rax, [rdi]
0x14007a324  mov     r14, [rax+0B0h]
0x14007a32b  xor     ebx, ebx
0x14007a32d  cmp     [rbp+57h+var_A0], 2
0x14007a331  setz    bl
0x14007a334  lea     r8, ?METRIC_ENABLED_RELATIVE@@3QBGB; "/enabled"
0x14007a33b  mov     rdx, rsi; Src
0x14007a33e  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a342  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a347  nop
0x14007a348  cmp     qword ptr [rax+18h], 7
0x14007a34d  jbe     short loc_14007A352
0x14007a34f  mov     rax, [rax]
0x14007a352  mov     r8d, ebx
0x14007a355  mov     rdx, rax
0x14007a358  mov     rcx, rdi
0x14007a35b  mov     rax, r14
0x14007a35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a363  mov     rcx, [rbp+5Fh]; this
0x14007a367  test    eax, eax
0x14007a369  jns     short loc_14007A380
0x14007a36b  mov     r9d, eax; char *
0x14007a36e  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a375  mov     edx, 1EFh; void *
0x14007a37a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a380  lea     rcx, [rbp+57h+var_C0]
0x14007a384  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a389  lea     rdx, qword_1402E4D20
0x14007a390  mov     rcx, [rbp+57h+var_98]
0x14007a394  call    cs:__imp__o__wcsicmp
0x14007a39b  nop     dword ptr [rax+rax+00h]
0x14007a3a0  test    eax, eax
0x14007a3a2  jz      loc_14007A46E
0x14007a3a8  mov     rax, [rdi]
0x14007a3ab  mov     r14, [rax+98h]
0x14007a3b2  mov     rbx, [rbp+57h+var_98]
0x14007a3b6  lea     r8, ?METRIC_BREAKDOWNDIMENSION_RELATIVE@@3QBGB; "/breakdowndimension"
0x14007a3bd  mov     rdx, rsi; Src
0x14007a3c0  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a3c4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a3c9  nop
0x14007a3ca  cmp     qword ptr [rax+18h], 7
0x14007a3cf  jbe     short loc_14007A3D4
0x14007a3d1  mov     rax, [rax]
0x14007a3d4  mov     r8, rbx
0x14007a3d7  mov     rdx, rax
0x14007a3da  mov     rcx, rdi
0x14007a3dd  mov     rax, r14
0x14007a3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a3e5  mov     rcx, [rbp+5Fh]; this
0x14007a3e9  test    eax, eax
0x14007a3eb  jns     short loc_14007A402
0x14007a3ed  mov     r9d, eax; char *
0x14007a3f0  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a3f7  mov     edx, 1F9h; void *
0x14007a3fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a402  lea     rcx, [rbp+57h+var_C0]
0x14007a406  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a40b  mov     rax, [rdi]
0x14007a40e  mov     r14, [rax+98h]
0x14007a415  mov     rbx, [rbp+57h+var_88]
0x14007a419  lea     r8, ?METRIC_BREAKDOWNVALUE_RELATIVE@@3QBGB; "/breakdownvalue"
0x14007a420  mov     rdx, rsi; Src
0x14007a423  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a427  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a42c  nop
0x14007a42d  cmp     qword ptr [rax+18h], 7
0x14007a432  jbe     short loc_14007A437
0x14007a434  mov     rax, [rax]
0x14007a437  mov     r8, rbx
0x14007a43a  mov     rdx, rax
0x14007a43d  mov     rcx, rdi
0x14007a440  mov     rax, r14
0x14007a443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a448  mov     rcx, [rbp+5Fh]; this
0x14007a44c  test    eax, eax
0x14007a44e  jns     short loc_14007A465
0x14007a450  mov     r9d, eax; char *
0x14007a453  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a45a  mov     edx, 1FDh; void *
0x14007a45f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a465  lea     rcx, [rbp+57h+var_C0]
0x14007a469  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a46e  mov     rax, [rdi]
0x14007a471  mov     r14, [rax+0A0h]
0x14007a478  mov     rbx, [rbp+57h+var_78]
0x14007a47c  lea     r8, ?METRIC_STARTTIME_RELATIVE@@3QBGB; "/starttime"
0x14007a483  mov     rdx, rsi; Src
0x14007a486  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a48a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a48f  nop
0x14007a490  cmp     qword ptr [rax+18h], 7
0x14007a495  jbe     short loc_14007A49A
0x14007a497  mov     rax, [rax]
0x14007a49a  mov     r8, rbx
0x14007a49d  mov     rdx, rax
0x14007a4a0  mov     rcx, rdi
0x14007a4a3  mov     rax, r14
0x14007a4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a4ab  mov     rcx, [rbp+5Fh]; this
0x14007a4af  test    eax, eax
0x14007a4b1  jns     short loc_14007A4C8
0x14007a4b3  mov     r9d, eax; char *
0x14007a4b6  lea     r8, aOnecoreVmCommo_94; "onecore\\vm\\common\\metrics\\vmmetricr"...
0x14007a4bd  mov     edx, 202h; void *
0x14007a4c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14007a4c8  lea     rcx, [rbp+57h+var_C0]
0x14007a4cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14007a4d1  mov     rax, [rdi]
0x14007a4d4  mov     r14, [rax+0A0h]
0x14007a4db  mov     rbx, [rbp+57h+var_70]
0x14007a4df  lea     r8, ?METRIC_LASTCOMPUTEDTIME_RELATIVE@@3QBGB; "/lastcomputedtime"
0x14007a4e6  mov     rdx, rsi; Src
0x14007a4e9  lea     rcx, [rbp+57h+var_C0]; void *
0x14007a4ed  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x14007a4f2  nop
0x14007a4f3  cmp     qword ptr [rax+18h], 7
0x14007a4f8  jbe     short loc_14007A4FD
0x14007a4fa  mov     rax, [rax]
0x14007a4fd  mov     r8, rbx
0x14007a500  mov     rdx, rax
0x14007a503  mov     rcx, rdi
0x14007a506  mov     rax, r14
0x14007a509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007a50e  mov     rcx, [rbp+5Fh]; this
0x14007a512  test    eax, eax
  ... truncated ...
```
