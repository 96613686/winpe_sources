# CBlbRestoreAsync::ConfirmMediaArrival(void)

- ea: `0x1400572c0`
- end: `0x140057638`
- name: `?ConfirmMediaArrival@CBlbRestoreAsync@@UEAAJXZ`
- size: `888`
- prototype: `__int64 __fastcall(CBlbRestoreAsync *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task`

## callees

- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x140056110`
- `0x1400572c0`
- `0x14005a370`
- `0x14005b8b0`
- `0x14008863c`
- `0x1400889f0`
- `0x140104240`
- `0x1401042c4`
- `0x140104b4c`
- `0x1401232b0`
- `0x140137010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14005733b`
- `KERNEL32!EnterCriticalSection` at `0x14005748b`
- `KERNEL32!EnterCriticalSection` at `0x14005733b`
- `KERNEL32!EnterCriticalSection` at `0x14005748b`
- `ole32!CoTaskMemFree` at `0x1400574b1`
- `ole32!CoTaskMemFree` at `0x1400574cd`
- `ole32!CoTaskMemFree` at `0x1400574ea`
- `ole32!CoTaskMemFree` at `0x140057507`
- `ole32!CoTaskMemFree` at `0x14005761e`
- `ole32!CoTaskMemFree` at `0x1400574b1`
- `ole32!CoTaskMemFree` at `0x1400574cd`
- `ole32!CoTaskMemFree` at `0x1400574ea`
- `ole32!CoTaskMemFree` at `0x140057507`
- `ole32!CoTaskMemFree` at `0x14005761e`

## pseudocode

```c
__int64 __fastcall CBlbRestoreAsync::ConfirmMediaArrival(CBlbRestoreAsync *this)
{
  bool v2; // zf
  int ShinyTargetWithMediaId; // ebx
  PVOID *v4; // rcx
  unsigned __int16 *v6; // r8
  const unsigned __int16 **v7; // rsi
  void *v8; // rcx
  unsigned __int16 **v9; // r15
  void *v10; // rcx
  void *v11; // rcx
  unsigned __int16 **v12; // r14
  void *v13; // rcx
  int appended; // eax
  void *v15; // rsi
  int VolumeAccessPath; // eax
  struct _GUID v17; // [rsp+30h] [rbp-30h] BYREF
  void **v18; // [rsp+40h] [rbp-20h] BYREF
  CBlbRestoreAsync *v19; // [rsp+48h] [rbp-18h]
  char v20; // [rsp+50h] [rbp-10h]
  unsigned int v21; // [rsp+A0h] [rbp+40h] BYREF
  struct _BLB_TARGET_INFO *v22; // [rsp+A8h] [rbp+48h] BYREF
  struct _BLB_TARGET_INFO *v23; // [rsp+B0h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+58h] BYREF

  v21 = 0;
  v18 = &CBlbObjectLock<CBlbVerifyBackupAsync>::`vftable';
  v22 = 0;
  v23 = 0;
  pv = 0;
  v19 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v2 = *((_DWORD *)this + 69) == 6;
  v20 = 1;
  if ( !v2 )
  {
LABEL_6:
    ShinyTargetWithMediaId = -2139619279;
    goto LABEL_7;
  }
  CBlbObjectLock<CBlbVerifyBackupAsync>::ReleaseLock(&v18);
  ShinyTargetWithMediaId = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, struct _BLB_TARGET_INFO **))(**((_QWORD **)this + 8) + 72LL))(
                             *((_QWORD *)this + 8),
                             &v21,
                             &v22);
  if ( ShinyTargetWithMediaId >= 0 )
  {
    v6 = (unsigned __int16 *)*((_QWORD *)this + 28);
    v17 = *(struct _GUID *)(108LL * *((unsigned int *)this + 70) + *((_QWORD *)this + 36) + 64);
    ShinyTargetWithMediaId = BlbGetShinyTargetWithMediaId(&v17, v22, v6, v21, &v23);
    if ( ShinyTargetWithMediaId < 0 )
      goto LABEL_7;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v19 + 72));
    v2 = *((_DWORD *)this + 69) == 6;
    v20 = 1;
    if ( !v2 )
      goto LABEL_6;
    v7 = (const unsigned __int16 **)((char *)this + 232);
    v8 = (void *)*((_QWORD *)this + 29);
    if ( v8 )
    {
      CoTaskMemFree(v8);
      *v7 = 0;
    }
    v9 = (unsigned __int16 **)((char *)this + 248);
    v10 = (void *)*((_QWORD *)this + 31);
    if ( v10 )
    {
      CoTaskMemFree(v10);
      *v9 = 0;
    }
    v11 = (void *)*((_QWORD *)this + 25);
    if ( v11 )
    {
      CoTaskMemFree(v11);
      *((_QWORD *)this + 25) = 0;
    }
    v12 = (unsigned __int16 **)((char *)this + 256);
    v13 = (void *)*((_QWORD *)this + 32);
    if ( v13 )
    {
      CoTaskMemFree(v13);
      *v12 = 0;
    }
    ShinyTargetWithMediaId = BlbutilDuplicateString(
                               *((const unsigned __int16 **)v23 + 2),
                               (unsigned __int16 **)this + 29,
                               0);
    if ( ShinyTargetWithMediaId < 0 )
      goto LABEL_7;
    ShinyTargetWithMediaId = BlbutilDuplicateString(*v7, (unsigned __int16 **)this + 31, 0);
    if ( ShinyTargetWithMediaId < 0 )
      goto LABEL_7;
    ShinyTargetWithMediaId = BlbGetBackupRootDirectory(
                               *v9,
                               *((unsigned __int16 **)this + 28),
                               (unsigned __int16 **)this + 32);
    if ( ShinyTargetWithMediaId < 0 )
      goto LABEL_7;
    ShinyTargetWithMediaId = BlbGetBackupSetDirectory(
                               *v12,
                               *(struct _FILETIME *)((char *)this + 316),
                               (unsigned __int16 **)this + 25);
    if ( ShinyTargetWithMediaId < 0 )
      goto LABEL_7;
    appended = BlbutilAppendString(*v7, L"\\", (unsigned __int16 **)&pv);
    v15 = pv;
    ShinyTargetWithMediaId = appended;
    if ( appended >= 0 )
    {
      VolumeAccessPath = BlbQueryVolumeAccessPath((LPCWSTR)pv, (unsigned __int16 **)this + 30);
      ShinyTargetWithMediaId = VolumeAccessPath;
      if ( VolumeAccessPath >= 0 )
      {
        CBlbRestoreAsync::SetState(this, 7, 0);
        CBlbObjectLock<CBlbVerifyBackupAsync>::ReleaseLock(&v18);
      }
      else
      {
        v4 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_44:
          if ( v15 )
          {
            CoTaskMemFree(v15);
            v4 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( ShinyTargetWithMediaId >= 0 )
            goto LABEL_12;
          goto LABEL_8;
        }
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          (unsigned int)&WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids,
          (_DWORD)v15,
          VolumeAccessPath);
      }
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_44;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_8;
  }
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
LABEL_7:
  v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_8:
  if ( v4 == &WPP_GLOBAL_Control )
    goto LABEL_16;
  if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    WPP_SF_d(v4[2], 61, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 4u )
    WPP_SF_(v4[2], 62, &WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids);
LABEL_16:
  CBlbObjectLock<CBlbVerifyBackupAsync>::~CBlbObjectLock<CBlbVerifyBackupAsync>(&v18);
  return (unsigned int)ShinyTargetWithMediaId;
}

```

## disassembly

```asm
0x1400572c0  push    rbp
0x1400572c2  push    rbx
0x1400572c3  push    rsi
0x1400572c4  push    rdi
0x1400572c5  push    r12
0x1400572c7  push    r14
0x1400572c9  push    r15
0x1400572cb  mov     rbp, rsp
0x1400572ce  sub     rsp, 60h
0x1400572d2  lea     rax, ??_7?$CBlbObjectLock@VCBlbVerifyBackupAsync@@@@6B@; const CBlbObjectLock<CBlbVerifyBackupAsync>::`vftable'
0x1400572d9  mov     [rbp+arg_0], 0
0x1400572e0  mov     [rbp+var_20], rax
0x1400572e4  mov     rdi, rcx
0x1400572e7  mov     [rbp+arg_8], 0
0x1400572ef  mov     [rbp+arg_10], 0
0x1400572f7  mov     [rbp+pv], 0
0x1400572ff  mov     [rbp+var_18], rcx
0x140057303  mov     rcx, cs:WPP_GLOBAL_Control
0x14005730a  lea     rsi, WPP_GLOBAL_Control
0x140057311  cmp     rcx, rsi
0x140057314  jz      short loc_140057337
0x140057316  test    byte ptr [rcx+1Ch], 1
0x14005731a  jz      short loc_140057337
0x14005731c  cmp     byte ptr [rcx+19h], 4
0x140057320  jb      short loc_140057337
0x140057322  mov     rcx, [rcx+10h]
0x140057326  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005732d  mov     edx, 3Ah ; ':'
0x140057332  call    WPP_SF_
0x140057337  lea     rcx, [rdi+48h]; lpCriticalSection
0x14005733b  call    cs:__imp_EnterCriticalSection
0x140057341  cmp     dword ptr [rdi+114h], 6
0x140057348  mov     [rbp+var_10], 1
0x14005734c  jz      loc_1400573D5
0x140057352  mov     ebx, 80780031h
0x140057357  mov     rcx, cs:WPP_GLOBAL_Control
0x14005735e  lea     rdi, WPP_GLOBAL_Control
0x140057365  cmp     rcx, rdi
0x140057368  jz      short loc_1400573BB
0x14005736a  test    byte ptr [rcx+1Ch], 1
0x14005736e  jz      short loc_140057395
0x140057370  cmp     byte ptr [rcx+19h], 2
0x140057374  jb      short loc_140057395
0x140057376  mov     rcx, [rcx+10h]
0x14005737a  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x140057381  mov     edx, 3Dh ; '='
0x140057386  mov     r9d, ebx
0x140057389  call    WPP_SF_d
0x14005738e  mov     rcx, cs:WPP_GLOBAL_Control
0x140057395  cmp     rcx, rdi
0x140057398  jz      short loc_1400573BB
0x14005739a  test    byte ptr [rcx+1Ch], 1
0x14005739e  jz      short loc_1400573BB
0x1400573a0  cmp     byte ptr [rcx+19h], 4
0x1400573a4  jb      short loc_1400573BB
0x1400573a6  mov     rcx, [rcx+10h]
0x1400573aa  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x1400573b1  mov     edx, 3Eh ; '>'
0x1400573b6  call    WPP_SF_
0x1400573bb  lea     rcx, [rbp+var_20]
0x1400573bf  call    ??1?$CBlbObjectLock@VCBlbVerifyBackupAsync@@@@UEAA@XZ; CBlbObjectLock<CBlbVerifyBackupAsync>::~CBlbObjectLock<CBlbVerifyBackupAsync>(void)
0x1400573c4  mov     eax, ebx
0x1400573c6  add     rsp, 60h
0x1400573ca  pop     r15
0x1400573cc  pop     r14
0x1400573ce  pop     r12
0x1400573d0  pop     rdi
0x1400573d1  pop     rsi
0x1400573d2  pop     rbx
0x1400573d3  pop     rbp
0x1400573d4  retn
0x1400573d5  lea     rcx, [rbp+var_20]
0x1400573d9  call    ?ReleaseLock@?$CBlbObjectLock@VCBlbVerifyBackupAsync@@@@UEAAXXZ; CBlbObjectLock<CBlbVerifyBackupAsync>::ReleaseLock(void)
0x1400573de  mov     rcx, [rdi+40h]
0x1400573e2  lea     r8, [rbp+arg_8]
0x1400573e6  lea     rdx, [rbp+arg_0]
0x1400573ea  mov     rax, [rcx]
0x1400573ed  mov     rax, [rax+48h]
0x1400573f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400573f6  mov     ebx, eax
0x1400573f8  test    eax, eax
0x1400573fa  jns     short loc_14005743D
0x1400573fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140057403  cmp     rcx, rsi
0x140057406  jz      loc_14005735E
0x14005740c  test    byte ptr [rcx+1Ch], 1
0x140057410  jz      loc_14005735E
0x140057416  cmp     byte ptr [rcx+19h], 2
0x14005741a  jb      loc_14005735E
0x140057420  mov     rcx, [rcx+10h]
0x140057424  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x14005742b  mov     edx, 3Bh ; ';'
0x140057430  mov     r9d, eax
0x140057433  call    WPP_SF_d
0x140057438  jmp     loc_140057357
0x14005743d  mov     eax, [rdi+118h]
0x140057443  mov     r9d, [rbp+arg_0]; unsigned int
0x140057447  mov     r8, [rdi+0E0h]; unsigned __int16 *
0x14005744e  mov     rdx, [rbp+arg_8]; struct _BLB_TARGET_INFO *
0x140057452  imul    rcx, rax, 6Ch ; 'l'
0x140057456  mov     rax, [rdi+120h]
0x14005745d  movups  xmm0, xmmword ptr [rcx+rax+40h]
0x140057462  lea     rax, [rbp+arg_10]
0x140057466  lea     rcx, [rbp+var_30]; struct _GUID
0x14005746a  mov     [rsp+60h+var_40], rax; struct _BLB_TARGET_INFO **
0x14005746f  movdqu  xmmword ptr [rbp+var_30.Data1], xmm0
0x140057474  call    ?BlbGetShinyTargetWithMediaId@@YAJU_GUID@@PEAU_BLB_TARGET_INFO@@PEAGKPEAPEAU2@@Z; BlbGetShinyTargetWithMediaId(_GUID,_BLB_TARGET_INFO *,ushort *,ulong,_BLB_TARGET_INFO * *)
0x140057479  mov     ebx, eax
0x14005747b  test    eax, eax
0x14005747d  js      loc_140057357
0x140057483  mov     rcx, [rbp+var_18]
0x140057487  add     rcx, 48h ; 'H'; lpCriticalSection
0x14005748b  call    cs:__imp_EnterCriticalSection
0x140057491  cmp     dword ptr [rdi+114h], 6
0x140057498  mov     [rbp+var_10], 1
0x14005749c  jnz     loc_140057352
0x1400574a2  lea     rsi, [rdi+0E8h]
0x1400574a9  mov     rcx, [rsi]; pv
0x1400574ac  test    rcx, rcx
0x1400574af  jz      short loc_1400574BE
0x1400574b1  call    cs:__imp_CoTaskMemFree
0x1400574b7  mov     qword ptr [rsi], 0
0x1400574be  lea     r15, [rdi+0F8h]
0x1400574c5  mov     rcx, [r15]; pv
0x1400574c8  test    rcx, rcx
0x1400574cb  jz      short loc_1400574DA
0x1400574cd  call    cs:__imp_CoTaskMemFree
0x1400574d3  mov     qword ptr [r15], 0
0x1400574da  lea     r12, [rdi+0C8h]
0x1400574e1  mov     rcx, [r12]; pv
0x1400574e5  test    rcx, rcx
0x1400574e8  jz      short loc_1400574F8
0x1400574ea  call    cs:__imp_CoTaskMemFree
0x1400574f0  mov     qword ptr [r12], 0
0x1400574f8  lea     r14, [rdi+100h]
0x1400574ff  mov     rcx, [r14]; pv
0x140057502  test    rcx, rcx
0x140057505  jz      short loc_140057514
0x140057507  call    cs:__imp_CoTaskMemFree
0x14005750d  mov     qword ptr [r14], 0
0x140057514  mov     rcx, [rbp+arg_10]
0x140057518  xor     r8d, r8d; unsigned __int64
0x14005751b  mov     rdx, rsi; unsigned __int16 **
0x14005751e  mov     rcx, [rcx+10h]; unsigned __int16 *
0x140057522  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140057527  mov     ebx, eax
0x140057529  test    eax, eax
0x14005752b  js      loc_140057357
0x140057531  mov     rcx, [rsi]; unsigned __int16 *
0x140057534  xor     r8d, r8d; unsigned __int64
0x140057537  mov     rdx, r15; unsigned __int16 **
0x14005753a  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x14005753f  mov     ebx, eax
0x140057541  test    eax, eax
0x140057543  js      loc_140057357
0x140057549  mov     rdx, [rdi+0E0h]; unsigned __int16 *
0x140057550  mov     r8, r14; unsigned __int16 **
0x140057553  mov     rcx, [r15]; unsigned __int16 *
0x140057556  call    ?BlbGetBackupRootDirectory@@YAJPEAG0PEAPEAG@Z; BlbGetBackupRootDirectory(ushort *,ushort *,ushort * *)
0x14005755b  mov     ebx, eax
0x14005755d  test    eax, eax
0x14005755f  js      loc_140057357
0x140057565  mov     rdx, [rdi+13Ch]; struct _FILETIME
0x14005756c  mov     r8, r12; unsigned __int16 **
0x14005756f  mov     rcx, [r14]; unsigned __int16 *
0x140057572  call    ?BlbGetBackupSetDirectory@@YAJPEAGU_FILETIME@@PEAPEAG@Z; BlbGetBackupSetDirectory(ushort *,_FILETIME,ushort * *)
0x140057577  mov     ebx, eax
0x140057579  test    eax, eax
0x14005757b  js      loc_140057357
0x140057581  mov     rcx, [rsi]; unsigned __int16 *
0x140057584  lea     r8, [rbp+pv]; unsigned __int16 **
0x140057588  lea     rdx, asc_14013C090; "\\"
0x14005758f  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x140057594  mov     rsi, [rbp+pv]
0x140057598  mov     ebx, eax
0x14005759a  test    eax, eax
0x14005759c  js      short loc_140057608
0x14005759e  lea     rdx, [rdi+0F0h]; unsigned __int16 **
0x1400575a5  mov     rcx, rsi; lpszVolumeName
0x1400575a8  call    ?BlbQueryVolumeAccessPath@@YAJPEAGPEAPEAG@Z; BlbQueryVolumeAccessPath(ushort *,ushort * *)
0x1400575ad  mov     ebx, eax
0x1400575af  test    eax, eax
0x1400575b1  jns     short loc_1400575F0
0x1400575b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400575ba  lea     rdi, WPP_GLOBAL_Control
0x1400575c1  cmp     rcx, rdi
0x1400575c4  jz      short loc_140057616
0x1400575c6  test    byte ptr [rcx+1Ch], 1
0x1400575ca  jz      short loc_140057616
0x1400575cc  cmp     byte ptr [rcx+19h], 2
0x1400575d0  jb      short loc_140057616
0x1400575d2  mov     rcx, [rcx+10h]
0x1400575d6  lea     r8, WPP_63ffbe7c4885359c89b482e1b41beed9_Traceguids
0x1400575dd  mov     edx, 3Ch ; '<'
0x1400575e2  mov     dword ptr [rsp+60h+var_40], eax
0x1400575e6  mov     r9, rsi
0x1400575e9  call    WPP_SF_Sd
0x1400575ee  jmp     short loc_14005760F
0x1400575f0  xor     r8d, r8d
0x1400575f3  mov     rcx, rdi
0x1400575f6  lea     edx, [r8+7]
0x1400575fa  call    ?SetState@CBlbRestoreAsync@@IEAAXW4_BLB_RESTORE_STATE@@E@Z; CBlbRestoreAsync::SetState(_BLB_RESTORE_STATE,uchar)
0x1400575ff  lea     rcx, [rbp+var_20]
0x140057603  call    ?ReleaseLock@?$CBlbObjectLock@VCBlbVerifyBackupAsync@@@@UEAAXXZ; CBlbObjectLock<CBlbVerifyBackupAsync>::ReleaseLock(void)
0x140057608  lea     rdi, WPP_GLOBAL_Control
0x14005760f  mov     rcx, cs:WPP_GLOBAL_Control
0x140057616  test    rsi, rsi
0x140057619  jz      short loc_14005762B
0x14005761b  mov     rcx, rsi; pv
0x14005761e  call    cs:__imp_CoTaskMemFree
0x140057624  mov     rcx, cs:WPP_GLOBAL_Control
0x14005762b  test    ebx, ebx
0x14005762d  jns     loc_140057395
0x140057633  jmp     loc_140057365
```
