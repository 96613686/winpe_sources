# NtGdiGetPath

- ea: `0x14031b110`
- end: `0x14031b589`
- name: `NtGdiGetPath`
- size: `1145`
- prototype: `__int64 __fastcall(HDC, struct _POINTL *, char *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x140053654`
- `0x14007eef8`
- `0x140080fd4`
- `0x14011922c`
- `0x140119254`
- `0x1401fb8a4`
- `0x140219164`
- `0x14031b038`
- `0x14031b110`

## import_xrefs

- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031b3bf`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031b409`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031b47f`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031b4cf`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031b3bf`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031b409`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031b47f`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031b4cf`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031b450`
- `win32kbase!?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x14031b450`
- `win32kbase!EngSetLastError` at `0x14031b21b`
- `win32kbase!EngSetLastError` at `0x14031b36b`
- `win32kbase!EngSetLastError` at `0x14031b50e`
- `win32kbase!EngSetLastError` at `0x14031b529`
- `win32kbase!EngSetLastError` at `0x14031b550`
- `win32kbase!EngSetLastError` at `0x14031b21b`
- `win32kbase!EngSetLastError` at `0x14031b36b`
- `win32kbase!EngSetLastError` at `0x14031b50e`
- `win32kbase!EngSetLastError` at `0x14031b529`
- `win32kbase!EngSetLastError` at `0x14031b550`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14031b186`
- `win32kbase!?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z` at `0x14031b186`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x14031b2b6`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x14031b2cc`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x14031b2b6`
- `win32kbase!?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z` at `0x14031b2cc`
- `win32kbase!?bEnum@EPATHOBJ@@QEAAHPEAU_PATHDATA@@@Z` at `0x14031b32a`
- `win32kbase!?bEnum@EPATHOBJ@@QEAAHPEAU_PATHDATA@@@Z` at `0x14031b32a`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTFIX@@PEAU_POINTL@@_K@Z` at `0x14031b356`
- `win32kbase!?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTFIX@@PEAU_POINTL@@_K@Z` at `0x14031b356`
- `win32kbase!?cTotalPts@EPATHOBJ@@QEAAKXZ` at `0x14031b1dd`
- `win32kbase!?cTotalPts@EPATHOBJ@@QEAAKXZ` at `0x14031b1f5`
- `win32kbase!?cTotalPts@EPATHOBJ@@QEAAKXZ` at `0x14031b1dd`
- `win32kbase!?cTotalPts@EPATHOBJ@@QEAAKXZ` at `0x14031b1f5`
- `win32kbase!Win32FreePool` at `0x14031b4fb`
- `win32kbase!Win32FreePool` at `0x14031b4fb`

## pseudocode

```c
__int64 __fastcall NtGdiGetPath(HDC a1, struct _POINTL *a2, char *a3, unsigned int a4)
{
  __int64 v4; // rbx
  unsigned int v7; // edi
  __int64 v8; // r9
  char v9; // r12
  struct _POINTL *v10; // r13
  struct _POINTL *v11; // rax
  ULONG v12; // ecx
  char *v13; // r12
  char *v14; // rbx
  char flags; // dl
  ULONG v16; // ecx
  char v18; // [rsp+30h] [rbp-178h] BYREF
  char v19; // [rsp+31h] [rbp-177h] BYREF
  char v20[2]; // [rsp+32h] [rbp-176h] BYREF
  int v21; // [rsp+34h] [rbp-174h]
  char v22[8]; // [rsp+38h] [rbp-170h] BYREF
  const void **v23; // [rsp+40h] [rbp-168h] BYREF
  struct _POINTL *v24; // [rsp+48h] [rbp-160h] BYREF
  struct _PATHDATA v25; // [rsp+50h] [rbp-158h] BYREF
  __int64 v26; // [rsp+60h] [rbp-148h] BYREF
  struct _POINTL *v27; // [rsp+68h] [rbp-140h]
  char *v28; // [rsp+70h] [rbp-138h]
  void **v29; // [rsp+78h] [rbp-130h] BYREF
  char v30; // [rsp+80h] [rbp-128h]
  int v31; // [rsp+90h] [rbp-118h] BYREF
  __int64 v32; // [rsp+98h] [rbp-110h]
  DC *v33[14]; // [rsp+110h] [rbp-98h] BYREF

  v4 = a4;
  v7 = -1;
  v21 = -1;
  APIDCOBJ::APIDCOBJ((APIDCOBJ *)v33, a1);
  if ( !v33[0] || (int)v4 < 0 )
    goto LABEL_46;
  if ( !(unsigned int)DC::bInactive(v33[0]) )
  {
    v16 = 1003;
LABEL_47:
    EngSetLastError(v16);
    goto LABEL_48;
  }
  DC::QuickInitXform(v8, &v26, 1026);
  if ( !v26 )
  {
LABEL_46:
    v16 = 87;
    goto LABEL_47;
  }
  XEPATHOBJ::XEPATHOBJ((XEPATHOBJ *)&v31, *((struct HPATH__ **)v33[0] + 25));
  if ( v32 )
  {
    v9 = 0;
    if ( (unsigned int)Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline() )
    {
      v7 = EPATHOBJ::cTotalPts((EPATHOBJ *)&v31);
      if ( v7 > 0x7FFFFFFF )
      {
        v21 = -1;
        EngSetLastError(0x216u);
        v9 = 1;
      }
      v21 = v7;
    }
    else
    {
      v7 = EPATHOBJ::cTotalPts((EPATHOBJ *)&v31);
      v21 = v7;
    }
    if ( (_DWORD)v4 && !v9 )
    {
      if ( (int)v4 >= (int)v7 && (unsigned __int64)(int)v4 <= 0x1FFFFFFF )
      {
        v25 = 0;
        v18 = 0;
        v10 = 0;
        v27 = 0;
        v24 = 0;
        v23 = (const void **)&v24;
        wil::scope_exit__UMPDOBJ::BackPropagateLargeBitmapBits_::_2_::_lambda_1___(&v29, &v23);
        v31 &= ~8u;
        *(_QWORD *)(v32 + 80) = *(_QWORD *)(v32 + 32);
        GreProbeForWriteToUntrustedVa(a2, 8LL * (int)v4, 4u);
        GreProbeForWriteToUntrustedVa(a3, (int)v4, 4u);
        if ( (unsigned int)Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline() )
        {
          v11 = (struct _POINTL *)PALLOCNOZ(8 * v7, 1886221383);
          v24 = v11;
          if ( !v11 )
          {
            v12 = 8;
LABEL_23:
            EngSetLastError(v12);
            v7 = -1;
            v21 = -1;
LABEL_35:
            if ( (unsigned int)Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline()
              && v24
              && (int)v7 > 0 )
            {
              GreProbeAndWriteToUntrustedVa(v10, 8LL * v7, v24, 8LL * v7, 1u);
            }
            if ( v30 && *v29 )
              Win32FreePool(*v29);
            goto LABEL_44;
          }
          v10 = a2;
          v27 = a2;
          a2 = v11;
        }
        v28 = a3;
        v13 = &a3[v4];
        while ( 1 )
        {
          LODWORD(v23) = EPATHOBJ::bEnum((EPATHOBJ *)&v31, &v25);
          if ( v25.count )
          {
            if ( !EXFORMOBJ::bXform((EXFORMOBJ *)&v26, v25.pptfx, a2, v25.count) )
            {
              v12 = 534;
              goto LABEL_23;
            }
            a2 += v25.count;
            v14 = &a3[v25.count];
            flags = v25.flags;
            if ( (v25.flags & 1) != 0 && a3 < v13 )
            {
              v22[0] = 6;
              GreProbeAndWriteToUntrustedVa(a3++, 1u, v22, 1u, 1u);
              flags = v25.flags;
            }
            v18 = (flags & 0x10) != 0 ? 4 : 2;
            if ( v14 <= v13 )
            {
              while ( a3 < v14 )
              {
                GreProbeAndWriteToUntrustedVa(a3++, 1u, &v18, 1u, 1u);
                flags = v25.flags;
              }
            }
            if ( (flags & 8) != 0 && a3 > v28 && a3 <= v13 )
            {
              v19 = 0;
              GreProbeAndReadFromUntrustedVa(&v19, 1u, a3 - 1, 1u, 1u);
              v20[0] = v19 | 1;
              GreProbeAndWriteToUntrustedVa(a3 - 1, 1u, v20, 1u, 1u);
            }
          }
          if ( !(_DWORD)v23 )
            goto LABEL_35;
        }
      }
      EngSetLastError(0x57u);
      v7 = -1;
      v21 = -1;
    }
  }
  else
  {
    EngSetLastError(0x57u);
  }
LABEL_44:
  XEPATHOBJ::~XEPATHOBJ((XEPATHOBJ *)&v31);
LABEL_48:
  APIDCOBJ::~APIDCOBJ((APIDCOBJ *)v33);
  return v7;
}

```

## disassembly

```asm
0x14031b110  mov     [rsp+arg_0], rbx
0x14031b115  mov     [rsp+arg_18], rsi
0x14031b11a  push    rdi
0x14031b11b  push    r12
0x14031b11d  push    r13
0x14031b11f  push    r14
0x14031b121  push    r15
0x14031b123  sub     rsp, 180h
0x14031b12a  mov     ebx, r9d
0x14031b12d  mov     r14, r8
0x14031b130  mov     r15, rdx
0x14031b133  or      r13d, 0FFFFFFFFh
0x14031b137  mov     edi, r13d
0x14031b13a  mov     [rsp+1A8h+var_174], r13d
0x14031b13f  mov     rdx, rcx; HDC
0x14031b142  lea     rcx, [rsp+1A8h+var_98]; this
0x14031b14a  call    ??0APIDCOBJ@@QEAA@PEAUHDC__@@@Z; APIDCOBJ::APIDCOBJ(HDC__ *)
0x14031b14f  mov     r9, [rsp+1A8h+var_98]
0x14031b157  test    r9, r9
0x14031b15a  jz      loc_14031B54B
0x14031b160  test    ebx, ebx
0x14031b162  js      loc_14031B54B
0x14031b168  mov     rcx, r9; this
0x14031b16b  call    ?bInactive@DC@@QEBAHXZ; DC::bInactive(void)
0x14031b170  test    eax, eax
0x14031b172  jz      loc_14031B544
0x14031b178  mov     r8d, 402h
0x14031b17e  lea     rdx, [rsp+1A8h+var_148]
0x14031b183  mov     rcx, r9
0x14031b186  call    cs:__imp_?QuickInitXform@DC@@QEAA?AVEXFORMOBJ@@K@Z; DC::QuickInitXform(ulong)
0x14031b18d  nop     dword ptr [rax+rax+00h]
0x14031b192  cmp     [rsp+1A8h+var_148], 0
0x14031b198  jz      loc_14031B54B
0x14031b19e  mov     rdx, [rsp+1A8h+var_98]
0x14031b1a6  mov     rdx, [rdx+0C8h]; struct HPATH__ *
0x14031b1ad  lea     rcx, [rsp+1A8h+var_118]; this
0x14031b1b5  call    ??0XEPATHOBJ@@QEAA@PEAUHPATH__@@@Z; XEPATHOBJ::XEPATHOBJ(HPATH__ *)
0x14031b1ba  cmp     [rsp+1A8h+var_110], 0
0x14031b1c3  jz      loc_14031B524
0x14031b1c9  xor     r12b, r12b
0x14031b1cc  call    Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline
0x14031b1d1  lea     rcx, [rsp+1A8h+var_118]
0x14031b1d9  test    eax, eax
0x14031b1db  jnz     short loc_14031B1F5
0x14031b1dd  call    cs:__imp_?cTotalPts@EPATHOBJ@@QEAAKXZ; EPATHOBJ::cTotalPts(void)
0x14031b1e4  nop     dword ptr [rax+rax+00h]
0x14031b1e9  mov     edi, eax
0x14031b1eb  mov     [rsp+1A8h+var_174], eax
0x14031b1ef  lea     esi, [r13+2]
0x14031b1f3  jmp     short loc_14031B233
0x14031b1f5  call    cs:__imp_?cTotalPts@EPATHOBJ@@QEAAKXZ; EPATHOBJ::cTotalPts(void)
0x14031b1fc  nop     dword ptr [rax+rax+00h]
0x14031b201  mov     edi, eax
0x14031b203  cmp     eax, 7FFFFFFFh
0x14031b208  ja      short loc_14031B211
0x14031b20a  mov     esi, 1
0x14031b20f  jmp     short loc_14031B22F
0x14031b211  mov     [rsp+1A8h+var_174], r13d
0x14031b216  mov     ecx, 216h; iError
0x14031b21b  call    cs:__imp_EngSetLastError
0x14031b222  nop     dword ptr [rax+rax+00h]
0x14031b227  mov     esi, 1
0x14031b22c  mov     r12b, sil
0x14031b22f  mov     [rsp+1A8h+var_174], edi
0x14031b233  test    ebx, ebx
0x14031b235  jz      loc_14031B535
0x14031b23b  test    r12b, r12b
0x14031b23e  jnz     loc_14031B535
0x14031b244  cmp     ebx, edi
0x14031b246  jl      loc_14031B509
0x14031b24c  movsxd  r12, ebx
0x14031b24f  cmp     r12, 1FFFFFFFh
0x14031b256  ja      loc_14031B509
0x14031b25c  xorps   xmm0, xmm0
0x14031b25f  movups  [rsp+1A8h+var_158], xmm0
0x14031b264  mov     [rsp+1A8h+var_178], 0
0x14031b269  xor     r13d, r13d
0x14031b26c  mov     [rsp+1A8h+var_140], r13
0x14031b271  mov     [rsp+1A8h+var_160], r13
0x14031b276  lea     rax, [rsp+1A8h+var_160]
0x14031b27b  mov     [rsp+1A8h+var_168], rax
0x14031b280  lea     rdx, [rsp+1A8h+var_168]
0x14031b285  lea     rcx, [rsp+1A8h+var_130]
0x14031b28a  call    wil__scope_exit__UMPDOBJ__BackPropagateLargeBitmapBits____2____lambda_1___
0x14031b28f  and     [rsp+1A8h+var_118], 0FFFFFFF7h
0x14031b297  mov     rcx, [rsp+1A8h+var_110]
0x14031b29f  mov     rax, [rcx+20h]
0x14031b2a3  mov     [rcx+50h], rax
0x14031b2a7  lea     rdx, ds:0[r12*8]
0x14031b2af  lea     r8d, [r13+4]
0x14031b2b3  mov     rcx, r15
0x14031b2b6  call    cs:__imp_?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z; GreProbeForWriteToUntrustedVa(void *,unsigned __int64,unsigned __int64)
0x14031b2bd  nop     dword ptr [rax+rax+00h]
0x14031b2c2  lea     r8d, [r13+4]
0x14031b2c6  mov     rdx, r12
0x14031b2c9  mov     rcx, r14
0x14031b2cc  call    cs:__imp_?GreProbeForWriteToUntrustedVa@@YAXPEAX_K1@Z; GreProbeForWriteToUntrustedVa(void *,unsigned __int64,unsigned __int64)
0x14031b2d3  nop     dword ptr [rax+rax+00h]
0x14031b2d8  call    Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline
0x14031b2dd  test    eax, eax
0x14031b2df  jz      short loc_14031B314
0x14031b2e1  lea     ecx, ds:0[rdi*8]
0x14031b2e8  mov     edx, 706D7447h
0x14031b2ed  call    PALLOCNOZ
0x14031b2f2  mov     [rsp+1A8h+var_160], rax
0x14031b2f7  test    rax, rax
0x14031b2fa  jnz     short loc_14031B301
0x14031b2fc  lea     ecx, [rax+8]
0x14031b2ff  jmp     short loc_14031B36B
0x14031b301  mov     r13, r15
0x14031b304  mov     [rsp+1A8h+var_140], r15
0x14031b309  mov     r15, rax
0x14031b30c  mov     [rsp+1A8h+arg_8], rax
0x14031b314  mov     [rsp+1A8h+var_138], r14
0x14031b319  lea     r12, [r14+rbx]
0x14031b31d  lea     rdx, [rsp+1A8h+var_158]
0x14031b322  lea     rcx, [rsp+1A8h+var_118]
0x14031b32a  call    cs:__imp_?bEnum@EPATHOBJ@@QEAAHPEAU_PATHDATA@@@Z; EPATHOBJ::bEnum(_PATHDATA *)
0x14031b331  nop     dword ptr [rax+rax+00h]
0x14031b336  mov     dword ptr [rsp+1A8h+var_168], eax
0x14031b33a  mov     ecx, dword ptr [rsp+1A8h+var_158+4]
0x14031b33e  test    ecx, ecx
0x14031b340  jz      loc_14031B48B
0x14031b346  mov     r9d, ecx
0x14031b349  mov     r8, r15
0x14031b34c  mov     rdx, qword ptr [rsp+1A8h+var_158+8]
0x14031b351  lea     rcx, [rsp+1A8h+var_148]
0x14031b356  call    cs:__imp_?bXform@EXFORMOBJ@@QEBA_NPEBU_POINTFIX@@PEAU_POINTL@@_K@Z; EXFORMOBJ::bXform(_POINTFIX const *,_POINTL *,unsigned __int64)
0x14031b35d  nop     dword ptr [rax+rax+00h]
0x14031b362  test    al, al
0x14031b364  jnz     short loc_14031B385
0x14031b366  mov     ecx, 216h; iError
0x14031b36b  call    cs:__imp_EngSetLastError
0x14031b372  nop     dword ptr [rax+rax+00h]
0x14031b377  mov     edi, 0FFFFFFFFh
0x14031b37c  mov     [rsp+1A8h+var_174], edi
0x14031b380  jmp     loc_14031B496
0x14031b385  mov     eax, dword ptr [rsp+1A8h+var_158+4]
0x14031b389  lea     r15, [r15+rax*8]
0x14031b38d  mov     [rsp+1A8h+arg_8], r15
0x14031b395  lea     rbx, [rax+r14]
0x14031b399  mov     edx, dword ptr [rsp+1A8h+var_158]
0x14031b39d  test    sil, dl
0x14031b3a0  jz      short loc_14031B3DA
0x14031b3a2  cmp     r14, r12
0x14031b3a5  jnb     short loc_14031B3DA
0x14031b3a7  mov     [rsp+1A8h+var_170], 6
0x14031b3ac  mov     [rsp+1A8h+var_188], rsi
0x14031b3b1  mov     r9, rsi
0x14031b3b4  lea     r8, [rsp+1A8h+var_170]
0x14031b3b9  mov     rdx, rsi
0x14031b3bc  mov     rcx, r14
0x14031b3bf  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14031b3c6  nop     dword ptr [rax+rax+00h]
0x14031b3cb  add     r14, rsi
0x14031b3ce  mov     [rsp+1A8h+arg_10], r14
0x14031b3d6  mov     edx, dword ptr [rsp+1A8h+var_158]
0x14031b3da  mov     eax, edx
0x14031b3dc  and     al, 10h
0x14031b3de  neg     al
0x14031b3e0  sbb     cl, cl
0x14031b3e2  and     cl, 2
0x14031b3e5  add     cl, 2
0x14031b3e8  mov     [rsp+1A8h+var_178], cl
0x14031b3ec  cmp     rbx, r12
0x14031b3ef  ja      short loc_14031B426
0x14031b3f1  cmp     r14, rbx
0x14031b3f4  jnb     short loc_14031B426
0x14031b3f6  mov     [rsp+1A8h+var_188], rsi
0x14031b3fb  mov     r9, rsi
0x14031b3fe  lea     r8, [rsp+1A8h+var_178]
0x14031b403  mov     rdx, rsi
0x14031b406  mov     rcx, r14
0x14031b409  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14031b410  nop     dword ptr [rax+rax+00h]
0x14031b415  add     r14, rsi
0x14031b418  mov     [rsp+1A8h+arg_10], r14
0x14031b420  mov     edx, dword ptr [rsp+1A8h+var_158]
0x14031b424  jmp     short loc_14031B3F1
0x14031b426  test    dl, 8
0x14031b429  jz      short loc_14031B48B
0x14031b42b  cmp     r14, [rsp+1A8h+var_138]
0x14031b430  jbe     short loc_14031B48B
0x14031b432  cmp     r14, r12
0x14031b435  ja      short loc_14031B48B
0x14031b437  mov     [rsp+1A8h+var_177], 0
0x14031b43c  mov     [rsp+1A8h+var_188], rsi
0x14031b441  mov     r9, rsi
0x14031b444  lea     r8, [r14-1]
0x14031b448  mov     rdx, rsi
0x14031b44b  lea     rcx, [rsp+1A8h+var_177]
0x14031b450  call    cs:__imp_?GreProbeAndReadFromUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndReadFromUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14031b457  nop     dword ptr [rax+rax+00h]
0x14031b45c  mov     al, [rsp+1A8h+var_177]
0x14031b460  mov     [rsp+1A8h+var_176], al
0x14031b464  or      al, sil
0x14031b467  mov     [rsp+1A8h+var_176], al
0x14031b46b  mov     [rsp+1A8h+var_188], rsi
0x14031b470  mov     r9, rsi
0x14031b473  lea     r8, [rsp+1A8h+var_176]
0x14031b478  mov     rdx, rsi
0x14031b47b  lea     rcx, [r14-1]
0x14031b47f  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14031b486  nop     dword ptr [rax+rax+00h]
0x14031b48b  cmp     dword ptr [rsp+1A8h+var_168], 0
0x14031b490  jnz     loc_14031B31D
0x14031b496  jmp     short loc_14031B4A7
0x14031b498  or      edi, 0FFFFFFFFh
0x14031b49b  mov     [rsp+1A8h+var_174], edi
0x14031b49f  lea     esi, [rdi+2]
0x14031b4a2  mov     r13, [rsp+1A8h+var_140]
0x14031b4a7  call    Feature_Servicing_GdiUMAGetPath__private_IsEnabledDeviceUsageNoInline
0x14031b4ac  test    eax, eax
0x14031b4ae  jz      short loc_14031B4E4
0x14031b4b0  mov     r8, [rsp+1A8h+var_160]
0x14031b4b5  test    r8, r8
0x14031b4b8  jz      short loc_14031B4E4
0x14031b4ba  test    edi, edi
0x14031b4bc  jle     short loc_14031B4E4
0x14031b4be  mov     edx, edi
0x14031b4c0  shl     rdx, 3
0x14031b4c4  mov     [rsp+1A8h+var_188], rsi
0x14031b4c9  mov     r9, rdx
0x14031b4cc  mov     rcx, r13
0x14031b4cf  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x14031b4d6  nop     dword ptr [rax+rax+00h]
0x14031b4db  jmp     short loc_14031B4E4
0x14031b4dd  or      edi, 0FFFFFFFFh
0x14031b4e0  mov     [rsp+1A8h+var_174], edi
0x14031b4e4  cmp     [rsp+1A8h+var_128], 0
0x14031b4ec  jz      short loc_14031B535
0x14031b4ee  mov     rax, [rsp+1A8h+var_130]
0x14031b4f3  mov     rcx, [rax]
0x14031b4f6  test    rcx, rcx
0x14031b4f9  jz      short loc_14031B535
0x14031b4fb  call    cs:__imp_Win32FreePool
0x14031b502  nop     dword ptr [rax+rax+00h]
0x14031b507  jmp     short loc_14031B535
0x14031b509  mov     ecx, 57h ; 'W'; iError
0x14031b50e  call    cs:__imp_EngSetLastError
0x14031b515  nop     dword ptr [rax+rax+00h]
0x14031b51a  mov     edi, r13d
0x14031b51d  mov     [rsp+1A8h+var_174], r13d
0x14031b522  jmp     short loc_14031B535
0x14031b524  mov     ecx, 57h ; 'W'; iError
0x14031b529  call    cs:__imp_EngSetLastError
0x14031b530  nop     dword ptr [rax+rax+00h]
0x14031b535  lea     rcx, [rsp+1A8h+var_118]; this
0x14031b53d  call    ??1XEPATHOBJ@@QEAA@XZ; XEPATHOBJ::~XEPATHOBJ(void)
0x14031b542  jmp     short loc_14031B55C
0x14031b544  mov     ecx, 3EBh
0x14031b549  jmp     short loc_14031B550
0x14031b54b  mov     ecx, 57h ; 'W'; iError
0x14031b550  call    cs:__imp_EngSetLastError
0x14031b557  nop     dword ptr [rax+rax+00h]
0x14031b55c  lea     rcx, [rsp+1A8h+var_98]; this
0x14031b564  call    ??1APIDCOBJ@@QEAA@XZ; APIDCOBJ::~APIDCOBJ(void)
0x14031b569  mov     eax, edi
0x14031b56b  lea     r11, [rsp+1A8h+var_28]
0x14031b573  mov     rbx, [r11+30h]
0x14031b577  mov     rsi, [r11+48h]
0x14031b57b  mov     rsp, r11
0x14031b57e  pop     r15
0x14031b580  pop     r14
0x14031b582  pop     r13
0x14031b584  pop     r12
0x14031b586  pop     rdi
0x14031b587  retn
```
