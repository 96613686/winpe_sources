# CTEsConvertToWstr<52,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x100704720`
- end: `0x100704c3b`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0DE@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1307`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1006ff140`

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
- `0x100704720`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100704ad7`
- `sqldk!??_V@YAXPEAX@Z` at `0x100704ad7`
- `sqldk!SystemThread_TlsIndex` at `0x1007049cb`
- `sqldk!SystemThread_TlsOffset` at `0x1007049d4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1007049ef`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1007049ef`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100704b16`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100704b16`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007047c0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007047ef`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070481d`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007047c0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007047ef`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070481d`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007047cc`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007047fb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100704829`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007047cc`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007047fb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100704829`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007047df`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070480e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070483c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007047df`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070480e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070483c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100704aaa`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100704ac1`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100704aaa`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100704ac1`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100704acd`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100704acd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<52,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
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
    v16 = CXVariant::WstrConvertFromI8(&v37, *(__int16 *)(a2 + 8), v35);
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
      0x34u,
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
0x100704720  push    rbp
0x100704722  push    rsi
0x100704723  push    rdi
0x100704724  push    r12
0x100704726  push    r13
0x100704728  push    r14
0x10070472a  push    r15
0x10070472c  lea     rbp, [rsp-0C0h]
0x100704734  sub     rsp, 1C0h
0x10070473b  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x100704743  mov     [rsp+1F0h+arg_10], rbx
0x10070474b  mov     rax, cs:__security_cookie
0x100704752  xor     rax, rsp
0x100704755  mov     [rbp+0F0h+var_40], rax
0x10070475c  mov     r15, rdx
0x10070475f  mov     r13, rcx
0x100704762  mov     rbx, [rcx+20h]
0x100704766  cmp     dword ptr [rbx+8], 0
0x10070476a  jle     short loc_10070478D
0x10070476c  cmp     byte ptr [rdx+20h], 3
0x100704770  jnz     short loc_10070477C
0x100704772  mov     [rsp+1F0h+var_18C], 0FFFFFFFFh
0x10070477a  jmp     short loc_100704783
0x10070477c  mov     ecx, [rdx+28h]
0x10070477f  mov     [rsp+1F0h+var_18C], ecx
0x100704783  jnz     short loc_100704795
0x100704785  mov     byte ptr [rdx], 3
0x100704788  jmp     loc_100704C11
0x10070478d  movzx   eax, byte ptr [rbx+0Eh]
0x100704791  mov     [rsp+1F0h+var_18C], eax
0x100704795  movzx   esi, byte ptr [rbx+10h]
0x100704799  mov     rax, [r13+48h]
0x10070479d  test    rax, rax
0x1007047a0  jz      short loc_1007047BD
0x1007047a2  mov     rax, [rax+198h]
0x1007047a9  test    rax, rax
0x1007047ac  jz      short loc_1007047BD
0x1007047ae  cmp     qword ptr [rax+1A8h], 0
0x1007047b6  jz      short loc_1007047BD
0x1007047b8  mov     dil, 1
0x1007047bb  jmp     short loc_1007047C0
0x1007047bd  xor     dil, dil
0x1007047c0  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007047c6  test    byte ptr [rax+39h], 10h
0x1007047ca  jnz     short loc_1007047E9
0x1007047cc  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007047d2  test    rax, rax
0x1007047d5  jz      short loc_100704842
0x1007047d7  mov     edx, 1CCh
0x1007047dc  mov     rcx, rax
0x1007047df  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007047e5  test    eax, eax
0x1007047e7  jz      short loc_100704842
0x1007047e9  cmp     sil, 1
0x1007047ed  jnz     short loc_100704842
0x1007047ef  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007047f5  test    byte ptr [rax+39h], 8
0x1007047f9  jnz     short loc_10070481D
0x1007047fb  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100704801  test    rax, rax
0x100704804  jz      short loc_100704818
0x100704806  mov     edx, 1CBh
0x10070480b  mov     rcx, rax
0x10070480e  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100704814  test    eax, eax
0x100704816  jnz     short loc_10070481D
0x100704818  test    dil, dil
0x10070481b  jnz     short loc_100704842
0x10070481d  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100704823  test    byte ptr [rax+39h], 8
0x100704827  jnz     short loc_100704842
0x100704829  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10070482f  test    rax, rax
0x100704832  jz      short loc_100704842
0x100704834  mov     edx, 1CBh
0x100704839  mov     rcx, rax
0x10070483c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100704842  movzx   eax, byte ptr [rbx+0Fh]
0x100704846  mov     [rsp+1F0h+var_190], eax
0x10070484a  mov     rax, [r13+20h]
0x10070484e  movzx   edx, word ptr [rax+12h]
0x100704852  mov     rax, [r13+38h]
0x100704856  mov     r12, [rax+rdx*8]
0x10070485a  mov     rax, [r13+10h]
0x10070485e  mov     rcx, [rax+20h]
0x100704862  movzx   esi, word ptr [rcx+rdx*2]
0x100704866  xor     r14d, r14d
0x100704869  cmp     [r15], r14b
0x10070486c  jz      short loc_10070487E
0x10070486e  mov     [r15+8], r12
0x100704872  mov     [r15+10h], rsi
0x100704876  mov     r12d, r14d
0x100704879  jmp     loc_10070493E
0x10070487e  mov     dword ptr [rsp+1F0h+var_188], 0E703h
0x100704886  xorps   xmm0, xmm0
0x100704889  movdqu  [rsp+1F0h+var_188+8], xmm0
0x10070488f  mov     [rbp+0F0h+var_170], r14d
0x100704893  mov     r8d, esi; int
0x100704896  mov     dl, 0E7h; unsigned __int8
0x100704898  lea     rcx, [rbp+0F0h+var_148]; this
0x10070489c  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x1007048a1  movzx   edx, [rbp+0F0h+var_148]
0x1007048a5  cmp     dl, 62h ; 'b'
0x1007048a8  jnz     short loc_1007048B3
0x1007048aa  mov     eax, 2
0x1007048af  mov     [rbp+0F0h+var_138], ax
0x1007048b3  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1007048ba  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x1007048c2  cmp     [rax+rcx+45AFC0h], r14b
0x1007048ca  jnz     short loc_1007048D4
0x1007048cc  sub     dl, 23h ; '#'
0x1007048cf  test    dl, 0BFh
0x1007048d2  jnz     short loc_1007048ED
0x1007048d4  lea     rcx, [rbp+0F0h+var_148]; this
0x1007048d8  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x1007048dd  mov     ecx, [rbp+0F0h+var_134]
0x1007048e0  mov     edx, 0FFFFFFFFh
0x1007048e5  test    al, al
0x1007048e7  cmovnz  ecx, edx
0x1007048ea  mov     [rbp+0F0h+var_134], ecx
0x1007048ed  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x1007048f2  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x1007048f6  mov     r8d, esi; unsigned int
0x1007048f9  mov     rdx, r12; unsigned __int8 *
0x1007048fc  lea     rcx, [rsp+1F0h+var_188]; this
0x100704901  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x100704906  movsx   rdx, word ptr [r15+8]
0x10070490b  mov     r8d, [rsp+1F0h+var_190]
0x100704910  lea     rcx, [rsp+1F0h+var_188]
0x100704915  call    ?WstrConvertFromI8@CXVariant@@QEAAJ_JW4EPadding@@@Z; CXVariant::WstrConvertFromI8(__int64,EPadding)
0x10070491a  mov     r12d, eax
0x10070491d  test    eax, eax
0x10070491f  jnz     short loc_10070493E
0x100704921  movups  xmm0, [rsp+1F0h+var_188]
0x100704926  movups  xmmword ptr [r15], xmm0
0x10070492a  movups  xmm1, xmmword ptr [rsp+78h]
0x10070492f  movups  xmmword ptr [r15+10h], xmm1
0x100704934  mov     eax, 0FFFEh
0x100704939  and     [r15+2], ax
0x10070493e  cmp     byte ptr [rbx+10h], 1
0x100704942  jnz     loc_100704B1C
0x100704948  movzx   eax, word ptr [r15+2]
0x10070494d  shr     ax, 0Ch
0x100704951  test    al, 1
0x100704953  jz      loc_100704B1C
0x100704959  mov     eax, r14d
0x10070495c  mov     [rsp+1F0h+var_190], eax
0x100704960  test    dil, dil
0x100704963  jz      loc_100704AE1
0x100704969  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100704970  mov     rax, [rcx]
0x100704973  lea     rdx, [rbp+0F0h+var_168]
0x100704977  call    qword ptr [rax]
0x100704979  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100704980  mov     rax, [rcx]
0x100704983  mov     rdx, [rbp+0F0h+var_168]
0x100704987  call    qword ptr [rax+8]
0x10070498a  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x100704991  mov     rax, [rcx]
0x100704994  call    qword ptr [rax]
0x100704996  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x10070499d  mov     r8, [rcx]
0x1007049a0  movzx   edx, ax
0x1007049a3  call    qword ptr [r8+8]
0x1007049a7  mov     rsi, rax
0x1007049aa  mov     r9, [r13+20h]
0x1007049ae  movzx   ebx, word ptr [r9+18h]
0x1007049b3  shl     rbx, 5
0x1007049b7  mov     rcx, [r13+10h]
0x1007049bb  add     rbx, [rcx+0A8h]
0x1007049c2  mov     r8, gs:58h
0x1007049cb  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x1007049d2  mov     edx, [rcx]
0x1007049d4  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x1007049db  mov     edi, [rcx]
0x1007049dd  add     rdi, [r8+rdx*8]
0x1007049e1  mov     rdx, [rdi+100h]
0x1007049e8  test    rdx, rdx
0x1007049eb  jnz     short loc_100704A00
0x1007049ed  xor     ecx, ecx
0x1007049ef  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1007049f5  mov     rdx, [rdi+100h]
0x1007049fc  mov     r9, [r13+20h]
0x100704a00  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x100704a07  mov     ecx, [r9+0Ch]
0x100704a0b  mov     rax, [r13+30h]
0x100704a0f  mov     [rsp+1F0h+var_198], r14d; int
0x100704a14  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x100704a19  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x100704a1e  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x100704a23  mov     [rsp+1F0h+Src], r14; Src
0x100704a28  mov     [rsp+1F0h+var_1C0], 2; int
0x100704a30  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x100704a35  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x100704a3a  mov     r9, rdx; struct IMemObj *
0x100704a3d  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x100704a42  mov     rcx, [rax+rcx*8]; this
0x100704a46  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x100704a4b  mov     rdi, rax
0x100704a4e  mov     [rbp+0F0h+var_120], rax
0x100704a52  test    rax, rax
0x100704a55  jnz     short loc_100704A5C
0x100704a57  mov     eax, r14d
0x100704a5a  jmp     short loc_100704A6A
0x100704a5c  mov     eax, [rsp+1F0h+var_190]
0x100704a60  mov     ecx, 64h ; 'd'
0x100704a65  cmp     eax, ecx
0x100704a67  cmovnb  eax, ecx
0x100704a6a  mov     [rsp+1F0h+var_190], eax
0x100704a6e  mov     ebx, eax
0x100704a70  add     rbx, rbx
0x100704a73  jz      short loc_100704AD4
0x100704a75  test    rdi, rdi
0x100704a78  jz      short loc_100704A94
0x100704a7a  cmp     rbx, 0C8h
0x100704a81  ja      short loc_100704A94
0x100704a83  mov     r8, rbx; Size
0x100704a86  mov     rdx, rdi; Src
0x100704a89  lea     rcx, [rbp+0F0h+var_110]; void *
0x100704a8d  call    memmove
0x100704a92  jmp     short loc_100704AD4
0x100704a94  xor     edx, edx; Val
0x100704a96  mov     r8d, 0C8h; Size
0x100704a9c  lea     rcx, [rbp+0F0h+var_110]; void *
0x100704aa0  call    memset_0
0x100704aa5  test    rdi, rdi
0x100704aa8  jnz     short loc_100704AB8
0x100704aaa  call    cs:__imp__errno
0x100704ab0  mov     dword ptr [rax], 16h
0x100704ab6  jmp     short loc_100704ACD
0x100704ab8  cmp     rbx, 0C8h
0x100704abf  jbe     short loc_100704AD4
0x100704ac1  call    cs:__imp__errno
0x100704ac7  mov     dword ptr [rax], 22h ; '"'
0x100704acd  call    cs:__imp__invalid_parameter_noinfo
0x100704ad3  nop
0x100704ad4  mov     rcx, rdi
0x100704ad7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100704add  mov     eax, [rsp+1F0h+var_190]
0x100704ae1  add     rax, rax
0x100704ae4  lea     rcx, [rbp+0F0h+var_110]
0x100704ae8  mov     [rsp+1F0h+var_1A8], rcx
0x100704aed  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x100704af2  mov     [rsp+1F0h+Src], r14
0x100704af7  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x100704afc  mov     [rsp+1F0h+var_1C8], r14
0x100704b01  mov     [rsp+1F0h+var_1D0], r14
0x100704b06  mov     edx, 1Ch
0x100704b0b  lea     ecx, [rdx-2]
0x100704b0e  lea     r9d, [rdx-1Ah]
0x100704b12  lea     r8d, [rdx-0Ch]
0x100704b16  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100704b1c  test    r12d, r12d
0x100704b1f  jz      loc_100704C11
0x100704b25  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100704b2c  mov     rax, [rcx]
0x100704b2f  lea     rdx, [rbp+0F0h+var_160]
0x100704b33  call    qword ptr [rax]
0x100704b35  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100704b3c  mov     rax, [rcx]
0x100704b3f  mov     rdx, [rbp+0F0h+var_160]
0x100704b43  call    qword ptr [rax+8]
0x100704b46  mov     edx, 800h; unsigned int
0x100704b4b  mov     rcx, rax; this
0x100704b4e  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100704b53  mov     ebx, eax
0x100704b55  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100704b5c  mov     r8, [rcx]
0x100704b5f  lea     rdx, [rbp+0F0h+var_158]
0x100704b63  call    qword ptr [r8]
0x100704b66  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100704b6d  mov     r8, [rcx]
0x100704b70  mov     rdx, [rbp+0F0h+var_158]
0x100704b74  call    qword ptr [r8+8]
0x100704b78  mov     edx, 10000000h; unsigned int
0x100704b7d  mov     rcx, rax; this
0x100704b80  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100704b85  mov     edi, eax
0x100704b87  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100704b8e  mov     r8, [rcx]
0x100704b91  lea     rdx, [rbp+0F0h+var_150]
0x100704b95  call    qword ptr [r8]
0x100704b98  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100704b9f  mov     r8, [rcx]
0x100704ba2  mov     rdx, [rbp+0F0h+var_150]
0x100704ba6  call    qword ptr [r8+8]
0x100704baa  mov     esi, r14d
0x100704bad  test    ebx, ebx
0x100704baf  setnz   sil
0x100704bb3  mov     ebx, r14d
0x100704bb6  test    edi, edi
0x100704bb8  setnz   bl
0x100704bbb  mov     edx, 1000h; unsigned int
0x100704bc0  mov     rcx, rax; this
0x100704bc3  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100704bc8  mov     r9d, r14d
0x100704bcb  test    eax, eax
0x100704bcd  setnz   r9b
0x100704bd1  mov     rax, [r13+20h]
0x100704bd5  movzx   r8d, byte ptr [rax+11h]
  ... truncated ...
```
