# CSpp::_AddInterestingComponents(int,IVssBackupComponents *,CWriterEntryArray *,CVolumeEntryMap *,ulong,_SPP_WRITER_COMPONENT_INFO *,ulong,ulong const *,ulong,ulong,_SPP_ONDISK_SNAPSHOT_PROP *,_SPP_METADATA_PROP *)

- ea: `0x180010e68`
- end: `0x180011192`
- name: `?_AddInterestingComponents@CSpp@@AEAAJHPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@PEAVCVolumeEntryMap@@KPEAU_SPP_WRITER_COMPONENT_INFO@@KPEBKKKPEAU_SPP_ONDISK_SNAPSHOT_PROP@@PEAU_SPP_METADATA_PROP@@@Z`
- size: `810`
- prototype: `__int64 __fastcall(CSpp *this, int, struct IVssBackupComponents *, struct CWriterEntryArray *, struct CVolumeEntryMap *, unsigned int, struct _SPP_WRITER_COMPONENT_INFO *, char, unsigned int *, unsigned int, unsigned int, struct _SPP_ONDISK_SNAPSHOT_PROP *, struct _SPP_METADATA_PROP *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001431c`

## callees

- `0x180010e68`
- `0x180014ef0`
- `0x18001549c`
- `0x180015744`
- `0x180015a28`
- `0x180015d2c`
- `0x180015fcc`
- `0x180016258`
- `0x180016b14`
- `0x18001daa8`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002daf0`

## import_xrefs

- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180010fbf`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x180010fbf`

## string_xrefs

- `0x180010ec8`: `CSpp::_AddInterestingComponents`

## pseudocode

```c
__int64 __fastcall CSpp::_AddInterestingComponents(
        CSpp *this,
        int a2,
        struct IVssBackupComponents *a3,
        struct CWriterEntryArray *a4,
        struct CVolumeEntryMap *a5,
        unsigned int a6,
        struct _SPP_WRITER_COMPONENT_INFO *a7,
        char a8,
        unsigned int *a9,
        unsigned int a10,
        unsigned int a11,
        struct _SPP_ONDISK_SNAPSHOT_PROP *a12,
        struct _SPP_METADATA_PROP *a13)
{
  __int64 v17; // r8
  __int64 v18; // rdx
  __int16 v19; // ax
  int v20; // ebx
  __int64 v22; // rcx
  CSpp *v23; // rcx
  __int16 v24; // ax
  __int64 v25; // rcx
  CSpp *v26; // rcx
  CSpp *v27; // rcx
  CSpp *v28; // rcx
  __int64 v29; // rcx
  int v30[4]; // [rsp+40h] [rbp-61h] BYREF
  GUID v31; // [rsp+50h] [rbp-51h] BYREF
  int v32; // [rsp+60h] [rbp-41h] BYREF
  __int16 v33; // [rsp+64h] [rbp-3Dh]
  __int16 v34; // [rsp+66h] [rbp-3Bh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v32, "CSpp::_AddInterestingComponents", 5746, 1);
  v18 = 0;
  v19 = 5755;
  *(_QWORD *)v30 = 0;
  if ( !a3 )
    goto LABEL_12;
  v33 = 5755;
  v19 = 5756;
  if ( !a4 )
    goto LABEL_12;
  v33 = 5756;
  v19 = 5757;
  if ( !a13 )
    goto LABEL_12;
  v33 = 5757;
  v19 = 5758;
  if ( !a12 )
    goto LABEL_12;
  v33 = 5758;
  if ( !a5 && !a7 && !a2 )
  {
    v19 = 5759;
LABEL_12:
    v20 = -2147024809;
    v32 = -2147024809;
LABEL_13:
    v34 = v19;
    goto LABEL_14;
  }
  v22 = *((_QWORD *)this + 13);
  v32 = 0;
  v33 = 5759;
  if ( v22 )
  {
    v31 = GUID_NULL;
    v20 = CSxDiagnostics::LogDiagnostic(v22, 2004, 0, 0, &v31);
    v32 = v20;
    v19 = 5763;
    if ( v20 < 0 )
      goto LABEL_13;
    v33 = 5763;
  }
  if ( !RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)a5) )
  {
    v20 = CSpp::_DiscoverUnnecessaryComponents(v23, a4, a6, a7, a2);
    v32 = v20;
    v24 = 5771;
    if ( v20 < 0 )
    {
LABEL_20:
      v34 = v24;
      goto LABEL_37;
    }
    v33 = 5771;
  }
  v20 = CSpp::_DiscoverTornComponents(this, a4, a5, a6, a7, a2, a11, a12);
  v32 = v20;
  v24 = 5779;
  if ( v20 < 0 )
    goto LABEL_20;
  v33 = 5779;
  v20 = CSpp::_DiscoverPreviousAttemptsFailedComponents(this, a4);
  v32 = v20;
  v24 = 5781;
  if ( v20 < 0 )
    goto LABEL_20;
  v33 = 5781;
  v25 = 1;
  while ( (_DWORD)v25 )
  {
    v32 = CSpp::_DiscoverAllExcludedComponents((CSpp *)v25, a4);
    v20 = v32;
    if ( v32 < 0 )
    {
      v34 = 5790;
      goto LABEL_37;
    }
    v33 = 5790;
    v32 = CSpp::_DiscoverComponentExcludedDependencies(v26, a4, &v30[1]);
    v20 = v32;
    if ( v32 < 0 )
    {
      v34 = 5797;
      goto LABEL_37;
    }
    v33 = 5797;
    v32 = CSpp::_DiscoverExcludedWriters(v27, a4, a8 & 1, v30);
    v20 = v32;
    if ( v32 < 0 )
    {
      v34 = 5807;
      goto LABEL_37;
    }
    v25 = (unsigned int)(v30[1] | v30[0]);
    v33 = 5807;
  }
  v20 = CSpp::_DiscoverASRExcludedComponents(this, a4, a9, a10);
  v32 = v20;
  v24 = 5817;
  if ( v20 < 0 )
    goto LABEL_20;
  v33 = 5817;
  v20 = CSpp::_DiscoverExplicitlyIncludedComponents(v28, a4);
  v32 = v20;
  v24 = 5824;
  if ( v20 < 0 )
    goto LABEL_20;
  v33 = 5824;
  v20 = CSpp::_SelectExplicitlyIncludedComponents(this, a3, a4, a13);
  v32 = v20;
  v24 = 5829;
  if ( v20 < 0 )
    goto LABEL_20;
  v33 = 5829;
LABEL_37:
  v29 = *((_QWORD *)this + 13);
  if ( v29 )
  {
    v31 = GUID_NULL;
    CSxDiagnostics::LogDiagnostic(v29, 2004, 1, (unsigned int)v20, &v31);
    v20 = v32;
  }
LABEL_14:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v32, v18, v17);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180010e68  mov     [rsp-8+arg_10], r8
0x180010e6d  push    rbp
0x180010e6e  push    rbx
0x180010e6f  push    rsi
0x180010e70  push    rdi
0x180010e71  push    r12
0x180010e73  push    r13
0x180010e75  push    r14
0x180010e77  push    r15
0x180010e79  lea     rbp, [rsp-7]
0x180010e7e  sub     rsp, 0A8h
0x180010e85  mov     rdi, r9
0x180010e88  mov     rbx, r8
0x180010e8b  mov     r12d, edx
0x180010e8e  mov     rsi, rcx
0x180010e91  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e98  lea     rax, WPP_GLOBAL_Control
0x180010e9f  cmp     rcx, rax
0x180010ea2  jz      short loc_180010EC2
0x180010ea4  test    dword ptr [rcx+1Ch], 20000000h
0x180010eab  jz      short loc_180010EC2
0x180010ead  mov     rcx, [rcx+10h]
0x180010eb1  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x180010eb8  mov     edx, 62h ; 'b'
0x180010ebd  call    WPP_SF_
0x180010ec2  mov     r9d, 1; unsigned __int16
0x180010ec8  lea     rdx, aCsppAddinteres; "CSpp::_AddInterestingComponents"
0x180010ecf  mov     r8d, 1672h; unsigned __int16
0x180010ed5  lea     rcx, [rbp+3Fh+var_80]; this
0x180010ed9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180010ede  xor     edx, edx
0x180010ee0  mov     eax, 167Bh
0x180010ee5  mov     [rbp+3Fh+var_A0+4], edx
0x180010ee8  mov     [rbp+3Fh+var_A0], edx
0x180010eeb  test    rbx, rbx
0x180010eee  jz      short loc_180010F45
0x180010ef0  mov     [rbp+3Fh+var_7C], ax
0x180010ef4  mov     eax, 167Ch
0x180010ef9  test    rdi, rdi
0x180010efc  jz      short loc_180010F45
0x180010efe  mov     [rbp+3Fh+var_7C], ax
0x180010f02  mov     eax, 167Dh
0x180010f07  cmp     [rbp+3Fh+arg_60], rdx
0x180010f0e  jz      short loc_180010F45
0x180010f10  mov     r13, [rbp+3Fh+arg_58]
0x180010f17  mov     [rbp+3Fh+var_7C], ax
0x180010f1b  mov     eax, 167Eh
0x180010f20  test    r13, r13
0x180010f23  jz      short loc_180010F45
0x180010f25  mov     r15, [rbp+3Fh+arg_20]
0x180010f29  mov     r14, [rbp+3Fh+arg_30]
0x180010f2d  mov     [rbp+3Fh+var_7C], ax
0x180010f31  test    r15, r15
0x180010f34  jnz     short loc_180010F70
0x180010f36  test    r14, r14
0x180010f39  jnz     short loc_180010F70
0x180010f3b  test    r12d, r12d
0x180010f3e  jnz     short loc_180010F70
0x180010f40  mov     eax, 167Fh
0x180010f45  mov     ebx, 80070057h
0x180010f4a  mov     [rbp+3Fh+var_80], ebx
0x180010f4d  mov     [rbp+3Fh+var_7A], ax
0x180010f51  lea     rcx, [rbp+3Fh+var_80]; this
0x180010f55  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180010f5a  mov     eax, ebx
0x180010f5c  add     rsp, 0A8h
0x180010f63  pop     r15
0x180010f65  pop     r14
0x180010f67  pop     r13
0x180010f69  pop     r12
0x180010f6b  pop     rdi
0x180010f6c  pop     rsi
0x180010f6d  pop     rbx
0x180010f6e  pop     rbp
0x180010f6f  retn
0x180010f70  mov     rcx, [rsi+68h]
0x180010f74  mov     eax, 167Fh
0x180010f79  mov     [rbp+3Fh+var_80], edx
0x180010f7c  mov     [rbp+3Fh+var_7C], ax
0x180010f80  test    rcx, rcx
0x180010f83  jz      short loc_180010FBC
0x180010f85  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180010f8c  lea     rax, [rbp+3Fh+var_90]
0x180010f90  xor     r9d, r9d
0x180010f93  xor     r8d, r8d
0x180010f96  mov     [rsp+0E0h+var_C0], rax
0x180010f9b  mov     edx, 7D4h
0x180010fa0  movdqu  [rbp+3Fh+var_90], xmm0
0x180010fa5  call    ?LogDiagnostic@CSxDiagnostics@@QEAAJW4SX_DIAG_OPERATION@@W4SX_DIAG_TYPE@@JU_GUID@@@Z; CSxDiagnostics::LogDiagnostic(SX_DIAG_OPERATION,SX_DIAG_TYPE,long,_GUID)
0x180010faa  mov     ebx, eax
0x180010fac  mov     [rbp+3Fh+var_80], eax
0x180010faf  test    eax, eax
0x180010fb1  mov     eax, 1683h
0x180010fb6  js      short loc_180010F4D
0x180010fb8  mov     [rbp+3Fh+var_7C], ax
0x180010fbc  mov     rcx, [r15]; Table
0x180010fbf  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180010fc5  test    eax, eax
0x180010fc7  jnz     short loc_180010FF8
0x180010fc9  mov     r8d, [rbp+3Fh+arg_28]; unsigned int
0x180010fcd  mov     r9, r14; struct _SPP_WRITER_COMPONENT_INFO *
0x180010fd0  mov     rdx, rdi; struct CWriterEntryArray *
0x180010fd3  mov     dword ptr [rsp+0E0h+var_C0], r12d; int
0x180010fd8  call    ?_DiscoverUnnecessaryComponents@CSpp@@AEAAJPEAVCWriterEntryArray@@KPEAU_SPP_WRITER_COMPONENT_INFO@@H@Z; CSpp::_DiscoverUnnecessaryComponents(CWriterEntryArray *,ulong,_SPP_WRITER_COMPONENT_INFO *,int)
0x180010fdd  mov     ebx, eax
0x180010fdf  mov     [rbp+3Fh+var_80], eax
0x180010fe2  test    eax, eax
0x180010fe4  mov     eax, 168Bh
0x180010fe9  jns     short loc_180010FF4
0x180010feb  mov     [rbp+3Fh+var_7A], ax
0x180010fef  jmp     loc_180011155
0x180010ff4  mov     [rbp+3Fh+var_7C], ax
0x180010ff8  mov     eax, [rbp+3Fh+arg_50]
0x180010ffe  mov     r8, r15; struct CVolumeEntryMap *
0x180011001  mov     r9d, [rbp+3Fh+arg_28]; unsigned int
0x180011005  mov     rdx, rdi; struct CWriterEntryArray *
0x180011008  mov     [rsp+0E0h+var_A8], r13; struct _SPP_ONDISK_SNAPSHOT_PROP *
0x18001100d  mov     rcx, rsi; this
0x180011010  mov     [rsp+0E0h+var_B0], eax; unsigned int
0x180011014  mov     [rsp+0E0h+var_B8], r12d; int
0x180011019  mov     [rsp+0E0h+var_C0], r14; struct _SPP_WRITER_COMPONENT_INFO *
0x18001101e  call    ?_DiscoverTornComponents@CSpp@@AEAAJPEAVCWriterEntryArray@@PEAVCVolumeEntryMap@@KPEAU_SPP_WRITER_COMPONENT_INFO@@HKPEAU_SPP_ONDISK_SNAPSHOT_PROP@@@Z; CSpp::_DiscoverTornComponents(CWriterEntryArray *,CVolumeEntryMap *,ulong,_SPP_WRITER_COMPONENT_INFO *,int,ulong,_SPP_ONDISK_SNAPSHOT_PROP *)
0x180011023  mov     ebx, eax
0x180011025  mov     [rbp+3Fh+var_80], eax
0x180011028  test    eax, eax
0x18001102a  mov     eax, 1693h
0x18001102f  js      short loc_180010FEB
0x180011031  mov     rdx, rdi; struct CWriterEntryArray *
0x180011034  mov     [rbp+3Fh+var_7C], ax
0x180011038  mov     rcx, rsi; this
0x18001103b  call    ?_DiscoverPreviousAttemptsFailedComponents@CSpp@@AEAAJPEAVCWriterEntryArray@@@Z; CSpp::_DiscoverPreviousAttemptsFailedComponents(CWriterEntryArray *)
0x180011040  mov     ebx, eax
0x180011042  mov     [rbp+3Fh+var_80], eax
0x180011045  test    eax, eax
0x180011047  mov     eax, 1695h
0x18001104c  js      short loc_180010FEB
0x18001104e  mov     r14d, dword ptr [rbp+3Fh+arg_38]
0x180011055  lea     r12d, [rax+9]
0x180011059  and     r14d, 1
0x18001105d  mov     [rbp+3Fh+var_7C], ax
0x180011061  mov     ecx, 1; this
0x180011066  lea     r13d, [rax+10h]
0x18001106a  lea     r15d, [rax+1Ah]
0x18001106e  mov     rdx, rdi; struct CWriterEntryArray *
0x180011071  test    ecx, ecx
0x180011073  jz      short loc_1800110DF
0x180011075  call    ?_DiscoverAllExcludedComponents@CSpp@@AEAAJPEAVCWriterEntryArray@@@Z; CSpp::_DiscoverAllExcludedComponents(CWriterEntryArray *)
0x18001107a  mov     [rbp+3Fh+var_80], eax
0x18001107d  mov     ebx, eax
0x18001107f  test    eax, eax
0x180011081  js      short loc_1800110D8
0x180011083  lea     r8, [rbp+3Fh+var_A0+4]; int *
0x180011087  mov     [rbp+3Fh+var_7C], r12w
0x18001108c  mov     rdx, rdi; struct CWriterEntryArray *
0x18001108f  call    ?_DiscoverComponentExcludedDependencies@CSpp@@AEAAJPEAVCWriterEntryArray@@PEAH@Z; CSpp::_DiscoverComponentExcludedDependencies(CWriterEntryArray *,int *)
0x180011094  mov     [rbp+3Fh+var_80], eax
0x180011097  mov     ebx, eax
0x180011099  test    eax, eax
0x18001109b  js      short loc_1800110D1
0x18001109d  lea     r9, [rbp+3Fh+var_A0]; int *
0x1800110a1  mov     [rbp+3Fh+var_7C], r13w
0x1800110a6  mov     r8d, r14d; int
0x1800110a9  mov     rdx, rdi; struct CWriterEntryArray *
0x1800110ac  call    ?_DiscoverExcludedWriters@CSpp@@AEAAJPEAVCWriterEntryArray@@HPEAH@Z; CSpp::_DiscoverExcludedWriters(CWriterEntryArray *,int,int *)
0x1800110b1  mov     [rbp+3Fh+var_80], eax
0x1800110b4  mov     ebx, eax
0x1800110b6  test    eax, eax
0x1800110b8  js      short loc_1800110C7
0x1800110ba  mov     ecx, [rbp+3Fh+var_A0]
0x1800110bd  or      ecx, [rbp+3Fh+var_A0+4]
0x1800110c0  mov     [rbp+3Fh+var_7C], r15w
0x1800110c5  jmp     short loc_18001106E
0x1800110c7  mov     [rbp+3Fh+var_7A], r15w
0x1800110cc  jmp     loc_180011155
0x1800110d1  mov     [rbp+3Fh+var_7A], r13w
0x1800110d6  jmp     short loc_180011155
0x1800110d8  mov     [rbp+3Fh+var_7A], r12w
0x1800110dd  jmp     short loc_180011155
0x1800110df  mov     r9d, [rbp+3Fh+arg_48]; unsigned int
0x1800110e6  mov     rcx, rsi; this
0x1800110e9  mov     r8, [rbp+3Fh+arg_40]; unsigned int *
0x1800110f0  call    ?_DiscoverASRExcludedComponents@CSpp@@AEAAJPEAVCWriterEntryArray@@PEBKK@Z; CSpp::_DiscoverASRExcludedComponents(CWriterEntryArray *,ulong const *,ulong)
0x1800110f5  mov     ebx, eax
0x1800110f7  mov     [rbp+3Fh+var_80], eax
0x1800110fa  test    eax, eax
0x1800110fc  mov     eax, 16B9h
0x180011101  js      loc_180010FEB
0x180011107  mov     rdx, rdi; struct CWriterEntryArray *
0x18001110a  mov     [rbp+3Fh+var_7C], ax
0x18001110e  call    ?_DiscoverExplicitlyIncludedComponents@CSpp@@AEAAJPEAVCWriterEntryArray@@@Z; CSpp::_DiscoverExplicitlyIncludedComponents(CWriterEntryArray *)
0x180011113  mov     ebx, eax
0x180011115  mov     [rbp+3Fh+var_80], eax
0x180011118  test    eax, eax
0x18001111a  mov     eax, 16C0h
0x18001111f  js      loc_180010FEB
0x180011125  mov     r9, [rbp+3Fh+arg_60]; struct _SPP_METADATA_PROP *
0x18001112c  mov     r8, rdi; struct CWriterEntryArray *
0x18001112f  mov     rdx, [rbp+3Fh+arg_10]; struct IVssBackupComponents *
0x180011133  mov     rcx, rsi; this
0x180011136  mov     [rbp+3Fh+var_7C], ax
0x18001113a  call    ?_SelectExplicitlyIncludedComponents@CSpp@@AEAAJPEAVIVssBackupComponents@@PEAVCWriterEntryArray@@PEAU_SPP_METADATA_PROP@@@Z; CSpp::_SelectExplicitlyIncludedComponents(IVssBackupComponents *,CWriterEntryArray *,_SPP_METADATA_PROP *)
0x18001113f  mov     ebx, eax
0x180011141  mov     [rbp+3Fh+var_80], eax
0x180011144  test    eax, eax
0x180011146  mov     eax, 16C5h
0x18001114b  js      loc_180010FEB
0x180011151  mov     [rbp+3Fh+var_7C], ax
0x180011155  mov     rcx, [rsi+68h]
0x180011159  test    rcx, rcx
0x18001115c  jz      loc_180010F51
0x180011162  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180011169  lea     rax, [rbp+3Fh+var_90]
0x18001116d  mov     r9d, ebx
0x180011170  mov     edx, 7D4h
0x180011175  mov     [rsp+0E0h+var_C0], rax
0x18001117a  mov     r8d, 1
0x180011180  movdqu  [rbp+3Fh+var_90], xmm0
0x180011185  call    ?LogDiagnostic@CSxDiagnostics@@QEAAJW4SX_DIAG_OPERATION@@W4SX_DIAG_TYPE@@JU_GUID@@@Z; CSxDiagnostics::LogDiagnostic(SX_DIAG_OPERATION,SX_DIAG_TYPE,long,_GUID)
0x18001118a  mov     ebx, [rbp+3Fh+var_80]
0x18001118d  jmp     loc_180010F51
```
