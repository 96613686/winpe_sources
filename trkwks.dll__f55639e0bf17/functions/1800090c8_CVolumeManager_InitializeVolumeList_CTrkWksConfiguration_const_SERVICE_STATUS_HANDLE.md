# CVolumeManager::InitializeVolumeList(CTrkWksConfiguration const *,SERVICE_STATUS_HANDLE__ *)

- ea: `0x1800090c8`
- end: `0x18000935d`
- name: `?InitializeVolumeList@CVolumeManager@@AEAAXPEBVCTrkWksConfiguration@@PEAUSERVICE_STATUS_HANDLE__@@@Z`
- size: `661`
- prototype: `void __fastcall(const struct CTrkWksConfiguration **this, const struct CTrkWksConfiguration *, struct SERVICE_STATUS_HANDLE__ *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18000a880`

## callees

- `0x1800066c0`
- `0x1800090c8`
- `0x180009364`
- `0x180009488`
- `0x18000c330`
- `0x18000d020`
- `0x18000d318`
- `0x18000d39c`
- `0x18000dae8`
- `0x18000db28`
- `0x18000e218`
- `0x180010fbe`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092ff`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18000931d`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180011603`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x18000931d`
- `api-ms-win-core-file-l1-1-0!FindVolumeClose` at `0x180011603`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800091c1`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800091c1`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x18000911e`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x18000911e`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800091f5`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800091f5`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800092f5`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x1800092f5`

## pseudocode

```c
void __fastcall CVolumeManager::InitializeVolumeList(
        const struct CTrkWksConfiguration **this,
        const struct CTrkWksConfiguration *a2,
        struct SERVICE_STATUS_HANDLE__ *a3)
{
  HANDLE FirstVolumeW; // r15
  unsigned int v6; // esi
  __int64 v7; // r14
  PLogFileNotify *Volume; // rax
  struct CVolumeNode *v9; // rax
  struct CVolumeNode *v10; // rdi
  CVolume *v11; // rax
  CVolume *v12; // rax
  DWORD FileSystemFlags; // [rsp+44h] [rbp-2E4h] BYREF
  struct CVolumeNode *v14; // [rsp+48h] [rbp-2E0h]
  HANDLE v15; // [rsp+50h] [rbp-2D8h]
  const struct CTrkWksConfiguration **v16; // [rsp+58h] [rbp-2D0h]
  wchar_t szVolumeName[56]; // [rsp+70h] [rbp-2B8h] BYREF
  unsigned __int16 v18[264]; // [rsp+E0h] [rbp-248h] BYREF

  v16 = this;
  v14 = 0;
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x33u);
  v15 = FirstVolumeW;
  if ( FirstVolumeW == (HANDLE)-1LL )
    TrkRaiseLastError();
  v6 = 1;
  while ( v6 <= 0x1A )
  {
    v7 = -1;
    do
      ++v7;
    while ( szVolumeName[v7] );
    memcpy_0(v18, szVolumeName, 2LL * (unsigned int)v7);
    if ( 2 * (unsigned __int64)(unsigned int)(v7 - 1) >= 0x20A )
      _report_rangecheckfailure();
    v18[(unsigned int)(v7 - 1)] = 0;
    Volume = CVolumeManager::FindVolume((CVolumeManager *)this, v18);
    if ( Volume )
    {
      PLogFileNotify::Release(Volume);
      ++v6;
    }
    else
    {
      FileSystemFlags = 0;
      if ( GetDriveTypeW(szVolumeName) == 3
        && GetVolumeInformationW(szVolumeName, 0, 0, 0, 0, &FileSystemFlags, 0, 0)
        && (FileSystemFlags & 0x10000) != 0 )
      {
        v9 = (struct CVolumeNode *)operator new(0x10u);
        v10 = v9;
        if ( v9 )
        {
          *(_QWORD *)v9 = 0;
          *((_QWORD *)v9 + 1) = 0;
        }
        else
        {
          v10 = 0;
        }
        v14 = v10;
        if ( !v10 )
          TrkRaiseException(-2147024882);
        v11 = (CVolume *)operator new(0xB90u);
        if ( v11 )
          v12 = CVolume::CVolume(v11);
        else
          v12 = 0;
        *(_QWORD *)v10 = v12;
        if ( !v12 )
          TrkRaiseException(-2147024882);
        if ( (unsigned int)CVolume::Initialize(v12, szVolumeName, this[23], (struct CVolumeManager *)this, a3) )
        {
          ++v6;
          CVolumeManager::AddNodeToLinkedList((CVolumeManager *)this, v10);
          v10 = 0;
          v14 = 0;
        }
        if ( v10 )
        {
          PLogFileNotify::Release(*(PLogFileNotify **)v10);
          operator delete(v10);
          v14 = 0;
        }
      }
    }
    if ( !FindNextVolumeW(FirstVolumeW, szVolumeName, 0x33u) )
    {
      if ( GetLastError() != 18 )
        TrkRaiseLastError();
      break;
    }
  }
  FindVolumeClose(FirstVolumeW);
}

```

## disassembly

```asm
0x1800090c8  mov     [rsp+arg_8], rbx
0x1800090cd  mov     [rsp+arg_18], rsi
0x1800090d2  mov     [rsp+arg_10], r8
0x1800090d7  push    rdi
0x1800090d8  push    r12
0x1800090da  push    r13
0x1800090dc  push    r14
0x1800090de  push    r15
0x1800090e0  sub     rsp, 300h
0x1800090e7  mov     rax, cs:__security_cookie
0x1800090ee  xor     rax, rsp
0x1800090f1  mov     [rsp+328h+var_38], rax
0x1800090f9  mov     r12, r8
0x1800090fc  mov     r13, rcx
0x1800090ff  mov     [rsp+328h+var_2D0], rcx
0x180009104  mov     [rsp+328h+var_2D8], 0FFFFFFFFFFFFFFFFh
0x18000910d  xor     ebx, ebx
0x18000910f  mov     edi, ebx
0x180009111  mov     [rsp+328h+var_2E0], rbx
0x180009116  lea     edx, [rbx+33h]; cchBufferLength
0x180009119  lea     rcx, [rsp+328h+szVolumeName]; lpszVolumeName
0x18000911e  call    cs:__imp_FindFirstVolumeW
0x180009124  mov     r15, rax
0x180009127  mov     [rsp+328h+var_2D8], rax
0x18000912c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009130  jnz     short loc_180009137
0x180009132  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x180009137  mov     esi, 1
0x18000913c  mov     [rsp+328h+var_2E8], esi
0x180009140  cmp     esi, 1Ah
0x180009143  ja      loc_18000931A
0x180009149  lea     rax, [rsp+328h+szVolumeName]
0x18000914e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180009152  inc     r14
0x180009155  cmp     [rax+r14*2], bx
0x18000915a  jnz     short loc_180009152
0x18000915c  mov     r8d, r14d
0x18000915f  add     r8, r8; Size
0x180009162  lea     rdx, [rsp+328h+szVolumeName]; Src
0x180009167  lea     rcx, [rsp+328h+var_248]; void *
0x18000916f  call    memcpy_0
0x180009174  lea     ecx, [r14-1]
0x180009178  add     rcx, rcx
0x18000917b  cmp     rcx, 20Ah
0x180009182  jnb     loc_180009314
0x180009188  mov     [rsp+rcx+328h+var_248], bx
0x180009190  lea     rdx, [rsp+328h+var_248]; unsigned __int16 *
0x180009198  mov     rcx, r13; this
0x18000919b  call    ?FindVolume@CVolumeManager@@QEAAPEAVCVolume@@PEBG@Z; CVolumeManager::FindVolume(ushort const *)
0x1800091a0  test    rax, rax
0x1800091a3  jz      short loc_1800091B8
0x1800091a5  mov     rcx, rax; this
0x1800091a8  call    ?Release@PLogFileNotify@@QEAAKXZ; PLogFileNotify::Release(void)
0x1800091ad  inc     esi
0x1800091af  mov     [rsp+328h+var_2E8], esi
0x1800091b3  jmp     loc_1800092E7
0x1800091b8  mov     [rsp+328h+FileSystemFlags], ebx
0x1800091bc  lea     rcx, [rsp+328h+szVolumeName]; lpRootPathName
0x1800091c1  call    cs:__imp_GetDriveTypeW
0x1800091c7  cmp     eax, 3
0x1800091ca  jnz     loc_1800092E7
0x1800091d0  mov     [rsp+328h+nFileSystemNameSize], ebx; nFileSystemNameSize
0x1800091d4  mov     [rsp+328h+lpFileSystemNameBuffer], rbx; lpFileSystemNameBuffer
0x1800091d9  lea     rax, [rsp+328h+FileSystemFlags]
0x1800091de  mov     [rsp+328h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1800091e3  mov     [rsp+328h+lpMaximumComponentLength], rbx; lpMaximumComponentLength
0x1800091e8  xor     r9d, r9d; lpVolumeSerialNumber
0x1800091eb  xor     r8d, r8d; nVolumeNameSize
0x1800091ee  xor     edx, edx; lpVolumeNameBuffer
0x1800091f0  lea     rcx, [rsp+328h+szVolumeName]; lpRootPathName
0x1800091f5  call    cs:__imp_GetVolumeInformationW
0x1800091fb  test    eax, eax
0x1800091fd  jz      loc_1800092E7
0x180009203  test    [rsp+328h+FileSystemFlags], 10000h
0x18000920b  jz      loc_1800092E7
0x180009211  mov     ecx, 10h; Size
0x180009216  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000921b  mov     rdi, rax
0x18000921e  test    rax, rax
0x180009221  jz      short loc_18000922C
0x180009223  mov     [rax], rbx
0x180009226  mov     [rax+8], rbx
0x18000922a  jmp     short loc_18000922F
0x18000922c  mov     rdi, rbx
0x18000922f  mov     [rsp+328h+var_2E0], rdi
0x180009234  test    rdi, rdi
0x180009237  jnz     short loc_180009243
0x180009239  mov     ecx, 8007000Eh; int
0x18000923e  call    ?TrkRaiseException@@YAXJ@Z; TrkRaiseException(long)
0x180009243  mov     ecx, 0B90h; Size
0x180009248  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000924d  test    rax, rax
0x180009250  jz      short loc_18000925C
0x180009252  mov     rcx, rax; this
0x180009255  call    ??0CVolume@@QEAA@XZ; CVolume::CVolume(void)
0x18000925a  jmp     short loc_18000925F
0x18000925c  mov     rax, rbx
0x18000925f  mov     [rdi], rax
0x180009262  test    rax, rax
0x180009265  jnz     short loc_180009272
0x180009267  mov     ecx, 8007000Eh; int
0x18000926c  call    ?TrkRaiseException@@YAXJ@Z; TrkRaiseException(long)
0x180009271  nop
0x180009272  mov     [rsp+328h+lpMaximumComponentLength], r12; struct SERVICE_STATUS_HANDLE__ *
0x180009277  mov     r9, r13; struct CVolumeManager *
0x18000927a  mov     r8, [r13+0B8h]; struct CTrkWksConfiguration *
0x180009281  lea     rdx, [rsp+328h+szVolumeName]; pszSrc
0x180009286  mov     rcx, rax; this
0x180009289  call    ?Initialize@CVolume@@QEAAHPEBGPEBVCTrkWksConfiguration@@PEAVCVolumeManager@@PEAUSERVICE_STATUS_HANDLE__@@@Z; CVolume::Initialize(ushort const *,CTrkWksConfiguration const *,CVolumeManager *,SERVICE_STATUS_HANDLE__ *)
0x18000928e  test    eax, eax
0x180009290  jz      short loc_1800092AB
0x180009292  inc     esi
0x180009294  mov     [rsp+328h+var_2E8], esi
0x180009298  mov     rdx, rdi; struct CVolumeNode *
0x18000929b  mov     rcx, r13; this
0x18000929e  call    ?AddNodeToLinkedList@CVolumeManager@@AEAAXPEAVCVolumeNode@@@Z; CVolumeManager::AddNodeToLinkedList(CVolumeNode *)
0x1800092a3  mov     rdi, rbx
0x1800092a6  mov     [rsp+328h+var_2E0], rbx
0x1800092ab  jmp     short loc_1800092CA
0x1800092ad  xor     ebx, ebx
0x1800092af  mov     r12, [rsp+328h+arg_10]
0x1800092b7  mov     esi, [rsp+328h+var_2E8]
0x1800092bb  mov     r15, [rsp+328h+var_2D8]
0x1800092c0  mov     rdi, [rsp+328h+var_2E0]
0x1800092c5  mov     r13, [rsp+328h+var_2D0]
0x1800092ca  test    rdi, rdi
0x1800092cd  jz      short loc_1800092E7
0x1800092cf  mov     rcx, [rdi]; this
0x1800092d2  call    ?Release@PLogFileNotify@@QEAAKXZ; PLogFileNotify::Release(void)
0x1800092d7  mov     rcx, rdi; Block
0x1800092da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800092df  mov     rdi, rbx
0x1800092e2  mov     [rsp+328h+var_2E0], rbx
0x1800092e7  mov     r8d, 33h ; '3'; cchBufferLength
0x1800092ed  lea     rdx, [rsp+328h+szVolumeName]; lpszVolumeName
0x1800092f2  mov     rcx, r15; hFindVolume
0x1800092f5  call    cs:__imp_FindNextVolumeW
0x1800092fb  test    eax, eax
0x1800092fd  jnz     short loc_18000930F
0x1800092ff  call    cs:__imp_GetLastError
0x180009305  cmp     eax, 12h
0x180009308  jz      short loc_18000931A
0x18000930a  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x18000930f  jmp     loc_180009140
0x180009314  call    __report_rangecheckfailure
0x18000931a  mov     rcx, r15; hFindVolume
0x18000931d  call    cs:__imp_FindVolumeClose
0x180009323  test    rdi, rdi
0x180009326  jz      short loc_180009330
0x180009328  mov     rcx, rdi; Block
0x18000932b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009330  mov     rcx, [rsp+328h+var_38]
0x180009338  xor     rcx, rsp; StackCookie
0x18000933b  call    __security_check_cookie
0x180009340  lea     r11, [rsp+328h+var_28]
0x180009348  mov     rbx, [r11+38h]
0x18000934c  mov     rsi, [r11+48h]
0x180009350  mov     rsp, r11
0x180009353  pop     r15
0x180009355  pop     r14
0x180009357  pop     r13
0x180009359  pop     r12
0x18000935b  pop     rdi
0x18000935c  retn
0x1800115db  push    rbp
0x1800115dd  sub     rsp, 40h
0x1800115e1  mov     rbp, rdx
0x1800115e4  mov     eax, 1
0x1800115e9  add     rsp, 40h
0x1800115ed  pop     rbp
0x1800115ee  retn
0x1800115f0  push    rbp
0x1800115f2  sub     rsp, 40h
0x1800115f6  mov     rbp, rdx
0x1800115f9  mov     rcx, [rbp+50h]; hFindVolume
0x1800115fd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011601  jz      short loc_18001160A
0x180011603  call    cs:__imp_FindVolumeClose
0x180011609  nop
0x18001160a  mov     rcx, [rbp+48h]; Block
0x18001160e  test    rcx, rcx
0x180011611  jz      short loc_180011619
0x180011613  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011618  nop
0x180011619  add     rsp, 40h
0x18001161d  pop     rbp
0x18001161e  retn
```
