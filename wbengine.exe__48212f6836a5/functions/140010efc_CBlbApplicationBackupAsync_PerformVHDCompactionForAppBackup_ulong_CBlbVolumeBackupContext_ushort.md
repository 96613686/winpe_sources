# CBlbApplicationBackupAsync::PerformVHDCompactionForAppBackup(ulong,CBlbVolumeBackupContext *,ushort *)

- ea: `0x140010efc`
- end: `0x1400115ea`
- name: `?PerformVHDCompactionForAppBackup@CBlbApplicationBackupAsync@@AEAAJKPEAVCBlbVolumeBackupContext@@PEAG@Z`
- size: `1774`
- prototype: `__int64 __fastcall(CBlbApplicationBackupAsync *__hidden this, unsigned int, struct CBlbVolumeBackupContext *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002dfa8`

## callees

- `0x140006ca8`
- `0x140008ac8`
- `0x14000aee8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140010efc`
- `0x1400130fc`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x14002d79c`
- `0x14003469c`
- `0x1400889f0`
- `0x140088ba4`
- `0x140088d0c`
- `0x14008b7d4`
- `0x1400ff774`
- `0x140108018`
- `0x1401087ac`
- `0x140109304`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14001104a`
- `ole32!CoTaskMemFree` at `0x1400111da`
- `ole32!CoTaskMemFree` at `0x140011214`
- `ole32!CoTaskMemFree` at `0x140011328`
- `ole32!CoTaskMemFree` at `0x14001133d`
- `ole32!CoTaskMemFree` at `0x140011351`
- `ole32!CoTaskMemFree` at `0x140011485`
- `ole32!CoTaskMemFree` at `0x14001149a`
- `ole32!CoTaskMemFree` at `0x1400114af`
- `ole32!CoTaskMemFree` at `0x14001104a`
- `ole32!CoTaskMemFree` at `0x1400111da`
- `ole32!CoTaskMemFree` at `0x140011214`
- `ole32!CoTaskMemFree` at `0x140011328`
- `ole32!CoTaskMemFree` at `0x14001133d`
- `ole32!CoTaskMemFree` at `0x140011351`
- `ole32!CoTaskMemFree` at `0x140011485`
- `ole32!CoTaskMemFree` at `0x14001149a`
- `ole32!CoTaskMemFree` at `0x1400114af`

## pseudocode

```c
__int64 __fastcall CBlbApplicationBackupAsync::PerformVHDCompactionForAppBackup(
        CBlbApplicationBackupAsync *this,
        unsigned int a2,
        struct CBlbVolumeBackupContext *a3,
        unsigned __int16 *a4)
{
  PVOID *v5; // rcx
  int v6; // eax
  unsigned __int16 *v7; // r13
  WCHAR *v8; // rsi
  unsigned __int16 *v9; // r12
  int VolumeAccessPath; // edi
  unsigned int v11; // edx
  __int64 v12; // rax
  __int64 v13; // r12
  __int64 v14; // r15
  __int64 v15; // r14
  __int64 v16; // rdx
  __int64 v17; // rax
  void *v18; // rcx
  unsigned int j; // r14d
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  unsigned __int8 v23; // r12
  const wchar_t *v24; // r9
  __int64 v25; // r12
  int v26; // eax
  void *v27; // rcx
  __int64 v28; // rdx
  struct CBlbVolumeBackupContext *v29; // rsi
  __int64 v30; // rdi
  void *v31; // rcx
  struct _GUID v32; // xmm0
  unsigned int v33; // edx
  int v34; // eax
  LPVOID *v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  int v41; // [rsp+30h] [rbp-48h]
  unsigned int i; // [rsp+34h] [rbp-44h]
  unsigned __int16 *v43; // [rsp+38h] [rbp-40h] BYREF
  __int64 v44; // [rsp+40h] [rbp-38h]
  PCWSTR Path; // [rsp+48h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-28h] BYREF
  struct _GUID Buf1; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int8 v48; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int v49; // [rsp+C8h] [rbp+50h]
  struct CBlbVolumeBackupContext *v50; // [rsp+D0h] [rbp+58h]
  unsigned __int16 *v51; // [rsp+D8h] [rbp+60h]

  v51 = a4;
  v50 = a3;
  v49 = a2;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = *((_DWORD *)this + 72);
  v7 = 0;
  v8 = 0;
  pv = 0;
  v9 = 0;
  Path = 0;
  v43 = 0;
  VolumeAccessPath = 0;
  if ( (unsigned int)(v6 - 4) <= 1 && *((_DWORD *)this + 74) != -2139618978 )
    goto LABEL_84;
  v11 = *((_DWORD *)this + 78);
  v12 = 0;
  for ( i = v11; ; v11 = i )
  {
    v41 = v12;
    if ( (unsigned int)v12 >= *((_DWORD *)this + 55) )
      goto LABEL_84;
    v13 = *((_QWORD *)this + 28);
    v14 = 96 * v12;
    v15 = 0;
    v44 = v13;
    while ( (unsigned int)v15 < v11 )
    {
      if ( (unsigned __int64)(unsigned int)v15 >= *((_QWORD *)this + 39) )
      {
        BlbAssert("onecore\\external\\sdk\\inc\\atlmfc\\atlcoll.h", 0x2CFu, "iElement < m_nSize");
        if ( (unsigned __int64)(unsigned int)v15 >= *((_QWORD *)this + 39) )
          ATL::AtlThrowImpl(-2147024809);
      }
      v13 = v44;
      v16 = 368LL * *(unsigned int *)(*((_QWORD *)this + 38) + 4 * v15);
      v17 = *(_QWORD *)(v14 + v44) - *(_QWORD *)((char *)v50 + v16 + 68);
      if ( !v17 )
        v17 = *(_QWORD *)(v14 + v44 + 8) - *(_QWORD *)((char *)v50 + v16 + 76);
      if ( !v17 )
        goto LABEL_58;
      v11 = i;
      v15 = (unsigned int)(v15 + 1);
    }
    if ( (_DWORD)v15 != v11 )
    {
LABEL_58:
      v9 = v43;
      goto LABEL_59;
    }
    v18 = (void *)*((_QWORD *)this + 55);
    if ( v18 )
    {
      CoTaskMemFree(v18);
      *((_QWORD *)this + 55) = 0;
    }
    VolumeAccessPath = BlbutilQueryVolumeAccessPath(*(LPCWSTR *)(v14 + v13 + 16), (unsigned __int16 **)this + 55);
    if ( VolumeAccessPath < 0 )
      goto LABEL_82;
    if ( *((_DWORD *)this + 72) != 5 )
      CBlbApplicationBackupAsync::SetState(this, 3);
    for ( j = 0; j < v49; ++j )
    {
      v20 = 368LL * j;
      v21 = *(_QWORD *)(v14 + v13) - *(_QWORD *)((char *)v50 + v20 + 68);
      if ( !v21 )
        v21 = *(_QWORD *)(v14 + v13 + 8) - *(_QWORD *)((char *)v50 + v20 + 76);
      if ( !v21 )
        break;
    }
    v22 = *((_QWORD *)this + 28);
    v48 = 0;
    VolumeAccessPath = CBlbVhdHelper::IsCompactionRequired(*(unsigned __int16 **)(v14 + v22 + 80), &v48);
    if ( VolumeAccessPath < 0 )
    {
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v39 = 144;
LABEL_114:
        WPP_SF_d(v38[2], v39, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
      }
LABEL_115:
      CBlbApplicationBackupAsync::SetState(this, 5);
      v37 = 2155348305LL;
LABEL_102:
      (*(void (__fastcall **)(CBlbApplicationBackupAsync *, __int64, _QWORD))(*(_QWORD *)this + 64LL))(
        this,
        v37,
        (unsigned int)VolumeAccessPath);
      goto LABEL_108;
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v23 = v48;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v24 = L"TRUE";
      if ( !v48 )
        v24 = (const wchar_t *)L"FALSE";
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids, v24);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !v23 )
      break;
    CBlbBackupAsync::ResetCompactionStatus(
      *((CBlbBackupAsync **)this + 30),
      (struct _GUID *)(v14 + *((_QWORD *)this + 28)));
    v25 = v14 + v44;
    VolumeAccessPath = BlbutilRemoveTrailingBackslash(
                         *(const unsigned __int16 **)(v14 + v44 + 80),
                         (unsigned __int16 **)&pv);
    if ( VolumeAccessPath < 0 )
    {
      v7 = (unsigned __int16 *)pv;
      goto LABEL_82;
    }
    v7 = (unsigned __int16 *)pv;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        147,
        (unsigned int)WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids,
        (_DWORD)pv,
        *(_QWORD *)(v14 + v44 + 16));
    }
    v26 = CBlbVhdHelper::Dismount(v7);
    VolumeAccessPath = v26;
    if ( v26 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          148,
          (unsigned int)WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids,
          (_DWORD)v7,
          v26);
      }
      CBlbApplicationBackupAsync::SetState(this, 5);
      v37 = 2155348300LL;
      goto LABEL_102;
    }
    v27 = *(void **)(v25 + 80);
    if ( v27 )
    {
      CoTaskMemFree(v27);
      *(_QWORD *)(v25 + 80) = 0;
    }
    v28 = v44;
    *(_BYTE *)(v14 + v44 + 44) = 0;
    if ( j < v49 )
    {
      v29 = v50;
      v30 = 368LL * j;
      v31 = *(void **)((char *)v50 + v30 + 224);
      if ( v31 )
      {
        CoTaskMemFree(v31);
        v28 = v44;
        *(_QWORD *)((char *)v29 + v30 + 224) = 0;
      }
      *((_BYTE *)v29 + v30 + 346) = 1;
    }
    v32 = *(struct _GUID *)(v14 + v28);
    v33 = *(_DWORD *)(v14 + v28 + 40);
    Buf1 = v32;
    VolumeAccessPath = BlbGetVhdPath(&Buf1, v33, v51, (unsigned __int16 **)&Path);
    if ( VolumeAccessPath < 0 )
    {
      v8 = (WCHAR *)Path;
LABEL_82:
      v9 = v43;
LABEL_83:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_84;
    }
    if ( !CBlbAsync::CheckPoint((CBlbAsync *)(*((_QWORD *)this + 30) + 24LL)) )
    {
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        v8 = (WCHAR *)Path;
        goto LABEL_109;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
      v8 = (WCHAR *)Path;
      goto LABEL_108;
    }
    v8 = (WCHAR *)Path;
    VolumeAccessPath = CBlbVhdHelper::CompactVHD(
                         (struct CBlbImpersonationHelper *)(*((_QWORD *)this + 30) + 40LL),
                         Path,
                         (unsigned __int8 (*)(void *, __int64, __int64))BlbPerformCompactionCallback,
                         *((void **)this + 30));
    if ( VolumeAccessPath < 0 )
    {
      v38 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v39 = 150;
        goto LABEL_114;
      }
      goto LABEL_115;
    }
    v34 = CBlbBackupAsync::MountVHD(*((CBlbBackupAsync **)this + 30), v8, &v43);
    VolumeAccessPath = v34;
    if ( v34 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          151,
          (unsigned int)WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids,
          (_DWORD)v8,
          v34);
      }
      CBlbApplicationBackupAsync::SetState(this, 5);
      v37 = 2155348228LL;
      goto LABEL_102;
    }
    v35 = (LPVOID *)(v25 + 80);
    v9 = v43;
    VolumeAccessPath = BlbutilSlashTerminatePath(v43, v35);
    if ( VolumeAccessPath < 0 )
      goto LABEL_83;
    if ( j == v49 || (v36 = 368LL * j, (*((_BYTE *)v50 + v36 + 84) & 8) != 0) )
    {
      *(_BYTE *)(v14 + v44 + 44) = 1;
    }
    else
    {
      VolumeAccessPath = BlbutilDuplicateString(v9, (unsigned __int16 **)((char *)v50 + v36 + 224), 0);
      if ( VolumeAccessPath < 0 )
        goto LABEL_83;
    }
LABEL_59:
    if ( v7 )
    {
      CoTaskMemFree(v7);
      v7 = 0;
      pv = 0;
    }
    if ( v8 )
    {
      CoTaskMemFree(v8);
      v8 = 0;
      Path = 0;
    }
    if ( v9 )
    {
      CoTaskMemFree(v9);
      v9 = 0;
      v43 = 0;
    }
    v5 = (PVOID *)WPP_GLOBAL_Control;
    v12 = (unsigned int)(v41 + 1);
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
  {
    WPP_SF_(v5[2], 146, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
LABEL_108:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_109:
  v9 = v43;
LABEL_84:
  if ( *((_DWORD *)this + 72) != 5 )
  {
    CBlbApplicationBackupAsync::SetState(this, 4);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    CoTaskMemFree(v7);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    CoTaskMemFree(v8);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    CoTaskMemFree(v9);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
    WPP_SF_(v5[2], 152, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids);
  return (unsigned int)VolumeAccessPath;
}

```

## disassembly

```asm
0x140010efc  mov     [rsp-40h+arg_18], r9
0x140010f01  mov     [rsp-40h+arg_10], r8
0x140010f06  mov     [rsp-40h+arg_8], edx
0x140010f0a  push    rbp
0x140010f0b  push    rbx
0x140010f0c  push    rsi
0x140010f0d  push    rdi
0x140010f0e  push    r12
0x140010f10  push    r13
0x140010f12  push    r14
0x140010f14  push    r15
0x140010f16  mov     rbp, rsp
0x140010f19  sub     rsp, 78h
0x140010f1d  mov     rbx, rcx
0x140010f20  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f27  lea     r14, WPP_GLOBAL_Control
0x140010f2e  cmp     rcx, r14
0x140010f31  jz      short loc_140010F5B
0x140010f33  test    byte ptr [rcx+1Ch], 1
0x140010f37  jz      short loc_140010F5B
0x140010f39  cmp     byte ptr [rcx+19h], 4
0x140010f3d  jb      short loc_140010F5B
0x140010f3f  mov     rcx, [rcx+10h]
0x140010f43  lea     r8, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids
0x140010f4a  mov     edx, 8Fh
0x140010f4f  call    WPP_SF_
0x140010f54  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f5b  mov     eax, [rbx+120h]
0x140010f61  xor     r13d, r13d
0x140010f64  xor     esi, esi
0x140010f66  mov     [rbp+pv], r13
0x140010f6a  xor     r12d, r12d
0x140010f6d  mov     [rbp+Path], rsi
0x140010f71  sub     eax, 4
0x140010f74  mov     [rbp+var_40], r12
0x140010f78  xor     edi, edi
0x140010f7a  cmp     eax, 1
0x140010f7d  ja      short loc_140010F8F
0x140010f7f  cmp     dword ptr [rbx+128h], 8078015Eh
0x140010f89  jnz     loc_140011460
0x140010f8f  mov     edx, [rbx+138h]
0x140010f95  xor     eax, eax
0x140010f97  mov     [rbp+var_44], edx
0x140010f9a  mov     [rbp+var_48], eax
0x140010f9d  cmp     eax, [rbx+0DCh]
0x140010fa3  jnb     loc_140011459
0x140010fa9  mov     r12, [rbx+0E0h]
0x140010fb0  lea     r15, [rax+rax*2]
0x140010fb4  shl     r15, 5
0x140010fb8  xor     r14d, r14d
0x140010fbb  mov     [rbp+var_38], r12
0x140010fbf  cmp     r14d, edx
0x140010fc2  jnb     short loc_140011035
0x140010fc4  mov     r12d, r14d
0x140010fc7  cmp     r12, [rbx+138h]
0x140010fce  jb      short loc_140010FF5
0x140010fd0  lea     r8, aIelementMNsize; "iElement < m_nSize"
0x140010fd7  mov     edx, 2CFh; unsigned int
0x140010fdc  lea     rcx, aOnecoreExterna_11; "onecore\\external\\sdk\\inc\\atlmfc\\at"...
0x140010fe3  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140010fe8  cmp     r12, [rbx+138h]
0x140010fef  jnb     loc_140011372
0x140010ff5  mov     rax, [rbx+130h]
0x140010ffc  mov     r12, [rbp+var_38]
0x140011000  mov     r8, [rbp+arg_10]
0x140011004  mov     ecx, [rax+r14*4]
0x140011008  mov     rax, [r15+r12]
0x14001100c  imul    rdx, rcx, 170h
0x140011013  sub     rax, [rdx+r8+44h]
0x140011018  jnz     short loc_140011024
0x14001101a  mov     rax, [r15+r12+8]
0x14001101f  sub     rax, [rdx+r8+4Ch]
0x140011024  test    rax, rax
0x140011027  jz      loc_14001131C
0x14001102d  mov     edx, [rbp+var_44]
0x140011030  inc     r14d
0x140011033  jmp     short loc_140010FBF
0x140011035  jnz     loc_14001131C
0x14001103b  lea     rdi, [rbx+1B8h]
0x140011042  mov     rcx, [rdi]; pv
0x140011045  test    rcx, rcx
0x140011048  jz      short loc_140011057
0x14001104a  call    cs:__imp_CoTaskMemFree
0x140011050  mov     qword ptr [rdi], 0
0x140011057  mov     rcx, [r15+r12+10h]; lpszVolumeName
0x14001105c  mov     rdx, rdi; unsigned __int16 **
0x14001105f  call    ?BlbutilQueryVolumeAccessPath@@YAJPEAGPEAPEAG@Z; BlbutilQueryVolumeAccessPath(ushort *,ushort * *)
0x140011064  mov     edi, eax
0x140011066  test    eax, eax
0x140011068  js      loc_14001144E
0x14001106e  cmp     dword ptr [rbx+120h], 5
0x140011075  jz      short loc_140011084
0x140011077  mov     edx, 3
0x14001107c  mov     rcx, rbx
0x14001107f  call    ?SetState@CBlbApplicationBackupAsync@@QEAAXW4BLB_APPLICATION_BACKUP_STATE@@@Z; CBlbApplicationBackupAsync::SetState(BLB_APPLICATION_BACKUP_STATE)
0x140011084  mov     r8d, [rbp+arg_8]
0x140011088  xor     r14d, r14d
0x14001108b  test    r8d, r8d
0x14001108e  jz      short loc_1400110C0
0x140011090  mov     rdx, [rbp+arg_10]
0x140011094  mov     eax, r14d
0x140011097  imul    rcx, rax, 170h
0x14001109e  mov     rax, [r15+r12]
0x1400110a2  sub     rax, [rcx+rdx+44h]
0x1400110a7  jnz     short loc_1400110B3
0x1400110a9  mov     rax, [r15+r12+8]
0x1400110ae  sub     rax, [rcx+rdx+4Ch]
0x1400110b3  test    rax, rax
0x1400110b6  jz      short loc_1400110C0
0x1400110b8  inc     r14d
0x1400110bb  cmp     r14d, r8d
0x1400110be  jb      short loc_140011094
0x1400110c0  mov     rcx, [rbx+0E0h]
0x1400110c7  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x1400110cb  mov     [rbp+arg_0], 0
0x1400110cf  mov     rcx, [r15+rcx+50h]; unsigned __int16 *
0x1400110d4  call    ?IsCompactionRequired@CBlbVhdHelper@@SAJPEAGPEAE@Z; CBlbVhdHelper::IsCompactionRequired(ushort *,uchar *)
0x1400110d9  mov     edi, eax
0x1400110db  test    eax, eax
0x1400110dd  js      loc_14001159C
0x1400110e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400110ea  lea     rax, WPP_GLOBAL_Control
0x1400110f1  mov     r12b, [rbp+arg_0]
0x1400110f5  cmp     rcx, rax
0x1400110f8  jz      short loc_140011137
0x1400110fa  test    byte ptr [rcx+1Ch], 1
0x1400110fe  jz      short loc_140011137
0x140011100  cmp     byte ptr [rcx+19h], 4
0x140011104  jb      short loc_140011137
0x140011106  mov     rcx, [rcx+10h]
0x14001110a  lea     rax, aFalse_2; "FALSE"
0x140011111  test    r12b, r12b
0x140011114  lea     r9, aTrue_1; "TRUE"
0x14001111b  mov     edx, 91h
0x140011120  lea     r8, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids
0x140011127  cmovz   r9, rax
0x14001112b  call    WPP_SF_S
0x140011130  mov     rcx, cs:WPP_GLOBAL_Control
0x140011137  test    r12b, r12b
0x14001113a  jz      loc_14001155F
0x140011140  mov     rdx, [rbx+0E0h]
0x140011147  mov     rcx, [rbx+0F0h]; this
0x14001114e  add     rdx, r15; struct _GUID *
0x140011151  call    ?ResetCompactionStatus@CBlbBackupAsync@@QEAAXPEAU_GUID@@@Z; CBlbBackupAsync::ResetCompactionStatus(_GUID *)
0x140011156  mov     r12, [rbp+var_38]
0x14001115a  lea     rdx, [rbp+pv]; unsigned __int16 **
0x14001115e  add     r12, r15
0x140011161  mov     rcx, [r12+50h]; unsigned __int16 *
0x140011166  call    ?BlbutilRemoveTrailingBackslash@@YAJPEBGPEAPEAG@Z; BlbutilRemoveTrailingBackslash(ushort const *,ushort * *)
0x14001116b  mov     edi, eax
0x14001116d  test    eax, eax
0x14001116f  js      loc_140011556
0x140011175  mov     rcx, cs:WPP_GLOBAL_Control
0x14001117c  lea     rax, WPP_GLOBAL_Control
0x140011183  mov     r13, [rbp+pv]
0x140011187  cmp     rcx, rax
0x14001118a  jz      short loc_1400111BE
0x14001118c  test    byte ptr [rcx+1Ch], 1
0x140011190  jz      short loc_1400111BE
0x140011192  cmp     byte ptr [rcx+19h], 4
0x140011196  jb      short loc_1400111BE
0x140011198  mov     rax, [rbp+var_38]
0x14001119c  lea     r8, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids
0x1400111a3  mov     rcx, [rcx+10h]
0x1400111a7  mov     edx, 93h
0x1400111ac  mov     r9, r13
0x1400111af  mov     rax, [r15+rax+10h]
0x1400111b4  mov     [rsp+78h+var_58], rax
0x1400111b9  call    WPP_SF_SS
0x1400111be  mov     rcx, r13; unsigned __int16 *
0x1400111c1  call    ?Dismount@CBlbVhdHelper@@SAJPEBG@Z; CBlbVhdHelper::Dismount(ushort const *)
0x1400111c6  mov     edi, eax
0x1400111c8  test    eax, eax
0x1400111ca  js      loc_1400114F5
0x1400111d0  mov     rcx, [r12+50h]; pv
0x1400111d5  test    rcx, rcx
0x1400111d8  jz      short loc_1400111E9
0x1400111da  call    cs:__imp_CoTaskMemFree
0x1400111e0  mov     qword ptr [r12+50h], 0
0x1400111e9  mov     rdx, [rbp+var_38]
0x1400111ed  mov     byte ptr [r15+rdx+2Ch], 0
0x1400111f3  cmp     r14d, [rbp+arg_8]
0x1400111f7  jnb     short loc_140011232
0x1400111f9  mov     rsi, [rbp+arg_10]
0x1400111fd  mov     eax, r14d
0x140011200  imul    rdi, rax, 170h
0x140011207  mov     rcx, [rdi+rsi+0E0h]; pv
0x14001120f  test    rcx, rcx
0x140011212  jz      short loc_14001122A
0x140011214  call    cs:__imp_CoTaskMemFree
0x14001121a  mov     rdx, [rbp+var_38]
0x14001121e  mov     qword ptr [rdi+rsi+0E0h], 0
0x14001122a  mov     byte ptr [rdi+rsi+15Ah], 1
0x140011232  movups  xmm0, xmmword ptr [r15+rdx]
0x140011237  mov     r8, [rbp+arg_18]; unsigned __int16 *
0x14001123b  lea     r9, [rbp+Path]; unsigned __int16 **
0x14001123f  mov     edx, [r15+rdx+28h]; unsigned int
0x140011244  lea     rcx, [rbp+Buf1]; Buf1
0x140011248  movdqu  xmmword ptr [rbp+Buf1.Data1], xmm0
0x14001124d  call    ?BlbGetVhdPath@@YAJU_GUID@@KPEAGPEAPEAG@Z; BlbGetVhdPath(_GUID,ulong,ushort *,ushort * *)
0x140011252  mov     edi, eax
0x140011254  test    eax, eax
0x140011256  js      loc_14001144A
0x14001125c  mov     rcx, [rbx+0F0h]
0x140011263  add     rcx, 18h; this
0x140011267  call    ?CheckPoint@CBlbAsync@@QEAAEXZ; CBlbAsync::CheckPoint(void)
0x14001126c  test    al, al
0x14001126e  jz      loc_140011404
0x140011274  mov     r9, [rbx+0F0h]; void *
0x14001127b  lea     r8, ?BlbPerformCompactionCallback@@YAEPEAX_J1@Z; unsigned __int8 (*)(void *, __int64, __int64)
0x140011282  mov     rsi, [rbp+Path]
0x140011286  mov     rdx, rsi; Path
0x140011289  lea     rcx, [r9+28h]; this
0x14001128d  call    ?CompactVHD@CBlbVhdHelper@@SAJPEAVCBlbImpersonationHelper@@PEBGP6AEPEAX_J3@Z2@Z; CBlbVhdHelper::CompactVHD(CBlbImpersonationHelper *,ushort const *,uchar (*)(void *,__int64,__int64),void *)
0x140011292  mov     edi, eax
0x140011294  test    eax, eax
0x140011296  js      loc_1400113CF
0x14001129c  mov     rcx, [rbx+0F0h]; this
0x1400112a3  lea     r8, [rbp+var_40]; unsigned __int16 **
0x1400112a7  mov     rdx, rsi; PCWSTR
0x1400112aa  call    ?MountVHD@CBlbBackupAsync@@QEAAJPEBGPEAPEAG@Z; CBlbBackupAsync::MountVHD(ushort const *,ushort * *)
0x1400112af  mov     edi, eax
0x1400112b1  test    eax, eax
0x1400112b3  js      loc_14001137D
0x1400112b9  lea     rdx, [r12+50h]; unsigned __int16 **
0x1400112be  mov     r12, [rbp+var_40]
0x1400112c2  mov     rcx, r12; unsigned __int16 *
0x1400112c5  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x1400112ca  mov     edi, eax
0x1400112cc  test    eax, eax
0x1400112ce  js      loc_140011452
0x1400112d4  cmp     r14d, [rbp+arg_8]
0x1400112d8  jz      short loc_140011310
0x1400112da  mov     eax, r14d
0x1400112dd  imul    rcx, rax, 170h
0x1400112e4  mov     rax, [rbp+arg_10]
0x1400112e8  test    byte ptr [rcx+rax+54h], 8
0x1400112ed  jnz     short loc_140011310
0x1400112ef  lea     rdx, [rax+0E0h]
0x1400112f6  xor     r8d, r8d; unsigned __int64
0x1400112f9  add     rdx, rcx; unsigned __int16 **
0x1400112fc  mov     rcx, r12; unsigned __int16 *
0x1400112ff  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140011304  mov     edi, eax
0x140011306  test    eax, eax
0x140011308  js      loc_140011452
0x14001130e  jmp     short loc_140011320
0x140011310  mov     rax, [rbp+var_38]
0x140011314  mov     byte ptr [r15+rax+2Ch], 1
0x14001131a  jmp     short loc_140011320
0x14001131c  mov     r12, [rbp+var_40]
0x140011320  test    r13, r13
0x140011323  jz      short loc_140011335
0x140011325  mov     rcx, r13; pv
0x140011328  call    cs:__imp_CoTaskMemFree
0x14001132e  xor     r13d, r13d
0x140011331  mov     [rbp+pv], r13
0x140011335  test    rsi, rsi
0x140011338  jz      short loc_140011349
0x14001133a  mov     rcx, rsi; pv
0x14001133d  call    cs:__imp_CoTaskMemFree
0x140011343  xor     esi, esi
0x140011345  mov     [rbp+Path], rsi
0x140011349  test    r12, r12
0x14001134c  jz      short loc_14001135E
0x14001134e  mov     rcx, r12; pv
0x140011351  call    cs:__imp_CoTaskMemFree
0x140011357  xor     r12d, r12d
0x14001135a  mov     [rbp+var_40], r12
0x14001135e  mov     eax, [rbp+var_48]
0x140011361  mov     rcx, cs:WPP_GLOBAL_Control
0x140011368  inc     eax
0x14001136a  mov     edx, [rbp+var_44]
0x14001136d  jmp     loc_140010F9A
0x140011372  mov     ecx, 80070057h; int
0x140011377  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001137d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011384  lea     r14, WPP_GLOBAL_Control
0x14001138b  cmp     rcx, r14
0x14001138e  jz      short loc_1400113B8
0x140011390  test    byte ptr [rcx+1Ch], 1
0x140011394  jz      short loc_1400113B8
0x140011396  cmp     byte ptr [rcx+19h], 2
0x14001139a  jb      short loc_1400113B8
0x14001139c  mov     rcx, [rcx+10h]
0x1400113a0  lea     r8, WPP_7d2043e956a53eb416ccda4830c6c098_Traceguids
0x1400113a7  mov     edx, 97h
0x1400113ac  mov     dword ptr [rsp+78h+var_58], edi
0x1400113b0  mov     r9, rsi
0x1400113b3  call    WPP_SF_Sd
0x1400113b8  mov     edx, 5
0x1400113bd  mov     rcx, rbx
0x1400113c0  call    ?SetState@CBlbApplicationBackupAsync@@QEAAXW4BLB_APPLICATION_BACKUP_STATE@@@Z; CBlbApplicationBackupAsync::SetState(BLB_APPLICATION_BACKUP_STATE)
0x1400113c5  mov     edx, 80780104h
0x1400113ca  jmp     loc_140011542
0x1400113cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400113d6  lea     r14, WPP_GLOBAL_Control
0x1400113dd  cmp     rcx, r14
0x1400113e0  jz      loc_1400115D3
0x1400113e6  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
