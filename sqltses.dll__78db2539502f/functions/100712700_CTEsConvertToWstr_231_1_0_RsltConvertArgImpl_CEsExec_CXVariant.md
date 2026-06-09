# CTEsConvertToWstr<231,1,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x100712700`
- end: `0x100712d1b`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0OH@$00$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1563`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting`

## callers

- `0x1006fff00`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x100410bc0`
- `0x10045db60`
- `0x10047a590`
- `0x100712700`
- `0x10072bc00`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100712bb9`
- `sqldk!??_V@YAXPEAX@Z` at `0x100712bb9`
- `sqldk!SystemThread_TlsIndex` at `0x100712aad`
- `sqldk!SystemThread_TlsOffset` at `0x100712ab6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100712ad1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100712ad1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007127f5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100712bf8`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007127f5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100712bf8`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071288b`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007128ba`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007128e7`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071288b`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007128ba`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007128e7`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100712897`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007128c6`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007128f3`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100712897`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007128c6`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007128f3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007128aa`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007128d9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100712906`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007128aa`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007128d9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100712906`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100712b8c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100712ba3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100712b8c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100712ba3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100712baf`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100712baf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<231,1,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rdi
  bool v5; // zf
  unsigned int v6; // esi
  unsigned int v7; // ebx
  char v8; // r10
  unsigned int v9; // edx
  __int16 *i; // r8
  __int16 v11; // ax
  unsigned int v12; // eax
  int v13; // r14d
  char v14; // si
  __int64 v15; // rax
  __int64 v16; // rcx
  bool v17; // bl
  struct CSessionTraceFlags *v18; // rax
  struct CSessionTraceFlags *v19; // rax
  struct CSessionTraceFlags *v20; // rax
  __int64 v21; // rdx
  unsigned __int8 *v22; // r8
  __int64 v23; // r12
  int v24; // r12d
  bool v25; // al
  int v26; // ecx
  int v27; // r9d
  __int64 v28; // rax
  unsigned __int16 v29; // ax
  const struct CDefaultCollation *v30; // rsi
  __int64 v31; // r9
  const struct CTypeInfo *v32; // rbx
  __int64 v33; // rdi
  __int64 v34; // rdx
  wchar_t *v35; // rdi
  unsigned int v36; // eax
  unsigned __int64 v37; // rbx
  CDbAndSetOpts *v38; // rax
  unsigned int v39; // ebx
  CDbAndSetOpts *v40; // rax
  unsigned int v41; // edi
  CDbAndSetOpts *v42; // rax
  unsigned int v43; // eax
  int v44; // [rsp+20h] [rbp-E0h]
  unsigned int v45; // [rsp+60h] [rbp-A0h] BYREF
  int v46; // [rsp+64h] [rbp-9Ch]
  unsigned __int8 *v47; // [rsp+68h] [rbp-98h] BYREF
  __m256i v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h] BYREF
  __int64 v50; // [rsp+98h] [rbp-68h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v52[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v53; // [rsp+B8h] [rbp-48h]
  int v54; // [rsp+BCh] [rbp-44h]
  __int64 v55; // [rsp+C8h] [rbp-38h]
  wchar_t *v56; // [rsp+D0h] [rbp-30h]
  _BYTE v57[208]; // [rsp+E0h] [rbp-20h] BYREF

  v55 = -2;
  v4 = a1[4];
  if ( *(int *)(v4 + 8) <= 0 )
  {
    v46 = *(unsigned __int8 *)(v4 + 14);
  }
  else
  {
    v5 = *(_BYTE *)(a2 + 32) == 3;
    if ( *(_BYTE *)(a2 + 32) == 3 )
      v46 = -1;
    else
      v46 = *(_DWORD *)(a2 + 40);
    if ( v5 )
    {
      *(_BYTE *)a2 = 3;
      return;
    }
  }
  if ( (*(_BYTE *)(v4 + 17) & 1) != 0 )
  {
    if ( !*(_BYTE *)a2 )
    {
      v6 = *(_DWORD *)(a2 + 16);
      v7 = v6;
      if ( v6 >= *(unsigned __int16 *)(v4 + 18) )
        v7 = *(unsigned __int16 *)(v4 + 18);
      v8 = *(_BYTE *)(v4 + 16);
      if ( v8 )
      {
        v9 = v6 >> 1;
        for ( i = (__int16 *)(*(_QWORD *)(a2 + 8) + 2LL * ((v6 >> 1) - 1)); v9; --v9 )
        {
          v11 = *i--;
          if ( v11 != 32 )
            break;
        }
        if ( 2 * (unsigned __int64)v9 > v7 )
        {
          if ( v8 == 1 )
            ex_raise(81, 52, 16, 13);
          *(_WORD *)(a2 + 2) |= 0x1000u;
        }
      }
      v12 = v7 >> 1;
      v13 = 0;
      if ( v7 >> 1 && v12 < v6 >> 1 )
        LOBYTE(v13) = (unsigned __int16)(*(_WORD *)(*(_QWORD *)(a2 + 8) + 2LL * (v12 - 1)) + 10240) <= 0x3FFu;
      if ( v13 )
        v7 -= 2 * v13;
      *(_QWORD *)(a2 + 16) = v7;
      if ( *(_BYTE *)(v4 + 15) )
        CXVariantBase::AdjustPadding<231>(a2, *(unsigned __int8 *)(v4 + 15), v7);
    }
    return;
  }
  v14 = *(_BYTE *)(v4 + 16);
  v15 = a1[9];
  v17 = 0;
  if ( v15 )
  {
    v16 = *(_QWORD *)(v15 + 408);
    if ( v16 )
    {
      if ( *(_QWORD *)(v16 + 424) )
        v17 = 1;
    }
  }
  if ( ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 0x10) != 0
     || (v18 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v18, 0x1CCu))
    && v14 == 1
    && ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) != 0
     || (v19 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v19, 0x1CBu)
     || !v17)
    && (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) == 0 )
  {
    v20 = PSessTraceFlags();
    if ( v20 )
      CSessionTraceFlags::CheckSessionTraceInternal(v20, 0x1CBu);
  }
  v45 = *(unsigned __int8 *)(v4 + 15);
  v21 = *(unsigned __int16 *)(a1[4] + 18LL);
  v22 = *(unsigned __int8 **)(a1[7] + 8 * v21);
  v47 = v22;
  v23 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v21);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v22;
    *(_QWORD *)(a2 + 16) = v23;
    v24 = 0;
  }
  else
  {
    v48.m256i_i32[0] = 59139;
    memset(&v48.m256i_u64[1], 0, 20);
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v52, 0xE7u, v23);
    if ( v52[0] == 98 )
      v53 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v52[0]))
      || ((v52[0] - 35) & 0xBF) == 0 )
    {
      v25 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v52);
      v26 = v54;
      if ( v25 )
        v26 = -1;
      v54 = v26;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v48, v47, v23, (const struct CTypeInfo *)v52, 0);
    v24 = CXVariantPerformConvertToWstr<231,1,0>::Convert((unsigned int)&v48, a2, v45, v27, v44);
    if ( !v24 )
    {
      *(__m256i *)a2 = v48;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v28 = 0;
    v45 = 0;
    if ( !v17 )
    {
LABEL_73:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v28, v57);
      goto LABEL_74;
    }
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 **))x_pContextProvider)(
      x_pContextProvider,
      &v47);
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 *))(*(_QWORD *)x_pContextProvider
                                                                                               + 8LL))(
      x_pContextProvider,
      v47);
    v29 = (**(__int64 (__fastcall ***)(struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *))x_pIDbOptsProvider)(x_pIDbOptsProvider);
    v30 = (const struct CDefaultCollation *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IDbTableOptionsProvider *, _QWORD))(*(_QWORD *)x_pIDbTableProvider + 8LL))(
                                              x_pIDbTableProvider,
                                              v29);
    v31 = a1[4];
    v32 = (const struct CTypeInfo *)(*(_QWORD *)(a1[2] + 168LL) + 32LL * *(unsigned __int16 *)(v31 + 24));
    v33 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v34 = *(_QWORD *)(v33 + 256);
    if ( !v34 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v34 = *(_QWORD *)(v33 + 256);
      v31 = a1[4];
    }
    v35 = CXVariant::PwchConvertToStringInternal(
            *(CXVariant **)(a1[6] + 8LL * *(unsigned int *)(v31 + 12)),
            *(struct IMemObj **)(v34 + 1000),
            &v45,
            *(struct IMemObj **)(v34 + 1000),
            v32,
            v30,
            2,
            0,
            0,
            0,
            0,
            0);
    v56 = v35;
    if ( v35 )
    {
      v36 = v45;
      if ( v45 >= 0x64 )
        v36 = 100;
    }
    else
    {
      v36 = 0;
    }
    v45 = v36;
    v37 = 2LL * v36;
    if ( v37 )
    {
      if ( !v35 || v37 > 0xC8 )
      {
        memset_0(v57, 0, 0xC8u);
        if ( v35 )
        {
          if ( v37 <= 0xC8 )
            goto LABEL_72;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_72;
      }
      memmove(v57, v35, 2LL * v36);
    }
LABEL_72:
    operator delete[](v35);
    v28 = v45;
    goto LABEL_73;
  }
LABEL_74:
  if ( v24 )
  {
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v49);
    v38 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v49);
    v39 = CDbAndSetOpts::LUserOpt1Get(v38, 0x800u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v50);
    v40 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v50);
    v41 = CDbAndSetOpts::LUserOpt1Get(v40, 0x10000000u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v51);
    v42 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v51);
    v43 = CDbAndSetOpts::LUserOpt1Get(v42, 0x1000u);
    ESConvertErrorHandler(
      v24,
      (struct CXVariant *)a2,
      0xE7u,
      0xE7u,
      0,
      v46,
      *(_BYTE *)(a1[4] + 17LL) & 0x80,
      v43 != 0,
      v41 != 0,
      v39 != 0);
  }
}

```

## disassembly

```asm
0x100712700  push    rbp
0x100712702  push    rsi
0x100712703  push    rdi
0x100712704  push    r12
0x100712706  push    r13
0x100712708  push    r14
0x10071270a  push    r15
0x10071270c  lea     rbp, [rsp-0C0h]
0x100712714  sub     rsp, 1C0h
0x10071271b  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x100712723  mov     [rsp+1F0h+arg_10], rbx
0x10071272b  mov     rax, cs:__security_cookie
0x100712732  xor     rax, rsp
0x100712735  mov     [rbp+0F0h+var_40], rax
0x10071273c  mov     r15, rdx
0x10071273f  mov     r13, rcx
0x100712742  mov     rdi, [rcx+20h]
0x100712746  cmp     dword ptr [rdi+8], 0
0x10071274a  jle     short loc_10071276D
0x10071274c  cmp     byte ptr [rdx+20h], 3
0x100712750  jnz     short loc_10071275C
0x100712752  mov     [rsp+1F0h+var_18C], 0FFFFFFFFh
0x10071275a  jmp     short loc_100712763
0x10071275c  mov     ecx, [rdx+28h]
0x10071275f  mov     [rsp+1F0h+var_18C], ecx
0x100712763  jnz     short loc_100712775
0x100712765  mov     byte ptr [rdx], 3
0x100712768  jmp     loc_100712CF1
0x10071276d  movzx   eax, byte ptr [rdi+0Eh]
0x100712771  mov     [rsp+1F0h+var_18C], eax
0x100712775  test    byte ptr [rdi+11h], 1
0x100712779  jz      loc_100712862
0x10071277f  cmp     byte ptr [rdx], 0
0x100712782  jnz     loc_100712CF1
0x100712788  mov     esi, [rdx+10h]
0x10071278b  movzx   eax, word ptr [rdi+12h]
0x10071278f  mov     ebx, esi
0x100712791  cmp     esi, eax
0x100712793  cmovnb  ebx, eax
0x100712796  movzx   r10d, byte ptr [rdi+10h]
0x10071279b  test    r10b, r10b
0x10071279e  jz      short loc_100712805
0x1007127a0  mov     edx, esi
0x1007127a2  shr     edx, 1
0x1007127a4  lea     ecx, [rdx-1]
0x1007127a7  mov     rax, [r15+8]
0x1007127ab  lea     r8, [rax+rcx*2]
0x1007127af  jz      short loc_1007127D3
0x1007127b1  mov     r9d, 0FFFFFFFFh
0x1007127b7  nop     word ptr [rax+rax+00000000h]
0x1007127c0  movzx   eax, word ptr [r8]
0x1007127c4  lea     r8, [r8-2]
0x1007127c8  cmp     ax, 20h ; ' '
0x1007127cc  jnz     short loc_1007127D3
0x1007127ce  add     edx, r9d
0x1007127d1  jnz     short loc_1007127C0
0x1007127d3  mov     ecx, edx
0x1007127d5  add     rcx, rcx
0x1007127d8  mov     eax, ebx
0x1007127da  cmp     rcx, rax
0x1007127dd  jbe     short loc_100712805
0x1007127df  cmp     r10b, 1
0x1007127e3  jnz     short loc_1007127FB
0x1007127e5  mov     edx, 34h ; '4'
0x1007127ea  lea     ecx, [rdx+1Dh]
0x1007127ed  lea     r9d, [rdx-27h]
0x1007127f1  lea     r8d, [rdx-24h]
0x1007127f5  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1007127fb  mov     edx, 1000h
0x100712800  or      [r15+2], dx
0x100712805  mov     eax, ebx
0x100712807  shr     eax, 1
0x100712809  mov     r14d, 0
0x10071280f  jz      short loc_100712833
0x100712811  shr     esi, 1
0x100712813  cmp     eax, esi
0x100712815  jnb     short loc_100712833
0x100712817  lea     ecx, [rax-1]
0x10071281a  mov     rax, [r15+8]
0x10071281e  mov     edx, 2800h
0x100712823  add     dx, [rax+rcx*2]
0x100712827  mov     eax, 3FFh
0x10071282c  cmp     dx, ax
0x10071282f  setbe   r14b
0x100712833  test    r14d, r14d
0x100712836  jz      short loc_10071283E
0x100712838  lea     eax, [r14+r14]
0x10071283c  sub     ebx, eax
0x10071283e  mov     eax, ebx
0x100712840  mov     [r15+10h], rax
0x100712844  movzx   eax, byte ptr [rdi+0Fh]
0x100712848  test    al, al
0x10071284a  jz      loc_100712CF1
0x100712850  mov     edx, eax
0x100712852  mov     r8d, ebx
0x100712855  mov     rcx, r15
0x100712858  call    ??$AdjustPadding@$0OH@@CXVariantBase@@QEAAXW4EPadding@@I@Z; CXVariantBase::AdjustPadding<231>(EPadding,uint)
0x10071285d  jmp     loc_100712CF1
0x100712862  movzx   esi, byte ptr [rdi+10h]
0x100712866  mov     rax, [r13+48h]
0x10071286a  test    rax, rax
0x10071286d  jz      short loc_100712889
0x10071286f  mov     rcx, [rax+198h]
0x100712876  test    rcx, rcx
0x100712879  jz      short loc_100712889
0x10071287b  cmp     qword ptr [rcx+1A8h], 0
0x100712883  jz      short loc_100712889
0x100712885  mov     bl, 1
0x100712887  jmp     short loc_10071288B
0x100712889  xor     bl, bl
0x10071288b  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100712891  test    byte ptr [rax+39h], 10h
0x100712895  jnz     short loc_1007128B4
0x100712897  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071289d  test    rax, rax
0x1007128a0  jz      short loc_100712917
0x1007128a2  mov     edx, 1CCh
0x1007128a7  mov     rcx, rax
0x1007128aa  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007128b0  test    eax, eax
0x1007128b2  jz      short loc_100712917
0x1007128b4  cmp     sil, 1
0x1007128b8  jnz     short loc_100712917
0x1007128ba  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007128c0  test    byte ptr [rax+39h], 8
0x1007128c4  jnz     short loc_1007128E7
0x1007128c6  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007128cc  test    rax, rax
0x1007128cf  jz      short loc_1007128E3
0x1007128d1  mov     edx, 1CBh
0x1007128d6  mov     rcx, rax
0x1007128d9  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007128df  test    eax, eax
0x1007128e1  jnz     short loc_1007128E7
0x1007128e3  test    bl, bl
0x1007128e5  jnz     short loc_100712914
0x1007128e7  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007128ed  test    byte ptr [rax+39h], 8
0x1007128f1  jnz     short loc_100712910
0x1007128f3  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007128f9  test    rax, rax
0x1007128fc  jz      short loc_100712917
0x1007128fe  mov     edx, 1CBh
0x100712903  mov     rcx, rax
0x100712906  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071290c  test    eax, eax
0x10071290e  jz      short loc_100712917
0x100712910  test    bl, bl
0x100712912  jnz     short loc_100712917
0x100712914  mov     sil, 2
0x100712917  movzx   eax, byte ptr [rdi+0Fh]
0x10071291b  mov     [rsp+1F0h+var_190], eax
0x10071291f  mov     rax, [r13+20h]
0x100712923  movzx   edx, word ptr [rax+12h]
0x100712927  mov     rax, [r13+38h]
0x10071292b  mov     r8, [rax+rdx*8]
0x10071292f  mov     [rsp+1F0h+var_188], r8
0x100712934  mov     rax, [r13+10h]
0x100712938  mov     rcx, [rax+20h]
0x10071293c  movzx   r12d, word ptr [rcx+rdx*2]
0x100712941  xor     r14d, r14d
0x100712944  cmp     [r15], r14b
0x100712947  jz      short loc_100712959
0x100712949  mov     [r15+8], r8
0x10071294d  mov     [r15+10h], r12
0x100712951  mov     r12d, r14d
0x100712954  jmp     loc_100712A1F
0x100712959  mov     dword ptr [rsp+1F0h+var_180], 0E703h
0x100712961  xorps   xmm0, xmm0
0x100712964  movdqu  [rsp+1F0h+var_180+8], xmm0
0x10071296a  mov     [rbp+0F0h+var_168], r14d
0x10071296e  mov     r8d, r12d; int
0x100712971  mov     dl, 0E7h; unsigned __int8
0x100712973  lea     rcx, [rbp+0F0h+var_148]; this
0x100712977  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x10071297c  movzx   edx, [rbp+0F0h+var_148]
0x100712980  cmp     dl, 62h ; 'b'
0x100712983  jnz     short loc_10071298E
0x100712985  mov     eax, 2
0x10071298a  mov     [rbp+0F0h+var_138], ax
0x10071298e  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100712995  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x10071299d  cmp     [rax+rcx+45AFC0h], r14b
0x1007129a5  jnz     short loc_1007129AF
0x1007129a7  sub     dl, 23h ; '#'
0x1007129aa  test    dl, 0BFh
0x1007129ad  jnz     short loc_1007129CA
0x1007129af  lea     rcx, [rbp+0F0h+var_148]; this
0x1007129b3  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x1007129b8  mov     ecx, [rbp+0F0h+var_134]
0x1007129bb  mov     r9d, 0FFFFFFFFh
0x1007129c1  test    al, al
0x1007129c3  cmovnz  ecx, r9d
0x1007129c7  mov     [rbp+0F0h+var_134], ecx
0x1007129ca  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x1007129cf  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x1007129d3  mov     r8d, r12d; unsigned int
0x1007129d6  mov     rdx, [rsp+1F0h+var_188]; unsigned __int8 *
0x1007129db  lea     rcx, [rsp+1F0h+var_180]; this
0x1007129e0  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x1007129e5  mov     byte ptr [rsp+1F0h+var_1C0], sil
0x1007129ea  mov     r8d, [rsp+1F0h+var_190]
0x1007129ef  mov     rdx, r15
0x1007129f2  lea     rcx, [rsp+1F0h+var_180]
0x1007129f7  call    ?Convert@?$CXVariantPerformConvertToWstr@$0OH@$00$0A@@@SAJPEAVCXVariant@@0W4EPadding@@IJFW4EErrorHandling@@@Z; CXVariantPerformConvertToWstr<231,1,0>::Convert(CXVariant *,CXVariant *,EPadding,uint,long,short,EErrorHandling)
0x1007129fc  mov     r12d, eax
0x1007129ff  test    eax, eax
0x100712a01  jnz     short loc_100712A1F
0x100712a03  movups  xmm0, [rsp+1F0h+var_180]
0x100712a08  movups  xmmword ptr [r15], xmm0
0x100712a0c  movups  xmm1, xmmword ptr [rbp-80h]
0x100712a10  movups  xmmword ptr [r15+10h], xmm1
0x100712a15  mov     eax, 0FFFEh
0x100712a1a  and     [r15+2], ax
0x100712a1f  cmp     byte ptr [rdi+10h], 1
0x100712a23  jnz     loc_100712BFE
0x100712a29  movzx   eax, word ptr [r15+2]
0x100712a2e  shr     ax, 0Ch
0x100712a32  test    al, 1
0x100712a34  jz      loc_100712BFE
0x100712a3a  mov     eax, r14d
0x100712a3d  mov     [rsp+1F0h+var_190], eax
0x100712a41  test    bl, bl
0x100712a43  jz      loc_100712BC3
0x100712a49  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100712a50  mov     rax, [rcx]
0x100712a53  lea     rdx, [rsp+1F0h+var_188]
0x100712a58  call    qword ptr [rax]
0x100712a5a  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100712a61  mov     rax, [rcx]
0x100712a64  mov     rdx, [rsp+1F0h+var_188]
0x100712a69  call    qword ptr [rax+8]
0x100712a6c  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x100712a73  mov     rax, [rcx]
0x100712a76  call    qword ptr [rax]
0x100712a78  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x100712a7f  mov     r8, [rcx]
0x100712a82  movzx   edx, ax
0x100712a85  call    qword ptr [r8+8]
0x100712a89  mov     rsi, rax
0x100712a8c  mov     r9, [r13+20h]
0x100712a90  movzx   ebx, word ptr [r9+18h]
0x100712a95  shl     rbx, 5
0x100712a99  mov     rcx, [r13+10h]
0x100712a9d  add     rbx, [rcx+0A8h]
0x100712aa4  mov     r8, gs:58h
0x100712aad  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100712ab4  mov     edx, [rcx]
0x100712ab6  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100712abd  mov     edi, [rcx]
0x100712abf  add     rdi, [r8+rdx*8]
0x100712ac3  mov     rdx, [rdi+100h]
0x100712aca  test    rdx, rdx
0x100712acd  jnz     short loc_100712AE2
0x100712acf  xor     ecx, ecx
0x100712ad1  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100712ad7  mov     rdx, [rdi+100h]
0x100712ade  mov     r9, [r13+20h]
0x100712ae2  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x100712ae9  mov     ecx, [r9+0Ch]
0x100712aed  mov     rax, [r13+30h]
0x100712af1  mov     [rsp+1F0h+var_198], r14d; int
0x100712af6  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x100712afb  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x100712b00  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x100712b05  mov     [rsp+1F0h+Src], r14; Src
0x100712b0a  mov     [rsp+1F0h+var_1C0], 2; int
0x100712b12  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x100712b17  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x100712b1c  mov     r9, rdx; struct IMemObj *
0x100712b1f  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x100712b24  mov     rcx, [rax+rcx*8]; this
0x100712b28  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x100712b2d  mov     rdi, rax
0x100712b30  mov     [rbp+0F0h+var_120], rax
0x100712b34  test    rax, rax
0x100712b37  jnz     short loc_100712B3E
0x100712b39  mov     eax, r14d
0x100712b3c  jmp     short loc_100712B4C
0x100712b3e  mov     eax, [rsp+1F0h+var_190]
0x100712b42  mov     ecx, 64h ; 'd'
0x100712b47  cmp     eax, ecx
0x100712b49  cmovnb  eax, ecx
0x100712b4c  mov     [rsp+1F0h+var_190], eax
0x100712b50  mov     ebx, eax
0x100712b52  add     rbx, rbx
0x100712b55  jz      short loc_100712BB6
0x100712b57  test    rdi, rdi
0x100712b5a  jz      short loc_100712B76
0x100712b5c  cmp     rbx, 0C8h
0x100712b63  ja      short loc_100712B76
0x100712b65  mov     r8, rbx; Size
0x100712b68  mov     rdx, rdi; Src
0x100712b6b  lea     rcx, [rbp+0F0h+var_110]; void *
0x100712b6f  call    memmove
0x100712b74  jmp     short loc_100712BB6
0x100712b76  xor     edx, edx; Val
0x100712b78  mov     r8d, 0C8h; Size
0x100712b7e  lea     rcx, [rbp+0F0h+var_110]; void *
0x100712b82  call    memset_0
  ... truncated ...
```
