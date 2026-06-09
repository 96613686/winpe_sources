# CSpp::CreateGroupEx(uchar,ulong,ushort const * const *,ulong,_SPP_WRITER_COMPONENT_INFO *,ulong,ushort const * const *,ushort const *,ulong,ulong,uchar *,_GUID *)

- ea: `0x180006730`
- end: `0x180006ce1`
- name: `?CreateGroupEx@CSpp@@UEAAJEKPEBQEBGKPEAU_SPP_WRITER_COMPONENT_INFO@@K0PEBGKKPEAEPEAU_GUID@@@Z`
- size: `1457`
- prototype: `__int64 __fastcall(CSpp *this, unsigned __int8, unsigned int, const unsigned __int16 *const *, unsigned int, struct _SPP_WRITER_COMPONENT_INFO *, unsigned int, unsigned __int16 **, unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *, struct _GUID *)`
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002bb8`
- `0x180006730`
- `0x180007650`
- `0x180008ed0`
- `0x18000e48c`
- `0x18000f888`
- `0x180010514`
- `0x18001176c`
- `0x18001386c`
- `0x1800139e0`
- `0x18001431c`
- `0x18001b1e0`
- `0x18001b668`
- `0x18001b70c`
- `0x18001cbfc`
- `0x18001e3cc`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d00c`
- `0x18002d1e0`
- `0x18002daf0`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `ntdll!RtlGetCurrentTransaction` at `0x180006827`
- `ntdll!RtlGetCurrentTransaction` at `0x180006827`
- `ntdll!RtlSetCurrentTransaction` at `0x180006832`
- `ntdll!RtlSetCurrentTransaction` at `0x180006962`
- `ntdll!RtlSetCurrentTransaction` at `0x180006832`
- `ntdll!RtlSetCurrentTransaction` at `0x180006962`

## string_xrefs

- `0x1800067e8`: `CSpp::CreateGroupEx`

## pseudocode

```c
__int64 __fastcall CSpp::CreateGroupEx(
        CSpp *this,
        unsigned __int8 a2,
        unsigned int a3,
        const unsigned __int16 *const *a4,
        unsigned int a5,
        struct _SPP_WRITER_COMPONENT_INFO *a6,
        unsigned int a7,
        unsigned __int16 **a8,
        unsigned __int16 *a9,
        unsigned int a10,
        unsigned int a11,
        unsigned __int8 *a12,
        struct _GUID *a13)
{
  struct CVolumeEntryMap *v16; // r15
  __int64 CurrentTransaction; // rbx
  int v18; // edx
  OLECHAR *v19; // rcx
  unsigned __int8 *v20; // rcx
  __int64 v21; // rcx
  struct _GUID *v22; // rax
  __int16 v23; // ax
  __int64 v24; // r9
  bool v25; // zf
  __int64 v26; // rcx
  unsigned int v27; // edi
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v31; // rcx
  int v32; // eax
  bool v33; // sf
  CSpp *v34; // rcx
  CSpp *v35; // rcx
  unsigned int v36; // r13d
  int v37; // eax
  int v38; // eax
  struct CVolumeEntryMap **v39; // rdi
  CVolumeEntryMap *v40; // rcx
  int Instance; // eax
  CSpp *v42; // rcx
  int v43; // eax
  int v44; // eax
  CSpp *v45; // rcx
  int v46; // edi
  unsigned int v47; // eax
  int inited; // eax
  CSpp *v49; // rcx
  __int64 v50; // xmm0_8
  int v51; // eax
  unsigned __int8 v53[7]; // [rsp+61h] [rbp-9Fh] BYREF
  int v54; // [rsp+68h] [rbp-98h] BYREF
  __int16 v55; // [rsp+6Ch] [rbp-94h]
  __int16 v56; // [rsp+6Eh] [rbp-92h]
  unsigned int v57; // [rsp+A0h] [rbp-60h]
  unsigned int v58; // [rsp+A4h] [rbp-5Ch]
  int v59; // [rsp+A8h] [rbp-58h]
  struct CVolumeEntryMap *v60; // [rsp+B0h] [rbp-50h] BYREF
  struct _SPP_WRITER_COMPONENT_INFO *v61; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *v62; // [rsp+C0h] [rbp-40h]
  unsigned __int16 **v63; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v64; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v65; // [rsp+D8h] [rbp-28h] BYREF
  GUID v66; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v67; // [rsp+F0h] [rbp-10h] BYREF

  v61 = a6;
  v58 = a7;
  v63 = a8;
  v64 = a9;
  v57 = a11;
  v62 = a12;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v54, "CSpp::CreateGroupEx", 9551, 1);
  v59 = 0;
  v60 = 0;
  v16 = 0;
  v67.Data1 = 0;
  memset_0(&v67.Data2, 0, 0x94u);
  v65 = 0;
  v53[0] = 0;
  CurrentTransaction = RtlGetCurrentTransaction();
  RtlSetCurrentTransaction(0);
  LOBYTE(v18) = a2;
  CSpp::_CreateGroupExTraceInputParams(
    v19,
    v18,
    a3,
    a4,
    a5,
    v61,
    v58,
    (const unsigned __int16 *const *)v63,
    v64,
    a10,
    a11);
  v20 = v62;
  if ( v62 )
    *v62 = 0;
  if ( a13 )
  {
    v21 = 16;
    v22 = a13;
    do
    {
      LOBYTE(v22->Data1) = 0;
      v22 = (struct _GUID *)((char *)v22 + 1);
      --v21;
    }
    while ( v21 );
    v20 = v62;
  }
  v23 = 9572;
  if ( (a10 & 0xFFFFFFE0) != 0 )
    goto LABEL_17;
  v55 = 9572;
  v23 = 9573;
  if ( (v57 & 0xFFFFFFF8) != 0 )
    goto LABEL_17;
  v55 = 9573;
  v23 = 9574;
  if ( !v20 )
    goto LABEL_17;
  v55 = 9574;
  v23 = 9575;
  if ( !a13 )
    goto LABEL_17;
  v55 = 9575;
  if ( !a4 && a3 )
  {
    v23 = 9576;
LABEL_17:
    v24 = 2147942487LL;
LABEL_18:
    v54 = v24;
    goto LABEL_19;
  }
  v55 = 9576;
  if ( !v61 && a5 )
  {
    v23 = 9577;
    goto LABEL_17;
  }
  v55 = 9577;
  if ( !a4 && !v61 && !a2 )
  {
    v23 = 9578;
    goto LABEL_17;
  }
  v54 = 0;
  v55 = 9578;
  if ( (unsigned int)SxIsSafeMode() || (unsigned int)SxIsWinPE() || (unsigned int)SxIsAuditMode() )
  {
    v24 = 2147943484LL;
    v23 = 9580;
    goto LABEL_18;
  }
  v31 = *((_QWORD *)this + 13);
  v54 = 0;
  v55 = 9580;
  if ( v31 )
  {
    v66 = GUID_NULL;
    v32 = CSxDiagnostics::LogDiagnostic(v31, 2000, 0, 0, &v66);
    v24 = (unsigned int)v32;
    v54 = v32;
    v33 = v32 < 0;
    v23 = 9584;
    if ( v33 )
      goto LABEL_19;
    v55 = 9584;
  }
  v59 = 1;
  ATL::CComPtr<IVssBackupComponentsEx3>::operator=((struct IUnknown **)this + 10);
  *((_BYTE *)this + 40) = (unsigned int)CSpp::_IsServerSku(v34) == 0;
  v36 = CSpp::_ModifyBackupFlagForBackupType(v35, a10);
  v37 = CVolumeEntryMap::CreateInstance(&v60);
  v16 = v60;
  v24 = (unsigned int)v37;
  v54 = v37;
  v33 = v37 < 0;
  v23 = 9595;
  if ( !v33 )
  {
    v55 = 9595;
    if ( a4 )
    {
      v38 = CSpp::_AddGoodVolumesToMap(this, a3, a4, v57, v60, v53);
      v24 = (unsigned int)v38;
      v54 = v38;
      v33 = v38 < 0;
      v23 = 9598;
      if ( v33 )
        goto LABEL_19;
      v55 = 9598;
    }
    v39 = (struct CVolumeEntryMap **)((char *)this + 112);
    v40 = (CVolumeEntryMap *)*((_QWORD *)this + 14);
    if ( v40 )
    {
      *v39 = 0;
      CVolumeEntryMap::Release(v40);
    }
    Instance = CVolumeEntryMap::CreateInstance((struct CVolumeEntryMap **)this + 14);
    v24 = (unsigned int)Instance;
    v54 = Instance;
    v33 = Instance < 0;
    v23 = 9601;
    if ( v33 )
      goto LABEL_19;
    v55 = 9601;
    if ( v63 )
    {
      v43 = CSpp::_ConvertVolumeArrayToVolumeMap(v42, v58, (const unsigned __int16 *const *)v63, *v39);
      v24 = (unsigned int)v43;
      v54 = v43;
      v33 = v43 < 0;
      v23 = 9604;
      if ( v33 )
        goto LABEL_19;
      v55 = 9604;
    }
    v44 = CSpp::_BuildCommonSnapshotProp(this, 15, v64, (__int64)&v67);
    v24 = (unsigned int)v44;
    v54 = v44;
    v33 = v44 < 0;
    v23 = 9610;
    if ( !v33 )
    {
      v46 = 0;
      v55 = 9610;
      *((_DWORD *)this + 30) = 0;
      v47 = 0;
      while ( 1 )
      {
        v24 = (unsigned int)v46;
        if ( v47 >= 5 )
          break;
        inited = CSpp::_InitTimer(v45, *((unsigned int *)this + 11), &v65);
        v24 = (unsigned int)inited;
        v54 = inited;
        v33 = inited < 0;
        v23 = 9618;
        if ( v33 )
          goto LABEL_19;
        v55 = 9618;
        v46 = CSpp::_CreateSnapshotSet(this, v16, v65, v36, a2, a5, v61, 0, 0, 0, v57, &v67);
        v24 = (unsigned int)v46;
        if ( v46 >= 0 )
        {
          v54 = v46;
LABEL_60:
          v50 = *(_QWORD *)&v67.Data2;
          v55 = 9640;
          a13->Data1 = v67.Data1;
          v51 = *(_DWORD *)&v67.Data4[4];
          *(_QWORD *)&a13->Data2 = v50;
          *(_DWORD *)&a13->Data4[4] = v51;
          goto LABEL_20;
        }
        if ( (unsigned int)CSpp::_IsRetryableError(v49, &dword_18003BB40, 7u, v46) )
        {
          v24 = (unsigned int)v46;
          v54 = v46;
          v23 = 9637;
          goto LABEL_19;
        }
        v54 = Sleep(0x1388u);
        v24 = (unsigned int)v54;
        if ( v54 < 0 )
        {
          v56 = 9634;
          goto LABEL_20;
        }
        v47 = ++*((_DWORD *)this + 30);
        v55 = 9634;
      }
      v54 = v46;
      if ( v46 >= 0 )
        goto LABEL_60;
      v23 = 9640;
    }
  }
LABEL_19:
  v56 = v23;
LABEL_20:
  v25 = v59 == 0;
  *v62 = *((_BYTE *)this + 41);
  if ( !v25 )
  {
    v26 = *((_QWORD *)this + 13);
    if ( v26 )
    {
      v66 = *a13;
      CSxDiagnostics::LogDiagnostic(v26, 2000, 1, v24, &v66);
    }
  }
  Free_SPP_ONDISK_SNAPSHOT_PROP((struct _SPP_ONDISK_SNAPSHOT_PROP *)&v67);
  v27 = v54;
  RtlSetCurrentTransaction(CurrentTransaction);
  if ( v16 )
    CVolumeEntryMap::Release(v16);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v54, v28, v29);
  return v27;
}

```

## disassembly

```asm
0x180006730  push    rbp
0x180006732  push    rbx
0x180006733  push    rsi
0x180006734  push    rdi
0x180006735  push    r12
0x180006737  push    r13
0x180006739  push    r14
0x18000673b  push    r15
0x18000673d  lea     rbp, [rsp-0A8h]
0x180006745  sub     rsp, 1A8h
0x18000674c  mov     rax, cs:__security_cookie
0x180006753  xor     rax, rsp
0x180006756  mov     [rbp+0E0h+var_50], rax
0x18000675d  mov     rax, [rbp+0E0h+arg_28]
0x180006764  mov     rsi, rcx
0x180006767  mov     rcx, [rbp+0E0h+arg_58]
0x18000676e  mov     rdi, r9
0x180006771  mov     r13d, [rbp+0E0h+arg_50]
0x180006778  mov     r12d, r8d
0x18000677b  mov     r14, [rbp+0E0h+arg_60]
0x180006782  mov     [rbp+0E0h+var_128], rax
0x180006786  mov     eax, [rbp+0E0h+arg_30]
0x18000678c  mov     [rbp+0E0h+var_13C], eax
0x18000678f  mov     rax, [rbp+0E0h+arg_38]
0x180006796  mov     [rbp+0E0h+var_118], rax
0x18000679a  mov     rax, [rbp+0E0h+arg_40]
0x1800067a1  mov     [rbp+0E0h+var_110], rax
0x1800067a5  mov     [rsp+1E0h+var_180], dl
0x1800067a9  mov     [rbp+0E0h+var_140], r13d
0x1800067ad  mov     [rbp+0E0h+var_120], rcx
0x1800067b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067b8  lea     rax, WPP_GLOBAL_Control
0x1800067bf  cmp     rcx, rax
0x1800067c2  jz      short loc_1800067E2
0x1800067c4  test    dword ptr [rcx+1Ch], 20000000h
0x1800067cb  jz      short loc_1800067E2
0x1800067cd  mov     rcx, [rcx+10h]
0x1800067d1  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800067d8  mov     edx, 9Fh
0x1800067dd  call    WPP_SF_
0x1800067e2  mov     r9d, 1; unsigned __int16
0x1800067e8  lea     rdx, aCsppCreategrou_2; "CSpp::CreateGroupEx"
0x1800067ef  mov     r8d, 254Fh; unsigned __int16
0x1800067f5  lea     rcx, [rsp+1E0h+var_178]; this
0x1800067fa  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800067ff  xor     ebx, ebx
0x180006801  lea     rcx, [rbp+0E0h+var_F0.Data2]; void *
0x180006805  xor     edx, edx; Val
0x180006807  mov     [rbp+0E0h+var_138], ebx
0x18000680a  mov     r8d, 94h; Size
0x180006810  mov     [rbp+0E0h+var_130], rbx
0x180006814  mov     r15d, ebx
0x180006817  mov     [rbp+0E0h+var_F0.Data1], ebx
0x18000681a  call    memset_0
0x18000681f  mov     [rbp+0E0h+var_108], rbx
0x180006823  mov     [rsp+1E0h+var_17F], bl
0x180006827  call    cs:__imp_RtlGetCurrentTransaction
0x18000682d  xor     ecx, ecx
0x18000682f  mov     rbx, rax
0x180006832  call    cs:__imp_RtlSetCurrentTransaction
0x180006838  mov     rax, [rbp+0E0h+var_110]
0x18000683c  mov     r9, rdi; unsigned __int16 **
0x18000683f  mov     dl, [rsp+1E0h+var_180]; unsigned __int8
0x180006843  mov     r8d, r12d; unsigned int
0x180006846  mov     [rsp+1E0h+var_190], r13d; unsigned int
0x18000684b  mov     r13d, [rbp+0E0h+arg_48]
0x180006852  mov     [rsp+1E0h+var_198], r13d; unsigned int
0x180006857  mov     [rsp+1E0h+var_1A0], rax; unsigned __int16 *
0x18000685c  mov     rax, [rbp+0E0h+var_118]
0x180006860  mov     [rsp+1E0h+var_1A8], rax; unsigned __int16 **
0x180006865  mov     eax, [rbp+0E0h+var_13C]
0x180006868  mov     dword ptr [rsp+1E0h+var_1B0], eax; unsigned int
0x18000686c  mov     rax, [rbp+0E0h+var_128]
0x180006870  mov     [rsp+1E0h+var_1B8], rax; struct _SPP_WRITER_COMPONENT_INFO *
0x180006875  mov     eax, [rbp+0E0h+arg_20]
0x18000687b  mov     dword ptr [rsp+1E0h+var_1C0], eax; unsigned int
0x18000687f  call    ?_CreateGroupExTraceInputParams@CSpp@@AEAAXEKPEBQEBGKPEAU_SPP_WRITER_COMPONENT_INFO@@K0PEBGKK@Z; CSpp::_CreateGroupExTraceInputParams(uchar,ulong,ushort const * const *,ulong,_SPP_WRITER_COMPONENT_INFO *,ulong,ushort const * const *,ushort const *,ulong,ulong)
0x180006884  mov     rcx, [rbp+0E0h+var_120]
0x180006888  test    rcx, rcx
0x18000688b  jz      short loc_180006890
0x18000688d  mov     [rcx], r15b
0x180006890  test    r14, r14
0x180006893  jz      short loc_1800068AD
0x180006895  mov     ecx, 10h
0x18000689a  mov     rax, r14
0x18000689d  mov     [rax], r15b
0x1800068a0  inc     rax
0x1800068a3  sub     rcx, 1
0x1800068a7  jnz     short loc_18000689D
0x1800068a9  mov     rcx, [rbp+0E0h+var_120]
0x1800068ad  mov     eax, 2564h
0x1800068b2  test    r13d, 0FFFFFFE0h
0x1800068b9  jnz     short loc_180006908
0x1800068bb  test    [rbp+0E0h+var_140], 0FFFFFFF8h
0x1800068c2  mov     [rsp+1E0h+var_174], ax
0x1800068c7  mov     eax, 2565h
0x1800068cc  jnz     short loc_180006908
0x1800068ce  mov     [rsp+1E0h+var_174], ax
0x1800068d3  mov     eax, 2566h
0x1800068d8  test    rcx, rcx
0x1800068db  jz      short loc_180006908
0x1800068dd  mov     [rsp+1E0h+var_174], ax
0x1800068e2  mov     eax, 2567h
0x1800068e7  test    r14, r14
0x1800068ea  jz      short loc_180006908
0x1800068ec  mov     [rsp+1E0h+var_174], ax
0x1800068f1  test    rdi, rdi
0x1800068f4  jnz     loc_1800069A4
0x1800068fa  test    r12d, r12d
0x1800068fd  jz      loc_1800069A4
0x180006903  mov     eax, 2568h
0x180006908  mov     r9d, 80070057h
0x18000690e  mov     [rsp+1E0h+var_178], r9d
0x180006913  mov     [rsp+1E0h+var_172], ax
0x180006918  cmp     [rbp+0E0h+var_138], 0
0x18000691c  mov     rcx, [rbp+0E0h+var_120]
0x180006920  mov     al, [rsi+29h]
0x180006923  mov     [rcx], al
0x180006925  jz      short loc_180006952
0x180006927  mov     rcx, [rsi+68h]
0x18000692b  test    rcx, rcx
0x18000692e  jz      short loc_180006952
0x180006930  movups  xmm0, xmmword ptr [r14]
0x180006934  lea     rax, [rbp+0E0h+var_100]
0x180006938  mov     edx, 7D0h
0x18000693d  mov     r8d, 1
0x180006943  mov     [rsp+1E0h+var_1C0], rax
0x180006948  movdqu  [rbp+0E0h+var_100], xmm0
0x18000694d  call    ?LogDiagnostic@CSxDiagnostics@@QEAAJW4SX_DIAG_OPERATION@@W4SX_DIAG_TYPE@@JU_GUID@@@Z; CSxDiagnostics::LogDiagnostic(SX_DIAG_OPERATION,SX_DIAG_TYPE,long,_GUID)
0x180006952  lea     rcx, [rbp+0E0h+var_F0]; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x180006956  call    ?Free_SPP_ONDISK_SNAPSHOT_PROP@@YAXPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; Free_SPP_ONDISK_SNAPSHOT_PROP(_SPP_ONDISK_SNAPSHOT_PROP *)
0x18000695b  mov     edi, [rsp+1E0h+var_178]
0x18000695f  mov     rcx, rbx
0x180006962  call    cs:__imp_RtlSetCurrentTransaction
0x180006968  test    r15, r15
0x18000696b  jz      short loc_180006975
0x18000696d  mov     rcx, r15; this
0x180006970  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x180006975  lea     rcx, [rsp+1E0h+var_178]; this
0x18000697a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000697f  mov     eax, edi
0x180006981  mov     rcx, [rbp+0E0h+var_50]
0x180006988  xor     rcx, rsp; StackCookie
0x18000698b  call    __security_check_cookie
0x180006990  add     rsp, 1A8h
0x180006997  pop     r15
0x180006999  pop     r14
0x18000699b  pop     r13
0x18000699d  pop     r12
0x18000699f  pop     rdi
0x1800069a0  pop     rsi
0x1800069a1  pop     rbx
0x1800069a2  pop     rbp
0x1800069a3  retn
0x1800069a4  mov     rcx, [rbp+0E0h+var_128]
0x1800069a8  mov     eax, 2568h
0x1800069ad  mov     [rsp+1E0h+var_174], ax
0x1800069b2  test    rcx, rcx
0x1800069b5  jnz     short loc_1800069CA
0x1800069b7  cmp     [rbp+0E0h+arg_20], r15d
0x1800069be  jz      short loc_1800069CA
0x1800069c0  mov     eax, 2569h
0x1800069c5  jmp     loc_180006908
0x1800069ca  mov     eax, 2569h
0x1800069cf  mov     [rsp+1E0h+var_174], ax
0x1800069d4  test    rdi, rdi
0x1800069d7  jnz     short loc_1800069EF
0x1800069d9  test    rcx, rcx
0x1800069dc  jnz     short loc_1800069EF
0x1800069de  cmp     [rsp+1E0h+var_180], r15b
0x1800069e3  jnz     short loc_1800069EF
0x1800069e5  mov     eax, 256Ah
0x1800069ea  jmp     loc_180006908
0x1800069ef  mov     eax, 256Ah
0x1800069f4  mov     [rsp+1E0h+var_178], r15d
0x1800069f9  mov     [rsp+1E0h+var_174], ax
0x1800069fe  call    ?SxIsSafeMode@@YAHXZ; SxIsSafeMode(void)
0x180006a03  test    eax, eax
0x180006a05  jnz     loc_180006CD1
0x180006a0b  call    ?SxIsWinPE@@YAHXZ; SxIsWinPE(void)
0x180006a10  test    eax, eax
0x180006a12  jnz     loc_180006CD1
0x180006a18  call    ?SxIsAuditMode@@YAHXZ; SxIsAuditMode(void)
0x180006a1d  test    eax, eax
0x180006a1f  jnz     loc_180006CD1
0x180006a25  mov     rcx, [rsi+68h]
0x180006a29  mov     eax, 256Ch
0x180006a2e  mov     [rsp+1E0h+var_178], r15d
0x180006a33  mov     [rsp+1E0h+var_174], ax
0x180006a38  test    rcx, rcx
0x180006a3b  jz      short loc_180006A7B
0x180006a3d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180006a44  lea     rax, [rbp+0E0h+var_100]
0x180006a48  xor     r9d, r9d
0x180006a4b  xor     r8d, r8d
0x180006a4e  mov     [rsp+1E0h+var_1C0], rax
0x180006a53  mov     edx, 7D0h
0x180006a58  movdqu  [rbp+0E0h+var_100], xmm0
0x180006a5d  call    ?LogDiagnostic@CSxDiagnostics@@QEAAJW4SX_DIAG_OPERATION@@W4SX_DIAG_TYPE@@JU_GUID@@@Z; CSxDiagnostics::LogDiagnostic(SX_DIAG_OPERATION,SX_DIAG_TYPE,long,_GUID)
0x180006a62  mov     r9d, eax
0x180006a65  mov     [rsp+1E0h+var_178], eax
0x180006a69  test    eax, eax
0x180006a6b  mov     eax, 2570h
0x180006a70  js      loc_180006913
0x180006a76  mov     [rsp+1E0h+var_174], ax
0x180006a7b  lea     rcx, [rsi+50h]
0x180006a7f  mov     [rbp+0E0h+var_138], 1
0x180006a86  call    ??4?$CComPtr@VIVssBackupComponentsEx3@@@ATL@@QEAAPEAVIVssBackupComponentsEx3@@PEAV2@@Z; ATL::CComPtr<IVssBackupComponentsEx3>::operator=(IVssBackupComponentsEx3 *)
0x180006a8b  call    ?_IsServerSku@CSpp@@AEAAJXZ; CSpp::_IsServerSku(void)
0x180006a90  test    eax, eax
0x180006a92  mov     edx, r13d; unsigned int
0x180006a95  setz    al
0x180006a98  mov     [rsi+28h], al
0x180006a9b  call    ?_ModifyBackupFlagForBackupType@CSpp@@AEAAKK@Z; CSpp::_ModifyBackupFlagForBackupType(ulong)
0x180006aa0  lea     rcx, [rbp+0E0h+var_130]; struct CVolumeEntryMap **
0x180006aa4  mov     r13d, eax
0x180006aa7  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x180006aac  mov     r15, [rbp+0E0h+var_130]
0x180006ab0  mov     r9d, eax
0x180006ab3  mov     [rsp+1E0h+var_178], eax
0x180006ab7  test    eax, eax
0x180006ab9  mov     eax, 257Bh
0x180006abe  js      loc_180006913
0x180006ac4  mov     [rsp+1E0h+var_174], ax
0x180006ac9  test    rdi, rdi
0x180006acc  jz      short loc_180006B08
0x180006ace  mov     r9d, [rbp+0E0h+var_140]; unsigned int
0x180006ad2  lea     rax, [rsp+1E0h+var_17F]
0x180006ad7  mov     [rsp+1E0h+var_1B8], rax; unsigned __int8 *
0x180006adc  mov     r8, rdi; unsigned __int16 **
0x180006adf  mov     edx, r12d; unsigned int
0x180006ae2  mov     [rsp+1E0h+var_1C0], r15; struct CVolumeEntryMap *
0x180006ae7  mov     rcx, rsi; this
0x180006aea  call    ?_AddGoodVolumesToMap@CSpp@@AEAAJKPEBQEBGKPEAVCVolumeEntryMap@@PEAE@Z; CSpp::_AddGoodVolumesToMap(ulong,ushort const * const *,ulong,CVolumeEntryMap *,uchar *)
0x180006aef  mov     r9d, eax
0x180006af2  mov     [rsp+1E0h+var_178], eax
0x180006af6  test    eax, eax
0x180006af8  mov     eax, 257Eh
0x180006afd  js      loc_180006913
0x180006b03  mov     [rsp+1E0h+var_174], ax
0x180006b08  lea     rdi, [rsi+70h]
0x180006b0c  mov     rcx, [rdi]; this
0x180006b0f  test    rcx, rcx
0x180006b12  jz      short loc_180006B20
0x180006b14  mov     qword ptr [rdi], 0
0x180006b1b  call    ?Release@CVolumeEntryMap@@QEAAKXZ; CVolumeEntryMap::Release(void)
0x180006b20  mov     rcx, rdi; struct CVolumeEntryMap **
0x180006b23  call    ?CreateInstance@CVolumeEntryMap@@SAJPEAPEAV1@@Z; CVolumeEntryMap::CreateInstance(CVolumeEntryMap * *)
0x180006b28  mov     r9d, eax
0x180006b2b  mov     [rsp+1E0h+var_178], eax
0x180006b2f  test    eax, eax
0x180006b31  mov     eax, 2581h
0x180006b36  js      loc_180006913
0x180006b3c  mov     [rsp+1E0h+var_174], ax
0x180006b41  mov     rax, [rbp+0E0h+var_118]
0x180006b45  test    rax, rax
0x180006b48  jz      short loc_180006B71
0x180006b4a  mov     r9, [rdi]; struct CVolumeEntryMap *
0x180006b4d  mov     r8, rax; unsigned __int16 **
0x180006b50  mov     edx, [rbp+0E0h+var_13C]; unsigned int
0x180006b53  call    ?_ConvertVolumeArrayToVolumeMap@CSpp@@AEAAJKPEBQEBGPEAVCVolumeEntryMap@@@Z; CSpp::_ConvertVolumeArrayToVolumeMap(ulong,ushort const * const *,CVolumeEntryMap *)
0x180006b58  mov     r9d, eax
0x180006b5b  mov     [rsp+1E0h+var_178], eax
0x180006b5f  test    eax, eax
0x180006b61  mov     eax, 2584h
0x180006b66  js      loc_180006913
0x180006b6c  mov     [rsp+1E0h+var_174], ax
0x180006b71  mov     r8, [rbp+0E0h+var_110]
0x180006b75  lea     r9, [rbp+0E0h+var_F0]
0x180006b79  mov     edx, 0Fh
0x180006b7e  mov     rcx, rsi
0x180006b81  call    ?_BuildCommonSnapshotProp@CSpp@@AEAAJW4_SPP_CREATE_REASON@@PEBGPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; CSpp::_BuildCommonSnapshotProp(_SPP_CREATE_REASON,ushort const *,_SPP_ONDISK_SNAPSHOT_PROP *)
0x180006b86  mov     r9d, eax
0x180006b89  mov     [rsp+1E0h+var_178], eax
0x180006b8d  test    eax, eax
0x180006b8f  mov     eax, 258Ah
0x180006b94  js      loc_180006913
0x180006b9a  xor     edi, edi
0x180006b9c  mov     [rsp+1E0h+var_174], ax
0x180006ba1  mov     [rsi+78h], edi
0x180006ba4  xor     eax, eax
0x180006ba6  mov     r12d, 25A2h
0x180006bac  mov     r9d, edi
0x180006baf  cmp     eax, 5
0x180006bb2  jnb     loc_180006CBF
0x180006bb8  mov     edx, [rsi+2Ch]; unsigned int
0x180006bbb  lea     r8, [rbp+0E0h+var_108]; unsigned __int64 *
0x180006bbf  call    ?_InitTimer@CSpp@@AEAAJKPEA_K@Z; CSpp::_InitTimer(ulong,unsigned __int64 *)
0x180006bc4  mov     r9d, eax
0x180006bc7  mov     [rsp+1E0h+var_178], eax
0x180006bcb  test    eax, eax
0x180006bcd  mov     eax, 2592h
0x180006bd2  js      loc_180006913
0x180006bd8  mov     r8, [rbp+0E0h+var_108]; unsigned __int64
0x180006bdc  mov     r9d, r13d; unsigned int
0x180006bdf  mov     [rsp+1E0h+var_174], ax
0x180006be4  mov     rdx, r15; struct CVolumeEntryMap *
0x180006be7  lea     rax, [rbp+0E0h+var_F0]
0x180006beb  mov     rcx, rsi; this
0x180006bee  mov     [rsp+1E0h+var_188], rax; struct _GUID *
  ... truncated ...
```
