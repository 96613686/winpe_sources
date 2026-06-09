# CTEsConvertToWstr<61,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x1007167c0`
- end: `0x100716d57`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0DN@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1431`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x100700400`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x10040c990`
- `0x100410bc0`
- `0x10047a590`
- `0x1007167c0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100716bf6`
- `sqldk!??_V@YAXPEAX@Z` at `0x100716bf6`
- `sqldk!SystemThread_TlsIndex` at `0x100716ae6`
- `sqldk!SystemThread_TlsOffset` at `0x100716aef`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100716b0a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100716b0a`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100716c35`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100716c35`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100716887`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007168b6`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007168e4`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100716887`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007168b6`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007168e4`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100716893`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007168c2`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007168f0`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100716893`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007168c2`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007168f0`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007168a6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007168d5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100716903`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007168a6`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007168d5`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100716903`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100716bc9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100716be0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100716bc9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100716be0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100716bec`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100716bec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<61,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  unsigned int v5; // r12d
  char v6; // si
  __int64 v7; // rax
  __int64 v8; // rax
  bool v9; // di
  struct CSessionTraceFlags *v10; // rax
  struct CSessionTraceFlags *v11; // rax
  struct CSessionTraceFlags *v12; // rax
  __int64 v13; // rdx
  unsigned __int8 *v14; // rsi
  __int64 v15; // rdi
  int v16; // esi
  bool v17; // al
  int v18; // ecx
  struct CLangInfo near **v19; // r9
  wchar_t *const *v20; // r9
  __int64 v21; // rax
  unsigned __int16 v22; // ax
  __int64 v23; // r9
  const struct CTypeInfo *v24; // rbx
  __int64 v25; // rdi
  __int64 v26; // rdx
  wchar_t *v27; // rdi
  unsigned int v28; // eax
  unsigned __int64 v29; // rbx
  CDbAndSetOpts *v30; // rax
  unsigned int v31; // ebx
  CDbAndSetOpts *v32; // rax
  unsigned int v33; // edi
  CDbAndSetOpts *v34; // rax
  unsigned int v35; // eax
  bool v36; // [rsp+60h] [rbp-A0h]
  unsigned int v37; // [rsp+64h] [rbp-9Ch] BYREF
  int v38[2]; // [rsp+68h] [rbp-98h] BYREF
  __m256i v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  struct CDefaultCollation *v41; // [rsp+98h] [rbp-68h]
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[16]; // [rsp+B8h] [rbp-48h] BYREF
  __int16 v46; // [rsp+C8h] [rbp-38h]
  int v47; // [rsp+CCh] [rbp-34h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  wchar_t *v49; // [rsp+E0h] [rbp-20h]
  _BYTE v50[208]; // [rsp+F0h] [rbp-10h] BYREF

  v48 = -2;
  v4 = a1[4];
  if ( *(int *)(v4 + 8) <= 0 )
  {
    v5 = *(unsigned __int8 *)(v4 + 14);
  }
  else
  {
    if ( *(_BYTE *)(a2 + 32) == 3 )
    {
      *(_BYTE *)a2 = 3;
      return;
    }
    v5 = *(_DWORD *)(a2 + 40);
  }
  (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, int *))x_pContextProvider)(
    x_pContextProvider,
    v38);
  LOWORD(v37) = *(_WORD *)((*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, _QWORD))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             *(_QWORD *)v38)
                         + 16);
  v6 = *(_BYTE *)(v4 + 16);
  v7 = a1[9];
  v9 = 0;
  if ( v7 )
  {
    v8 = *(_QWORD *)(v7 + 408);
    if ( v8 )
    {
      if ( *(_QWORD *)(v8 + 424) )
        v9 = 1;
    }
  }
  v36 = v9;
  if ( ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 0x10) != 0
     || (v10 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v10, 0x1CCu))
    && v6 == 1
    && ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) != 0
     || (v11 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v11, 0x1CBu)
     || !v9)
    && (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) == 0 )
  {
    v12 = PSessTraceFlags();
    if ( v12 )
      CSessionTraceFlags::CheckSessionTraceInternal(v12, 0x1CBu);
  }
  v38[0] = *(unsigned __int8 *)(v4 + 15);
  v13 = *(unsigned __int16 *)(a1[4] + 18LL);
  v14 = *(unsigned __int8 **)(a1[7] + 8 * v13);
  v15 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v13);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v14;
    *(_QWORD *)(a2 + 16) = v15;
    v16 = 0;
    v38[0] = 0;
  }
  else
  {
    v39.m256i_i32[0] = 59139;
    memset(&v39.m256i_u64[1], 0, 20);
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v45, 0xE7u, v15);
    if ( v45[0] == 98 )
      v46 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v45[0]))
      || ((v45[0] - 35) & 0xBF) == 0 )
    {
      v17 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v45);
      v18 = v47;
      if ( v17 )
        v18 = -1;
      v47 = v18;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v39, v14, v15, (const struct CTypeInfo *)v45, 0);
    if ( v5 - 130 <= 1 )
    {
      v20 = &rgwszHijriMonth;
    }
    else if ( (unsigned __int16)v37 <= 0x21u && (v19 = &xrg_Languages + 37 * (__int16)v37) != 0 )
    {
      v20 = (wchar_t *const *)(v19 + 17);
    }
    else
    {
      v20 = (wchar_t *const *)&rgwszShortmths;
    }
    v16 = SQLDATE::ConvertToWstr(a2 + 8, &v39, v5, v20, v38[0]);
    v38[0] = v16;
    if ( !v16 )
    {
      *(__m256i *)a2 = v39;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v21 = 0;
    v37 = 0;
    if ( !v36 )
    {
LABEL_58:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v21, v50);
      goto LABEL_59;
    }
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v40);
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider
                                                                                     + 8LL))(
      x_pContextProvider,
      v40);
    v22 = (**(__int64 (__fastcall ***)(struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *))x_pIDbOptsProvider)(x_pIDbOptsProvider);
    v41 = (struct CDefaultCollation *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IDbTableOptionsProvider *, _QWORD))(*(_QWORD *)x_pIDbTableProvider + 8LL))(
                                        x_pIDbTableProvider,
                                        v22);
    v23 = a1[4];
    v24 = (const struct CTypeInfo *)(*(_QWORD *)(a1[2] + 168LL) + 32LL * *(unsigned __int16 *)(v23 + 24));
    v25 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v26 = *(_QWORD *)(v25 + 256);
    if ( !v26 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v26 = *(_QWORD *)(v25 + 256);
      v23 = a1[4];
    }
    v27 = CXVariant::PwchConvertToStringInternal(
            *(CXVariant **)(a1[6] + 8LL * *(unsigned int *)(v23 + 12)),
            *(struct IMemObj **)(v26 + 1000),
            &v37,
            *(struct IMemObj **)(v26 + 1000),
            v24,
            v41,
            2,
            0,
            0,
            0,
            0,
            0);
    v49 = v27;
    if ( v27 )
    {
      v28 = v37;
      if ( v37 >= 0x64 )
        v28 = 100;
    }
    else
    {
      v28 = 0;
    }
    v37 = v28;
    v29 = 2LL * v28;
    if ( v29 )
    {
      if ( !v27 || v29 > 0xC8 )
      {
        memset_0(v50, 0, 0xC8u);
        if ( v27 )
        {
          if ( v29 <= 0xC8 )
            goto LABEL_57;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_57;
      }
      memmove(v50, v27, 2LL * v28);
    }
LABEL_57:
    operator delete[](v27);
    v21 = v37;
    goto LABEL_58;
  }
LABEL_59:
  if ( v16 )
  {
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v42);
    v30 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v42);
    v31 = CDbAndSetOpts::LUserOpt1Get(v30, 0x800u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v43);
    v32 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v43);
    v33 = CDbAndSetOpts::LUserOpt1Get(v32, 0x10000000u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v44);
    v34 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v44);
    v35 = CDbAndSetOpts::LUserOpt1Get(v34, 0x1000u);
    ESConvertErrorHandler(
      v38[0],
      (struct CXVariant *)a2,
      0xE7u,
      0x3Du,
      0,
      v5,
      *(_BYTE *)(a1[4] + 17LL) & 0x80,
      v35 != 0,
      v33 != 0,
      v31 != 0);
  }
}

```

## disassembly

```asm
0x1007167c0  push    rbp
0x1007167c2  push    rsi
0x1007167c3  push    rdi
0x1007167c4  push    r12
0x1007167c6  push    r13
0x1007167c8  push    r14
0x1007167ca  push    r15
0x1007167cc  lea     rbp, [rsp-0D0h]
0x1007167d4  sub     rsp, 1D0h
0x1007167db  mov     [rbp+100h+var_128], 0FFFFFFFFFFFFFFFEh
0x1007167e3  mov     [rsp+200h+arg_10], rbx
0x1007167eb  mov     rax, cs:__security_cookie
0x1007167f2  xor     rax, rsp
0x1007167f5  mov     [rbp+100h+var_40], rax
0x1007167fc  mov     r15, rdx
0x1007167ff  mov     r13, rcx
0x100716802  mov     rbx, [rcx+20h]
0x100716806  cmp     dword ptr [rbx+8], 0
0x10071680a  jle     short loc_100716826
0x10071680c  cmp     byte ptr [rdx+20h], 3
0x100716810  mov     r12d, 0FFFFFFFFh
0x100716816  jz      short loc_10071681E
0x100716818  mov     r12d, [rdx+28h]
0x10071681c  jmp     short loc_10071682B
0x10071681e  mov     byte ptr [rdx], 3
0x100716821  jmp     loc_100716D2D
0x100716826  movzx   r12d, byte ptr [rbx+0Eh]
0x10071682b  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100716832  mov     rax, [rcx]
0x100716835  lea     rdx, [rsp+200h+var_198]
0x10071683a  call    qword ptr [rax]
0x10071683c  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100716843  mov     rax, [rcx]
0x100716846  mov     rdx, qword ptr [rsp+200h+var_198]
0x10071684b  call    qword ptr [rax+8]
0x10071684e  movzx   ecx, word ptr [rax+10h]
0x100716852  mov     word ptr [rsp+200h+var_19C], cx
0x100716857  movzx   esi, byte ptr [rbx+10h]
0x10071685b  mov     rax, [r13+48h]
0x10071685f  test    rax, rax
0x100716862  jz      short loc_10071687F
0x100716864  mov     rax, [rax+198h]
0x10071686b  test    rax, rax
0x10071686e  jz      short loc_10071687F
0x100716870  cmp     qword ptr [rax+1A8h], 0
0x100716878  jz      short loc_10071687F
0x10071687a  mov     dil, 1
0x10071687d  jmp     short loc_100716882
0x10071687f  xor     dil, dil
0x100716882  mov     [rsp+200h+var_1A0], dil
0x100716887  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071688d  test    byte ptr [rax+39h], 10h
0x100716891  jnz     short loc_1007168B0
0x100716893  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100716899  test    rax, rax
0x10071689c  jz      short loc_100716909
0x10071689e  mov     edx, 1CCh
0x1007168a3  mov     rcx, rax
0x1007168a6  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007168ac  test    eax, eax
0x1007168ae  jz      short loc_100716909
0x1007168b0  cmp     sil, 1
0x1007168b4  jnz     short loc_100716909
0x1007168b6  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007168bc  test    byte ptr [rax+39h], 8
0x1007168c0  jnz     short loc_1007168E4
0x1007168c2  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007168c8  test    rax, rax
0x1007168cb  jz      short loc_1007168DF
0x1007168cd  mov     edx, 1CBh
0x1007168d2  mov     rcx, rax
0x1007168d5  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007168db  test    eax, eax
0x1007168dd  jnz     short loc_1007168E4
0x1007168df  test    dil, dil
0x1007168e2  jnz     short loc_100716909
0x1007168e4  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007168ea  test    byte ptr [rax+39h], 8
0x1007168ee  jnz     short loc_100716909
0x1007168f0  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007168f6  test    rax, rax
0x1007168f9  jz      short loc_100716909
0x1007168fb  mov     edx, 1CBh
0x100716900  mov     rcx, rax
0x100716903  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100716909  movzx   eax, byte ptr [rbx+0Fh]
0x10071690d  mov     [rsp+200h+var_198], eax
0x100716911  mov     rax, [r13+20h]
0x100716915  movzx   edx, word ptr [rax+12h]
0x100716919  mov     rax, [r13+38h]
0x10071691d  mov     rsi, [rax+rdx*8]
0x100716921  mov     rax, [r13+10h]
0x100716925  mov     rcx, [rax+20h]
0x100716929  movzx   edi, word ptr [rcx+rdx*2]
0x10071692d  xor     r14d, r14d
0x100716930  cmp     [r15], r14b
0x100716933  jz      short loc_10071694A
0x100716935  mov     [r15+8], rsi
0x100716939  mov     [r15+10h], rdi
0x10071693d  mov     esi, r14d
0x100716940  mov     [rsp+200h+var_198], r14d
0x100716945  jmp     loc_100716A56
0x10071694a  mov     dword ptr [rsp+200h+var_190], 0E703h
0x100716952  xorps   xmm0, xmm0
0x100716955  movdqu  [rsp+200h+var_190+8], xmm0
0x10071695b  mov     [rbp+100h+var_178], r14d
0x10071695f  mov     r8d, edi; int
0x100716962  mov     dl, 0E7h; unsigned __int8
0x100716964  lea     rcx, [rbp+100h+var_148]; this
0x100716968  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x10071696d  movzx   edx, [rbp+100h+var_148]
0x100716971  cmp     dl, 62h ; 'b'
0x100716974  jnz     short loc_10071697F
0x100716976  mov     eax, 2
0x10071697b  mov     [rbp+100h+var_138], ax
0x10071697f  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100716986  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x10071698e  cmp     [rax+rcx+45AFC0h], r14b
0x100716996  jnz     short loc_1007169A0
0x100716998  sub     dl, 23h ; '#'
0x10071699b  test    dl, 0BFh
0x10071699e  jnz     short loc_1007169B9
0x1007169a0  lea     rcx, [rbp+100h+var_148]; this
0x1007169a4  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x1007169a9  mov     ecx, [rbp+100h+var_134]
0x1007169ac  mov     edx, 0FFFFFFFFh
0x1007169b1  test    al, al
0x1007169b3  cmovnz  ecx, edx
0x1007169b6  mov     [rbp+100h+var_134], ecx
0x1007169b9  mov     dword ptr [rsp+200h+var_1E0], r14d; int
0x1007169be  lea     r9, [rbp+100h+var_148]; struct CTypeInfo *
0x1007169c2  mov     r8d, edi; unsigned int
0x1007169c5  mov     rdx, rsi; unsigned __int8 *
0x1007169c8  lea     rcx, [rsp+200h+var_190]; this
0x1007169cd  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x1007169d2  lea     eax, [r12-82h]
0x1007169da  cmp     eax, 1
0x1007169dd  jbe     short loc_100716A10
0x1007169df  movsx   rax, word ptr [rsp+200h+var_19C]
0x1007169e5  cmp     ax, 21h ; '!'
0x1007169e9  ja      short loc_100716A07
0x1007169eb  imul    r9, rax, 128h
0x1007169f2  lea     rax, ?xrg_Languages@@3PAUCLangInfo@@A; CLangInfo near * xrg_Languages
0x1007169f9  add     r9, rax
0x1007169fc  jz      short loc_100716A07
0x1007169fe  add     r9, 88h
0x100716a05  jmp     short loc_100716A17
0x100716a07  lea     r9, ?rgwszShortmths@@3QBQEB_WB; wchar_t const * const near * const rgwszShortmths
0x100716a0e  jmp     short loc_100716A17
0x100716a10  lea     r9, ?rgwszHijriMonth@@3QBQEB_WB; wchar_t const * const near * const rgwszHijriMonth
0x100716a17  lea     rcx, [r15+8]
0x100716a1b  mov     eax, [rsp+200h+var_198]
0x100716a1f  mov     dword ptr [rsp+200h+var_1E0], eax
0x100716a23  mov     r8d, r12d
0x100716a26  lea     rdx, [rsp+200h+var_190]
0x100716a2b  call    ?ConvertToWstr@SQLDATE@@QEBAJPEAVCXVariant@@JPEBQEB_WW4EPadding@@@Z; SQLDATE::ConvertToWstr(CXVariant *,long,wchar_t const * const *,EPadding)
0x100716a30  mov     esi, eax
0x100716a32  mov     [rsp+200h+var_198], eax
0x100716a36  test    eax, eax
0x100716a38  jnz     short loc_100716A56
0x100716a3a  movups  xmm0, [rsp+200h+var_190]
0x100716a3f  movups  xmmword ptr [r15], xmm0
0x100716a43  movups  xmm1, xmmword ptr [rbp-80h]
0x100716a47  movups  xmmword ptr [r15+10h], xmm1
0x100716a4c  mov     eax, 0FFFEh
0x100716a51  and     [r15+2], ax
0x100716a56  cmp     byte ptr [rbx+10h], 1
0x100716a5a  jnz     loc_100716C3B
0x100716a60  movzx   eax, word ptr [r15+2]
0x100716a65  shr     ax, 0Ch
0x100716a69  test    al, 1
0x100716a6b  jz      loc_100716C3B
0x100716a71  mov     eax, r14d
0x100716a74  mov     [rsp+200h+var_19C], eax
0x100716a78  cmp     [rsp+200h+var_1A0], 0
0x100716a7d  jz      loc_100716C00
0x100716a83  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100716a8a  mov     rax, [rcx]
0x100716a8d  lea     rdx, [rbp+100h+var_170]
0x100716a91  call    qword ptr [rax]
0x100716a93  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100716a9a  mov     rax, [rcx]
0x100716a9d  mov     rdx, [rbp+100h+var_170]
0x100716aa1  call    qword ptr [rax+8]
0x100716aa4  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x100716aab  mov     rax, [rcx]
0x100716aae  call    qword ptr [rax]
0x100716ab0  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x100716ab7  mov     r8, [rcx]
0x100716aba  movzx   edx, ax
0x100716abd  call    qword ptr [r8+8]
0x100716ac1  mov     [rbp+100h+var_168], rax
0x100716ac5  mov     r9, [r13+20h]
0x100716ac9  movzx   ebx, word ptr [r9+18h]
0x100716ace  shl     rbx, 5
0x100716ad2  mov     rcx, [r13+10h]
0x100716ad6  add     rbx, [rcx+0A8h]
0x100716add  mov     r8, gs:58h
0x100716ae6  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100716aed  mov     edx, [rcx]
0x100716aef  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100716af6  mov     edi, [rcx]
0x100716af8  add     rdi, [r8+rdx*8]
0x100716afc  mov     rdx, [rdi+100h]
0x100716b03  test    rdx, rdx
0x100716b06  jnz     short loc_100716B1B
0x100716b08  xor     ecx, ecx
0x100716b0a  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100716b10  mov     rdx, [rdi+100h]
0x100716b17  mov     r9, [r13+20h]
0x100716b1b  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x100716b22  mov     ecx, [r9+0Ch]
0x100716b26  mov     rax, [r13+30h]
0x100716b2a  mov     [rsp+200h+var_1A8], r14d; int
0x100716b2f  mov     [rsp+200h+var_1B0], r14d; unsigned int
0x100716b34  mov     [rsp+200h+var_1B8], r14; wchar_t *
0x100716b39  mov     [rsp+200h+var_1C0], r14d; unsigned int
0x100716b3e  mov     [rsp+200h+Src], r14; Src
0x100716b43  mov     [rsp+200h+var_1D0], 2; int
0x100716b4b  mov     r8, [rbp+100h+var_168]
0x100716b4f  mov     [rsp+200h+var_1D8], r8; struct CDefaultCollation *
0x100716b54  mov     [rsp+200h+var_1E0], rbx; struct CTypeInfo *
0x100716b59  mov     r9, rdx; struct IMemObj *
0x100716b5c  lea     r8, [rsp+200h+var_19C]; unsigned int *
0x100716b61  mov     rcx, [rax+rcx*8]; this
0x100716b65  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x100716b6a  mov     rdi, rax
0x100716b6d  mov     [rbp+100h+var_120], rax
0x100716b71  test    rax, rax
0x100716b74  jnz     short loc_100716B7B
0x100716b76  mov     eax, r14d
0x100716b79  jmp     short loc_100716B89
0x100716b7b  mov     eax, [rsp+200h+var_19C]
0x100716b7f  mov     ecx, 64h ; 'd'
0x100716b84  cmp     eax, ecx
0x100716b86  cmovnb  eax, ecx
0x100716b89  mov     [rsp+200h+var_19C], eax
0x100716b8d  mov     ebx, eax
0x100716b8f  add     rbx, rbx
0x100716b92  jz      short loc_100716BF3
0x100716b94  test    rdi, rdi
0x100716b97  jz      short loc_100716BB3
0x100716b99  cmp     rbx, 0C8h
0x100716ba0  ja      short loc_100716BB3
0x100716ba2  mov     r8, rbx; Size
0x100716ba5  mov     rdx, rdi; Src
0x100716ba8  lea     rcx, [rbp+100h+var_110]; void *
0x100716bac  call    memmove
0x100716bb1  jmp     short loc_100716BF3
0x100716bb3  xor     edx, edx; Val
0x100716bb5  mov     r8d, 0C8h; Size
0x100716bbb  lea     rcx, [rbp+100h+var_110]; void *
0x100716bbf  call    memset_0
0x100716bc4  test    rdi, rdi
0x100716bc7  jnz     short loc_100716BD7
0x100716bc9  call    cs:__imp__errno
0x100716bcf  mov     dword ptr [rax], 16h
0x100716bd5  jmp     short loc_100716BEC
0x100716bd7  cmp     rbx, 0C8h
0x100716bde  jbe     short loc_100716BF3
0x100716be0  call    cs:__imp__errno
0x100716be6  mov     dword ptr [rax], 22h ; '"'
0x100716bec  call    cs:__imp__invalid_parameter_noinfo
0x100716bf2  nop
0x100716bf3  mov     rcx, rdi
0x100716bf6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100716bfc  mov     eax, [rsp+200h+var_19C]
0x100716c00  add     rax, rax
0x100716c03  lea     rcx, [rbp+100h+var_110]
0x100716c07  mov     [rsp+200h+var_1B8], rcx
0x100716c0c  mov     qword ptr [rsp+200h+var_1C0], rax
0x100716c11  mov     [rsp+200h+Src], r14
0x100716c16  mov     qword ptr [rsp+200h+var_1D0], r14
0x100716c1b  mov     [rsp+200h+var_1D8], r14
0x100716c20  mov     [rsp+200h+var_1E0], r14
0x100716c25  mov     edx, 1Ch
0x100716c2a  lea     ecx, [rdx-2]
0x100716c2d  lea     r9d, [rdx-1Ah]
0x100716c31  lea     r8d, [rdx-0Ch]
0x100716c35  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100716c3b  test    esi, esi
0x100716c3d  jz      loc_100716D2D
0x100716c43  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100716c4a  mov     rax, [rcx]
0x100716c4d  lea     rdx, [rbp+100h+var_160]
0x100716c51  call    qword ptr [rax]
0x100716c53  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100716c5a  mov     rax, [rcx]
0x100716c5d  mov     rdx, [rbp+100h+var_160]
0x100716c61  call    qword ptr [rax+8]
0x100716c64  mov     edx, 800h; unsigned int
0x100716c69  mov     rcx, rax; this
0x100716c6c  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100716c71  mov     ebx, eax
0x100716c73  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100716c7a  mov     r8, [rcx]
0x100716c7d  lea     rdx, [rbp+100h+var_158]
0x100716c81  call    qword ptr [r8]
0x100716c84  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100716c8b  mov     r8, [rcx]
  ... truncated ...
```
