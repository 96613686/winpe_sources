# CTEsConvertToWstr<231,1,1>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x100726ac0`
- end: `0x100727000`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0OH@$00$00@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1344`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x100701360`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100410bc0`
- `0x100415580`
- `0x10045e6b0`
- `0x100460690`
- `0x100726ac0`
- `0x10072bc00`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100726f91`
- `sqldk!??_V@YAXPEAX@Z` at `0x100726f91`
- `sqldk!SystemThread_TlsIndex` at `0x100726e85`
- `sqldk!SystemThread_TlsOffset` at `0x100726e8e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100726ea9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100726ea9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100726b95`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100726fd0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100726b95`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100726fd0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100726c0f`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100726c3e`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100726c6c`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100726c0f`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100726c3e`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100726c6c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100726c1b`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100726c4a`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100726c78`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100726c1b`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100726c4a`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100726c78`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100726c2e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100726c5d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100726c8b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100726c2e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100726c5d`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100726c8b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100726f64`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100726f7b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100726f64`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100726f7b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100726f87`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100726f87`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<231,1,1>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rsi
  unsigned int v5; // r14d
  unsigned int v6; // ebx
  char v7; // r10
  unsigned int v8; // edx
  __int16 *i; // r8
  __int16 v10; // ax
  int v11; // eax
  char v12; // r15
  __int64 v13; // rax
  __int64 v14; // rcx
  bool v15; // r13
  struct CSessionTraceFlags *v16; // rax
  struct CSessionTraceFlags *v17; // rax
  struct CSessionTraceFlags *v18; // rax
  __int64 v19; // rdx
  unsigned __int8 *v20; // r12
  __int64 v21; // rbx
  bool v22; // al
  int v23; // ecx
  __int64 v24; // r8
  unsigned int v25; // r12d
  unsigned int v26; // ebx
  int v27; // eax
  __int64 v28; // rax
  unsigned __int16 v29; // ax
  const struct CDefaultCollation *v30; // rsi
  __int64 v31; // r9
  const struct CTypeInfo *v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // rdx
  wchar_t *v35; // rdi
  unsigned int v36; // eax
  unsigned __int64 v37; // rbx
  char v38; // [rsp+60h] [rbp-A0h]
  unsigned int v39; // [rsp+64h] [rbp-9Ch] BYREF
  __int128 v40; // [rsp+68h] [rbp-98h] BYREF
  __int128 v41; // [rsp+78h] [rbp-88h]
  __int64 v42; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v43[16]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v44; // [rsp+A0h] [rbp-60h]
  int v45; // [rsp+A4h] [rbp-5Ch]
  __int64 v46; // [rsp+B0h] [rbp-50h]
  wchar_t *v47; // [rsp+B8h] [rbp-48h]
  _BYTE v48[208]; // [rsp+C0h] [rbp-40h] BYREF

  v46 = -2;
  v4 = a1[4];
  if ( *(int *)(v4 + 8) > 0 && *(_BYTE *)(a2 + 32) == 3 )
  {
    *(_BYTE *)a2 = 3;
    return;
  }
  if ( (*(_BYTE *)(v4 + 17) & 1) != 0 )
  {
    if ( !*(_BYTE *)a2 )
    {
      v5 = *(_DWORD *)(a2 + 16);
      v6 = v5;
      if ( v5 >= *(unsigned __int16 *)(v4 + 18) )
        v6 = *(unsigned __int16 *)(v4 + 18);
      v7 = *(_BYTE *)(v4 + 16);
      if ( v7 )
      {
        v8 = v5 >> 1;
        for ( i = (__int16 *)(*(_QWORD *)(a2 + 8) + 2LL * ((v5 >> 1) - 1)); v8; --v8 )
        {
          v10 = *i--;
          if ( v10 != 32 )
            break;
        }
        if ( 2 * (unsigned __int64)v8 > v6 )
        {
          if ( v7 == 1 )
            ex_raise(81, 52, 16, 13);
          *(_WORD *)(a2 + 2) |= 0x1000u;
        }
      }
      v11 = CTrailingBrokenCodepoints<1>(v5 >> 1, v6 >> 1, *(_QWORD *)(a2 + 8));
      if ( v11 )
        v6 -= 2 * v11;
      *(_QWORD *)(a2 + 16) = v6;
      if ( *(_BYTE *)(v4 + 15) )
        CXVariantBase::AdjustPadding<231>(a2, *(unsigned __int8 *)(v4 + 15), v6);
    }
    return;
  }
  v12 = *(_BYTE *)(v4 + 16);
  v13 = a1[9];
  v15 = 0;
  if ( v13 )
  {
    v14 = *(_QWORD *)(v13 + 408);
    if ( v14 )
    {
      if ( *(_QWORD *)(v14 + 424) )
        v15 = 1;
    }
  }
  if ( ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 0x10) != 0
     || (v16 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v16, 0x1CCu))
    && v12 == 1
    && ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) == 0
     && ((v17 = PSessTraceFlags()) == 0 || !CSessionTraceFlags::CheckSessionTraceInternal(v17, 0x1CBu))
     && v15
     || ((*(_BYTE *)(CGlobalTraceFlags::GetUlTraceFlags() + 57) & 8) != 0
      || (v18 = PSessTraceFlags()) != 0 && CSessionTraceFlags::CheckSessionTraceInternal(v18, 0x1CBu))
     && !v15) )
  {
    v12 = 2;
  }
  v39 = *(unsigned __int8 *)(v4 + 15);
  v19 = *(unsigned __int16 *)(a1[4] + 18LL);
  v20 = *(unsigned __int8 **)(a1[7] + 8 * v19);
  v21 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v19);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v20;
    *(_QWORD *)(a2 + 16) = v21;
  }
  else
  {
    LODWORD(v40) = 59139;
    *((_QWORD *)&v40 + 1) = 0;
    *(_QWORD *)&v41 = 0;
    DWORD2(v41) = 0;
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v43, 0xE7u, v21);
    if ( v43[0] == 98 )
      v44 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v43[0]))
      || ((v43[0] - 35) & 0xBF) == 0 )
    {
      v22 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v43);
      v23 = v45;
      if ( v22 )
        v23 = -1;
      v45 = v23;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v40, v20, v21, (const struct CTypeInfo *)v43, 0);
    v25 = v41;
    if ( v12 )
    {
      LOBYTE(v24) = v12 == 1;
      v38 = CheckWarnTrunc<231>(a2, (unsigned int)v41, v24);
    }
    else
    {
      v38 = 0;
    }
    v26 = *(_DWORD *)(a2 + 16);
    CXVariant::WstrConvertFromWstr(&v40, *(_QWORD *)(a2 + 8), v26, v39);
    v27 = CTrailingBrokenCodepoints<1>(v26 >> 1, v25 >> 1, *(_QWORD *)(a2 + 8));
    if ( v27 )
      *(_QWORD *)&v41 = v25 - 2 * v27;
    if ( v12 == 2 && v38 )
      WORD1(v40) |= 0x1000u;
    *(_OWORD *)a2 = v40;
    *(_OWORD *)(a2 + 16) = v41;
    *(_WORD *)(a2 + 2) &= ~1u;
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v28 = 0;
    v39 = 0;
    if ( !v15 )
    {
LABEL_75:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v28, v48);
      return;
    }
    (**(void (__fastcall ***)(struct ISqlTypeSystemExtender_ContextProvider *, __int64 *))x_pContextProvider)(
      x_pContextProvider,
      &v42);
    (*(void (__fastcall **)(struct ISqlTypeSystemExtender_ContextProvider *, __int64))(*(_QWORD *)x_pContextProvider
                                                                                     + 8LL))(
      x_pContextProvider,
      v42);
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
            &v39,
            *(struct IMemObj **)(v34 + 1000),
            v32,
            v30,
            2,
            0,
            0,
            0,
            0,
            0);
    v47 = v35;
    if ( v35 )
    {
      v36 = v39;
      if ( v39 >= 0x64 )
        v36 = 100;
    }
    else
    {
      v36 = 0;
    }
    v39 = v36;
    v37 = 2LL * v36;
    if ( v37 )
    {
      if ( !v35 || v37 > 0xC8 )
      {
        memset_0(v48, 0, 0xC8u);
        if ( v35 )
        {
          if ( v37 <= 0xC8 )
            goto LABEL_74;
          *_errno() = 34;
        }
        else
        {
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
        goto LABEL_74;
      }
      memmove(v48, v35, 2LL * v36);
    }
LABEL_74:
    operator delete[](v35);
    v28 = v39;
    goto LABEL_75;
  }
}

```

## disassembly

```asm
0x100726ac0  push    rbp
0x100726ac2  push    rsi
0x100726ac3  push    rdi
0x100726ac4  push    r12
0x100726ac6  push    r13
0x100726ac8  push    r14
0x100726aca  push    r15
0x100726acc  lea     rbp, [rsp-0A0h]
0x100726ad4  sub     rsp, 1A0h
0x100726adb  mov     [rbp+0D0h+var_120], 0FFFFFFFFFFFFFFFEh
0x100726ae3  mov     [rsp+1D0h+arg_10], rbx
0x100726aeb  mov     rax, cs:__security_cookie
0x100726af2  xor     rax, rsp
0x100726af5  mov     [rbp+0D0h+var_40], rax
0x100726afc  mov     rdi, rdx
0x100726aff  mov     r14, rcx
0x100726b02  mov     rsi, [rcx+20h]
0x100726b06  cmp     dword ptr [rsi+8], 0
0x100726b0a  jle     short loc_100726B1A
0x100726b0c  cmp     byte ptr [rdx+20h], 3
0x100726b10  jnz     short loc_100726B1A
0x100726b12  mov     byte ptr [rdx], 3
0x100726b15  jmp     loc_100726FD6
0x100726b1a  test    byte ptr [rsi+11h], 1
0x100726b1e  jz      loc_100726BE3
0x100726b24  cmp     byte ptr [rdx], 0
0x100726b27  jnz     loc_100726FD6
0x100726b2d  mov     r14d, [rdx+10h]
0x100726b31  movzx   eax, word ptr [rsi+12h]
0x100726b35  mov     ebx, r14d
0x100726b38  cmp     r14d, eax
0x100726b3b  cmovnb  ebx, eax
0x100726b3e  movzx   r10d, byte ptr [rsi+10h]
0x100726b43  test    r10b, r10b
0x100726b46  jz      short loc_100726BA4
0x100726b48  mov     edx, r14d
0x100726b4b  shr     edx, 1
0x100726b4d  lea     ecx, [rdx-1]
0x100726b50  mov     rax, [rdi+8]
0x100726b54  lea     r8, [rax+rcx*2]
0x100726b58  jz      short loc_100726B73
0x100726b5a  mov     r9d, 0FFFFFFFFh
0x100726b60  movzx   eax, word ptr [r8]
0x100726b64  lea     r8, [r8-2]
0x100726b68  cmp     ax, 20h ; ' '
0x100726b6c  jnz     short loc_100726B73
0x100726b6e  add     edx, r9d
0x100726b71  jnz     short loc_100726B60
0x100726b73  mov     ecx, edx
0x100726b75  add     rcx, rcx
0x100726b78  mov     eax, ebx
0x100726b7a  cmp     rcx, rax
0x100726b7d  jbe     short loc_100726BA4
0x100726b7f  cmp     r10b, 1
0x100726b83  jnz     short loc_100726B9B
0x100726b85  mov     edx, 34h ; '4'
0x100726b8a  lea     ecx, [rdx+1Dh]
0x100726b8d  lea     r9d, [rdx-27h]
0x100726b91  lea     r8d, [rdx-24h]
0x100726b95  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100726b9b  mov     eax, 1000h
0x100726ba0  or      [rdi+2], ax
0x100726ba4  mov     edx, ebx
0x100726ba6  shr     edx, 1
0x100726ba8  shr     r14d, 1
0x100726bab  mov     r8, [rdi+8]
0x100726baf  mov     ecx, r14d
0x100726bb2  call    ??$CTrailingBrokenCodepoints@$00@@YAIKKPEB_W@Z; CTrailingBrokenCodepoints<1>(ulong,ulong,wchar_t const *)
0x100726bb7  test    eax, eax
0x100726bb9  jz      short loc_100726BBF
0x100726bbb  add     eax, eax
0x100726bbd  sub     ebx, eax
0x100726bbf  mov     eax, ebx
0x100726bc1  mov     [rdi+10h], rax
0x100726bc5  movzx   eax, byte ptr [rsi+0Fh]
0x100726bc9  test    al, al
0x100726bcb  jz      loc_100726FD6
0x100726bd1  mov     edx, eax
0x100726bd3  mov     r8d, ebx
0x100726bd6  mov     rcx, rdi
0x100726bd9  call    ??$AdjustPadding@$0OH@@CXVariantBase@@QEAAXW4EPadding@@I@Z; CXVariantBase::AdjustPadding<231>(EPadding,uint)
0x100726bde  jmp     loc_100726FD6
0x100726be3  movzx   r15d, byte ptr [rsi+10h]
0x100726be8  mov     rax, [rcx+48h]
0x100726bec  test    rax, rax
0x100726bef  jz      short loc_100726C0C
0x100726bf1  mov     rcx, [rax+198h]
0x100726bf8  test    rcx, rcx
0x100726bfb  jz      short loc_100726C0C
0x100726bfd  cmp     qword ptr [rcx+1A8h], 0
0x100726c05  jz      short loc_100726C0C
0x100726c07  mov     r13b, 1
0x100726c0a  jmp     short loc_100726C0F
0x100726c0c  xor     r13b, r13b
0x100726c0f  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100726c15  test    byte ptr [rax+39h], 10h
0x100726c19  jnz     short loc_100726C38
0x100726c1b  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100726c21  test    rax, rax
0x100726c24  jz      short loc_100726C9D
0x100726c26  mov     edx, 1CCh
0x100726c2b  mov     rcx, rax
0x100726c2e  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100726c34  test    eax, eax
0x100726c36  jz      short loc_100726C9D
0x100726c38  cmp     r15b, 1
0x100726c3c  jnz     short loc_100726C9D
0x100726c3e  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100726c44  test    byte ptr [rax+39h], 8
0x100726c48  jnz     short loc_100726C6C
0x100726c4a  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100726c50  test    rax, rax
0x100726c53  jz      short loc_100726C67
0x100726c55  mov     edx, 1CBh
0x100726c5a  mov     rcx, rax
0x100726c5d  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100726c63  test    eax, eax
0x100726c65  jnz     short loc_100726C6C
0x100726c67  test    r13b, r13b
0x100726c6a  jnz     short loc_100726C9A
0x100726c6c  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100726c72  test    byte ptr [rax+39h], 8
0x100726c76  jnz     short loc_100726C95
0x100726c78  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100726c7e  test    rax, rax
0x100726c81  jz      short loc_100726C9D
0x100726c83  mov     edx, 1CBh
0x100726c88  mov     rcx, rax
0x100726c8b  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100726c91  test    eax, eax
0x100726c93  jz      short loc_100726C9D
0x100726c95  test    r13b, r13b
0x100726c98  jnz     short loc_100726C9D
0x100726c9a  mov     r15b, 2
0x100726c9d  movzx   eax, byte ptr [rsi+0Fh]
0x100726ca1  mov     [rsp+1D0h+var_16C], eax
0x100726ca5  mov     rax, [r14+20h]
0x100726ca9  movzx   edx, word ptr [rax+12h]
0x100726cad  mov     rax, [r14+38h]
0x100726cb1  mov     r12, [rax+rdx*8]
0x100726cb5  mov     rax, [r14+10h]
0x100726cb9  mov     rcx, [rax+20h]
0x100726cbd  movzx   ebx, word ptr [rcx+rdx*2]
0x100726cc1  xor     eax, eax
0x100726cc3  cmp     [rdi], al
0x100726cc5  jz      short loc_100726CD4
0x100726cc7  mov     [rdi+8], r12
0x100726ccb  mov     [rdi+10h], rbx
0x100726ccf  jmp     loc_100726DF6
0x100726cd4  mov     dword ptr [rsp+1D0h+var_168], 0E703h
0x100726cdc  mov     qword ptr [rsp+1D0h+var_168+8], rax
0x100726ce1  mov     qword ptr [rsp+1D0h+var_158], rax
0x100726ce6  mov     dword ptr [rbp+0D0h+var_158+8], eax
0x100726ce9  mov     r8d, ebx; int
0x100726cec  mov     dl, 0E7h; unsigned __int8
0x100726cee  lea     rcx, [rbp+0D0h+var_140]; this
0x100726cf2  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x100726cf7  movzx   edx, [rbp+0D0h+var_140]
0x100726cfb  cmp     dl, 62h ; 'b'
0x100726cfe  jnz     short loc_100726D09
0x100726d00  mov     eax, 2
0x100726d05  mov     [rbp+0D0h+var_130], ax
0x100726d09  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100726d10  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x100726d18  cmp     byte ptr [rax+rcx+45AFC0h], 0
0x100726d20  jnz     short loc_100726D2A
0x100726d22  sub     dl, 23h ; '#'
0x100726d25  test    dl, 0BFh
0x100726d28  jnz     short loc_100726D45
0x100726d2a  lea     rcx, [rbp+0D0h+var_140]; this
0x100726d2e  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x100726d33  mov     ecx, [rbp+0D0h+var_12C]
0x100726d36  mov     r9d, 0FFFFFFFFh
0x100726d3c  test    al, al
0x100726d3e  cmovnz  ecx, r9d
0x100726d42  mov     [rbp+0D0h+var_12C], ecx
0x100726d45  mov     dword ptr [rsp+1D0h+var_1B0], 0; int
0x100726d4d  lea     r9, [rbp+0D0h+var_140]; struct CTypeInfo *
0x100726d51  mov     r8d, ebx; unsigned int
0x100726d54  mov     rdx, r12; unsigned __int8 *
0x100726d57  lea     rcx, [rsp+1D0h+var_168]; this
0x100726d5c  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x100726d61  mov     r12d, dword ptr [rsp+1D0h+var_158]
0x100726d66  test    r15b, r15b
0x100726d69  jnz     short loc_100726D72
0x100726d6b  mov     [rsp+1D0h+var_170], r15b
0x100726d70  jmp     short loc_100726D89
0x100726d72  cmp     r15b, 1
0x100726d76  setz    r8b
0x100726d7a  mov     edx, r12d
0x100726d7d  mov     rcx, rdi
0x100726d80  call    ??$CheckWarnTrunc@$0OH@@@YA_NPEAVCXVariant@@I_N@Z; CheckWarnTrunc<231>(CXVariant *,uint,bool)
0x100726d85  mov     [rsp+1D0h+var_170], al
0x100726d89  mov     ebx, [rdi+10h]
0x100726d8c  mov     r9d, [rsp+1D0h+var_16C]
0x100726d91  mov     r8d, ebx
0x100726d94  mov     rdx, [rdi+8]
0x100726d98  lea     rcx, [rsp+1D0h+var_168]
0x100726d9d  call    ?WstrConvertFromWstr@CXVariant@@QEAAXPEB_WKW4EPadding@@@Z; CXVariant::WstrConvertFromWstr(wchar_t const *,ulong,EPadding)
0x100726da2  mov     edx, r12d
0x100726da5  shr     edx, 1
0x100726da7  shr     ebx, 1
0x100726da9  mov     r8, [rdi+8]
0x100726dad  mov     ecx, ebx
0x100726daf  call    ??$CTrailingBrokenCodepoints@$00@@YAIKKPEB_W@Z; CTrailingBrokenCodepoints<1>(ulong,ulong,wchar_t const *)
0x100726db4  test    eax, eax
0x100726db6  jz      short loc_100726DC5
0x100726db8  add     eax, eax
0x100726dba  sub     r12d, eax
0x100726dbd  mov     eax, r12d
0x100726dc0  mov     qword ptr [rsp+1D0h+var_158], rax
0x100726dc5  cmp     r15b, 2
0x100726dc9  jnz     short loc_100726DDC
0x100726dcb  cmp     [rsp+1D0h+var_170], 0
0x100726dd0  jz      short loc_100726DDC
0x100726dd2  mov     eax, 1000h
0x100726dd7  or      word ptr [rsp+1D0h+var_168+2], ax
0x100726ddc  movups  xmm0, [rsp+1D0h+var_168]
0x100726de1  movups  xmmword ptr [rdi], xmm0
0x100726de4  movups  xmm1, [rsp+1D0h+var_158]
0x100726de9  movups  xmmword ptr [rdi+10h], xmm1
0x100726ded  mov     eax, 0FFFEh
0x100726df2  and     [rdi+2], ax
0x100726df6  cmp     byte ptr [rsi+10h], 1
0x100726dfa  jnz     loc_100726FD6
0x100726e00  movzx   eax, word ptr [rdi+2]
0x100726e04  shr     ax, 0Ch
0x100726e08  test    al, 1
0x100726e0a  jz      loc_100726FD6
0x100726e10  xor     r15d, r15d
0x100726e13  mov     eax, r15d
0x100726e16  mov     [rsp+1D0h+var_16C], eax
0x100726e1a  test    r13b, r13b
0x100726e1d  jz      loc_100726F9B
0x100726e23  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100726e2a  mov     rax, [rcx]
0x100726e2d  lea     rdx, [rbp+0D0h+var_148]
0x100726e31  call    qword ptr [rax]
0x100726e33  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100726e3a  mov     rax, [rcx]
0x100726e3d  mov     rdx, [rbp+0D0h+var_148]
0x100726e41  call    qword ptr [rax+8]
0x100726e44  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x100726e4b  mov     rax, [rcx]
0x100726e4e  call    qword ptr [rax]
0x100726e50  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x100726e57  mov     r8, [rcx]
0x100726e5a  movzx   edx, ax
0x100726e5d  call    qword ptr [r8+8]
0x100726e61  mov     rsi, rax
0x100726e64  mov     r9, [r14+20h]
0x100726e68  movzx   edi, word ptr [r9+18h]
0x100726e6d  shl     rdi, 5
0x100726e71  mov     rcx, [r14+10h]
0x100726e75  add     rdi, [rcx+0A8h]
0x100726e7c  mov     r8, gs:58h
0x100726e85  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100726e8c  mov     edx, [rcx]
0x100726e8e  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100726e95  mov     ebx, [rcx]
0x100726e97  add     rbx, [r8+rdx*8]
0x100726e9b  mov     rdx, [rbx+100h]
0x100726ea2  test    rdx, rdx
0x100726ea5  jnz     short loc_100726EBA
0x100726ea7  xor     ecx, ecx
0x100726ea9  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100726eaf  mov     rdx, [rbx+100h]
0x100726eb6  mov     r9, [r14+20h]
0x100726eba  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x100726ec1  mov     ecx, [r9+0Ch]
0x100726ec5  mov     rax, [r14+30h]
0x100726ec9  mov     [rsp+1D0h+var_178], r15d; int
0x100726ece  mov     [rsp+1D0h+var_180], r15d; unsigned int
0x100726ed3  mov     [rsp+1D0h+var_188], r15; wchar_t *
0x100726ed8  mov     [rsp+1D0h+var_190], r15d; unsigned int
0x100726edd  mov     [rsp+1D0h+Src], r15; Src
0x100726ee2  mov     [rsp+1D0h+var_1A0], 2; int
0x100726eea  mov     [rsp+1D0h+var_1A8], rsi; struct CDefaultCollation *
0x100726eef  mov     [rsp+1D0h+var_1B0], rdi; struct CTypeInfo *
0x100726ef4  mov     r9, rdx; struct IMemObj *
0x100726ef7  lea     r8, [rsp+1D0h+var_16C]; unsigned int *
0x100726efc  mov     rcx, [rax+rcx*8]; this
0x100726f00  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x100726f05  mov     rdi, rax
0x100726f08  mov     [rbp+0D0h+var_118], rax
0x100726f0c  test    rax, rax
0x100726f0f  jnz     short loc_100726F16
0x100726f11  mov     eax, r15d
0x100726f14  jmp     short loc_100726F24
0x100726f16  mov     eax, [rsp+1D0h+var_16C]
0x100726f1a  mov     ecx, 64h ; 'd'
0x100726f1f  cmp     eax, ecx
0x100726f21  cmovnb  eax, ecx
0x100726f24  mov     [rsp+1D0h+var_16C], eax
0x100726f28  mov     ebx, eax
0x100726f2a  add     rbx, rbx
0x100726f2d  jz      short loc_100726F8E
0x100726f2f  test    rdi, rdi
0x100726f32  jz      short loc_100726F4E
0x100726f34  cmp     rbx, 0C8h
  ... truncated ...
```
