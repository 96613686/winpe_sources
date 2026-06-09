# CBlbEngine::MergeAndPatchCatalogFromTarget(ushort *,ushort *,uchar,uchar,CBlbImpersonationHelper *,uchar *,long *)

- ea: `0x140049700`
- end: `0x140049e34`
- name: `?MergeAndPatchCatalogFromTarget@CBlbEngine@@QEAAJPEAG0EEPEAVCBlbImpersonationHelper@@PEAEPEAJ@Z`
- size: `1844`
- prototype: `int(CBlbEngine *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int8, unsigned __int8, struct CBlbImpersonationHelper *, unsigned __int8 *, int *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update`

## callers

- `0x14003b924`

## callees

- `0x140005334`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000cbcc`
- `0x140014260`
- `0x1400142d8`
- `0x140049700`
- `0x1400881ac`
- `0x140088d0c`
- `0x14008bd48`
- `0x14009257c`
- `0x1400a0f00`
- `0x140104240`
- `0x140104908`
- `0x140106e60`
- `0x1401232b0`
- `0x14012dbcc`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400497e4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400499a8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400497e4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400499a8`
- `ole32!CoTaskMemFree` at `0x1400499b7`
- `ole32!CoTaskMemFree` at `0x1400499c6`
- `ole32!CoTaskMemFree` at `0x1400499d4`
- `ole32!CoTaskMemFree` at `0x1400499e2`
- `ole32!CoTaskMemFree` at `0x1400499f0`
- `ole32!CoTaskMemFree` at `0x1400499ff`
- `ole32!CoTaskMemFree` at `0x1400499b7`
- `ole32!CoTaskMemFree` at `0x1400499c6`
- `ole32!CoTaskMemFree` at `0x1400499d4`
- `ole32!CoTaskMemFree` at `0x1400499e2`
- `ole32!CoTaskMemFree` at `0x1400499f0`
- `ole32!CoTaskMemFree` at `0x1400499ff`

## pseudocode

```c
__int64 __fastcall CBlbEngine::MergeAndPatchCatalogFromTarget(
        CBlbEngine *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int8 a5,
        struct CBlbImpersonationHelper *a6,
        unsigned __int8 *a7,
        int *a8)
{
  unsigned __int16 *v10; // r15
  struct IBLBCatalogSystem *v11; // r13
  WCHAR *v12; // rdi
  int TargetMediaType; // eax
  int v14; // ebx
  _OWORD *v15; // rsi
  unsigned int v16; // esi
  int BackupRootDirectory; // eax
  int MediaIdInTarget; // eax
  BlbGuidStr *v19; // rax
  int v20; // eax
  int v21; // eax
  CBlbEngine *v23; // r12
  int v24; // eax
  int v25; // eax
  unsigned int i; // r8d
  __int64 v27; // rdx
  int v28; // eax
  int VolumeLabel; // eax
  _QWORD *v30; // rcx
  int v31; // edx
  int v32; // ebx
  int v33; // [rsp+38h] [rbp-C8h]
  char v34; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v35[7]; // [rsp+51h] [rbp-AFh] BYREF
  LPVOID v36; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v37; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v38; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v39; // [rsp+68h] [rbp-98h] BYREF
  struct _BLB_BACKUP_SET_INFO *v40; // [rsp+70h] [rbp-90h] BYREF
  int *v41; // [rsp+78h] [rbp-88h]
  LPCWSTR lpszVolumeName; // [rsp+80h] [rbp-80h] BYREF
  struct IBLBCatalogSystem *v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v44; // [rsp+90h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v46; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 *v47; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int8 *v48; // [rsp+B0h] [rbp-50h]
  struct _GUID v49; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-30h] BYREF
  CBlbEngine *v51; // [rsp+D8h] [rbp-28h]
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v53[112]; // [rsp+F0h] [rbp-10h] BYREF

  v48 = a7;
  v41 = a8;
  v51 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
  }
  v10 = 0;
  v44 = 0;
  v49 = GUID_NULL;
  v43 = 0;
  v11 = 0;
  v50 = 0;
  pv = 0;
  v12 = 0;
  v46 = 0;
  v39 = 0;
  lpszVolumeName = 0;
  v40 = 0;
  v37 = 0;
  v36 = 0;
  v34 = 0;
  v35[0] = 0;
  v47 = 0;
  v38 = 0;
  *a8 = 0;
  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
  GetSystemTimeAsFileTime(SystemTimeAsFileTime);
  *v48 = 0;
  TargetMediaType = BlbQueryTargetMediaType(a2, a6, (enum _BLB_MEDIA_TYPE *)&v39);
  v14 = TargetMediaType;
  if ( TargetMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        183,
        (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
        (_DWORD)a2,
        TargetMediaType);
    }
LABEL_10:
    v15 = v36;
    goto LABEL_32;
  }
  v16 = v39;
  if ( (BlbutilGetBackupFeatures(v39) & 0x20) != 0 || v16 == 4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    goto LABEL_10;
  }
  BackupRootDirectory = BlbGetBackupRootDirectory(a2, a3, &v44);
  v10 = v44;
  v14 = BackupRootDirectory;
  if ( BackupRootDirectory < 0 )
    goto LABEL_31;
  MediaIdInTarget = BlbGetMediaIdInTarget(v44, &v49);
  if ( MediaIdInTarget < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        185,
        (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
        (_DWORD)v10,
        MediaIdInTarget);
    }
    v14 = 0;
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v19 = BlbGuidStr::BlbGuidStr((BlbGuidStr *)v53, &v49);
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      186,
      (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
      (_DWORD)v10,
      (__int64)v19);
  }
  v20 = CreateCatalogSystem(&v43);
  v11 = v43;
  v14 = v20;
  if ( v20 < 0 )
    goto LABEL_31;
  v21 = (*(__int64 (__fastcall **)(struct IBLBCatalogSystem *, unsigned __int16 *, __int64, __int64 *))(*(_QWORD *)v43 + 168LL))(
          v43,
          v10,
          1,
          &v50);
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        187,
        (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
        (_DWORD)v10,
        v21);
    }
    v14 = 0;
LABEL_31:
    v15 = v36;
    goto LABEL_32;
  }
  v23 = v51;
  v24 = (*(__int64 (__fastcall **)(CBlbEngine *, struct IBLBCatalogSystem *, struct _GUID *, unsigned __int16 *, __int64, _BYTE, unsigned int *, struct _BLB_BACKUP_SET_INFO **))(*(_QWORD *)v51 + 176LL))(
          v51,
          v11,
          &v49,
          a2,
          -1,
          0,
          &v37,
          &v40);
  v14 = v24;
  if ( v24 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        188,
        (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
        (_DWORD)a2,
        v24);
    }
    *v41 = v14;
    v14 = -2139619034;
    goto LABEL_31;
  }
  if ( !v37 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    }
    goto LABEL_31;
  }
  v25 = BlbutilMemalloc(&v36, v37, 0x10u);
  v15 = v36;
  v14 = v25;
  if ( v25 >= 0 )
  {
    for ( i = 0; i < v37; v15[v27] = *(_OWORD *)((char *)v40 + 168 * v27) )
      v27 = i++;
    v28 = BlbutilSlashTerminatePath(a2, (LPVOID *)&lpszVolumeName);
    v12 = (WCHAR *)lpszVolumeName;
    v14 = v28;
    if ( v28 >= 0 )
    {
      VolumeLabel = BlbQueryVolumeLabel((unsigned __int16 *)lpszVolumeName, (unsigned __int16 **)&pv);
      v14 = VolumeLabel;
      if ( VolumeLabel >= 0 )
      {
        VolumeLabel = BlbQueryVolumeAccessPath(v12, &v46);
        v14 = VolumeLabel;
        if ( VolumeLabel >= 0 )
        {
          VolumeLabel = BlbutilQueryVolumeUniqueId(v12, &v47, &v38);
          v14 = VolumeLabel;
          if ( VolumeLabel >= 0 )
          {
            v32 = (*(__int64 (__fastcall **)(_QWORD, struct IBLBCatalogSystem *, _QWORD, _OWORD *, char *))(**((_QWORD **)v23 + 2) + 272LL))(
                    *((_QWORD *)v23 + 2),
                    v11,
                    v37,
                    v15,
                    &v34);
            if ( v32 >= 0 )
            {
              LOWORD(v33) = v38;
              v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _OWORD *, unsigned __int16 *, LPVOID, unsigned __int16 *, unsigned __int8 *, int, _BYTE *))(**((_QWORD **)v23 + 2) + 280LL))(
                      *((_QWORD *)v23 + 2),
                      v37,
                      v15,
                      a2,
                      pv,
                      v46,
                      v47,
                      v33,
                      v35);
              if ( v14 >= 0 )
              {
                if ( v34 || v35[0] )
                  *v48 = 1;
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
                }
                *v41 = v14;
                v14 = -2139619033;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
              }
              *v41 = v32;
              v14 = -2139619034;
            }
          }
          else
          {
            v30 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v31 = 192;
              goto LABEL_73;
            }
          }
        }
        else
        {
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v31 = 191;
            goto LABEL_73;
          }
        }
      }
      else
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v31 = 190;
LABEL_73:
          WPP_SF_Sd(
            v30[2],
            v31,
            (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
            (_DWORD)v12,
            VolumeLabel);
        }
      }
    }
  }
LABEL_32:
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v46 )
    CoTaskMemFree(v46);
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v15 )
    CoTaskMemFree(v15);
  if ( v47 )
    CoTaskMemFree(v47);
  if ( v40 )
    FreeBackupSets(&v40, &v37);
  if ( v11 )
    (*(void (__fastcall **)(struct IBLBCatalogSystem *))(*(_QWORD *)v11 + 240LL))(v11);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140049700  mov     [rsp-8+arg_18], rbx
0x140049705  push    rbp
0x140049706  push    rsi
0x140049707  push    rdi
0x140049708  push    r12
0x14004970a  push    r13
0x14004970c  push    r14
0x14004970e  push    r15
0x140049710  lea     rbp, [rsp-70h]
0x140049715  sub     rsp, 170h
0x14004971c  mov     rax, cs:__security_cookie
0x140049723  xor     rax, rsp
0x140049726  mov     [rbp+0A0h+var_40], rax
0x14004972a  mov     rax, [rbp+0A0h+arg_30]
0x140049731  mov     r12, r8
0x140049734  mov     rsi, [rbp+0A0h+arg_38]
0x14004973b  mov     r14, rdx
0x14004973e  mov     rbx, [rbp+0A0h+arg_28]
0x140049745  mov     [rbp+0A0h+var_F0], rax
0x140049749  mov     [rsp+1A0h+var_128], rsi
0x14004974e  mov     [rbp+0A0h+var_C8], rcx
0x140049752  mov     rcx, cs:WPP_GLOBAL_Control
0x140049759  lea     rax, WPP_GLOBAL_Control
0x140049760  cmp     rcx, rax
0x140049763  jz      short loc_140049786
0x140049765  test    byte ptr [rcx+1Ch], 1
0x140049769  jz      short loc_140049786
0x14004976b  cmp     byte ptr [rcx+19h], 4
0x14004976f  jb      short loc_140049786
0x140049771  mov     rcx, [rcx+10h]
0x140049775  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004977c  mov     edx, 0B6h
0x140049781  call    WPP_SF_
0x140049786  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14004978d  xor     ecx, ecx
0x14004978f  mov     r15d, ecx
0x140049792  mov     [rbp+0A0h+var_110], rcx
0x140049796  movdqu  xmmword ptr [rbp+0A0h+var_E0.Data1], xmm0
0x14004979b  mov     [rbp+0A0h+var_118], rcx
0x14004979f  mov     r13d, ecx
0x1400497a2  xorps   xmm0, xmm0
0x1400497a5  mov     [rbp+0A0h+var_D0], rcx
0x1400497a9  mov     [rbp+0A0h+pv], rcx
0x1400497ad  mov     edi, ecx
0x1400497af  mov     [rbp+0A0h+var_100], rcx
0x1400497b3  mov     [rsp+1A0h+var_138], ecx
0x1400497b7  mov     [rbp+0A0h+lpszVolumeName], rcx
0x1400497bb  mov     [rsp+1A0h+var_130], rcx
0x1400497c0  mov     [rsp+1A0h+var_140], ecx
0x1400497c4  mov     [rsp+1A0h+var_148], rcx
0x1400497c9  mov     [rsp+1A0h+var_150], cl
0x1400497cd  mov     [rsp+1A0h+var_14F], cl
0x1400497d1  mov     [rbp+0A0h+var_F8], rcx
0x1400497d5  mov     [rsp+1A0h+var_13C], cx
0x1400497da  mov     [rsi], ecx
0x1400497dc  lea     rcx, [rbp+0A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400497e0  movups  xmmword ptr [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x1400497e4  call    cs:__imp_GetSystemTimeAsFileTime
0x1400497ea  mov     rax, [rbp+0A0h+var_F0]
0x1400497ee  lea     r8, [rsp+1A0h+var_138]; enum _BLB_MEDIA_TYPE *
0x1400497f3  mov     rdx, rbx; this
0x1400497f6  mov     rcx, r14; unsigned __int16 *
0x1400497f9  mov     [rax], dil
0x1400497fc  call    ?BlbQueryTargetMediaType@@YAJPEAGPEAVCBlbImpersonationHelper@@PEAW4_BLB_MEDIA_TYPE@@@Z; BlbQueryTargetMediaType(ushort *,CBlbImpersonationHelper *,_BLB_MEDIA_TYPE *)
0x140049801  mov     ebx, eax
0x140049803  test    eax, eax
0x140049805  jns     short loc_14004984C
0x140049807  mov     rcx, cs:WPP_GLOBAL_Control
0x14004980e  lea     r12, WPP_GLOBAL_Control
0x140049815  cmp     rcx, r12
0x140049818  jz      short loc_140049842
0x14004981a  test    byte ptr [rcx+1Ch], 1
0x14004981e  jz      short loc_140049842
0x140049820  cmp     byte ptr [rcx+19h], 2
0x140049824  jb      short loc_140049842
0x140049826  mov     rcx, [rcx+10h]
0x14004982a  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x140049831  mov     edx, 0B7h
0x140049836  mov     dword ptr [rsp+1A0h+var_180], eax
0x14004983a  mov     r9, r14
0x14004983d  call    WPP_SF_Sd
0x140049842  mov     rsi, [rsp+1A0h+var_148]
0x140049847  jmp     loc_1400499A4
0x14004984c  mov     esi, [rsp+1A0h+var_138]
0x140049850  mov     ecx, esi
0x140049852  call    ?BlbutilGetBackupFeatures@@YAKW4_BLB_MEDIA_TYPE@@@Z; BlbutilGetBackupFeatures(_BLB_MEDIA_TYPE)
0x140049857  test    al, 20h
0x140049859  jnz     loc_140049DEC
0x14004985f  cmp     esi, 4
0x140049862  jz      loc_140049DEC
0x140049868  lea     r8, [rbp+0A0h+var_110]; unsigned __int16 **
0x14004986c  mov     rdx, r12; unsigned __int16 *
0x14004986f  mov     rcx, r14; unsigned __int16 *
0x140049872  call    ?BlbGetBackupRootDirectory@@YAJPEAG0PEAPEAG@Z; BlbGetBackupRootDirectory(ushort *,ushort *,ushort * *)
0x140049877  mov     r15, [rbp+0A0h+var_110]
0x14004987b  mov     ebx, eax
0x14004987d  test    eax, eax
0x14004987f  js      loc_140049998
0x140049885  lea     rdx, [rbp+0A0h+var_E0]; struct _GUID *
0x140049889  mov     rcx, r15; unsigned __int16 *
0x14004988c  call    ?BlbGetMediaIdInTarget@@YAJPEAGPEAU_GUID@@@Z; BlbGetMediaIdInTarget(ushort *,_GUID *)
0x140049891  test    eax, eax
0x140049893  jns     short loc_1400498D7
0x140049895  mov     rcx, cs:WPP_GLOBAL_Control
0x14004989c  lea     r12, WPP_GLOBAL_Control
0x1400498a3  cmp     rcx, r12
0x1400498a6  jz      short loc_1400498D0
0x1400498a8  test    byte ptr [rcx+1Ch], 1
0x1400498ac  jz      short loc_1400498D0
0x1400498ae  cmp     byte ptr [rcx+19h], 4
0x1400498b2  jb      short loc_1400498D0
0x1400498b4  mov     rcx, [rcx+10h]
0x1400498b8  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x1400498bf  mov     edx, 0B9h
0x1400498c4  mov     dword ptr [rsp+1A0h+var_180], eax
0x1400498c8  mov     r9, r15
0x1400498cb  call    WPP_SF_Sd
0x1400498d0  xor     ebx, ebx
0x1400498d2  jmp     loc_140049842
0x1400498d7  mov     rax, cs:WPP_GLOBAL_Control
0x1400498de  lea     rsi, WPP_GLOBAL_Control
0x1400498e5  cmp     rax, rsi
0x1400498e8  jz      short loc_140049927
0x1400498ea  test    byte ptr [rax+1Ch], 1
0x1400498ee  jz      short loc_140049927
0x1400498f0  cmp     byte ptr [rax+19h], 4
0x1400498f4  jb      short loc_140049927
0x1400498f6  lea     rdx, [rbp+0A0h+var_E0]; struct _GUID *
0x1400498fa  lea     rcx, [rbp+0A0h+var_B0]; this
0x1400498fe  call    ??0BlbGuidStr@@QEAA@AEBU_GUID@@@Z; BlbGuidStr::BlbGuidStr(_GUID const &)
0x140049903  mov     rcx, cs:WPP_GLOBAL_Control
0x14004990a  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x140049911  mov     edx, 0BAh
0x140049916  mov     [rsp+1A0h+var_180], rax
0x14004991b  mov     r9, r15
0x14004991e  mov     rcx, [rcx+10h]
0x140049922  call    WPP_SF_SS
0x140049927  lea     rcx, [rbp+0A0h+var_118]; struct IBLBCatalogSystem **
0x14004992b  call    ?CreateCatalogSystem@@YAJPEAPEAUIBLBCatalogSystem@@@Z; CreateCatalogSystem(IBLBCatalogSystem * *)
0x140049930  mov     r13, [rbp+0A0h+var_118]
0x140049934  mov     ebx, eax
0x140049936  test    eax, eax
0x140049938  js      short loc_140049998
0x14004993a  mov     rax, [r13+0]
0x14004993e  lea     r9, [rbp+0A0h+var_D0]
0x140049942  mov     r8d, 1
0x140049948  mov     rdx, r15
0x14004994b  mov     rcx, r13
0x14004994e  mov     rax, [rax+0A8h]
0x140049955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004995a  test    eax, eax
0x14004995c  jns     loc_140049A8A
0x140049962  mov     rcx, cs:WPP_GLOBAL_Control
0x140049969  cmp     rcx, rsi
0x14004996c  jz      short loc_140049996
0x14004996e  test    byte ptr [rcx+1Ch], 1
0x140049972  jz      short loc_140049996
0x140049974  cmp     byte ptr [rcx+19h], 4
0x140049978  jb      short loc_140049996
0x14004997a  mov     rcx, [rcx+10h]
0x14004997e  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x140049985  mov     edx, 0BBh
0x14004998a  mov     dword ptr [rsp+1A0h+var_180], eax
0x14004998e  mov     r9, r15
0x140049991  call    WPP_SF_Sd
0x140049996  xor     ebx, ebx
0x140049998  mov     rsi, [rsp+1A0h+var_148]
0x14004999d  lea     r12, WPP_GLOBAL_Control
0x1400499a4  lea     rcx, [rbp+0A0h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x1400499a8  call    cs:__imp_GetSystemTimeAsFileTime
0x1400499ae  mov     rcx, [rbp+0A0h+pv]; pv
0x1400499b2  test    rcx, rcx
0x1400499b5  jz      short loc_1400499BD
0x1400499b7  call    cs:__imp_CoTaskMemFree
0x1400499bd  mov     rcx, [rbp+0A0h+var_100]; pv
0x1400499c1  test    rcx, rcx
0x1400499c4  jz      short loc_1400499CC
0x1400499c6  call    cs:__imp_CoTaskMemFree
0x1400499cc  test    rdi, rdi
0x1400499cf  jz      short loc_1400499DA
0x1400499d1  mov     rcx, rdi; pv
0x1400499d4  call    cs:__imp_CoTaskMemFree
0x1400499da  test    r15, r15
0x1400499dd  jz      short loc_1400499E8
0x1400499df  mov     rcx, r15; pv
0x1400499e2  call    cs:__imp_CoTaskMemFree
0x1400499e8  test    rsi, rsi
0x1400499eb  jz      short loc_1400499F6
0x1400499ed  mov     rcx, rsi; pv
0x1400499f0  call    cs:__imp_CoTaskMemFree
0x1400499f6  mov     rcx, [rbp+0A0h+var_F8]; pv
0x1400499fa  test    rcx, rcx
0x1400499fd  jz      short loc_140049A05
0x1400499ff  call    cs:__imp_CoTaskMemFree
0x140049a05  cmp     [rsp+1A0h+var_130], 0
0x140049a0b  jz      short loc_140049A1C
0x140049a0d  lea     rdx, [rsp+1A0h+var_140]; unsigned int *
0x140049a12  lea     rcx, [rsp+1A0h+var_130]; struct _BLB_BACKUP_SET_INFO **
0x140049a17  call    ?FreeBackupSets@@YAXAEAPEAU_BLB_BACKUP_SET_INFO@@AEAK@Z; FreeBackupSets(_BLB_BACKUP_SET_INFO * &,ulong &)
0x140049a1c  test    r13, r13
0x140049a1f  jz      short loc_140049A34
0x140049a21  mov     rax, [r13+0]
0x140049a25  mov     rcx, r13
0x140049a28  mov     rax, [rax+0F0h]
0x140049a2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049a34  mov     rcx, cs:WPP_GLOBAL_Control
0x140049a3b  cmp     rcx, r12
0x140049a3e  jz      short loc_140049A61
0x140049a40  test    byte ptr [rcx+1Ch], 1
0x140049a44  jz      short loc_140049A61
0x140049a46  cmp     byte ptr [rcx+19h], 4
0x140049a4a  jb      short loc_140049A61
0x140049a4c  mov     rcx, [rcx+10h]
0x140049a50  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x140049a57  mov     edx, 0C3h
0x140049a5c  call    WPP_SF_
0x140049a61  mov     eax, ebx
0x140049a63  mov     rcx, [rbp+0A0h+var_40]
0x140049a67  xor     rcx, rsp; StackCookie
0x140049a6a  call    __security_check_cookie
0x140049a6f  mov     rbx, [rsp+1A0h+arg_18]
0x140049a77  add     rsp, 170h
0x140049a7e  pop     r15
0x140049a80  pop     r14
0x140049a82  pop     r13
0x140049a84  pop     r12
0x140049a86  pop     rdi
0x140049a87  pop     rsi
0x140049a88  pop     rbp
0x140049a89  retn
0x140049a8a  mov     r12, [rbp+0A0h+var_C8]
0x140049a8e  lea     rcx, [rsp+1A0h+var_130]
0x140049a93  movaps  xmm0, xmmword ptr [rbp+0A0h+var_E0.Data1]
0x140049a97  lea     r8, [rbp+0A0h+var_E0]
0x140049a9b  mov     [rsp+1A0h+var_168], rcx
0x140049aa0  mov     r9, r14
0x140049aa3  lea     rcx, [rsp+1A0h+var_140]
0x140049aa8  movdqa  xmmword ptr [rbp+0A0h+var_E0.Data1], xmm0
0x140049aad  mov     rax, [r12]
0x140049ab1  mov     rdx, r13
0x140049ab4  mov     [rsp+1A0h+var_170], rcx
0x140049ab9  mov     rcx, r12
0x140049abc  mov     byte ptr [rsp+1A0h+var_178], dil
0x140049ac1  mov     [rsp+1A0h+var_180], 0FFFFFFFFFFFFFFFFh
0x140049aca  mov     rax, [rax+0B0h]
0x140049ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049ad6  mov     ebx, eax
0x140049ad8  test    eax, eax
0x140049ada  jns     short loc_140049B21
0x140049adc  mov     rcx, cs:WPP_GLOBAL_Control
0x140049ae3  cmp     rcx, rsi
0x140049ae6  jz      short loc_140049B10
0x140049ae8  test    byte ptr [rcx+1Ch], 1
0x140049aec  jz      short loc_140049B10
0x140049aee  cmp     byte ptr [rcx+19h], 2
0x140049af2  jb      short loc_140049B10
0x140049af4  mov     rcx, [rcx+10h]
0x140049af8  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x140049aff  mov     edx, 0BCh
0x140049b04  mov     dword ptr [rsp+1A0h+var_180], eax
0x140049b08  mov     r9, r14
0x140049b0b  call    WPP_SF_Sd
0x140049b10  mov     rax, [rsp+1A0h+var_128]
0x140049b15  mov     [rax], ebx
0x140049b17  mov     ebx, 80780126h
0x140049b1c  jmp     loc_140049998
0x140049b21  mov     edx, [rsp+1A0h+var_140]; unsigned int
0x140049b25  test    edx, edx
0x140049b27  jnz     short loc_140049B67
0x140049b29  mov     rcx, cs:WPP_GLOBAL_Control
0x140049b30  cmp     rcx, rsi
0x140049b33  jz      loc_140049998
0x140049b39  test    byte ptr [rcx+1Ch], 1
0x140049b3d  jz      loc_140049998
0x140049b43  cmp     byte ptr [rcx+19h], 4
0x140049b47  jb      loc_140049998
0x140049b4d  mov     rcx, [rcx+10h]
0x140049b51  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x140049b58  mov     edx, 0BDh
0x140049b5d  call    WPP_SF_
0x140049b62  jmp     loc_140049998
0x140049b67  mov     r8d, 10h; unsigned int
0x140049b6d  lea     rcx, [rsp+1A0h+var_148]; void **
0x140049b72  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x140049b77  mov     rsi, [rsp+1A0h+var_148]
0x140049b7c  mov     ebx, eax
0x140049b7e  test    eax, eax
0x140049b80  js      loc_14004999D
0x140049b86  xor     r8d, r8d
0x140049b89  cmp     [rsp+1A0h+var_140], edi
0x140049b8d  jbe     short loc_140049BB4
0x140049b8f  mov     rax, [rsp+1A0h+var_130]
0x140049b94  mov     edx, r8d
0x140049b97  inc     r8d
0x140049b9a  imul    rcx, rdx, 0A8h
0x140049ba1  add     rdx, rdx
0x140049ba4  movups  xmm0, xmmword ptr [rcx+rax]
0x140049ba8  movdqu  xmmword ptr [rsi+rdx*8], xmm0
0x140049bad  cmp     r8d, [rsp+1A0h+var_140]
0x140049bb2  jb      short loc_140049B8F
  ... truncated ...
```
