# BlbGetTargetPathForBackupSet(ushort *,uchar,_BLBCAT_BACKUP_SET_INFO *,CBlbImpersonationHelper *,ushort * *,ushort * *,ushort * *)

- ea: `0x140104e8c`
- end: `0x140105724`
- name: `?BlbGetTargetPathForBackupSet@@YAJPEAGEPEAU_BLBCAT_BACKUP_SET_INFO@@PEAVCBlbImpersonationHelper@@PEAPEAG33@Z`
- size: `2200`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int8@<dl>, struct _BLBCAT_BACKUP_SET_INFO *@<r8>, struct CBlbImpersonationHelper *@<r9>, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `11`
- callee_count: `24`
- tags: `authz_impersonation, service_task`

## callers

- `0x140021210`
- `0x14004a690`
- `0x14004c680`
- `0x14004fb00`
- `0x140058444`
- `0x14006c8b0`
- `0x140071f1c`
- `0x140076588`
- `0x14007ce58`
- `0x14007fcb8`
- `0x1401026c8`

## callees

- `0x14000bb24`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x140014384`
- `0x14003c434`
- `0x1400877b0`
- `0x14008863c`
- `0x1400889f0`
- `0x14009257c`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f11ec`
- `0x140100584`
- `0x140104240`
- `0x1401042c4`
- `0x140104e8c`
- `0x1401061f8`
- `0x140106e60`
- `0x1401159d0`
- `0x1401218b8`
- `0x1401232b0`
- `0x140124d1c`
- `0x14012780c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140105401`
- `ole32!CoTaskMemFree` at `0x140105416`
- `ole32!CoTaskMemFree` at `0x14010542c`
- `ole32!CoTaskMemFree` at `0x140105443`
- `ole32!CoTaskMemFree` at `0x140105451`
- `ole32!CoTaskMemFree` at `0x14010545f`
- `ole32!CoTaskMemFree` at `0x14010546d`
- `ole32!CoTaskMemFree` at `0x140105401`
- `ole32!CoTaskMemFree` at `0x140105416`
- `ole32!CoTaskMemFree` at `0x14010542c`
- `ole32!CoTaskMemFree` at `0x140105443`
- `ole32!CoTaskMemFree` at `0x140105451`
- `ole32!CoTaskMemFree` at `0x14010545f`
- `ole32!CoTaskMemFree` at `0x14010546d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BlbGetTargetPathForBackupSet(
        unsigned __int16 *a1,
        char a2,
        struct _BLBCAT_BACKUP_SET_INFO *a3,
        struct CBlbImpersonationHelper *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7)
{
  unsigned __int16 *v10; // rsi
  unsigned __int16 *v11; // r12
  unsigned __int16 *v12; // r15
  LPVOID *v13; // r13
  int TargetMediaType; // ebx
  LPVOID *v15; // rdi
  unsigned int v16; // r15d
  __int16 BackupFeatures; // r13
  int v18; // edi
  _QWORD *v19; // rcx
  int v20; // edx
  int IsVolumeBitlocked; // eax
  char v22; // si
  char v23; // di
  __int64 v24; // rax
  int SnapshotDeviceName; // eax
  unsigned __int16 *v26; // rax
  int v27; // ecx
  int v28; // edx
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  PVOID *v31; // rcx
  int appended; // eax
  bool v33; // cf
  bool v34; // zf
  unsigned __int8 v36; // [rsp+38h] [rbp-81h] BYREF
  unsigned __int8 v37[7]; // [rsp+39h] [rbp-80h] BYREF
  unsigned __int16 *v38; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int16 *v39; // [rsp+48h] [rbp-71h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v41; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int16 *v42; // [rsp+60h] [rbp-59h] BYREF
  _OWORD v43[2]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v44; // [rsp+88h] [rbp-31h]
  int v45; // [rsp+90h] [rbp-29h]
  int v46; // [rsp+98h] [rbp-21h]
  __int64 v47; // [rsp+A0h] [rbp-19h]
  int v48; // [rsp+A8h] [rbp-11h]
  __int64 v49; // [rsp+B0h] [rbp-9h]
  char v50; // [rsp+B8h] [rbp-1h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids);
  }
  v37[0] = 0;
  v36 = 0;
  pv = 0;
  v10 = 0;
  v39 = 0;
  v41 = 0;
  v11 = 0;
  v42 = 0;
  v12 = 0;
  v38 = 0;
  *a5 = 0;
  *a6 = 0;
  v13 = (LPVOID *)a7;
  *a7 = 0;
  TargetMediaType = BlbQueryTargetMediaType(a1, a4, (enum _BLB_MEDIA_TYPE *)&v41);
  if ( TargetMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
        (_DWORD)pv,
        TargetMediaType);
    }
    goto LABEL_10;
  }
  v16 = v41;
  if ( v41 != *((_DWORD *)a3 + 7)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids);
  }
  BackupFeatures = BlbutilGetBackupFeatures(v16);
  if ( v16 != 4 )
  {
    memset(v43, 0, sizeof(v43));
    v44 = 0;
    v45 = 10;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v46 = 0;
    TargetMediaType = BlbutilAppendString(a1, L"\\", (unsigned __int16 **)&pv);
    if ( TargetMediaType >= 0 )
    {
      if ( a2 )
      {
        if ( v16 - 2 <= 1 )
        {
          v18 = CBlbVdsHelperLibrary::MountVolumes((CBlbVdsHelperLibrary *)v43, (unsigned __int16 **)&pv, 1u);
          if ( v18 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
                (_DWORD)pv,
                v18);
            }
            if ( v18 != -2139619172 )
              v18 = -2139619316;
            TargetMediaType = v18;
            goto LABEL_25;
          }
        }
      }
      TargetMediaType = BlbIsVolumeNameValid((wchar_t *)pv, 0, v37);
      if ( TargetMediaType >= 0 )
      {
        if ( !v37[0] )
        {
LABEL_38:
          TargetMediaType = -2139619316;
          goto LABEL_25;
        }
        TargetMediaType = BlbIsTargetValid((unsigned __int16 *)pv, v37, &v36);
        if ( TargetMediaType < 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_25;
          }
          v20 = 32;
          goto LABEL_44;
        }
        if ( !v36 )
          goto LABEL_38;
        TargetMediaType = BlbQueryVolumeAccessPath((LPCWSTR)pv, a5);
        if ( TargetMediaType >= 0 )
        {
          if ( (BlbutilGetBackupFeatures(v16) & 0x200) == 0 )
          {
            v36 = 0;
            IsVolumeBitlocked = BlbIsVolumeBitlocked((unsigned __int16 *)pv, &v36);
            if ( IsVolumeBitlocked >= 0 )
            {
              if ( v36 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    35,
                    &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
                    pv);
                }
                TargetMediaType = -2139619149;
                goto LABEL_25;
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                34,
                (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
                (_DWORD)pv,
                IsVolumeBitlocked);
            }
          }
          CBlbVdsHelperLibrary::~CBlbVdsHelperLibrary((CBlbVdsHelperLibrary *)v43);
          goto LABEL_58;
        }
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = 33;
LABEL_44:
          WPP_SF_Sd(
            v19[2],
            v20,
            (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
            (_DWORD)pv,
            TargetMediaType);
        }
      }
    }
LABEL_25:
    CBlbVdsHelperLibrary::~CBlbVdsHelperLibrary((CBlbVdsHelperLibrary *)v43);
    goto LABEL_21;
  }
  TargetMediaType = CBlbImpersonationHelper::ImpersonateCaller(a4, 0);
  if ( TargetMediaType < 0 )
    goto LABEL_21;
  TargetMediaType = BlbutilCheckNetworkShare(a1, 0, v37);
  if ( TargetMediaType < 0 )
    goto LABEL_21;
  if ( !v37[0] )
  {
    TargetMediaType = -2139619316;
LABEL_21:
    v15 = (LPVOID *)a6;
LABEL_90:
    v13 = (LPVOID *)a7;
    goto LABEL_91;
  }
  TargetMediaType = BlbutilDuplicateString(a1, a5, 0);
  if ( TargetMediaType < 0 )
    goto LABEL_21;
LABEL_58:
  v22 = 0;
  v23 = 0;
  if ( (BackupFeatures & 8) == 0 )
  {
    TargetMediaType = BlbutilDuplicateString(a1, a6, 0);
    if ( TargetMediaType < 0 )
      goto LABEL_88;
    goto LABEL_119;
  }
  v24 = *(_QWORD *)((char *)a3 + 108) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v24 )
    v24 = *(_QWORD *)((char *)a3 + 116) - *(_QWORD *)GUID_NULL.Data4;
  if ( !v24 )
    goto LABEL_112;
  SnapshotDeviceName = BlbGetSnapshotDeviceName((struct _GUID *)((char *)a3 + 108), a6, &v39);
  TargetMediaType = SnapshotDeviceName;
  if ( SnapshotDeviceName < 0 )
  {
    if ( SnapshotDeviceName != -2139619271 )
      goto LABEL_88;
LABEL_112:
    v15 = (LPVOID *)a6;
    TargetMediaType = BlbutilDuplicateString(a1, a6, 0);
    if ( TargetMediaType < 0 )
      goto LABEL_89;
    v23 = 1;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v30 = 39;
      goto LABEL_117;
    }
    goto LABEL_119;
  }
  v26 = (unsigned __int16 *)pv;
  do
  {
    v27 = *(unsigned __int16 *)((char *)v26 + (char *)v39 - (_BYTE *)pv);
    v28 = *v26 - v27;
    if ( v28 )
      break;
    ++v26;
  }
  while ( v27 );
  if ( v28 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      v10 = v39;
    }
    else
    {
      v10 = v39;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
          (_DWORD)pv,
          (__int64)v39);
    }
    TargetMediaType = BlbutilDuplicateString(a1, a6, 0);
    if ( TargetMediaType < 0 )
      goto LABEL_21;
    v22 = 1;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v30 = 37;
LABEL_117:
      WPP_SF_S(v29[2], v30, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids, *a6);
    }
  }
  else
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v30 = 38;
      goto LABEL_117;
    }
  }
LABEL_119:
  TargetMediaType = BlbGetBackupRootDirectory(*a6, *((unsigned __int16 **)a3 + 19), &v42);
  if ( TargetMediaType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = (LPVOID *)a6;
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
        (unsigned int)*a6,
        *((_QWORD *)a3 + 19),
        TargetMediaType);
      v11 = v42;
      goto LABEL_89;
    }
    v11 = v42;
    goto LABEL_88;
  }
  if ( *((_DWORD *)a3 + 48) || *((_DWORD *)a3 + 49) || !*((_BYTE *)a3 + 168) )
  {
    v11 = v42;
    appended = BlbutilDuplicateString(v42, &v38, 0);
  }
  else
  {
    v11 = v42;
    appended = BlbutilAppendString(v42, L"\\SystemStateBackup", &v38);
  }
  TargetMediaType = appended;
  if ( appended < 0
    || (TargetMediaType = BlbGetBackupSetDirectory(v38, *(struct _FILETIME *)((char *)a3 + 100), a7), TargetMediaType < 0) )
  {
LABEL_88:
    v15 = (LPVOID *)a6;
LABEL_89:
    v10 = v39;
    goto LABEL_90;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      41,
      (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
      (unsigned int)*a7,
      (__int64)*a6,
      v16);
  }
  v33 = (BackupFeatures & 0x200) != 0;
  v13 = (LPVOID *)a7;
  if ( !v33 )
  {
    v36 = 0;
    TargetMediaType = BlbCheckDirectory(*a7, &v36);
    if ( TargetMediaType >= 0 && !v36 )
    {
      v12 = v38;
      v34 = v22 == 0;
      v10 = v39;
      if ( v34 )
        TargetMediaType = v23 != 0 ? -2139619271 : -2139619289;
      else
        TargetMediaType = -2139619261;
LABEL_10:
      v15 = (LPVOID *)a6;
      goto LABEL_92;
    }
  }
  v15 = (LPVOID *)a6;
  v10 = v39;
LABEL_91:
  v12 = v38;
LABEL_92:
  CBlbImpersonationHelper::Revert(a4);
  if ( TargetMediaType < 0 )
  {
    if ( *a5 )
    {
      CoTaskMemFree(*a5);
      *a5 = 0;
    }
    if ( *v15 )
    {
      CoTaskMemFree(*v15);
      *v15 = 0;
    }
    if ( *v13 )
    {
      CoTaskMemFree(*v13);
      *v13 = 0;
    }
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v10 )
    CoTaskMemFree(v10);
  if ( v11 )
    CoTaskMemFree(v11);
  if ( v12 )
    CoTaskMemFree(v12);
  if ( TargetMediaType >= 0 )
    goto LABEL_143;
  v31 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)TargetMediaType;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
      (_DWORD)a1,
      TargetMediaType);
LABEL_143:
    v31 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 1) != 0 && *((_BYTE *)v31 + 25) >= 4u )
    WPP_SF_(v31[2], 43, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids);
  return (unsigned int)TargetMediaType;
}

```

## disassembly

```asm
0x140104e8c  mov     rax, rsp
0x140104e8f  mov     [rax+10h], rbx
0x140104e93  mov     [rax+20h], r9
0x140104e97  mov     [rax+8], rcx
0x140104e9b  push    rbp
0x140104e9c  push    rsi
0x140104e9d  push    rdi
0x140104e9e  push    r12
0x140104ea0  push    r13
0x140104ea2  push    r14
0x140104ea4  push    r15
0x140104ea6  lea     rbp, [rax-47h]
0x140104eaa  sub     rsp, 0C0h
0x140104eb1  mov     r14, r8
0x140104eb4  mov     dil, dl
0x140104eb7  mov     rbx, rcx
0x140104eba  lea     rax, WPP_GLOBAL_Control
0x140104ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x140104ec8  cmp     rcx, rax
0x140104ecb  jz      short loc_140104EEE
0x140104ecd  test    byte ptr [rcx+1Ch], 1
0x140104ed1  jz      short loc_140104EEE
0x140104ed3  cmp     byte ptr [rcx+19h], 4
0x140104ed7  jb      short loc_140104EEE
0x140104ed9  mov     edx, 1Ch
0x140104ede  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x140104ee5  mov     rcx, [rcx+10h]
0x140104ee9  call    WPP_SF_
0x140104eee  xor     ecx, ecx
0x140104ef0  mov     [rbp+3Fh+var_BF], cl
0x140104ef3  mov     [rsp+0F0h+var_C0], cl
0x140104ef7  mov     [rbp+3Fh+pv], rcx
0x140104efb  mov     esi, ecx
0x140104efd  mov     [rbp+3Fh+var_B0], rcx
0x140104f01  mov     [rbp+3Fh+var_A0], ecx
0x140104f04  mov     r12d, ecx
0x140104f07  mov     [rbp+3Fh+var_98], rcx
0x140104f0b  mov     r15d, ecx
0x140104f0e  mov     [rbp+3Fh+var_B8], rcx
0x140104f12  mov     rax, [rbp+3Fh+arg_20]
0x140104f16  mov     [rax], rcx
0x140104f19  mov     rax, [rbp+3Fh+arg_28]
0x140104f1d  mov     [rax], rcx
0x140104f20  mov     r13, [rbp+3Fh+arg_30]
0x140104f24  mov     [r13+0], rcx
0x140104f28  lea     r8, [rbp+3Fh+var_A0]; enum _BLB_MEDIA_TYPE *
0x140104f2c  mov     rdx, [rbp+3Fh+arg_18]; this
0x140104f30  mov     rcx, rbx; unsigned __int16 *
0x140104f33  call    ?BlbQueryTargetMediaType@@YAJPEAGPEAVCBlbImpersonationHelper@@PEAW4_BLB_MEDIA_TYPE@@@Z; BlbQueryTargetMediaType(ushort *,CBlbImpersonationHelper *,_BLB_MEDIA_TYPE *)
0x140104f38  mov     ebx, eax
0x140104f3a  test    eax, eax
0x140104f3c  jns     short loc_140104F82
0x140104f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140104f45  lea     rax, WPP_GLOBAL_Control
0x140104f4c  cmp     rcx, rax
0x140104f4f  jz      short loc_140104F79
0x140104f51  test    byte ptr [rcx+1Ch], 1
0x140104f55  jz      short loc_140104F79
0x140104f57  cmp     byte ptr [rcx+19h], 2
0x140104f5b  jb      short loc_140104F79
0x140104f5d  lea     edx, [r15+1Dh]
0x140104f61  mov     [rsp+0F0h+var_D0], ebx
0x140104f65  mov     r9, [rbp+3Fh+pv]
0x140104f69  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x140104f70  mov     rcx, [rcx+10h]
0x140104f74  call    WPP_SF_Sd
0x140104f79  mov     rdi, [rbp+3Fh+arg_28]
0x140104f7d  jmp     loc_1401053E8
0x140104f82  mov     r9d, [r14+1Ch]
0x140104f86  mov     r15d, [rbp+3Fh+var_A0]
0x140104f8a  cmp     r15d, r9d
0x140104f8d  jz      short loc_140104FC8
0x140104f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140104f96  lea     rax, WPP_GLOBAL_Control
0x140104f9d  cmp     rcx, rax
0x140104fa0  jz      short loc_140104FC8
0x140104fa2  test    byte ptr [rcx+1Ch], 1
0x140104fa6  jz      short loc_140104FC8
0x140104fa8  cmp     byte ptr [rcx+19h], 4
0x140104fac  jb      short loc_140104FC8
0x140104fae  mov     edx, 1Eh
0x140104fb3  mov     [rsp+0F0h+var_D0], r15d
0x140104fb8  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x140104fbf  mov     rcx, [rcx+10h]
0x140104fc3  call    WPP_SF_dd
0x140104fc8  mov     ecx, r15d
0x140104fcb  call    ?BlbutilGetBackupFeatures@@YAKW4_BLB_MEDIA_TYPE@@@Z; BlbutilGetBackupFeatures(_BLB_MEDIA_TYPE)
0x140104fd0  mov     r13d, eax
0x140104fd3  cmp     r15d, 4
0x140104fd7  jnz     short loc_140105030
0x140104fd9  xor     edx, edx; unsigned __int8
0x140104fdb  mov     rcx, [rbp+3Fh+arg_18]; this
0x140104fdf  call    ?ImpersonateCaller@CBlbImpersonationHelper@@QEAAJE@Z; CBlbImpersonationHelper::ImpersonateCaller(uchar)
0x140104fe4  mov     ebx, eax
0x140104fe6  test    eax, eax
0x140104fe8  js      short loc_14010500D
0x140104fea  lea     r8, [rbp+3Fh+var_BF]; unsigned __int8 *
0x140104fee  xor     edx, edx; unsigned __int8
0x140104ff0  mov     rdi, [rbp+3Fh+arg_0]
0x140104ff4  mov     rcx, rdi; unsigned __int16 *
0x140104ff7  call    ?BlbutilCheckNetworkShare@@YAJPEBGEPEAE@Z; BlbutilCheckNetworkShare(ushort const *,uchar,uchar *)
0x140104ffc  mov     ebx, eax
0x140104ffe  test    eax, eax
0x140105000  js      short loc_14010500D
0x140105002  cmp     [rbp+3Fh+var_BF], sil
0x140105006  jnz     short loc_140105016
0x140105008  mov     ebx, 8078000Ch
0x14010500d  mov     rdi, [rbp+3Fh+arg_28]
0x140105011  jmp     loc_1401053E0
0x140105016  xor     r8d, r8d; unsigned __int64
0x140105019  mov     rdx, [rbp+3Fh+arg_20]; unsigned __int16 **
0x14010501d  mov     rcx, rdi; unsigned __int16 *
0x140105020  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140105025  mov     ebx, eax
0x140105027  test    eax, eax
0x140105029  js      short loc_14010500D
0x14010502b  jmp     loc_140105241
0x140105030  xorps   xmm0, xmm0
0x140105033  movdqa  [rbp+3Fh+var_90], xmm0
0x140105038  xorps   xmm1, xmm1
0x14010503b  movdqa  [rbp+3Fh+var_80], xmm1
0x140105040  xor     eax, eax
0x140105042  mov     [rbp+3Fh+var_70], rax
0x140105046  mov     [rbp+3Fh+var_68], 0Ah
0x14010504d  mov     [rbp+3Fh+var_58], rax
0x140105051  mov     [rbp+3Fh+var_50], eax
0x140105054  mov     [rbp+3Fh+var_48], rax
0x140105058  mov     [rbp+3Fh+var_40], al
0x14010505b  mov     [rbp+3Fh+var_60], eax
0x14010505e  lea     r8, [rbp+3Fh+pv]; unsigned __int16 **
0x140105062  lea     rdx, asc_14013C090; "\\"
0x140105069  mov     rcx, [rbp+3Fh+arg_0]; unsigned __int16 *
0x14010506d  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x140105072  mov     ebx, eax
0x140105074  test    eax, eax
0x140105076  jns     short loc_140105083
0x140105078  lea     rcx, [rbp+3Fh+var_90]; this
0x14010507c  call    ??1CBlbVdsHelperLibrary@@QEAA@XZ; CBlbVdsHelperLibrary::~CBlbVdsHelperLibrary(void)
0x140105081  jmp     short loc_14010500D
0x140105083  test    dil, dil
0x140105086  jz      short loc_1401050F8
0x140105088  lea     eax, [r15-2]
0x14010508c  cmp     eax, 1
0x14010508f  ja      short loc_1401050F8
0x140105091  mov     r8d, 1; unsigned int
0x140105097  lea     rdx, [rbp+3Fh+pv]; unsigned __int16 **
0x14010509b  lea     rcx, [rbp+3Fh+var_90]; this
0x14010509f  call    ?MountVolumes@CBlbVdsHelperLibrary@@QEAAJPEAPEAGI@Z; CBlbVdsHelperLibrary::MountVolumes(ushort * *,uint)
0x1401050a4  mov     edi, eax
0x1401050a6  test    eax, eax
0x1401050a8  jns     short loc_1401050F8
0x1401050aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1401050b1  lea     rax, WPP_GLOBAL_Control
0x1401050b8  cmp     rcx, rax
0x1401050bb  jz      short loc_1401050E6
0x1401050bd  test    byte ptr [rcx+1Ch], 1
0x1401050c1  jz      short loc_1401050E6
0x1401050c3  cmp     byte ptr [rcx+19h], 2
0x1401050c7  jb      short loc_1401050E6
0x1401050c9  mov     edx, 1Fh
0x1401050ce  mov     [rsp+0F0h+var_D0], edi
0x1401050d2  mov     r9, [rbp+3Fh+pv]
0x1401050d6  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x1401050dd  mov     rcx, [rcx+10h]
0x1401050e1  call    WPP_SF_Sd
0x1401050e6  mov     ebx, 8078000Ch
0x1401050eb  cmp     edi, 8078009Ch
0x1401050f1  cmovnz  edi, ebx
0x1401050f4  mov     ebx, edi
0x1401050f6  jmp     short loc_140105078
0x1401050f8  lea     r8, [rbp+3Fh+var_BF]; unsigned __int8 *
0x1401050fc  xor     edx, edx; unsigned int
0x1401050fe  mov     rcx, [rbp+3Fh+pv]; String2
0x140105102  call    ?BlbIsVolumeNameValid@@YAJPEAGKPEAE@Z; BlbIsVolumeNameValid(ushort *,ulong,uchar *)
0x140105107  mov     ebx, eax
0x140105109  test    eax, eax
0x14010510b  js      loc_140105078
0x140105111  cmp     [rbp+3Fh+var_BF], 0
0x140105115  jnz     short loc_140105121
0x140105117  mov     ebx, 8078000Ch
0x14010511c  jmp     loc_140105078
0x140105121  lea     r8, [rsp+0F0h+var_C0]; unsigned __int8 *
0x140105126  lea     rdx, [rbp+3Fh+var_BF]; unsigned __int8 *
0x14010512a  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x14010512e  call    ?BlbIsTargetValid@@YAJPEAGPEAE1@Z; BlbIsTargetValid(ushort *,uchar *,uchar *)
0x140105133  mov     ebx, eax
0x140105135  test    eax, eax
0x140105137  jns     short loc_140105186
0x140105139  mov     rcx, cs:WPP_GLOBAL_Control
0x140105140  lea     rax, WPP_GLOBAL_Control
0x140105147  cmp     rcx, rax
0x14010514a  jz      loc_140105078
0x140105150  test    byte ptr [rcx+1Ch], 1
0x140105154  jz      loc_140105078
0x14010515a  cmp     byte ptr [rcx+19h], 2
0x14010515e  jb      loc_140105078
0x140105164  mov     edx, 20h ; ' '
0x140105169  mov     [rsp+0F0h+var_D0], ebx
0x14010516d  mov     r9, [rbp+3Fh+pv]
0x140105171  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x140105178  mov     rcx, [rcx+10h]
0x14010517c  call    WPP_SF_Sd
0x140105181  jmp     loc_140105078
0x140105186  cmp     [rsp+0F0h+var_C0], 0
0x14010518b  jz      short loc_140105117
0x14010518d  mov     rdx, [rbp+3Fh+arg_20]; unsigned __int16 **
0x140105191  mov     rcx, [rbp+3Fh+pv]; lpszVolumeName
0x140105195  call    ?BlbQueryVolumeAccessPath@@YAJPEAGPEAPEAG@Z; BlbQueryVolumeAccessPath(ushort *,ushort * *)
0x14010519a  mov     ebx, eax
0x14010519c  test    eax, eax
0x14010519e  jns     short loc_1401051D2
0x1401051a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1401051a7  lea     rax, WPP_GLOBAL_Control
0x1401051ae  cmp     rcx, rax
0x1401051b1  jz      loc_140105078
0x1401051b7  test    byte ptr [rcx+1Ch], 1
0x1401051bb  jz      loc_140105078
0x1401051c1  cmp     byte ptr [rcx+19h], 2
0x1401051c5  jb      loc_140105078
0x1401051cb  mov     edx, 21h ; '!'
0x1401051d0  jmp     short loc_140105169
0x1401051d2  mov     ecx, r15d
0x1401051d5  call    ?BlbutilGetBackupFeatures@@YAKW4_BLB_MEDIA_TYPE@@@Z; BlbutilGetBackupFeatures(_BLB_MEDIA_TYPE)
0x1401051da  bt      eax, 9
0x1401051de  jb      short loc_140105238
0x1401051e0  mov     [rsp+0F0h+var_C0], 0
0x1401051e5  lea     rdx, [rsp+0F0h+var_C0]; unsigned __int8 *
0x1401051ea  mov     rcx, [rbp+3Fh+pv]; unsigned __int16 *
0x1401051ee  call    ?BlbIsVolumeBitlocked@@YAJPEAGPEAE@Z; BlbIsVolumeBitlocked(ushort *,uchar *)
0x1401051f3  test    eax, eax
0x1401051f5  jns     loc_1401052F5
0x1401051fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140105202  lea     rdx, WPP_GLOBAL_Control
0x140105209  cmp     rcx, rdx
0x14010520c  jz      short loc_140105238
0x14010520e  test    byte ptr [rcx+1Ch], 1
0x140105212  jz      short loc_140105238
0x140105214  cmp     byte ptr [rcx+19h], 3
0x140105218  jb      short loc_140105238
0x14010521a  mov     edx, 22h ; '"'
0x14010521f  mov     [rsp+0F0h+var_D0], eax
0x140105223  mov     r9, [rbp+3Fh+pv]
0x140105227  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x14010522e  mov     rcx, [rcx+10h]
0x140105232  call    WPP_SF_Sd
0x140105237  nop
0x140105238  lea     rcx, [rbp+3Fh+var_90]; this
0x14010523c  call    ??1CBlbVdsHelperLibrary@@QEAA@XZ; CBlbVdsHelperLibrary::~CBlbVdsHelperLibrary(void)
0x140105241  xor     sil, sil
0x140105244  xor     dil, dil
0x140105247  test    r13b, 8
0x14010524b  jz      loc_140105525
0x140105251  lea     rcx, [r14+6Ch]; struct _GUID *
0x140105255  mov     rax, [rcx]
0x140105258  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14010525f  jnz     short loc_14010526C
0x140105261  mov     rax, [rcx+8]
0x140105265  sub     rax, qword ptr cs:GUID_NULL.Data4
0x14010526c  test    rax, rax
0x14010526f  jz      loc_1401054C8
0x140105275  lea     r8, [rbp+3Fh+var_B0]; unsigned __int16 **
0x140105279  mov     rdx, [rbp+3Fh+arg_28]; unsigned __int16 **
0x14010527d  call    ?BlbGetSnapshotDeviceName@@YAJPEAU_GUID@@PEAPEAG1@Z; BlbGetSnapshotDeviceName(_GUID *,ushort * *,ushort * *)
0x140105282  mov     ebx, eax
0x140105284  test    eax, eax
0x140105286  js      loc_1401053CD
0x14010528c  mov     r9, [rbp+3Fh+pv]
0x140105290  mov     rax, r9
0x140105293  mov     r8, [rbp+3Fh+var_B0]
0x140105297  sub     r8, r9
0x14010529a  movzx   edx, word ptr [rax]
0x14010529d  movzx   ecx, word ptr [rax+r8]
0x1401052a2  sub     edx, ecx
0x1401052a4  jnz     short loc_1401052AE
0x1401052a6  add     rax, 2
0x1401052aa  test    ecx, ecx
0x1401052ac  jnz     short loc_14010529A
0x1401052ae  test    edx, edx
0x1401052b0  jz      loc_140105398
0x1401052b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1401052bd  lea     rax, WPP_GLOBAL_Control
0x1401052c4  cmp     rcx, rax
0x1401052c7  jz      short loc_140105342
0x1401052c9  test    byte ptr [rcx+1Ch], 1
0x1401052cd  jz      short loc_140105342
0x1401052cf  mov     rsi, [rbp+3Fh+var_B0]
0x1401052d3  cmp     byte ptr [rcx+19h], 2
0x1401052d7  jb      short loc_140105346
0x1401052d9  mov     edx, 24h ; '$'
0x1401052de  mov     qword ptr [rsp+0F0h+var_D0], rsi
0x1401052e3  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x1401052ea  mov     rcx, [rcx+10h]
0x1401052ee  call    WPP_SF_SS
0x1401052f3  jmp     short loc_140105346
0x1401052f5  cmp     [rsp+0F0h+var_C0], 0
0x1401052fa  jz      loc_140105238
0x140105300  mov     rcx, cs:WPP_GLOBAL_Control
0x140105307  lea     rax, WPP_GLOBAL_Control
0x14010530e  cmp     rcx, rax
0x140105311  jz      short loc_140105338
  ... truncated ...
```
