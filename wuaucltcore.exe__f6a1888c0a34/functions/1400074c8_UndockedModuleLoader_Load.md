# UndockedModuleLoader::Load

- ea: `0x1400074c8`
- end: `0x140007a6a`
- name: `UndockedModuleLoader::Load`
- size: `1442`
- prototype: `__int64 __usercall@<rax>(wchar_t *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140008c78`

## callees

- `0x140002ac0`
- `0x140006f90`
- `0x14000713c`
- `0x140007320`
- `0x1400074c8`
- `0x140007a9c`
- `0x140009084`
- `0x1400090f0`
- `0x140009214`
- `0x140009340`
- `0x14000b1cc`
- `0x14000b1f4`
- `0x14000b4c8`
- `0x14000bb30`
- `0x14000fd28`
- `0x140010f3c`
- `0x1400110ac`
- `0x1400111a4`
- `0x1400112c0`
- `0x14001aa60`
- `0x14001ad2c`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400079ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400079ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400079e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400079e1`

## string_xrefs

- `0x140007a4a`: `C:\__w\1\s\src\inc\UndockedUpdateStack.hpp`
- `0x140007706`: `UUS: Session=%ws, Module=%ws, Version=%ws, Path=%ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall UndockedModuleLoader::Load(wchar_t *a1, _WORD *a2, __int64 a3, __int64 *a4, uus::Session **a5)
{
  const wchar_t *v7; // r14
  uus::Session **v8; // r13
  __int64 v9; // rdx
  int v10; // esi
  __int64 v11; // r15
  uus::Session *v12; // rax
  uus::Session *v13; // rax
  void (__fastcall ***v14)(_QWORD, __int64); // rcx
  __int64 v15; // rcx
  const wchar_t *v16; // rax
  void **v17; // rdx
  void *FullPath; // rax
  int *v19; // rcx
  __int128 *v20; // rax
  __int64 v21; // rcx
  uus::Session *v22; // rdi
  int v23; // eax
  unsigned int v24; // r8d
  const char *v25; // r9
  int v26; // edx
  const wchar_t *v27; // rcx
  int *v28; // rax
  int v29; // eax
  int v30; // eax
  unsigned int v31; // r8d
  int v32; // eax
  wil::details::in1diag3 *v33; // rcx
  __int64 v34; // rdx
  void *v35; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v38; // [rsp+0h] [rbp-168h] BYREF
  int v39[2]; // [rsp+20h] [rbp-148h]
  const wchar_t *v40; // [rsp+28h] [rbp-140h]
  LPVOID v41; // [rsp+30h] [rbp-138h]
  _WORD *v42; // [rsp+38h] [rbp-130h]
  __int128 *v43; // [rsp+40h] [rbp-128h]
  int *v44; // [rsp+48h] [rbp-120h]
  int v45; // [rsp+50h] [rbp-118h]
  uus::Session *v46; // [rsp+58h] [rbp-110h]
  uus::Session **v47; // [rsp+60h] [rbp-108h]
  __int64 v48; // [rsp+68h] [rbp-100h] BYREF
  __int128 v49; // [rsp+70h] [rbp-F8h]
  __int128 v50; // [rsp+80h] [rbp-E8h]
  __int64 v51; // [rsp+90h] [rbp-D8h]
  __int64 v52; // [rsp+98h] [rbp-D0h]
  uus::Session *v53; // [rsp+A0h] [rbp-C8h] BYREF
  wchar_t *v54; // [rsp+A8h] [rbp-C0h]
  LPVOID lpMem; // [rsp+B0h] [rbp-B8h] BYREF
  void *Src[2]; // [rsp+B8h] [rbp-B0h] BYREF
  __int128 v57; // [rsp+C8h] [rbp-A0h]
  __int128 v58; // [rsp+D8h] [rbp-90h]
  int v59[4]; // [rsp+E8h] [rbp-80h] BYREF
  __m128i v60; // [rsp+F8h] [rbp-70h]
  __int128 v61; // [rsp+108h] [rbp-60h] BYREF
  __m128i si128; // [rsp+118h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v7 = a1;
  v54 = a1;
  v8 = a5;
  v47 = a5;
  if ( !a1 || !*a1 )
  {
    v9 = 39;
    goto LABEL_51;
  }
  if ( !a2 || !*a2 )
  {
    v9 = 40;
    goto LABEL_51;
  }
  if ( !a5 )
  {
    v9 = 41;
LABEL_51:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
      (const char *)0x80070057LL,
      v39[0]);
    return 2147942487LL;
  }
  try
  {
    *a5 = 0;
    v10 = 0;
    v46 = 0;
    v11 = -1;
    v51 = -1;
    v52 = 0;
    lpMem = 0;
    v61 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v61) = 0;
    *(_OWORD *)v59 = 0;
    v60 = si128;
    LOWORD(v59[0]) = 0;
    v45 = 0;
    if ( !*a4 )
    {
      v12 = (uus::Session *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v53 = v12;
      v13 = v12 ? uus::Session::Session(v12, v7) : 0LL;
      v14 = (void (__fastcall ***)(_QWORD, __int64))*a4;
      *a4 = (__int64)v13;
      if ( v14 )
        (**v14)(v14, 1);
    }
    v15 = *(_QWORD *)(*a4 + 8);
    if ( v15 )
      v16 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15);
    else
      v16 = L"0.0.0.0";
    *(_OWORD *)Src = 0;
    v57 = 0;
    do
      ++v11;
    while ( v16[v11] );
    std::wstring::_Construct<1,wchar_t const *>(Src, v16);
    v17 = Src;
    if ( *((_QWORD *)&v57 + 1) > 7u )
      v17 = (void **)Src[0];
    std::wstring::assign(&v61, v17);
    std::wstring::~wstring(Src);
    FullPath = uus::Session::GetFullPath(*a4, Src, (__int64)a2);
    std::filesystem::path::operator=(v59, FullPath);
    std::wstring::~wstring(Src);
    v45 = 1;
    v19 = v59;
    if ( v60.m128i_i64[1] > 7uLL )
      v19 = *(int **)v59;
    v20 = &v61;
    if ( si128.m128i_i64[1] > 7uLL )
      v20 = (__int128 *)v61;
    v44 = v19;
    v43 = v20;
    v42 = a2;
    v41 = (LPVOID)v7;
    v40 = L"UUS: Session=%ws, Module=%ws, Version=%ws, Path=%ws";
    *(_QWORD *)v39 = 0;
    WUTrace(0, 0, 32, 4);
    v21 = *(_QWORD *)(*a4 + 8);
    if ( !v21 )
    {
      v22 = 0;
      v46 = 0;
LABEL_28:
      v10 = -2147418113;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
        (const char *)0x8000FFFFLL,
        v39[0]);
      goto LABEL_56;
    }
    v53 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, uus::Session **))(*(_QWORD *)v21 + 48LL))(
            v21,
            a2,
            0,
            &v53);
    if ( v23 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1F4,
        (unsigned int)"C:\\__w\\1\\s\\src\\inc\\UndockedUpdateStack.hpp",
        (const char *)(unsigned int)v23,
        v39[0]);
    v22 = v53;
    v46 = v53;
    if ( !v53 )
      goto LABEL_28;
  }
  catch ( ... )
  {
    LODWORD(v53) = wil::details::in1diag3::Log_CaughtException(retaddr, &v38, v24, v25);
    v45 |= 8u;
    v10 = (int)v53;
    v22 = v46;
    v26 = v45;
    v7 = v54;
    v8 = v47;
    goto LABEL_30;
  }
LABEL_56:
  v26 = 1;
LABEL_30:
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v27 = (const wchar_t *)&v61;
  if ( si128.m128i_i64[1] > 7uLL )
    v27 = (const wchar_t *)v61;
  v28 = v59;
  if ( v60.m128i_i64[1] > 7uLL )
    v28 = *(int **)v59;
  v40 = v27;
  *(_QWORD *)v39 = v28;
  v29 = UndockedComponentInfo::Init(&v48, (unsigned int)v10, v26 | (((v10 >> 31) & 0xEu) + 2), v7);
  if ( v29 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
      (const char *)(unsigned int)v29,
      v39[0]);
  Src[0] = &lpMem;
  Src[1] = 0;
  LOBYTE(v57) = 1;
  v30 = UndockedComponentInfo::ToString((UndockedComponentInfo *)&v48, (wchar_t **)&Src[1]);
  if ( v30 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
      (const char *)(unsigned int)v30,
      v39[0]);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(Src);
  v41 = lpMem;
  v40 = L"Load undocked module: %ws";
  v39[0] = v10;
  WUTrace(0, 0, 32, ((v10 >> 31) & 0xFFFFFFFD) + 4);
  if ( v10 >= 0 )
    goto LABEL_45;
  Src[1] = 0;
  v57 = 0;
  v58 = 0;
  Src[0] = &UndockedComponentLoadFailedEvent::`vftable';
  v32 = UndockedComponentLoadEvent::Init((UndockedComponentLoadEvent *)Src, (const struct UndockedComponentInfo *)&v48);
  v33 = retaddr;
  if ( v32 < 0 )
  {
    v34 = 181;
LABEL_43:
    wil::details::in1diag3::_Log_Hr(
      v33,
      (void *)v34,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\inc\\UndockedModuleLoader.h",
      (const char *)(unsigned int)v32,
      v39[0]);
    goto LABEL_44;
  }
  v32 = UndockedComponentLoadFailedEvent::FireAsimovEvent((UndockedComponentLoadFailedEvent *)Src, 0, 0);
  v33 = retaddr;
  if ( v32 < 0 )
  {
    v34 = 183;
    goto LABEL_43;
  }
LABEL_44:
  UndockedComponentInfo::~UndockedComponentInfo((UndockedComponentInfo *)&Src[1]);
LABEL_45:
  if ( v10 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, (void *)0xC6, v31, (const char *)(unsigned int)v10, v39[0]);
  UndockedComponentInfo::~UndockedComponentInfo((UndockedComponentInfo *)&v48);
  std::wstring::~wstring(v59);
  std::wstring::~wstring(&v61);
  *v8 = v22;
  v35 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v35);
  }
  return 0;
}

```

## disassembly

```asm
0x1400074c8  push    rbx
0x1400074ca  push    rsi
0x1400074cb  push    rdi
0x1400074cc  push    r12
0x1400074ce  push    r13
0x1400074d0  push    r14
0x1400074d2  push    r15
0x1400074d4  sub     rsp, 130h
0x1400074db  mov     rax, cs:__security_cookie
0x1400074e2  xor     rax, rsp
0x1400074e5  mov     [rsp+168h+var_40], rax
0x1400074ed  mov     rdi, r9
0x1400074f0  mov     r12, rdx
0x1400074f3  mov     r14, rcx
0x1400074f6  mov     [rsp+168h+var_C0], rcx
0x1400074fe  mov     r13, [rsp+168h+arg_20]
0x140007506  mov     [rsp+168h+var_108], r13
0x14000750b  xor     ebx, ebx
0x14000750d  test    rcx, rcx
0x140007510  jz      loc_140007A01
0x140007516  cmp     [rcx], bx
0x140007519  jz      loc_140007A01
0x14000751f  test    rdx, rdx
0x140007522  jz      loc_1400079FA
0x140007528  cmp     [rdx], bx
0x14000752b  jz      loc_1400079FA
0x140007531  test    r13, r13
0x140007534  jnz     short loc_14000753E
0x140007536  lea     edx, [rbx+29h]
0x140007539  jmp     loc_140007A06
0x14000753e  mov     [r13+0], rbx
0x140007542  mov     esi, ebx
0x140007544  mov     [rsp+168h+var_110], rbx
0x140007549  or      r15, 0FFFFFFFFFFFFFFFFh
0x14000754d  mov     [rsp+168h+var_D8], r15
0x140007555  mov     [rsp+168h+var_D0], rbx
0x14000755d  mov     [rsp+168h+lpMem], rbx
0x140007565  xorps   xmm0, xmm0
0x140007568  movups  [rsp+168h+var_60], xmm0
0x140007570  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140007578  movdqu  [rsp+168h+var_50], xmm1
0x140007581  mov     word ptr [rsp+168h+var_60], bx
0x140007589  movups  xmmword ptr [rsp+168h+var_80], xmm0
0x140007591  movdqu  [rsp+168h+var_70], xmm1
0x14000759a  mov     word ptr [rsp+168h+var_80], bx
0x1400075a2  mov     [rsp+168h+var_118], ebx
0x1400075a6  cmp     [r9], rbx
0x1400075a9  jnz     short loc_1400075F3
0x1400075ab  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400075b2  lea     ecx, [r15+11h]; unsigned __int64
0x1400075b6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400075bb  mov     [rsp+168h+var_C8], rax
0x1400075c3  test    rax, rax
0x1400075c6  jz      short loc_1400075D5
0x1400075c8  mov     rdx, r14; wchar_t *
0x1400075cb  mov     rcx, rax; this
0x1400075ce  call    ??0Session@uus@@QEAA@PEB_W@Z; uus::Session::Session(wchar_t const *)
0x1400075d3  jmp     short loc_1400075D8
0x1400075d5  mov     rax, rbx
0x1400075d8  mov     rcx, [rdi]
0x1400075db  mov     [rdi], rax
0x1400075de  test    rcx, rcx
0x1400075e1  jz      short loc_1400075F3
0x1400075e3  mov     rax, [rcx]
0x1400075e6  mov     edx, 1
0x1400075eb  mov     rax, [rax]
0x1400075ee  call    _guard_dispatch_icall
0x1400075f3  mov     rax, [rdi]
0x1400075f6  mov     rcx, [rax+8]
0x1400075fa  test    rcx, rcx
0x1400075fd  jz      short loc_14000760D
0x1400075ff  mov     rax, [rcx]
0x140007602  mov     rax, [rax+20h]
0x140007606  call    _guard_dispatch_icall
0x14000760b  jmp     short loc_140007614
0x14000760d  lea     rax, a0000; "0.0.0.0"
0x140007614  xorps   xmm0, xmm0
0x140007617  movups  xmmword ptr [rsp+168h+Src], xmm0
0x14000761f  xorps   xmm1, xmm1
0x140007622  movdqu  [rsp+168h+var_A0], xmm1
0x14000762b  inc     r15
0x14000762e  cmp     [rax+r15*2], bx
0x140007633  jnz     short loc_14000762B
0x140007635  mov     r8, r15
0x140007638  mov     rdx, rax
0x14000763b  lea     rcx, [rsp+168h+Src]
0x140007643  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140007648  nop
0x140007649  lea     rdx, [rsp+168h+Src]
0x140007651  cmp     qword ptr [rsp+168h+var_A0+8], 7
0x14000765a  cmova   rdx, [rsp+168h+Src]; Src
0x140007663  mov     r8, qword ptr [rsp+168h+var_A0]
0x14000766b  lea     rcx, [rsp+168h+var_60]; void *
0x140007673  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x140007678  nop
0x140007679  lea     rcx, [rsp+168h+Src]
0x140007681  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140007686  mov     r8, r12
0x140007689  lea     rdx, [rsp+168h+Src]
0x140007691  mov     rcx, [rdi]
0x140007694  call    ?GetFullPath@Session@uus@@QEBA?AVpath@filesystem@std@@PEB_W@Z; uus::Session::GetFullPath(wchar_t const *)
0x140007699  mov     rdx, rax
0x14000769c  lea     rcx, [rsp+168h+var_80]
0x1400076a4  call    ??4path@filesystem@std@@QEAAAEAV012@$$QEAV012@@Z; std::filesystem::path::operator=(std::filesystem::path &&)
0x1400076a9  lea     rcx, [rsp+168h+Src]
0x1400076b1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400076b6  mov     [rsp+168h+var_118], 1
0x1400076be  lea     rcx, [rsp+168h+var_80]
0x1400076c6  cmp     qword ptr [rsp+168h+var_70+8], 7
0x1400076cf  cmova   rcx, qword ptr [rsp+168h+var_80]
0x1400076d8  lea     rax, [rsp+168h+var_60]
0x1400076e0  cmp     qword ptr [rsp+168h+var_50+8], 7
0x1400076e9  cmova   rax, qword ptr [rsp+168h+var_60]
0x1400076f2  mov     [rsp+168h+var_120], rcx
0x1400076f7  mov     [rsp+168h+var_128], rax
0x1400076fc  mov     [rsp+168h+var_130], r12
0x140007701  mov     [rsp+168h+var_138], r14
0x140007706  lea     rax, aUusSessionWsMo; "UUS: Session=%ws, Module=%ws, Version=%"...
0x14000770d  mov     [rsp+168h+var_140], rax
0x140007712  mov     qword ptr [rsp+168h+var_148], rbx; int
0x140007717  xor     edx, edx
0x140007719  xor     ecx, ecx
0x14000771b  lea     r9d, [rdx+4]
0x14000771f  lea     r8d, [rdx+20h]
0x140007723  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140007728  mov     rax, [rdi]
0x14000772b  mov     rcx, [rax+8]
0x14000772f  test    rcx, rcx
0x140007732  jnz     short loc_14000773E
0x140007734  mov     rdi, rbx
0x140007737  mov     [rsp+168h+var_110], rbx
0x14000773c  jmp     short loc_140007782
0x14000773e  mov     [rsp+168h+var_C8], rbx
0x140007746  mov     rax, [rcx]
0x140007749  lea     r9, [rsp+168h+var_C8]
0x140007751  xor     r8d, r8d
0x140007754  mov     rdx, r12
0x140007757  mov     rax, [rax+30h]
0x14000775b  call    _guard_dispatch_icall
0x140007760  mov     rcx, [rsp+168h]; this
0x140007768  test    eax, eax
0x14000776a  js      loc_140007A47
0x140007770  mov     rdi, [rsp+168h+var_C8]
0x140007778  mov     [rsp+168h+var_110], rdi
0x14000777d  test    rdi, rdi
0x140007780  jnz     short loc_1400077A4
0x140007782  mov     esi, 8000FFFFh
0x140007787  mov     rcx, [rsp+168h]; this
0x14000778f  mov     r9d, esi; char *
0x140007792  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x140007799  mov     edx, 7Ah ; 'z'; void *
0x14000779e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1400077a3  nop
0x1400077a4  mov     edx, 1
0x1400077a9  jmp     short loc_1400077CA
0x1400077ab  xor     ebx, ebx
0x1400077ad  mov     esi, dword ptr [rsp+168h+var_C8]
0x1400077b4  mov     rdi, [rsp+168h+var_110]
0x1400077b9  mov     edx, [rsp+168h+var_118]
0x1400077bd  mov     r14, [rsp+168h+var_C0]
0x1400077c5  mov     r13, [rsp+168h+var_108]
0x1400077ca  mov     r15d, esi
0x1400077cd  sar     r15d, 1Fh
0x1400077d1  mov     r8d, r15d
0x1400077d4  and     r8d, 0Eh
0x1400077d8  add     r8d, 2
0x1400077dc  or      r8d, edx
0x1400077df  mov     [rsp+168h+var_100], 0
0x1400077e8  xorps   xmm0, xmm0
0x1400077eb  movdqu  [rsp+168h+var_F8], xmm0
0x1400077f1  xorps   xmm1, xmm1
0x1400077f4  movdqu  [rsp+168h+var_E8], xmm1
0x1400077fd  lea     rcx, [rsp+168h+var_60]
0x140007805  cmp     qword ptr [rsp+168h+var_50+8], 7
0x14000780e  cmova   rcx, qword ptr [rsp+168h+var_60]
0x140007817  lea     rax, [rsp+168h+var_80]
0x14000781f  cmp     qword ptr [rsp+168h+var_70+8], 7
0x140007828  cmova   rax, qword ptr [rsp+168h+var_80]
0x140007831  mov     [rsp+168h+var_140], rcx
0x140007836  mov     qword ptr [rsp+168h+var_148], rax; int
0x14000783b  mov     r9, r14
0x14000783e  mov     edx, esi
0x140007840  lea     rcx, [rsp+168h+var_100]
0x140007845  call    ?Init@UndockedComponentInfo@@QEAAJJW4UndockedComponentLoadFlags@@PEB_W11@Z; UndockedComponentInfo::Init(long,UndockedComponentLoadFlags,wchar_t const *,wchar_t const *,wchar_t const *)
0x14000784a  mov     rcx, [rsp+168h]; this
0x140007852  test    eax, eax
0x140007854  jns     short loc_14000786A
0x140007856  mov     r9d, eax; char *
0x140007859  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x140007860  mov     edx, 0AAh; void *
0x140007865  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000786a  lea     rax, [rsp+168h+lpMem]
0x140007872  mov     [rsp+168h+Src], rax
0x14000787a  mov     [rsp+168h+Src+8], rbx
0x140007882  mov     byte ptr [rsp+168h+var_A0], 1
0x14000788a  lea     rdx, [rsp+168h+Src+8]; wchar_t **
0x140007892  lea     rcx, [rsp+168h+var_100]; this
0x140007897  call    ?ToString@UndockedComponentInfo@@QEAAJPEAPEA_W@Z; UndockedComponentInfo::ToString(wchar_t * *)
0x14000789c  mov     rcx, [rsp+168h]; this
0x1400078a4  test    eax, eax
0x1400078a6  jns     short loc_1400078BC
0x1400078a8  mov     r9d, eax; char *
0x1400078ab  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x1400078b2  mov     edx, 0ABh; void *
0x1400078b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400078bc  lea     rcx, [rsp+168h+Src]
0x1400078c4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)
0x1400078c9  and     r15d, 0FFFFFFFDh
0x1400078cd  lea     r9d, [r15+4]
0x1400078d1  mov     rax, [rsp+168h+lpMem]
0x1400078d9  mov     [rsp+168h+var_138], rax
0x1400078de  lea     rax, aLoadUndockedMo; "Load undocked module: %ws"
0x1400078e5  mov     [rsp+168h+var_140], rax
0x1400078ea  mov     [rsp+168h+var_148], esi; int
0x1400078ee  xor     edx, edx
0x1400078f0  xor     ecx, ecx
0x1400078f2  lea     r8d, [rdx+20h]
0x1400078f6  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400078fb  test    esi, esi
0x1400078fd  jns     loc_14000799A
0x140007903  mov     [rsp+168h+Src+8], 0
0x14000790f  xorps   xmm0, xmm0
0x140007912  movdqu  [rsp+168h+var_A0], xmm0
0x14000791b  xorps   xmm1, xmm1
0x14000791e  movdqu  [rsp+168h+var_90], xmm1
0x140007927  lea     rax, ??_7UndockedComponentLoadFailedEvent@@6B@; const UndockedComponentLoadFailedEvent::`vftable'
0x14000792e  mov     [rsp+168h+Src], rax
0x140007936  lea     rdx, [rsp+168h+var_100]; struct UndockedComponentInfo *
0x14000793b  lea     rcx, [rsp+168h+Src]; this
0x140007943  call    ?Init@UndockedComponentLoadEvent@@QEAAJAEBUUndockedComponentInfo@@@Z; UndockedComponentLoadEvent::Init(UndockedComponentInfo const &)
0x140007948  mov     rcx, [rsp+168h]
0x140007950  test    eax, eax
0x140007952  jns     short loc_14000795B
0x140007954  mov     edx, 0B5h
0x140007959  jmp     short loc_14000797E
0x14000795b  xor     r8d, r8d; char *
0x14000795e  xor     edx, edx; char *
0x140007960  lea     rcx, [rsp+168h+Src]; this
0x140007968  call    ?FireAsimovEvent@UndockedComponentLoadFailedEvent@@UEAAJPEBD0@Z; UndockedComponentLoadFailedEvent::FireAsimovEvent(char const *,char const *)
0x14000796d  mov     rcx, [rsp+168h]; this
0x140007975  test    eax, eax
0x140007977  jns     short loc_14000798D
0x140007979  mov     edx, 0B7h; void *
0x14000797e  mov     r9d, eax; char *
0x140007981  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x140007988  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000798d  lea     rcx, [rsp+168h+Src+8]; this
0x140007995  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
0x14000799a  mov     rcx, [rsp+168h]; this
0x1400079a2  test    esi, esi
0x1400079a4  js      loc_140007A5C
0x1400079aa  lea     rcx, [rsp+168h+var_100]; this
0x1400079af  call    ??1UndockedComponentInfo@@QEAA@XZ; UndockedComponentInfo::~UndockedComponentInfo(void)
0x1400079b4  nop
0x1400079b5  lea     rcx, [rsp+168h+var_80]
0x1400079bd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400079c2  nop
0x1400079c3  lea     rcx, [rsp+168h+var_60]
0x1400079cb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400079d0  mov     [r13+0], rdi
0x1400079d4  mov     rdi, [rsp+168h+lpMem]
0x1400079dc  test    rdi, rdi
0x1400079df  jz      short loc_1400079F6
0x1400079e1  call    cs:__imp_GetProcessHeap
0x1400079e7  mov     rcx, rax; hHeap
0x1400079ea  mov     r8, rdi; lpMem
0x1400079ed  xor     edx, edx; dwFlags
0x1400079ef  call    cs:__imp_HeapFree
0x1400079f5  nop
0x1400079f6  xor     eax, eax
0x1400079f8  jmp     short loc_140007A24
0x1400079fa  mov     edx, 28h ; '('
0x1400079ff  jmp     short loc_140007A06
0x140007a01  mov     edx, 27h ; '''; void *
0x140007a06  mov     ebx, 80070057h
0x140007a0b  mov     r9d, ebx; char *
0x140007a0e  lea     r8, aCW1SSrcClientI; "C:\\__w\\1\\s\\src\\Client\\inc\\Undock"...
0x140007a15  mov     rcx, [rsp+168h]; this
0x140007a1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007a22  mov     eax, ebx
0x140007a24  mov     rcx, [rsp+168h+var_40]
0x140007a2c  xor     rcx, rsp; StackCookie
0x140007a2f  call    __security_check_cookie
0x140007a34  add     rsp, 130h
0x140007a3b  pop     r15
0x140007a3d  pop     r14
0x140007a3f  pop     r13
0x140007a41  pop     r12
0x140007a43  pop     rdi
0x140007a44  pop     rsi
0x140007a45  pop     rbx
0x140007a46  retn
0x140007a47  mov     r9d, eax; char *
0x140007a4a  lea     r8, aCW1SSrcIncUndo; "C:\\__w\\1\\s\\src\\inc\\UndockedUpdate"...
0x140007a51  mov     edx, 1F4h; void *
0x140007a56  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140007a5c  mov     r9d, esi; char *
0x140007a5f  mov     edx, 0C6h; void *
0x140007a64  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
