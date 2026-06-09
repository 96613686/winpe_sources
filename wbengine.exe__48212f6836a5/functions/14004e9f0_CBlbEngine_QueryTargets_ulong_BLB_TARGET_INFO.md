# CBlbEngine::QueryTargets(ulong *,_BLB_TARGET_INFO * *)

- ea: `0x14004e9f0`
- end: `0x14004efeb`
- name: `?QueryTargets@CBlbEngine@@UEAAJPEAKPEAPEAU_BLB_TARGET_INFO@@@Z`
- size: `1531`
- prototype: `__int64 __fastcall(CBlbEngine *__hidden this, unsigned int *, struct _BLB_TARGET_INFO **)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x140055280`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x14003c434`
- `0x14004504c`
- `0x140048394`
- `0x14004e9f0`
- `0x140102a34`
- `0x1401060f4`
- `0x1401061f8`
- `0x14012d2d8`
- `0x140134d20`

## import_xrefs

- `KERNEL32!FindVolumeClose` at `0x14004ebe0`
- `KERNEL32!FindVolumeClose` at `0x14004ef9e`
- `KERNEL32!FindVolumeClose` at `0x14004ebe0`
- `KERNEL32!FindVolumeClose` at `0x14004ef9e`
- `KERNEL32!FindNextVolumeW` at `0x14004ebc2`
- `KERNEL32!FindNextVolumeW` at `0x14004ee73`
- `KERNEL32!FindNextVolumeW` at `0x14004ebc2`
- `KERNEL32!FindNextVolumeW` at `0x14004ee73`
- `KERNEL32!FindFirstVolumeW` at `0x14004eb4d`
- `KERNEL32!FindFirstVolumeW` at `0x14004ec1e`
- `KERNEL32!FindFirstVolumeW` at `0x14004eb4d`
- `KERNEL32!FindFirstVolumeW` at `0x14004ec1e`
- `KERNEL32!GetLastError` at `0x14004eb5c`
- `KERNEL32!GetLastError` at `0x14004ebcc`
- `KERNEL32!GetLastError` at `0x14004ec2d`
- `KERNEL32!GetLastError` at `0x14004ee81`
- `KERNEL32!GetLastError` at `0x14004eb5c`
- `KERNEL32!GetLastError` at `0x14004ebcc`
- `KERNEL32!GetLastError` at `0x14004ec2d`
- `KERNEL32!GetLastError` at `0x14004ee81`
- `ole32!CoTaskMemAlloc` at `0x14004ebf1`
- `ole32!CoTaskMemAlloc` at `0x14004ebf1`
- `ole32!CoTaskMemFree` at `0x14004ee9b`
- `ole32!CoTaskMemFree` at `0x14004efca`
- `ole32!CoTaskMemFree` at `0x14004ee9b`
- `ole32!CoTaskMemFree` at `0x14004efca`
- `ole32!CoTaskMemRealloc` at `0x14004ed28`
- `ole32!CoTaskMemRealloc` at `0x14004ed28`

## string_xrefs

- `0x14004ef16`: `base\stor\blb\engine\service\engine.cpp`

## pseudocode

```c
__int64 __fastcall CBlbEngine::QueryTargets(CBlbEngine *this, unsigned int *a2, struct _BLB_TARGET_INFO **a3)
{
  struct _BLB_TARGET_INFO **v3; // rax
  PVOID *v6; // rcx
  signed int IsInitialized; // ebx
  HANDLE FirstVolumeW; // r12
  bool v10; // sf
  __int64 v11; // r15
  LPVOID *v12; // rax
  LPVOID *v13; // rsi
  __int64 v14; // r14
  int IsTargetProbable; // eax
  _QWORD *v16; // rcx
  int v17; // edx
  bool v18; // cf
  __int64 v19; // rdi
  LPVOID *v20; // rax
  LPVOID *v21; // rbx
  LPVOID *v22; // rdi
  int v23; // eax
  bool v24; // al
  int v25; // eax
  signed int LastError; // edi
  struct _BLB_TARGET_INFO **v27; // rax
  __int64 i; // rdi
  unsigned __int8 v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v30; // [rsp+31h] [rbp-CFh] BYREF
  unsigned __int8 v31[6]; // [rsp+32h] [rbp-CEh] BYREF
  struct _BLB_TARGET_INFO **v32; // [rsp+38h] [rbp-C8h]
  WCHAR szVolumeName[264]; // [rsp+40h] [rbp-C0h] BYREF

  v3 = a3;
  v30 = 0;
  v32 = a3;
  v31[0] = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v3 = v32;
  }
  if ( a2 )
  {
    *a2 = 0;
    if ( !v3 )
    {
      IsInitialized = -2147467261;
LABEL_9:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_10;
    }
    *v3 = 0;
    IsInitialized = CBlbEngine::IsInitialized(this);
    if ( IsInitialized < 0 )
      goto LABEL_9;
    FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
    if ( FirstVolumeW == (HANDLE)-1LL )
    {
      IsInitialized = GetLastError();
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      v10 = IsInitialized < 0;
      if ( IsInitialized <= 0 )
      {
LABEL_107:
        if ( !v10 )
          goto LABEL_14;
        goto LABEL_10;
      }
      IsInitialized = (unsigned __int16)IsInitialized | 0x80070000;
LABEL_106:
      v10 = IsInitialized < 0;
      goto LABEL_107;
    }
    LODWORD(v11) = 0;
    do
      v11 = (unsigned int)(v11 + 1);
    while ( FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) );
    IsInitialized = GetLastError();
    if ( IsInitialized != 18 )
    {
      v13 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      }
      if ( IsInitialized > 0 )
      {
        IsInitialized = (unsigned __int16)IsInitialized;
        goto LABEL_100;
      }
LABEL_101:
      FindVolumeClose(FirstVolumeW);
      if ( !v13 )
        goto LABEL_105;
      goto LABEL_102;
    }
    FindVolumeClose(FirstVolumeW);
    v12 = (LPVOID *)CoTaskMemAlloc(96LL * (unsigned int)v11);
    v13 = v12;
    if ( !v12 )
    {
      IsInitialized = -2147024882;
      goto LABEL_9;
    }
    memset_0(v12, 0, 96 * v11);
    FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
    if ( FirstVolumeW == (HANDLE)-1LL )
    {
      IsInitialized = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
      }
      if ( IsInitialized > 0 )
        IsInitialized = (unsigned __int16)IsInitialized | 0x80070000;
LABEL_102:
      for ( i = 0; (unsigned int)i < (unsigned int)v11; i = (unsigned int)(i + 1) )
        CleanupTargetInfo(&v13[12 * i]);
      CoTaskMemFree(v13);
LABEL_105:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_106;
    }
    v14 = 0;
    while ( 1 )
    {
      v29 = 0;
      IsTargetProbable = BlbIsTargetProbable(szVolumeName, &v29);
      if ( IsTargetProbable < 0 )
        break;
      if ( !v29 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
            szVolumeName);
        }
        goto LABEL_46;
      }
      v18 = (unsigned int)v14 < (unsigned int)v11;
      if ( (_DWORD)v14 == (_DWORD)v11 )
      {
        v19 = (unsigned int)(v11 + 8);
        v20 = (LPVOID *)CoTaskMemRealloc(v13, 96 * v19);
        v21 = v20;
        if ( !v20 )
        {
          IsInitialized = -2147024882;
          goto LABEL_101;
        }
        memset_0(&v20[12 * (unsigned int)v11], 0, 0x300u);
        LODWORD(v11) = v11 + 8;
        v13 = v21;
        v18 = (unsigned int)v14 < (unsigned int)v19;
      }
      if ( !v18 )
      {
        BlbAssert("base\\stor\\blb\\engine\\service\\engine.cpp", 0x533u, "cTarget < cMaxTarget");
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
        }
        IsInitialized = -2147418113;
        goto LABEL_101;
      }
      v22 = &v13[12 * v14];
      v23 = CBlbEngine::FillTargetInfo(szVolumeName, (struct _BLB_TARGET_INFO *)v22);
      IsInitialized = v23;
      if ( v23 < 0 )
      {
        if ( v23 == -2147024882 )
          goto LABEL_101;
        IsInitialized = 0;
        goto LABEL_75;
      }
      IsTargetProbable = BlbIsTargetValid(szVolumeName, &v30, v31);
      if ( IsTargetProbable >= 0 )
      {
        v24 = !v30 && v31[0];
        *((_BYTE *)v22 + 73) = v24;
        v25 = BlbCheckIfOldFormatVhdsExist(szVolumeName, (unsigned __int8 *)v22 + 92);
        IsInitialized = v25;
        if ( v25 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              80,
              (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
              (unsigned int)szVolumeName,
              v25);
          }
          IsInitialized = 0;
        }
        v14 = (unsigned int)(v14 + 1);
        goto LABEL_75;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v17 = 79;
LABEL_45:
        WPP_SF_Sd(
          v16[2],
          v17,
          (unsigned int)&WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids,
          (unsigned int)szVolumeName,
          IsTargetProbable);
      }
LABEL_46:
      IsInitialized = 0;
LABEL_75:
      if ( !FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) )
      {
        LastError = GetLastError();
        if ( LastError == 18 )
        {
          if ( !(_DWORD)v14 && v13 )
          {
            CoTaskMemFree(v13);
            v13 = 0;
          }
          v27 = v32;
          *a2 = v14;
          *v27 = (struct _BLB_TARGET_INFO *)v13;
          v13 = 0;
          goto LABEL_101;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
        }
        if ( LastError <= 0 )
        {
          IsInitialized = LastError;
          goto LABEL_101;
        }
        IsInitialized = (unsigned __int16)LastError;
LABEL_100:
        IsInitialized |= 0x80070000;
        goto LABEL_101;
      }
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_46;
    }
    v17 = 76;
    goto LABEL_45;
  }
  IsInitialized = -2147467261;
LABEL_10:
  if ( v6 == &WPP_GLOBAL_Control )
    return (unsigned int)IsInitialized;
  if ( (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
  {
    WPP_SF_d(v6[2], 82, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_14:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_(v6[2], 83, &WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids);
  return (unsigned int)IsInitialized;
}

```

## disassembly

```asm
0x14004e9f0  mov     [rsp-8+arg_18], rbx
0x14004e9f5  push    rbp
0x14004e9f6  push    rsi
0x14004e9f7  push    rdi
0x14004e9f8  push    r12
0x14004e9fa  push    r13
0x14004e9fc  push    r14
0x14004e9fe  push    r15
0x14004ea00  lea     rbp, [rsp-160h]
0x14004ea08  sub     rsp, 260h
0x14004ea0f  mov     rax, cs:__security_cookie
0x14004ea16  xor     rax, rsp
0x14004ea19  mov     [rbp+190h+var_40], rax
0x14004ea20  mov     rax, r8
0x14004ea23  mov     [rsp+290h+var_25F], 0
0x14004ea28  mov     [rsp+290h+var_258], rax
0x14004ea2d  mov     r13, rdx
0x14004ea30  mov     rbx, rcx
0x14004ea33  mov     [rsp+290h+var_25E], 0
0x14004ea38  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ea3f  lea     rdi, WPP_GLOBAL_Control
0x14004ea46  cmp     rcx, rdi
0x14004ea49  jz      short loc_14004EA7B
0x14004ea4b  test    dword ptr [rcx+1Ch], 200h
0x14004ea52  jz      short loc_14004EA7B
0x14004ea54  cmp     byte ptr [rcx+19h], 4
0x14004ea58  jb      short loc_14004EA7B
0x14004ea5a  mov     rcx, [rcx+10h]
0x14004ea5e  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004ea65  mov     edx, 48h ; 'H'
0x14004ea6a  call    WPP_SF_
0x14004ea6f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ea76  mov     rax, [rsp+290h+var_258]
0x14004ea7b  test    r13, r13
0x14004ea7e  jnz     short loc_14004EA87
0x14004ea80  mov     ebx, 80004003h
0x14004ea85  jmp     short loc_14004EAA4
0x14004ea87  mov     dword ptr [r13+0], 0
0x14004ea8f  test    rax, rax
0x14004ea92  jnz     loc_14004EB26
0x14004ea98  mov     ebx, 80004003h
0x14004ea9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eaa4  cmp     rcx, rdi
0x14004eaa7  jz      short loc_14004EAFA
0x14004eaa9  test    byte ptr [rcx+1Ch], 1
0x14004eaad  jz      short loc_14004EAD4
0x14004eaaf  cmp     byte ptr [rcx+19h], 2
0x14004eab3  jb      short loc_14004EAD4
0x14004eab5  mov     rcx, [rcx+10h]
0x14004eab9  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004eac0  mov     edx, 52h ; 'R'
0x14004eac5  mov     r9d, ebx
0x14004eac8  call    WPP_SF_d
0x14004eacd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ead4  cmp     rcx, rdi
0x14004ead7  jz      short loc_14004EAFA
0x14004ead9  test    byte ptr [rcx+1Ch], 1
0x14004eadd  jz      short loc_14004EAFA
0x14004eadf  cmp     byte ptr [rcx+19h], 4
0x14004eae3  jb      short loc_14004EAFA
0x14004eae5  mov     rcx, [rcx+10h]
0x14004eae9  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004eaf0  mov     edx, 53h ; 'S'
0x14004eaf5  call    WPP_SF_
0x14004eafa  mov     eax, ebx
0x14004eafc  mov     rcx, [rbp+190h+var_40]
0x14004eb03  xor     rcx, rsp; StackCookie
0x14004eb06  call    __security_check_cookie
0x14004eb0b  mov     rbx, [rsp+290h+arg_18]
0x14004eb13  add     rsp, 260h
0x14004eb1a  pop     r15
0x14004eb1c  pop     r14
0x14004eb1e  pop     r13
0x14004eb20  pop     r12
0x14004eb22  pop     rdi
0x14004eb23  pop     rsi
0x14004eb24  pop     rbp
0x14004eb25  retn
0x14004eb26  mov     rcx, rbx; this
0x14004eb29  mov     qword ptr [rax], 0
0x14004eb30  call    ?IsInitialized@CBlbEngine@@QEAAJXZ; CBlbEngine::IsInitialized(void)
0x14004eb35  mov     ebx, eax
0x14004eb37  test    eax, eax
0x14004eb39  js      loc_14004EA9D
0x14004eb3f  mov     r14d, 104h
0x14004eb45  lea     rcx, [rsp+290h+szVolumeName]; lpszVolumeName
0x14004eb4a  mov     edx, r14d; cchBufferLength
0x14004eb4d  call    cs:__imp_FindFirstVolumeW
0x14004eb53  mov     r12, rax
0x14004eb56  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004eb5a  jnz     short loc_14004EBB1
0x14004eb5c  call    cs:__imp_GetLastError
0x14004eb62  mov     ebx, eax
0x14004eb64  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eb6b  cmp     rcx, rdi
0x14004eb6e  jz      short loc_14004EB9B
0x14004eb70  test    byte ptr [rcx+1Ch], 1
0x14004eb74  jz      short loc_14004EB9B
0x14004eb76  cmp     byte ptr [rcx+19h], 2
0x14004eb7a  jb      short loc_14004EB9B
0x14004eb7c  mov     rcx, [rcx+10h]
0x14004eb80  lea     edx, [r12+4Ah]
0x14004eb85  mov     r9d, eax
0x14004eb88  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004eb8f  call    WPP_SF_d
0x14004eb94  mov     rcx, cs:WPP_GLOBAL_Control
0x14004eb9b  test    ebx, ebx
0x14004eb9d  jle     loc_14004EFD9
0x14004eba3  movzx   ebx, bx
0x14004eba6  or      ebx, 80070000h
0x14004ebac  jmp     loc_14004EFD7
0x14004ebb1  xor     r15d, r15d
0x14004ebb4  mov     r8d, r14d; cchBufferLength
0x14004ebb7  lea     rdx, [rsp+290h+szVolumeName]; lpszVolumeName
0x14004ebbc  mov     rcx, r12; hFindVolume
0x14004ebbf  inc     r15d
0x14004ebc2  call    cs:__imp_FindNextVolumeW
0x14004ebc8  test    eax, eax
0x14004ebca  jnz     short loc_14004EBB4
0x14004ebcc  call    cs:__imp_GetLastError
0x14004ebd2  mov     ebx, eax
0x14004ebd4  cmp     eax, 12h
0x14004ebd7  jnz     loc_14004EF5E
0x14004ebdd  mov     rcx, r12; hFindVolume
0x14004ebe0  call    cs:__imp_FindVolumeClose
0x14004ebe6  lea     rbx, [r15+r15*2]
0x14004ebea  shl     rbx, 5
0x14004ebee  mov     rcx, rbx; cb
0x14004ebf1  call    cs:__imp_CoTaskMemAlloc
0x14004ebf7  mov     rsi, rax
0x14004ebfa  test    rax, rax
0x14004ebfd  jnz     short loc_14004EC09
0x14004ebff  mov     ebx, 8007000Eh
0x14004ec04  jmp     loc_14004EA9D
0x14004ec09  mov     r8, rbx; Size
0x14004ec0c  xor     edx, edx; Val
0x14004ec0e  mov     rcx, rax; void *
0x14004ec11  call    memset_0
0x14004ec16  mov     edx, r14d; cchBufferLength
0x14004ec19  lea     rcx, [rsp+290h+szVolumeName]; lpszVolumeName
0x14004ec1e  call    cs:__imp_FindFirstVolumeW
0x14004ec24  mov     r12, rax
0x14004ec27  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14004ec2b  jnz     short loc_14004EC7B
0x14004ec2d  call    cs:__imp_GetLastError
0x14004ec33  mov     ebx, eax
0x14004ec35  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ec3c  cmp     rcx, rdi
0x14004ec3f  jz      short loc_14004EC65
0x14004ec41  test    byte ptr [rcx+1Ch], 1
0x14004ec45  jz      short loc_14004EC65
0x14004ec47  cmp     byte ptr [rcx+19h], 2
0x14004ec4b  jb      short loc_14004EC65
0x14004ec4d  mov     rcx, [rcx+10h]
0x14004ec51  lea     edx, [r12+4Ch]
0x14004ec56  mov     r9d, eax
0x14004ec59  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004ec60  call    WPP_SF_d
0x14004ec65  test    ebx, ebx
0x14004ec67  jle     loc_14004EFA9
0x14004ec6d  movzx   ebx, bx
0x14004ec70  or      ebx, 80070000h
0x14004ec76  jmp     loc_14004EFA9
0x14004ec7b  xor     r14d, r14d
0x14004ec7e  lea     rdx, [rsp+290h+var_260]; unsigned __int8 *
0x14004ec83  mov     [rsp+290h+var_260], 0
0x14004ec88  lea     rcx, [rsp+290h+szVolumeName]; unsigned __int16 *
0x14004ec8d  call    ?BlbIsTargetProbable@@YAJPEAGPEAE@Z; BlbIsTargetProbable(ushort *,uchar *)
0x14004ec92  test    eax, eax
0x14004ec94  jns     short loc_14004ECD6
0x14004ec96  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ec9d  cmp     rcx, rdi
0x14004eca0  jz      short loc_14004ECCF
0x14004eca2  test    dword ptr [rcx+1Ch], 200h
0x14004eca9  jz      short loc_14004ECCF
0x14004ecab  cmp     byte ptr [rcx+19h], 3
0x14004ecaf  jb      short loc_14004ECCF
0x14004ecb1  mov     edx, 4Ch ; 'L'
0x14004ecb6  mov     rcx, [rcx+10h]
0x14004ecba  lea     r9, [rsp+290h+szVolumeName]
0x14004ecbf  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004ecc6  mov     [rsp+290h+var_270], eax
0x14004ecca  call    WPP_SF_Sd
0x14004eccf  xor     ebx, ebx
0x14004ecd1  jmp     loc_14004EE65
0x14004ecd6  cmp     [rsp+290h+var_260], 0
0x14004ecdb  jnz     short loc_14004ED14
0x14004ecdd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ece4  cmp     rcx, rdi
0x14004ece7  jz      short loc_14004ECCF
0x14004ece9  test    dword ptr [rcx+1Ch], 200h
0x14004ecf0  jz      short loc_14004ECCF
0x14004ecf2  cmp     byte ptr [rcx+19h], 3
0x14004ecf6  jb      short loc_14004ECCF
0x14004ecf8  mov     rcx, [rcx+10h]
0x14004ecfc  lea     r9, [rsp+290h+szVolumeName]
0x14004ed01  mov     edx, 4Dh ; 'M'
0x14004ed06  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004ed0d  call    WPP_SF_S
0x14004ed12  jmp     short loc_14004ECCF
0x14004ed14  cmp     r14d, r15d
0x14004ed17  jnz     short loc_14004ED65
0x14004ed19  lea     edi, [r15+8]
0x14004ed1d  mov     rcx, rsi; pv
0x14004ed20  lea     rdx, [rdi+rdi*2]
0x14004ed24  shl     rdx, 5; cb
0x14004ed28  call    cs:__imp_CoTaskMemRealloc
0x14004ed2e  mov     rbx, rax
0x14004ed31  test    rax, rax
0x14004ed34  jz      loc_14004EEB6
0x14004ed3a  mov     ecx, r15d
0x14004ed3d  xor     edx, edx; Val
0x14004ed3f  mov     r8d, 300h; Size
0x14004ed45  lea     rcx, [rcx+rcx*2]
0x14004ed49  shl     rcx, 5
0x14004ed4d  add     rcx, rax; void *
0x14004ed50  call    memset_0
0x14004ed55  mov     r15d, edi
0x14004ed58  mov     rsi, rbx
0x14004ed5b  cmp     r14d, r15d
0x14004ed5e  lea     rdi, WPP_GLOBAL_Control
0x14004ed65  jnb     loc_14004EF0A
0x14004ed6b  lea     rdi, [r14+r14*2]
0x14004ed6f  shl     rdi, 5
0x14004ed73  lea     rcx, [rsp+290h+szVolumeName]; unsigned __int16 *
0x14004ed78  add     rdi, rsi
0x14004ed7b  mov     rdx, rdi; struct _BLB_TARGET_INFO *
0x14004ed7e  call    ?FillTargetInfo@CBlbEngine@@CAJPEAGPEAU_BLB_TARGET_INFO@@@Z; CBlbEngine::FillTargetInfo(ushort *,_BLB_TARGET_INFO *)
0x14004ed83  mov     ebx, eax
0x14004ed85  test    eax, eax
0x14004ed87  jns     short loc_14004EDA2
0x14004ed89  cmp     eax, 8007000Eh
0x14004ed8e  jz      loc_14004EF9B
0x14004ed94  xor     ebx, ebx
0x14004ed96  lea     rdi, WPP_GLOBAL_Control
0x14004ed9d  jmp     loc_14004EE65
0x14004eda2  lea     r8, [rsp+290h+var_25E]; unsigned __int8 *
0x14004eda7  lea     rdx, [rsp+290h+var_25F]; unsigned __int8 *
0x14004edac  lea     rcx, [rsp+290h+szVolumeName]; unsigned __int16 *
0x14004edb1  call    ?BlbIsTargetValid@@YAJPEAGPEAE1@Z; BlbIsTargetValid(ushort *,uchar *,uchar *)
0x14004edb6  test    eax, eax
0x14004edb8  jns     short loc_14004EDEF
0x14004edba  mov     rcx, cs:WPP_GLOBAL_Control
0x14004edc1  lea     rdi, WPP_GLOBAL_Control
0x14004edc8  cmp     rcx, rdi
0x14004edcb  jz      loc_14004ECCF
0x14004edd1  test    byte ptr [rcx+1Ch], 1
0x14004edd5  jz      loc_14004ECCF
0x14004eddb  cmp     byte ptr [rcx+19h], 3
0x14004eddf  jb      loc_14004ECCF
0x14004ede5  mov     edx, 4Fh ; 'O'
0x14004edea  jmp     loc_14004ECB6
0x14004edef  cmp     [rsp+290h+var_25F], 0
0x14004edf4  jnz     short loc_14004EE01
0x14004edf6  cmp     [rsp+290h+var_25E], 0
0x14004edfb  jz      short loc_14004EE01
0x14004edfd  mov     al, 1
0x14004edff  jmp     short loc_14004EE03
0x14004ee01  xor     al, al
0x14004ee03  lea     rdx, [rdi+5Ch]; unsigned __int8 *
0x14004ee07  mov     [rdi+49h], al
0x14004ee0a  lea     rcx, [rsp+290h+szVolumeName]; unsigned __int16 *
0x14004ee0f  call    ?BlbCheckIfOldFormatVhdsExist@@YAJPEBGPEAE@Z; BlbCheckIfOldFormatVhdsExist(ushort const *,uchar *)
0x14004ee14  mov     ebx, eax
0x14004ee16  test    eax, eax
0x14004ee18  jns     short loc_14004EE5B
0x14004ee1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ee21  lea     rdi, WPP_GLOBAL_Control
0x14004ee28  cmp     rcx, rdi
0x14004ee2b  jz      short loc_14004EE57
0x14004ee2d  test    byte ptr [rcx+1Ch], 1
0x14004ee31  jz      short loc_14004EE57
0x14004ee33  cmp     byte ptr [rcx+19h], 3
0x14004ee37  jb      short loc_14004EE57
0x14004ee39  mov     rcx, [rcx+10h]
0x14004ee3d  lea     r9, [rsp+290h+szVolumeName]
0x14004ee42  mov     edx, 50h ; 'P'
0x14004ee47  mov     [rsp+290h+var_270], eax
0x14004ee4b  lea     r8, WPP_9870b93072233f1de7a88e8cd32d2237_Traceguids
0x14004ee52  call    WPP_SF_Sd
0x14004ee57  xor     ebx, ebx
0x14004ee59  jmp     short loc_14004EE62
0x14004ee5b  lea     rdi, WPP_GLOBAL_Control
0x14004ee62  inc     r14d
0x14004ee65  mov     r8d, 104h; cchBufferLength
0x14004ee6b  lea     rdx, [rsp+290h+szVolumeName]; lpszVolumeName
0x14004ee70  mov     rcx, r12; hFindVolume
0x14004ee73  call    cs:__imp_FindNextVolumeW
0x14004ee79  test    eax, eax
0x14004ee7b  jnz     loc_14004EC7E
0x14004ee81  call    cs:__imp_GetLastError
0x14004ee87  mov     edi, eax
0x14004ee89  cmp     eax, 12h
0x14004ee8c  jnz     short loc_14004EEC0
0x14004ee8e  test    r14d, r14d
0x14004ee91  jnz     short loc_14004EEA3
0x14004ee93  test    rsi, rsi
0x14004ee96  jz      short loc_14004EEA3
0x14004ee98  mov     rcx, rsi; pv
0x14004ee9b  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
