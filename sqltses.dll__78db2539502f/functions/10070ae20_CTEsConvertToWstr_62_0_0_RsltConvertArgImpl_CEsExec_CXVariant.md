# CTEsConvertToWstr<62,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x10070ae20`
- end: `0x10070b347`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0DO@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1319`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1006ff7e0`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x100410bc0`
- `0x100416790`
- `0x10047a590`
- `0x10070ae20`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10070b1e3`
- `sqldk!??_V@YAXPEAX@Z` at `0x10070b1e3`
- `sqldk!SystemThread_TlsIndex` at `0x10070b0d7`
- `sqldk!SystemThread_TlsOffset` at `0x10070b0e0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10070b0fb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10070b0fb`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10070b222`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10070b222`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070aec0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070aeef`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070af1d`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070aec0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070aeef`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10070af1d`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070aecc`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070aefb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070af29`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070aecc`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070aefb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070af29`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070aedf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070af0e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070af3c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070aedf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070af0e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070af3c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070b1b6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070b1cd`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070b1b6`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070b1cd`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10070b1d9`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10070b1d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<62,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  bool v5; // zf
  unsigned int v6; // r12d
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
  __int64 v20; // rdx
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
    v17 = CXVariant::WstrConvertFromR8(&v40, v20, v37, v6);
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
      0x3Eu,
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
0x10070ae20  push    rbp
0x10070ae22  push    rsi
0x10070ae23  push    rdi
0x10070ae24  push    r12
0x10070ae26  push    r13
0x10070ae28  push    r14
0x10070ae2a  push    r15
0x10070ae2c  lea     rbp, [rsp-0C0h]
0x10070ae34  sub     rsp, 1C0h
0x10070ae3b  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x10070ae43  mov     [rsp+1F0h+arg_10], rbx
0x10070ae4b  mov     rax, cs:__security_cookie
0x10070ae52  xor     rax, rsp
0x10070ae55  mov     [rbp+0F0h+var_40], rax
0x10070ae5c  mov     r15, rdx
0x10070ae5f  mov     r13, rcx
0x10070ae62  mov     rbx, [rcx+20h]
0x10070ae66  cmp     dword ptr [rbx+8], 0
0x10070ae6a  jle     short loc_10070AE8B
0x10070ae6c  cmp     byte ptr [rdx+20h], 3
0x10070ae70  mov     r12d, 0FFFFFFFFh
0x10070ae76  jz      short loc_10070AE7C
0x10070ae78  mov     r12d, [rdx+28h]
0x10070ae7c  mov     [rsp+1F0h+var_18C], r12d
0x10070ae81  jnz     short loc_10070AE95
0x10070ae83  mov     byte ptr [rdx], 3
0x10070ae86  jmp     loc_10070B31D
0x10070ae8b  movzx   r12d, byte ptr [rbx+0Eh]
0x10070ae90  mov     [rsp+1F0h+var_18C], r12d
0x10070ae95  movzx   esi, byte ptr [rbx+10h]
0x10070ae99  mov     rax, [rcx+48h]
0x10070ae9d  test    rax, rax
0x10070aea0  jz      short loc_10070AEBD
0x10070aea2  mov     rax, [rax+198h]
0x10070aea9  test    rax, rax
0x10070aeac  jz      short loc_10070AEBD
0x10070aeae  cmp     qword ptr [rax+1A8h], 0
0x10070aeb6  jz      short loc_10070AEBD
0x10070aeb8  mov     dil, 1
0x10070aebb  jmp     short loc_10070AEC0
0x10070aebd  xor     dil, dil
0x10070aec0  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10070aec6  test    byte ptr [rax+39h], 10h
0x10070aeca  jnz     short loc_10070AEE9
0x10070aecc  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10070aed2  test    rax, rax
0x10070aed5  jz      short loc_10070AF42
0x10070aed7  mov     edx, 1CCh
0x10070aedc  mov     rcx, rax
0x10070aedf  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10070aee5  test    eax, eax
0x10070aee7  jz      short loc_10070AF42
0x10070aee9  cmp     sil, 1
0x10070aeed  jnz     short loc_10070AF42
0x10070aeef  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10070aef5  test    byte ptr [rax+39h], 8
0x10070aef9  jnz     short loc_10070AF1D
0x10070aefb  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10070af01  test    rax, rax
0x10070af04  jz      short loc_10070AF18
0x10070af06  mov     edx, 1CBh
0x10070af0b  mov     rcx, rax
0x10070af0e  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10070af14  test    eax, eax
0x10070af16  jnz     short loc_10070AF1D
0x10070af18  test    dil, dil
0x10070af1b  jnz     short loc_10070AF42
0x10070af1d  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10070af23  test    byte ptr [rax+39h], 8
0x10070af27  jnz     short loc_10070AF42
0x10070af29  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10070af2f  test    rax, rax
0x10070af32  jz      short loc_10070AF42
0x10070af34  mov     edx, 1CBh
0x10070af39  mov     rcx, rax
0x10070af3c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10070af42  movzx   eax, byte ptr [rbx+0Fh]
0x10070af46  mov     [rsp+1F0h+var_190], eax
0x10070af4a  mov     rax, [r13+20h]
0x10070af4e  movzx   edx, word ptr [rax+12h]
0x10070af52  mov     rax, [r13+38h]
0x10070af56  mov     r8, [rax+rdx*8]
0x10070af5a  mov     [rsp+1F0h+var_188], r8
0x10070af5f  mov     rax, [r13+10h]
0x10070af63  mov     rcx, [rax+20h]
0x10070af67  movzx   esi, word ptr [rcx+rdx*2]
0x10070af6b  xor     r14d, r14d
0x10070af6e  cmp     [r15], r14b
0x10070af71  jz      short loc_10070AF83
0x10070af73  mov     [r15+8], r8
0x10070af77  mov     [r15+10h], rsi
0x10070af7b  mov     r12d, r14d
0x10070af7e  jmp     loc_10070B048
0x10070af83  mov     dword ptr [rsp+1F0h+var_180], 0E703h
0x10070af8b  xorps   xmm0, xmm0
0x10070af8e  movdqu  [rsp+1F0h+var_180+8], xmm0
0x10070af94  mov     [rbp+0F0h+var_168], r14d
0x10070af98  mov     r8d, esi; int
0x10070af9b  mov     dl, 0E7h; unsigned __int8
0x10070af9d  lea     rcx, [rbp+0F0h+var_148]; this
0x10070afa1  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x10070afa6  movzx   edx, [rbp+0F0h+var_148]
0x10070afaa  cmp     dl, 62h ; 'b'
0x10070afad  jnz     short loc_10070AFB8
0x10070afaf  mov     eax, 2
0x10070afb4  mov     [rbp+0F0h+var_138], ax
0x10070afb8  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10070afbf  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x10070afc7  cmp     [rax+rcx+45AFC0h], r14b
0x10070afcf  jnz     short loc_10070AFD9
0x10070afd1  sub     dl, 23h ; '#'
0x10070afd4  test    dl, 0BFh
0x10070afd7  jnz     short loc_10070AFF2
0x10070afd9  lea     rcx, [rbp+0F0h+var_148]; this
0x10070afdd  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x10070afe2  mov     ecx, [rbp+0F0h+var_134]
0x10070afe5  mov     edx, 0FFFFFFFFh
0x10070afea  test    al, al
0x10070afec  cmovnz  ecx, edx
0x10070afef  mov     [rbp+0F0h+var_134], ecx
0x10070aff2  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x10070aff7  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x10070affb  mov     r8d, esi; unsigned int
0x10070affe  mov     rdx, [rsp+1F0h+var_188]; unsigned __int8 *
0x10070b003  lea     rcx, [rsp+1F0h+var_180]; this
0x10070b008  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x10070b00d  mov     r9d, r12d
0x10070b010  mov     r8d, [rsp+1F0h+var_190]
0x10070b015  movsd   xmm1, qword ptr [r15+8]
0x10070b01b  lea     rcx, [rsp+1F0h+var_180]
0x10070b020  call    ?WstrConvertFromR8@CXVariant@@QEAAJNW4EPadding@@J@Z; CXVariant::WstrConvertFromR8(double,EPadding,long)
0x10070b025  mov     r12d, eax
0x10070b028  test    eax, eax
0x10070b02a  jnz     short loc_10070B048
0x10070b02c  movups  xmm0, [rsp+1F0h+var_180]
0x10070b031  movups  xmmword ptr [r15], xmm0
0x10070b035  movups  xmm1, xmmword ptr [rbp-80h]
0x10070b039  movups  xmmword ptr [r15+10h], xmm1
0x10070b03e  mov     eax, 0FFFEh
0x10070b043  and     [r15+2], ax
0x10070b048  cmp     byte ptr [rbx+10h], 1
0x10070b04c  jnz     loc_10070B228
0x10070b052  movzx   eax, word ptr [r15+2]
0x10070b057  shr     ax, 0Ch
0x10070b05b  test    al, 1
0x10070b05d  jz      loc_10070B228
0x10070b063  mov     eax, r14d
0x10070b066  mov     [rsp+1F0h+var_190], eax
0x10070b06a  test    dil, dil
0x10070b06d  jz      loc_10070B1ED
0x10070b073  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070b07a  mov     rax, [rcx]
0x10070b07d  lea     rdx, [rsp+1F0h+var_188]
0x10070b082  call    qword ptr [rax]
0x10070b084  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070b08b  mov     rax, [rcx]
0x10070b08e  mov     rdx, [rsp+1F0h+var_188]
0x10070b093  call    qword ptr [rax+8]
0x10070b096  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x10070b09d  mov     rax, [rcx]
0x10070b0a0  call    qword ptr [rax]
0x10070b0a2  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x10070b0a9  mov     r8, [rcx]
0x10070b0ac  movzx   edx, ax
0x10070b0af  call    qword ptr [r8+8]
0x10070b0b3  mov     rsi, rax
0x10070b0b6  mov     r9, [r13+20h]
0x10070b0ba  movzx   ebx, word ptr [r9+18h]
0x10070b0bf  shl     rbx, 5
0x10070b0c3  mov     rcx, [r13+10h]
0x10070b0c7  add     rbx, [rcx+0A8h]
0x10070b0ce  mov     r8, gs:58h
0x10070b0d7  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10070b0de  mov     edx, [rcx]
0x10070b0e0  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10070b0e7  mov     edi, [rcx]
0x10070b0e9  add     rdi, [r8+rdx*8]
0x10070b0ed  mov     rdx, [rdi+100h]
0x10070b0f4  test    rdx, rdx
0x10070b0f7  jnz     short loc_10070B10C
0x10070b0f9  xor     ecx, ecx
0x10070b0fb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10070b101  mov     rdx, [rdi+100h]
0x10070b108  mov     r9, [r13+20h]
0x10070b10c  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x10070b113  mov     ecx, [r9+0Ch]
0x10070b117  mov     rax, [r13+30h]
0x10070b11b  mov     [rsp+1F0h+var_198], r14d; int
0x10070b120  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x10070b125  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x10070b12a  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x10070b12f  mov     [rsp+1F0h+Src], r14; Src
0x10070b134  mov     [rsp+1F0h+var_1C0], 2; int
0x10070b13c  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x10070b141  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x10070b146  mov     r9, rdx; struct IMemObj *
0x10070b149  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x10070b14e  mov     rcx, [rax+rcx*8]; this
0x10070b152  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x10070b157  mov     rdi, rax
0x10070b15a  mov     [rbp+0F0h+var_120], rax
0x10070b15e  test    rax, rax
0x10070b161  jnz     short loc_10070B168
0x10070b163  mov     eax, r14d
0x10070b166  jmp     short loc_10070B176
0x10070b168  mov     eax, [rsp+1F0h+var_190]
0x10070b16c  mov     ecx, 64h ; 'd'
0x10070b171  cmp     eax, ecx
0x10070b173  cmovnb  eax, ecx
0x10070b176  mov     [rsp+1F0h+var_190], eax
0x10070b17a  mov     ebx, eax
0x10070b17c  add     rbx, rbx
0x10070b17f  jz      short loc_10070B1E0
0x10070b181  test    rdi, rdi
0x10070b184  jz      short loc_10070B1A0
0x10070b186  cmp     rbx, 0C8h
0x10070b18d  ja      short loc_10070B1A0
0x10070b18f  mov     r8, rbx; Size
0x10070b192  mov     rdx, rdi; Src
0x10070b195  lea     rcx, [rbp+0F0h+var_110]; void *
0x10070b199  call    memmove
0x10070b19e  jmp     short loc_10070B1E0
0x10070b1a0  xor     edx, edx; Val
0x10070b1a2  mov     r8d, 0C8h; Size
0x10070b1a8  lea     rcx, [rbp+0F0h+var_110]; void *
0x10070b1ac  call    memset_0
0x10070b1b1  test    rdi, rdi
0x10070b1b4  jnz     short loc_10070B1C4
0x10070b1b6  call    cs:__imp__errno
0x10070b1bc  mov     dword ptr [rax], 16h
0x10070b1c2  jmp     short loc_10070B1D9
0x10070b1c4  cmp     rbx, 0C8h
0x10070b1cb  jbe     short loc_10070B1E0
0x10070b1cd  call    cs:__imp__errno
0x10070b1d3  mov     dword ptr [rax], 22h ; '"'
0x10070b1d9  call    cs:__imp__invalid_parameter_noinfo
0x10070b1df  nop
0x10070b1e0  mov     rcx, rdi
0x10070b1e3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10070b1e9  mov     eax, [rsp+1F0h+var_190]
0x10070b1ed  add     rax, rax
0x10070b1f0  lea     rcx, [rbp+0F0h+var_110]
0x10070b1f4  mov     [rsp+1F0h+var_1A8], rcx
0x10070b1f9  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x10070b1fe  mov     [rsp+1F0h+Src], r14
0x10070b203  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x10070b208  mov     [rsp+1F0h+var_1C8], r14
0x10070b20d  mov     [rsp+1F0h+var_1D0], r14
0x10070b212  mov     edx, 1Ch
0x10070b217  lea     ecx, [rdx-2]
0x10070b21a  lea     r9d, [rdx-1Ah]
0x10070b21e  lea     r8d, [rdx-0Ch]
0x10070b222  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10070b228  test    r12d, r12d
0x10070b22b  jz      loc_10070B31D
0x10070b231  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070b238  mov     rax, [rcx]
0x10070b23b  lea     rdx, [rbp+0F0h+var_160]
0x10070b23f  call    qword ptr [rax]
0x10070b241  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070b248  mov     rax, [rcx]
0x10070b24b  mov     rdx, [rbp+0F0h+var_160]
0x10070b24f  call    qword ptr [rax+8]
0x10070b252  mov     edx, 800h; unsigned int
0x10070b257  mov     rcx, rax; this
0x10070b25a  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10070b25f  mov     ebx, eax
0x10070b261  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070b268  mov     r8, [rcx]
0x10070b26b  lea     rdx, [rbp+0F0h+var_158]
0x10070b26f  call    qword ptr [r8]
0x10070b272  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070b279  mov     r8, [rcx]
0x10070b27c  mov     rdx, [rbp+0F0h+var_158]
0x10070b280  call    qword ptr [r8+8]
0x10070b284  mov     edx, 10000000h; unsigned int
0x10070b289  mov     rcx, rax; this
0x10070b28c  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10070b291  mov     edi, eax
0x10070b293  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070b29a  mov     r8, [rcx]
0x10070b29d  lea     rdx, [rbp+0F0h+var_150]
0x10070b2a1  call    qword ptr [r8]
0x10070b2a4  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070b2ab  mov     r8, [rcx]
0x10070b2ae  mov     rdx, [rbp+0F0h+var_150]
0x10070b2b2  call    qword ptr [r8+8]
0x10070b2b6  mov     esi, r14d
0x10070b2b9  test    ebx, ebx
0x10070b2bb  setnz   sil
0x10070b2bf  mov     ebx, r14d
0x10070b2c2  test    edi, edi
0x10070b2c4  setnz   bl
0x10070b2c7  mov     edx, 1000h; unsigned int
0x10070b2cc  mov     rcx, rax; this
0x10070b2cf  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10070b2d4  mov     r9d, r14d
0x10070b2d7  test    eax, eax
0x10070b2d9  setnz   r9b
0x10070b2dd  mov     rax, [r13+20h]
  ... truncated ...
```
