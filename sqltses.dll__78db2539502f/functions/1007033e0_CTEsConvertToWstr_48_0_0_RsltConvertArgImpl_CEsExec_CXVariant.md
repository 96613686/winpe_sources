# CTEsConvertToWstr<48,0,0>::RsltConvertArgImpl(CEsExec *,CXVariant *)

- ea: `0x1007033e0`
- end: `0x1007038fb`
- name: `?RsltConvertArgImpl@?$CTEsConvertToWstr@$0DA@$0A@$0A@@@CAXPEAVCEsExec@@PEAVCXVariant@@@Z`
- size: `1307`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1006fefa0`

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
- `0x1007033e0`

## import_xrefs

- `sqldk!??_V@YAXPEAX@Z` at `0x100703797`
- `sqldk!??_V@YAXPEAX@Z` at `0x100703797`
- `sqldk!SystemThread_TlsIndex` at `0x10070368b`
- `sqldk!SystemThread_TlsOffset` at `0x100703694`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1007036af`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1007036af`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007037d6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007037d6`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100703480`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007034af`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007034dd`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x100703480`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007034af`
- `sqldk!?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ` at `0x1007034dd`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070348c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007034bb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007034e9`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x10070348c`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007034bb`
- `sqldk!?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ` at `0x1007034e9`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070349f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007034ce`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007034fc`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10070349f`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007034ce`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1007034fc`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070376a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100703781`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10070376a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x100703781`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10070378d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10070378d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTEsConvertToWstr<48,0,0>::RsltConvertArgImpl(_QWORD *a1, __int64 a2)
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
    v16 = CXVariant::WstrConvertFromI8(&v37, *(unsigned __int8 *)(a2 + 8), v35);
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
      0x30u,
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
0x1007033e0  push    rbp
0x1007033e2  push    rsi
0x1007033e3  push    rdi
0x1007033e4  push    r12
0x1007033e6  push    r13
0x1007033e8  push    r14
0x1007033ea  push    r15
0x1007033ec  lea     rbp, [rsp-0C0h]
0x1007033f4  sub     rsp, 1C0h
0x1007033fb  mov     [rbp+0F0h+var_128], 0FFFFFFFFFFFFFFFEh
0x100703403  mov     [rsp+1F0h+arg_10], rbx
0x10070340b  mov     rax, cs:__security_cookie
0x100703412  xor     rax, rsp
0x100703415  mov     [rbp+0F0h+var_40], rax
0x10070341c  mov     r15, rdx
0x10070341f  mov     r13, rcx
0x100703422  mov     rbx, [rcx+20h]
0x100703426  cmp     dword ptr [rbx+8], 0
0x10070342a  jle     short loc_10070344D
0x10070342c  cmp     byte ptr [rdx+20h], 3
0x100703430  jnz     short loc_10070343C
0x100703432  mov     [rsp+1F0h+var_18C], 0FFFFFFFFh
0x10070343a  jmp     short loc_100703443
0x10070343c  mov     ecx, [rdx+28h]
0x10070343f  mov     [rsp+1F0h+var_18C], ecx
0x100703443  jnz     short loc_100703455
0x100703445  mov     byte ptr [rdx], 3
0x100703448  jmp     loc_1007038D1
0x10070344d  movzx   eax, byte ptr [rbx+0Eh]
0x100703451  mov     [rsp+1F0h+var_18C], eax
0x100703455  movzx   esi, byte ptr [rbx+10h]
0x100703459  mov     rax, [r13+48h]
0x10070345d  test    rax, rax
0x100703460  jz      short loc_10070347D
0x100703462  mov     rax, [rax+198h]
0x100703469  test    rax, rax
0x10070346c  jz      short loc_10070347D
0x10070346e  cmp     qword ptr [rax+1A8h], 0
0x100703476  jz      short loc_10070347D
0x100703478  mov     dil, 1
0x10070347b  jmp     short loc_100703480
0x10070347d  xor     dil, dil
0x100703480  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x100703486  test    byte ptr [rax+39h], 10h
0x10070348a  jnz     short loc_1007034A9
0x10070348c  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x100703492  test    rax, rax
0x100703495  jz      short loc_100703502
0x100703497  mov     edx, 1CCh
0x10070349c  mov     rcx, rax
0x10070349f  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007034a5  test    eax, eax
0x1007034a7  jz      short loc_100703502
0x1007034a9  cmp     sil, 1
0x1007034ad  jnz     short loc_100703502
0x1007034af  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007034b5  test    byte ptr [rax+39h], 8
0x1007034b9  jnz     short loc_1007034DD
0x1007034bb  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007034c1  test    rax, rax
0x1007034c4  jz      short loc_1007034D8
0x1007034c6  mov     edx, 1CBh
0x1007034cb  mov     rcx, rax
0x1007034ce  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x1007034d4  test    eax, eax
0x1007034d6  jnz     short loc_1007034DD
0x1007034d8  test    dil, dil
0x1007034db  jnz     short loc_100703502
0x1007034dd  call    cs:__imp_?GetUlTraceFlags@CGlobalTraceFlags@@SAPEAEXZ; CGlobalTraceFlags::GetUlTraceFlags(void)
0x1007034e3  test    byte ptr [rax+39h], 8
0x1007034e7  jnz     short loc_100703502
0x1007034e9  call    cs:__imp_?PSessTraceFlags@@YAPEAVCSessionTraceFlags@@XZ; PSessTraceFlags(void)
0x1007034ef  test    rax, rax
0x1007034f2  jz      short loc_100703502
0x1007034f4  mov     edx, 1CBh
0x1007034f9  mov     rcx, rax
0x1007034fc  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x100703502  movzx   eax, byte ptr [rbx+0Fh]
0x100703506  mov     [rsp+1F0h+var_190], eax
0x10070350a  mov     rax, [r13+20h]
0x10070350e  movzx   edx, word ptr [rax+12h]
0x100703512  mov     rax, [r13+38h]
0x100703516  mov     r12, [rax+rdx*8]
0x10070351a  mov     rax, [r13+10h]
0x10070351e  mov     rcx, [rax+20h]
0x100703522  movzx   esi, word ptr [rcx+rdx*2]
0x100703526  xor     r14d, r14d
0x100703529  cmp     [r15], r14b
0x10070352c  jz      short loc_10070353E
0x10070352e  mov     [r15+8], r12
0x100703532  mov     [r15+10h], rsi
0x100703536  mov     r12d, r14d
0x100703539  jmp     loc_1007035FE
0x10070353e  mov     dword ptr [rsp+1F0h+var_188], 0E703h
0x100703546  xorps   xmm0, xmm0
0x100703549  movdqu  [rsp+1F0h+var_188+8], xmm0
0x10070354f  mov     [rbp+0F0h+var_170], r14d
0x100703553  mov     r8d, esi; int
0x100703556  mov     dl, 0E7h; unsigned __int8
0x100703558  lea     rcx, [rbp+0F0h+var_148]; this
0x10070355c  call    ?InitWithMaxLen@CTypeInfo@@AEAAXEH@Z; CTypeInfo::InitWithMaxLen(uchar,int)
0x100703561  movzx   edx, [rbp+0F0h+var_148]
0x100703565  cmp     dl, 62h ; 'b'
0x100703568  jnz     short loc_100703573
0x10070356a  mov     eax, 2
0x10070356f  mov     [rbp+0F0h+var_138], ax
0x100703573  lea     rcx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10070357a  movzx   eax, byte ptr [rdx+rcx+45AE60h]
0x100703582  cmp     [rax+rcx+45AFC0h], r14b
0x10070358a  jnz     short loc_100703594
0x10070358c  sub     dl, 23h ; '#'
0x10070358f  test    dl, 0BFh
0x100703592  jnz     short loc_1007035AD
0x100703594  lea     rcx, [rbp+0F0h+var_148]; this
0x100703598  call    ?FCharacterOrEncryptedCharacter@CTypeInfo@@QEBA_NXZ; CTypeInfo::FCharacterOrEncryptedCharacter(void)
0x10070359d  mov     ecx, [rbp+0F0h+var_134]
0x1007035a0  mov     edx, 0FFFFFFFFh
0x1007035a5  test    al, al
0x1007035a7  cmovnz  ecx, edx
0x1007035aa  mov     [rbp+0F0h+var_134], ecx
0x1007035ad  mov     dword ptr [rsp+1F0h+var_1D0], r14d; int
0x1007035b2  lea     r9, [rbp+0F0h+var_148]; struct CTypeInfo *
0x1007035b6  mov     r8d, esi; unsigned int
0x1007035b9  mov     rdx, r12; unsigned __int8 *
0x1007035bc  lea     rcx, [rsp+1F0h+var_188]; this
0x1007035c1  call    ?CopyFromPbInternal@CXVariant@@AEAAXPEAEKPEBVCTypeInfo@@H@Z; CXVariant::CopyFromPbInternal(uchar *,ulong,CTypeInfo const *,int)
0x1007035c6  movzx   edx, byte ptr [r15+8]
0x1007035cb  mov     r8d, [rsp+1F0h+var_190]
0x1007035d0  lea     rcx, [rsp+1F0h+var_188]
0x1007035d5  call    ?WstrConvertFromI8@CXVariant@@QEAAJ_JW4EPadding@@@Z; CXVariant::WstrConvertFromI8(__int64,EPadding)
0x1007035da  mov     r12d, eax
0x1007035dd  test    eax, eax
0x1007035df  jnz     short loc_1007035FE
0x1007035e1  movups  xmm0, [rsp+1F0h+var_188]
0x1007035e6  movups  xmmword ptr [r15], xmm0
0x1007035ea  movups  xmm1, xmmword ptr [rsp+78h]
0x1007035ef  movups  xmmword ptr [r15+10h], xmm1
0x1007035f4  mov     eax, 0FFFEh
0x1007035f9  and     [r15+2], ax
0x1007035fe  cmp     byte ptr [rbx+10h], 1
0x100703602  jnz     loc_1007037DC
0x100703608  movzx   eax, word ptr [r15+2]
0x10070360d  shr     ax, 0Ch
0x100703611  test    al, 1
0x100703613  jz      loc_1007037DC
0x100703619  mov     eax, r14d
0x10070361c  mov     [rsp+1F0h+var_190], eax
0x100703620  test    dil, dil
0x100703623  jz      loc_1007037A1
0x100703629  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100703630  mov     rax, [rcx]
0x100703633  lea     rdx, [rbp+0F0h+var_168]
0x100703637  call    qword ptr [rax]
0x100703639  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x100703640  mov     rax, [rcx]
0x100703643  mov     rdx, [rbp+0F0h+var_168]
0x100703647  call    qword ptr [rax+8]
0x10070364a  mov     rcx, cs:?x_pIDbOptsProvider@@3PEAUISqlTypeSystemExtender_IDbAndSetOptsProvider@@EA; ISqlTypeSystemExtender_IDbAndSetOptsProvider * x_pIDbOptsProvider
0x100703651  mov     rax, [rcx]
0x100703654  call    qword ptr [rax]
0x100703656  mov     rcx, cs:?x_pIDbTableProvider@@3PEAUISqlTypeSystemExtender_IDbTableOptionsProvider@@EA; ISqlTypeSystemExtender_IDbTableOptionsProvider * x_pIDbTableProvider
0x10070365d  mov     r8, [rcx]
0x100703660  movzx   edx, ax
0x100703663  call    qword ptr [r8+8]
0x100703667  mov     rsi, rax
0x10070366a  mov     r9, [r13+20h]
0x10070366e  movzx   ebx, word ptr [r9+18h]
0x100703673  shl     rbx, 5
0x100703677  mov     rcx, [r13+10h]
0x10070367b  add     rbx, [rcx+0A8h]
0x100703682  mov     r8, gs:58h
0x10070368b  mov     rcx, cs:__imp_SystemThread_TlsIndex
0x100703692  mov     edx, [rcx]
0x100703694  mov     rcx, cs:__imp_SystemThread_TlsOffset
0x10070369b  mov     edi, [rcx]
0x10070369d  add     rdi, [r8+rdx*8]
0x1007036a1  mov     rdx, [rdi+100h]
0x1007036a8  test    rdx, rdx
0x1007036ab  jnz     short loc_1007036C0
0x1007036ad  xor     ecx, ecx
0x1007036af  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1007036b5  mov     rdx, [rdi+100h]
0x1007036bc  mov     r9, [r13+20h]
0x1007036c0  mov     rdx, [rdx+3E8h]; struct IMemObj *
0x1007036c7  mov     ecx, [r9+0Ch]
0x1007036cb  mov     rax, [r13+30h]
0x1007036cf  mov     [rsp+1F0h+var_198], r14d; int
0x1007036d4  mov     [rsp+1F0h+var_1A0], r14d; unsigned int
0x1007036d9  mov     [rsp+1F0h+var_1A8], r14; wchar_t *
0x1007036de  mov     [rsp+1F0h+var_1B0], r14d; unsigned int
0x1007036e3  mov     [rsp+1F0h+Src], r14; Src
0x1007036e8  mov     [rsp+1F0h+var_1C0], 2; int
0x1007036f0  mov     [rsp+1F0h+var_1C8], rsi; struct CDefaultCollation *
0x1007036f5  mov     [rsp+1F0h+var_1D0], rbx; struct CTypeInfo *
0x1007036fa  mov     r9, rdx; struct IMemObj *
0x1007036fd  lea     r8, [rsp+1F0h+var_190]; unsigned int *
0x100703702  mov     rcx, [rax+rcx*8]; this
0x100703706  call    ?PwchConvertToStringInternal@CXVariant@@IEBAPEA_WPEAVIMemObj@@PEAK0PEBVCTypeInfo@@PEBVCDefaultCollation@@JPEB_WK4KH@Z; CXVariant::PwchConvertToStringInternal(IMemObj *,ulong *,IMemObj *,CTypeInfo const *,CDefaultCollation const *,long,wchar_t const *,ulong,wchar_t const *,ulong,int)
0x10070370b  mov     rdi, rax
0x10070370e  mov     [rbp+0F0h+var_120], rax
0x100703712  test    rax, rax
0x100703715  jnz     short loc_10070371C
0x100703717  mov     eax, r14d
0x10070371a  jmp     short loc_10070372A
0x10070371c  mov     eax, [rsp+1F0h+var_190]
0x100703720  mov     ecx, 64h ; 'd'
0x100703725  cmp     eax, ecx
0x100703727  cmovnb  eax, ecx
0x10070372a  mov     [rsp+1F0h+var_190], eax
0x10070372e  mov     ebx, eax
0x100703730  add     rbx, rbx
0x100703733  jz      short loc_100703794
0x100703735  test    rdi, rdi
0x100703738  jz      short loc_100703754
0x10070373a  cmp     rbx, 0C8h
0x100703741  ja      short loc_100703754
0x100703743  mov     r8, rbx; Size
0x100703746  mov     rdx, rdi; Src
0x100703749  lea     rcx, [rbp+0F0h+var_110]; void *
0x10070374d  call    memmove
0x100703752  jmp     short loc_100703794
0x100703754  xor     edx, edx; Val
0x100703756  mov     r8d, 0C8h; Size
0x10070375c  lea     rcx, [rbp+0F0h+var_110]; void *
0x100703760  call    memset_0
0x100703765  test    rdi, rdi
0x100703768  jnz     short loc_100703778
0x10070376a  call    cs:__imp__errno
0x100703770  mov     dword ptr [rax], 16h
0x100703776  jmp     short loc_10070378D
0x100703778  cmp     rbx, 0C8h
0x10070377f  jbe     short loc_100703794
0x100703781  call    cs:__imp__errno
0x100703787  mov     dword ptr [rax], 22h ; '"'
0x10070378d  call    cs:__imp__invalid_parameter_noinfo
0x100703793  nop
0x100703794  mov     rcx, rdi
0x100703797  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10070379d  mov     eax, [rsp+1F0h+var_190]
0x1007037a1  add     rax, rax
0x1007037a4  lea     rcx, [rbp+0F0h+var_110]
0x1007037a8  mov     [rsp+1F0h+var_1A8], rcx
0x1007037ad  mov     qword ptr [rsp+1F0h+var_1B0], rax
0x1007037b2  mov     [rsp+1F0h+Src], r14
0x1007037b7  mov     qword ptr [rsp+1F0h+var_1C0], r14
0x1007037bc  mov     [rsp+1F0h+var_1C8], r14
0x1007037c1  mov     [rsp+1F0h+var_1D0], r14
0x1007037c6  mov     edx, 1Ch
0x1007037cb  lea     ecx, [rdx-2]
0x1007037ce  lea     r9d, [rdx-1Ah]
0x1007037d2  lea     r8d, [rdx-0Ch]
0x1007037d6  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1007037dc  test    r12d, r12d
0x1007037df  jz      loc_1007038D1
0x1007037e5  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007037ec  mov     rax, [rcx]
0x1007037ef  lea     rdx, [rbp+0F0h+var_160]
0x1007037f3  call    qword ptr [rax]
0x1007037f5  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x1007037fc  mov     rax, [rcx]
0x1007037ff  mov     rdx, [rbp+0F0h+var_160]
0x100703803  call    qword ptr [rax+8]
0x100703806  mov     edx, 800h; unsigned int
0x10070380b  mov     rcx, rax; this
0x10070380e  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100703813  mov     ebx, eax
0x100703815  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070381c  mov     r8, [rcx]
0x10070381f  lea     rdx, [rbp+0F0h+var_158]
0x100703823  call    qword ptr [r8]
0x100703826  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070382d  mov     r8, [rcx]
0x100703830  mov     rdx, [rbp+0F0h+var_158]
0x100703834  call    qword ptr [r8+8]
0x100703838  mov     edx, 10000000h; unsigned int
0x10070383d  mov     rcx, rax; this
0x100703840  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100703845  mov     edi, eax
0x100703847  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070384e  mov     r8, [rcx]
0x100703851  lea     rdx, [rbp+0F0h+var_150]
0x100703855  call    qword ptr [r8]
0x100703858  mov     rcx, cs:?x_pContextProvider@@3PEAUISqlTypeSystemExtender_ContextProvider@@EA; ISqlTypeSystemExtender_ContextProvider * x_pContextProvider
0x10070385f  mov     r8, [rcx]
0x100703862  mov     rdx, [rbp+0F0h+var_150]
0x100703866  call    qword ptr [r8+8]
0x10070386a  mov     esi, r14d
0x10070386d  test    ebx, ebx
0x10070386f  setnz   sil
0x100703873  mov     ebx, r14d
0x100703876  test    edi, edi
0x100703878  setnz   bl
0x10070387b  mov     edx, 1000h; unsigned int
0x100703880  mov     rcx, rax; this
0x100703883  call    ?LUserOpt1Get@CDbAndSetOpts@@AEBAII@Z; CDbAndSetOpts::LUserOpt1Get(uint)
0x100703888  mov     r9d, r14d
0x10070388b  test    eax, eax
0x10070388d  setnz   r9b
0x100703891  mov     rax, [r13+20h]
0x100703895  movzx   r8d, byte ptr [rax+11h]
  ... truncated ...
```
