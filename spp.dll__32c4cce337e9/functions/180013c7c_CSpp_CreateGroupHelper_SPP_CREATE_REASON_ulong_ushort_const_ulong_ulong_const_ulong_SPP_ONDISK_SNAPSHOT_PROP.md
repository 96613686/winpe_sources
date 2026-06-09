# CSpp::_CreateGroupHelper(_SPP_CREATE_REASON,ulong,ushort const *,ulong,ulong const *,ulong,_SPP_ONDISK_SNAPSHOT_PROP *)

- ea: `0x180013c7c`
- end: `0x1800141a6`
- name: `?_CreateGroupHelper@CSpp@@AEAAJW4_SPP_CREATE_REASON@@KPEBGKPEBKKPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z`
- size: `1322`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64, unsigned int, unsigned int *, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006550`
- `0x180006cf0`

## callees

- `0x180002bb8`
- `0x180007650`
- `0x180008ed0`
- `0x18000e48c`
- `0x18000f888`
- `0x18001176c`
- `0x180013c7c`
- `0x18001431c`
- `0x18001ac40`
- `0x18001b1e0`
- `0x18001b668`
- `0x18001bb24`
- `0x18001cbfc`
- `0x18001e3cc`
- `0x180021360`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d00c`
- `0x18002d1e0`
- `0x18002daf0`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180013f58`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180013f58`
- `ntdll!RtlGetCurrentTransaction` at `0x180013cd1`
- `ntdll!RtlGetCurrentTransaction` at `0x180013cd1`
- `ntdll!RtlSetCurrentTransaction` at `0x180013cdc`
- `ntdll!RtlSetCurrentTransaction` at `0x18001417b`
- `ntdll!RtlSetCurrentTransaction` at `0x180013cdc`
- `ntdll!RtlSetCurrentTransaction` at `0x18001417b`

## string_xrefs

- `0x180013d1a`: `CSpp::_CreateGroupHelper`

## pseudocode

```c
__int64 __fastcall CSpp::_CreateGroupHelper(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6,
        unsigned int a7,
        __int64 a8)
{
  __int64 CurrentTransaction; // rbx
  int v13; // r8d
  CVolumeEntryMap *v14; // r14
  __int64 v15; // rcx
  _BYTE *v16; // rax
  __int16 v17; // ax
  CSpp *v18; // rcx
  int v19; // esi
  unsigned int v20; // r12d
  int v21; // r13d
  unsigned int v22; // eax
  CSpp *v23; // rcx
  int inited; // eax
  __int64 v25; // r9
  bool v26; // sf
  __int16 v27; // ax
  int v28; // eax
  unsigned int v29; // esi
  int UniqueVolumes; // eax
  int v31; // eax
  int v32; // eax
  CSpp *v33; // rcx
  int v34; // eax
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int64 v37; // rax
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int64 v44; // rcx
  unsigned int v45; // r8d
  __int16 v46; // ax
  __int64 v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  unsigned int v50; // edi
  int v52; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v53; // [rsp+64h] [rbp-9Ch]
  __int16 v54; // [rsp+66h] [rbp-9Ah]
  struct CVolumeEntryMap *v55; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v56; // [rsp+A0h] [rbp-60h]
  unsigned int v57; // [rsp+A4h] [rbp-5Ch]
  int v58; // [rsp+A8h] [rbp-58h]
  unsigned int *v59; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v60; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v61; // [rsp+C0h] [rbp-40h] BYREF
  GUID v62; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v63; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v64; // [rsp+F0h] [rbp-10h]
  __int128 v65; // [rsp+100h] [rbp+0h]
  __int128 v66; // [rsp+110h] [rbp+10h]
  __int128 v67; // [rsp+120h] [rbp+20h]
  __int128 v68; // [rsp+130h] [rbp+30h]
  __int128 v69; // [rsp+140h] [rbp+40h]
  __int128 v70; // [rsp+150h] [rbp+50h]
  __int128 v71; // [rsp+160h] [rbp+60h]
  __int64 v72; // [rsp+170h] [rbp+70h]

  v59 = a6;
  *(_QWORD *)&v61.Data1 = a4;
  v57 = a3;
  v56 = a2;
  CurrentTransaction = RtlGetCurrentTransaction();
  RtlSetCurrentTransaction(0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, v13, a2, a4);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v52, "CSpp::_CreateGroupHelper", 8774, 1);
  v14 = 0;
  v55 = 0;
  v63.Data1 = 0;
  memset_0(&v63.Data2, 0, 0x94u);
  v60 = 0;
  if ( a8 )
  {
    v15 = 152;
    v16 = (_BYTE *)a8;
    do
    {
      *v16++ = 0;
      --v15;
    }
    while ( v15 );
  }
  v17 = 8785;
  if ( a2 > 0x12 )
    goto LABEL_8;
  v53 = 8785;
  v17 = 8786;
  if ( (a5 & 0xFFFFFFE0) != 0 )
    goto LABEL_8;
  v53 = 8786;
  v17 = 8787;
  if ( (a3 & 0xFFFFFFF8) != 0 )
    goto LABEL_8;
  v53 = 8787;
  if ( a7 && !v59 )
  {
    v52 = -2147024809;
    v17 = 8788;
    goto LABEL_52;
  }
  v53 = 8788;
  v17 = 8789;
  if ( !a8 )
  {
LABEL_8:
    v52 = -2147024809;
LABEL_52:
    v54 = v17;
    goto LABEL_53;
  }
  v52 = 0;
  v53 = 8789;
  if ( (unsigned int)SxIsSafeMode() || (unsigned int)SxIsWinPE() || (unsigned int)SxIsAuditMode() )
  {
    v52 = -2147023812;
    v17 = 8791;
    goto LABEL_52;
  }
  v18 = *(CSpp **)(a1 + 104);
  v52 = 0;
  v53 = 8791;
  if ( v18 )
  {
    v62 = GUID_NULL;
    v52 = CSxDiagnostics::LogDiagnostic(v18, 2000, 0, 0, &v62);
    v17 = 8795;
    if ( v52 < 0 )
      goto LABEL_52;
    v53 = 8795;
  }
  v19 = 0;
  v20 = a5 & 0xFFFFFFFD;
  if ( !*(_DWORD *)(a1 + 48) )
    v20 = a5;
  v21 = v56;
  v58 = (v20 >> 4) & 1;
  if ( v56 == 15 )
    v20 = CSpp::_ModifyBackupFlagForBackupType(v18, v20);
  ATL::CComPtr<IVssBackupComponentsEx3>::operator=((struct IUnknown **)(a1 + 80));
  v22 = 0;
  for ( *(_DWORD *)(a1 + 120) = 0; ; v22 = *(_DWORD *)(a1 + 120) )
  {
    if ( v22 >= 5 )
    {
      v52 = v19;
      v25 = (unsigned int)v19;
      if ( v19 < 0 )
      {
        v27 = 8879;
        goto LABEL_39;
      }
LABEL_41:
      v35 = v64;
      *(struct _GUID *)a8 = v63;
      v53 = 8879;
      v36 = v65;
      v37 = v72;
      *(_OWORD *)(a8 + 16) = v35;
      v38 = v66;
      *(_OWORD *)(a8 + 32) = v36;
      v39 = v67;
      *(_OWORD *)(a8 + 48) = v38;
      v40 = v68;
      *(_OWORD *)(a8 + 64) = v39;
      v41 = v69;
      *(_OWORD *)(a8 + 80) = v40;
      v42 = v70;
      *(_OWORD *)(a8 + 96) = v41;
      v43 = v71;
      *(_OWORD *)(a8 + 112) = v42;
      *(_OWORD *)(a8 + 128) = v43;
      *(_QWORD *)(a8 + 144) = v37;
      memset_0(&v63, 0, 0x98u);
      if ( (v20 & 2) != 0 )
        v45 = *(_DWORD *)(a8 + 16);
      else
        v45 = 0;
      CSpp::_LaunchScopingForRestorePoint(v44, v21, v45);
      v25 = 0;
      v46 = 8891;
      goto LABEL_48;
    }
    Free_SPP_ONDISK_SNAPSHOT_PROP((struct _SPP_ONDISK_SNAPSHOT_PROP *)&v63);
    inited = CSpp::_InitTimer(v23, *(_DWORD *)(a1 + 44), &v60);
    v25 = (unsigned int)inited;
    v52 = inited;
    v26 = inited < 0;
    v27 = 8833;
    if ( v26 )
      goto LABEL_39;
    v53 = 8833;
    if ( v14 )
    {
      v55 = 0;
      CVolumeEntryMap::Release(v14);
    }
    v28 = CVolumeEntryMap::CreateInstance(&v55);
    v14 = v55;
    v25 = (unsigned int)v28;
    v52 = v28;
    v26 = v28 < 0;
    v27 = 8836;
    if ( v26 )
      goto LABEL_39;
    v29 = v57;
    v53 = 8836;
    UniqueVolumes = CSpp::_GetUniqueVolumes((CSpp *)a1, v58, v57, v55, (struct _SPP_ONDISK_SNAPSHOT_PROP *)&v63);
    v25 = (unsigned int)UniqueVolumes;
    v52 = UniqueVolumes;
    v26 = UniqueVolumes < 0;
    v27 = 8842;
    if ( v26 )
      goto LABEL_39;
    v53 = 8842;
    if ( !RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)v14) )
      break;
    v31 = CSpp::_BuildCommonSnapshotProp((CSpp *)a1, v21, *(const unsigned __int16 **)&v61.Data1, (__int64)&v63);
    v25 = (unsigned int)v31;
    v52 = v31;
    v26 = v31 < 0;
    v27 = 8851;
    if ( v26 )
      goto LABEL_39;
    v53 = 8851;
    v32 = CSpp::_CreateSnapshotSet((CSpp *)a1, v14, v60, v20, 0, 0, 0, v59, a7, v21 == 15, v29, &v63);
    v19 = v32;
    if ( v32 >= 0 )
    {
      v52 = v32;
      goto LABEL_41;
    }
    if ( (unsigned int)CSpp::_IsRetryableError(v33, &dword_18003BB40, 7u, v32) )
    {
      v25 = (unsigned int)v19;
      v52 = v19;
      v27 = 8876;
LABEL_39:
      v54 = v27;
      goto LABEL_49;
    }
    v34 = Sleep(0x1388u);
    v25 = (unsigned int)v34;
    v52 = v34;
    v26 = v34 < 0;
    v27 = 8873;
    if ( v26 )
      goto LABEL_39;
    ++*(_DWORD *)(a1 + 120);
    v53 = 8873;
  }
  v25 = 1;
  v46 = 8845;
LABEL_48:
  v53 = v46;
  v52 = v25;
LABEL_49:
  v47 = *(_QWORD *)(a1 + 104);
  if ( v47 )
  {
    v61 = v63;
    CSxDiagnostics::LogDiagnostic(v47, 2000, 1, v25, &v61);
  }
LABEL_53:
  Free_SPP_ONDISK_SNAPSHOT_PROP((struct _SPP_ONDISK_SNAPSHOT_PROP *)&v63);
  v50 = v52;
  if ( v14 )
    CVolumeEntryMap::Release(v14);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v52, v48, v49);
  RtlSetCurrentTransaction(CurrentTransaction);
  return v50;
}

```

## disassembly

```asm
0x180013c7c  push    rbp
0x180013c7e  push    rbx
0x180013c7f  push    rsi
0x180013c80  push    rdi
0x180013c81  push    r12
0x180013c83  push    r13
0x180013c85  push    r14
0x180013c87  push    r15
0x180013c89  lea     rbp, [rsp-98h]
0x180013c91  sub     rsp, 198h
0x180013c98  mov     rax, cs:__security_cookie
0x180013c9f  xor     rax, rsp
0x180013ca2  mov     [rbp+0D0h+var_50], rax
0x180013ca9  mov     rax, [rbp+0D0h+arg_28]
0x180013cb0  mov     r14, r9
0x180013cb3  mov     rdi, [rbp+0D0h+arg_38]
0x180013cba  mov     r12d, r8d
0x180013cbd  mov     [rbp+0D0h+var_120], rax
0x180013cc1  mov     esi, edx
0x180013cc3  mov     qword ptr [rbp+0D0h+var_110], r9
0x180013cc7  mov     r15, rcx
0x180013cca  mov     [rbp+0D0h+var_12C], r8d
0x180013cce  mov     [rbp+0D0h+var_130], edx
0x180013cd1  call    cs:__imp_RtlGetCurrentTransaction
0x180013cd7  xor     ecx, ecx
0x180013cd9  mov     rbx, rax
0x180013cdc  call    cs:__imp_RtlSetCurrentTransaction
0x180013ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ce9  lea     rax, WPP_GLOBAL_Control
0x180013cf0  cmp     rcx, rax
0x180013cf3  jz      short loc_180013D14
0x180013cf5  test    dword ptr [rcx+1Ch], 20000000h
0x180013cfc  jz      short loc_180013D14
0x180013cfe  mov     rcx, [rcx+10h]
0x180013d02  mov     edx, 8Ch
0x180013d07  mov     r9d, esi
0x180013d0a  mov     [rsp+1D0h+var_1B0], r14
0x180013d0f  call    WPP_SF_dS
0x180013d14  mov     r9d, 1; unsigned __int16
0x180013d1a  lea     rdx, aCsppCreategrou; "CSpp::_CreateGroupHelper"
0x180013d21  mov     r8d, 2246h; unsigned __int16
0x180013d27  lea     rcx, [rsp+1D0h+var_170]; this
0x180013d2c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180013d31  xor     r14d, r14d
0x180013d34  lea     rcx, [rbp+0D0h+var_F0.Data2]; void *
0x180013d38  xor     edx, edx; Val
0x180013d3a  mov     [rbp+0D0h+var_138], r14
0x180013d3e  mov     r8d, 94h; Size
0x180013d44  mov     [rbp+0D0h+var_F0.Data1], r14d
0x180013d48  call    memset_0
0x180013d4d  xor     edx, edx
0x180013d4f  mov     [rbp+0D0h+var_118], rdx
0x180013d53  test    rdi, rdi
0x180013d56  jz      short loc_180013D6B
0x180013d58  mov     ecx, 98h
0x180013d5d  mov     rax, rdi
0x180013d60  mov     [rax], dl
0x180013d62  inc     rax
0x180013d65  sub     rcx, 1
0x180013d69  jnz     short loc_180013D60
0x180013d6b  mov     eax, 2251h
0x180013d70  cmp     esi, 12h
0x180013d73  jbe     short loc_180013D82
0x180013d75  mov     [rsp+1D0h+var_170], 80070057h
0x180013d7d  jmp     loc_18001414F
0x180013d82  mov     r13d, [rbp+0D0h+arg_20]
0x180013d89  mov     [rsp+1D0h+var_16C], ax
0x180013d8e  mov     eax, 2252h
0x180013d93  test    r13d, 0FFFFFFE0h
0x180013d9a  jnz     short loc_180013D75
0x180013d9c  mov     [rsp+1D0h+var_16C], ax
0x180013da1  mov     eax, 2253h
0x180013da6  test    r12d, 0FFFFFFF8h
0x180013dad  jnz     short loc_180013D75
0x180013daf  mov     [rsp+1D0h+var_16C], ax
0x180013db4  cmp     [rbp+0D0h+arg_30], edx
0x180013dba  jz      short loc_180013DD4
0x180013dbc  cmp     [rbp+0D0h+var_120], rdx
0x180013dc0  jnz     short loc_180013DD4
0x180013dc2  mov     [rsp+1D0h+var_170], 80070057h
0x180013dca  mov     eax, 2254h
0x180013dcf  jmp     loc_18001414F
0x180013dd4  mov     eax, 2254h
0x180013dd9  mov     [rsp+1D0h+var_16C], ax
0x180013dde  mov     eax, 2255h
0x180013de3  test    rdi, rdi
0x180013de6  jz      short loc_180013D75
0x180013de8  mov     [rsp+1D0h+var_170], edx
0x180013dec  mov     [rsp+1D0h+var_16C], ax
0x180013df1  call    ?SxIsSafeMode@@YAHXZ; SxIsSafeMode(void)
0x180013df6  test    eax, eax
0x180013df8  jnz     loc_180014142
0x180013dfe  call    ?SxIsWinPE@@YAHXZ; SxIsWinPE(void)
0x180013e03  test    eax, eax
0x180013e05  jnz     loc_180014142
0x180013e0b  call    ?SxIsAuditMode@@YAHXZ; SxIsAuditMode(void)
0x180013e10  test    eax, eax
0x180013e12  jnz     loc_180014142
0x180013e18  mov     rcx, [r15+68h]
0x180013e1c  mov     eax, 2257h
0x180013e21  mov     [rsp+1D0h+var_170], r14d
0x180013e26  mov     [rsp+1D0h+var_16C], ax
0x180013e2b  test    rcx, rcx
0x180013e2e  jz      short loc_180013E6B
0x180013e30  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180013e37  lea     rax, [rbp+0D0h+var_100]
0x180013e3b  xor     r9d, r9d
0x180013e3e  xor     r8d, r8d
0x180013e41  mov     [rsp+1D0h+var_1B0], rax
0x180013e46  mov     edx, 7D0h
0x180013e4b  movdqu  [rbp+0D0h+var_100], xmm0
0x180013e50  call    ?LogDiagnostic@CSxDiagnostics@@QEAAJW4SX_DIAG_OPERATION@@W4SX_DIAG_TYPE@@JU_GUID@@@Z; CSxDiagnostics::LogDiagnostic(SX_DIAG_OPERATION,SX_DIAG_TYPE,long,_GUID)
0x180013e55  mov     [rsp+1D0h+var_170], eax
0x180013e59  test    eax, eax
0x180013e5b  mov     eax, 225Bh
0x180013e60  js      loc_18001414F
0x180013e66  mov     [rsp+1D0h+var_16C], ax
0x180013e6b  mov     r12d, r13d
0x180013e6e  xor     esi, esi
0x180013e70  and     r12d, 0FFFFFFFDh
0x180013e74  cmp     [r15+30h], esi
0x180013e78  cmovz   r12d, r13d
0x180013e7c  mov     r13d, [rbp+0D0h+var_130]
0x180013e80  mov     eax, r12d
0x180013e83  shr     eax, 4
0x180013e86  and     eax, 1
0x180013e89  mov     [rbp+0D0h+var_128], eax
0x180013e8c  cmp     r13d, 0Fh
0x180013e90  jnz     short loc_180013E9D
0x180013e92  mov     edx, r12d; unsigned int
0x180013e95  call    ?_ModifyBackupFlagForBackupType@CSpp@@AEAAKK@Z; CSpp::_ModifyBackupFlagForBackupType(ulong)
0x180013e9a  mov     r12d, eax
0x180013e9d  lea     rcx, [r15+50h]
0x180013ea1  call    ??4?$CComPtr@VIVssBackupComponentsEx3@@@ATL@@QEAAPEAVIVssBackupComponentsEx3@@PEAV2@@Z; ATL::CComPtr<IVssBackupComponentsEx3>::operator=(IVssBackupComponentsEx3 *)
0x180013ea6  xor     eax, eax
0x180013ea8  mov     [r15+78h], esi
0x180013eac  cmp     eax, 5
0x180013eaf  jnb     loc_1800140D2
0x180013eb5  lea     rcx, [rbp+0D0h+var_F0]; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x180013eb9  call    ?Free_SPP_ONDISK_SNAPSHOT_PROP@@YAXPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; Free_SPP_ONDISK_SNAPSHOT_PROP(_SPP_ONDISK_SNAPSHOT_PROP *)
0x180013ebe  mov     edx, [r15+2Ch]; unsigned int
0x180013ec2  lea     r8, [rbp+0D0h+var_118]; unsigned __int64 *
0x180013ec6  call    ?_InitTimer@CSpp@@AEAAJKPEA_K@Z; CSpp::_InitTimer(ulong,unsigned __int64 *)
0x180013ecb  mov     r9d, eax
0x180013ece  mov     [rsp+1D0h+var_170], eax
0x180013ed2  test    eax, eax
0x180013ed4  mov     eax, 2281h
0x180013ed9  js      loc_18001403B
0x180013edf  mov     [rsp+1D0h+var_16C], ax
0x180013ee4  test    r14, r14
0x180013ee7  jz      short loc_180013EF9
0x180013ee9  mov     rcx, r14; this
0x180013eec  mov     [rbp+0D0h+var_138], 0
0x180013ef4  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x180013ef9  lea     rcx, [rbp+0D0h+var_138]; struct CVolumeEntryMap **
0x180013efd  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x180013f02  mov     r14, [rbp+0D0h+var_138]
0x180013f06  mov     r9d, eax
0x180013f09  mov     [rsp+1D0h+var_170], eax
0x180013f0d  test    eax, eax
0x180013f0f  mov     eax, 2284h
0x180013f14  js      loc_18001403B
0x180013f1a  mov     esi, [rbp+0D0h+var_12C]
0x180013f1d  mov     r9, r14; struct CVolumeEntryMap *
0x180013f20  mov     edx, [rbp+0D0h+var_128]; int
0x180013f23  mov     r8d, esi; unsigned int
0x180013f26  mov     [rsp+1D0h+var_16C], ax
0x180013f2b  mov     rcx, r15; this
0x180013f2e  lea     rax, [rbp+0D0h+var_F0]
0x180013f32  mov     [rsp+1D0h+var_1B0], rax; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x180013f37  call    ?_GetUniqueVolumes@CSpp@@AEAAJHKPEAVCVolumeEntryMap@@PEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; CSpp::_GetUniqueVolumes(int,ulong,CVolumeEntryMap *,_SPP_ONDISK_SNAPSHOT_PROP *)
0x180013f3c  mov     r9d, eax
0x180013f3f  mov     [rsp+1D0h+var_170], eax
0x180013f43  test    eax, eax
0x180013f45  mov     eax, 228Ah
0x180013f4a  js      loc_18001403B
0x180013f50  mov     [rsp+1D0h+var_16C], ax
0x180013f55  mov     rcx, [r14]; Table
0x180013f58  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180013f5e  test    eax, eax
0x180013f60  jz      loc_1800140C5
0x180013f66  mov     r8, qword ptr [rbp+0D0h+var_110]
0x180013f6a  lea     r9, [rbp+0D0h+var_F0]
0x180013f6e  mov     edx, r13d
0x180013f71  mov     rcx, r15
0x180013f74  call    ?_BuildCommonSnapshotProp@CSpp@@AEAAJW4_SPP_CREATE_REASON@@PEBGPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; CSpp::_BuildCommonSnapshotProp(_SPP_CREATE_REASON,ushort const *,_SPP_ONDISK_SNAPSHOT_PROP *)
0x180013f79  mov     r9d, eax
0x180013f7c  mov     [rsp+1D0h+var_170], eax
0x180013f80  test    eax, eax
0x180013f82  mov     eax, 2293h
0x180013f87  js      loc_18001403B
0x180013f8d  mov     r8, [rbp+0D0h+var_118]; unsigned __int64
0x180013f91  lea     rcx, [rbp+0D0h+var_F0]
0x180013f95  mov     [rsp+1D0h+var_178], rcx; struct _GUID *
0x180013f9a  xor     r9d, r9d
0x180013f9d  mov     [rsp+1D0h+var_180], esi; unsigned int
0x180013fa1  cmp     r13d, 0Fh
0x180013fa5  mov     [rsp+1D0h+var_16C], ax
0x180013faa  mov     rdx, r14; struct CVolumeEntryMap *
0x180013fad  mov     eax, r9d
0x180013fb0  mov     rcx, r15; this
0x180013fb3  setz    al
0x180013fb6  mov     [rsp+1D0h+var_188], eax; int
0x180013fba  mov     eax, [rbp+0D0h+arg_30]
0x180013fc0  mov     [rsp+1D0h+var_190], eax; unsigned int
0x180013fc4  mov     rax, [rbp+0D0h+var_120]
0x180013fc8  mov     [rsp+1D0h+var_198], rax; unsigned int *
0x180013fcd  mov     [rsp+1D0h+var_1A0], r9; struct _SPP_WRITER_COMPONENT_INFO *
0x180013fd2  mov     [rsp+1D0h+var_1A8], r9d; unsigned int
0x180013fd7  mov     byte ptr [rsp+1D0h+var_1B0], r9b; char
0x180013fdc  mov     r9d, r12d; unsigned int
0x180013fdf  call    ?_CreateSnapshotSet@CSpp@@AEAAJPEAVCVolumeEntryMap@@_KKEKPEAU_SPP_WRITER_COMPONENT_INFO@@PEBKKHKPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; CSpp::_CreateSnapshotSet(CVolumeEntryMap *,unsigned __int64,ulong,uchar,ulong,_SPP_WRITER_COMPONENT_INFO *,ulong const *,ulong,int,ulong,_SPP_ONDISK_SNAPSHOT_PROP *)
0x180013fe4  mov     esi, eax
0x180013fe6  test    eax, eax
0x180013fe8  jns     short loc_180014045
0x180013fea  mov     r9d, eax; int
0x180013fed  lea     rdx, dword_18003BB40; int *
0x180013ff4  mov     r8d, 7; unsigned int
0x180013ffa  call    ?_IsRetryableError@CSpp@@AEAAJQEBJKJ@Z; CSpp::_IsRetryableError(long const * const,ulong,long)
0x180013fff  test    eax, eax
0x180014001  jnz     short loc_18001402F
0x180014003  mov     ecx, 1388h; dwTimeout
0x180014008  call    _Sleep
0x18001400d  mov     r9d, eax
0x180014010  mov     [rsp+1D0h+var_170], eax
0x180014014  test    eax, eax
0x180014016  mov     eax, 22A9h
0x18001401b  js      short loc_18001403B
0x18001401d  inc     dword ptr [r15+78h]
0x180014021  mov     [rsp+1D0h+var_16C], ax
0x180014026  mov     eax, [r15+78h]
0x18001402a  jmp     loc_180013EAC
0x18001402f  mov     r9d, esi
0x180014032  mov     [rsp+1D0h+var_170], esi
0x180014036  mov     eax, 22ACh
0x18001403b  mov     [rsp+1D0h+var_16A], ax
0x180014040  jmp     loc_180014108
0x180014045  mov     [rsp+1D0h+var_170], esi
0x180014049  movaps  xmm0, xmmword ptr [rbp+0D0h+var_F0.Data1]
0x18001404d  lea     rcx, [rbp+0D0h+var_F0]; void *
0x180014051  movaps  xmm1, [rbp+0D0h+var_E0]
0x180014055  mov     eax, 22AFh
0x18001405a  movups  xmmword ptr [rdi], xmm0
0x18001405d  xor     edx, edx; Val
0x18001405f  mov     [rsp+1D0h+var_16C], ax
0x180014064  movaps  xmm0, [rbp+0D0h+var_D0]
0x180014068  mov     r8d, 98h; Size
0x18001406e  mov     rax, [rbp+0D0h+var_60]
0x180014072  movups  xmmword ptr [rdi+10h], xmm1
0x180014076  movaps  xmm1, [rbp+0D0h+var_C0]
0x18001407a  movups  xmmword ptr [rdi+20h], xmm0
0x18001407e  movaps  xmm0, [rbp+0D0h+var_B0]
0x180014082  movups  xmmword ptr [rdi+30h], xmm1
0x180014086  movaps  xmm1, [rbp+0D0h+var_A0]
0x18001408a  movups  xmmword ptr [rdi+40h], xmm0
0x18001408e  movaps  xmm0, [rbp+0D0h+var_90]
0x180014092  movups  xmmword ptr [rdi+50h], xmm1
0x180014096  movaps  xmm1, [rbp+0D0h+var_80]
0x18001409a  movups  xmmword ptr [rdi+60h], xmm0
0x18001409e  movaps  xmm0, [rbp+0D0h+var_70]
0x1800140a2  movups  xmmword ptr [rdi+70h], xmm1
0x1800140a6  movups  xmmword ptr [rdi+80h], xmm0
0x1800140ad  mov     [rdi+90h], rax
0x1800140b4  call    memset_0
0x1800140b9  test    r12b, 2
0x1800140bd  jz      short loc_1800140EB
0x1800140bf  mov     r8d, [rdi+10h]
0x1800140c3  jmp     short loc_1800140EE
0x1800140c5  mov     r9d, 1
0x1800140cb  mov     eax, 228Dh
0x1800140d0  jmp     short loc_1800140FE
0x1800140d2  mov     [rsp+1D0h+var_170], esi
0x1800140d6  mov     r9d, esi
0x1800140d9  test    esi, esi
0x1800140db  jns     loc_180014049
0x1800140e1  mov     eax, 22AFh
0x1800140e6  jmp     loc_18001403B
0x1800140eb  xor     r8d, r8d
0x1800140ee  mov     edx, r13d
0x1800140f1  call    ?_LaunchScopingForRestorePoint@CSpp@@AEAAJW4_SPP_CREATE_REASON@@K@Z; CSpp::_LaunchScopingForRestorePoint(_SPP_CREATE_REASON,ulong)
0x1800140f6  xor     r9d, r9d
0x1800140f9  mov     eax, 22BBh
0x1800140fe  mov     [rsp+1D0h+var_16C], ax
0x180014103  mov     [rsp+1D0h+var_170], r9d
0x180014108  mov     rcx, [r15+68h]
0x18001410c  test    rcx, rcx
0x18001410f  jz      short loc_180014154
0x180014111  mov     eax, [rbp+0D0h+var_F0.Data1]
0x180014114  mov     edx, 7D0h
0x180014119  movsd   xmm0, qword ptr [rbp+0D0h+var_F0.Data2]
0x18001411e  mov     r8d, 1
0x180014124  mov     dword ptr [rbp+0D0h+var_110], eax
0x180014127  mov     eax, dword ptr [rbp+0D0h+var_F0.Data4+4]
0x18001412a  mov     [rbp+0D0h+var_104], eax
0x18001412d  lea     rax, [rbp+0D0h+var_110]
0x180014131  mov     [rsp+1D0h+var_1B0], rax
0x180014136  movsd   qword ptr [rbp+0D0h+var_110+4], xmm0
0x18001413b  call    ?LogDiagnostic@CSxDiagnostics@@QEAAJW4SX_DIAG_OPERATION@@W4SX_DIAG_TYPE@@JU_GUID@@@Z; CSxDiagnostics::LogDiagnostic(SX_DIAG_OPERATION,SX_DIAG_TYPE,long,_GUID)
0x180014140  jmp     short loc_180014154
0x180014142  mov     [rsp+1D0h+var_170], 8007043Ch
  ... truncated ...
```
