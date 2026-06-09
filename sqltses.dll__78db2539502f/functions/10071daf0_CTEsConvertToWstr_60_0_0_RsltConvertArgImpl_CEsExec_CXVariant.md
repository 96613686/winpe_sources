# CTEsConvertToWstr<60,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x10071daf0`
- end: `0x10071e015`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0DM@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1317`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x100700c80`

## callees

- `0x100401170`
- `0x1004011fc`
- `0x100401450`
- `0x100401cc0`
- `0x100403380`
- `0x100403530`
- `0x100408f40`
- `0x100410bc0`
- `0x10041d440`
- `0x10047a590`
- `0x10071daf0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x10071deb1`
- `sqldk!??_V@YAXPEAX@Z` at `0x10071deb1`
- `sqldk!SystemThread_TlsIndex` at `0x10071dda5`
- `sqldk!SystemThread_TlsOffset` at `0x10071ddae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10071ddc9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10071ddc9`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10071def0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10071def0`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071db90`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071dbbf`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071dbed`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071db90`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071dbbf`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x10071dbed`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071db9c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071dbcb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071dbf9`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071db9c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071dbcb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10071dbf9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071dbaf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071dbde`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071dc0c`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071dbaf`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071dbde`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10071dc0c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071de84`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071de9b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071de84`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10071de9b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10071dea7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10071dea7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<60,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
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
    v6 = *(unsigned __int8 *)(v4 + 14);
    v37 = v6;
  }
  else
  {
    v5 = *(_BYTE *)(a2 + 32) == 3;
    v6 = -1;
    if ( *(_BYTE *)(a2 + 32) != 3 )
      v6 = *(_DWORD *)(a2 + 40);
    v37 = v6;
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
  v36 = *(unsigned __int8 *)(v4 + 15);
  v14 = *(unsigned __int16 *)(a1[4] + 18LL);
  v15 = *(unsigned __int8 **)(a1[7] + 8 * v14);
  v38 = v15;
  v16 = *(unsigned __int16 *)(*(_QWORD *)(a1[2] + 32LL) + 2 * v14);
  if ( *(_BYTE *)a2 )
  {
    *(_QWORD *)(a2 + 8) = v15;
    *(_QWORD *)(a2 + 16) = v16;
    v17 = 0;
  }
  else
  {
    v39.m256i_i32[0] = 59139;
    memset(&v39.m256i_u64[1], 0, 20);
    CTypeInfo::InitWithMaxLen((CTypeInfo *)v43, 0xE7u, v16);
    if ( v43[0] == 98 )
      v44 = 2;
    if ( *((_BYTE *)&CTypeInfo::sxm_rgfIsStringOrWString + *((unsigned __int8 *)&xsm_rgOrdFromXvt + v43[0]))
      || ((v43[0] - 35) & 0xBF) == 0 )
    {
      v18 = CTypeInfo::FCharacterOrEncryptedCharacter((CTypeInfo *)v43);
      v19 = v45;
      if ( v18 )
        v19 = -1;
      v45 = v19;
    }
    CXVariant::CopyFromPbInternal((CXVariant *)&v39, v38, v16, (const struct CTypeInfo *)v43, 0);
    v17 = CSsMoney8::ConvertToWstr(a2 + 8, &v39, v6, v36);
    if ( !v17 )
    {
      *(__m256i *)a2 = v39;
      *(_WORD *)(a2 + 2) &= ~1u;
    }
  }
  if ( *(_BYTE *)(v4 + 16) == 1 && (*(_WORD *)(a2 + 2) & 0x1000) != 0 )
  {
    v20 = 0;
    v36 = 0;
    if ( !v10 )
    {
LABEL_53:
      ex_raise(26, 28, 16, 2, 0, 0, 0, 0, 2 * v20, v48);
      goto LABEL_54;
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
      memmove(v48, v27, 2LL * v28);
    }
LABEL_52:
    operator delete[](v27);
    v20 = v36;
    goto LABEL_53;
  }
LABEL_54:
  if ( v17 )
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
      v17,
      (struct CXVariant *)a2,
      0xE7u,
      0x3Cu,
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
0x10071daf0  push    rbp
0x10071daf2  push    rsi
0x10071daf3  push    rdi
0x10071daf4  push    r12
0x10071daf6  push    r13
0x10071daf8  push    r14
0x10071dafa  push    r15
0x10071dafc  lea     rbp, [rsp-0C0h]
0x10071db04  sub     rsp, 1C0h
0x10071db0b  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x10071db13  mov     [rsp+1F0h+arg_10], rbx
0x10071db1b  mov     rax, cs:__security_cookie
0x10071db22  xor     rax, rsp
0x10071db25  mov     [rbp+0F0h+var_40], rax
0x10071db2c  mov     r15, rdx
0x10071db2f  mov     r13, rcx
0x10071db32  mov     rbx, [rcx+20h]
0x10071db36  cmp     dword ptr [rbx+8], 0
0x10071db3a  jle     short loc_10071DB5B
0x10071db3c  cmp     byte ptr [rdx+20h], 3
0x10071db40  mov     r12d, 0FFFFFFFFh
0x10071db46  jz      short loc_10071DB4C
0x10071db48  mov     r12d, [rdx+28h]
0x10071db4c  mov     [rsp+1F0h+var_18C], r12d
0x10071db51  jnz     short loc_10071DB65
0x10071db53  mov     byte ptr [rdx], 3
0x10071db56  jmp     loc_10071DFEB
0x10071db5b  movzx   r12d, byte ptr [rbx+0Eh]
0x10071db60  mov     [rsp+1F0h+var_18C], r12d
0x10071db65  movzx   esi, byte ptr [rbx+10h]
0x10071db69  mov     rax, [rcx+48h]
0x10071db6d  test    rax, rax
0x10071db70  jz      short loc_10071DB8D
0x10071db72  mov     rax, [rax+198h]
0x10071db79  test    rax, rax
0x10071db7c  jz      short loc_10071DB8D
0x10071db7e  cmp     qword ptr [rax+1A8h], 0
0x10071db86  jz      short loc_10071DB8D
0x10071db88  mov     dil, 1
0x10071db8b  jmp     short loc_10071DB90
0x10071db8d  xor     dil, dil
0x10071db90  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071db96  test    byte ptr [rax+39h], 10h
0x10071db9a  jnz     short loc_10071DBB9
0x10071db9c  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071dba2  test    rax, rax
0x10071dba5  jz      short loc_10071DC12
0x10071dba7  mov     edx, 1CCh
0x10071dbac  mov     rcx, rax
0x10071dbaf  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071dbb5  test    eax, eax
0x10071dbb7  jz      short loc_10071DC12
0x10071dbb9  cmp     sil, 1
0x10071dbbd  jnz     short loc_10071DC12
0x10071dbbf  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071dbc5  test    byte ptr [rax+39h], 8
0x10071dbc9  jnz     short loc_10071DBED
0x10071dbcb  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071dbd1  test    rax, rax
0x10071dbd4  jz      short loc_10071DBE8
0x10071dbd6  mov     edx, 1CBh
0x10071dbdb  mov     rcx, rax
0x10071dbde  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071dbe4  test    eax, eax
0x10071dbe6  jnz     short loc_10071DBED
0x10071dbe8  test    dil, dil
0x10071dbeb  jnz     short loc_10071DC12
0x10071dbed  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x10071dbf3  test    byte ptr [rax+39h], 8
0x10071dbf7  jnz     short loc_10071DC12
0x10071dbf9  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x10071dbff  test    rax, rax
0x10071dc02  jz      short loc_10071DC12
0x10071dc04  mov     edx, 1CBh
0x10071dc09  mov     rcx, rax
0x10071dc0c  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10071dc12  movzx   eax, byte ptr [rbx+0Fh]
0x10071dc16  mov     [rsp+1F0h+var_190], eax
0x10071dc1a  mov     rax, [r13+20h]
0x10071dc1e  movzx   edx, word ptr [rax+12h]
0x10071dc22  mov     rax, [r13+38h]
0x10071dc26  mov     r8, [rax+rdx*8]
0x10071dc2a  mov     [rsp+1F0h+var_188], r8
0x10071dc2f  mov     rax, [r13+10h]
0x10071dc33  mov     rcx, [rax+20h]
0x10071dc37  movzx   esi, word ptr [rcx+rdx*2]
0x10071dc3b  xor     r14d, r14d
0x10071dc3e  cmp     [r15], r14b
0x10071dc41  jz      short loc_10071DC53
0x10071dc43  mov     [r15+8], r8
0x10071dc47  mov     [r15+10h], rsi
0x10071dc4b  mov     r12d, r14d
0x10071dc4e  jmp     loc_10071DD16
0x10071dc53  mov     dword ptr [rsp+1F0h+var_180], 0E703h
0x10071dc5b  xorps   xmm0, xmm0
0x10071dc5e  movdqu  [rsp+1F0h+var_180+8], xmm0
0x10071dc64  mov     [rbp+0F0h+var_168], r14d
0x10071dc68  mov     r8d, esi; int
0x10071dc6b  mov     dl, 0E7h; unsigned __int8
0x10071dc6d  lea     rcx, [rbp+0F0h+var_148]; this
0x10071dc71  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x10071dc76  movzx   edx, [rbp+0F0h+var_148]
0x10071dc7a  cmp     dl, 62h ; 'b'
0x10071dc7d  jnz     short loc_10071DC88
0x10071dc7f  mov     eax, 2
0x10071dc84  mov     [rbp+0F0h+var_138], ax
0x10071dc88  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10071dc8f  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x10071dc97  cmp     [rax+rcx+45AFC0h], r14b
0x10071dc9f  jnz     short loc_10071DCA9
0x10071dca1  sub     dl, 23h ; '#'
0x10071dca4  test    dl, 0BFh
0x10071dca7  jnz     short loc_10071DCC2
0x10071dca9  lea     rcx, [rbp+0F0h+var_148]; this
0x10071dcad  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x10071dcb2  mov     ecx, [rbp+0F0h+var_134]
0x10071dcb5  mov     edx, 0FFFFFFFFh
0x10071dcba  test    al, al
0x10071dcbc  cmovnz  ecx, edx
0x10071dcbf  mov     [rbp+0F0h+var_134], ecx
0x10071dcc2  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x10071dcc7  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x10071dccb  mov     r8d, esi; unsigned int
0x10071dcce  mov     rdx, [rsp+1F0h+var_188]; unsigned __int8 *
0x10071dcd3  lea     rcx, [rsp+1F0h+var_180]; this
0x10071dcd8  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x10071dcdd  lea     rcx, [r15+8]
0x10071dce1  mov     r9d, [rsp+1F0h+var_190]
0x10071dce6  mov     r8d, r12d
0x10071dce9  lea     rdx, [rsp+1F0h+var_180]
0x10071dcee  call    ?ConvertToWstr@CSsMoney8@@QEBAJPEAVCXVariant@@JW4EPadding@@@Z; CSsMoney8::ConvertToWstr(CXVariant *,long,EPadding)
0x10071dcf3  mov     r12d, eax
0x10071dcf6  test    eax, eax
0x10071dcf8  jnz     short loc_10071DD16
0x10071dcfa  movups  xmm0, [rsp+1F0h+var_180]
0x10071dcff  movups  xmmword ptr [r15], xmm0
0x10071dd03  movups  xmm1, xmmword ptr [rbp-80h]
0x10071dd07  movups  xmmword ptr [r15+10h], xmm1
0x10071dd0c  mov     eax, 0FFFEh
0x10071dd11  and     [r15+2], ax
0x10071dd16  cmp     byte ptr [rbx+10h], 1
0x10071dd1a  jnz     loc_10071DEF6
0x10071dd20  movzx   eax, word ptr [r15+2]
0x10071dd25  shr     ax, 0Ch
0x10071dd29  test    al, 1
0x10071dd2b  jz      loc_10071DEF6
0x10071dd31  mov     eax, r14d
0x10071dd34  mov     [rsp+1F0h+var_190], eax
0x10071dd38  test    dil, dil
0x10071dd3b  jz      loc_10071DEBB
0x10071dd41  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071dd48  mov     rax, [rcx]
0x10071dd4b  lea     rdx, [rsp+1F0h+var_188]
0x10071dd50  call    qword ptr [rax]
0x10071dd52  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071dd59  mov     rax, [rcx]
0x10071dd5c  mov     rdx, [rsp+1F0h+var_188]
0x10071dd61  call    qword ptr [rax+8]
0x10071dd64  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x10071dd6b  mov     rax, [rcx]
0x10071dd6e  call    qword ptr [rax]
0x10071dd70  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x10071dd77  mov     r8, [rcx]
0x10071dd7a  movzx   edx, ax
0x10071dd7d  call    qword ptr [r8+8]
0x10071dd81  mov     rsi, rax
0x10071dd84  mov     r9, [r13+20h]
0x10071dd88  movzx   ebx, word ptr [r9+18h]
0x10071dd8d  shl     rbx, 5
0x10071dd91  mov     rcx, [r13+10h]
0x10071dd95  add     rbx, [rcx+0A8h]
0x10071dd9c  mov     r8, gs:58h
0x10071dda5  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x10071ddac  mov     edx, [rcx]
0x10071ddae  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10071ddb5  mov     edi, [rcx]
0x10071ddb7  add     rdi, [r8+rdx*8]
0x10071ddbb  mov     rdx, [rdi+100h]
0x10071ddc2  test    rdx, rdx
0x10071ddc5  jnz     short loc_10071DDDA
0x10071ddc7  xor     ecx, ecx
0x10071ddc9  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10071ddcf  mov     rdx, [rdi+100h]
0x10071ddd6  mov     r9, [r13+20h]
0x10071ddda  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x10071dde1  mov     ecx, [r9+0Ch]
0x10071dde5  mov     rax, [r13+30h]
0x10071dde9  mov     [rsp+1F0h+var_198], r14d; int
0x10071ddee  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x10071ddf3  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x10071ddf8  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x10071ddfd  mov     [rsp+1F0h+Src], r14; Src
0x10071de02  mov     [rsp+1F0h+var_1C0], 2; int
0x10071de0a  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x10071de0f  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x10071de14  mov     r9, rdx; struct IMemObj *
0x10071de17  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x10071de1c  mov     rcx, [rax+rcx*8]; this
0x10071de20  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x10071de25  mov     rdi, rax
0x10071de28  mov     [rbp+0F0h+var_120], rax
0x10071de2c  test    rax, rax
0x10071de2f  jnz     short loc_10071DE36
0x10071de31  mov     eax, r14d
0x10071de34  jmp     short loc_10071DE44
0x10071de36  mov     eax, [rsp+1F0h+var_190]
0x10071de3a  mov     ecx, 64h ; 'd'
0x10071de3f  cmp     eax, ecx
0x10071de41  cmovnb  eax, ecx
0x10071de44  mov     [rsp+1F0h+var_190], eax
0x10071de48  mov     ebx, eax
0x10071de4a  add     rbx, rbx
0x10071de4d  jz      short loc_10071DEAE
0x10071de4f  test    rdi, rdi
0x10071de52  jz      short loc_10071DE6E
0x10071de54  cmp     rbx, 0C8h
0x10071de5b  ja      short loc_10071DE6E
0x10071de5d  mov     r8, rbx; Size
0x10071de60  mov     rdx, rdi; Src
0x10071de63  lea     rcx, [rbp+0F0h+var_110]; void *
0x10071de67  call    memmove
0x10071de6c  jmp     short loc_10071DEAE
0x10071de6e  xor     edx, edx; Val
0x10071de70  mov     r8d, 0C8h; Size
0x10071de76  lea     rcx, [rbp+0F0h+var_110]; void *
0x10071de7a  call    memset_0
0x10071de7f  test    rdi, rdi
0x10071de82  jnz     short loc_10071DE92
0x10071de84  call    cs:__imp__errno
0x10071de8a  mov     dword ptr [rax], 16h
0x10071de90  jmp     short loc_10071DEA7
0x10071de92  cmp     rbx, 0C8h
0x10071de99  jbe     short loc_10071DEAE
0x10071de9b  call    cs:__imp__errno
0x10071dea1  mov     dword ptr [rax], 22h ; '"'
0x10071dea7  call    cs:__imp__invalid_parameter_noinfo
0x10071dead  nop
0x10071deae  mov     rcx, rdi
0x10071deb1  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10071deb7  mov     eax, [rsp+1F0h+var_190]
0x10071debb  add     rax, rax
0x10071debe  lea     rcx, [rbp+0F0h+var_110]
0x10071dec2  mov     [rsp+1F0h+var_1A8], rcx
0x10071dec7  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x10071decc  mov     [rsp+1F0h+Src], r14
0x10071ded1  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x10071ded6  mov     [rsp+1F0h+var_1C8], r14
0x10071dedb  mov     [rsp+1F0h+var_1D0], r14
0x10071dee0  mov     edx, 1Ch
0x10071dee5  lea     ecx, [rdx-2]
0x10071dee8  lea     r9d, [rdx-1Ah]
0x10071deec  lea     r8d, [rdx-0Ch]
0x10071def0  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10071def6  test    r12d, r12d
0x10071def9  jz      loc_10071DFEB
0x10071deff  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071df06  mov     rax, [rcx]
0x10071df09  lea     rdx, [rbp+0F0h+var_160]
0x10071df0d  call    qword ptr [rax]
0x10071df0f  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071df16  mov     rax, [rcx]
0x10071df19  mov     rdx, [rbp+0F0h+var_160]
0x10071df1d  call    qword ptr [rax+8]
0x10071df20  mov     edx, 800h; unsigned int
0x10071df25  mov     rcx, rax; this
0x10071df28  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10071df2d  mov     ebx, eax
0x10071df2f  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071df36  mov     r8, [rcx]
0x10071df39  lea     rdx, [rbp+0F0h+var_158]
0x10071df3d  call    qword ptr [r8]
0x10071df40  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071df47  mov     r8, [rcx]
0x10071df4a  mov     rdx, [rbp+0F0h+var_158]
0x10071df4e  call    qword ptr [r8+8]
0x10071df52  mov     edx, 10000000h; unsigned int
0x10071df57  mov     rcx, rax; this
0x10071df5a  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10071df5f  mov     edi, eax
0x10071df61  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071df68  mov     r8, [rcx]
0x10071df6b  lea     rdx, [rbp+0F0h+var_150]
0x10071df6f  call    qword ptr [r8]
0x10071df72  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10071df79  mov     r8, [rcx]
0x10071df7c  mov     rdx, [rbp+0F0h+var_150]
0x10071df80  call    qword ptr [r8+8]
0x10071df84  mov     esi, r14d
0x10071df87  test    ebx, ebx
0x10071df89  setnz   sil
0x10071df8d  mov     ebx, r14d
0x10071df90  test    edi, edi
0x10071df92  setnz   bl
0x10071df95  mov     edx, 1000h; unsigned int
0x10071df9a  mov     rcx, rax; this
0x10071df9d  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x10071dfa2  mov     r9d, r14d
0x10071dfa5  test    eax, eax
0x10071dfa7  setnz   r9b
0x10071dfab  mov     rax, [r13+20h]
  ... truncated ...
```
