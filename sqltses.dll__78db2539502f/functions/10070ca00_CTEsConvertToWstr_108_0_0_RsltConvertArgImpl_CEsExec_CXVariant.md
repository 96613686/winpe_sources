# CTEsConvertToWstr<108,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x10070ca00`
- end: `0x10070cf26`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0GM@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1318`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1006ff9a0`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x100410bc0`
- `0x10041fa40`
- `0x10047a590`
- `0x10070ca00`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10070cdc2`
- `sqldk!??_V@YAXPEAX@Z` at `0x10070cdc2`
- `sqldk!SystemThread_TlsIndex` at `0x10070ccb6`
- `sqldk!SystemThread_TlsOffset` at `0x10070ccbf`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10070ccda`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10070ccda`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10070ce01`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10070ce01`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070caa0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070cacf`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070cafd`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070caa0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070cacf`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070cafd`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070caac`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070cadb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070cb09`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070caac`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070cadb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070cb09`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070cabf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070caee`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070cb1c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070cabf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070caee`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070cb1c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070cd95`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070cdac`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070cd95`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070cdac`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10070cdb8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10070cdb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<108,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  bool v5; // zf
  int v6; // r12d
  char v7; // si
  __int64 v8; // rax
  __int64 v9; // rax
  bool v10; // di
  struct CSessionTraceFlags *v11; // rax
  struct CSessionTraceFlags *v12; // rax
  struct CSessionTraceFlags *v13; // rax
  __int64 v14; // rdx
  unsigned __int8 *v15; // r8
  __int64 v16; // rsi
  int v17; // r12d
  bool v18; // al
  int v19; // ecx
  int v20; // r9d
  __int64 v21; // rax
  unsigned __int16 v22; // ax
  const struct CDefaultCollation *v23; // rsi
  __int64 v24; // r9
  const struct CTypeInfo *v25; // rbx
  __int64 v26; // rdi
  __int64 v27; // rdx
  wchar_t *v28; // rdi
  unsigned int v29; // eax
  unsigned __int64 v30; // rbx
  CDbAndSetOpts *v31; // rax
  unsigned int v32; // ebx
  CDbAndSetOpts *v33; // rax
  unsigned int v34; // edi
  CDbAndSetOpts *v35; // rax
  unsigned int v36; // eax
  unsigned int v37; // [rsp+60h] [rbp-A0h] BYREF
  int v38; // [rsp+64h] [rbp-9Ch]
  unsigned __int8 *v39; // [rsp+68h] [rbp-98h] BYREF
  __m256i v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+98h] [rbp-68h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v44[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v45; // [rsp+B8h] [rbp-48h]
  int v46; // [rsp+BCh] [rbp-44h]
  __int64 v47; // [rsp+C8h] [rbp-38h]
  wchar_t *v48; // [rsp+D0h] [rbp-30h]
  _BYTE v49[208]; // [rsp+E0h] [rbp-20h] BYREF

  v47 = -2;
  v4 = a1[4];
  if ( *(int *)(v4 + 8) <= 0 )
  {
    v6 = *(unsigned __int8 *)(v4 + 14);
    v38 = v6;
  }
  else
  {
    v5 = *(_BYTE *)(a2 + 32) == 3;
    v6 = -1;
    if ( *(_BYTE *)(a2 + 32) != 3 )
      v6 = *(_DWORD *)(a2 + 40);
    v38 = v6;
    if ( v5 )
    {
      *(_BYTE *)a2 = 3;
      return;
    }
  }
  v7 = *(_BYTE *)(v4 + 16);
  v8 = a1[9];
  v10 = 0;
  if ( v8 )
  {
    v9 = *(_QWORD *)(v8 + 408);
    if ( v9 )
    {
      if ( *(_QWORD *)(v9 + 424) )
        v10 = 1;
    }
  }
  if ( ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 0x10) != 0
     || (v11 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v11, 0x1CCu))
    && v7 == 1
    && ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) != 0
     || (v12 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v12, 0x1CBu)
     || !v10)
    && (*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) == 0 )
  {
    v13 = PSessTraceFlags();
    if ( v13 )
      CSessionTraceFlags::CheckSessionTraceInternal(v13, 0x1CBu);
  }
  v37 = *(unsigned __int8 *)(v4 + 15);
  v14 = *(unsigned __int16 *)(a1[4] + 18LL);
  v15 = *(unsigned __int8 **)(a1[7] + 8 * v14);
  v39 = v15;
  v16 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v14);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v15;
    *(_QWORD *)(a2 + 16) = v16;
    v17 = 0;
  }
  else
  {
    v40.m256i_i32[0] = 59139;
    memset(&v40.m256i_u64[1], 0, 20);
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v44, 0xE7u, v16);
    if ( v44[0] == 98 )
      v45 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v44[0]))
      || ((v44[0] - 35) & 0xBF) == 0 )
    {
      v18 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v44);
      v19 = v46;
      if ( v18 )
        v19 = -1;
      v46 = v19;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v40, v39, v16, (const struct CTypeInfo *)v44, 0);
    v17 = CXVariantPerformConvertToWstr<108,0,0>::Convert((unsigned int)&v40, a2, v37, v20, v6);
    if ( !v17 )
    {
      *(__m256i *)a2 = v40;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v21 = 0;
    v37 = 0;
    if ( !v10 )
    {
LABEL_53:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v21, v49);
      goto LABEL_54;
    }
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 **))x_pContextProvider)(
      x_pContextProvider,
      &v39);
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, unsigned __int8 *))(*(_QWORD *)x_pContextProvider
                                                                                               + 8LL))(
      x_pContextProvider,
      v39);
    v22 = (**(__int64 (__fastcall ***)(struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *))x_pIDbOptsProvider)(x_pIDbOptsProvider);
    v23 = (const struct CDefaultCollation *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IDbTableOptionsProvider *, _QWORD))(*(_QWORD *)x_pIDbTableProvider + 8LL))(
                                              x_pIDbTableProvider,
                                              v22);
    v24 = a1[4];
    v25 = (const struct CTypeInfo *)(*(_QWORD *)(a1[2] + 168LL) + 32LL * *(unsigned __int16 *)(v24 + 24));
    v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v27 = *(_QWORD *)(v26 + 256);
    if ( !v27 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v27 = *(_QWORD *)(v26 + 256);
      v24 = a1[4];
    }
    v28 = CXVariant::PwchConvertToStringInternal(
            *(CXVariant **)(a1[6] + 8LL * *(unsigned int *)(v24 + 12)),
            *(struct IMemObj **)(v27 + 1000),
            &v37,
            *(struct IMemObj **)(v27 + 1000),
            v25,
            v23,
            2,
            0,
            0,
            0,
            0,
            0);
    v48 = v28;
    if ( v28 )
    {
      v29 = v37;
      if ( v37 >= 0x64 )
        v29 = 100;
    }
    else
    {
      v29 = 0;
    }
    v37 = v29;
    v30 = 2LL * v29;
    if ( v30 )
    {
      if ( !v28 || v30 > 0xC8 )
      {
        memset_0(v49, 0, 0xC8u);
        if ( v28 )
        {
          if ( v30 <= 0xC8 )
            goto LABEL_52;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_52;
      }
      memmove(v49, v28, 2LL * v29);
    }
LABEL_52:
    operator delete[](v28);
    v21 = v37;
    goto LABEL_53;
  }
LABEL_54:
  if ( v17 )
  {
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v41);
    v31 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v41);
    v32 = CDbAndSetOpts::LUserOpt1Get(v31, 0x800u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v42);
    v33 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v42);
    v34 = CDbAndSetOpts::LUserOpt1Get(v33, 0x10000000u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v43);
    v35 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v43);
    v36 = CDbAndSetOpts::LUserOpt1Get(v35, 0x1000u);
    ESConvertErrorHandler(
      v17,
      (struct CXVariant *)a2,
      0xE7u,
      0x6Cu,
      0,
      v38,
      *(_BYTE *)(a1[4] + 17LL) & 0x80,
      v36 != 0,
      v34 != 0,
      v32 != 0);
  }
}

```

## disassembly

```asm
0x10070ca00  push    rbp
0x10070ca02  push    rsi
0x10070ca03  push    rdi
0x10070ca04  push    r12
0x10070ca06  push    r13
0x10070ca08  push    r14
0x10070ca0a  push    r15
0x10070ca0c  lea     rbp, [rsp-0C0h]
0x10070ca14  sub     rsp, 1C0h
0x10070ca1b  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x10070ca23  mov     [rsp+1F0h+arg_10], rbx
0x10070ca2b  mov     rax, cs:__security_cookie
0x10070ca32  xor     rax, rsp
0x10070ca35  mov     [rbp+0F0h+var_40], rax
0x10070ca3c  mov     r15, rdx
0x10070ca3f  mov     r13, rcx
0x10070ca42  mov     rbx, [rcx+20h]
0x10070ca46  cmp     dword ptr [rbx+8], 0
0x10070ca4a  jle     short loc_10070CA6B
0x10070ca4c  cmp     byte ptr [rdx+20h], 3
0x10070ca50  mov     r12d, 0FFFFFFFFh
0x10070ca56  jz      short loc_10070CA5C
0x10070ca58  mov     r12d, [rdx+28h]
0x10070ca5c  mov     [rsp+1F0h+var_18C], r12d
0x10070ca61  jnz     short loc_10070CA75
0x10070ca63  mov     byte ptr [rdx], 3
0x10070ca66  jmp     loc_10070CEFC
0x10070ca6b  movzx   r12d, byte ptr [rbx+0Eh]
0x10070ca70  mov     [rsp+1F0h+var_18C], r12d
0x10070ca75  movzx   esi, byte ptr [rbx+10h]
0x10070ca79  mov     rax, [rcx+48h]
0x10070ca7d  test    rax, rax
0x10070ca80  jz      short loc_10070CA9D
0x10070ca82  mov     rax, [rax+198h]
0x10070ca89  test    rax, rax
0x10070ca8c  jz      short loc_10070CA9D
0x10070ca8e  cmp     qword ptr [rax+1A8h], 0
0x10070ca96  jz      short loc_10070CA9D
0x10070ca98  mov     dil, 1
0x10070ca9b  jmp     short loc_10070CAA0
0x10070ca9d  xor     dil, dil
0x10070caa0  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10070caa6  test    byte ptr [rax+39h], 10h
0x10070caaa  jnz     short loc_10070CAC9
0x10070caac  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10070cab2  test    rax, rax
0x10070cab5  jz      short loc_10070CB22
0x10070cab7  mov     edx, 1CCh
0x10070cabc  mov     rcx, rax
0x10070cabf  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10070cac5  test    eax, eax
0x10070cac7  jz      short loc_10070CB22
0x10070cac9  cmp     sil, 1
0x10070cacd  jnz     short loc_10070CB22
0x10070cacf  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10070cad5  test    byte ptr [rax+39h], 8
0x10070cad9  jnz     short loc_10070CAFD
0x10070cadb  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10070cae1  test    rax, rax
0x10070cae4  jz      short loc_10070CAF8
0x10070cae6  mov     edx, 1CBh
0x10070caeb  mov     rcx, rax
0x10070caee  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10070caf4  test    eax, eax
0x10070caf6  jnz     short loc_10070CAFD
0x10070caf8  test    dil, dil
0x10070cafb  jnz     short loc_10070CB22
0x10070cafd  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10070cb03  test    byte ptr [rax+39h], 8
0x10070cb07  jnz     short loc_10070CB22
0x10070cb09  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10070cb0f  test    rax, rax
0x10070cb12  jz      short loc_10070CB22
0x10070cb14  mov     edx, 1CBh
0x10070cb19  mov     rcx, rax
0x10070cb1c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10070cb22  movzx   eax, byte ptr [rbx+0Fh]
0x10070cb26  mov     [rsp+1F0h+var_190], eax
0x10070cb2a  mov     rax, [r13+20h]
0x10070cb2e  movzx   edx, word ptr [rax+12h]
0x10070cb32  mov     rax, [r13+38h]
0x10070cb36  mov     r8, [rax+rdx*8]
0x10070cb3a  mov     [rsp+1F0h+var_188], r8
0x10070cb3f  mov     rax, [r13+10h]
0x10070cb43  mov     rcx, [rax+20h]
0x10070cb47  movzx   esi, word ptr [rcx+rdx*2]
0x10070cb4b  xor     r14d, r14d
0x10070cb4e  cmp     [r15], r14b
0x10070cb51  jz      short loc_10070CB63
0x10070cb53  mov     [r15+8], r8
0x10070cb57  mov     [r15+10h], rsi
0x10070cb5b  mov     r12d, r14d
0x10070cb5e  jmp     loc_10070CC27
0x10070cb63  mov     dword ptr [rsp+1F0h+var_180], 0E703h
0x10070cb6b  xorps   xmm0, xmm0
0x10070cb6e  movdqu  [rsp+1F0h+var_180+8], xmm0
0x10070cb74  mov     [rbp+0F0h+var_168], r14d
0x10070cb78  mov     r8d, esi; int
0x10070cb7b  mov     dl, 0E7h; unsigned __int8
0x10070cb7d  lea     rcx, [rbp+0F0h+var_148]; this
0x10070cb81  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x10070cb86  movzx   edx, [rbp+0F0h+var_148]
0x10070cb8a  cmp     dl, 62h ; 'b'
0x10070cb8d  jnz     short loc_10070CB98
0x10070cb8f  mov     eax, 2
0x10070cb94  mov     [rbp+0F0h+var_138], ax
0x10070cb98  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10070cb9f  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x10070cba7  cmp     [rax+rcx+45AFC0h], r14b
0x10070cbaf  jnz     short loc_10070CBB9
0x10070cbb1  sub     dl, 23h ; '#'
0x10070cbb4  test    dl, 0BFh
0x10070cbb7  jnz     short loc_10070CBD2
0x10070cbb9  lea     rcx, [rbp+0F0h+var_148]; this
0x10070cbbd  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x10070cbc2  mov     ecx, [rbp+0F0h+var_134]
0x10070cbc5  mov     edx, 0FFFFFFFFh
0x10070cbca  test    al, al
0x10070cbcc  cmovnz  ecx, edx
0x10070cbcf  mov     [rbp+0F0h+var_134], ecx
0x10070cbd2  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x10070cbd7  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x10070cbdb  mov     r8d, esi; unsigned int
0x10070cbde  mov     rdx, [rsp+1F0h+var_188]; unsigned __int8 *
0x10070cbe3  lea     rcx, [rsp+1F0h+var_180]; this
0x10070cbe8  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x10070cbed  mov     dword ptr [rsp+1F0h+var_1D0], r12d
0x10070cbf2  mov     r8d, [rsp+1F0h+var_190]
0x10070cbf7  mov     rdx, r15
0x10070cbfa  lea     rcx, [rsp+1F0h+var_180]
0x10070cbff  call    ?Convert@?$CXVariantPerformConvertToWstr@$0GM@$0A@$0A@@@SAJPEAVCXVariant@@0W4EPadding@@IJFW4EErrorHandling@@@Z; CXVariantPerformConvertToWstr<108,0,0>::Convert(CXVariant *,CXVariant *,EPadding,uint,long,short,EErrorHandling)
0x10070cc04  mov     r12d, eax
0x10070cc07  test    eax, eax
0x10070cc09  jnz     short loc_10070CC27
0x10070cc0b  movups  xmm0, [rsp+1F0h+var_180]
0x10070cc10  movups  xmmword ptr [r15], xmm0
0x10070cc14  movups  xmm1, xmmword ptr [rbp-80h]
0x10070cc18  movups  xmmword ptr [r15+10h], xmm1
0x10070cc1d  mov     eax, 0FFFEh
0x10070cc22  and     [r15+2], ax
0x10070cc27  cmp     byte ptr [rbx+10h], 1
0x10070cc2b  jnz     loc_10070CE07
0x10070cc31  movzx   eax, word ptr [r15+2]
0x10070cc36  shr     ax, 0Ch
0x10070cc3a  test    al, 1
0x10070cc3c  jz      loc_10070CE07
0x10070cc42  mov     eax, r14d
0x10070cc45  mov     [rsp+1F0h+var_190], eax
0x10070cc49  test    dil, dil
0x10070cc4c  jz      loc_10070CDCC
0x10070cc52  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070cc59  mov     rax, [rcx]
0x10070cc5c  lea     rdx, [rsp+1F0h+var_188]
0x10070cc61  call    qword ptr [rax]
0x10070cc63  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070cc6a  mov     rax, [rcx]
0x10070cc6d  mov     rdx, [rsp+1F0h+var_188]
0x10070cc72  call    qword ptr [rax+8]
0x10070cc75  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x10070cc7c  mov     rax, [rcx]
0x10070cc7f  call    qword ptr [rax]
0x10070cc81  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x10070cc88  mov     r8, [rcx]
0x10070cc8b  movzx   edx, ax
0x10070cc8e  call    qword ptr [r8+8]
0x10070cc92  mov     rsi, rax
0x10070cc95  mov     r9, [r13+20h]
0x10070cc99  movzx   ebx, word ptr [r9+18h]
0x10070cc9e  shl     rbx, 5
0x10070cca2  mov     rcx, [r13+10h]
0x10070cca6  add     rbx, [rcx+0A8h]
0x10070ccad  mov     r8, gs:58h
0x10070ccb6  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10070ccbd  mov     edx, [rcx]
0x10070ccbf  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10070ccc6  mov     edi, [rcx]
0x10070ccc8  add     rdi, [r8+rdx*8]
0x10070cccc  mov     rdx, [rdi+100h]
0x10070ccd3  test    rdx, rdx
0x10070ccd6  jnz     short loc_10070CCEB
0x10070ccd8  xor     ecx, ecx
0x10070ccda  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10070cce0  mov     rdx, [rdi+100h]
0x10070cce7  mov     r9, [r13+20h]
0x10070cceb  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x10070ccf2  mov     ecx, [r9+0Ch]
0x10070ccf6  mov     rax, [r13+30h]
0x10070ccfa  mov     [rsp+1F0h+var_198], r14d; int
0x10070ccff  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x10070cd04  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x10070cd09  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x10070cd0e  mov     [rsp+1F0h+Src], r14; Src
0x10070cd13  mov     [rsp+1F0h+var_1C0], 2; int
0x10070cd1b  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x10070cd20  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x10070cd25  mov     r9, rdx; struct IMemObj *
0x10070cd28  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x10070cd2d  mov     rcx, [rax+rcx*8]; this
0x10070cd31  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x10070cd36  mov     rdi, rax
0x10070cd39  mov     [rbp+0F0h+var_120], rax
0x10070cd3d  test    rax, rax
0x10070cd40  jnz     short loc_10070CD47
0x10070cd42  mov     eax, r14d
0x10070cd45  jmp     short loc_10070CD55
0x10070cd47  mov     eax, [rsp+1F0h+var_190]
0x10070cd4b  mov     ecx, 64h ; 'd'
0x10070cd50  cmp     eax, ecx
0x10070cd52  cmovnb  eax, ecx
0x10070cd55  mov     [rsp+1F0h+var_190], eax
0x10070cd59  mov     ebx, eax
0x10070cd5b  add     rbx, rbx
0x10070cd5e  jz      short loc_10070CDBF
0x10070cd60  test    rdi, rdi
0x10070cd63  jz      short loc_10070CD7F
0x10070cd65  cmp     rbx, 0C8h
0x10070cd6c  ja      short loc_10070CD7F
0x10070cd6e  mov     r8, rbx; Size
0x10070cd71  mov     rdx, rdi; Src
0x10070cd74  lea     rcx, [rbp+0F0h+var_110]; void *
0x10070cd78  call    memmove
0x10070cd7d  jmp     short loc_10070CDBF
0x10070cd7f  xor     edx, edx; Val
0x10070cd81  mov     r8d, 0C8h; Size
0x10070cd87  lea     rcx, [rbp+0F0h+var_110]; void *
0x10070cd8b  call    memset_0
0x10070cd90  test    rdi, rdi
0x10070cd93  jnz     short loc_10070CDA3
0x10070cd95  call    cs:__imp__errno
0x10070cd9b  mov     dword ptr [rax], 16h
0x10070cda1  jmp     short loc_10070CDB8
0x10070cda3  cmp     rbx, 0C8h
0x10070cdaa  jbe     short loc_10070CDBF
0x10070cdac  call    cs:__imp__errno
0x10070cdb2  mov     dword ptr [rax], 22h ; '"'
0x10070cdb8  call    cs:__imp__invalid_parameter_noinfo
0x10070cdbe  nop
0x10070cdbf  mov     rcx, rdi
0x10070cdc2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10070cdc8  mov     eax, [rsp+1F0h+var_190]
0x10070cdcc  add     rax, rax
0x10070cdcf  lea     rcx, [rbp+0F0h+var_110]
0x10070cdd3  mov     [rsp+1F0h+var_1A8], rcx
0x10070cdd8  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x10070cddd  mov     [rsp+1F0h+Src], r14
0x10070cde2  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x10070cde7  mov     [rsp+1F0h+var_1C8], r14
0x10070cdec  mov     [rsp+1F0h+var_1D0], r14
0x10070cdf1  mov     edx, 1Ch
0x10070cdf6  lea     ecx, [rdx-2]
0x10070cdf9  lea     r9d, [rdx-1Ah]
0x10070cdfd  lea     r8d, [rdx-0Ch]
0x10070ce01  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10070ce07  test    r12d, r12d
0x10070ce0a  jz      loc_10070CEFC
0x10070ce10  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070ce17  mov     rax, [rcx]
0x10070ce1a  lea     rdx, [rbp+0F0h+var_160]
0x10070ce1e  call    qword ptr [rax]
0x10070ce20  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070ce27  mov     rax, [rcx]
0x10070ce2a  mov     rdx, [rbp+0F0h+var_160]
0x10070ce2e  call    qword ptr [rax+8]
0x10070ce31  mov     edx, 800h; unsigned int
0x10070ce36  mov     rcx, rax; this
0x10070ce39  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10070ce3e  mov     ebx, eax
0x10070ce40  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070ce47  mov     r8, [rcx]
0x10070ce4a  lea     rdx, [rbp+0F0h+var_158]
0x10070ce4e  call    qword ptr [r8]
0x10070ce51  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070ce58  mov     r8, [rcx]
0x10070ce5b  mov     rdx, [rbp+0F0h+var_158]
0x10070ce5f  call    qword ptr [r8+8]
0x10070ce63  mov     edx, 10000000h; unsigned int
0x10070ce68  mov     rcx, rax; this
0x10070ce6b  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10070ce70  mov     edi, eax
0x10070ce72  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070ce79  mov     r8, [rcx]
0x10070ce7c  lea     rdx, [rbp+0F0h+var_150]
0x10070ce80  call    qword ptr [r8]
0x10070ce83  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070ce8a  mov     r8, [rcx]
0x10070ce8d  mov     rdx, [rbp+0F0h+var_150]
0x10070ce91  call    qword ptr [r8+8]
0x10070ce95  mov     esi, r14d
0x10070ce98  test    ebx, ebx
0x10070ce9a  setnz   sil
0x10070ce9e  mov     ebx, r14d
0x10070cea1  test    edi, edi
0x10070cea3  setnz   bl
0x10070cea6  mov     edx, 1000h; unsigned int
0x10070ceab  mov     rcx, rax; this
0x10070ceae  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10070ceb3  mov     r9d, r14d
0x10070ceb6  test    eax, eax
0x10070ceb8  setnz   r9b
0x10070cebc  mov     rax, [r13+20h]
  ... truncated ...
```
