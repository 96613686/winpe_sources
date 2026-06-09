# BlbQueryBackupSize(ushort *,_BLBCAT_BACKUP_SET_INFO *,_GUID *,ulong *,uchar *,ulong,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1401068d4`
- end: `0x140106e59`
- name: `?BlbQueryBackupSize@@YAJPEAGPEAU_BLBCAT_BACKUP_SET_INFO@@PEAU_GUID@@PEAKPEAEKPEA_K5@Z`
- size: `1413`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, struct _BLBCAT_BACKUP_SET_INFO *@<rdx>, struct _GUID *@<r8>, unsigned int *@<r9>, unsigned __int8 *, unsigned int, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x14001d750`
- `0x14010ff8c`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x1400142d8`
- `0x14003c434`
- `0x1400881ac`
- `0x1400f25c0`
- `0x1400ffcc0`
- `0x140101e78`
- `0x140102128`
- `0x1401068d4`
- `0x140107c28`
- `0x140107ccc`
- `0x140134d20`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x140106ada`
- `KERNEL32!GetFileAttributesExW` at `0x140106c22`
- `KERNEL32!GetFileAttributesExW` at `0x140106ada`
- `KERNEL32!GetFileAttributesExW` at `0x140106c22`
- `KERNEL32!GetLastError` at `0x140106ae8`
- `KERNEL32!GetLastError` at `0x140106c30`
- `KERNEL32!GetLastError` at `0x140106ae8`
- `KERNEL32!GetLastError` at `0x140106c30`
- `ole32!CoTaskMemFree` at `0x140106a72`
- `ole32!CoTaskMemFree` at `0x140106bcb`
- `ole32!CoTaskMemFree` at `0x140106d90`
- `ole32!CoTaskMemFree` at `0x140106da8`
- `ole32!CoTaskMemFree` at `0x140106db6`
- `ole32!CoTaskMemFree` at `0x140106a72`
- `ole32!CoTaskMemFree` at `0x140106bcb`
- `ole32!CoTaskMemFree` at `0x140106d90`
- `ole32!CoTaskMemFree` at `0x140106da8`
- `ole32!CoTaskMemFree` at `0x140106db6`

## pseudocode

```c
__int64 __fastcall BlbQueryBackupSize(
        unsigned __int16 *a1,
        struct _BLBCAT_BACKUP_SET_INFO *a2,
        struct _GUID *a3,
        unsigned int *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int64 *a7,
        unsigned __int64 *a8)
{
  unsigned __int16 *v8; // r12
  unsigned __int16 *v9; // r14
  WCHAR *v10; // rdi
  int appended; // ebx
  int File; // eax
  PVOID *v13; // r10
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // r12
  unsigned __int8 *v17; // r13
  struct _GUID *v18; // rsi
  unsigned int *v19; // r15
  __int64 v20; // r8
  signed int LastError; // eax
  unsigned int v22; // ebx
  BlbGuidStr *v23; // rbx
  unsigned int v24; // eax
  unsigned int v25; // r8d
  BlbGuidStr *v26; // rax
  int v27; // edx
  int v28; // r8d
  bool v29; // zf
  PVOID *v30; // rcx
  unsigned __int8 v32[8]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v33; // [rsp+38h] [rbp-C8h]
  unsigned __int64 v34; // [rsp+40h] [rbp-C0h]
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v36; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  struct _BLBCAT_BACKUP_SET_INFO *v38; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v39; // [rsp+68h] [rbp-98h]
  unsigned int *v40; // [rsp+70h] [rbp-90h]
  struct _GUID *v41; // [rsp+78h] [rbp-88h]
  unsigned __int64 *v42; // [rsp+80h] [rbp-80h]
  unsigned __int64 *v43; // [rsp+88h] [rbp-78h]
  struct _GUID v44; // [rsp+90h] [rbp-70h] BYREF
  __int128 FileInformation; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v46; // [rsp+B0h] [rbp-50h]
  unsigned int v47; // [rsp+C0h] [rbp-40h]
  UUID Uuid; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v49[112]; // [rsp+E0h] [rbp-20h] BYREF
  char v50[112]; // [rsp+150h] [rbp+50h] BYREF

  v8 = a1;
  v42 = a7;
  v43 = a8;
  v40 = a4;
  v41 = a3;
  v38 = a2;
  v39 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids);
  }
  v9 = 0;
  v10 = 0;
  v36 = 0;
  pv = 0;
  lpFileName = 0;
  if ( !a7 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbbackuptargetutils.cpp", 0x6CFu, "pullBackupSize");
  *a7 = 0;
  *a8 = 0;
  appended = BlbAppendBackupDateDirectory(v8, 0, (unsigned __int16 **)&pv);
  if ( appended < 0 )
    goto LABEL_61;
  File = BlbFindFile((unsigned __int16 *)pv, &v36);
  v9 = v36;
  appended = File;
  if ( File < 0 || !v36 )
    goto LABEL_61;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  v14 = 0;
  v15 = 0;
  v33 = 0;
  v34 = 0;
  v36 = 0;
  FileInformation = 0;
  v47 = 0;
  v16 = 0;
  v46 = 0;
  while ( (unsigned int)v16 < a6 )
  {
    v17 = &a5[(unsigned int)v16];
    if ( *v17 )
    {
      if ( v10 )
      {
        CoTaskMemFree(v10);
        lpFileName = 0;
      }
      v18 = &v41[(unsigned int)v16];
      v19 = &v40[v16];
      appended = BlbAppendBagFile(v9, v18, *v19, L".vhdx", (unsigned __int16 **)&lpFileName);
      if ( appended < 0 )
      {
LABEL_57:
        v10 = (WCHAR *)lpFileName;
        goto LABEL_58;
      }
      v10 = (WCHAR *)lpFileName;
      v47 = 0;
      FileInformation = 0;
      v46 = 0;
      if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
      {
        LastError = GetLastError();
        v22 = LastError;
        if ( LastError > 0 )
          v22 = (unsigned __int16)LastError | 0x80070000;
        if ( v22 != -2147024894 || !v38 || (*(_BYTE *)v19 & 1) != 0 )
        {
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v26 = BlbGuidStr::BlbGuidStr((BlbGuidStr *)v49, v18);
            WPP_SF_DqS(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, v28, v22, (char)v38, (__int64)v26);
LABEL_40:
            v13 = (PVOID *)WPP_GLOBAL_Control;
          }
LABEL_41:
          appended = 0;
LABEL_55:
          v14 = v33;
          v15 = v34;
          goto LABEL_56;
        }
        v32[0] = 0;
        Uuid = GUID_NULL;
        v44 = *v18;
        appended = BlbGetVolumeGuidUsedInLastBackup(&v44, v38, &Uuid, v32);
        if ( appended < 0 )
          goto LABEL_58;
        if ( !v32[0] )
          goto LABEL_54;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v23 = BlbGuidStr::BlbGuidStr((BlbGuidStr *)v50, &Uuid);
          v24 = (unsigned int)BlbGuidStr::BlbGuidStr((BlbGuidStr *)v49, v18);
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
            v24,
            (__int64)v23);
        }
        if ( v10 )
        {
          CoTaskMemFree(v10);
          lpFileName = 0;
        }
        v25 = *v19;
        v47 = 0;
        FileInformation = 0;
        v46 = 0;
        appended = BlbAppendBagFile(v9, &Uuid, v25, L".vhdx", (unsigned __int16 **)&lpFileName);
        if ( appended < 0 )
          goto LABEL_57;
        v10 = (WCHAR *)lpFileName;
        if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
        {
          GetLastError();
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids);
            goto LABEL_40;
          }
          goto LABEL_41;
        }
      }
      v14 = v33;
      v36 = (unsigned __int16 *)__PAIR64__(HIDWORD(v46), v47);
      v15 = __PAIR64__(HIDWORD(v46), v47) + v34;
      v29 = *v17 == 0;
      v34 += __PAIR64__(HIDWORD(v46), v47);
      if ( !v29 && (*(_BYTE *)v19 & 4) != 0 )
      {
        v14 = __PAIR64__(HIDWORD(v46), v47) + v33;
        v33 += __PAIR64__(HIDWORD(v46), v47);
      }
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_did(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          v20,
          (unsigned int)v16,
          __PAIR64__(HIDWORD(v46), v47),
          (*v19 >> 2) & 1);
        goto LABEL_54;
      }
    }
    else if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 && *((_BYTE *)v13 + 25) >= 4u )
    {
      WPP_SF_d(v13[2], 62, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids);
LABEL_54:
      v13 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_55;
    }
LABEL_56:
    v16 = (unsigned int)(v16 + 1);
  }
  *v42 = v15;
  *v43 = v14;
LABEL_58:
  if ( v10 )
    CoTaskMemFree(v10);
  LODWORD(v8) = (_DWORD)v39;
LABEL_61:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v9 )
    CoTaskMemFree(v9);
  if ( appended >= 0 )
  {
LABEL_70:
    v30 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_71;
  }
  v30 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        (unsigned int)&WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids,
        (_DWORD)v8,
        appended);
      goto LABEL_70;
    }
LABEL_71:
    if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 && *((_BYTE *)v30 + 25) >= 4u )
      WPP_SF_(v30[2], 68, &WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1401068d4  push    rbp
0x1401068d6  push    rbx
0x1401068d7  push    rsi
0x1401068d8  push    rdi
0x1401068d9  push    r12
0x1401068db  push    r13
0x1401068dd  push    r14
0x1401068df  push    r15
0x1401068e1  lea     rbp, [rsp-0D8h]
0x1401068e9  sub     rsp, 1D8h
0x1401068f0  mov     rax, cs:__security_cookie
0x1401068f7  xor     rax, rsp
0x1401068fa  mov     [rbp+110h+var_50], rax
0x140106901  mov     rsi, [rbp+110h+arg_30]
0x140106908  mov     r12, rcx
0x14010690b  mov     r15, [rbp+110h+arg_38]
0x140106912  mov     [rbp+110h+var_190], rsi
0x140106916  mov     [rbp+110h+var_188], r15
0x14010691a  mov     [rsp+210h+var_1A0], r9
0x14010691f  mov     [rsp+210h+var_198], r8
0x140106924  mov     [rsp+210h+var_1B0], rdx
0x140106929  mov     [rsp+210h+var_1A8], rcx
0x14010692e  mov     rcx, cs:WPP_GLOBAL_Control
0x140106935  lea     r13, WPP_GLOBAL_Control
0x14010693c  cmp     rcx, r13
0x14010693f  jz      short loc_140106962
0x140106941  test    byte ptr [rcx+1Ch], 1
0x140106945  jz      short loc_140106962
0x140106947  cmp     byte ptr [rcx+19h], 4
0x14010694b  jb      short loc_140106962
0x14010694d  mov     rcx, [rcx+10h]
0x140106951  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x140106958  mov     edx, 3Dh ; '='
0x14010695d  call    WPP_SF_
0x140106962  xor     r14d, r14d
0x140106965  xor     edi, edi
0x140106967  mov     [rsp+210h+var_1C0], r14
0x14010696c  mov     [rsp+210h+pv], r14
0x140106971  mov     [rsp+210h+lpFileName], rdi
0x140106976  test    rsi, rsi
0x140106979  jnz     short loc_140106993
0x14010697b  lea     r8, aPullbackupsize; "pullBackupSize"
0x140106982  mov     edx, 6CFh; unsigned int
0x140106987  lea     rcx, aBaseStorBlbEng_16; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x14010698e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140106993  mov     [rsi], rdi
0x140106996  lea     r8, [rsp+210h+pv]; unsigned __int16 **
0x14010699b  xor     edx, edx; lpFileTime
0x14010699d  mov     [r15], rdi
0x1401069a0  mov     rcx, r12; unsigned __int16 *
0x1401069a3  call    ?BlbAppendBackupDateDirectory@@YAJPEAGPEAU_FILETIME@@PEAPEAG@Z; BlbAppendBackupDateDirectory(ushort *,_FILETIME *,ushort * *)
0x1401069a8  mov     ebx, eax
0x1401069aa  test    eax, eax
0x1401069ac  js      loc_140106D9B
0x1401069b2  mov     rcx, [rsp+210h+pv]; unsigned __int16 *
0x1401069b7  lea     rdx, [rsp+210h+var_1C0]; unsigned __int16 **
0x1401069bc  call    ?BlbFindFile@@YAJPEAGPEAPEAG@Z; BlbFindFile(ushort *,ushort * *)
0x1401069c1  mov     r14, [rsp+210h+var_1C0]
0x1401069c6  mov     ebx, eax
0x1401069c8  test    eax, eax
0x1401069ca  js      loc_140106D9B
0x1401069d0  test    r14, r14
0x1401069d3  jz      loc_140106D9B
0x1401069d9  mov     r10, cs:WPP_GLOBAL_Control
0x1401069e0  xor     ecx, ecx
0x1401069e2  xor     edx, edx
0x1401069e4  mov     [rsp+210h+var_1D8], rcx
0x1401069e9  xorps   xmm0, xmm0
0x1401069ec  mov     [rsp+210h+var_1D0], rdx
0x1401069f1  xor     eax, eax
0x1401069f3  mov     [rsp+210h+var_1C0], rcx
0x1401069f8  movups  [rbp+110h+FileInformation], xmm0
0x1401069fc  mov     [rbp+110h+var_150], eax
0x1401069ff  xor     r12d, r12d
0x140106a02  movups  [rbp+110h+var_160], xmm0
0x140106a06  cmp     r12d, [rbp+110h+arg_28]
0x140106a0d  jnb     loc_140106E46
0x140106a13  mov     r13, [rbp+110h+arg_20]
0x140106a1a  mov     esi, r12d
0x140106a1d  add     r13, rsi
0x140106a20  cmp     byte ptr [r13+0], 0
0x140106a25  jnz     short loc_140106A6A
0x140106a27  lea     r13, WPP_GLOBAL_Control
0x140106a2e  cmp     r10, r13
0x140106a31  jz      loc_140106D74
0x140106a37  test    byte ptr [r10+1Ch], 1
0x140106a3c  jz      loc_140106D74
0x140106a42  cmp     byte ptr [r10+19h], 4
0x140106a47  jb      loc_140106D74
0x140106a4d  mov     rcx, [r10+10h]
0x140106a51  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x140106a58  mov     edx, 3Eh ; '>'
0x140106a5d  mov     r9d, r12d
0x140106a60  call    WPP_SF_d
0x140106a65  jmp     loc_140106D63
0x140106a6a  test    rdi, rdi
0x140106a6d  jz      short loc_140106A81
0x140106a6f  mov     rcx, rdi; pv
0x140106a72  call    cs:__imp_CoTaskMemFree
0x140106a78  mov     [rsp+210h+lpFileName], 0
0x140106a81  mov     rax, [rsp+210h+var_1A0]
0x140106a86  lea     r9, aVhdx; ".vhdx"
0x140106a8d  shl     rsi, 4
0x140106a91  mov     rcx, r14; unsigned __int16 *
0x140106a94  add     rsi, [rsp+210h+var_198]
0x140106a99  mov     rdx, rsi; Uuid
0x140106a9c  lea     r15, [rax+r12*4]
0x140106aa0  mov     r8d, [r15]; unsigned int
0x140106aa3  lea     rax, [rsp+210h+lpFileName]
0x140106aa8  mov     [rsp+210h+var_1F0], rax; unsigned __int16 **
0x140106aad  call    ?BlbAppendBagFile@@YAJPEAGPEAU_GUID@@KPEBGPEAPEAG@Z; BlbAppendBagFile(ushort *,_GUID *,ulong,ushort const *,ushort * *)
0x140106ab2  mov     ebx, eax
0x140106ab4  test    eax, eax
0x140106ab6  js      loc_140106D7C
0x140106abc  mov     rdi, [rsp+210h+lpFileName]
0x140106ac1  lea     r8, [rbp+110h+FileInformation]; lpFileInformation
0x140106ac5  xorps   xmm0, xmm0
0x140106ac8  xor     eax, eax
0x140106aca  mov     rcx, rdi; lpFileName
0x140106acd  mov     [rbp+110h+var_150], eax
0x140106ad0  xor     edx, edx; fInfoLevelId
0x140106ad2  movups  [rbp+110h+FileInformation], xmm0
0x140106ad6  movups  [rbp+110h+var_160], xmm0
0x140106ada  call    cs:__imp_GetFileAttributesExW
0x140106ae0  test    eax, eax
0x140106ae2  jnz     loc_140106CEA
0x140106ae8  call    cs:__imp_GetLastError
0x140106aee  mov     ebx, eax
0x140106af0  test    eax, eax
0x140106af2  jle     short loc_140106AFD
0x140106af4  movzx   ebx, ax
0x140106af7  or      ebx, 80070000h
0x140106afd  cmp     ebx, 80070002h
0x140106b03  jnz     loc_140106C99
0x140106b09  mov     rax, [rsp+210h+var_1B0]
0x140106b0e  test    rax, rax
0x140106b11  jz      loc_140106C99
0x140106b17  test    byte ptr [r15], 1
0x140106b1b  jnz     loc_140106C99
0x140106b21  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140106b28  lea     r9, [rsp+210h+var_1E0]; unsigned __int8 *
0x140106b2d  mov     [rsp+210h+var_1E0], 0
0x140106b32  lea     r8, [rbp+110h+Uuid]; struct _GUID *
0x140106b36  mov     rdx, rax; struct _BLBCAT_BACKUP_SET_INFO *
0x140106b39  movdqu  xmmword ptr [rbp+110h+Uuid.Data1], xmm0
0x140106b3e  lea     rcx, [rbp+110h+var_180]; struct _GUID *
0x140106b42  movups  xmm0, xmmword ptr [rsi]
0x140106b45  movdqu  xmmword ptr [rbp+110h+var_180.Data1], xmm0
0x140106b4a  call    ?BlbGetVolumeGuidUsedInLastBackup@@YAJU_GUID@@PEAU_BLBCAT_BACKUP_SET_INFO@@PEAU1@PEAE@Z; BlbGetVolumeGuidUsedInLastBackup(_GUID,_BLBCAT_BACKUP_SET_INFO *,_GUID *,uchar *)
0x140106b4f  mov     ebx, eax
0x140106b51  test    eax, eax
0x140106b53  js      loc_140106D81
0x140106b59  cmp     [rsp+210h+var_1E0], 0
0x140106b5e  jz      loc_140106C8D
0x140106b64  mov     rax, cs:WPP_GLOBAL_Control
0x140106b6b  lea     rcx, WPP_GLOBAL_Control
0x140106b72  cmp     rax, rcx
0x140106b75  jz      short loc_140106BC3
0x140106b77  test    byte ptr [rax+1Ch], 1
0x140106b7b  jz      short loc_140106BC3
0x140106b7d  cmp     byte ptr [rax+19h], 4
0x140106b81  jb      short loc_140106BC3
0x140106b83  lea     rdx, [rbp+110h+Uuid]; struct _GUID *
0x140106b87  lea     rcx, [rbp+110h+var_C0]; this
0x140106b8b  call    ??0BlbGuidStr@@QEAA@AEBU_GUID@@@Z; BlbGuidStr::BlbGuidStr(_GUID const &)
0x140106b90  mov     rdx, rsi; struct _GUID *
0x140106b93  lea     rcx, [rbp+110h+var_130]; this
0x140106b97  mov     rbx, rax
0x140106b9a  call    ??0BlbGuidStr@@QEAA@AEBU_GUID@@@Z; BlbGuidStr::BlbGuidStr(_GUID const &)
0x140106b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140106ba6  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x140106bad  mov     edx, 40h ; '@'
0x140106bb2  mov     [rsp+210h+var_1F0], rbx
0x140106bb7  mov     r9, rax
0x140106bba  mov     rcx, [rcx+10h]
0x140106bbe  call    WPP_SF_SS
0x140106bc3  test    rdi, rdi
0x140106bc6  jz      short loc_140106BDA
0x140106bc8  mov     rcx, rdi; pv
0x140106bcb  call    cs:__imp_CoTaskMemFree
0x140106bd1  mov     [rsp+210h+lpFileName], 0
0x140106bda  mov     r8d, [r15]; unsigned int
0x140106bdd  lea     r9, aVhdx; ".vhdx"
0x140106be4  xor     eax, eax
0x140106be6  lea     rdx, [rbp+110h+Uuid]; Uuid
0x140106bea  xorps   xmm0, xmm0
0x140106bed  mov     [rbp+110h+var_150], eax
0x140106bf0  lea     rax, [rsp+210h+lpFileName]
0x140106bf5  mov     rcx, r14; unsigned __int16 *
0x140106bf8  mov     [rsp+210h+var_1F0], rax; unsigned __int16 **
0x140106bfd  movups  [rbp+110h+FileInformation], xmm0
0x140106c01  movups  [rbp+110h+var_160], xmm0
0x140106c05  call    ?BlbAppendBagFile@@YAJPEAGPEAU_GUID@@KPEBGPEAPEAG@Z; BlbAppendBagFile(ushort *,_GUID *,ulong,ushort const *,ushort * *)
0x140106c0a  mov     ebx, eax
0x140106c0c  test    eax, eax
0x140106c0e  js      loc_140106D7C
0x140106c14  mov     rdi, [rsp+210h+lpFileName]
0x140106c19  lea     r8, [rbp+110h+FileInformation]; lpFileInformation
0x140106c1d  mov     rcx, rdi; lpFileName
0x140106c20  xor     edx, edx; fInfoLevelId
0x140106c22  call    cs:__imp_GetFileAttributesExW
0x140106c28  test    eax, eax
0x140106c2a  jnz     loc_140106CEA
0x140106c30  call    cs:__imp_GetLastError
0x140106c36  test    eax, eax
0x140106c38  jle     short loc_140106C42
0x140106c3a  movzx   eax, ax
0x140106c3d  or      eax, 80070000h
0x140106c42  mov     r10, cs:WPP_GLOBAL_Control
0x140106c49  lea     r13, WPP_GLOBAL_Control
0x140106c50  cmp     r10, r13
0x140106c53  jz      short loc_140106C86
0x140106c55  test    byte ptr [r10+1Ch], 1
0x140106c5a  jz      short loc_140106C86
0x140106c5c  cmp     byte ptr [r10+19h], 3
0x140106c61  jb      short loc_140106C86
0x140106c63  mov     rcx, [r10+10h]
0x140106c67  lea     r8, WPP_a4ce851ccccc3ce18ba06013107ef47e_Traceguids
0x140106c6e  mov     edx, 41h ; 'A'
0x140106c73  mov     dword ptr [rsp+210h+var_1F0], eax
0x140106c77  mov     r9d, r12d
0x140106c7a  call    WPP_SF_dd
0x140106c7f  mov     r10, cs:WPP_GLOBAL_Control
0x140106c86  xor     ebx, ebx
0x140106c88  jmp     loc_140106D6A
0x140106c8d  lea     r13, WPP_GLOBAL_Control
0x140106c94  jmp     loc_140106D63
0x140106c99  mov     r10, cs:WPP_GLOBAL_Control
0x140106ca0  lea     r13, WPP_GLOBAL_Control
0x140106ca7  cmp     r10, r13
0x140106caa  jz      short loc_140106C86
0x140106cac  test    byte ptr [r10+1Ch], 1
0x140106cb1  jz      short loc_140106C86
0x140106cb3  cmp     byte ptr [r10+19h], 4
0x140106cb8  jb      short loc_140106C86
0x140106cba  mov     rdx, rsi; struct _GUID *
0x140106cbd  lea     rcx, [rbp+110h+var_130]; this
0x140106cc1  call    ??0BlbGuidStr@@QEAA@AEBU_GUID@@@Z; BlbGuidStr::BlbGuidStr(_GUID const &)
0x140106cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140106ccd  mov     r9d, ebx
0x140106cd0  mov     [rsp+210h+var_1E8], rax
0x140106cd5  mov     rax, [rsp+210h+var_1B0]
0x140106cda  mov     [rsp+210h+var_1F0], rax
0x140106cdf  mov     rcx, [rcx+10h]
0x140106ce3  call    WPP_SF_DqS
0x140106ce8  jmp     short loc_140106C7F
0x140106cea  mov     eax, [rbp+110h+var_150]
0x140106ced  mov     rdx, [rsp+210h+var_1D0]
0x140106cf2  mov     rcx, [rsp+210h+var_1D8]
0x140106cf7  mov     dword ptr [rsp+210h+var_1C0], eax
0x140106cfb  mov     eax, dword ptr [rbp+110h+var_160+0Ch]
0x140106cfe  mov     dword ptr [rsp+210h+var_1C0+4], eax
0x140106d02  mov     rax, [rsp+210h+var_1C0]
0x140106d07  add     rdx, rax
0x140106d0a  cmp     byte ptr [r13+0], 0
0x140106d0f  mov     [rsp+210h+var_1D0], rdx
0x140106d14  jz      short loc_140106D24
0x140106d16  test    byte ptr [r15], 4
0x140106d1a  jz      short loc_140106D24
0x140106d1c  add     rcx, rax
0x140106d1f  mov     [rsp+210h+var_1D8], rcx
0x140106d24  mov     r10, cs:WPP_GLOBAL_Control
0x140106d2b  lea     r13, WPP_GLOBAL_Control
0x140106d32  cmp     r10, r13
0x140106d35  jz      short loc_140106D74
0x140106d37  test    byte ptr [r10+1Ch], 1
0x140106d3c  jz      short loc_140106D74
0x140106d3e  cmp     byte ptr [r10+19h], 4
0x140106d43  jb      short loc_140106D74
0x140106d45  mov     ecx, [r15]
0x140106d48  mov     r9d, r12d
0x140106d4b  shr     ecx, 2
0x140106d4e  and     ecx, 1
0x140106d51  mov     dword ptr [rsp+210h+var_1E8], ecx
0x140106d55  mov     rcx, [r10+10h]
0x140106d59  mov     [rsp+210h+var_1F0], rax
0x140106d5e  call    WPP_SF_did
0x140106d63  mov     r10, cs:WPP_GLOBAL_Control
0x140106d6a  mov     rcx, [rsp+210h+var_1D8]
0x140106d6f  mov     rdx, [rsp+210h+var_1D0]
0x140106d74  inc     r12d
0x140106d77  jmp     loc_140106A06
0x140106d7c  mov     rdi, [rsp+210h+lpFileName]
0x140106d81  lea     r13, WPP_GLOBAL_Control
0x140106d88  test    rdi, rdi
0x140106d8b  jz      short loc_140106D96
0x140106d8d  mov     rcx, rdi; pv
0x140106d90  call    cs:__imp_CoTaskMemFree
0x140106d96  mov     r12, [rsp+210h+var_1A8]
0x140106d9b  cmp     [rsp+210h+pv], 0
0x140106da1  jz      short loc_140106DAE
0x140106da3  mov     rcx, [rsp+210h+pv]; pv
0x140106da8  call    cs:__imp_CoTaskMemFree
0x140106dae  test    r14, r14
0x140106db1  jz      short loc_140106DBC
0x140106db3  mov     rcx, r14; pv
0x140106db6  call    cs:__imp_CoTaskMemFree
0x140106dbc  test    ebx, ebx
0x140106dbe  jns     short loc_140106DF4
0x140106dc0  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
