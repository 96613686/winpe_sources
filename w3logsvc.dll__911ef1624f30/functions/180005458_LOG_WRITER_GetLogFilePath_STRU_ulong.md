# LOG_WRITER::GetLogFilePath(STRU *,ulong)

- ea: `0x180005458`
- end: `0x18000579a`
- name: `?GetLogFilePath@LOG_WRITER@@AEAAJPEAVSTRU@@K@Z`
- size: `834`
- prototype: `__int64 __fastcall(PCWSTR *this, struct STRU *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004fe4`

## callees

- `0x180002808`
- `0x180002b14`
- `0x180004878`
- `0x180004dbc`
- `0x180005458`
- `0x180005960`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180005552`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180005552`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180005546`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180005546`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800054df`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800054df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005778`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005778`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180005754`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180005754`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180005619`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180005619`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005767`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005767`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000556c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005586`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000563d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005652`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800056d8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005736`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000556c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005586`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000563d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005652`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800056d8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005736`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180005631`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180005631`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::GetLogFilePath(PCWSTR *this, struct STRU *a2, unsigned int a3)
{
  _WORD *v4; // rcx
  HRESULT LowestDirectory; // ebx
  PCWSTR v8; // rax
  HRESULT IncrementalFilePath; // eax
  LOG_WRITER *v10; // rcx
  int v11; // eax
  const unsigned __int16 *v12; // r9
  unsigned int v13; // r8d
  unsigned int v14; // r14d
  LOG_WRITER *v15; // rcx
  int appended; // eax
  const unsigned __int16 *lpTimeStr; // [rsp+20h] [rbp-59h]
  int cchTime; // [rsp+28h] [rbp-51h]
  PWSTR ppszPathOut; // [rsp+40h] [rbp-39h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-31h] BYREF
  __int128 FileInformation; // [rsp+58h] [rbp-21h] BYREF
  __int128 v23; // [rsp+68h] [rbp-11h]
  unsigned int v24; // [rsp+78h] [rbp-1h]
  unsigned __int16 v25[4]; // [rsp+80h] [rbp+7h] BYREF
  __int16 v26; // [rsp+88h] [rbp+Fh]
  WCHAR TimeStr[8]; // [rsp+90h] [rbp+17h] BYREF
  __int16 v28; // [rsp+A0h] [rbp+27h]

  ppszPathOut = 0;
  v24 = 0;
  v4 = (_WORD *)*((_QWORD *)a2 + 4);
  FileInformation = 0;
  v23 = 0;
  *v4 = 0;
  *((_DWORD *)a2 + 12) = 0;
  LowestDirectory = LOG_WRITER::ExpandDirPathAndCreateLowestDirectory((LOG_WRITER *)this);
  if ( LowestDirectory < 0 )
    goto LABEL_41;
  v8 = this[1];
  if ( !*((_DWORD *)v8 + 6) )
  {
    LowestDirectory = LOG_WRITER::GetIncrementalFilePath((LOG_WRITER *)this, a2);
    if ( LowestDirectory >= 0 )
    {
      if ( GetFileAttributesExW(*((LPCWSTR *)a2 + 4), GetFileExInfoStandard, &FileInformation) )
      {
        *(_QWORD *)v25 = __PAIR64__(HIDWORD(v23), v24);
        if ( (unsigned int)LOG_WRITER::NeedToRolloverToNewLogFile((LOG_WRITER *)this, __PAIR64__(HIDWORD(v23), v24), a3) )
        {
          ++*((_DWORD *)this + 156);
          IncrementalFilePath = LOG_WRITER::GetIncrementalFilePath((LOG_WRITER *)this, a2);
LABEL_40:
          LowestDirectory = IncrementalFilePath;
          goto LABEL_41;
        }
      }
    }
    goto LABEL_41;
  }
  *(_QWORD *)v25 = 0;
  v26 = 0;
  SystemTime = 0;
  if ( v8 && *((_DWORD *)v8 + 1) == 1 )
    GetLocalTime(&SystemTime);
  else
    GetSystemTime(&SystemTime);
  if ( *((_DWORD *)this[1] + 3) )
  {
    LowestDirectory = STRU::Append(a2, L"u_");
    if ( LowestDirectory < 0 )
      goto LABEL_41;
  }
  LowestDirectory = STRU::Append(a2, L"ex");
  if ( LowestDirectory < 0 )
    goto LABEL_41;
  v10 = (LOG_WRITER *)this[1];
  switch ( *((_DWORD *)v10 + 6) )
  {
    case 1:
      v12 = L"yyMMdd";
      break;
    case 2:
      v13 = SystemTime.wDay - SystemTime.wDayOfWeek;
      if ( SystemTime.wDay == SystemTime.wDayOfWeek )
      {
        v14 = 1;
      }
      else
      {
        v10 = (LOG_WRITER *)(v13 / 7);
        v14 = (_DWORD)v10 + 1;
        if ( v13 != 7 * (_DWORD)v10 )
          v14 = (_DWORD)v10 + 2;
      }
      LowestDirectory = LOG_WRITER::AppendFormattedDate(v10, a2, &SystemTime, L"yyMM", lpTimeStr, cchTime);
      if ( LowestDirectory < 0 )
        goto LABEL_41;
      LowestDirectory = STRU::Append(a2, L"0");
      if ( LowestDirectory < 0 )
        goto LABEL_41;
      appended = LOG_WRITER::AppendNum(v15, a2, v14, v25, 5u, 0, 0);
      goto LABEL_36;
    case 3:
      v12 = L"yyMM";
      break;
    case 4:
      LowestDirectory = LOG_WRITER::AppendFormattedDate(v10, a2, &SystemTime, L"yyMMdd", lpTimeStr, cchTime);
      if ( LowestDirectory < 0 )
        goto LABEL_41;
      v28 = 0;
      *(_OWORD *)TimeStr = 0;
      if ( GetTimeFormatEx(&LocaleName, 4u, &SystemTime, L"HH", TimeStr, 9) )
      {
        LowestDirectory = STRU::Append(a2, TimeStr);
        if ( LowestDirectory < 0 )
          goto LABEL_41;
        v11 = STRU::Append(a2, 0);
      }
      else
      {
        v11 = STRU::Append(a2, L"- ", 2u);
      }
      LowestDirectory = v11;
      if ( v11 < 0 )
        goto LABEL_41;
      goto LABEL_37;
    default:
      LowestDirectory = -2147024809;
      goto LABEL_41;
  }
  appended = LOG_WRITER::AppendFormattedDate(v10, a2, &SystemTime, v12, lpTimeStr, cchTime);
LABEL_36:
  LowestDirectory = appended;
  if ( appended < 0 )
    goto LABEL_41;
LABEL_37:
  LowestDirectory = STRU::Append(a2, L"_x.log");
  if ( LowestDirectory >= 0 )
  {
    LowestDirectory = PathAllocCombine(this[13], *((PCWSTR *)a2 + 4), 1u, &ppszPathOut);
    if ( LowestDirectory >= 0 )
    {
      IncrementalFilePath = STRU::Copy(a2, ppszPathOut);
      goto LABEL_40;
    }
  }
LABEL_41:
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  return (unsigned int)LowestDirectory;
}

```

## disassembly

```asm
0x180005458  push    rbp
0x18000545a  push    rbx
0x18000545b  push    rsi
0x18000545c  push    rdi
0x18000545d  push    r14
0x18000545f  lea     rbp, [rsp-37h]
0x180005464  sub     rsp, 0B0h
0x18000546b  mov     rax, cs:__security_cookie
0x180005472  xor     rax, rsp
0x180005475  mov     [rbp+57h+var_28], rax
0x180005479  xor     eax, eax
0x18000547b  mov     [rbp+57h+ppszPathOut], 0
0x180005483  mov     rsi, rcx
0x180005486  mov     [rbp+57h+var_58], eax
0x180005489  mov     rcx, [rdx+20h]
0x18000548d  xorps   xmm0, xmm0
0x180005490  movups  [rbp+57h+FileInformation], xmm0
0x180005494  mov     r14d, r8d
0x180005497  mov     rdi, rdx
0x18000549a  movups  [rbp+57h+var_68], xmm0
0x18000549e  mov     [rcx], ax
0x1800054a1  mov     rcx, rsi; this
0x1800054a4  mov     [rdx+30h], eax
0x1800054a7  call    ?ExpandDirPathAndCreateLowestDirectory@LOG_WRITER@@AEAAJXZ; LOG_WRITER::ExpandDirPathAndCreateLowestDirectory(void)
0x1800054ac  mov     ebx, eax
0x1800054ae  test    eax, eax
0x1800054b0  js      loc_18000576F
0x1800054b6  mov     rax, [rsi+8]
0x1800054ba  cmp     dword ptr [rax+18h], 0
0x1800054be  jnz     short loc_180005526
0x1800054c0  mov     rdx, rdi; struct STRU *
0x1800054c3  mov     rcx, rsi; this
0x1800054c6  call    ?GetIncrementalFilePath@LOG_WRITER@@AEAAJPEAVSTRU@@@Z; LOG_WRITER::GetIncrementalFilePath(STRU *)
0x1800054cb  mov     ebx, eax
0x1800054cd  test    eax, eax
0x1800054cf  js      loc_18000576F
0x1800054d5  mov     rcx, [rdi+20h]; lpFileName
0x1800054d9  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x1800054dd  xor     edx, edx; fInfoLevelId
0x1800054df  call    cs:__imp_GetFileAttributesExW
0x1800054e5  test    eax, eax
0x1800054e7  jz      loc_18000576F
0x1800054ed  mov     eax, dword ptr [rbp+57h+var_68+0Ch]
0x1800054f0  mov     r8d, r14d; unsigned int
0x1800054f3  mov     dword ptr [rbp+57h+var_50+4], eax
0x1800054f6  mov     rcx, rsi; this
0x1800054f9  mov     eax, [rbp+57h+var_58]
0x1800054fc  mov     dword ptr [rbp+57h+var_50], eax
0x1800054ff  mov     rdx, qword ptr [rbp+57h+var_50]; unsigned __int64
0x180005503  call    ?NeedToRolloverToNewLogFile@LOG_WRITER@@AEAAH_KK@Z; LOG_WRITER::NeedToRolloverToNewLogFile(unsigned __int64,ulong)
0x180005508  test    eax, eax
0x18000550a  jz      loc_18000576F
0x180005510  inc     dword ptr [rsi+270h]
0x180005516  mov     rdx, rdi; struct STRU *
0x180005519  mov     rcx, rsi; this
0x18000551c  call    ?GetIncrementalFilePath@LOG_WRITER@@AEAAJPEAVSTRU@@@Z; LOG_WRITER::GetIncrementalFilePath(STRU *)
0x180005521  jmp     loc_18000576D
0x180005526  xor     ecx, ecx
0x180005528  xorps   xmm0, xmm0
0x18000552b  mov     qword ptr [rbp+57h+var_50], rcx
0x18000552f  mov     [rbp+57h+var_48], cx
0x180005533  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180005537  test    rax, rax
0x18000553a  jz      short loc_18000554E
0x18000553c  cmp     dword ptr [rax+4], 1
0x180005540  jnz     short loc_18000554E
0x180005542  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180005546  call    cs:__imp_GetLocalTime
0x18000554c  jmp     short loc_180005558
0x18000554e  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180005552  call    cs:__imp_GetSystemTime
0x180005558  mov     rax, [rsi+8]
0x18000555c  cmp     dword ptr [rax+0Ch], 0
0x180005560  jz      short loc_18000557C
0x180005562  lea     rdx, aU; "u_"
0x180005569  mov     rcx, rdi
0x18000556c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005572  mov     ebx, eax
0x180005574  test    eax, eax
0x180005576  js      loc_18000576F
0x18000557c  lea     rdx, aEx; "ex"
0x180005583  mov     rcx, rdi
0x180005586  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000558c  mov     ebx, eax
0x18000558e  test    eax, eax
0x180005590  js      loc_18000576F
0x180005596  mov     rcx, [rsi+8]; this
0x18000559a  mov     edx, [rcx+18h]
0x18000559d  sub     edx, 1
0x1800055a0  jz      loc_180005713
0x1800055a6  sub     edx, 1
0x1800055a9  jz      loc_180005673
0x1800055af  sub     edx, 1
0x1800055b2  jz      loc_180005667
0x1800055b8  cmp     edx, 1
0x1800055bb  jz      short loc_1800055C7
0x1800055bd  mov     ebx, 80070057h
0x1800055c2  jmp     loc_18000576F
0x1800055c7  lea     r9, aYymmdd; "yyMMdd"
0x1800055ce  mov     rdx, rdi; struct STRU *
0x1800055d1  lea     r8, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x1800055d5  call    ?AppendFormattedDate@LOG_WRITER@@AEAAJPEAVSTRU@@PEAU_SYSTEMTIME@@PEBG2H@Z; LOG_WRITER::AppendFormattedDate(STRU *,_SYSTEMTIME *,ushort const *,ushort const *,int)
0x1800055da  mov     ebx, eax
0x1800055dc  test    eax, eax
0x1800055de  js      loc_18000576F
0x1800055e4  xor     eax, eax
0x1800055e6  mov     [rsp+0D0h+cchTime], 9; cchTime
0x1800055ee  mov     [rbp+57h+var_30], ax
0x1800055f2  lea     r9, Format; "HH"
0x1800055f9  lea     rax, [rbp+57h+TimeStr]
0x1800055fd  xorps   xmm0, xmm0
0x180005600  lea     r8, [rbp+57h+SystemTime]; lpTime
0x180005604  mov     [rsp+0D0h+lpTimeStr], rax; lpTimeStr
0x180005609  mov     edx, 4; dwFlags
0x18000560e  lea     rcx, LocaleName; lpLocaleName
0x180005615  movups  xmmword ptr [rbp+57h+TimeStr], xmm0
0x180005619  call    cs:__imp_GetTimeFormatEx
0x18000561f  mov     rcx, rdi
0x180005622  test    eax, eax
0x180005624  jnz     short loc_180005639
0x180005626  lea     r8d, [rax+2]
0x18000562a  lea     rdx, asc_180012130; "- "
0x180005631  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180005637  jmp     short loc_180005658
0x180005639  lea     rdx, [rbp+57h+TimeStr]
0x18000563d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005643  mov     ebx, eax
0x180005645  test    eax, eax
0x180005647  js      loc_18000576F
0x18000564d  xor     edx, edx
0x18000564f  mov     rcx, rdi
0x180005652  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005658  mov     ebx, eax
0x18000565a  test    eax, eax
0x18000565c  jns     loc_18000572C
0x180005662  jmp     loc_18000576F
0x180005667  lea     r9, aYymm; "yyMM"
0x18000566e  jmp     loc_18000571A
0x180005673  movzx   eax, [rbp+57h+SystemTime.wDayOfWeek]
0x180005677  movzx   r8d, [rbp+57h+SystemTime.wDay]
0x18000567c  sub     r8d, eax
0x18000567f  cmp     r8d, 1
0x180005683  jnb     short loc_18000568D
0x180005685  mov     r14d, 1
0x18000568b  jmp     short loc_1800056B1
0x18000568d  mov     eax, 24924925h
0x180005692  mov     ecx, r8d
0x180005695  mul     r8d
0x180005698  sub     ecx, edx
0x18000569a  shr     ecx, 1
0x18000569c  add     ecx, edx
0x18000569e  shr     ecx, 2; this
0x1800056a1  imul    eax, ecx, 7
0x1800056a4  lea     r14d, [rcx+1]
0x1800056a8  cmp     r8d, eax
0x1800056ab  jz      short loc_1800056B1
0x1800056ad  lea     r14d, [rcx+2]
0x1800056b1  lea     r9, aYymm; "yyMM"
0x1800056b8  mov     rdx, rdi; struct STRU *
0x1800056bb  lea     r8, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x1800056bf  call    ?AppendFormattedDate@LOG_WRITER@@AEAAJPEAVSTRU@@PEAU_SYSTEMTIME@@PEBG2H@Z; LOG_WRITER::AppendFormattedDate(STRU *,_SYSTEMTIME *,ushort const *,ushort const *,int)
0x1800056c4  mov     ebx, eax
0x1800056c6  test    eax, eax
0x1800056c8  js      loc_18000576F
0x1800056ce  lea     rdx, a0; "0"
0x1800056d5  mov     rcx, rdi
0x1800056d8  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800056de  mov     ebx, eax
0x1800056e0  test    eax, eax
0x1800056e2  js      loc_18000576F
0x1800056e8  mov     [rsp+0D0h+var_A0], 0; int
0x1800056f0  lea     r9, [rbp+57h+var_50]; unsigned __int16 *
0x1800056f4  mov     qword ptr [rsp+0D0h+cchTime], 0; unsigned __int16 *
0x1800056fd  mov     rdx, rdi; struct STRU *
0x180005700  mov     r8d, r14d; unsigned __int64
0x180005703  mov     [rsp+0D0h+lpTimeStr], 5; unsigned __int64
0x18000570c  call    ?AppendNum@LOG_WRITER@@AEAAJPEAVSTRU@@_KPEAG1PEBGH@Z; LOG_WRITER::AppendNum(STRU *,unsigned __int64,ushort *,unsigned __int64,ushort const *,int)
0x180005711  jmp     short loc_180005726
0x180005713  lea     r9, aYymmdd; "yyMMdd"
0x18000571a  lea     r8, [rbp+57h+SystemTime]; struct _SYSTEMTIME *
0x18000571e  mov     rdx, rdi; struct STRU *
0x180005721  call    ?AppendFormattedDate@LOG_WRITER@@AEAAJPEAVSTRU@@PEAU_SYSTEMTIME@@PEBG2H@Z; LOG_WRITER::AppendFormattedDate(STRU *,_SYSTEMTIME *,ushort const *,ushort const *,int)
0x180005726  mov     ebx, eax
0x180005728  test    eax, eax
0x18000572a  js      short loc_18000576F
0x18000572c  lea     rdx, aXLog; "_x.log"
0x180005733  mov     rcx, rdi
0x180005736  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000573c  mov     ebx, eax
0x18000573e  test    eax, eax
0x180005740  js      short loc_18000576F
0x180005742  mov     rdx, [rdi+20h]; pszMore
0x180005746  lea     r9, [rbp+57h+ppszPathOut]; ppszPathOut
0x18000574a  mov     rcx, [rsi+68h]; pszPathIn
0x18000574e  mov     r8d, 1; dwFlags
0x180005754  call    cs:__imp_PathAllocCombine
0x18000575a  mov     ebx, eax
0x18000575c  test    eax, eax
0x18000575e  js      short loc_18000576F
0x180005760  mov     rdx, [rbp+57h+ppszPathOut]
0x180005764  mov     rcx, rdi
0x180005767  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000576d  mov     ebx, eax
0x18000576f  mov     rcx, [rbp+57h+ppszPathOut]; hMem
0x180005773  test    rcx, rcx
0x180005776  jz      short loc_18000577E
0x180005778  call    cs:__imp_LocalFree
0x18000577e  mov     eax, ebx
0x180005780  mov     rcx, [rbp+57h+var_28]
0x180005784  xor     rcx, rsp; StackCookie
0x180005787  call    __security_check_cookie
0x18000578c  add     rsp, 0B0h
0x180005793  pop     r14
0x180005795  pop     rdi
0x180005796  pop     rsi
0x180005797  pop     rbx
0x180005798  pop     rbp
0x180005799  retn
```
