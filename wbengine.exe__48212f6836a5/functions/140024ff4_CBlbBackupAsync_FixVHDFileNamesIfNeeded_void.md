# CBlbBackupAsync::FixVHDFileNamesIfNeeded(void)

- ea: `0x140024ff4`
- end: `0x1400257c6`
- name: `?FixVHDFileNamesIfNeeded@CBlbBackupAsync@@AEAAJXZ`
- size: `2002`
- prototype: `__int64 __fastcall(CBlbBackupAsync *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140019fd0`

## callees

- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x140014384`
- `0x14001d660`
- `0x140024ff4`
- `0x140026cac`
- `0x14003ccd0`
- `0x1400881ac`
- `0x14008e440`
- `0x14009257c`
- `0x140098c04`
- `0x1400f2a28`
- `0x1400f2d74`
- `0x140102128`
- `0x140134cc6`
- `0x140134d20`

## import_xrefs

- `KERNEL32!FindClose` at `0x140025725`
- `KERNEL32!FindClose` at `0x14002579e`
- `KERNEL32!FindClose` at `0x140025725`
- `KERNEL32!FindClose` at `0x14002579e`
- `KERNEL32!MoveFileW` at `0x14002567f`
- `KERNEL32!MoveFileW` at `0x14002567f`
- `KERNEL32!GetLastError` at `0x1400256a1`
- `KERNEL32!GetLastError` at `0x1400256a1`
- `msvcrt!_wcsnicmp` at `0x1400252e0`
- `msvcrt!_wcsnicmp` at `0x1400252e0`
- `ole32!CoTaskMemFree` at `0x140025291`
- `ole32!CoTaskMemFree` at `0x1400252a4`
- `ole32!CoTaskMemFree` at `0x1400255aa`
- `ole32!CoTaskMemFree` at `0x1400256d7`
- `ole32!CoTaskMemFree` at `0x140025737`
- `ole32!CoTaskMemFree` at `0x14002574a`
- `ole32!CoTaskMemFree` at `0x140025758`
- `ole32!CoTaskMemFree` at `0x140025766`
- `ole32!CoTaskMemFree` at `0x140025774`
- `ole32!CoTaskMemFree` at `0x14002578f`
- `ole32!CoTaskMemFree` at `0x140025291`
- `ole32!CoTaskMemFree` at `0x1400252a4`
- `ole32!CoTaskMemFree` at `0x1400255aa`
- `ole32!CoTaskMemFree` at `0x1400256d7`
- `ole32!CoTaskMemFree` at `0x140025737`
- `ole32!CoTaskMemFree` at `0x14002574a`
- `ole32!CoTaskMemFree` at `0x140025758`
- `ole32!CoTaskMemFree` at `0x140025766`
- `ole32!CoTaskMemFree` at `0x140025774`
- `ole32!CoTaskMemFree` at `0x14002578f`
- `RPCRT4!UuidFromStringW` at `0x140025387`
- `RPCRT4!UuidFromStringW` at `0x140025387`

## pseudocode

```c
__int64 __fastcall CBlbBackupAsync::FixVHDFileNamesIfNeeded(unsigned __int16 **this)
{
  CBlbBackupAsync *v1; // r14
  __int64 v2; // rcx
  int LastBackupDoneToTarget; // ebx
  __int64 v4; // r12
  unsigned __int16 *v5; // rsi
  wchar_t *v6; // r15
  unsigned __int16 *v7; // rdi
  WCHAR *v8; // r13
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // rax
  struct _BLBCAT_BACKUP_SET_INFO *v15; // r8
  unsigned int v16; // edi
  unsigned int v17; // ecx
  _QWORD *v18; // rdx
  __int64 v19; // rax
  unsigned int v20; // r14d
  unsigned int v21; // ebx
  unsigned __int16 *v22; // r13
  __int64 v23; // rcx
  __int64 v24; // rax
  const unsigned __int8 *v25; // r15
  unsigned __int16 v26; // si
  BlbGuidStr *v27; // rax
  __int64 v28; // r14
  unsigned __int16 *v29; // rdx
  _QWORD *v30; // rcx
  __int64 v31; // rax
  const OLECHAR *v32; // rbx
  unsigned __int16 *v33; // rcx
  BlbGuidStr *v34; // rax
  char LastError; // al
  int NextFile; // eax
  struct _BLBCAT_BACKUP_SET_INFO *v37; // rdi
  LPCWSTR lpExistingFileName; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v41; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpNewFileName; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String1; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  struct _BLBCAT_BACKUP_SET_INFO *v45; // [rsp+70h] [rbp-90h] BYREF
  UUID Uuid; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v47[112]; // [rsp+90h] [rbp-70h] BYREF

  v1 = (CBlbBackupAsync *)this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 327, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
  }
  v2 = *((unsigned int *)v1 + 84);
  LastBackupDoneToTarget = 0;
  v4 = -1;
  pv = 0;
  *(_QWORD *)&Uuid.Data1 = -1;
  v5 = 0;
  lpExistingFileName = 0;
  v6 = 0;
  String1 = 0;
  v7 = 0;
  v41 = 0;
  v8 = 0;
  v45 = 0;
  lpNewFileName = 0;
  if ( (BlbutilGetBackupFeatures(v2) & 8) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 328, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    return (unsigned int)LastBackupDoneToTarget;
  }
  if ( !*((_QWORD *)v1 + 59) )
  {
    LastBackupDoneToTarget = -2147024809;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)LastBackupDoneToTarget;
    }
    v10 = 329;
    goto LABEL_15;
  }
  LastBackupDoneToTarget = CBlbBackupAsync::GetLastBackupDoneToTarget(v1, &v45);
  if ( LastBackupDoneToTarget < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 330, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    }
    goto LABEL_117;
  }
  if ( !v45 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      return (unsigned int)LastBackupDoneToTarget;
    }
    v10 = 331;
LABEL_15:
    WPP_SF_(v9[2], v10, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids);
    return (unsigned int)LastBackupDoneToTarget;
  }
  LastBackupDoneToTarget = BlbAppendBagFile(*((unsigned __int16 **)v1 + 59), 0, 0, L".vhdx", (unsigned __int16 **)&pv);
  if ( LastBackupDoneToTarget < 0 )
    goto LABEL_109;
  LastBackupDoneToTarget = BlbFindFirstFile((unsigned __int16 *)pv, (LPVOID *)&lpExistingFileName, (void **)&Uuid, 0);
  if ( LastBackupDoneToTarget < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        332,
        (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
        (_DWORD)pv,
        LastBackupDoneToTarget);
    }
    v4 = *(_QWORD *)&Uuid.Data1;
    v5 = (unsigned __int16 *)lpExistingFileName;
    goto LABEL_109;
  }
  v4 = *(_QWORD *)&Uuid.Data1;
  while ( 1 )
  {
    v5 = (unsigned __int16 *)lpExistingFileName;
    if ( !lpExistingFileName )
      break;
    Uuid = GUID_NULL;
    if ( v6 )
    {
      CoTaskMemFree(v6);
      String1 = 0;
    }
    if ( v7 )
    {
      CoTaskMemFree(v7);
      v41 = 0;
    }
    v11 = BlbutilSplitFilePath(v5, &v41, &String1);
    v6 = String1;
    LastBackupDoneToTarget = v11;
    if ( v11 < 0 )
    {
      v7 = v41;
      goto LABEL_107;
    }
    if ( !_wcsnicmp(String1, L"Esp", 3u) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_102;
      }
      v13 = 333;
      goto LABEL_45;
    }
    v14 = -1;
    do
      ++v14;
    while ( v6[v14] );
    if ( v14 < 0x24 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_102;
      }
      v13 = 334;
      goto LABEL_45;
    }
    v6[36] = 0;
    if ( UuidFromStringW(v6, &Uuid) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_102;
      }
      v13 = 335;
      goto LABEL_45;
    }
    if ( !memcmp_0(&Uuid, &GUID_NULL, 0x10u) )
      goto LABEL_102;
    v15 = v45;
    v16 = 0;
    v17 = *((_DWORD *)v45 + 16);
    if ( v17 )
    {
      while ( 1 )
      {
        v18 = (_QWORD *)(*((_QWORD *)v45 + 9) + 120LL * v16);
        v19 = *v18 - *(_QWORD *)&Uuid.Data1;
        if ( *v18 == *(_QWORD *)&Uuid.Data1 )
          v19 = v18[1] - *(_QWORD *)Uuid.Data4;
        if ( !v19 )
          break;
        if ( ++v16 >= v17 )
          goto LABEL_64;
      }
    }
    else
    {
LABEL_64:
      if ( v16 >= v17 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_102;
        }
        v13 = 336;
LABEL_45:
        WPP_SF_S(v12[2], v13, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v5);
        goto LABEL_102;
      }
    }
    v20 = *((_DWORD *)v1 + 92);
    v21 = 0;
    if ( v20 )
    {
      v22 = this[27];
      v23 = 120LL * v16;
      v24 = *((_QWORD *)v45 + 9);
      v25 = *(const unsigned __int8 **)(v23 + v24 + 72);
      v26 = *(_WORD *)(v23 + v24 + 68);
      do
      {
        if ( BlbutilCompareUniqueIds(v26, v25, v22[184 * v21 + 53], *(const unsigned __int8 **)&v22[184 * v21 + 56]) == 1 )
          break;
        ++v21;
      }
      while ( v21 < v20 );
      v5 = (unsigned __int16 *)lpExistingFileName;
      v6 = String1;
      v8 = (WCHAR *)lpNewFileName;
      v15 = v45;
    }
    if ( v21 == v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v27 = BlbGuidStr::BlbGuidStr((BlbGuidStr *)v47, (const struct _GUID *)(*((_QWORD *)v15 + 9) + 120LL * v16));
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 337, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v27);
      }
    }
    else
    {
      v28 = 184LL * v21;
      v29 = this[27];
      v30 = (_QWORD *)(*((_QWORD *)v15 + 9) + 120LL * v16);
      v31 = *v30 - *(_QWORD *)&v29[v28 + 34];
      if ( !v31 )
        v31 = v30[1] - *(_QWORD *)&v29[v28 + 38];
      if ( !v31 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 338, &WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids, v5);
        }
        v1 = (CBlbBackupAsync *)this;
        goto LABEL_102;
      }
      if ( v8 )
      {
        CoTaskMemFree(v8);
        lpNewFileName = 0;
      }
      LastBackupDoneToTarget = BlbAppendBagFile(
                                 this[59],
                                 (UUID *)&this[27][v28 + 34],
                                 *(_DWORD *)&this[27][v28 + 42],
                                 L".vhdx",
                                 (unsigned __int16 **)&lpNewFileName);
      if ( LastBackupDoneToTarget < 0 )
      {
        v7 = v41;
        v8 = (WCHAR *)lpNewFileName;
        goto LABEL_107;
      }
      v8 = (WCHAR *)lpNewFileName;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v32 = &::String1;
        v33 = this[27];
        if ( *(_QWORD *)&v33[v28 + 44] )
          v32 = *(const OLECHAR **)&v33[v28 + 44];
        v34 = BlbGuidStr::BlbGuidStr((BlbGuidStr *)v47, (const struct _GUID *)&v33[v28 + 34]);
        WPP_SF_SSSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v8, (__int64)v34, (__int64)v32);
      }
      if ( !MoveFileW(v5, v8)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        LastError = GetLastError();
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          340,
          (unsigned int)&WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids,
          (_DWORD)v5,
          (__int64)v8,
          LastError);
      }
    }
    v1 = (CBlbBackupAsync *)this;
LABEL_102:
    CoTaskMemFree(v5);
    lpExistingFileName = 0;
    NextFile = BlbFindNextFile((unsigned __int16 *)pv, (HANDLE)v4, (LPVOID *)&lpExistingFileName, 0);
    v7 = v41;
    LastBackupDoneToTarget = NextFile;
    if ( NextFile < 0 )
    {
      v5 = (unsigned __int16 *)lpExistingFileName;
      goto LABEL_107;
    }
  }
  FindClose((HANDLE)v4);
  v4 = -1;
LABEL_107:
  if ( v8 )
    CoTaskMemFree(v8);
LABEL_109:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v7 )
    CoTaskMemFree(v7);
LABEL_117:
  v37 = v45;
  if ( v45 )
  {
    FreeBackupSetContents(v45);
    CoTaskMemFree(v37);
  }
  if ( v4 != -1 )
    FindClose((HANDLE)v4);
  return (unsigned int)LastBackupDoneToTarget;
}

```

## disassembly

```asm
0x140024ff4  push    rbp
0x140024ff6  push    rbx
0x140024ff7  push    rsi
0x140024ff8  push    rdi
0x140024ff9  push    r12
0x140024ffb  push    r13
0x140024ffd  push    r14
0x140024fff  push    r15
0x140025001  lea     rbp, [rsp-18h]
0x140025006  sub     rsp, 118h
0x14002500d  mov     rax, cs:__security_cookie
0x140025014  xor     rax, rsp
0x140025017  mov     [rbp+50h+var_50], rax
0x14002501b  mov     r14, rcx
0x14002501e  mov     [rsp+150h+var_110], rcx
0x140025023  mov     rcx, cs:WPP_GLOBAL_Control
0x14002502a  lea     rax, WPP_GLOBAL_Control
0x140025031  cmp     rcx, rax
0x140025034  jz      short loc_140025057
0x140025036  test    byte ptr [rcx+1Ch], 1
0x14002503a  jz      short loc_140025057
0x14002503c  cmp     byte ptr [rcx+19h], 4
0x140025040  jb      short loc_140025057
0x140025042  mov     rcx, [rcx+10h]
0x140025046  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002504d  mov     edx, 147h
0x140025052  call    WPP_SF_
0x140025057  mov     ecx, [r14+150h]
0x14002505e  xor     ebx, ebx
0x140025060  or      r12, 0FFFFFFFFFFFFFFFFh
0x140025064  mov     [rsp+150h+pv], rbx
0x140025069  mov     qword ptr [rsp+150h+Uuid.Data1], r12
0x14002506e  mov     esi, ebx
0x140025070  mov     [rsp+150h+lpExistingFileName], rbx
0x140025075  mov     r15d, ebx
0x140025078  mov     [rsp+150h+String1], rbx
0x14002507d  mov     edi, ebx
0x14002507f  mov     [rsp+150h+var_100], rbx
0x140025084  mov     r13d, ebx
0x140025087  mov     [rsp+150h+var_E0], rbx
0x14002508c  mov     [rsp+150h+lpNewFileName], rbx
0x140025091  call    ?BlbutilGetBackupFeatures@@YAKW4_BLB_MEDIA_TYPE@@@Z; BlbutilGetBackupFeatures(_BLB_MEDIA_TYPE)
0x140025096  test    al, 8
0x140025098  jnz     short loc_1400250E6
0x14002509a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400250a1  lea     rax, WPP_GLOBAL_Control
0x1400250a8  cmp     rcx, rax
0x1400250ab  jz      loc_1400257A4
0x1400250b1  test    byte ptr [rcx+1Ch], 1
0x1400250b5  jz      loc_1400257A4
0x1400250bb  cmp     byte ptr [rcx+19h], 4
0x1400250bf  jb      loc_1400257A4
0x1400250c5  mov     r9d, [r14+150h]
0x1400250cc  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x1400250d3  mov     rcx, [rcx+10h]
0x1400250d7  mov     edx, 148h
0x1400250dc  call    WPP_SF_d
0x1400250e1  jmp     loc_1400257A4
0x1400250e6  cmp     [r14+1D8h], rbx
0x1400250ed  jnz     short loc_140025139
0x1400250ef  mov     ebx, 80070057h
0x1400250f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400250fb  lea     rax, WPP_GLOBAL_Control
0x140025102  cmp     rcx, rax
0x140025105  jz      loc_1400257A4
0x14002510b  test    byte ptr [rcx+1Ch], 1
0x14002510f  jz      loc_1400257A4
0x140025115  cmp     byte ptr [rcx+19h], 2
0x140025119  jb      loc_1400257A4
0x14002511f  mov     edx, 149h
0x140025124  mov     rcx, [rcx+10h]
0x140025128  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x14002512f  call    WPP_SF_
0x140025134  jmp     loc_1400257A4
0x140025139  lea     rdx, [rsp+150h+var_E0]; struct _BLBCAT_BACKUP_SET_INFO **
0x14002513e  mov     rcx, r14; this
0x140025141  call    ?GetLastBackupDoneToTarget@CBlbBackupAsync@@AEAAJPEAPEAU_BLBCAT_BACKUP_SET_INFO@@@Z; CBlbBackupAsync::GetLastBackupDoneToTarget(_BLBCAT_BACKUP_SET_INFO * *)
0x140025146  xor     ecx, ecx
0x140025148  mov     ebx, eax
0x14002514a  test    eax, eax
0x14002514c  jns     short loc_140025196
0x14002514e  mov     rcx, cs:WPP_GLOBAL_Control
0x140025155  lea     rax, WPP_GLOBAL_Control
0x14002515c  cmp     rcx, rax
0x14002515f  jz      loc_14002577A
0x140025165  test    byte ptr [rcx+1Ch], 1
0x140025169  jz      loc_14002577A
0x14002516f  cmp     byte ptr [rcx+19h], 2
0x140025173  jb      loc_14002577A
0x140025179  mov     rcx, [rcx+10h]
0x14002517d  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140025184  mov     edx, 14Ah
0x140025189  mov     r9d, ebx
0x14002518c  call    WPP_SF_d
0x140025191  jmp     loc_14002577A
0x140025196  cmp     [rsp+150h+var_E0], rcx
0x14002519b  jnz     short loc_1400251D2
0x14002519d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400251a4  lea     rax, WPP_GLOBAL_Control
0x1400251ab  cmp     rcx, rax
0x1400251ae  jz      loc_1400257A4
0x1400251b4  test    byte ptr [rcx+1Ch], 1
0x1400251b8  jz      loc_1400257A4
0x1400251be  cmp     byte ptr [rcx+19h], 4
0x1400251c2  jb      loc_1400257A4
0x1400251c8  mov     edx, 14Bh
0x1400251cd  jmp     loc_140025124
0x1400251d2  mov     rcx, [r14+1D8h]; unsigned __int16 *
0x1400251d9  lea     rax, [rsp+150h+pv]
0x1400251de  lea     r9, aVhdx; ".vhdx"
0x1400251e5  mov     [rsp+150h+var_130], rax; unsigned __int16 **
0x1400251ea  xor     r8d, r8d; unsigned int
0x1400251ed  xor     edx, edx; Uuid
0x1400251ef  call    ?BlbAppendBagFile@@YAJPEAGPEAU_GUID@@KPEBGPEAPEAG@Z; BlbAppendBagFile(ushort *,_GUID *,ulong,ushort const *,ushort * *)
0x1400251f4  mov     ebx, eax
0x1400251f6  test    eax, eax
0x1400251f8  js      loc_14002573D
0x1400251fe  mov     rcx, [rsp+150h+pv]; unsigned __int16 *
0x140025203  lea     r8, [rsp+150h+Uuid]; void **
0x140025208  xor     r9d, r9d; struct _WIN32_FIND_DATAW **
0x14002520b  lea     rdx, [rsp+150h+lpExistingFileName]; unsigned __int16 **
0x140025210  call    ?BlbFindFirstFile@@YAJPEAGPEAPEAGPEAPEAXPEAPEAU_WIN32_FIND_DATAW@@@Z; BlbFindFirstFile(ushort *,ushort * *,void * *,_WIN32_FIND_DATAW * *)
0x140025215  mov     ebx, eax
0x140025217  test    eax, eax
0x140025219  jns     short loc_140025267
0x14002521b  mov     rcx, cs:WPP_GLOBAL_Control
0x140025222  lea     rax, WPP_GLOBAL_Control
0x140025229  cmp     rcx, rax
0x14002522c  jz      short loc_140025258
0x14002522e  test    byte ptr [rcx+1Ch], 1
0x140025232  jz      short loc_140025258
0x140025234  cmp     byte ptr [rcx+19h], 2
0x140025238  jb      short loc_140025258
0x14002523a  mov     r9, [rsp+150h+pv]
0x14002523f  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140025246  mov     rcx, [rcx+10h]
0x14002524a  mov     edx, 14Ch
0x14002524f  mov     dword ptr [rsp+150h+var_130], ebx
0x140025253  call    WPP_SF_Sd
0x140025258  mov     r12, qword ptr [rsp+150h+Uuid.Data1]
0x14002525d  mov     rsi, [rsp+150h+lpExistingFileName]
0x140025262  jmp     loc_14002573D
0x140025267  mov     r12, qword ptr [rsp+150h+Uuid.Data1]
0x14002526c  mov     rsi, [rsp+150h+lpExistingFileName]
0x140025271  test    rsi, rsi
0x140025274  jz      loc_140025722
0x14002527a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140025281  xor     ebx, ebx
0x140025283  movdqu  xmmword ptr [rsp+150h+Uuid.Data1], xmm0
0x140025289  test    r15, r15
0x14002528c  jz      short loc_14002529C
0x14002528e  mov     rcx, r15; pv
0x140025291  call    cs:__imp_CoTaskMemFree
0x140025297  mov     [rsp+150h+String1], rbx
0x14002529c  test    rdi, rdi
0x14002529f  jz      short loc_1400252AF
0x1400252a1  mov     rcx, rdi; pv
0x1400252a4  call    cs:__imp_CoTaskMemFree
0x1400252aa  mov     [rsp+150h+var_100], rbx
0x1400252af  lea     r8, [rsp+150h+String1]; unsigned __int16 **
0x1400252b4  mov     rcx, rsi; unsigned __int16 *
0x1400252b7  lea     rdx, [rsp+150h+var_100]; unsigned __int16 **
0x1400252bc  call    ?BlbutilSplitFilePath@@YAJPEAGPEAPEAG1@Z; BlbutilSplitFilePath(ushort *,ushort * *,ushort * *)
0x1400252c1  mov     r15, [rsp+150h+String1]
0x1400252c6  mov     ebx, eax
0x1400252c8  test    eax, eax
0x1400252ca  js      loc_14002571B
0x1400252d0  mov     r8d, 3; MaxCount
0x1400252d6  lea     rdx, aEsp; "Esp"
0x1400252dd  mov     rcx, r15; String1
0x1400252e0  call    cs:__imp__wcsnicmp
0x1400252e6  xor     ecx, ecx
0x1400252e8  test    eax, eax
0x1400252ea  jnz     short loc_140025334
0x1400252ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400252f3  lea     rax, WPP_GLOBAL_Control
0x1400252fa  cmp     rcx, rax
0x1400252fd  jz      loc_1400256D4
0x140025303  test    byte ptr [rcx+1Ch], 1
0x140025307  jz      loc_1400256D4
0x14002530d  cmp     byte ptr [rcx+19h], 4
0x140025311  jb      loc_1400256D4
0x140025317  mov     edx, 14Dh
0x14002531c  mov     rcx, [rcx+10h]
0x140025320  lea     r8, WPP_3ca8677ecac93883a00eef9eca1ec65f_Traceguids
0x140025327  mov     r9, rsi
0x14002532a  call    WPP_SF_S
0x14002532f  jmp     loc_1400256D4
0x140025334  or      rax, 0FFFFFFFFFFFFFFFFh
0x140025338  inc     rax
0x14002533b  cmp     [r15+rax*2], cx
0x140025340  jnz     short loc_140025338
0x140025342  cmp     rax, 24h ; '$'
0x140025346  jnb     short loc_14002537A
0x140025348  mov     rcx, cs:WPP_GLOBAL_Control
0x14002534f  lea     rax, WPP_GLOBAL_Control
0x140025356  cmp     rcx, rax
0x140025359  jz      loc_1400256D4
0x14002535f  test    byte ptr [rcx+1Ch], 1
0x140025363  jz      loc_1400256D4
0x140025369  cmp     byte ptr [rcx+19h], 4
0x14002536d  jb      loc_1400256D4
0x140025373  mov     edx, 14Eh
0x140025378  jmp     short loc_14002531C
0x14002537a  mov     [r15+48h], cx
0x14002537f  lea     rdx, [rsp+150h+Uuid]; Uuid
0x140025384  mov     rcx, r15; StringUuid
0x140025387  call    cs:__imp_UuidFromStringW
0x14002538d  test    eax, eax
0x14002538f  jz      short loc_1400253C6
0x140025391  mov     rcx, cs:WPP_GLOBAL_Control
0x140025398  lea     rax, WPP_GLOBAL_Control
0x14002539f  cmp     rcx, rax
0x1400253a2  jz      loc_1400256D4
0x1400253a8  test    byte ptr [rcx+1Ch], 1
0x1400253ac  jz      loc_1400256D4
0x1400253b2  cmp     byte ptr [rcx+19h], 4
0x1400253b6  jb      loc_1400256D4
0x1400253bc  mov     edx, 14Fh
0x1400253c1  jmp     loc_14002531C
0x1400253c6  mov     r8d, 10h; Size
0x1400253cc  lea     rdx, GUID_NULL; Buf2
0x1400253d3  lea     rcx, [rsp+150h+Uuid]; Buf1
0x1400253d8  call    memcmp_0
0x1400253dd  xor     r9d, r9d
0x1400253e0  test    eax, eax
0x1400253e2  jz      loc_1400256D4
0x1400253e8  mov     r8, [rsp+150h+var_E0]
0x1400253ed  mov     edi, r9d
0x1400253f0  mov     ecx, [r8+40h]
0x1400253f4  test    ecx, ecx
0x1400253f6  jz      short loc_14002541F
0x1400253f8  mov     eax, edi
0x1400253fa  imul    rdx, rax, 78h ; 'x'
0x1400253fe  add     rdx, [r8+48h]
0x140025402  mov     rax, [rdx]
0x140025405  sub     rax, qword ptr [rsp+150h+Uuid.Data1]
0x14002540a  jnz     short loc_140025414
0x14002540c  mov     rax, [rdx+8]
0x140025410  sub     rax, qword ptr [rbp+50h+Uuid.Data4]
0x140025414  test    rax, rax
0x140025417  jz      short loc_140025458
0x140025419  inc     edi
0x14002541b  cmp     edi, ecx
0x14002541d  jb      short loc_1400253F8
0x14002541f  cmp     edi, ecx
0x140025421  jb      short loc_140025458
0x140025423  mov     rcx, cs:WPP_GLOBAL_Control
0x14002542a  lea     rax, WPP_GLOBAL_Control
0x140025431  cmp     rcx, rax
0x140025434  jz      loc_1400256D4
0x14002543a  test    byte ptr [rcx+1Ch], 1
0x14002543e  jz      loc_1400256D4
0x140025444  cmp     byte ptr [rcx+19h], 3
0x140025448  jb      loc_1400256D4
0x14002544e  mov     edx, 150h
0x140025453  jmp     loc_14002531C
0x140025458  mov     r14d, [r14+170h]
0x14002545f  mov     ebx, r9d
0x140025462  test    r14d, r14d
0x140025465  jz      short loc_1400254C5
0x140025467  mov     rcx, [rsp+150h+var_110]
0x14002546c  mov     eax, edi
0x14002546e  mov     r13, [rcx+0D8h]
0x140025475  imul    rcx, rax, 78h ; 'x'
0x140025479  mov     rax, [r8+48h]
0x14002547d  mov     r15, [rcx+rax+48h]
0x140025482  movzx   esi, word ptr [rcx+rax+44h]
0x140025487  mov     eax, ebx
0x140025489  mov     rdx, r15; unsigned __int8 *
0x14002548c  imul    r8, rax, 170h
0x140025493  movzx   ecx, si; unsigned __int16
0x140025496  mov     r9, [r8+r13+70h]; unsigned __int8 *
0x14002549b  movzx   r8d, word ptr [r8+r13+6Ah]; unsigned __int16
0x1400254a1  call    ?BlbutilCompareUniqueIds@@YAEGPEBEG0@Z; BlbutilCompareUniqueIds(ushort,uchar const *,ushort,uchar const *)
0x1400254a6  cmp     al, 1
0x1400254a8  jz      short loc_1400254B1
0x1400254aa  inc     ebx
0x1400254ac  cmp     ebx, r14d
0x1400254af  jb      short loc_140025487
0x1400254b1  mov     rsi, [rsp+150h+lpExistingFileName]
0x1400254b6  mov     r15, [rsp+150h+String1]
0x1400254bb  mov     r13, [rsp+150h+lpNewFileName]
0x1400254c0  mov     r8, [rsp+150h+var_E0]
0x1400254c5  cmp     ebx, r14d
0x1400254c8  jnz     short loc_14002552C
0x1400254ca  mov     rax, cs:WPP_GLOBAL_Control
0x1400254d1  lea     rcx, WPP_GLOBAL_Control
0x1400254d8  cmp     rax, rcx
0x1400254db  jz      loc_1400256CF
0x1400254e1  test    byte ptr [rax+1Ch], 1
0x1400254e5  jz      loc_1400256CF
0x1400254eb  cmp     byte ptr [rax+19h], 4
0x1400254ef  jb      loc_1400256CF
0x1400254f5  mov     eax, edi
0x1400254f7  lea     rcx, [rbp+50h+var_C0]; this
0x1400254fb  imul    rdx, rax, 78h ; 'x'
0x1400254ff  add     rdx, [r8+48h]; struct _GUID *
0x140025503  call    ??0BlbGuidStr@@QEAA@AEBU_GUID@@@Z; BlbGuidStr::BlbGuidStr(_GUID const &)
0x140025508  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
