# CTEsConvertToWstr<231,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x100712290`
- end: `0x1007126ee`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0OH@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1118`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1006ffee0`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100410bc0`
- `0x100415580`
- `0x100460690`
- `0x100712290`
- `0x100728370`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10071267f`
- `sqldk!??_V@YAXPEAX@Z` at `0x10071267f`
- `sqldk!SystemThread_TlsIndex` at `0x100712573`
- `sqldk!SystemThread_TlsOffset` at `0x10071257c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100712597`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100712597`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007126be`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007126be`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071232c`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071235b`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100712389`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071232c`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071235b`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100712389`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100712338`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100712367`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100712395`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100712338`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100712367`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100712395`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071234b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071237a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007123a8`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071234b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071237a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007123a8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100712652`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100712669`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100712652`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100712669`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100712675`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100712675`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<231,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  _QWORD *v3; // rsi
  __int64 v4; // rdi
  char v5; // r14
  __int64 v6; // rax
  bool v7; // r15
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct CSessionTraceFlags *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  struct CSessionTraceFlags *v13; // rax
  struct CSessionTraceFlags *v14; // rax
  __int64 v15; // rdx
  unsigned __int8 *v16; // r13
  __int64 v17; // r12
  bool v18; // al
  int v19; // ecx
  __int64 v20; // r8
  char v21; // r12
  __int64 v22; // rax
  unsigned __int16 v23; // ax
  const struct CDefaultCollation *v24; // r14
  __int64 v25; // r9
  const struct CTypeInfo *v26; // rdi
  __int64 v27; // rbx
  __int64 v28; // rdx
  wchar_t *v29; // rdi
  unsigned int v30; // eax
  unsigned __int64 v31; // rbx
  unsigned int v32; // [rsp+60h] [rbp-A0h] BYREF
  __m256i v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v35[16]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v36; // [rsp+A0h] [rbp-60h]
  int v37; // [rsp+A4h] [rbp-5Ch]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  wchar_t *v39; // [rsp+B8h] [rbp-48h]
  _BYTE v40[208]; // [rsp+C0h] [rbp-40h] BYREF

  v38 = -2;
  v3 = a1;
  v4 = a1[4];
  if ( *(int *)(v4 + 8) > 0 && *(_BYTE *)(a2 + 32) == 3 )
  {
    *(_BYTE *)a2 = 3;
    return;
  }
  if ( (*(_BYTE *)(v4 + 17) & 1) != 0 )
  {
    ShallowCopyStrWstrBin<231,0,0>(a2, a1[4]);
    return;
  }
  v5 = *(_BYTE *)(v4 + 16);
  v6 = a1[9];
  v7 = 0;
  if ( v6 )
  {
    a1 = *(_QWORD **)(v6 + 408);
    if ( a1 )
    {
      if ( a1[53] )
        v7 = 1;
    }
  }
  if ( ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags(a1, a2) + 57) & 0x10) != 0
     || (v10 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v10, 0x1CCu))
    && v5 == 1
    && ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags(v9, v8) + 57) & 8) == 0
     && ((v13 = PSessTraceFlags()) == 0 || !CSessionTraceFlags::CheckSessionTraceInternal(v13, 0x1CBu))
     && v7
     || ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags(v12, v11) + 57) & 8) != 0
      || (v14 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v14, 0x1CBu))
     && !v7) )
  {
    v5 = 2;
  }
  v32 = *(unsigned __int8 *)(v4 + 15);
  v15 = *(unsigned __int16 *)(v3[4] + 18LL);
  v16 = *(unsigned __int8 **)(v3[7] + 8 * v15);
  v17 = *(unsigned __int16 *)(*(_QWORD *)(v3[2] + 32LL) + 2 * v15);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v16;
    *(_QWORD *)(a2 + 16) = v17;
  }
  else
  {
    v33.m256i_i32[0] = 59139;
    memset(&v33.m256i_u64[1], 0, 20);
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v35, 0xE7u, v17);
    if ( v35[0] == 98 )
      v36 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v35[0]))
      || ((v35[0] - 35) & 0xBF) == 0 )
    {
      v18 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v35);
      v19 = v37;
      if ( v18 )
        v19 = -1;
      v37 = v19;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v33, v16, v17, (const struct CTypeInfo *)v35, 0);
    if ( v5 )
    {
      LOBYTE(v20) = v5 == 1;
      v21 = CheckWarnTrunc<231>(a2, v33.m256i_u32[4], v20);
    }
    else
    {
      v21 = 0;
    }
    CXVariant::WstrConvertFromWstr(&v33, *(_QWORD *)(a2 + 8), *(unsigned int *)(a2 + 16), v32);
    if ( v5 == 2 && v21 )
      v33.m256i_i16[1] |= 0x1000u;
    *(__m256i *)a2 = v33;
    *(_WORD *)(a2 + 2) &= ~1u;
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v22 = 0;
    v32 = 0;
    if ( !v7 )
    {
LABEL_59:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v22, v40);
      return;
    }
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v34);
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider
                                                                                     + 8LL))(
      x_pContextProvider,
      v34);
    v23 = (**(__int64 (__fastcall ***)(struct ISqlTypeSystemExtender_IDbAndSetOptsProvider *))x_pIDbOptsProvider)(x_pIDbOptsProvider);
    v24 = (const struct CDefaultCollation *)(*(__int64 (__fastcall **)(struct ISqlTypeSystemExtender_IDbTableOptionsProvider *, _QWORD))(*(_QWORD *)x_pIDbTableProvider + 8LL))(
                                              x_pIDbTableProvider,
                                              v23);
    v25 = v3[4];
    v26 = (const struct CTypeInfo *)(*(_QWORD *)(v3[2] + 168LL) + 32LL * *(unsigned __int16 *)(v25 + 24));
    v27 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v28 = *(_QWORD *)(v27 + 256);
    if ( !v28 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v28 = *(_QWORD *)(v27 + 256);
      v25 = v3[4];
    }
    v29 = CXVariant::PwchConvertToStringInternal(
            *(CXVariant **)(v3[6] + 8LL * *(unsigned int *)(v25 + 12)),
            *(struct IMemObj **)(v28 + 1000),
            &v32,
            *(struct IMemObj **)(v28 + 1000),
            v26,
            v24,
            2,
            0,
            0,
            0,
            0,
            0);
    v39 = v29;
    if ( v29 )
    {
      v30 = v32;
      if ( v32 >= 0x64 )
        v30 = 100;
    }
    else
    {
      v30 = 0;
    }
    v32 = v30;
    v31 = 2LL * v30;
    if ( v31 )
    {
      if ( !v29 || v31 > 0xC8 )
      {
        memset_0(v40, 0, 0xC8u);
        if ( v29 )
        {
          if ( v31 <= 0xC8 )
            goto LABEL_58;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_58;
      }
      memmove(v40, v29, 2LL * v30);
    }
LABEL_58:
    operator delete[](v29);
    v22 = v32;
    goto LABEL_59;
  }
}

```

## disassembly

```asm
0x100712290  push    rbp
0x100712292  push    rsi
0x100712293  push    rdi
0x100712294  push    r12
0x100712296  push    r13
0x100712298  push    r14
0x10071229a  push    r15
0x10071229c  lea     rbp, [rsp-0A0h]
0x1007122a4  sub     rsp, 1A0h
0x1007122ab  mov     [rbp+0D0h+var_120], 0FFFFFFFFFFFFFFFEh
0x1007122b3  mov     [rsp+1D0h+arg_10], rbx
0x1007122bb  mov     rax, cs:__security_cookie
0x1007122c2  xor     rax, rsp
0x1007122c5  mov     [rbp+0D0h+var_40], rax
0x1007122cc  mov     rbx, rdx
0x1007122cf  mov     rsi, rcx
0x1007122d2  mov     rdi, [rcx+20h]
0x1007122d6  cmp     dword ptr [rdi+8], 0
0x1007122da  jle     short loc_1007122EA
0x1007122dc  cmp     byte ptr [rdx+20h], 3
0x1007122e0  jnz     short loc_1007122EA
0x1007122e2  mov     byte ptr [rdx], 3
0x1007122e5  jmp     loc_1007126C4
0x1007122ea  test    byte ptr [rdi+11h], 1
0x1007122ee  jz      short loc_100712300
0x1007122f0  mov     rdx, rdi
0x1007122f3  mov     rcx, rbx
0x1007122f6  call    ??$ShallowCopyStrWstrBin@$0OH@$0A@$0A@@@YAXPEAVCXVariant@@PEAUCXCodeInst@@I@Z; ShallowCopyStrWstrBin<231,0,0>(CXVariant *,CXCodeInst *,uint)
0x1007122fb  jmp     loc_1007126C4
0x100712300  movzx   r14d, byte ptr [rdi+10h]
0x100712305  mov     rax, [rcx+48h]
0x100712309  test    rax, rax
0x10071230c  jz      short loc_100712329
0x10071230e  mov     rcx, [rax+198h]
0x100712315  test    rcx, rcx
0x100712318  jz      short loc_100712329
0x10071231a  cmp     qword ptr [rcx+1A8h], 0
0x100712322  jz      short loc_100712329
0x100712324  mov     r15b, 1
0x100712327  jmp     short loc_10071232C
0x100712329  xor     r15b, r15b
0x10071232c  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100712332  test    byte ptr [rax+39h], 10h
0x100712336  jnz     short loc_100712355
0x100712338  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071233e  test    rax, rax
0x100712341  jz      short loc_1007123BA
0x100712343  mov     edx, 1CCh
0x100712348  mov     rcx, rax
0x10071234b  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100712351  test    eax, eax
0x100712353  jz      short loc_1007123BA
0x100712355  cmp     r14b, 1
0x100712359  jnz     short loc_1007123BA
0x10071235b  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100712361  test    byte ptr [rax+39h], 8
0x100712365  jnz     short loc_100712389
0x100712367  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071236d  test    rax, rax
0x100712370  jz      short loc_100712384
0x100712372  mov     edx, 1CBh
0x100712377  mov     rcx, rax
0x10071237a  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100712380  test    eax, eax
0x100712382  jnz     short loc_100712389
0x100712384  test    r15b, r15b
0x100712387  jnz     short loc_1007123B7
0x100712389  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071238f  test    byte ptr [rax+39h], 8
0x100712393  jnz     short loc_1007123B2
0x100712395  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071239b  test    rax, rax
0x10071239e  jz      short loc_1007123BA
0x1007123a0  mov     edx, 1CBh
0x1007123a5  mov     rcx, rax
0x1007123a8  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007123ae  test    eax, eax
0x1007123b0  jz      short loc_1007123BA
0x1007123b2  test    r15b, r15b
0x1007123b5  jnz     short loc_1007123BA
0x1007123b7  mov     r14b, 2
0x1007123ba  movzx   eax, byte ptr [rdi+0Fh]
0x1007123be  mov     [rsp+1D0h+var_170], eax
0x1007123c2  mov     rax, [rsi+20h]
0x1007123c6  movzx   edx, word ptr [rax+12h]
0x1007123ca  mov     rax, [rsi+38h]
0x1007123ce  mov     r13, [rax+rdx*8]
0x1007123d2  mov     rax, [rsi+10h]
0x1007123d6  mov     rcx, [rax+20h]
0x1007123da  movzx   r12d, word ptr [rcx+rdx*2]
0x1007123df  xor     eax, eax
0x1007123e1  cmp     [rbx], al
0x1007123e3  jz      short loc_1007123F2
0x1007123e5  mov     [rbx+8], r13
0x1007123e9  mov     [rbx+10h], r12
0x1007123ed  jmp     loc_1007124E4
0x1007123f2  mov     dword ptr [rsp+1D0h+var_168], 0E703h
0x1007123fa  xorps   xmm0, xmm0
0x1007123fd  movdqu  [rsp+1D0h+var_168+8], xmm0
0x100712403  mov     [rbp+0D0h+var_150], eax
0x100712406  mov     r8d, r12d; int
0x100712409  mov     dl, 0E7h; unsigned __int8
0x10071240b  lea     rcx, [rbp+0D0h+var_140]; this
0x10071240f  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x100712414  movzx   edx, [rbp+0D0h+var_140]
0x100712418  cmp     dl, 62h ; 'b'
0x10071241b  jnz     short loc_100712426
0x10071241d  mov     eax, 2
0x100712422  mov     [rbp+0D0h+var_130], ax
0x100712426  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10071242d  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x100712435  cmp     byte ptr [rax+rcx+45AFC0h], 0
0x10071243d  jnz     short loc_100712447
0x10071243f  sub     dl, 23h ; '#'
0x100712442  test    dl, 0BFh
0x100712445  jnz     short loc_100712460
0x100712447  lea     rcx, [rbp+0D0h+var_140]; this
0x10071244b  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x100712450  mov     ecx, [rbp+0D0h+var_12C]
0x100712453  mov     edx, 0FFFFFFFFh
0x100712458  test    al, al
0x10071245a  cmovnz  ecx, edx
0x10071245d  mov     [rbp+0D0h+var_12C], ecx
0x100712460  mov     dword ptr [rsp+1D0h+var_1B0], 0; int
0x100712468  lea     r9, [rbp+0D0h+var_140]; struct CTypeInfo *
0x10071246c  mov     r8d, r12d; unsigned int
0x10071246f  mov     rdx, r13; unsigned __int8 *
0x100712472  lea     rcx, [rsp+1D0h+var_168]; this
0x100712477  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x10071247c  test    r14b, r14b
0x10071247f  jnz     short loc_100712486
0x100712481  xor     r12b, r12b
0x100712484  jmp     short loc_10071249E
0x100712486  cmp     r14b, 1
0x10071248a  setz    r8b
0x10071248e  mov     edx, [rsp+78h]
0x100712492  mov     rcx, rbx
0x100712495  call    ??$CheckWarnTrunc@$0OH@@@YA_NPEAVCXVariant@@I_N@Z; CheckWarnTrunc<231>(CXVariant *,uint,bool)
0x10071249a  movzx   r12d, al
0x10071249e  mov     r9d, [rsp+1D0h+var_170]
0x1007124a3  mov     r8d, [rbx+10h]
0x1007124a7  mov     rdx, [rbx+8]
0x1007124ab  lea     rcx, [rsp+1D0h+var_168]
0x1007124b0  call    ?WstrConvertFromWstr@CXVariant@@QEAAXPEB_WKW4EPadding@@@Z; CXVariant::WstrConvertFromWstr(wchar_t const *,ulong,EPadding)
0x1007124b5  cmp     r14b, 2
0x1007124b9  jnz     short loc_1007124CA
0x1007124bb  test    r12b, r12b
0x1007124be  jz      short loc_1007124CA
0x1007124c0  mov     eax, 1000h
0x1007124c5  or      word ptr [rsp+1D0h+var_168+2], ax
0x1007124ca  movups  xmm0, [rsp+1D0h+var_168]
0x1007124cf  movups  xmmword ptr [rbx], xmm0
0x1007124d2  movups  xmm1, xmmword ptr [rsp+78h]
0x1007124d7  movups  xmmword ptr [rbx+10h], xmm1
0x1007124db  mov     eax, 0FFFEh
0x1007124e0  and     [rbx+2], ax
0x1007124e4  cmp     byte ptr [rdi+10h], 1
0x1007124e8  jnz     loc_1007126C4
0x1007124ee  movzx   eax, word ptr [rbx+2]
0x1007124f2  shr     ax, 0Ch
0x1007124f6  test    al, 1
0x1007124f8  jz      loc_1007126C4
0x1007124fe  xor     r12d, r12d
0x100712501  mov     eax, r12d
0x100712504  mov     [rsp+1D0h+var_170], eax
0x100712508  test    r15b, r15b
0x10071250b  jz      loc_100712689
0x100712511  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100712518  mov     rax, [rcx]
0x10071251b  lea     rdx, [rbp+0D0h+var_148]
0x10071251f  call    qword ptr [rax]
0x100712521  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100712528  mov     rax, [rcx]
0x10071252b  mov     rdx, [rbp+0D0h+var_148]
0x10071252f  call    qword ptr [rax+8]
0x100712532  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x100712539  mov     rax, [rcx]
0x10071253c  call    qword ptr [rax]
0x10071253e  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x100712545  mov     r8, [rcx]
0x100712548  movzx   edx, ax
0x10071254b  call    qword ptr [r8+8]
0x10071254f  mov     r14, rax
0x100712552  mov     r9, [rsi+20h]
0x100712556  movzx   edi, word ptr [r9+18h]
0x10071255b  shl     rdi, 5
0x10071255f  mov     rcx, [rsi+10h]
0x100712563  add     rdi, [rcx+0A8h]
0x10071256a  mov     r8, gs:58h
0x100712573  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10071257a  mov     edx, [rcx]
0x10071257c  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100712583  mov     ebx, [rcx]
0x100712585  add     rbx, [r8+rdx*8]
0x100712589  mov     rdx, [rbx+100h]
0x100712590  test    rdx, rdx
0x100712593  jnz     short loc_1007125A8
0x100712595  xor     ecx, ecx
0x100712597  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10071259d  mov     rdx, [rbx+100h]
0x1007125a4  mov     r9, [rsi+20h]
0x1007125a8  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x1007125af  mov     ecx, [r9+0Ch]
0x1007125b3  mov     rax, [rsi+30h]
0x1007125b7  mov     [rsp+1D0h+var_178], r12d; int
0x1007125bc  mov     [rsp+1D0h+var_180], r12d; unsigned int
0x1007125c1  mov     [rsp+1D0h+var_188], r12; wchar_t *
0x1007125c6  mov     [rsp+1D0h+var_190], r12d; unsigned int
0x1007125cb  mov     [rsp+1D0h+Src], r12; Src
0x1007125d0  mov     [rsp+1D0h+var_1A0], 2; int
0x1007125d8  mov     [rsp+1D0h+var_1A8], r14; struct CDefaultCollation *
0x1007125dd  mov     [rsp+1D0h+var_1B0], rdi; struct CTypeInfo *
0x1007125e2  mov     r9, rdx; struct IMemObj *
0x1007125e5  lea     r8, [rsp+1D0h+var_170]; unsigned int *
0x1007125ea  mov     rcx, [rax+rcx*8]; this
0x1007125ee  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x1007125f3  mov     rdi, rax
0x1007125f6  mov     [rbp+0D0h+var_118], rax
0x1007125fa  test    rax, rax
0x1007125fd  jnz     short loc_100712604
0x1007125ff  mov     eax, r12d
0x100712602  jmp     short loc_100712612
0x100712604  mov     eax, [rsp+1D0h+var_170]
0x100712608  mov     ecx, 64h ; 'd'
0x10071260d  cmp     eax, ecx
0x10071260f  cmovnb  eax, ecx
0x100712612  mov     [rsp+1D0h+var_170], eax
0x100712616  mov     ebx, eax
0x100712618  add     rbx, rbx
0x10071261b  jz      short loc_10071267C
0x10071261d  test    rdi, rdi
0x100712620  jz      short loc_10071263C
0x100712622  cmp     rbx, 0C8h
0x100712629  ja      short loc_10071263C
0x10071262b  mov     r8, rbx; Size
0x10071262e  mov     rdx, rdi; Src
0x100712631  lea     rcx, [rbp+0D0h+var_110]; void *
0x100712635  call    memmove
0x10071263a  jmp     short loc_10071267C
0x10071263c  xor     edx, edx; Val
0x10071263e  mov     r8d, 0C8h; Size
0x100712644  lea     rcx, [rbp+0D0h+var_110]; void *
0x100712648  call    memset_0
0x10071264d  test    rdi, rdi
0x100712650  jnz     short loc_100712660
0x100712652  call    cs:__imp__errno
0x100712658  mov     dword ptr [rax], 16h
0x10071265e  jmp     short loc_100712675
0x100712660  cmp     rbx, 0C8h
0x100712667  jbe     short loc_10071267C
0x100712669  call    cs:__imp__errno
0x10071266f  mov     dword ptr [rax], 22h ; '"'
0x100712675  call    cs:__imp__invalid_parameter_noinfo
0x10071267b  nop
0x10071267c  mov     rcx, rdi
0x10071267f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100712685  mov     eax, [rsp+1D0h+var_170]
0x100712689  add     rax, rax
0x10071268c  lea     rcx, [rbp+0D0h+var_110]
0x100712690  mov     [rsp+1D0h+var_188], rcx
0x100712695  mov     qword ptr [rsp+1D0h+var_190], rax
0x10071269a  mov     [rsp+1D0h+Src], r12
0x10071269f  mov     qword ptr [rsp+1D0h+var_1A0], r12
0x1007126a4  mov     [rsp+1D0h+var_1A8], r12
0x1007126a9  mov     [rsp+1D0h+var_1B0], r12
0x1007126ae  mov     edx, 1Ch
0x1007126b3  lea     ecx, [rdx-2]
0x1007126b6  lea     r9d, [rdx-1Ah]
0x1007126ba  lea     r8d, [rdx-0Ch]
0x1007126be  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1007126c4  mov     rcx, [rbp+0D0h+var_40]
0x1007126cb  xor     rcx, rsp; StackCookie
0x1007126ce  call    __security_check_cookie
0x1007126d3  mov     rbx, [rsp+1D0h+arg_10]
0x1007126db  add     rsp, 1A0h
0x1007126e2  pop     r15
0x1007126e4  pop     r14
0x1007126e6  pop     r13
0x1007126e8  pop     r12
0x1007126ea  pop     rdi
0x1007126eb  pop     rsi
0x1007126ec  pop     rbp
0x1007126ed  retn
```
