# CTEsConvertToWstr<56,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x100705bf0`
- end: `0x10070610a`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0DI@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1306`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1006ff260`

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
- `0x100705bf0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100705fa6`
- `sqldk!??_V@YAXPEAX@Z` at `0x100705fa6`
- `sqldk!SystemThread_TlsIndex` at `0x100705e9a`
- `sqldk!SystemThread_TlsOffset` at `0x100705ea3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100705ebe`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100705ebe`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100705fe5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x100705fe5`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100705c90`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100705cbf`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100705ced`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100705c90`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100705cbf`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100705ced`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100705c9c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100705ccb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100705cf9`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100705c9c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100705ccb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x100705cf9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100705caf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100705cde`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100705d0c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100705caf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100705cde`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100705d0c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100705f79`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100705f90`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100705f79`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100705f90`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100705f9c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x100705f9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<56,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
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
    v16 = CXVariant::WstrConvertFromI8(&v37, *(int *)(a2 + 8), v35);
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
      0x38u,
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
0x100705bf0  push    rbp
0x100705bf2  push    rsi
0x100705bf3  push    rdi
0x100705bf4  push    r12
0x100705bf6  push    r13
0x100705bf8  push    r14
0x100705bfa  push    r15
0x100705bfc  lea     rbp, [rsp-0C0h]
0x100705c04  sub     rsp, 1C0h
0x100705c0b  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x100705c13  mov     [rsp+1F0h+arg_10], rbx
0x100705c1b  mov     rax, cs:__security_cookie
0x100705c22  xor     rax, rsp
0x100705c25  mov     [rbp+0F0h+var_40], rax
0x100705c2c  mov     r15, rdx
0x100705c2f  mov     r13, rcx
0x100705c32  mov     rbx, [rcx+20h]
0x100705c36  cmp     dword ptr [rbx+8], 0
0x100705c3a  jle     short loc_100705C5D
0x100705c3c  cmp     byte ptr [rdx+20h], 3
0x100705c40  jnz     short loc_100705C4C
0x100705c42  mov     [rsp+1F0h+var_18C], 0FFFFFFFFh
0x100705c4a  jmp     short loc_100705C53
0x100705c4c  mov     ecx, [rdx+28h]
0x100705c4f  mov     [rsp+1F0h+var_18C], ecx
0x100705c53  jnz     short loc_100705C65
0x100705c55  mov     byte ptr [rdx], 3
0x100705c58  jmp     loc_1007060E0
0x100705c5d  movzx   eax, byte ptr [rbx+0Eh]
0x100705c61  mov     [rsp+1F0h+var_18C], eax
0x100705c65  movzx   esi, byte ptr [rbx+10h]
0x100705c69  mov     rax, [r13+48h]
0x100705c6d  test    rax, rax
0x100705c70  jz      short loc_100705C8D
0x100705c72  mov     rax, [rax+198h]
0x100705c79  test    rax, rax
0x100705c7c  jz      short loc_100705C8D
0x100705c7e  cmp     qword ptr [rax+1A8h], 0
0x100705c86  jz      short loc_100705C8D
0x100705c88  mov     dil, 1
0x100705c8b  jmp     short loc_100705C90
0x100705c8d  xor     dil, dil
0x100705c90  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100705c96  test    byte ptr [rax+39h], 10h
0x100705c9a  jnz     short loc_100705CB9
0x100705c9c  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100705ca2  test    rax, rax
0x100705ca5  jz      short loc_100705D12
0x100705ca7  mov     edx, 1CCh
0x100705cac  mov     rcx, rax
0x100705caf  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100705cb5  test    eax, eax
0x100705cb7  jz      short loc_100705D12
0x100705cb9  cmp     sil, 1
0x100705cbd  jnz     short loc_100705D12
0x100705cbf  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100705cc5  test    byte ptr [rax+39h], 8
0x100705cc9  jnz     short loc_100705CED
0x100705ccb  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100705cd1  test    rax, rax
0x100705cd4  jz      short loc_100705CE8
0x100705cd6  mov     edx, 1CBh
0x100705cdb  mov     rcx, rax
0x100705cde  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100705ce4  test    eax, eax
0x100705ce6  jnz     short loc_100705CED
0x100705ce8  test    dil, dil
0x100705ceb  jnz     short loc_100705D12
0x100705ced  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100705cf3  test    byte ptr [rax+39h], 8
0x100705cf7  jnz     short loc_100705D12
0x100705cf9  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100705cff  test    rax, rax
0x100705d02  jz      short loc_100705D12
0x100705d04  mov     edx, 1CBh
0x100705d09  mov     rcx, rax
0x100705d0c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100705d12  movzx   eax, byte ptr [rbx+0Fh]
0x100705d16  mov     [rsp+1F0h+var_190], eax
0x100705d1a  mov     rax, [r13+20h]
0x100705d1e  movzx   edx, word ptr [rax+12h]
0x100705d22  mov     rax, [r13+38h]
0x100705d26  mov     r12, [rax+rdx*8]
0x100705d2a  mov     rax, [r13+10h]
0x100705d2e  mov     rcx, [rax+20h]
0x100705d32  movzx   esi, word ptr [rcx+rdx*2]
0x100705d36  xor     r14d, r14d
0x100705d39  cmp     [r15], r14b
0x100705d3c  jz      short loc_100705D4E
0x100705d3e  mov     [r15+8], r12
0x100705d42  mov     [r15+10h], rsi
0x100705d46  mov     r12d, r14d
0x100705d49  jmp     loc_100705E0D
0x100705d4e  mov     dword ptr [rsp+1F0h+var_188], 0E703h
0x100705d56  xorps   xmm0, xmm0
0x100705d59  movdqu  [rsp+1F0h+var_188+8], xmm0
0x100705d5f  mov     [rbp+0F0h+var_170], r14d
0x100705d63  mov     r8d, esi; int
0x100705d66  mov     dl, 0E7h; unsigned __int8
0x100705d68  lea     rcx, [rbp+0F0h+var_148]; this
0x100705d6c  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x100705d71  movzx   edx, [rbp+0F0h+var_148]
0x100705d75  cmp     dl, 62h ; 'b'
0x100705d78  jnz     short loc_100705D83
0x100705d7a  mov     eax, 2
0x100705d7f  mov     [rbp+0F0h+var_138], ax
0x100705d83  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x100705d8a  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x100705d92  cmp     [rax+rcx+45AFC0h], r14b
0x100705d9a  jnz     short loc_100705DA4
0x100705d9c  sub     dl, 23h ; '#'
0x100705d9f  test    dl, 0BFh
0x100705da2  jnz     short loc_100705DBD
0x100705da4  lea     rcx, [rbp+0F0h+var_148]; this
0x100705da8  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x100705dad  mov     ecx, [rbp+0F0h+var_134]
0x100705db0  mov     edx, 0FFFFFFFFh
0x100705db5  test    al, al
0x100705db7  cmovnz  ecx, edx
0x100705dba  mov     [rbp+0F0h+var_134], ecx
0x100705dbd  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x100705dc2  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x100705dc6  mov     r8d, esi; unsigned int
0x100705dc9  mov     rdx, r12; unsigned __int8 *
0x100705dcc  lea     rcx, [rsp+1F0h+var_188]; this
0x100705dd1  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x100705dd6  movsxd  rdx, dword ptr [r15+8]
0x100705dda  mov     r8d, [rsp+1F0h+var_190]
0x100705ddf  lea     rcx, [rsp+1F0h+var_188]
0x100705de4  call    ?WstrConvertFromI8@CXVariant@@QEAAJ_JW4EPadding@@@Z; CXVariant::WstrConvertFromI8(__int64,EPadding)
0x100705de9  mov     r12d, eax
0x100705dec  test    eax, eax
0x100705dee  jnz     short loc_100705E0D
0x100705df0  movups  xmm0, [rsp+1F0h+var_188]
0x100705df5  movups  xmmword ptr [r15], xmm0
0x100705df9  movups  xmm1, xmmword ptr [rsp+78h]
0x100705dfe  movups  xmmword ptr [r15+10h], xmm1
0x100705e03  mov     eax, 0FFFEh
0x100705e08  and     [r15+2], ax
0x100705e0d  cmp     byte ptr [rbx+10h], 1
0x100705e11  jnz     loc_100705FEB
0x100705e17  movzx   eax, word ptr [r15+2]
0x100705e1c  shr     ax, 0Ch
0x100705e20  test    al, 1
0x100705e22  jz      loc_100705FEB
0x100705e28  mov     eax, r14d
0x100705e2b  mov     [rsp+1F0h+var_190], eax
0x100705e2f  test    dil, dil
0x100705e32  jz      loc_100705FB0
0x100705e38  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100705e3f  mov     rax, [rcx]
0x100705e42  lea     rdx, [rbp+0F0h+var_168]
0x100705e46  call    qword ptr [rax]
0x100705e48  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100705e4f  mov     rax, [rcx]
0x100705e52  mov     rdx, [rbp+0F0h+var_168]
0x100705e56  call    qword ptr [rax+8]
0x100705e59  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x100705e60  mov     rax, [rcx]
0x100705e63  call    qword ptr [rax]
0x100705e65  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x100705e6c  mov     r8, [rcx]
0x100705e6f  movzx   edx, ax
0x100705e72  call    qword ptr [r8+8]
0x100705e76  mov     rsi, rax
0x100705e79  mov     r9, [r13+20h]
0x100705e7d  movzx   ebx, word ptr [r9+18h]
0x100705e82  shl     rbx, 5
0x100705e86  mov     rcx, [r13+10h]
0x100705e8a  add     rbx, [rcx+0A8h]
0x100705e91  mov     r8, gs:58h
0x100705e9a  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100705ea1  mov     edx, [rcx]
0x100705ea3  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x100705eaa  mov     edi, [rcx]
0x100705eac  add     rdi, [r8+rdx*8]
0x100705eb0  mov     rdx, [rdi+100h]
0x100705eb7  test    rdx, rdx
0x100705eba  jnz     short loc_100705ECF
0x100705ebc  xor     ecx, ecx
0x100705ebe  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100705ec4  mov     rdx, [rdi+100h]
0x100705ecb  mov     r9, [r13+20h]
0x100705ecf  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x100705ed6  mov     ecx, [r9+0Ch]
0x100705eda  mov     rax, [r13+30h]
0x100705ede  mov     [rsp+1F0h+var_198], r14d; int
0x100705ee3  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x100705ee8  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x100705eed  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x100705ef2  mov     [rsp+1F0h+Src], r14; Src
0x100705ef7  mov     [rsp+1F0h+var_1C0], 2; int
0x100705eff  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x100705f04  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x100705f09  mov     r9, rdx; struct IMemObj *
0x100705f0c  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x100705f11  mov     rcx, [rax+rcx*8]; this
0x100705f15  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x100705f1a  mov     rdi, rax
0x100705f1d  mov     [rbp+0F0h+var_120], rax
0x100705f21  test    rax, rax
0x100705f24  jnz     short loc_100705F2B
0x100705f26  mov     eax, r14d
0x100705f29  jmp     short loc_100705F39
0x100705f2b  mov     eax, [rsp+1F0h+var_190]
0x100705f2f  mov     ecx, 64h ; 'd'
0x100705f34  cmp     eax, ecx
0x100705f36  cmovnb  eax, ecx
0x100705f39  mov     [rsp+1F0h+var_190], eax
0x100705f3d  mov     ebx, eax
0x100705f3f  add     rbx, rbx
0x100705f42  jz      short loc_100705FA3
0x100705f44  test    rdi, rdi
0x100705f47  jz      short loc_100705F63
0x100705f49  cmp     rbx, 0C8h
0x100705f50  ja      short loc_100705F63
0x100705f52  mov     r8, rbx; Size
0x100705f55  mov     rdx, rdi; Src
0x100705f58  lea     rcx, [rbp+0F0h+var_110]; void *
0x100705f5c  call    memmove
0x100705f61  jmp     short loc_100705FA3
0x100705f63  xor     edx, edx; Val
0x100705f65  mov     r8d, 0C8h; Size
0x100705f6b  lea     rcx, [rbp+0F0h+var_110]; void *
0x100705f6f  call    memset_0
0x100705f74  test    rdi, rdi
0x100705f77  jnz     short loc_100705F87
0x100705f79  call    cs:__imp__errno
0x100705f7f  mov     dword ptr [rax], 16h
0x100705f85  jmp     short loc_100705F9C
0x100705f87  cmp     rbx, 0C8h
0x100705f8e  jbe     short loc_100705FA3
0x100705f90  call    cs:__imp__errno
0x100705f96  mov     dword ptr [rax], 22h ; '"'
0x100705f9c  call    cs:__imp__invalid_parameter_noinfo
0x100705fa2  nop
0x100705fa3  mov     rcx, rdi
0x100705fa6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100705fac  mov     eax, [rsp+1F0h+var_190]
0x100705fb0  add     rax, rax
0x100705fb3  lea     rcx, [rbp+0F0h+var_110]
0x100705fb7  mov     [rsp+1F0h+var_1A8], rcx
0x100705fbc  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x100705fc1  mov     [rsp+1F0h+Src], r14
0x100705fc6  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x100705fcb  mov     [rsp+1F0h+var_1C8], r14
0x100705fd0  mov     [rsp+1F0h+var_1D0], r14
0x100705fd5  mov     edx, 1Ch
0x100705fda  lea     ecx, [rdx-2]
0x100705fdd  lea     r9d, [rdx-1Ah]
0x100705fe1  lea     r8d, [rdx-0Ch]
0x100705fe5  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x100705feb  test    r12d, r12d
0x100705fee  jz      loc_1007060E0
0x100705ff4  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100705ffb  mov     rax, [rcx]
0x100705ffe  lea     rdx, [rbp+0F0h+var_160]
0x100706002  call    qword ptr [rax]
0x100706004  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070600b  mov     rax, [rcx]
0x10070600e  mov     rdx, [rbp+0F0h+var_160]
0x100706012  call    qword ptr [rax+8]
0x100706015  mov     edx, 800h; unsigned int
0x10070601a  mov     rcx, rax; this
0x10070601d  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100706022  mov     ebx, eax
0x100706024  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070602b  mov     r8, [rcx]
0x10070602e  lea     rdx, [rbp+0F0h+var_158]
0x100706032  call    qword ptr [r8]
0x100706035  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070603c  mov     r8, [rcx]
0x10070603f  mov     rdx, [rbp+0F0h+var_158]
0x100706043  call    qword ptr [r8+8]
0x100706047  mov     edx, 10000000h; unsigned int
0x10070604c  mov     rcx, rax; this
0x10070604f  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100706054  mov     edi, eax
0x100706056  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070605d  mov     r8, [rcx]
0x100706060  lea     rdx, [rbp+0F0h+var_150]
0x100706064  call    qword ptr [r8]
0x100706067  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070606e  mov     r8, [rcx]
0x100706071  mov     rdx, [rbp+0F0h+var_150]
0x100706075  call    qword ptr [r8+8]
0x100706079  mov     esi, r14d
0x10070607c  test    ebx, ebx
0x10070607e  setnz   sil
0x100706082  mov     ebx, r14d
0x100706085  test    edi, edi
0x100706087  setnz   bl
0x10070608a  mov     edx, 1000h; unsigned int
0x10070608f  mov     rcx, rax; this
0x100706092  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100706097  mov     r9d, r14d
0x10070609a  test    eax, eax
0x10070609c  setnz   r9b
0x1007060a0  mov     rax, [r13+20h]
0x1007060a4  movzx   r8d, byte ptr [rax+11h]
  ... truncated ...
```
