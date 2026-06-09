# CTEsConvertToWstr<165,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x100714740`
- end: `0x100714c7b`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0KF@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1339`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x100700160`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x100410bc0`
- `0x100462bd0`
- `0x10047a590`
- `0x100714740`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100714b17`
- `sqldk!??_V@YAXPEAX@Z` at `0x100714b17`
- `sqldk!SystemThread_TlsIndex` at `0x100714a0b`
- `sqldk!SystemThread_TlsOffset` at `0x100714a14`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100714a2f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100714a2f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100714b56`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100714b56`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007147e0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071480f`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071483d`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007147e0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071480f`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071483d`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007147ec`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071481b`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100714849`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007147ec`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071481b`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100714849`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007147ff`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071482e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071485c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007147ff`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071482e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071485c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100714aea`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100714b01`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100714aea`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100714b01`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100714b0d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100714b0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<165,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  bool v5; // zf
  char v6; // si
  __int64 v7; // rax
  __int64 v8; // rax
  bool v9; // di
  struct CSessionTraceFlags *v10; // rax
  struct CSessionTraceFlags *v11; // rax
  struct CSessionTraceFlags *v12; // rax
  __int64 v13; // rdx
  unsigned __int8 *v14; // r8
  __int64 v15; // r12
  int v16; // r12d
  bool v17; // al
  int v18; // ecx
  int v19; // r9d
  __int64 v20; // rax
  unsigned __int16 v21; // ax
  const struct CDefaultCollation *v22; // rsi
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
  unsigned int v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+64h] [rbp-9Ch]
  unsigned __int8 *v38; // [rsp+68h] [rbp-98h] BYREF
  __m256i v39; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v43[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v44; // [rsp+B8h] [rbp-48h]
  int v45; // [rsp+BCh] [rbp-44h]
  __int64 v46; // [rsp+C8h] [rbp-38h]
  wchar_t *v47; // [rsp+D0h] [rbp-30h]
  _BYTE v48[208]; // [rsp+E0h] [rbp-20h] BYREF

  v46 = -2;
  v4 = a1[4];
  if ( *(int *)(v4 + 8) <= 0 )
  {
    v37 = *(unsigned __int8 *)(v4 + 14);
  }
  else
  {
    v5 = *(_BYTE *)(a2 + 32) == 3;
    if ( *(_BYTE *)(a2 + 32) == 3 )
      v37 = -1;
    else
      v37 = *(_DWORD *)(a2 + 40);
    if ( v5 )
    {
      *(_BYTE *)a2 = 3;
      return;
    }
  }
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
  v36 = *(unsigned __int8 *)(v4 + 15);
  v13 = *(unsigned __int16 *)(a1[4] + 18LL);
  v14 = *(unsigned __int8 **)(a1[7] + 8 * v13);
  v38 = v14;
  v15 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v13);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v14;
    *(_QWORD *)(a2 + 16) = v15;
    v16 = 0;
  }
  else
  {
    v39.m256i_i32[0] = 59139;
    memset(&v39.m256i_u64[1], 0, 20);
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v43, 0xE7u, v15);
    if ( v43[0] == 98 )
      v44 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v43[0]))
      || ((v43[0] - 35) & 0xBF) == 0 )
    {
      v17 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v43);
      v18 = v45;
      if ( v17 )
        v18 = -1;
      v45 = v18;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v39, v38, v15, (const struct CTypeInfo *)v43, 0);
    v16 = CXVariantPerformConvertToWstr<165,0,0>::Convert((unsigned int)&v39, a2, v36, v19, v37);
    if ( !v16 )
    {
      *(__m256i *)a2 = v39;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v20 = 0;
    v36 = 0;
    if ( !v9 )
    {
LABEL_54:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v20, v48);
      goto LABEL_55;
    }
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 **))x_pContextProvider)(
      x_pContextProvider,
      &v38);
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 *))(*(_QWORD *)x_pContextProvider
                                                                                               + 8LL))(
      x_pContextProvider,
      v38);
    v21 = (**(__int64 (__fastcall ***)(struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *))x_pIDbOptsProvider)(x_pIDbOptsProvider);
    v22 = (const struct CDefaultCollation *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IDbTableOptionsProvider *, _QWORD))(*(_QWORD *)x_pIDbTableProvider + 8LL))(
                                              x_pIDbTableProvider,
                                              v21);
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
            &v36,
            *(struct IMemObj **)(v26 + 1000),
            v24,
            v22,
            2,
            0,
            0,
            0,
            0,
            0);
    v47 = v27;
    if ( v27 )
    {
      v28 = v36;
      if ( v36 >= 0x64 )
        v28 = 100;
    }
    else
    {
      v28 = 0;
    }
    v36 = v28;
    v29 = 2LL * v28;
    if ( v29 )
    {
      if ( !v27 || v29 > 0xC8 )
      {
        memset_0(v48, 0, 0xC8u);
        if ( v27 )
        {
          if ( v29 <= 0xC8 )
            goto LABEL_53;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_53;
      }
      memmove(v48, v27, 2LL * v28);
    }
LABEL_53:
    operator delete[](v27);
    v20 = v36;
    goto LABEL_54;
  }
LABEL_55:
  if ( v16 )
  {
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v40);
    v30 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v40);
    v31 = CDbAndSetOpts::LUserOpt1Get(v30, 0x800u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v41);
    v32 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v41);
    v33 = CDbAndSetOpts::LUserOpt1Get(v32, 0x10000000u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v42);
    v34 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v42);
    v35 = CDbAndSetOpts::LUserOpt1Get(v34, 0x1000u);
    ESConvertErrorHandler(
      v16,
      (struct CXVariant *)a2,
      0xE7u,
      0xA5u,
      0,
      v37,
      *(_BYTE *)(a1[4] + 17LL) & 0x80,
      v35 != 0,
      v33 != 0,
      v31 != 0);
  }
}

```

## disassembly

```asm
0x100714740  push    rbp
0x100714742  push    rsi
0x100714743  push    rdi
0x100714744  push    r12
0x100714746  push    r13
0x100714748  push    r14
0x10071474a  push    r15
0x10071474c  lea     rbp, [rsp-0C0h]
0x100714754  sub     rsp, 1C0h
0x10071475b  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x100714763  mov     [rsp+1F0h+arg_10], rbx
0x10071476b  mov     rax, cs:__security_cookie
0x100714772  xor     rax, rsp
0x100714775  mov     [rbp+0F0h+var_40], rax
0x10071477c  mov     r15, rdx
0x10071477f  mov     r13, rcx
0x100714782  mov     rbx, [rcx+20h]
0x100714786  cmp     dword ptr [rbx+8], 0
0x10071478a  jle     short loc_1007147AD
0x10071478c  cmp     byte ptr [rdx+20h], 3
0x100714790  jnz     short loc_10071479C
0x100714792  mov     [rsp+1F0h+var_18C], 0FFFFFFFFh
0x10071479a  jmp     short loc_1007147A3
0x10071479c  mov     ecx, [rdx+28h]
0x10071479f  mov     [rsp+1F0h+var_18C], ecx
0x1007147a3  jnz     short loc_1007147B5
0x1007147a5  mov     byte ptr [rdx], 3
0x1007147a8  jmp     loc_100714C51
0x1007147ad  movzx   eax, byte ptr [rbx+0Eh]
0x1007147b1  mov     [rsp+1F0h+var_18C], eax
0x1007147b5  movzx   esi, byte ptr [rbx+10h]
0x1007147b9  mov     rax, [r13+48h]
0x1007147bd  test    rax, rax
0x1007147c0  jz      short loc_1007147DD
0x1007147c2  mov     rax, [rax+198h]
0x1007147c9  test    rax, rax
0x1007147cc  jz      short loc_1007147DD
0x1007147ce  cmp     qword ptr [rax+1A8h], 0
0x1007147d6  jz      short loc_1007147DD
0x1007147d8  mov     dil, 1
0x1007147db  jmp     short loc_1007147E0
0x1007147dd  xor     dil, dil
0x1007147e0  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007147e6  test    byte ptr [rax+39h], 10h
0x1007147ea  jnz     short loc_100714809
0x1007147ec  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007147f2  test    rax, rax
0x1007147f5  jz      short loc_10071486E
0x1007147f7  mov     edx, 1CCh
0x1007147fc  mov     rcx, rax
0x1007147ff  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100714805  test    eax, eax
0x100714807  jz      short loc_10071486E
0x100714809  cmp     sil, 1
0x10071480d  jnz     short loc_10071486E
0x10071480f  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100714815  test    byte ptr [rax+39h], 8
0x100714819  jnz     short loc_10071483D
0x10071481b  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100714821  test    rax, rax
0x100714824  jz      short loc_100714838
0x100714826  mov     edx, 1CBh
0x10071482b  mov     rcx, rax
0x10071482e  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100714834  test    eax, eax
0x100714836  jnz     short loc_10071483D
0x100714838  test    dil, dil
0x10071483b  jnz     short loc_10071486B
0x10071483d  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100714843  test    byte ptr [rax+39h], 8
0x100714847  jnz     short loc_100714866
0x100714849  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071484f  test    rax, rax
0x100714852  jz      short loc_10071486E
0x100714854  mov     edx, 1CBh
0x100714859  mov     rcx, rax
0x10071485c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100714862  test    eax, eax
0x100714864  jz      short loc_10071486E
0x100714866  test    dil, dil
0x100714869  jnz     short loc_10071486E
0x10071486b  mov     sil, 2
0x10071486e  movzx   eax, byte ptr [rbx+0Fh]
0x100714872  mov     [rsp+1F0h+var_190], eax
0x100714876  mov     rax, [r13+20h]
0x10071487a  movzx   edx, word ptr [rax+12h]
0x10071487e  mov     rax, [r13+38h]
0x100714882  mov     r8, [rax+rdx*8]
0x100714886  mov     [rsp+1F0h+var_188], r8
0x10071488b  mov     rax, [r13+10h]
0x10071488f  mov     rcx, [rax+20h]
0x100714893  movzx   r12d, word ptr [rcx+rdx*2]
0x100714898  xor     r14d, r14d
0x10071489b  cmp     [r15], r14b
0x10071489e  jz      short loc_1007148B0
0x1007148a0  mov     [r15+8], r8
0x1007148a4  mov     [r15+10h], r12
0x1007148a8  mov     r12d, r14d
0x1007148ab  jmp     loc_10071497C
0x1007148b0  mov     dword ptr [rsp+1F0h+var_180], 0E703h
0x1007148b8  xorps   xmm0, xmm0
0x1007148bb  movdqu  [rsp+1F0h+var_180+8], xmm0
0x1007148c1  mov     [rbp+0F0h+var_168], r14d
0x1007148c5  mov     r8d, r12d; int
0x1007148c8  mov     dl, 0E7h; unsigned __int8
0x1007148ca  lea     rcx, [rbp+0F0h+var_148]; this
0x1007148ce  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x1007148d3  movzx   edx, [rbp+0F0h+var_148]
0x1007148d7  cmp     dl, 62h ; 'b'
0x1007148da  jnz     short loc_1007148E5
0x1007148dc  mov     eax, 2
0x1007148e1  mov     [rbp+0F0h+var_138], ax
0x1007148e5  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1007148ec  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x1007148f4  cmp     [rax+rcx+45AFC0h], r14b
0x1007148fc  jnz     short loc_100714906
0x1007148fe  sub     dl, 23h ; '#'
0x100714901  test    dl, 0BFh
0x100714904  jnz     short loc_10071491F
0x100714906  lea     rcx, [rbp+0F0h+var_148]; this
0x10071490a  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x10071490f  mov     ecx, [rbp+0F0h+var_134]
0x100714912  mov     edx, 0FFFFFFFFh
0x100714917  test    al, al
0x100714919  cmovnz  ecx, edx
0x10071491c  mov     [rbp+0F0h+var_134], ecx
0x10071491f  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x100714924  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x100714928  mov     r8d, r12d; unsigned int
0x10071492b  mov     rdx, [rsp+1F0h+var_188]; unsigned __int8 *
0x100714930  lea     rcx, [rsp+1F0h+var_180]; this
0x100714935  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x10071493a  mov     byte ptr [rsp+1F0h+var_1C0], sil
0x10071493f  mov     eax, [rsp+1F0h+var_18C]
0x100714943  mov     dword ptr [rsp+1F0h+var_1D0], eax
0x100714947  mov     r8d, [rsp+1F0h+var_190]
0x10071494c  mov     rdx, r15
0x10071494f  lea     rcx, [rsp+1F0h+var_180]
0x100714954  call    ?Convert@?$CXVariantPerformConvertToWstr@$0KF@$0A@$0A@@@SAJPEAVCXVariant@@0W4EPadding@@IJFW4EErrorHandling@@@Z; CXVariantPerformConvertToWstr<165,0,0>::Convert(CXVariant *,CXVariant *,EPadding,uint,long,short,EErrorHandling)
0x100714959  mov     r12d, eax
0x10071495c  test    eax, eax
0x10071495e  jnz     short loc_10071497C
0x100714960  movups  xmm0, [rsp+1F0h+var_180]
0x100714965  movups  xmmword ptr [r15], xmm0
0x100714969  movups  xmm1, xmmword ptr [rbp-80h]
0x10071496d  movups  xmmword ptr [r15+10h], xmm1
0x100714972  mov     eax, 0FFFEh
0x100714977  and     [r15+2], ax
0x10071497c  cmp     byte ptr [rbx+10h], 1
0x100714980  jnz     loc_100714B5C
0x100714986  movzx   eax, word ptr [r15+2]
0x10071498b  shr     ax, 0Ch
0x10071498f  test    al, 1
0x100714991  jz      loc_100714B5C
0x100714997  mov     eax, r14d
0x10071499a  mov     [rsp+1F0h+var_190], eax
0x10071499e  test    dil, dil
0x1007149a1  jz      loc_100714B21
0x1007149a7  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007149ae  mov     rax, [rcx]
0x1007149b1  lea     rdx, [rsp+1F0h+var_188]
0x1007149b6  call    qword ptr [rax]
0x1007149b8  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007149bf  mov     rax, [rcx]
0x1007149c2  mov     rdx, [rsp+1F0h+var_188]
0x1007149c7  call    qword ptr [rax+8]
0x1007149ca  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x1007149d1  mov     rax, [rcx]
0x1007149d4  call    qword ptr [rax]
0x1007149d6  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x1007149dd  mov     r8, [rcx]
0x1007149e0  movzx   edx, ax
0x1007149e3  call    qword ptr [r8+8]
0x1007149e7  mov     rsi, rax
0x1007149ea  mov     r9, [r13+20h]
0x1007149ee  movzx   ebx, word ptr [r9+18h]
0x1007149f3  shl     rbx, 5
0x1007149f7  mov     rcx, [r13+10h]
0x1007149fb  add     rbx, [rcx+0A8h]
0x100714a02  mov     r8, gs:58h
0x100714a0b  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100714a12  mov     edx, [rcx]
0x100714a14  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100714a1b  mov     edi, [rcx]
0x100714a1d  add     rdi, [r8+rdx*8]
0x100714a21  mov     rdx, [rdi+100h]
0x100714a28  test    rdx, rdx
0x100714a2b  jnz     short loc_100714A40
0x100714a2d  xor     ecx, ecx
0x100714a2f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100714a35  mov     rdx, [rdi+100h]
0x100714a3c  mov     r9, [r13+20h]
0x100714a40  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x100714a47  mov     ecx, [r9+0Ch]
0x100714a4b  mov     rax, [r13+30h]
0x100714a4f  mov     [rsp+1F0h+var_198], r14d; int
0x100714a54  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x100714a59  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x100714a5e  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x100714a63  mov     [rsp+1F0h+Src], r14; Src
0x100714a68  mov     [rsp+1F0h+var_1C0], 2; int
0x100714a70  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x100714a75  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x100714a7a  mov     r9, rdx; struct IMemObj *
0x100714a7d  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x100714a82  mov     rcx, [rax+rcx*8]; this
0x100714a86  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x100714a8b  mov     rdi, rax
0x100714a8e  mov     [rbp+0F0h+var_120], rax
0x100714a92  test    rax, rax
0x100714a95  jnz     short loc_100714A9C
0x100714a97  mov     eax, r14d
0x100714a9a  jmp     short loc_100714AAA
0x100714a9c  mov     eax, [rsp+1F0h+var_190]
0x100714aa0  mov     ecx, 64h ; 'd'
0x100714aa5  cmp     eax, ecx
0x100714aa7  cmovnb  eax, ecx
0x100714aaa  mov     [rsp+1F0h+var_190], eax
0x100714aae  mov     ebx, eax
0x100714ab0  add     rbx, rbx
0x100714ab3  jz      short loc_100714B14
0x100714ab5  test    rdi, rdi
0x100714ab8  jz      short loc_100714AD4
0x100714aba  cmp     rbx, 0C8h
0x100714ac1  ja      short loc_100714AD4
0x100714ac3  mov     r8, rbx; Size
0x100714ac6  mov     rdx, rdi; Src
0x100714ac9  lea     rcx, [rbp+0F0h+var_110]; void *
0x100714acd  call    memmove
0x100714ad2  jmp     short loc_100714B14
0x100714ad4  xor     edx, edx; Val
0x100714ad6  mov     r8d, 0C8h; Size
0x100714adc  lea     rcx, [rbp+0F0h+var_110]; void *
0x100714ae0  call    memset_0
0x100714ae5  test    rdi, rdi
0x100714ae8  jnz     short loc_100714AF8
0x100714aea  call    cs:__imp__errno
0x100714af0  mov     dword ptr [rax], 16h
0x100714af6  jmp     short loc_100714B0D
0x100714af8  cmp     rbx, 0C8h
0x100714aff  jbe     short loc_100714B14
0x100714b01  call    cs:__imp__errno
0x100714b07  mov     dword ptr [rax], 22h ; '"'
0x100714b0d  call    cs:__imp__invalid_parameter_noinfo
0x100714b13  nop
0x100714b14  mov     rcx, rdi
0x100714b17  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100714b1d  mov     eax, [rsp+1F0h+var_190]
0x100714b21  add     rax, rax
0x100714b24  lea     rcx, [rbp+0F0h+var_110]
0x100714b28  mov     [rsp+1F0h+var_1A8], rcx
0x100714b2d  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x100714b32  mov     [rsp+1F0h+Src], r14
0x100714b37  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x100714b3c  mov     [rsp+1F0h+var_1C8], r14
0x100714b41  mov     [rsp+1F0h+var_1D0], r14
0x100714b46  mov     edx, 1Ch
0x100714b4b  lea     ecx, [rdx-2]
0x100714b4e  lea     r9d, [rdx-1Ah]
0x100714b52  lea     r8d, [rdx-0Ch]
0x100714b56  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100714b5c  test    r12d, r12d
0x100714b5f  jz      loc_100714C51
0x100714b65  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100714b6c  mov     rax, [rcx]
0x100714b6f  lea     rdx, [rbp+0F0h+var_160]
0x100714b73  call    qword ptr [rax]
0x100714b75  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100714b7c  mov     rax, [rcx]
0x100714b7f  mov     rdx, [rbp+0F0h+var_160]
0x100714b83  call    qword ptr [rax+8]
0x100714b86  mov     edx, 800h; unsigned int
0x100714b8b  mov     rcx, rax; this
0x100714b8e  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100714b93  mov     ebx, eax
0x100714b95  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100714b9c  mov     r8, [rcx]
0x100714b9f  lea     rdx, [rbp+0F0h+var_158]
0x100714ba3  call    qword ptr [r8]
0x100714ba6  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100714bad  mov     r8, [rcx]
0x100714bb0  mov     rdx, [rbp+0F0h+var_158]
0x100714bb4  call    qword ptr [r8+8]
0x100714bb8  mov     edx, 10000000h; unsigned int
0x100714bbd  mov     rcx, rax; this
0x100714bc0  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100714bc5  mov     edi, eax
0x100714bc7  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100714bce  mov     r8, [rcx]
0x100714bd1  lea     rdx, [rbp+0F0h+var_150]
0x100714bd5  call    qword ptr [r8]
0x100714bd8  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100714bdf  mov     r8, [rcx]
0x100714be2  mov     rdx, [rbp+0F0h+var_150]
0x100714be6  call    qword ptr [r8+8]
0x100714bea  mov     esi, r14d
0x100714bed  test    ebx, ebx
0x100714bef  setnz   sil
0x100714bf3  mov     ebx, r14d
0x100714bf6  test    edi, edi
  ... truncated ...
```
