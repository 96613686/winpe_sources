# RADIUSAccounting::UpdateAccountingAttributesWithStatistics(void)

- ea: `0x18006145c`
- end: `0x18006192b`
- name: `?UpdateAccountingAttributesWithStatistics@RADIUSAccounting@@IEAAKXZ`
- size: `1231`
- prototype: `unsigned int __fastcall(RADIUSAccounting *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1800605b0`
- `0x180060f70`

## callees

- `0x180007794`
- `0x1800077bc`
- `0x18006145c`
- `0x180065b9c`
- `0x180065d28`
- `0x180066384`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800614b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800614b9`

## string_xrefs

- `0x18006186d`: `Update Statistics in Accouting attributes`

## pseudocode

```c
__int64 __fastcall RADIUSAccounting::UpdateAccountingAttributesWithStatistics(RADIUSAccounting *this)
{
  unsigned __int64 v2; // r12
  unsigned __int64 v3; // rax
  DWORD v4; // esi
  PVOID *v5; // rcx
  __int64 *v6; // rbx
  __int64 v7; // rdx
  unsigned int v8; // r15d
  __int64 v9; // rcx
  unsigned int v10; // r15d
  unsigned int v11; // r15d
  __int64 v12; // rcx
  _DWORD *v13; // rax
  _DWORD *v14; // rax
  _DWORD *v15; // rax
  _DWORD *v16; // rax
  _DWORD *v17; // rax
  size_t Size; // [rsp+20h] [rbp-E0h]
  size_t Sizea; // [rsp+20h] [rbp-E0h]
  size_t Sizeb; // [rsp+20h] [rbp-E0h]
  size_t Sizec; // [rsp+20h] [rbp-E0h]
  size_t Sized; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v26[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+44h] [rbp-BCh]
  unsigned int v28; // [rsp+48h] [rbp-B8h]
  unsigned int v29; // [rsp+4Ch] [rbp-B4h]
  unsigned int v30; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v32[2044]; // [rsp+F4h] [rbp-Ch] BYREF

  v24 = 164;
  v31 = 0;
  LODWORD(v2) = 0;
  memset_0(v32, 0, sizeof(v32));
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = *((_QWORD *)this + 6);
  if ( *(_QWORD *)&SystemTimeAsFileTime > v3 && v3 )
    v2 = (*(_QWORD *)&SystemTimeAsFileTime - v3) / 0x989680;
  v4 = ((__int64 (__fastcall *)(_QWORD, _BYTE *, int *))xmmword_1800AA960)(
         *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 112LL) + 16LL),
         v26,
         &v24);
  if ( v4 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (_QWORD)xmmword_1800AABC0 )
    {
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gBaseTemplateFunc)(
        gBaseEtwContext,
        xmmword_1800AABC0,
        L"Failed to get Statistics for this connection");
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    v6 = (__int64 *)((char *)this + 40);
LABEL_36:
    if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x20000000) != 0 && *((_BYTE *)v5 + 25) )
      WPP_SF_d(v5[2], 44, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids, v4);
    if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
    {
      LOWORD(v31) = 0;
      FormatRRASErrorString(&v31, L"Failed with error: %u", v4);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gBaseTemplateFunc)(
        gBaseEtwContext,
        *((_QWORD *)&xmmword_1800AABC0 + 1),
        &v31);
    }
    RasAuthAttributeDestroy((_DWORD *)*v6);
    *v6 = 0;
    return v4;
  }
  if ( !*((_BYTE *)this + 32) )
  {
    v6 = (__int64 *)((char *)this + 40);
    if ( *((_QWORD *)this + 5) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
      }
      if ( (_QWORD)xmmword_1800AABC0 )
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gBaseTemplateFunc)(
          gBaseEtwContext,
          xmmword_1800AABC0,
          L"Inserting Statistics in Accouting attributes");
      v7 = *v6;
      v8 = 0;
      if ( *(_DWORD *)*v6 )
      {
        do
          ++v8;
        while ( *(_DWORD *)(v7 + 16LL * v8) );
      }
      v9 = 2LL * v8;
      *(_DWORD *)(v7 + 8 * v9) = -1;
      *(_DWORD *)(*v6 + 8 * v9 + 4) = 0;
      *(_QWORD *)(*v6 + 8 * v9 + 8) = 0;
      LODWORD(Size) = 4;
      v4 = RasAuthAttributeInsert(v8, *v6, 46, 0, Size, (LPCWCH)(unsigned int)v2);
      if ( !v4 )
      {
        v10 = v8 + 1;
        LODWORD(Sizea) = 4;
        v4 = RasAuthAttributeInsert(v10, *v6, 43, 0, Sizea, (LPCWCH)v27);
        if ( !v4 )
        {
          LODWORD(Sizeb) = 4;
          v4 = RasAuthAttributeInsert(v10 + 1, *v6, 42, 0, Sizeb, (LPCWCH)v28);
          if ( !v4 )
          {
            v11 = v10 + 2;
            LODWORD(Sizec) = 4;
            v4 = RasAuthAttributeInsert(v11, *v6, 48, 0, Sizec, (LPCWCH)v29);
            if ( !v4 )
            {
              LODWORD(Sized) = 4;
              v4 = RasAuthAttributeInsert(v11 + 1, *v6, 47, 0, Sized, (LPCWCH)v30);
              if ( !v4 )
              {
                v12 = 2LL * (v11 + 2);
                *(_DWORD *)(*v6 + 8 * v12) = 0;
                *(_DWORD *)(*v6 + 8 * v12 + 4) = 0;
                *(_QWORD *)(*v6 + 8 * v12 + 8) = 0;
                *((_BYTE *)this + 32) = 1;
                return v4;
              }
            }
          }
        }
      }
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (_QWORD)xmmword_1800AABC0 )
      {
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gBaseTemplateFunc)(
          gBaseEtwContext,
          xmmword_1800AABC0,
          L"AccountingAttributes are NULL");
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      v4 = 13;
    }
    goto LABEL_36;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids);
  }
  if ( *((_QWORD *)&xmmword_1800AABC0 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gBaseTemplateFunc)(
      gBaseEtwContext,
      *((_QWORD *)&xmmword_1800AABC0 + 1),
      L"Update Statistics in Accouting attributes");
  v13 = RasAuthAttributeGet(46, *((_QWORD *)this + 5));
  if ( v13 )
    *((_QWORD *)v13 + 1) = (unsigned int)v2;
  v14 = RasAuthAttributeGet(43, *((_QWORD *)this + 5));
  if ( v14 )
    *((_QWORD *)v14 + 1) = v27;
  v15 = RasAuthAttributeGet(42, *((_QWORD *)this + 5));
  if ( v15 )
    *((_QWORD *)v15 + 1) = v28;
  v16 = RasAuthAttributeGet(48, *((_QWORD *)this + 5));
  if ( v16 )
    *((_QWORD *)v16 + 1) = v29;
  v17 = RasAuthAttributeGet(47, *((_QWORD *)this + 5));
  if ( v17 )
    *((_QWORD *)v17 + 1) = v30;
  return v4;
}

```

## disassembly

```asm
0x18006145c  push    rbp
0x18006145e  push    rbx
0x18006145f  push    rsi
0x180061460  push    rdi
0x180061461  push    r12
0x180061463  push    r13
0x180061465  push    r14
0x180061467  push    r15
0x180061469  lea     rbp, [rsp-808h]
0x180061471  sub     rsp, 908h
0x180061478  mov     rax, cs:__security_cookie
0x18006147f  xor     rax, rsp
0x180061482  mov     [rbp+840h+var_50], rax
0x180061489  mov     rdi, rcx
0x18006148c  mov     [rsp+940h+var_910], 0A4h
0x180061494  xor     r13d, r13d
0x180061497  lea     rcx, [rbp+840h+var_84C]; void *
0x18006149b  xor     edx, edx; Val
0x18006149d  mov     [rbp+840h+var_850], r13d
0x1800614a1  mov     r8d, 7FCh; Size
0x1800614a7  mov     r12d, r13d
0x1800614aa  call    memset_0
0x1800614af  lea     rcx, [rsp+940h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800614b4  mov     qword ptr [rsp+940h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800614b9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800614bf  mov     rax, [rdi+30h]
0x1800614c3  mov     rcx, qword ptr [rsp+940h+SystemTimeAsFileTime.dwLowDateTime]
0x1800614c8  cmp     rcx, rax
0x1800614cb  jbe     short loc_1800614E9
0x1800614cd  test    rax, rax
0x1800614d0  jz      short loc_1800614E9
0x1800614d2  sub     rcx, rax
0x1800614d5  mov     rax, 0D6BF94D5E57A42BDh
0x1800614df  mul     rcx
0x1800614e2  mov     r12, rdx
0x1800614e5  shr     r12, 17h
0x1800614e9  mov     rcx, [rdi+8]
0x1800614ed  lea     r8, [rsp+940h+var_910]
0x1800614f2  mov     rax, qword ptr cs:xmmword_1800AA960
0x1800614f9  lea     rdx, [rsp+940h+var_900]
0x1800614fe  mov     rcx, [rcx+70h]
0x180061502  mov     rcx, [rcx+10h]
0x180061506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006150b  mov     esi, eax
0x18006150d  test    eax, eax
0x18006150f  jz      short loc_180061585
0x180061511  mov     rcx, cs:WPP_GLOBAL_Control
0x180061518  lea     r14, WPP_GLOBAL_Control
0x18006151f  cmp     rcx, r14
0x180061522  jz      short loc_18006154F
0x180061524  test    dword ptr [rcx+1Ch], 20000000h
0x18006152b  jz      short loc_18006154F
0x18006152d  cmp     byte ptr [rcx+19h], 1
0x180061531  jb      short loc_18006154F
0x180061533  mov     rcx, [rcx+10h]
0x180061537  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x18006153e  mov     edx, 28h ; '('
0x180061543  call    WPP_SF_
0x180061548  mov     rcx, cs:WPP_GLOBAL_Control
0x18006154f  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x180061556  test    rdx, rdx
0x180061559  jz      short loc_18006157C
0x18006155b  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x180061562  lea     r8, aFailedToGetSta; "Failed to get Statistics for this conne"...
0x180061569  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180061570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061575  mov     rcx, cs:WPP_GLOBAL_Control
0x18006157c  lea     rbx, [rdi+28h]
0x180061580  jmp     loc_1800617A8
0x180061585  cmp     [rdi+20h], r13b
0x180061589  jnz     loc_180061823
0x18006158f  lea     rbx, [rdi+28h]
0x180061593  cmp     [rbx], r13
0x180061596  jnz     short loc_18006160D
0x180061598  mov     rcx, cs:WPP_GLOBAL_Control
0x18006159f  lea     r14, WPP_GLOBAL_Control
0x1800615a6  cmp     rcx, r14
0x1800615a9  jz      short loc_1800615D6
0x1800615ab  test    dword ptr [rcx+1Ch], 20000000h
0x1800615b2  jz      short loc_1800615D6
0x1800615b4  cmp     byte ptr [rcx+19h], 1
0x1800615b8  jb      short loc_1800615D6
0x1800615ba  mov     rcx, [rcx+10h]
0x1800615be  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x1800615c5  mov     edx, 29h ; ')'
0x1800615ca  call    WPP_SF_
0x1800615cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800615d6  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x1800615dd  test    rdx, rdx
0x1800615e0  jz      short loc_180061603
0x1800615e2  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x1800615e9  lea     r8, aAccountingattr; "AccountingAttributes are NULL"
0x1800615f0  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800615f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800615fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180061603  mov     esi, 0Dh
0x180061608  jmp     loc_1800617A8
0x18006160d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061614  lea     r14, WPP_GLOBAL_Control
0x18006161b  cmp     rcx, r14
0x18006161e  jz      short loc_180061644
0x180061620  test    dword ptr [rcx+1Ch], 20000000h
0x180061627  jz      short loc_180061644
0x180061629  cmp     byte ptr [rcx+19h], 3
0x18006162d  jb      short loc_180061644
0x18006162f  mov     rcx, [rcx+10h]
0x180061633  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x18006163a  mov     edx, 2Ah ; '*'
0x18006163f  call    WPP_SF_
0x180061644  mov     rdx, qword ptr cs:xmmword_1800AABC0
0x18006164b  test    rdx, rdx
0x18006164e  jz      short loc_18006166A
0x180061650  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x180061657  lea     r8, aInsertingStati; "Inserting Statistics in Accouting attri"...
0x18006165e  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180061665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006166a  mov     rdx, [rbx]
0x18006166d  mov     r15d, r13d
0x180061670  cmp     [rdx], r13d
0x180061673  jz      short loc_180061684
0x180061675  inc     r15d
0x180061678  mov     eax, r15d
0x18006167b  add     rax, rax
0x18006167e  cmp     [rdx+rax*8], r13d
0x180061682  jnz     short loc_180061675
0x180061684  mov     ecx, r15d
0x180061687  xor     r9d, r9d; int
0x18006168a  add     rcx, rcx
0x18006168d  mov     dword ptr [rdx+rcx*8], 0FFFFFFFFh
0x180061694  mov     rax, [rbx]
0x180061697  mov     [rax+rcx*8+4], r13d
0x18006169c  mov     rax, [rbx]
0x18006169f  mov     [rax+rcx*8+8], r13
0x1800616a4  mov     ecx, r15d; int
0x1800616a7  mov     rdx, [rbx]; int
0x1800616aa  mov     eax, r12d
0x1800616ad  mov     r12d, 4
0x1800616b3  mov     [rsp+940h+lpWideCharStr], rax; lpWideCharStr
0x1800616b8  mov     dword ptr [rsp+940h+Size], r12d; Size
0x1800616bd  lea     r8d, [r12+2Ah]; int
0x1800616c2  call    RasAuthAttributeInsert
0x1800616c7  mov     esi, eax
0x1800616c9  test    eax, eax
0x1800616cb  jnz     loc_1800617A1
0x1800616d1  mov     eax, dword ptr [rsp+940h+var_8FC]
0x1800616d5  lea     r8d, [r12+27h]; int
0x1800616da  mov     rdx, [rbx]; int
0x1800616dd  inc     r15d
0x1800616e0  mov     [rsp+940h+lpWideCharStr], rax; lpWideCharStr
0x1800616e5  mov     ecx, r15d; int
0x1800616e8  xor     r9d, r9d; int
0x1800616eb  mov     dword ptr [rsp+940h+Size], r12d; Size
0x1800616f0  call    RasAuthAttributeInsert
0x1800616f5  mov     esi, eax
0x1800616f7  test    eax, eax
0x1800616f9  jnz     loc_1800617A1
0x1800616ff  mov     eax, dword ptr [rsp+940h+var_8FC+4]
0x180061703  lea     r8d, [r12+26h]; int
0x180061708  mov     rdx, [rbx]; int
0x18006170b  lea     ecx, [r15+1]; int
0x18006170f  mov     [rsp+940h+lpWideCharStr], rax; lpWideCharStr
0x180061714  xor     r9d, r9d; int
0x180061717  mov     dword ptr [rsp+940h+Size], r12d; Size
0x18006171c  call    RasAuthAttributeInsert
0x180061721  mov     esi, eax
0x180061723  test    eax, eax
0x180061725  jnz     short loc_1800617A1
0x180061727  mov     eax, dword ptr [rsp+940h+var_8F4]
0x18006172b  lea     r8d, [r12+2Ch]; int
0x180061730  mov     rdx, [rbx]; int
0x180061733  add     r15d, 2
0x180061737  mov     [rsp+940h+lpWideCharStr], rax; lpWideCharStr
0x18006173c  mov     ecx, r15d; int
0x18006173f  xor     r9d, r9d; int
0x180061742  mov     dword ptr [rsp+940h+Size], r12d; Size
0x180061747  call    RasAuthAttributeInsert
0x18006174c  mov     esi, eax
0x18006174e  test    eax, eax
0x180061750  jnz     short loc_1800617A1
0x180061752  mov     eax, dword ptr [rsp+940h+var_8F4+4]
0x180061756  lea     r8d, [r12+2Bh]; int
0x18006175b  mov     rdx, [rbx]; int
0x18006175e  lea     ecx, [r15+1]; int
0x180061762  mov     [rsp+940h+lpWideCharStr], rax; lpWideCharStr
0x180061767  xor     r9d, r9d; int
0x18006176a  mov     dword ptr [rsp+940h+Size], r12d; Size
0x18006176f  call    RasAuthAttributeInsert
0x180061774  mov     esi, eax
0x180061776  test    eax, eax
0x180061778  jnz     short loc_1800617A1
0x18006177a  mov     rax, [rbx]
0x18006177d  lea     ecx, [r15+2]
0x180061781  add     rcx, rcx
0x180061784  mov     [rax+rcx*8], r13d
0x180061788  mov     rax, [rbx]
0x18006178b  mov     [rax+rcx*8+4], r13d
0x180061790  mov     rax, [rbx]
0x180061793  mov     [rax+rcx*8+8], r13
0x180061798  mov     byte ptr [rdi+20h], 1
0x18006179c  jmp     loc_180061906
0x1800617a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800617a8  cmp     rcx, r14
0x1800617ab  jz      short loc_1800617D4
0x1800617ad  test    dword ptr [rcx+1Ch], 20000000h
0x1800617b4  jz      short loc_1800617D4
0x1800617b6  cmp     byte ptr [rcx+19h], 1
0x1800617ba  jb      short loc_1800617D4
0x1800617bc  mov     rcx, [rcx+10h]
0x1800617c0  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x1800617c7  mov     edx, 2Ch ; ','
0x1800617cc  mov     r9d, esi
0x1800617cf  call    WPP_SF_d
0x1800617d4  cmp     qword ptr cs:xmmword_1800AABC0+8, r13
0x1800617db  jz      short loc_180061813
0x1800617dd  mov     r8d, esi
0x1800617e0  mov     word ptr [rbp+840h+var_850], r13w
0x1800617e5  lea     rdx, aFailedWithErro; "Failed with error: %u"
0x1800617ec  lea     rcx, [rbp+840h+var_850]
0x1800617f0  call    FormatRRASErrorString
0x1800617f5  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x1800617fc  lea     r8, [rbp+840h+var_850]
0x180061800  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x180061807  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18006180e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061813  mov     rcx, [rbx]; hMem
0x180061816  call    RasAuthAttributeDestroy
0x18006181b  mov     [rbx], r13
0x18006181e  jmp     loc_180061906
0x180061823  mov     rcx, cs:WPP_GLOBAL_Control
0x18006182a  lea     r14, WPP_GLOBAL_Control
0x180061831  cmp     rcx, r14
0x180061834  jz      short loc_18006185A
0x180061836  test    dword ptr [rcx+1Ch], 20000000h
0x18006183d  jz      short loc_18006185A
0x18006183f  cmp     byte ptr [rcx+19h], 3
0x180061843  jb      short loc_18006185A
0x180061845  mov     rcx, [rcx+10h]
0x180061849  lea     r8, WPP_4d685ec1d3383c2f1e3c51cfc2fa9b4d_Traceguids
0x180061850  mov     edx, 2Bh ; '+'
0x180061855  call    WPP_SF_
0x18006185a  mov     rdx, qword ptr cs:xmmword_1800AABC0+8
0x180061861  test    rdx, rdx
0x180061864  jz      short loc_180061880
0x180061866  mov     rcx, cs:?gBaseEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gBaseEtwContext
0x18006186d  lea     r8, aUpdateStatisti; "Update Statistics in Accouting attribut"...
0x180061874  mov     rax, cs:?gBaseTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gBaseTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18006187b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061880  mov     rdx, [rdi+28h]
0x180061884  mov     ecx, 2Eh ; '.'
0x180061889  call    RasAuthAttributeGet
0x18006188e  test    rax, rax
0x180061891  jz      short loc_18006189A
0x180061893  mov     ecx, r12d
0x180061896  mov     [rax+8], rcx
0x18006189a  mov     rdx, [rdi+28h]
0x18006189e  mov     ecx, 2Bh ; '+'
0x1800618a3  call    RasAuthAttributeGet
0x1800618a8  test    rax, rax
0x1800618ab  jz      short loc_1800618B5
0x1800618ad  mov     ecx, dword ptr [rsp+940h+var_8FC]
0x1800618b1  mov     [rax+8], rcx
0x1800618b5  mov     rdx, [rdi+28h]
0x1800618b9  mov     ecx, 2Ah ; '*'
0x1800618be  call    RasAuthAttributeGet
0x1800618c3  test    rax, rax
0x1800618c6  jz      short loc_1800618D0
0x1800618c8  mov     ecx, dword ptr [rsp+940h+var_8FC+4]
0x1800618cc  mov     [rax+8], rcx
0x1800618d0  mov     rdx, [rdi+28h]
0x1800618d4  mov     ecx, 30h ; '0'
0x1800618d9  call    RasAuthAttributeGet
0x1800618de  test    rax, rax
0x1800618e1  jz      short loc_1800618EB
0x1800618e3  mov     ecx, dword ptr [rsp+940h+var_8F4]
0x1800618e7  mov     [rax+8], rcx
0x1800618eb  mov     rdx, [rdi+28h]
0x1800618ef  mov     ecx, 2Fh ; '/'
0x1800618f4  call    RasAuthAttributeGet
0x1800618f9  test    rax, rax
0x1800618fc  jz      short loc_180061906
0x1800618fe  mov     ecx, dword ptr [rsp+940h+var_8F4+4]
0x180061902  mov     [rax+8], rcx
0x180061906  mov     eax, esi
0x180061908  mov     rcx, [rbp+840h+var_50]
0x18006190f  xor     rcx, rsp; StackCookie
0x180061912  call    __security_check_cookie
0x180061917  add     rsp, 908h
0x18006191e  pop     r15
0x180061920  pop     r14
0x180061922  pop     r13
0x180061924  pop     r12
0x180061926  pop     rdi
0x180061927  pop     rsi
0x180061928  pop     rbx
0x180061929  pop     rbp
0x18006192a  retn
```
