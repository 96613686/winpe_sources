# GetVolumeNameAndRelativeFilePath(ushort const *,ushort * *,ushort * *)

- ea: `0x140059484`
- end: `0x14005996d`
- name: `?GetVolumeNameAndRelativeFilePath@@YAHPEBGPEAPEAG1@Z`
- size: `1257`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x14005a294`

## callees

- `0x140021ca0`
- `0x1400227a0`
- `0x1400235a8`
- `0x140025abc`
- `0x14003ade4`
- `0x140059484`
- `0x14005a8ec`
- `0x14005b208`
- `0x140091560`
- `0x1400916f0`
- `0x1400921dc`
- `0x1400d257c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400595ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400595ca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005993a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005993a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400596d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400597dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400596d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400597dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140059805`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400596cb`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x1400596cb`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400597d0`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400597d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005990c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140059914`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005991d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140059926`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005990c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140059914`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005991d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140059926`

## string_xrefs

- `0x1400594b6`: `GetVolumeNameAndRelativeFilePath`
- `0x14005992c`: `GetVolumeNameAndRelativeFilePath`
- `0x1400596b6`: `wszVolumePathBuffer`
- `0x1400595a7`: `pwszRelativeFilePath`
- `0x140059810`: `GetVolumeNameForVolumeMountPoint(wszVolumePathBuffer, wszVolumeNameBuffer, ARRAYSIZE(wszVolumeNameBuffer))`
- `0x14005970b`: `GetVolumePathNameW( wszSSQMSPrependedFileName, wszVolumePathBuffer, cchPathLength)`
- `0x140059792`: `::StringCchCat( wszVolumePathBuffer, cchPathLength, L"\\" )`
- `0x1400598ec`: `wszRelativeFilePath`

## pseudocode

```c
__int64 __fastcall GetVolumeNameAndRelativeFilePath(
        const unsigned __int16 *a1,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // r12
  WCHAR *v8; // r14
  int v9; // r9d
  unsigned int v10; // ebx
  DWORD LastError; // edi
  struct _DRIVE_LAYOUT_INFORMATION_EX *v12; // rcx
  int v13; // edx
  const char *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  DWORD v17; // edi
  WCHAR *v18; // rax
  DWORD v19; // eax
  int v20; // edx
  const char *v21; // rcx
  __int64 v22; // rax
  DWORD v23; // ebp
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  unsigned __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned __int16 *v29; // rax
  __int16 v31; // [rsp+2Eh] [rbp-25Ah]
  WCHAR szVolumeName; // [rsp+30h] [rbp-258h] BYREF
  _BYTE v33[526]; // [rsp+32h] [rbp-256h] BYREF

  TraceFunctionEnter(L"GetVolumeNameAndRelativeFilePath");
  szVolumeName = 0;
  v6 = 0;
  memset_0(v33, 0, 0x206u);
  v7 = 0;
  v8 = 0;
  if ( !a2 )
  {
    v9 = 87;
    v10 = 0;
    LastError = 87;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v13 = 28;
      v14 = "pwszVolumeName";
LABEL_5:
      WPP_SF_Ds(
        *(_QWORD *)v12->Gpt.DiskId.Data4,
        v13,
        (unsigned int)WPP_214f6c84b4d4323947ecaa518c1defb8_Traceguids,
        v9,
        v14);
      goto LABEL_66;
    }
    goto LABEL_66;
  }
  if ( !a1 )
  {
    v9 = 87;
    v10 = 0;
    LastError = 87;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v13 = 29;
      v14 = "wszFileName";
      goto LABEL_5;
    }
    goto LABEL_66;
  }
  if ( !a3 )
  {
    v9 = 87;
    v10 = 0;
    LastError = 87;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
    {
      v13 = 30;
      v14 = "pwszRelativeFilePath";
      goto LABEL_5;
    }
    goto LABEL_66;
  }
  *a2 = 0;
  *a3 = 0;
  if ( (unsigned int)_o__wcsnicmp(a1, L"\\\\?\\", 4) )
  {
    v8 = SafeStrJoin(L"\\\\?\\", a1);
    if ( !v8 )
    {
      v9 = 14;
      v10 = 0;
      LastError = 14;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
      {
        goto LABEL_66;
      }
      v13 = 31;
      goto LABEL_19;
    }
  }
  else
  {
    v8 = SafeStrClone(a1);
    if ( !v8 )
    {
      v9 = 14;
      v10 = 0;
      LastError = 14;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
      {
        goto LABEL_66;
      }
      v13 = 32;
LABEL_19:
      v14 = "wszSSQMSPrependedFileName";
      goto LABEL_5;
    }
  }
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( v8[v16] );
  v17 = v16 + 2;
  v18 = (WCHAR *)ASR_ALLOC((unsigned int)(2 * (v16 + 2)));
  v6 = v18;
  if ( v18 )
  {
    if ( GetVolumePathNameW(v8, v18, v17) )
    {
      v22 = -1;
      do
        ++v22;
      while ( v6[v22] );
      if ( v6[v22 - 1] != 92 )
      {
        v23 = v17;
        v24 = StringCchCatW(v6, v17, L"\\");
        if ( v24 < 0 )
        {
          v10 = 0;
          LastError = WIN32_FROM_HRESULT((unsigned int)v24);
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v25 = StringCchCatW(v6, v23, L"\\");
            WPP_SF_Ds(
              *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
              35,
              (unsigned int)WPP_214f6c84b4d4323947ecaa518c1defb8_Traceguids,
              v25,
              "::StringCchCat( wszVolumePathBuffer, cchPathLength, L\"\\\\\" )");
          }
          goto LABEL_66;
        }
      }
      if ( GetVolumeNameForVolumeMountPointW(v6, &szVolumeName, 0x104u) )
      {
        v26 = -1;
        do
          ++v26;
        while ( *(_WORD *)&v33[2 * v26 - 2] );
        if ( *(&v31 + v26) == 92 )
        {
          v27 = 2 * v26 - 2;
          if ( v27 >= 0x208 )
            _report_rangecheckfailure();
          *(_WORD *)&v33[v27 - 2] = 0;
        }
        v28 = -1;
        do
          ++v28;
        while ( v6[v28] );
        if ( v6[v28 - 1] == 92 )
          v6[v28 - 1] = 0;
        v7 = SafeStrClone(&szVolumeName);
        if ( v7 )
        {
          do
            ++v15;
          while ( v6[v15] );
          v29 = SafeStrClone(&v8[v15]);
          if ( v29 )
          {
            *a3 = v29;
            LastError = 0;
            *a2 = v7;
            v10 = 1;
            v7 = 0;
            goto LABEL_66;
          }
          v9 = 14;
          v10 = 0;
          LastError = 14;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v13 = 38;
            v14 = "wszRelativeFilePath";
            goto LABEL_5;
          }
        }
        else
        {
          v9 = 14;
          v10 = 0;
          LastError = 14;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
          {
            v13 = 37;
            v14 = "wszVolumeName";
            goto LABEL_5;
          }
        }
        goto LABEL_66;
      }
      v10 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
      {
        goto LABEL_66;
      }
      v19 = GetLastError();
      v20 = 36;
      v21 = "GetVolumeNameForVolumeMountPoint(wszVolumePathBuffer, wszVolumeNameBuffer, ARRAYSIZE(wszVolumeNameBuffer))";
    }
    else
    {
      v10 = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) == 0 )
      {
        goto LABEL_66;
      }
      v19 = GetLastError();
      v20 = 34;
      v21 = "GetVolumePathNameW( wszSSQMSPrependedFileName, wszVolumePathBuffer, cchPathLength)";
    }
    WPP_SF_Ds(
      *(_QWORD *)WPP_GLOBAL_Control->Gpt.DiskId.Data4,
      v20,
      (unsigned int)WPP_214f6c84b4d4323947ecaa518c1defb8_Traceguids,
      v19,
      v21);
    goto LABEL_66;
  }
  v9 = 14;
  v10 = 0;
  LastError = 14;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _DRIVE_LAYOUT_INFORMATION_EX *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->Gpt.StartingUsableOffset.QuadPart & 0x800000000LL) != 0 )
  {
    v13 = 33;
    v14 = "wszVolumePathBuffer";
    goto LABEL_5;
  }
LABEL_66:
  CoTaskMemFree(v7);
  CoTaskMemFree(0);
  CoTaskMemFree(v6);
  CoTaskMemFree(v8);
  TraceFunctionExit(L"GetVolumeNameAndRelativeFilePath");
  SetLastError(LastError);
  return v10;
}

```

## disassembly

```asm
0x140059484  mov     [rsp+arg_18], rbx
0x140059489  push    rbp
0x14005948a  push    rsi
0x14005948b  push    rdi
0x14005948c  push    r12
0x14005948e  push    r13
0x140059490  push    r14
0x140059492  push    r15
0x140059494  sub     rsp, 250h
0x14005949b  mov     rax, cs:__security_cookie
0x1400594a2  xor     rax, rsp
0x1400594a5  mov     [rsp+288h+var_48], rax
0x1400594ad  mov     r15, r8
0x1400594b0  mov     r13, rdx
0x1400594b3  mov     rbx, rcx
0x1400594b6  lea     rcx, aGetvolumenamea; "GetVolumeNameAndRelativeFilePath"
0x1400594bd  call    ?TraceFunctionEnter@@YAXPEAG@Z; TraceFunctionEnter(ushort *)
0x1400594c2  xor     ebp, ebp
0x1400594c4  lea     rcx, [rsp+288h+var_256]; void *
0x1400594c9  xor     edx, edx; Val
0x1400594cb  mov     [rsp+288h+szVolumeName], bp
0x1400594d0  mov     r8d, 206h; Size
0x1400594d6  mov     esi, ebp
0x1400594d8  call    memset_0
0x1400594dd  mov     r12d, ebp
0x1400594e0  mov     r14d, ebp
0x1400594e3  test    r13, r13
0x1400594e6  jnz     short loc_140059536
0x1400594e8  lea     r9d, [rbp+57h]
0x1400594ec  mov     ebx, ebp
0x1400594ee  mov     edi, r9d
0x1400594f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400594f8  lea     rax, WPP_GLOBAL_Control
0x1400594ff  cmp     rcx, rax
0x140059502  jz      loc_140059909
0x140059508  test    byte ptr [rcx+1Ch], 8
0x14005950c  jz      loc_140059909
0x140059512  lea     edx, [rbp+1Ch]
0x140059515  lea     rax, aPwszvolumename; "pwszVolumeName"
0x14005951c  mov     [rsp+288h+var_268], rax
0x140059521  mov     rcx, [rcx+10h]
0x140059525  lea     r8, WPP_214f6c84b4d4323947ecaa518c1defb8_Traceguids
0x14005952c  call    WPP_SF_Ds
0x140059531  jmp     loc_140059909
0x140059536  test    rbx, rbx
0x140059539  jnz     short loc_140059574
0x14005953b  mov     r9d, 57h ; 'W'
0x140059541  mov     ebx, ebp
0x140059543  mov     edi, r9d
0x140059546  mov     rcx, cs:WPP_GLOBAL_Control
0x14005954d  lea     rax, WPP_GLOBAL_Control
0x140059554  cmp     rcx, rax
0x140059557  jz      loc_140059909
0x14005955d  test    byte ptr [rcx+1Ch], 8
0x140059561  jz      loc_140059909
0x140059567  lea     edx, [r9-3Ah]
0x14005956b  lea     rax, aWszfilename; "wszFileName"
0x140059572  jmp     short loc_14005951C
0x140059574  test    r15, r15
0x140059577  jnz     short loc_1400595B3
0x140059579  lea     r9d, [r15+57h]
0x14005957d  mov     ebx, ebp
0x14005957f  mov     edi, r9d
0x140059582  mov     rcx, cs:WPP_GLOBAL_Control
0x140059589  lea     rax, WPP_GLOBAL_Control
0x140059590  cmp     rcx, rax
0x140059593  jz      loc_140059909
0x140059599  test    byte ptr [rcx+1Ch], 8
0x14005959d  jz      loc_140059909
0x1400595a3  lea     edx, [r15+1Eh]
0x1400595a7  lea     rax, aPwszrelativefi; "pwszRelativeFilePath"
0x1400595ae  jmp     loc_14005951C
0x1400595b3  mov     [r13+0], rbp
0x1400595b7  lea     rdx, asc_140101648; "\\\\?\\"
0x1400595be  mov     r8d, 4
0x1400595c4  mov     [r15], rbp
0x1400595c7  mov     rcx, rbx
0x1400595ca  call    cs:__imp__o__wcsnicmp
0x1400595d0  test    eax, eax
0x1400595d2  jz      short loc_140059625
0x1400595d4  mov     rdx, rbx; unsigned __int16 *
0x1400595d7  lea     rcx, asc_140101648; "\\\\?\\"
0x1400595de  call    ?SafeStrJoin@@YAPEAGPEBG0@Z; SafeStrJoin(ushort const *,ushort const *)
0x1400595e3  mov     r14, rax
0x1400595e6  test    rax, rax
0x1400595e9  jnz     short loc_140059665
0x1400595eb  lea     r9d, [rax+0Eh]
0x1400595ef  mov     ebx, ebp
0x1400595f1  mov     edi, r9d
0x1400595f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400595fb  lea     rax, WPP_GLOBAL_Control
0x140059602  cmp     rcx, rax
0x140059605  jz      loc_140059909
0x14005960b  test    byte ptr [rcx+1Ch], 8
0x14005960f  jz      loc_140059909
0x140059615  lea     edx, [r14+1Fh]
0x140059619  lea     rax, aWszssqmsprepen; "wszSSQMSPrependedFileName"
0x140059620  jmp     loc_14005951C
0x140059625  mov     rcx, rbx; unsigned __int16 *
0x140059628  call    ?SafeStrClone@@YAPEAGPEBG@Z; SafeStrClone(ushort const *)
0x14005962d  mov     r14, rax
0x140059630  test    rax, rax
0x140059633  jnz     short loc_140059665
0x140059635  lea     r9d, [rax+0Eh]
0x140059639  mov     ebx, ebp
0x14005963b  mov     edi, r9d
0x14005963e  mov     rcx, cs:WPP_GLOBAL_Control
0x140059645  lea     rax, WPP_GLOBAL_Control
0x14005964c  cmp     rcx, rax
0x14005964f  jz      loc_140059909
0x140059655  test    byte ptr [rcx+1Ch], 8
0x140059659  jz      loc_140059909
0x14005965f  lea     edx, [r14+20h]
0x140059663  jmp     short loc_140059619
0x140059665  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140059669  mov     rax, rbx
0x14005966c  inc     rax
0x14005966f  cmp     [r14+rax*2], bp
0x140059674  jnz     short loc_14005966C
0x140059676  lea     edi, [rax+2]
0x140059679  lea     ecx, [rdi+rdi]; Size
0x14005967c  call    ?ASR_ALLOC@@YAPEAXK@Z; ASR_ALLOC(ulong)
0x140059681  mov     rsi, rax
0x140059684  test    rax, rax
0x140059687  jnz     short loc_1400596C2
0x140059689  lea     r9d, [rax+0Eh]
0x14005968d  mov     ebx, ebp
0x14005968f  mov     edi, r9d
0x140059692  mov     rcx, cs:WPP_GLOBAL_Control
0x140059699  lea     rax, WPP_GLOBAL_Control
0x1400596a0  cmp     rcx, rax
0x1400596a3  jz      loc_140059909
0x1400596a9  test    byte ptr [rcx+1Ch], 8
0x1400596ad  jz      loc_140059909
0x1400596b3  lea     edx, [rsi+21h]
0x1400596b6  lea     rax, aWszvolumepathb; "wszVolumePathBuffer"
0x1400596bd  jmp     loc_14005951C
0x1400596c2  mov     r8d, edi; cchBufferLength
0x1400596c5  mov     rdx, rsi; lpszVolumePathName
0x1400596c8  mov     rcx, r14; lpszFileName
0x1400596cb  call    cs:__imp_GetVolumePathNameW
0x1400596d1  test    eax, eax
0x1400596d3  jnz     short loc_140059726
0x1400596d5  mov     ebx, ebp
0x1400596d7  call    cs:__imp_GetLastError
0x1400596dd  mov     edi, eax
0x1400596df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400596e6  lea     rax, WPP_GLOBAL_Control
0x1400596ed  cmp     rcx, rax
0x1400596f0  jz      loc_140059909
0x1400596f6  test    byte ptr [rcx+1Ch], 8
0x1400596fa  jz      loc_140059909
0x140059700  call    cs:__imp_GetLastError
0x140059706  mov     edx, 22h ; '"'
0x14005970b  lea     rcx, aGetvolumepathn_3; "GetVolumePathNameW( wszSSQMSPrependedFi"...
0x140059712  mov     [rsp+288h+var_268], rcx
0x140059717  mov     r9d, eax
0x14005971a  mov     rcx, cs:WPP_GLOBAL_Control
0x140059721  jmp     loc_140059521
0x140059726  mov     rax, rbx
0x140059729  inc     rax
0x14005972c  cmp     [rsi+rax*2], bp
0x140059730  jnz     short loc_140059729
0x140059732  cmp     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x140059738  jz      loc_1400597C2
0x14005973e  lea     r8, pszSrc; "\\"
0x140059745  mov     edx, edi; unsigned __int64
0x140059747  mov     rcx, rsi; unsigned __int16 *
0x14005974a  mov     ebp, edi
0x14005974c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140059751  test    eax, eax
0x140059753  jns     short loc_1400597C0
0x140059755  xor     ebx, ebx
0x140059757  mov     ecx, eax
0x140059759  call    WIN32_FROM_HRESULT
0x14005975e  mov     edi, eax
0x140059760  mov     rcx, cs:WPP_GLOBAL_Control
0x140059767  lea     rax, WPP_GLOBAL_Control
0x14005976e  cmp     rcx, rax
0x140059771  jz      loc_140059909
0x140059777  test    byte ptr [rcx+1Ch], 8
0x14005977b  jz      loc_140059909
0x140059781  lea     r8, pszSrc; "\\"
0x140059788  mov     edx, ebp; unsigned __int64
0x14005978a  mov     rcx, rsi; unsigned __int16 *
0x14005978d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140059792  lea     rcx, aStringcchcatWs_0; "::StringCchCat( wszVolumePathBuffer, cc"...
0x140059799  mov     r9d, eax
0x14005979c  mov     [rsp+288h+var_268], rcx
0x1400597a1  lea     edx, [rbx+23h]
0x1400597a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400597ab  lea     r8, WPP_214f6c84b4d4323947ecaa518c1defb8_Traceguids
0x1400597b2  mov     rcx, [rcx+10h]
0x1400597b6  call    WPP_SF_Ds
0x1400597bb  jmp     loc_140059909
0x1400597c0  xor     ebp, ebp
0x1400597c2  mov     r8d, 104h; cchBufferLength
0x1400597c8  lea     rdx, [rsp+288h+szVolumeName]; lpszVolumeName
0x1400597cd  mov     rcx, rsi; lpszVolumeMountPoint
0x1400597d0  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1400597d6  test    eax, eax
0x1400597d8  jnz     short loc_14005981C
0x1400597da  mov     ebx, ebp
0x1400597dc  call    cs:__imp_GetLastError
0x1400597e2  mov     edi, eax
0x1400597e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400597eb  lea     rax, WPP_GLOBAL_Control
0x1400597f2  cmp     rcx, rax
0x1400597f5  jz      loc_140059909
0x1400597fb  test    byte ptr [rcx+1Ch], 8
0x1400597ff  jz      loc_140059909
0x140059805  call    cs:__imp_GetLastError
0x14005980b  mov     edx, 24h ; '$'
0x140059810  lea     rcx, aGetvolumenamef_6; "GetVolumeNameForVolumeMountPoint(wszVol"...
0x140059817  jmp     loc_140059712
0x14005981c  lea     rcx, [rsp+288h+szVolumeName]
0x140059821  mov     rax, rbx
0x140059824  inc     rax
0x140059827  cmp     [rcx+rax*2], bp
0x14005982b  jnz     short loc_140059824
0x14005982d  cmp     [rsp+rax*2+288h+var_25A], 5Ch ; '\'
0x140059833  jnz     short loc_14005984B
0x140059835  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x14005983d  cmp     rcx, 208h
0x140059844  jnb     short loc_1400598A9
0x140059846  mov     [rsp+rcx+288h+szVolumeName], bp
0x14005984b  mov     rcx, rbx
0x14005984e  inc     rcx
0x140059851  cmp     [rsi+rcx*2], bp
0x140059855  jnz     short loc_14005984E
0x140059857  cmp     word ptr [rsi+rcx*2-2], 5Ch ; '\'
0x14005985d  jnz     short loc_140059864
0x14005985f  mov     [rsi+rcx*2-2], bp
0x140059864  lea     rcx, [rsp+288h+szVolumeName]; unsigned __int16 *
0x140059869  call    ?SafeStrClone@@YAPEAGPEBG@Z; SafeStrClone(ushort const *)
0x14005986e  mov     r12, rax
0x140059871  test    rax, rax
0x140059874  jnz     short loc_1400598AF
0x140059876  lea     r9d, [rax+0Eh]
0x14005987a  mov     ebx, ebp
0x14005987c  mov     edi, r9d
0x14005987f  mov     rcx, cs:WPP_GLOBAL_Control
0x140059886  lea     rax, WPP_GLOBAL_Control
0x14005988d  cmp     rcx, rax
0x140059890  jz      short loc_140059909
0x140059892  test    byte ptr [rcx+1Ch], 8
0x140059896  jz      short loc_140059909
0x140059898  lea     edx, [r12+25h]
0x14005989d  lea     rax, aWszvolumename; "wszVolumeName"
0x1400598a4  jmp     loc_14005951C
0x1400598a9  call    __report_rangecheckfailure
0x1400598af  inc     rbx
0x1400598b2  cmp     [rsi+rbx*2], bp
0x1400598b6  jnz     short loc_1400598AF
0x1400598b8  lea     rcx, [r14+rbx*2]; unsigned __int16 *
0x1400598bc  call    ?SafeStrClone@@YAPEAGPEBG@Z; SafeStrClone(ushort const *)
0x1400598c1  test    rax, rax
0x1400598c4  jnz     short loc_1400598F8
0x1400598c6  lea     r9d, [rax+0Eh]
0x1400598ca  mov     ebx, ebp
0x1400598cc  mov     edi, r9d
0x1400598cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400598d6  lea     rax, WPP_GLOBAL_Control
0x1400598dd  cmp     rcx, rax
0x1400598e0  jz      short loc_140059909
0x1400598e2  test    byte ptr [rcx+1Ch], 8
0x1400598e6  jz      short loc_140059909
0x1400598e8  lea     edx, [r9+18h]
0x1400598ec  lea     rax, aWszrelativefil; "wszRelativeFilePath"
0x1400598f3  jmp     loc_14005951C
0x1400598f8  mov     [r15], rax
0x1400598fb  mov     edi, ebp
0x1400598fd  mov     [r13+0], r12
0x140059901  mov     ebx, 1
0x140059906  mov     r12, rbp
0x140059909  mov     rcx, r12; pv
0x14005990c  call    cs:__imp_CoTaskMemFree
0x140059912  xor     ecx, ecx; pv
0x140059914  call    cs:__imp_CoTaskMemFree
0x14005991a  mov     rcx, rsi; pv
0x14005991d  call    cs:__imp_CoTaskMemFree
0x140059923  mov     rcx, r14; pv
0x140059926  call    cs:__imp_CoTaskMemFree
0x14005992c  lea     rcx, aGetvolumenamea; "GetVolumeNameAndRelativeFilePath"
0x140059933  call    ?TraceFunctionExit@@YAXPEAG@Z; TraceFunctionExit(ushort *)
0x140059938  mov     ecx, edi; dwErrCode
0x14005993a  call    cs:__imp_SetLastError
0x140059940  mov     eax, ebx
0x140059942  mov     rcx, [rsp+288h+var_48]
0x14005994a  xor     rcx, rsp; StackCookie
0x14005994d  call    __security_check_cookie
0x140059952  mov     rbx, [rsp+288h+arg_18]
0x14005995a  add     rsp, 250h
0x140059961  pop     r15
0x140059963  pop     r14
0x140059965  pop     r13
0x140059967  pop     r12
0x140059969  pop     rdi
0x14005996a  pop     rsi
0x14005996b  pop     rbp
  ... truncated ...
```
