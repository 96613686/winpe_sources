# CSrmFunctionTracerBase::GetCurrentContexts(CSrmAutoPWSZ &)

- ea: `0x180017158`
- end: `0x180017819`
- name: `?GetCurrentContexts@CSrmFunctionTracerBase@@QEAAXAEAVCSrmAutoPWSZ@@@Z`
- size: `1729`
- prototype: `void __fastcall(CSrmFunctionTracerBase *this, LPVOID *)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800180a0`
- `0x180018f68`
- `0x1800191ec`

## callees

- `0x180001898`
- `0x180002238`
- `0x1800054cc`
- `0x1800083e0`
- `0x18000d368`
- `0x1800100b4`
- `0x1800103a8`
- `0x1800104a8`
- `0x18001623c`
- `0x180016564`
- `0x180016f34`
- `0x180017158`
- `0x180017e90`
- `0x180018f68`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `msvcrt!_snwscanf_s` at `0x180017431`
- `msvcrt!_snwscanf_s` at `0x180017431`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017471`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800174c4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800175e1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800176df`
- `msvcrt!??3@YAXPEAX@Z` at `0x180017471`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800174c4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800175e1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800176df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017754`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800172e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017754`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001722d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001722d`

## pseudocode

```c
void __fastcall CSrmFunctionTracerBase::GetCurrentContexts(CSrmFunctionTracerBase *this, LPVOID *a2)
{
  CSrmFunctionTracerBase *v2; // rbx
  unsigned int v3; // r15d
  _WORD *v4; // r12
  __int64 v5; // rax
  __int64 *v6; // rcx
  __int64 v7; // rdx
  _WORD *v8; // r9
  __int16 v9; // r8
  _WORD *v10; // rcx
  __int64 v11; // r8
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // r14
  char *v14; // r13
  __int64 v15; // rsi
  _QWORD *v16; // rdx
  __int64 v17; // rcx
  size_t v18; // rdx
  void **StringW; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rsi
  int v23; // r15d
  void **v24; // rcx
  __int64 v25; // r9
  int v26; // edi
  int i; // ebx
  UINT v28; // edx
  __int64 v29; // rax
  const unsigned __int16 *v30; // rdx
  LPVOID *v31; // rsi
  char Hr; // al
  int v33; // eax
  char v34; // al
  _WORD *v35; // [rsp+30h] [rbp-2E8h] BYREF
  UINT uID; // [rsp+38h] [rbp-2E0h] BYREF
  unsigned int v37; // [rsp+3Ch] [rbp-2DCh]
  int v38; // [rsp+40h] [rbp-2D8h]
  int v39; // [rsp+44h] [rbp-2D4h]
  int v40; // [rsp+48h] [rbp-2D0h] BYREF
  __int64 v41; // [rsp+50h] [rbp-2C8h]
  _QWORD *v42; // [rsp+58h] [rbp-2C0h]
  unsigned __int64 v43; // [rsp+60h] [rbp-2B8h]
  CSrmFunctionTracerBase *v44; // [rsp+68h] [rbp-2B0h]
  LPVOID *v45; // [rsp+70h] [rbp-2A8h]
  _QWORD v46[3]; // [rsp+78h] [rbp-2A0h] BYREF
  int v47; // [rsp+90h] [rbp-288h]
  int v48; // [rsp+94h] [rbp-284h]
  int v49; // [rsp+98h] [rbp-280h]
  _DWORD v50[26]; // [rsp+A0h] [rbp-278h] BYREF
  void *Src[2]; // [rsp+108h] [rbp-210h] BYREF
  __int64 v52; // [rsp+118h] [rbp-200h]
  unsigned __int64 v53; // [rsp+120h] [rbp-1F8h]
  void *v54[2]; // [rsp+130h] [rbp-1E8h] BYREF
  __int64 v55; // [rsp+140h] [rbp-1D8h]
  unsigned __int64 v56; // [rsp+148h] [rbp-1D0h]
  void *v57[3]; // [rsp+158h] [rbp-1C0h] BYREF
  unsigned __int64 v58; // [rsp+170h] [rbp-1A8h]
  void *v59[3]; // [rsp+180h] [rbp-198h] BYREF
  unsigned __int64 v60; // [rsp+198h] [rbp-180h]
  void **v61; // [rsp+1B0h] [rbp-168h] BYREF
  unsigned int v62; // [rsp+1B8h] [rbp-160h]
  _QWORD v63[16]; // [rsp+260h] [rbp-B8h] BYREF

  v45 = a2;
  v2 = this;
  v44 = this;
  v3 = 0;
  v37 = 0;
  v35 = 0;
  v42 = v46;
  v46[0] = L"base\\fs\\fsrm\\utilities\\inc\\srmstr.h";
  v46[1] = L"SrmDuplicateStr";
  v46[2] = L"INCLSTRH";
  v47 = 78;
  v48 = 17;
  v49 = 255;
  v50[24] = 0x1000000;
  memset_0(v50, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v61, (const struct CSrmDebugInfo *)v46, 0);
  v4 = CoTaskMemAlloc(2u);
  if ( !v4 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v61, -2147024882);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v61);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v61, 0x57, Hr, 0);
  }
  v62 = 0;
  v5 = 2147483646;
  v6 = &qword_180023088;
  v7 = 1;
  v8 = v4;
  do
  {
    if ( !v5 )
      break;
    v9 = *(_WORD *)v6;
    if ( !*(_WORD *)v6 )
      break;
    v6 = (__int64 *)((char *)v6 + 2);
    *v8++ = v9;
    --v5;
    --v7;
  }
  while ( v7 );
  v10 = v8 - 1;
  if ( v7 )
    v10 = v8;
  *v10 = 0;
  v62 = v7 == 0 ? 0x8007007A : 0;
  if ( !v7 )
  {
    v33 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v61);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v61, v33);
    v34 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v61);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v61, 0x59, v34, 0);
  }
  v62 = v7 == 0 ? 0x8007007A : 0;
  v61 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v61);
  CoTaskMemFree(0);
  v35 = v4;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    `eh vector constructor iterator'(v63, 0x28u, 3u, std::wstring::wstring, (void (*)(void *))std::wstring::~wstring);
    v26 = 0;
    v38 = 0;
    while ( v26 < 3 )
    {
      while ( v2 )
      {
        v11 = v26;
        v41 = 32LL * v26;
        v12 = (*(_QWORD *)((char *)v2 + v41 + 80) - *(_QWORD *)((char *)v2 + v41 + 72)) / 80LL;
        v42 = (_QWORD *)v12;
        v13 = 0;
        v43 = 0;
        while ( v13 < v12 )
        {
          v14 = (char *)&v63[5 * v11];
          std::wstring::operator+=(v14, (char *)L"\n   ", v11, v25);
          v15 = 80 * v13;
          v16 = (_QWORD *)(80 * v13 + *((_QWORD *)v2 + 4 * v26 + 9));
          if ( *(_QWORD *)(80 * v13 + *(_QWORD *)((char *)v2 + v41 + 72) + 16) )
          {
            if ( v16[3] >= 8u )
              v16 = (_QWORD *)*v16;
            if ( *(_WORD *)v16 == 31 )
            {
              uID = 0;
              v56 = 7;
              v55 = 0;
              LOWORD(v54[0]) = 0;
              v17 = v15 + *(_QWORD *)((char *)v2 + v41 + 72);
              v18 = *(_QWORD *)(v17 + 16);
              if ( *(_QWORD *)(v17 + 24) >= 8u )
                v17 = *(_QWORD *)v17;
              if ( _snwscanf_s((const wchar_t *const)v17, v18, &Format, &uID) )
              {
                StringW = (void **)CSrmResource::LoadStringW(v57, uID);
                std::wstring::assign(v54, StringW);
                if ( v58 >= 8 )
                  operator delete(v57[0]);
                v58 = 7;
                v57[2] = 0;
                LOWORD(v57[0]) = 0;
              }
              std::wstring::append(v14, v54, 0, -1);
              if ( v56 >= 8 )
                operator delete(v54[0]);
              v56 = 7;
              v55 = 0;
              LOWORD(v54[0]) = 0;
            }
            else
            {
              std::wstring::append(v14, 80 * v13 + *(_QWORD *)((char *)v2 + v41 + 72), 0, -1);
            }
            v22 = *(_QWORD *)((char *)v2 + v41 + 72) + v15;
            v53 = 7;
            v52 = 0;
            LOWORD(Src[0]) = 0;
            v23 = v3 | 1;
            v37 = v23;
            if ( *(_QWORD *)(v22 + 56) != 5 )
            {
              LOBYTE(v20) = 1;
              if ( (unsigned __int8)std::wstring::_Grow(Src, *(_QWORD *)(v22 + 56) + 2LL, v20) )
              {
                v24 = Src;
                if ( v53 >= 8 )
                  v24 = (void **)Src[0];
                v52 = 0;
                *(_WORD *)v24 = 0;
              }
            }
            std::wstring::operator+=((char *)Src, (char *)L": ", v20, v21);
            std::wstring::append(Src, v22 + 40, 0, -1);
            std::wstring::append(v14, Src, 0, -1);
            v3 = v23 & 0xFFFFFFFE;
            v37 = v3;
            if ( v53 >= 8 )
              operator delete(Src[0]);
            v53 = 7;
            v52 = 0;
            LOWORD(Src[0]) = 0;
          }
          else
          {
            std::wstring::append(v14, v16 + 5, 0, -1);
          }
          v43 = ++v13;
          v12 = (unsigned __int64)v42;
          v11 = v26;
        }
        v2 = (CSrmFunctionTracerBase *)*((_QWORD *)v2 + 21);
      }
      v38 = ++v26;
      v2 = v44;
    }
    for ( i = 0; ; ++i )
    {
      v39 = i;
      if ( i >= 3 )
        break;
      if ( v63[5 * i + 2] )
      {
        CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&v35, L"\n\n");
        if ( i )
        {
          if ( i == 1 )
            v28 = 1003;
          else
            v28 = 1004;
        }
        else
        {
          v28 = 1002;
        }
        v29 = (__int64)CSrmResource::LoadStringW(v59, v28);
        if ( *(_QWORD *)(v29 + 24) >= 8u )
          v29 = *(_QWORD *)v29;
        CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&v35, (const unsigned __int16 *)v29);
        if ( v60 >= 8 )
          operator delete(v59[0]);
        v60 = 7;
        v59[2] = 0;
        LOWORD(v59[0]) = 0;
        v30 = (const unsigned __int16 *)&v63[5 * i];
        if ( *((_QWORD *)v30 + 3) >= 8u )
          v30 = *(const unsigned __int16 **)v30;
        CSrmAutoPWSZ::Append((CSrmAutoPWSZ *)&v35, v30);
        v4 = v35;
      }
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v40 = -2147024882;
      throw (long *)&v40;
    }
  }
  `eh vector destructor iterator'(v63, 0x28u, 3u, (void (*)(void *))std::wstring::~wstring);
  v31 = v45;
  CoTaskMemFree(*v45);
  v35 = 0;
  *v31 = v4;
  CoTaskMemFree(0);
  v35 = 0;
}

```

## disassembly

```asm
0x180017158  mov     r11, rsp
0x18001715b  mov     [r11+18h], rbx
0x18001715f  mov     [r11+20h], rsi
0x180017163  push    rdi
0x180017164  push    r12
0x180017166  push    r13
0x180017168  push    r14
0x18001716a  push    r15
0x18001716c  sub     rsp, 2F0h
0x180017173  mov     rax, cs:__security_cookie
0x18001717a  xor     rax, rsp
0x18001717d  mov     [rsp+318h+var_38], rax
0x180017185  mov     [rsp+318h+var_2A8], rdx
0x18001718a  mov     rbx, rcx
0x18001718d  mov     [rsp+318h+var_2B0], rcx
0x180017192  xor     r13d, r13d
0x180017195  mov     r15d, r13d
0x180017198  mov     [rsp+318h+var_2DC], r13d
0x18001719d  mov     [rsp+318h+var_2E8], r13
0x1800171a2  lea     rax, [rsp+318h+var_2A0]
0x1800171a7  mov     [rsp+318h+var_2C0], rax
0x1800171ac  lea     rax, aBaseFsFsrmUtil_0; "base\\fs\\fsrm\\utilities\\inc\\srmstr."...
0x1800171b3  mov     [rsp+318h+var_2A0], rax
0x1800171b8  lea     rax, aSrmduplicatest; "SrmDuplicateStr"
0x1800171bf  mov     [r11-298h], rax
0x1800171c6  lea     rax, aInclstrh; "INCLSTRH"
0x1800171cd  mov     [r11-290h], rax
0x1800171d4  mov     [rsp+318h+var_288], 4Eh ; 'N'
0x1800171df  mov     [rsp+318h+var_284], 11h
0x1800171ea  mov     [rsp+318h+var_280], 0FFh
0x1800171f5  mov     [rsp+318h+var_218], 1000000h
0x180017200  xor     edx, edx; Val
0x180017202  lea     r8d, [r13+60h]; Size
0x180017206  lea     rcx, [r11-278h]; void *
0x18001720d  call    memset_0
0x180017212  nop
0x180017213  xor     r8d, r8d
0x180017216  lea     rdx, [rsp+318h+var_2A0]
0x18001721b  lea     rcx, [rsp+318h+var_168]
0x180017223  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180017228  nop
0x180017229  lea     ecx, [r13+2]; cb
0x18001722d  call    cs:__imp_CoTaskMemAlloc
0x180017233  mov     r12, rax
0x180017236  mov     eax, [rsp+318h+var_160]
0x18001723d  mov     [rsp+318h+var_160], eax
0x180017244  test    r12, r12
0x180017247  jz      loc_1800177A1
0x18001724d  mov     [rsp+318h+var_160], r13d
0x180017255  mov     eax, 7FFFFFFEh
0x18001725a  lea     rcx, qword_180023088
0x180017261  lea     edx, [r13+1]
0x180017265  mov     r9, r12
0x180017268  test    rax, rax
0x18001726b  jz      short loc_18001728C
0x18001726d  movzx   r8d, word ptr [rcx]
0x180017271  test    r8w, r8w
0x180017275  jz      short loc_18001728C
0x180017277  add     rcx, 2
0x18001727b  mov     [r9], r8w
0x18001727f  add     r9, 2
0x180017283  dec     rax
0x180017286  sub     rdx, 1
0x18001728a  jnz     short loc_180017268
0x18001728c  mov     rax, rdx
0x18001728f  neg     rax
0x180017292  sbb     r8d, r8d
0x180017295  not     r8d
0x180017298  and     r8d, 8007007Ah
0x18001729f  lea     rcx, [r9-2]
0x1800172a3  test    rdx, rdx
0x1800172a6  cmovnz  rcx, r9
0x1800172aa  mov     [rcx], r13w
0x1800172ae  mov     [rsp+318h+var_160], r8d
0x1800172b6  jz      loc_1800177D8
0x1800172bc  mov     [rsp+318h+var_160], r8d
0x1800172c4  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x1800172cb  mov     [rsp+318h+var_168], rax
0x1800172d3  lea     rcx, [rsp+318h+var_168]; this
0x1800172db  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800172e0  xor     ecx, ecx; pv
0x1800172e2  call    cs:__imp_CoTaskMemFree
0x1800172e8  mov     [rsp+318h+var_2E8], r13
0x1800172ed  mov     [rsp+318h+var_2E8], r12
0x1800172f2  lea     r14, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800172f9  mov     [rsp+318h+var_2F8], r14; void (*)(void *)
0x1800172fe  lea     r9, ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x180017305  mov     edx, 28h ; '('; unsigned __int64
0x18001730a  lea     r8d, [rdx-25h]; unsigned __int64
0x18001730e  lea     rcx, [rsp+318h+var_B8]; void *
0x180017316  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001731b  nop
0x18001731c  mov     edi, r13d
0x18001731f  mov     [rsp+318h+var_2D8], r13d
0x180017324  cmp     edi, 3
0x180017327  jge     loc_180017650
0x18001732d  test    rbx, rbx
0x180017330  jz      loc_180017640
0x180017336  movsxd  r8, edi
0x180017339  mov     rax, r8
0x18001733c  shl     rax, 5
0x180017340  mov     [rsp+318h+var_2C8], rax
0x180017345  mov     rcx, [rax+rbx+50h]
0x18001734a  sub     rcx, [rax+rbx+48h]
0x18001734f  mov     rax, 6666666666666667h
0x180017359  imul    rcx
0x18001735c  mov     rcx, rdx
0x18001735f  sar     rcx, 5
0x180017363  mov     rax, rcx
0x180017366  shr     rax, 3Fh
0x18001736a  add     rcx, rax
0x18001736d  mov     [rsp+318h+var_2C0], rcx
0x180017372  mov     r14, r13
0x180017375  mov     [rsp+318h+var_2B8], r13
0x18001737a  cmp     r14, rcx
0x18001737d  jnb     loc_180017634
0x180017383  lea     rax, [r8+r8*4]
0x180017387  lea     r13, [rsp+318h+var_B8]
0x18001738f  lea     r13, [r13+rax*8+0]
0x180017394  lea     rdx, asc_180023EB0; "\n   "
0x18001739b  mov     rcx, r13; Src
0x18001739e  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x1800173a3  lea     rsi, [r14+r14*4]
0x1800173a7  shl     rsi, 4
0x1800173ab  mov     r8, [rsp+318h+var_2C8]
0x1800173b0  mov     r10, [r8+rbx+48h]
0x1800173b5  add     r10, rsi
0x1800173b8  lea     rcx, [r14+r14*4]
0x1800173bc  shl     rcx, 4
0x1800173c0  movsxd  rax, edi
0x1800173c3  shl     rax, 5
0x1800173c7  mov     rdx, [rax+rbx+48h]
0x1800173cc  add     rdx, rcx
0x1800173cf  xor     eax, eax
0x1800173d1  cmp     [r10+10h], rax
0x1800173d5  jbe     loc_180017609
0x1800173db  cmp     qword ptr [rdx+18h], 8
0x1800173e0  jb      short loc_1800173E5
0x1800173e2  mov     rdx, [rdx]
0x1800173e5  cmp     word ptr [rdx], 1Fh
0x1800173e9  jnz     loc_1800174EE
0x1800173ef  mov     [rsp+318h+uID], eax
0x1800173f3  mov     [rsp+318h+var_1D0], 7
0x1800173ff  mov     [rsp+318h+var_1D8], rax
0x180017407  mov     word ptr [rsp+318h+var_1E8], ax
0x18001740f  mov     rcx, [r8+rbx+48h]
0x180017414  add     rcx, rsi
0x180017417  mov     rdx, [rcx+10h]; BufferCount
0x18001741b  cmp     qword ptr [rcx+18h], 8
0x180017420  jb      short loc_180017425
0x180017422  mov     rcx, [rcx]; Buffer
0x180017425  lea     r9, [rsp+318h+uID]
0x18001742a  lea     r8, Format; Format
0x180017431  call    cs:__imp__snwscanf_s
0x180017437  test    eax, eax
0x180017439  jz      short loc_180017499
0x18001743b  mov     edx, [rsp+318h+uID]; uID
0x18001743f  lea     rcx, [rsp+318h+var_1C0]; Src
0x180017447  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x18001744c  nop
0x18001744d  mov     rdx, rax; Src
0x180017450  lea     rcx, [rsp+318h+var_1E8]; void *
0x180017458  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x18001745d  nop
0x18001745e  cmp     [rsp+318h+var_1A8], 8
0x180017467  jb      short loc_180017477
0x180017469  mov     rcx, [rsp+318h+var_1C0]
0x180017471  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180017477  mov     [rsp+318h+var_1A8], 7
0x180017483  mov     [rsp+318h+var_1B0], 0
0x18001748f  xor     eax, eax
0x180017491  mov     word ptr [rsp+318h+var_1C0], ax
0x180017499  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001749d  xor     r8d, r8d
0x1800174a0  lea     rdx, [rsp+318h+var_1E8]
0x1800174a8  mov     rcx, r13
0x1800174ab  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800174b0  nop
0x1800174b1  cmp     [rsp+318h+var_1D0], 8
0x1800174ba  jb      short loc_1800174CA
0x1800174bc  mov     rcx, [rsp+318h+var_1E8]
0x1800174c4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800174ca  mov     [rsp+318h+var_1D0], 7
0x1800174d6  mov     [rsp+318h+var_1D8], 0
0x1800174e2  xor     eax, eax
0x1800174e4  mov     word ptr [rsp+318h+var_1E8], ax
0x1800174ec  jmp     short loc_180017500
0x1800174ee  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800174f2  xor     r8d, r8d
0x1800174f5  mov     rdx, r10
0x1800174f8  mov     rcx, r13
0x1800174fb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180017500  mov     rax, [rsp+318h+var_2C8]
0x180017505  add     rsi, [rax+rbx+48h]
0x18001750a  mov     [rsp+318h+var_1F8], 7
0x180017516  mov     [rsp+318h+var_200], 0
0x180017522  xor     eax, eax
0x180017524  mov     word ptr [rsp+318h+Src], ax
0x18001752c  or      r15d, 1
0x180017530  mov     [rsp+318h+var_2DC], r15d
0x180017535  mov     rdx, [rsi+38h]
0x180017539  add     rdx, 2
0x18001753d  cmp     rdx, 7
0x180017541  jz      short loc_180017582
0x180017543  mov     r8b, 1
0x180017546  lea     rcx, [rsp+318h+Src]
0x18001754e  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180017553  test    al, al
0x180017555  jz      short loc_180017582
0x180017557  lea     rcx, [rsp+318h+Src]
0x18001755f  cmp     [rsp+318h+var_1F8], 8
0x180017568  cmovnb  rcx, [rsp+318h+Src]
0x180017571  mov     [rsp+318h+var_200], 0
0x18001757d  xor     eax, eax
0x18001757f  mov     [rcx], ax
0x180017582  lea     rdx, asc_180023EBC; ": "
0x180017589  lea     rcx, [rsp+318h+Src]; Src
0x180017591  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180017596  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001759a  xor     r8d, r8d
0x18001759d  lea     rdx, [rsi+28h]
0x1800175a1  lea     rcx, [rsp+318h+Src]
0x1800175a9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800175ae  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800175b2  xor     r8d, r8d
0x1800175b5  lea     rdx, [rsp+318h+Src]
0x1800175bd  mov     rcx, r13
0x1800175c0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800175c5  and     r15d, 0FFFFFFFEh
0x1800175c9  mov     [rsp+318h+var_2DC], r15d
0x1800175ce  cmp     [rsp+318h+var_1F8], 8
0x1800175d7  jb      short loc_1800175E7
0x1800175d9  mov     rcx, [rsp+318h+Src]
0x1800175e1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800175e7  mov     [rsp+318h+var_1F8], 7
0x1800175f3  xor     r13d, r13d
0x1800175f6  mov     [rsp+318h+var_200], r13
0x1800175fe  mov     word ptr [rsp+318h+Src], r13w
0x180017607  jmp     short loc_18001761F
0x180017609  add     rdx, 28h ; '('
0x18001760d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180017611  xor     r8d, r8d
0x180017614  mov     rcx, r13
0x180017617  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001761c  xor     r13d, r13d
0x18001761f  inc     r14
0x180017622  mov     [rsp+318h+var_2B8], r14
0x180017627  mov     rcx, [rsp+318h+var_2C0]
0x18001762c  movsxd  r8, edi
0x18001762f  jmp     loc_18001737A
0x180017634  mov     rbx, [rbx+0A8h]
0x18001763b  jmp     loc_18001732D
0x180017640  inc     edi
0x180017642  mov     [rsp+318h+var_2D8], edi
0x180017646  mov     rbx, [rsp+318h+var_2B0]
0x18001764b  jmp     loc_180017324
0x180017650  mov     ebx, r13d
0x180017653  mov     esi, 3ECh
0x180017658  mov     [rsp+318h+var_2D4], ebx
0x18001765c  cmp     ebx, 3
0x18001765f  jge     loc_18001772E
0x180017665  movsxd  rax, ebx
0x180017668  lea     rdi, [rax+rax*4]
0x18001766c  cmp     [rsp+rdi*8+318h+var_A8], r13
0x180017674  jbe     loc_180017727
0x18001767a  lea     rdx, asc_180023EC4; "\n\n"
0x180017681  lea     rcx, [rsp+318h+var_2E8]; this
0x180017686  call    ?Append@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::Append(ushort const *)
0x18001768b  mov     ecx, ebx
0x18001768d  test    ebx, ebx
0x18001768f  jz      short loc_1800176A1
0x180017691  sub     ecx, 1
0x180017694  jz      short loc_18001769A
0x180017696  mov     edx, esi
0x180017698  jmp     short loc_1800176A6
0x18001769a  mov     edx, 3EBh
0x18001769f  jmp     short loc_1800176A6
0x1800176a1  mov     edx, 3EAh; uID
0x1800176a6  lea     rcx, [rsp+318h+var_198]; Src
0x1800176ae  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x1800176b3  nop
0x1800176b4  cmp     qword ptr [rax+18h], 8
0x1800176b9  jb      short loc_1800176BE
0x1800176bb  mov     rax, [rax]
0x1800176be  mov     rdx, rax; unsigned __int16 *
0x1800176c1  lea     rcx, [rsp+318h+var_2E8]; this
0x1800176c6  call    ?Append@CSrmAutoPWSZ@@QEAAXPEBG@Z; CSrmAutoPWSZ::Append(ushort const *)
0x1800176cb  nop
0x1800176cc  cmp     [rsp+318h+var_180], 8
0x1800176d5  jb      short loc_1800176E5
0x1800176d7  mov     rcx, [rsp+318h+var_198]
0x1800176df  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800176e5  mov     [rsp+318h+var_180], 7
0x1800176f1  mov     [rsp+318h+var_188], r13
0x1800176f9  mov     word ptr [rsp+318h+var_198], r13w
0x180017702  lea     rdx, [rsp+318h+var_B8]
0x18001770a  lea     rdx, [rdx+rdi*8]
0x18001770e  cmp     qword ptr [rdx+18h], 8
0x180017713  jb      short loc_180017718
0x180017715  mov     rdx, [rdx]; unsigned __int16 *
  ... truncated ...
```
