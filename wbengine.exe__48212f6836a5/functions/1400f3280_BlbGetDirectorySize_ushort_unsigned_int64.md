# BlbGetDirectorySize(ushort *,unsigned __int64 *)

- ea: `0x1400f3280`
- end: `0x1400f3706`
- name: `?BlbGetDirectorySize@@YAJPEAGPEA_K@Z`
- size: `1158`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x1400f3280`
- `0x140105f8c`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x140014200`
- `0x140014260`
- `0x14008863c`
- `0x140088b00`
- `0x1400f3280`
- `0x140134d20`

## import_xrefs

- `KERNEL32!FindClose` at `0x1400f35fd`
- `KERNEL32!FindClose` at `0x1400f35fd`
- `KERNEL32!FindNextFileW` at `0x1400f3582`
- `KERNEL32!FindNextFileW` at `0x1400f3582`
- `KERNEL32!FindFirstFileW` at `0x1400f342c`
- `KERNEL32!FindFirstFileW` at `0x1400f342c`
- `KERNEL32!GetFileAttributesW` at `0x1400f33d0`
- `KERNEL32!GetFileAttributesW` at `0x1400f33d0`
- `KERNEL32!GetLastError` at `0x1400f343b`
- `KERNEL32!GetLastError` at `0x1400f3590`
- `KERNEL32!GetLastError` at `0x1400f343b`
- `KERNEL32!GetLastError` at `0x1400f3590`
- `msvcrt!_wcsicmp` at `0x1400f3515`
- `msvcrt!_wcsicmp` at `0x1400f3515`
- `ole32!CoTaskMemFree` at `0x1400f34b4`
- `ole32!CoTaskMemFree` at `0x1400f35f4`
- `ole32!CoTaskMemFree` at `0x1400f361c`
- `ole32!CoTaskMemFree` at `0x1400f3631`
- `ole32!CoTaskMemFree` at `0x1400f364f`
- `ole32!CoTaskMemFree` at `0x1400f34b4`
- `ole32!CoTaskMemFree` at `0x1400f35f4`
- `ole32!CoTaskMemFree` at `0x1400f361c`
- `ole32!CoTaskMemFree` at `0x1400f3631`
- `ole32!CoTaskMemFree` at `0x1400f364f`

## string_xrefs

- `0x1400f32fc`: `wszPath`

## pseudocode

```c
__int64 __fastcall BlbGetDirectorySize(unsigned __int16 *a1, unsigned __int64 *a2)
{
  unsigned __int16 *v3; // r15
  unsigned __int16 *v4; // r14
  void *v5; // rsi
  __int64 v6; // rdx
  signed int LastError; // ebx
  int appended; // eax
  WCHAR *v9; // r15
  HANDLE FirstFileW; // r12
  PVOID *v11; // rcx
  int v12; // edx
  int v13; // edx
  int v14; // eax
  unsigned __int64 v15; // rax
  signed int v16; // edi
  LPCWSTR lpFileName; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v21; // [rsp+48h] [rbp-B8h]
  LPCWSTR v22; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v24; // [rsp+60h] [rbp-A0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF

  v24 = a1;
  v3 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids);
  }
  if ( !v3 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbfsutils.cpp", 0x62Eu, "wszPath");
  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbfsutils.cpp", 0x62Fu, "pullDirSize");
  v23 = 0;
  v22 = 0;
  lpFileName = 0;
  v4 = 0;
  v20 = 0;
  v5 = 0;
  pv = 0;
  *a2 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v6 = -1;
  v21 = 0;
  do
    ++v6;
  while ( v3[v6] );
  LastError = BlbutilRemoveAllTrailingBackslashes(v3, v6, (unsigned __int16 **)&lpFileName);
  if ( LastError < 0 )
    goto LABEL_70;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids, lpFileName);
  }
  if ( GetFileAttributesW(lpFileName) == -1 )
  {
LABEL_70:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_63;
  }
  appended = BlbutilAppendString(lpFileName, L"\\*", (unsigned __int16 **)&v22);
  v9 = (WCHAR *)v22;
  LastError = appended;
  if ( appended >= 0 )
  {
    LastError = BlbutilAppendString(lpFileName, L"\\", &v20);
    if ( LastError < 0 )
    {
      v4 = v20;
    }
    else
    {
      FirstFileW = FindFirstFileW(v9, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            81,
            (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
            (_DWORD)v9,
            LastError);
          v11 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v4 = v20;
        goto LABEL_58;
      }
      v4 = v20;
      do
      {
        if ( v5 )
        {
          CoTaskMemFree(v5);
          v5 = 0;
          pv = 0;
        }
        v12 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v12 = FindFileData.cFileName[1];
        if ( v12 )
        {
          v13 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
          {
            v13 = FindFileData.cFileName[1] - 46;
            if ( FindFileData.cFileName[1] == 46 )
              v13 = FindFileData.cFileName[2];
          }
          if ( v13 && _wcsicmp(FindFileData.cFileName, L"SystemStateBackup") )
          {
            v14 = BlbutilAppendString(v4, FindFileData.cFileName, (unsigned __int16 **)&pv);
            v5 = pv;
            LastError = v14;
            if ( v14 < 0 )
              goto LABEL_53;
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
            {
              LastError = BlbGetDirectorySize((unsigned __int16 *)pv, &v23);
              if ( LastError < 0 )
                goto LABEL_53;
              v15 = v23;
            }
            else
            {
              v21 = __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
              v15 = __PAIR64__(FindFileData.nFileSizeHigh, FindFileData.nFileSizeLow);
            }
            *a2 += v15;
          }
        }
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      v16 = GetLastError();
      if ( v16 != 18 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            82,
            (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
            (_DWORD)v9,
            v16);
        }
        if ( v16 > 0 )
          LastError = (unsigned __int16)v16 | 0x80070000;
        else
          LastError = v16;
      }
LABEL_53:
      if ( v5 )
        CoTaskMemFree(v5);
      FindClose(FirstFileW);
    }
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
LABEL_58:
  if ( v9 )
  {
    CoTaskMemFree(v9);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    CoTaskMemFree(v4);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  LODWORD(v3) = (_DWORD)v24;
LABEL_63:
  if ( lpFileName )
  {
    CoTaskMemFree((LPVOID)lpFileName);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( LastError < 0 )
  {
    if ( v11 == &WPP_GLOBAL_Control )
      return (unsigned int)LastError;
    if ( (*((_DWORD *)v11 + 7) & 0x200) != 0 && *((_BYTE *)v11 + 25) >= 2u )
    {
      WPP_SF_Sd(
        (unsigned int)v11[2],
        83,
        (unsigned int)&WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids,
        (_DWORD)v3,
        LastError);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 7) & 0x200) != 0 && *((_BYTE *)v11 + 25) >= 4u )
    WPP_SF_(v11[2], 84, &WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400f3280  mov     [rsp-8+arg_10], rbx
0x1400f3285  mov     [rsp-8+arg_18], rsi
0x1400f328a  push    rbp
0x1400f328b  push    rdi
0x1400f328c  push    r12
0x1400f328e  push    r14
0x1400f3290  push    r15
0x1400f3292  lea     rbp, [rsp-1D0h]
0x1400f329a  sub     rsp, 2D0h
0x1400f32a1  mov     rax, cs:__security_cookie
0x1400f32a8  xor     rax, rsp
0x1400f32ab  mov     [rbp+1F0h+var_30], rax
0x1400f32b2  mov     rdi, rdx
0x1400f32b5  mov     [rsp+2F0h+var_290], rcx
0x1400f32ba  mov     r15, rcx
0x1400f32bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f32c4  lea     rax, WPP_GLOBAL_Control
0x1400f32cb  cmp     rcx, rax
0x1400f32ce  jz      short loc_1400F32F4
0x1400f32d0  test    dword ptr [rcx+1Ch], 200h
0x1400f32d7  jz      short loc_1400F32F4
0x1400f32d9  cmp     byte ptr [rcx+19h], 4
0x1400f32dd  jb      short loc_1400F32F4
0x1400f32df  mov     rcx, [rcx+10h]
0x1400f32e3  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f32ea  mov     edx, 4Fh ; 'O'
0x1400f32ef  call    WPP_SF_
0x1400f32f4  xor     r12d, r12d
0x1400f32f7  test    r15, r15
0x1400f32fa  jnz     short loc_1400F3314
0x1400f32fc  lea     r8, aWszpath; "wszPath"
0x1400f3303  mov     edx, 62Eh; unsigned int
0x1400f3308  lea     rcx, aBaseStorBlbEng; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400f330f  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f3314  test    rdi, rdi
0x1400f3317  jnz     short loc_1400F3331
0x1400f3319  lea     r8, aPulldirsize; "pullDirSize"
0x1400f3320  mov     edx, 62Fh; unsigned int
0x1400f3325  lea     rcx, aBaseStorBlbEng; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400f332c  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f3331  xor     edx, edx; Val
0x1400f3333  mov     [rsp+2F0h+var_298], r12
0x1400f3338  mov     r8d, 250h; Size
0x1400f333e  mov     [rsp+2F0h+var_2A0], r12
0x1400f3343  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x1400f3348  mov     [rsp+2F0h+lpFileName], r12
0x1400f334d  mov     r14, r12
0x1400f3350  mov     [rsp+2F0h+var_2B0], r12
0x1400f3355  mov     rsi, r12
0x1400f3358  mov     [rsp+2F0h+pv], r12
0x1400f335d  mov     [rdi], r12
0x1400f3360  call    memset_0
0x1400f3365  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400f3369  mov     [rsp+2F0h+var_2A8], r12
0x1400f336e  inc     rdx; unsigned int
0x1400f3371  cmp     [r15+rdx*2], r12w
0x1400f3376  jnz     short loc_1400F336E
0x1400f3378  lea     r8, [rsp+2F0h+lpFileName]; unsigned __int16 **
0x1400f337d  mov     rcx, r15; unsigned __int16 *
0x1400f3380  call    ?BlbutilRemoveAllTrailingBackslashes@@YAJPEAGKPEAPEAG@Z; BlbutilRemoveAllTrailingBackslashes(ushort *,ulong,ushort * *)
0x1400f3385  mov     ebx, eax
0x1400f3387  test    eax, eax
0x1400f3389  js      loc_1400F36A0
0x1400f338f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3396  lea     rax, WPP_GLOBAL_Control
0x1400f339d  cmp     rcx, rax
0x1400f33a0  jz      short loc_1400F33CB
0x1400f33a2  test    dword ptr [rcx+1Ch], 200h
0x1400f33a9  jz      short loc_1400F33CB
0x1400f33ab  cmp     byte ptr [rcx+19h], 4
0x1400f33af  jb      short loc_1400F33CB
0x1400f33b1  mov     r9, [rsp+2F0h+lpFileName]
0x1400f33b6  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f33bd  mov     rcx, [rcx+10h]
0x1400f33c1  mov     edx, 50h ; 'P'
0x1400f33c6  call    WPP_SF_S
0x1400f33cb  mov     rcx, [rsp+2F0h+lpFileName]; lpFileName
0x1400f33d0  call    cs:__imp_GetFileAttributesW
0x1400f33d6  cmp     eax, 0FFFFFFFFh
0x1400f33d9  jz      loc_1400F36A0
0x1400f33df  mov     rcx, [rsp+2F0h+lpFileName]; unsigned __int16 *
0x1400f33e4  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int16 **
0x1400f33e9  lea     rdx, asc_140142BFC; "\\*"
0x1400f33f0  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1400f33f5  mov     r15, [rsp+2F0h+var_2A0]
0x1400f33fa  mov     ebx, eax
0x1400f33fc  test    eax, eax
0x1400f33fe  js      loc_1400F360D
0x1400f3404  mov     rcx, [rsp+2F0h+lpFileName]; unsigned __int16 *
0x1400f3409  lea     r8, [rsp+2F0h+var_2B0]; unsigned __int16 **
0x1400f340e  lea     rdx, asc_14013C090; "\\"
0x1400f3415  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1400f341a  mov     ebx, eax
0x1400f341c  test    eax, eax
0x1400f341e  js      loc_1400F3608
0x1400f3424  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1400f3429  mov     rcx, r15; lpFileName
0x1400f342c  call    cs:__imp_FindFirstFileW
0x1400f3432  mov     r12, rax
0x1400f3435  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400f3439  jnz     short loc_1400F34A2
0x1400f343b  call    cs:__imp_GetLastError
0x1400f3441  mov     ebx, eax
0x1400f3443  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f344a  lea     rax, WPP_GLOBAL_Control
0x1400f3451  cmp     rcx, rax
0x1400f3454  jz      short loc_1400F3488
0x1400f3456  test    dword ptr [rcx+1Ch], 200h
0x1400f345d  jz      short loc_1400F3488
0x1400f345f  cmp     byte ptr [rcx+19h], 2
0x1400f3463  jb      short loc_1400F3488
0x1400f3465  mov     rcx, [rcx+10h]
0x1400f3469  lea     edx, [r12+52h]
0x1400f346e  mov     r9, r15
0x1400f3471  mov     [rsp+2F0h+var_2D0], ebx
0x1400f3475  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f347c  call    WPP_SF_Sd
0x1400f3481  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3488  xor     r12d, r12d
0x1400f348b  test    ebx, ebx
0x1400f348d  jle     short loc_1400F3498
0x1400f348f  movzx   ebx, bx
0x1400f3492  or      ebx, 80070000h
0x1400f3498  mov     r14, [rsp+2F0h+var_2B0]
0x1400f349d  jmp     loc_1400F3614
0x1400f34a2  mov     r14, [rsp+2F0h+var_2B0]
0x1400f34a7  mov     ecx, 2Eh ; '.'
0x1400f34ac  test    rsi, rsi
0x1400f34af  jz      short loc_1400F34C4
0x1400f34b1  mov     rcx, rsi; pv
0x1400f34b4  call    cs:__imp_CoTaskMemFree
0x1400f34ba  xor     esi, esi
0x1400f34bc  mov     [rsp+2F0h+pv], rsi
0x1400f34c1  lea     ecx, [rsi+2Eh]
0x1400f34c4  movzx   edx, [rbp+1F0h+FindFileData.cFileName]
0x1400f34c8  movzx   eax, cx
0x1400f34cb  sub     edx, eax
0x1400f34cd  jnz     short loc_1400F34DD
0x1400f34cf  movzx   edx, [rbp+1F0h+FindFileData.cFileName+2]
0x1400f34d3  xor     eax, eax
0x1400f34d5  movzx   ecx, ax
0x1400f34d8  sub     edx, ecx
0x1400f34da  lea     ecx, [rax+2Eh]
0x1400f34dd  test    edx, edx
0x1400f34df  jz      loc_1400F357A
0x1400f34e5  movzx   edx, [rbp+1F0h+FindFileData.cFileName]
0x1400f34e9  movzx   eax, cx
0x1400f34ec  sub     edx, eax
0x1400f34ee  jnz     short loc_1400F3506
0x1400f34f0  movzx   edx, [rbp+1F0h+FindFileData.cFileName+2]
0x1400f34f4  movzx   eax, cx
0x1400f34f7  sub     edx, eax
0x1400f34f9  jnz     short loc_1400F3506
0x1400f34fb  movzx   edx, [rbp+1F0h+FindFileData.cFileName+4]
0x1400f34ff  xor     eax, eax
0x1400f3501  movzx   ecx, ax
0x1400f3504  sub     edx, ecx
0x1400f3506  test    edx, edx
0x1400f3508  jz      short loc_1400F357A
0x1400f350a  lea     rdx, aSystemstatebac_0; "SystemStateBackup"
0x1400f3511  lea     rcx, [rbp+1F0h+FindFileData.cFileName]; String1
0x1400f3515  call    cs:__imp__wcsicmp
0x1400f351b  test    eax, eax
0x1400f351d  jz      short loc_1400F357A
0x1400f351f  lea     r8, [rsp+2F0h+pv]; unsigned __int16 **
0x1400f3524  mov     rcx, r14; unsigned __int16 *
0x1400f3527  lea     rdx, [rbp+1F0h+FindFileData.cFileName]; unsigned __int16 *
0x1400f352b  call    ?BlbutilAppendString@@YAJPEBG0PEAPEAG@Z; BlbutilAppendString(ushort const *,ushort const *,ushort * *)
0x1400f3530  mov     rsi, [rsp+2F0h+pv]
0x1400f3535  mov     ebx, eax
0x1400f3537  test    eax, eax
0x1400f3539  js      loc_1400F35EC
0x1400f353f  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x1400f3544  jz      short loc_1400F3564
0x1400f3546  lea     rdx, [rsp+2F0h+var_298]; unsigned __int64 *
0x1400f354b  mov     rcx, rsi; unsigned __int16 *
0x1400f354e  call    ?BlbGetDirectorySize@@YAJPEAGPEA_K@Z; BlbGetDirectorySize(ushort *,unsigned __int64 *)
0x1400f3553  mov     ebx, eax
0x1400f3555  test    eax, eax
0x1400f3557  js      loc_1400F35EC
0x1400f355d  mov     rax, [rsp+2F0h+var_298]
0x1400f3562  jmp     short loc_1400F3577
0x1400f3564  mov     eax, [rbp+1F0h+FindFileData.nFileSizeLow]
0x1400f3567  mov     dword ptr [rsp+2F0h+var_2A8], eax
0x1400f356b  mov     eax, [rbp+1F0h+FindFileData.nFileSizeHigh]
0x1400f356e  mov     dword ptr [rsp+2F0h+var_2A8+4], eax
0x1400f3572  mov     rax, [rsp+2F0h+var_2A8]
0x1400f3577  add     [rdi], rax
0x1400f357a  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x1400f357f  mov     rcx, r12; hFindFile
0x1400f3582  call    cs:__imp_FindNextFileW
0x1400f3588  test    eax, eax
0x1400f358a  jnz     loc_1400F34A7
0x1400f3590  call    cs:__imp_GetLastError
0x1400f3596  mov     edi, eax
0x1400f3598  cmp     eax, 12h
0x1400f359b  jz      short loc_1400F35EC
0x1400f359d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f35a4  lea     rax, WPP_GLOBAL_Control
0x1400f35ab  cmp     rcx, rax
0x1400f35ae  jz      short loc_1400F35DB
0x1400f35b0  test    dword ptr [rcx+1Ch], 200h
0x1400f35b7  jz      short loc_1400F35DB
0x1400f35b9  cmp     byte ptr [rcx+19h], 2
0x1400f35bd  jb      short loc_1400F35DB
0x1400f35bf  mov     rcx, [rcx+10h]
0x1400f35c3  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f35ca  mov     edx, 52h ; 'R'
0x1400f35cf  mov     [rsp+2F0h+var_2D0], edi
0x1400f35d3  mov     r9, r15
0x1400f35d6  call    WPP_SF_Sd
0x1400f35db  test    edi, edi
0x1400f35dd  jg      short loc_1400F35E3
0x1400f35df  mov     ebx, edi
0x1400f35e1  jmp     short loc_1400F35EC
0x1400f35e3  movzx   ebx, di
0x1400f35e6  or      ebx, 80070000h
0x1400f35ec  test    rsi, rsi
0x1400f35ef  jz      short loc_1400F35FA
0x1400f35f1  mov     rcx, rsi; pv
0x1400f35f4  call    cs:__imp_CoTaskMemFree
0x1400f35fa  mov     rcx, r12; hFindFile
0x1400f35fd  call    cs:__imp_FindClose
0x1400f3603  xor     r12d, r12d
0x1400f3606  jmp     short loc_1400F360D
0x1400f3608  mov     r14, [rsp+2F0h+var_2B0]
0x1400f360d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3614  test    r15, r15
0x1400f3617  jz      short loc_1400F3629
0x1400f3619  mov     rcx, r15; pv
0x1400f361c  call    cs:__imp_CoTaskMemFree
0x1400f3622  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f3629  test    r14, r14
0x1400f362c  jz      short loc_1400F363E
0x1400f362e  mov     rcx, r14; pv
0x1400f3631  call    cs:__imp_CoTaskMemFree
0x1400f3637  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f363e  mov     r15, [rsp+2F0h+var_290]
0x1400f3643  cmp     [rsp+2F0h+lpFileName], r12
0x1400f3648  jz      short loc_1400F365C
0x1400f364a  mov     rcx, [rsp+2F0h+lpFileName]; pv
0x1400f364f  call    cs:__imp_CoTaskMemFree
0x1400f3655  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f365c  test    ebx, ebx
0x1400f365e  jns     short loc_1400F36A9
0x1400f3660  lea     rdi, WPP_GLOBAL_Control
0x1400f3667  cmp     rcx, rdi
0x1400f366a  jz      short loc_1400F36D9
0x1400f366c  test    dword ptr [rcx+1Ch], 200h
0x1400f3673  jz      short loc_1400F36B0
0x1400f3675  cmp     byte ptr [rcx+19h], 2
0x1400f3679  jb      short loc_1400F36B0
0x1400f367b  mov     rcx, [rcx+10h]
0x1400f367f  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f3686  mov     edx, 53h ; 'S'
0x1400f368b  mov     [rsp+2F0h+var_2D0], ebx
0x1400f368f  mov     r9, r15
0x1400f3692  call    WPP_SF_Sd
0x1400f3697  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f369e  jmp     short loc_1400F36B0
0x1400f36a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f36a7  jmp     short loc_1400F3643
0x1400f36a9  lea     rdi, WPP_GLOBAL_Control
0x1400f36b0  cmp     rcx, rdi
0x1400f36b3  jz      short loc_1400F36D9
0x1400f36b5  test    dword ptr [rcx+1Ch], 200h
0x1400f36bc  jz      short loc_1400F36D9
0x1400f36be  cmp     byte ptr [rcx+19h], 4
0x1400f36c2  jb      short loc_1400F36D9
0x1400f36c4  mov     rcx, [rcx+10h]
0x1400f36c8  lea     r8, WPP_d304baef4a5a329cd1a7abd9dd7d3c65_Traceguids
0x1400f36cf  mov     edx, 54h ; 'T'
0x1400f36d4  call    WPP_SF_
0x1400f36d9  mov     eax, ebx
0x1400f36db  mov     rcx, [rbp+1F0h+var_30]
0x1400f36e2  xor     rcx, rsp; StackCookie
0x1400f36e5  call    __security_check_cookie
0x1400f36ea  lea     r11, [rsp+2F0h+var_20]
0x1400f36f2  mov     rbx, [r11+40h]
0x1400f36f6  mov     rsi, [r11+48h]
0x1400f36fa  mov     rsp, r11
0x1400f36fd  pop     r15
0x1400f36ff  pop     r14
0x1400f3701  pop     r12
0x1400f3703  pop     rdi
0x1400f3704  pop     rbp
0x1400f3705  retn
```
