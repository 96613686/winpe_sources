# CTEsConvertToWstr<36,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x10071fba0`
- end: `0x1007200ba`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0CE@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1306`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x100700ec0`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x100410bc0`
- `0x10044e120`
- `0x10047a590`
- `0x10071fba0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10071ff56`
- `sqldk!??_V@YAXPEAX@Z` at `0x10071ff56`
- `sqldk!SystemThread_TlsIndex` at `0x10071fe4a`
- `sqldk!SystemThread_TlsOffset` at `0x10071fe53`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10071fe6e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10071fe6e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10071ff95`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10071ff95`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071fc40`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071fc6f`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071fc9d`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071fc40`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071fc6f`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071fc9d`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071fc4c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071fc7b`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071fca9`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071fc4c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071fc7b`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071fca9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071fc5f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071fc8e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071fcbc`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071fc5f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071fc8e`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071fcbc`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071ff29`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071ff40`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071ff29`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071ff40`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10071ff4c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10071ff4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<36,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
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
    v16 = CXVariant::WstrConvertFromGuid(&v37, a2 + 8, v35);
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
      0x24u,
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
0x10071fba0  push    rbp
0x10071fba2  push    rsi
0x10071fba3  push    rdi
0x10071fba4  push    r12
0x10071fba6  push    r13
0x10071fba8  push    r14
0x10071fbaa  push    r15
0x10071fbac  lea     rbp, [rsp-0C0h]
0x10071fbb4  sub     rsp, 1C0h
0x10071fbbb  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x10071fbc3  mov     [rsp+1F0h+arg_10], rbx
0x10071fbcb  mov     rax, cs:__security_cookie
0x10071fbd2  xor     rax, rsp
0x10071fbd5  mov     [rbp+0F0h+var_40], rax
0x10071fbdc  mov     r15, rdx
0x10071fbdf  mov     r13, rcx
0x10071fbe2  mov     rbx, [rcx+20h]
0x10071fbe6  cmp     dword ptr [rbx+8], 0
0x10071fbea  jle     short loc_10071FC0D
0x10071fbec  cmp     byte ptr [rdx+20h], 3
0x10071fbf0  jnz     short loc_10071FBFC
0x10071fbf2  mov     [rsp+1F0h+var_18C], 0FFFFFFFFh
0x10071fbfa  jmp     short loc_10071FC03
0x10071fbfc  mov     ecx, [rdx+28h]
0x10071fbff  mov     [rsp+1F0h+var_18C], ecx
0x10071fc03  jnz     short loc_10071FC15
0x10071fc05  mov     byte ptr [rdx], 3
0x10071fc08  jmp     loc_100720090
0x10071fc0d  movzx   eax, byte ptr [rbx+0Eh]
0x10071fc11  mov     [rsp+1F0h+var_18C], eax
0x10071fc15  movzx   esi, byte ptr [rbx+10h]
0x10071fc19  mov     rax, [r13+48h]
0x10071fc1d  test    rax, rax
0x10071fc20  jz      short loc_10071FC3D
0x10071fc22  mov     rax, [rax+198h]
0x10071fc29  test    rax, rax
0x10071fc2c  jz      short loc_10071FC3D
0x10071fc2e  cmp     qword ptr [rax+1A8h], 0
0x10071fc36  jz      short loc_10071FC3D
0x10071fc38  mov     dil, 1
0x10071fc3b  jmp     short loc_10071FC40
0x10071fc3d  xor     dil, dil
0x10071fc40  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071fc46  test    byte ptr [rax+39h], 10h
0x10071fc4a  jnz     short loc_10071FC69
0x10071fc4c  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071fc52  test    rax, rax
0x10071fc55  jz      short loc_10071FCC2
0x10071fc57  mov     edx, 1CCh
0x10071fc5c  mov     rcx, rax
0x10071fc5f  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071fc65  test    eax, eax
0x10071fc67  jz      short loc_10071FCC2
0x10071fc69  cmp     sil, 1
0x10071fc6d  jnz     short loc_10071FCC2
0x10071fc6f  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071fc75  test    byte ptr [rax+39h], 8
0x10071fc79  jnz     short loc_10071FC9D
0x10071fc7b  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071fc81  test    rax, rax
0x10071fc84  jz      short loc_10071FC98
0x10071fc86  mov     edx, 1CBh
0x10071fc8b  mov     rcx, rax
0x10071fc8e  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071fc94  test    eax, eax
0x10071fc96  jnz     short loc_10071FC9D
0x10071fc98  test    dil, dil
0x10071fc9b  jnz     short loc_10071FCC2
0x10071fc9d  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071fca3  test    byte ptr [rax+39h], 8
0x10071fca7  jnz     short loc_10071FCC2
0x10071fca9  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071fcaf  test    rax, rax
0x10071fcb2  jz      short loc_10071FCC2
0x10071fcb4  mov     edx, 1CBh
0x10071fcb9  mov     rcx, rax
0x10071fcbc  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071fcc2  movzx   eax, byte ptr [rbx+0Fh]
0x10071fcc6  mov     [rsp+1F0h+var_190], eax
0x10071fcca  mov     rax, [r13+20h]
0x10071fcce  movzx   edx, word ptr [rax+12h]
0x10071fcd2  mov     rax, [r13+38h]
0x10071fcd6  mov     r12, [rax+rdx*8]
0x10071fcda  mov     rax, [r13+10h]
0x10071fcde  mov     rcx, [rax+20h]
0x10071fce2  movzx   esi, word ptr [rcx+rdx*2]
0x10071fce6  xor     r14d, r14d
0x10071fce9  cmp     [r15], r14b
0x10071fcec  jz      short loc_10071FCFE
0x10071fcee  mov     [r15+8], r12
0x10071fcf2  mov     [r15+10h], rsi
0x10071fcf6  mov     r12d, r14d
0x10071fcf9  jmp     loc_10071FDBD
0x10071fcfe  mov     dword ptr [rsp+1F0h+var_188], 0E703h
0x10071fd06  xorps   xmm0, xmm0
0x10071fd09  movdqu  [rsp+1F0h+var_188+8], xmm0
0x10071fd0f  mov     [rbp+0F0h+var_170], r14d
0x10071fd13  mov     r8d, esi; int
0x10071fd16  mov     dl, 0E7h; unsigned __int8
0x10071fd18  lea     rcx, [rbp+0F0h+var_148]; this
0x10071fd1c  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x10071fd21  movzx   edx, [rbp+0F0h+var_148]
0x10071fd25  cmp     dl, 62h ; 'b'
0x10071fd28  jnz     short loc_10071FD33
0x10071fd2a  mov     eax, 2
0x10071fd2f  mov     [rbp+0F0h+var_138], ax
0x10071fd33  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10071fd3a  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x10071fd42  cmp     [rax+rcx+45AFC0h], r14b
0x10071fd4a  jnz     short loc_10071FD54
0x10071fd4c  sub     dl, 23h ; '#'
0x10071fd4f  test    dl, 0BFh
0x10071fd52  jnz     short loc_10071FD6D
0x10071fd54  lea     rcx, [rbp+0F0h+var_148]; this
0x10071fd58  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x10071fd5d  mov     ecx, [rbp+0F0h+var_134]
0x10071fd60  mov     edx, 0FFFFFFFFh
0x10071fd65  test    al, al
0x10071fd67  cmovnz  ecx, edx
0x10071fd6a  mov     [rbp+0F0h+var_134], ecx
0x10071fd6d  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x10071fd72  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x10071fd76  mov     r8d, esi; unsigned int
0x10071fd79  mov     rdx, r12; unsigned __int8 *
0x10071fd7c  lea     rcx, [rsp+1F0h+var_188]; this
0x10071fd81  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x10071fd86  lea     rdx, [r15+8]
0x10071fd8a  mov     r8d, [rsp+1F0h+var_190]
0x10071fd8f  lea     rcx, [rsp+1F0h+var_188]
0x10071fd94  call    ?WstrConvertFromGuid@CXVariant@@QEAAJPEBUCSsGuid@@W4EPadding@@@Z; CXVariant::WstrConvertFromGuid(CSsGuid const *,EPadding)
0x10071fd99  mov     r12d, eax
0x10071fd9c  test    eax, eax
0x10071fd9e  jnz     short loc_10071FDBD
0x10071fda0  movups  xmm0, [rsp+1F0h+var_188]
0x10071fda5  movups  xmmword ptr [r15], xmm0
0x10071fda9  movups  xmm1, xmmword ptr [rsp+78h]
0x10071fdae  movups  xmmword ptr [r15+10h], xmm1
0x10071fdb3  mov     eax, 0FFFEh
0x10071fdb8  and     [r15+2], ax
0x10071fdbd  cmp     byte ptr [rbx+10h], 1
0x10071fdc1  jnz     loc_10071FF9B
0x10071fdc7  movzx   eax, word ptr [r15+2]
0x10071fdcc  shr     ax, 0Ch
0x10071fdd0  test    al, 1
0x10071fdd2  jz      loc_10071FF9B
0x10071fdd8  mov     eax, r14d
0x10071fddb  mov     [rsp+1F0h+var_190], eax
0x10071fddf  test    dil, dil
0x10071fde2  jz      loc_10071FF60
0x10071fde8  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071fdef  mov     rax, [rcx]
0x10071fdf2  lea     rdx, [rbp+0F0h+var_168]
0x10071fdf6  call    qword ptr [rax]
0x10071fdf8  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071fdff  mov     rax, [rcx]
0x10071fe02  mov     rdx, [rbp+0F0h+var_168]
0x10071fe06  call    qword ptr [rax+8]
0x10071fe09  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x10071fe10  mov     rax, [rcx]
0x10071fe13  call    qword ptr [rax]
0x10071fe15  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x10071fe1c  mov     r8, [rcx]
0x10071fe1f  movzx   edx, ax
0x10071fe22  call    qword ptr [r8+8]
0x10071fe26  mov     rsi, rax
0x10071fe29  mov     r9, [r13+20h]
0x10071fe2d  movzx   ebx, word ptr [r9+18h]
0x10071fe32  shl     rbx, 5
0x10071fe36  mov     rcx, [r13+10h]
0x10071fe3a  add     rbx, [rcx+0A8h]
0x10071fe41  mov     r8, gs:58h
0x10071fe4a  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10071fe51  mov     edx, [rcx]
0x10071fe53  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10071fe5a  mov     edi, [rcx]
0x10071fe5c  add     rdi, [r8+rdx*8]
0x10071fe60  mov     rdx, [rdi+100h]
0x10071fe67  test    rdx, rdx
0x10071fe6a  jnz     short loc_10071FE7F
0x10071fe6c  xor     ecx, ecx
0x10071fe6e  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10071fe74  mov     rdx, [rdi+100h]
0x10071fe7b  mov     r9, [r13+20h]
0x10071fe7f  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x10071fe86  mov     ecx, [r9+0Ch]
0x10071fe8a  mov     rax, [r13+30h]
0x10071fe8e  mov     [rsp+1F0h+var_198], r14d; int
0x10071fe93  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x10071fe98  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x10071fe9d  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x10071fea2  mov     [rsp+1F0h+Src], r14; Src
0x10071fea7  mov     [rsp+1F0h+var_1C0], 2; int
0x10071feaf  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x10071feb4  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x10071feb9  mov     r9, rdx; struct IMemObj *
0x10071febc  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x10071fec1  mov     rcx, [rax+rcx*8]; this
0x10071fec5  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x10071feca  mov     rdi, rax
0x10071fecd  mov     [rbp+0F0h+var_120], rax
0x10071fed1  test    rax, rax
0x10071fed4  jnz     short loc_10071FEDB
0x10071fed6  mov     eax, r14d
0x10071fed9  jmp     short loc_10071FEE9
0x10071fedb  mov     eax, [rsp+1F0h+var_190]
0x10071fedf  mov     ecx, 64h ; 'd'
0x10071fee4  cmp     eax, ecx
0x10071fee6  cmovnb  eax, ecx
0x10071fee9  mov     [rsp+1F0h+var_190], eax
0x10071feed  mov     ebx, eax
0x10071feef  add     rbx, rbx
0x10071fef2  jz      short loc_10071FF53
0x10071fef4  test    rdi, rdi
0x10071fef7  jz      short loc_10071FF13
0x10071fef9  cmp     rbx, 0C8h
0x10071ff00  ja      short loc_10071FF13
0x10071ff02  mov     r8, rbx; Size
0x10071ff05  mov     rdx, rdi; Src
0x10071ff08  lea     rcx, [rbp+0F0h+var_110]; void *
0x10071ff0c  call    memmove
0x10071ff11  jmp     short loc_10071FF53
0x10071ff13  xor     edx, edx; Val
0x10071ff15  mov     r8d, 0C8h; Size
0x10071ff1b  lea     rcx, [rbp+0F0h+var_110]; void *
0x10071ff1f  call    memset_0
0x10071ff24  test    rdi, rdi
0x10071ff27  jnz     short loc_10071FF37
0x10071ff29  call    cs:__imp__errno
0x10071ff2f  mov     dword ptr [rax], 16h
0x10071ff35  jmp     short loc_10071FF4C
0x10071ff37  cmp     rbx, 0C8h
0x10071ff3e  jbe     short loc_10071FF53
0x10071ff40  call    cs:__imp__errno
0x10071ff46  mov     dword ptr [rax], 22h ; '"'
0x10071ff4c  call    cs:__imp__invalid_parameter_noinfo
0x10071ff52  nop
0x10071ff53  mov     rcx, rdi
0x10071ff56  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10071ff5c  mov     eax, [rsp+1F0h+var_190]
0x10071ff60  add     rax, rax
0x10071ff63  lea     rcx, [rbp+0F0h+var_110]
0x10071ff67  mov     [rsp+1F0h+var_1A8], rcx
0x10071ff6c  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x10071ff71  mov     [rsp+1F0h+Src], r14
0x10071ff76  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x10071ff7b  mov     [rsp+1F0h+var_1C8], r14
0x10071ff80  mov     [rsp+1F0h+var_1D0], r14
0x10071ff85  mov     edx, 1Ch
0x10071ff8a  lea     ecx, [rdx-2]
0x10071ff8d  lea     r9d, [rdx-1Ah]
0x10071ff91  lea     r8d, [rdx-0Ch]
0x10071ff95  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10071ff9b  test    r12d, r12d
0x10071ff9e  jz      loc_100720090
0x10071ffa4  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071ffab  mov     rax, [rcx]
0x10071ffae  lea     rdx, [rbp+0F0h+var_160]
0x10071ffb2  call    qword ptr [rax]
0x10071ffb4  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071ffbb  mov     rax, [rcx]
0x10071ffbe  mov     rdx, [rbp+0F0h+var_160]
0x10071ffc2  call    qword ptr [rax+8]
0x10071ffc5  mov     edx, 800h; unsigned int
0x10071ffca  mov     rcx, rax; this
0x10071ffcd  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10071ffd2  mov     ebx, eax
0x10071ffd4  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071ffdb  mov     r8, [rcx]
0x10071ffde  lea     rdx, [rbp+0F0h+var_158]
0x10071ffe2  call    qword ptr [r8]
0x10071ffe5  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071ffec  mov     r8, [rcx]
0x10071ffef  mov     rdx, [rbp+0F0h+var_158]
0x10071fff3  call    qword ptr [r8+8]
0x10071fff7  mov     edx, 10000000h; unsigned int
0x10071fffc  mov     rcx, rax; this
0x10071ffff  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100720004  mov     edi, eax
0x100720006  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10072000d  mov     r8, [rcx]
0x100720010  lea     rdx, [rbp+0F0h+var_150]
0x100720014  call    qword ptr [r8]
0x100720017  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10072001e  mov     r8, [rcx]
0x100720021  mov     rdx, [rbp+0F0h+var_150]
0x100720025  call    qword ptr [r8+8]
0x100720029  mov     esi, r14d
0x10072002c  test    ebx, ebx
0x10072002e  setnz   sil
0x100720032  mov     ebx, r14d
0x100720035  test    edi, edi
0x100720037  setnz   bl
0x10072003a  mov     edx, 1000h; unsigned int
0x10072003f  mov     rcx, rax; this
0x100720042  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100720047  mov     r9d, r14d
0x10072004a  test    eax, eax
0x10072004c  setnz   r9b
0x100720050  mov     rax, [r13+20h]
0x100720054  movzx   r8d, byte ptr [rax+11h]
  ... truncated ...
```
