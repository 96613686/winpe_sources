# CTEsConvertToWstr<127,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x100707670`
- end: `0x100707b8a`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0HP@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1306`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1006ff420`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x10040c780`
- `0x100410bc0`
- `0x10047a590`
- `0x100707670`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100707a26`
- `sqldk!??_V@YAXPEAX@Z` at `0x100707a26`
- `sqldk!SystemThread_TlsIndex` at `0x10070791a`
- `sqldk!SystemThread_TlsOffset` at `0x100707923`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10070793e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10070793e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100707a65`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100707a65`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100707710`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070773f`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070776d`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100707710`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070773f`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070776d`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070771c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070774b`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100707779`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070771c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070774b`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100707779`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070772f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070775e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070778c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070772f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070775e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070778c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1007079f9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100707a10`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1007079f9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100707a10`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100707a1c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100707a1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<127,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
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
  unsigned __int8 *v14; // r12
  __int64 v15; // rsi
  int v16; // r12d
  bool v17; // al
  int v18; // ecx
  __int64 v19; // rax
  unsigned __int16 v20; // ax
  const struct CDefaultCollation *v21; // rsi
  __int64 v22; // r9
  const struct CTypeInfo *v23; // rbx
  __int64 v24; // rdi
  __int64 v25; // rdx
  wchar_t *v26; // rdi
  unsigned int v27; // eax
  unsigned __int64 v28; // rbx
  CDbAndSetOpts *v29; // rax
  unsigned int v30; // ebx
  CDbAndSetOpts *v31; // rax
  unsigned int v32; // edi
  CDbAndSetOpts *v33; // rax
  unsigned int v34; // eax
  unsigned int v35; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+64h] [rbp-9Ch]
  __m256i v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v42[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v43; // [rsp+B8h] [rbp-48h]
  int v44; // [rsp+BCh] [rbp-44h]
  __int64 v45; // [rsp+C8h] [rbp-38h]
  wchar_t *v46; // [rsp+D0h] [rbp-30h]
  _BYTE v47[208]; // [rsp+E0h] [rbp-20h] BYREF

  v45 = -2;
  v4 = a1[4];
  if ( *(int *)(v4 + 8) <= 0 )
  {
    v36 = *(unsigned __int8 *)(v4 + 14);
  }
  else
  {
    v5 = *(_BYTE *)(a2 + 32) == 3;
    if ( *(_BYTE *)(a2 + 32) == 3 )
      v36 = -1;
    else
      v36 = *(_DWORD *)(a2 + 40);
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
  v35 = *(unsigned __int8 *)(v4 + 15);
  v13 = *(unsigned __int16 *)(a1[4] + 18LL);
  v14 = *(unsigned __int8 **)(a1[7] + 8 * v13);
  v15 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v13);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v14;
    *(_QWORD *)(a2 + 16) = v15;
    v16 = 0;
  }
  else
  {
    v37.m256i_i32[0] = 59139;
    memset(&v37.m256i_u64[1], 0, 20);
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v42, 0xE7u, v15);
    if ( v42[0] == 98 )
      v43 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v42[0]))
      || ((v42[0] - 35) & 0xBF) == 0 )
    {
      v17 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v42);
      v18 = v44;
      if ( v17 )
        v18 = -1;
      v44 = v18;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v37, v14, v15, (const struct CTypeInfo *)v42, 0);
    v16 = CXVariant::WstrConvertFromI8(&v37, *(_QWORD *)(a2 + 8), v35);
    if ( !v16 )
    {
      *(__m256i *)a2 = v37;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v19 = 0;
    v35 = 0;
    if ( !v9 )
    {
LABEL_54:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v19, v47);
      goto LABEL_55;
    }
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v38);
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider
                                                                                     + 8LL))(
      x_pContextProvider,
      v38);
    v20 = (**(__int64 (__fastcall ***)(struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *))x_pIDbOptsProvider)(x_pIDbOptsProvider);
    v21 = (const struct CDefaultCollation *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IDbTableOptionsProvider *, _QWORD))(*(_QWORD *)x_pIDbTableProvider + 8LL))(
                                              x_pIDbTableProvider,
                                              v20);
    v22 = a1[4];
    v23 = (const struct CTypeInfo *)(*(_QWORD *)(a1[2] + 168LL) + 32LL * *(unsigned __int16 *)(v22 + 24));
    v24 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v25 = *(_QWORD *)(v24 + 256);
    if ( !v25 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v25 = *(_QWORD *)(v24 + 256);
      v22 = a1[4];
    }
    v26 = CXVariant::PwchConvertToStringInternal(
            *(CXVariant **)(a1[6] + 8LL * *(unsigned int *)(v22 + 12)),
            *(struct IMemObj **)(v25 + 1000),
            &v35,
            *(struct IMemObj **)(v25 + 1000),
            v23,
            v21,
            2,
            0,
            0,
            0,
            0,
            0);
    v46 = v26;
    if ( v26 )
    {
      v27 = v35;
      if ( v35 >= 0x64 )
        v27 = 100;
    }
    else
    {
      v27 = 0;
    }
    v35 = v27;
    v28 = 2LL * v27;
    if ( v28 )
    {
      if ( !v26 || v28 > 0xC8 )
      {
        memset_0(v47, 0, 0xC8u);
        if ( v26 )
        {
          if ( v28 <= 0xC8 )
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
      memmove(v47, v26, 2LL * v27);
    }
LABEL_53:
    operator delete[](v26);
    v19 = v35;
    goto LABEL_54;
  }
LABEL_55:
  if ( v16 )
  {
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v39);
    v29 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v39);
    v30 = CDbAndSetOpts::LUserOpt1Get(v29, 0x800u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v40);
    v31 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v40);
    v32 = CDbAndSetOpts::LUserOpt1Get(v31, 0x10000000u);
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v41);
    v33 = (CDbAndSetOpts *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider + 8LL))(
                             x_pContextProvider,
                             v41);
    v34 = CDbAndSetOpts::LUserOpt1Get(v33, 0x1000u);
    ESConvertErrorHandler(
      v16,
      (struct CXVariant *)a2,
      0xE7u,
      0x7Fu,
      0,
      v36,
      *(_BYTE *)(a1[4] + 17LL) & 0x80,
      v34 != 0,
      v32 != 0,
      v30 != 0);
  }
}

```

## disassembly

```asm
0x100707670  push    rbp
0x100707672  push    rsi
0x100707673  push    rdi
0x100707674  push    r12
0x100707676  push    r13
0x100707678  push    r14
0x10070767a  push    r15
0x10070767c  lea     rbp, [rsp-0C0h]
0x100707684  sub     rsp, 1C0h
0x10070768b  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x100707693  mov     [rsp+1F0h+arg_10], rbx
0x10070769b  mov     rax, cs:__security_cookie
0x1007076a2  xor     rax, rsp
0x1007076a5  mov     [rbp+0F0h+var_40], rax
0x1007076ac  mov     r15, rdx
0x1007076af  mov     r13, rcx
0x1007076b2  mov     rbx, [rcx+20h]
0x1007076b6  cmp     dword ptr [rbx+8], 0
0x1007076ba  jle     short loc_1007076DD
0x1007076bc  cmp     byte ptr [rdx+20h], 3
0x1007076c0  jnz     short loc_1007076CC
0x1007076c2  mov     [rsp+1F0h+var_18C], 0FFFFFFFFh
0x1007076ca  jmp     short loc_1007076D3
0x1007076cc  mov     ecx, [rdx+28h]
0x1007076cf  mov     [rsp+1F0h+var_18C], ecx
0x1007076d3  jnz     short loc_1007076E5
0x1007076d5  mov     byte ptr [rdx], 3
0x1007076d8  jmp     loc_100707B60
0x1007076dd  movzx   eax, byte ptr [rbx+0Eh]
0x1007076e1  mov     [rsp+1F0h+var_18C], eax
0x1007076e5  movzx   esi, byte ptr [rbx+10h]
0x1007076e9  mov     rax, [r13+48h]
0x1007076ed  test    rax, rax
0x1007076f0  jz      short loc_10070770D
0x1007076f2  mov     rax, [rax+198h]
0x1007076f9  test    rax, rax
0x1007076fc  jz      short loc_10070770D
0x1007076fe  cmp     qword ptr [rax+1A8h], 0
0x100707706  jz      short loc_10070770D
0x100707708  mov     dil, 1
0x10070770b  jmp     short loc_100707710
0x10070770d  xor     dil, dil
0x100707710  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100707716  test    byte ptr [rax+39h], 10h
0x10070771a  jnz     short loc_100707739
0x10070771c  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100707722  test    rax, rax
0x100707725  jz      short loc_100707792
0x100707727  mov     edx, 1CCh
0x10070772c  mov     rcx, rax
0x10070772f  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100707735  test    eax, eax
0x100707737  jz      short loc_100707792
0x100707739  cmp     sil, 1
0x10070773d  jnz     short loc_100707792
0x10070773f  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100707745  test    byte ptr [rax+39h], 8
0x100707749  jnz     short loc_10070776D
0x10070774b  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100707751  test    rax, rax
0x100707754  jz      short loc_100707768
0x100707756  mov     edx, 1CBh
0x10070775b  mov     rcx, rax
0x10070775e  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100707764  test    eax, eax
0x100707766  jnz     short loc_10070776D
0x100707768  test    dil, dil
0x10070776b  jnz     short loc_100707792
0x10070776d  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100707773  test    byte ptr [rax+39h], 8
0x100707777  jnz     short loc_100707792
0x100707779  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10070777f  test    rax, rax
0x100707782  jz      short loc_100707792
0x100707784  mov     edx, 1CBh
0x100707789  mov     rcx, rax
0x10070778c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100707792  movzx   eax, byte ptr [rbx+0Fh]
0x100707796  mov     [rsp+1F0h+var_190], eax
0x10070779a  mov     rax, [r13+20h]
0x10070779e  movzx   edx, word ptr [rax+12h]
0x1007077a2  mov     rax, [r13+38h]
0x1007077a6  mov     r12, [rax+rdx*8]
0x1007077aa  mov     rax, [r13+10h]
0x1007077ae  mov     rcx, [rax+20h]
0x1007077b2  movzx   esi, word ptr [rcx+rdx*2]
0x1007077b6  xor     r14d, r14d
0x1007077b9  cmp     [r15], r14b
0x1007077bc  jz      short loc_1007077CE
0x1007077be  mov     [r15+8], r12
0x1007077c2  mov     [r15+10h], rsi
0x1007077c6  mov     r12d, r14d
0x1007077c9  jmp     loc_10070788D
0x1007077ce  mov     dword ptr [rsp+1F0h+var_188], 0E703h
0x1007077d6  xorps   xmm0, xmm0
0x1007077d9  movdqu  [rsp+1F0h+var_188+8], xmm0
0x1007077df  mov     [rbp+0F0h+var_170], r14d
0x1007077e3  mov     r8d, esi; int
0x1007077e6  mov     dl, 0E7h; unsigned __int8
0x1007077e8  lea     rcx, [rbp+0F0h+var_148]; this
0x1007077ec  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x1007077f1  movzx   edx, [rbp+0F0h+var_148]
0x1007077f5  cmp     dl, 62h ; 'b'
0x1007077f8  jnz     short loc_100707803
0x1007077fa  mov     eax, 2
0x1007077ff  mov     [rbp+0F0h+var_138], ax
0x100707803  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10070780a  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x100707812  cmp     [rax+rcx+45AFC0h], r14b
0x10070781a  jnz     short loc_100707824
0x10070781c  sub     dl, 23h ; '#'
0x10070781f  test    dl, 0BFh
0x100707822  jnz     short loc_10070783D
0x100707824  lea     rcx, [rbp+0F0h+var_148]; this
0x100707828  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x10070782d  mov     ecx, [rbp+0F0h+var_134]
0x100707830  mov     edx, 0FFFFFFFFh
0x100707835  test    al, al
0x100707837  cmovnz  ecx, edx
0x10070783a  mov     [rbp+0F0h+var_134], ecx
0x10070783d  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x100707842  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x100707846  mov     r8d, esi; unsigned int
0x100707849  mov     rdx, r12; unsigned __int8 *
0x10070784c  lea     rcx, [rsp+1F0h+var_188]; this
0x100707851  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x100707856  mov     r8d, [rsp+1F0h+var_190]
0x10070785b  mov     rdx, [r15+8]
0x10070785f  lea     rcx, [rsp+1F0h+var_188]
0x100707864  call    ?WstrConvertFromI8@CXVariant@@QEAAJ_JW4EPadding@@@Z; CXVariant::WstrConvertFromI8(__int64,EPadding)
0x100707869  mov     r12d, eax
0x10070786c  test    eax, eax
0x10070786e  jnz     short loc_10070788D
0x100707870  movups  xmm0, [rsp+1F0h+var_188]
0x100707875  movups  xmmword ptr [r15], xmm0
0x100707879  movups  xmm1, xmmword ptr [rsp+78h]
0x10070787e  movups  xmmword ptr [r15+10h], xmm1
0x100707883  mov     eax, 0FFFEh
0x100707888  and     [r15+2], ax
0x10070788d  cmp     byte ptr [rbx+10h], 1
0x100707891  jnz     loc_100707A6B
0x100707897  movzx   eax, word ptr [r15+2]
0x10070789c  shr     ax, 0Ch
0x1007078a0  test    al, 1
0x1007078a2  jz      loc_100707A6B
0x1007078a8  mov     eax, r14d
0x1007078ab  mov     [rsp+1F0h+var_190], eax
0x1007078af  test    dil, dil
0x1007078b2  jz      loc_100707A30
0x1007078b8  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007078bf  mov     rax, [rcx]
0x1007078c2  lea     rdx, [rbp+0F0h+var_168]
0x1007078c6  call    qword ptr [rax]
0x1007078c8  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007078cf  mov     rax, [rcx]
0x1007078d2  mov     rdx, [rbp+0F0h+var_168]
0x1007078d6  call    qword ptr [rax+8]
0x1007078d9  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x1007078e0  mov     rax, [rcx]
0x1007078e3  call    qword ptr [rax]
0x1007078e5  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x1007078ec  mov     r8, [rcx]
0x1007078ef  movzx   edx, ax
0x1007078f2  call    qword ptr [r8+8]
0x1007078f6  mov     rsi, rax
0x1007078f9  mov     r9, [r13+20h]
0x1007078fd  movzx   ebx, word ptr [r9+18h]
0x100707902  shl     rbx, 5
0x100707906  mov     rcx, [r13+10h]
0x10070790a  add     rbx, [rcx+0A8h]
0x100707911  mov     r8, gs:58h
0x10070791a  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100707921  mov     edx, [rcx]
0x100707923  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10070792a  mov     edi, [rcx]
0x10070792c  add     rdi, [r8+rdx*8]
0x100707930  mov     rdx, [rdi+100h]
0x100707937  test    rdx, rdx
0x10070793a  jnz     short loc_10070794F
0x10070793c  xor     ecx, ecx
0x10070793e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100707944  mov     rdx, [rdi+100h]
0x10070794b  mov     r9, [r13+20h]
0x10070794f  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x100707956  mov     ecx, [r9+0Ch]
0x10070795a  mov     rax, [r13+30h]
0x10070795e  mov     [rsp+1F0h+var_198], r14d; int
0x100707963  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x100707968  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x10070796d  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x100707972  mov     [rsp+1F0h+Src], r14; Src
0x100707977  mov     [rsp+1F0h+var_1C0], 2; int
0x10070797f  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x100707984  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x100707989  mov     r9, rdx; struct IMemObj *
0x10070798c  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x100707991  mov     rcx, [rax+rcx*8]; this
0x100707995  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x10070799a  mov     rdi, rax
0x10070799d  mov     [rbp+0F0h+var_120], rax
0x1007079a1  test    rax, rax
0x1007079a4  jnz     short loc_1007079AB
0x1007079a6  mov     eax, r14d
0x1007079a9  jmp     short loc_1007079B9
0x1007079ab  mov     eax, [rsp+1F0h+var_190]
0x1007079af  mov     ecx, 64h ; 'd'
0x1007079b4  cmp     eax, ecx
0x1007079b6  cmovnb  eax, ecx
0x1007079b9  mov     [rsp+1F0h+var_190], eax
0x1007079bd  mov     ebx, eax
0x1007079bf  add     rbx, rbx
0x1007079c2  jz      short loc_100707A23
0x1007079c4  test    rdi, rdi
0x1007079c7  jz      short loc_1007079E3
0x1007079c9  cmp     rbx, 0C8h
0x1007079d0  ja      short loc_1007079E3
0x1007079d2  mov     r8, rbx; Size
0x1007079d5  mov     rdx, rdi; Src
0x1007079d8  lea     rcx, [rbp+0F0h+var_110]; void *
0x1007079dc  call    memmove
0x1007079e1  jmp     short loc_100707A23
0x1007079e3  xor     edx, edx; Val
0x1007079e5  mov     r8d, 0C8h; Size
0x1007079eb  lea     rcx, [rbp+0F0h+var_110]; void *
0x1007079ef  call    memset_0
0x1007079f4  test    rdi, rdi
0x1007079f7  jnz     short loc_100707A07
0x1007079f9  call    cs:__imp__errno
0x1007079ff  mov     dword ptr [rax], 16h
0x100707a05  jmp     short loc_100707A1C
0x100707a07  cmp     rbx, 0C8h
0x100707a0e  jbe     short loc_100707A23
0x100707a10  call    cs:__imp__errno
0x100707a16  mov     dword ptr [rax], 22h ; '"'
0x100707a1c  call    cs:__imp__invalid_parameter_noinfo
0x100707a22  nop
0x100707a23  mov     rcx, rdi
0x100707a26  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100707a2c  mov     eax, [rsp+1F0h+var_190]
0x100707a30  add     rax, rax
0x100707a33  lea     rcx, [rbp+0F0h+var_110]
0x100707a37  mov     [rsp+1F0h+var_1A8], rcx
0x100707a3c  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x100707a41  mov     [rsp+1F0h+Src], r14
0x100707a46  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x100707a4b  mov     [rsp+1F0h+var_1C8], r14
0x100707a50  mov     [rsp+1F0h+var_1D0], r14
0x100707a55  mov     edx, 1Ch
0x100707a5a  lea     ecx, [rdx-2]
0x100707a5d  lea     r9d, [rdx-1Ah]
0x100707a61  lea     r8d, [rdx-0Ch]
0x100707a65  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100707a6b  test    r12d, r12d
0x100707a6e  jz      loc_100707B60
0x100707a74  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100707a7b  mov     rax, [rcx]
0x100707a7e  lea     rdx, [rbp+0F0h+var_160]
0x100707a82  call    qword ptr [rax]
0x100707a84  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100707a8b  mov     rax, [rcx]
0x100707a8e  mov     rdx, [rbp+0F0h+var_160]
0x100707a92  call    qword ptr [rax+8]
0x100707a95  mov     edx, 800h; unsigned int
0x100707a9a  mov     rcx, rax; this
0x100707a9d  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100707aa2  mov     ebx, eax
0x100707aa4  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100707aab  mov     r8, [rcx]
0x100707aae  lea     rdx, [rbp+0F0h+var_158]
0x100707ab2  call    qword ptr [r8]
0x100707ab5  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100707abc  mov     r8, [rcx]
0x100707abf  mov     rdx, [rbp+0F0h+var_158]
0x100707ac3  call    qword ptr [r8+8]
0x100707ac7  mov     edx, 10000000h; unsigned int
0x100707acc  mov     rcx, rax; this
0x100707acf  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100707ad4  mov     edi, eax
0x100707ad6  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100707add  mov     r8, [rcx]
0x100707ae0  lea     rdx, [rbp+0F0h+var_150]
0x100707ae4  call    qword ptr [r8]
0x100707ae7  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100707aee  mov     r8, [rcx]
0x100707af1  mov     rdx, [rbp+0F0h+var_150]
0x100707af5  call    qword ptr [r8+8]
0x100707af9  mov     esi, r14d
0x100707afc  test    ebx, ebx
0x100707afe  setnz   sil
0x100707b02  mov     ebx, r14d
0x100707b05  test    edi, edi
0x100707b07  setnz   bl
0x100707b0a  mov     edx, 1000h; unsigned int
0x100707b0f  mov     rcx, rax; this
0x100707b12  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100707b17  mov     r9d, r14d
0x100707b1a  test    eax, eax
0x100707b1c  setnz   r9b
0x100707b20  mov     rax, [r13+20h]
0x100707b24  movzx   r8d, byte ptr [rax+11h]
  ... truncated ...
```
