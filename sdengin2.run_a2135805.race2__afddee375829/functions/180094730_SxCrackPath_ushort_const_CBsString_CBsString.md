# SxCrackPath(ushort const *,CBsString *,CBsString *)

- ea: `0x180094730`
- end: `0x180094d42`
- name: `?SxCrackPath@@YAJPEBGPEAVCBsString@@1@Z`
- size: `1554`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, struct CBsString *this, struct CBsString *)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, installer_update`

## callers

- `0x18003a598`

## callees

- `0x1800083e4`
- `0x180014c30`
- `0x180014eac`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180094730`
- `0x180097b08`
- `0x18009dee8`
- `0x18009e24c`
- `0x18009e2e8`
- `0x18009e904`
- `0x18009ea0c`
- `0x18009ea6c`
- `0x18009eab0`
- `0x18009f560`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180094984`
- `KERNEL32!GetLastError` at `0x180094984`
- `KERNEL32!GetVolumePathNameW` at `0x180094968`
- `KERNEL32!GetVolumePathNameW` at `0x180094968`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180094ad5`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180094b79`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180094ad5`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180094b79`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180094856`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800948ab`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180094856`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800948ab`

## string_xrefs

- `0x18009478f`: `SxCrackPath`
- `0x180094cbc`: `dwPathLength != 0`
- `0x180094b19`: `::GetVolumeNameForVolumeMountPointW( strMountPoint, strTwice.GetBuffer(), strTwice.GetAllocLength() + 1 )`
- `0x180094bbd`: `::GetVolumeNameForVolumeMountPointW( strTwice, strVolume.GetBuffer(), strVolume.GetAllocLength() + 1 )`

## pseudocode

```c
__int64 __fastcall SxCrackPath(LPCWSTR lpSrc, struct CBsString *this, struct CBsString *a3)
{
  __int16 v6; // ax
  const WCHAR *v7; // rsi
  __int64 v8; // rcx
  DWORD FullPathNameW; // edi
  __int16 v10; // bx
  unsigned int v11; // ebx
  __int64 v12; // rcx
  const WCHAR *v13; // rsi
  __int64 v14; // rcx
  unsigned int v15; // edi
  LPWSTR v16; // rbx
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // rcx
  int v21; // eax
  int LastFailureAsHRESULT; // eax
  _QWORD *v23; // rcx
  int v24; // edx
  unsigned int v25; // ebx
  int v27; // [rsp+30h] [rbp-89h] BYREF
  __int16 v28; // [rsp+34h] [rbp-85h]
  __int16 v29; // [rsp+36h] [rbp-83h]
  LPWSTR lpszVolumePathName; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v31[2]; // [rsp+70h] [rbp-49h]
  LPWSTR lpBuffer; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v33[2]; // [rsp+80h] [rbp-39h]
  LPWSTR v34; // [rsp+88h] [rbp-31h] BYREF
  unsigned int v35[2]; // [rsp+90h] [rbp-29h]
  LPWSTR lpszVolumeName; // [rsp+98h] [rbp-21h] BYREF
  unsigned int v37[2]; // [rsp+A0h] [rbp-19h]
  _QWORD v38[2]; // [rsp+A8h] [rbp-11h] BYREF
  LPCWSTR lpFileName[11]; // [rsp+B8h] [rbp-1h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_Sqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, (_DWORD)a3, (_DWORD)lpSrc, (char)this, (char)a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "SxCrackPath", 0x559u, 1u);
  lpFileName[0] = (LPCWSTR)qword_1800EE510;
  lpBuffer = (LPWSTR)qword_1800EE510;
  lpszVolumePathName = (LPWSTR)qword_1800EE510;
  v38[0] = qword_1800EE510;
  lpszVolumeName = (LPWSTR)qword_1800EE510;
  v34 = (LPWSTR)qword_1800EE510;
  v6 = 1380;
  lpFileName[1] = 0;
  *(_QWORD *)v33 = 0;
  *(_QWORD *)v31 = 0;
  v38[1] = 0;
  *(_QWORD *)v37 = 0;
  *(_QWORD *)v35 = 0;
  if ( !lpSrc )
  {
    v27 = -2147024809;
    goto LABEL_62;
  }
  v27 = 0;
  v28 = 1380;
  v27 = CBsString::ExpandEnvironmentStringsW((CBsString *)lpFileName, lpSrc);
  v6 = 1382;
  if ( v27 < 0 )
  {
LABEL_62:
    v29 = v6;
    goto LABEL_63;
  }
  v28 = 1382;
  v7 = lpFileName[0];
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, lpFileName[0]);
  FullPathNameW = GetFullPathNameW(v7, 0, 0, 0);
  if ( FullPathNameW )
  {
    v27 = 0;
    v28 = 1390;
    v10 = 1393;
    do
    {
      v27 = CBsString::ExtendBuffer((CBsString *)&lpBuffer, FullPathNameW - 1);
      if ( v27 < 0 )
      {
LABEL_26:
        v29 = v10;
        goto LABEL_63;
      }
      v28 = 1393;
      v11 = v33[1];
      FullPathNameW = GetFullPathNameW(v7, v33[1] + 1, lpBuffer, 0);
      CBsString::BoundUpdateLength((CBsString *)&lpBuffer, v11);
      if ( !FullPathNameW )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
        v27 = LastFailureAsHRESULT;
        v29 = 1396;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          v24 = 39;
          goto LABEL_59;
        }
        goto LABEL_63;
      }
      v27 = 0;
      v28 = 1396;
      v10 = 1393;
    }
    while ( FullPathNameW > v33[1] );
    v27 = CBsString::SetLength((CBsString *)&lpBuffer, FullPathNameW);
    v6 = 1399;
    if ( v27 < 0 )
      goto LABEL_62;
    v28 = 1399;
    v13 = lpBuffer;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
        (_DWORD)lpBuffer,
        FullPathNameW);
    v27 = CBsString::ExtendBuffer((CBsString *)&lpszVolumePathName, FullPathNameW);
    v6 = 1408;
    if ( v27 < 0 )
      goto LABEL_62;
    while ( 1 )
    {
      v28 = v6;
      v10 = 1416;
      if ( GetVolumePathNameW(v13, lpszVolumePathName, FullPathNameW + 1) )
        break;
      CBsString::BoundUpdateLength((CBsString *)&lpszVolumePathName, v31[1]);
      if ( GetLastError() != 206 )
      {
        v27 = GetLastFailureAsHRESULT(v14);
        goto LABEL_26;
      }
      v28 = 1416;
      v6 = 1418;
      if ( 2 * FullPathNameW <= FullPathNameW )
      {
        v27 = -2147024362;
        goto LABEL_62;
      }
      v27 = 0;
      v28 = 1418;
      v27 = CBsString::ExtendBuffer((CBsString *)&lpszVolumePathName, 2 * FullPathNameW);
      v6 = 1419;
      if ( v27 < 0 )
        goto LABEL_62;
      FullPathNameW *= 2;
    }
    CBsString::BoundUpdateLength((CBsString *)&lpszVolumePathName, v31[1]);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
        lpszVolumePathName);
    v27 = CBsString::Set((CBsString *)v38, &v13[v31[0]]);
    v6 = 1430;
    if ( v27 < 0 )
      goto LABEL_62;
    v28 = 1430;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, v38[0]);
    v27 = CBsString::Trailing((CBsString *)&lpszVolumePathName, 0x5Cu);
    v6 = 1441;
    if ( v27 < 0 )
      goto LABEL_62;
    v28 = 1441;
    v27 = CBsString::ExtendBuffer((CBsString *)&lpszVolumeName, 0x104u);
    v6 = 1442;
    if ( v27 < 0 )
      goto LABEL_62;
    v15 = v37[1];
    v16 = lpszVolumePathName;
    v28 = 1442;
    if ( GetVolumeNameForVolumeMountPointW(lpszVolumePathName, lpszVolumeName, v37[1] + 1) )
    {
      v27 = 0;
      v28 = 1444;
      CBsString::BoundUpdateLength((CBsString *)&lpszVolumeName, v15);
      v27 = CBsString::ExtendBuffer((CBsString *)&v34, 0x104u);
      v6 = 1447;
      if ( v27 < 0 )
        goto LABEL_62;
      v19 = v35[1];
      v28 = 1447;
      if ( GetVolumeNameForVolumeMountPointW(lpszVolumeName, v34, v35[1] + 1) )
      {
        v27 = 0;
        v28 = 1449;
        CBsString::BoundUpdateLength((CBsString *)&v34, v19);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, v34);
        if ( this )
        {
          v27 = CBsString::Set(this, v34);
          v6 = 1459;
          if ( v27 < 0 )
            goto LABEL_62;
          v28 = 1459;
        }
        if ( a3 )
          CBsString::Transfer((CBsString *)v38, a3);
      }
      else
      {
        v21 = GetLastFailureAsHRESULT(v20);
        v27 = v21;
        v29 = 1449;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
            (unsigned int)"::GetVolumeNameForVolumeMountPointW( strTwice, strVolume.GetBuffer(), strVolume.GetAllocLength() + 1 )",
            (__int64)v16,
            v21);
      }
    }
    else
    {
      v18 = GetLastFailureAsHRESULT(v17);
      v27 = v18;
      v29 = 1444;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"::GetVolumeNameForVolumeMountPointW( strMountPoint, strTwice.GetBuffer(), strTwice.GetAllocLength() + 1 )",
          (__int64)v16,
          v18);
    }
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v27 = LastFailureAsHRESULT;
    v29 = 1390;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v24 = 38;
LABEL_59:
      WPP_SF_sSd(
        v23[2],
        v24,
        (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
        (unsigned int)"dwPathLength != 0",
        (__int64)v7,
        LastFailureAsHRESULT);
    }
  }
LABEL_63:
  v25 = v27;
  CBsString::_Release((CBsString *)&v34);
  CBsString::_Release((CBsString *)&lpszVolumeName);
  CBsString::_Release((CBsString *)v38);
  CBsString::_Release((CBsString *)&lpszVolumePathName);
  CBsString::_Release((CBsString *)&lpBuffer);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return v25;
}

```

## disassembly

```asm
0x180094730  push    rbp
0x180094732  push    rbx
0x180094733  push    rsi
0x180094734  push    rdi
0x180094735  push    r12
0x180094737  push    r13
0x180094739  push    r14
0x18009473b  push    r15
0x18009473d  lea     rbp, [rsp-1Fh]
0x180094742  sub     rsp, 0D8h
0x180094749  mov     r14, r8
0x18009474c  mov     r15, rdx
0x18009474f  mov     rbx, rcx
0x180094752  mov     rcx, cs:WPP_GLOBAL_Control
0x180094759  lea     r13, WPP_GLOBAL_Control
0x180094760  cmp     rcx, r13
0x180094763  jz      short loc_180094789
0x180094765  test    dword ptr [rcx+1Ch], 20000000h
0x18009476c  jz      short loc_180094789
0x18009476e  mov     rcx, [rcx+10h]
0x180094772  mov     edx, 24h ; '$'
0x180094777  mov     [rsp+110h+var_E8], r8
0x18009477c  mov     r9, rbx
0x18009477f  mov     [rsp+110h+var_F0], r15
0x180094784  call    WPP_SF_Sqq
0x180094789  mov     r9d, 1; unsigned __int16
0x18009478f  lea     rdx, aSxcrackpath; "SxCrackPath"
0x180094796  mov     r8d, 559h; unsigned __int16
0x18009479c  lea     rcx, [rsp+110h+var_E0]; this
0x1800947a1  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800947a6  lea     rax, qword_1800EE510
0x1800947ad  xor     r12d, r12d
0x1800947b0  mov     [rbp+57h+lpFileName], rax
0x1800947b4  mov     [rbp+57h+lpBuffer], rax
0x1800947b8  mov     [rbp+57h+lpszVolumePathName], rax
0x1800947bc  mov     [rbp+57h+var_68], rax
0x1800947c0  mov     [rbp+57h+lpszVolumeName], rax
0x1800947c4  mov     [rbp+57h+var_88], rax
0x1800947c8  mov     eax, 564h
0x1800947cd  mov     [rbp+57h+var_50], r12
0x1800947d1  mov     qword ptr [rbp+57h+var_90], r12
0x1800947d5  mov     qword ptr [rbp+57h+var_A0], r12
0x1800947d9  mov     [rbp+57h+var_60], r12
0x1800947dd  mov     qword ptr [rbp+57h+var_70], r12
0x1800947e1  mov     qword ptr [rbp+57h+var_80], r12
0x1800947e5  test    rbx, rbx
0x1800947e8  jz      loc_180094CDA
0x1800947ee  mov     rdx, rbx; lpSrc
0x1800947f1  mov     [rsp+110h+var_E0], r12d
0x1800947f6  lea     rcx, [rbp+57h+lpFileName]; this
0x1800947fa  mov     [rsp+110h+var_DC], ax
0x1800947ff  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x180094804  mov     [rsp+110h+var_E0], eax
0x180094808  test    eax, eax
0x18009480a  mov     eax, 566h
0x18009480f  js      loc_180094CE2
0x180094815  mov     [rsp+110h+var_DC], ax
0x18009481a  mov     rcx, cs:WPP_GLOBAL_Control
0x180094821  mov     rsi, [rbp+57h+lpFileName]
0x180094825  cmp     rcx, r13
0x180094828  jz      short loc_18009484B
0x18009482a  test    dword ptr [rcx+1Ch], 1000000h
0x180094831  jz      short loc_18009484B
0x180094833  mov     rcx, [rcx+10h]
0x180094837  lea     edx, [r12+25h]
0x18009483c  mov     r9, rsi
0x18009483f  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180094846  call    WPP_SF_S
0x18009484b  xor     r9d, r9d; lpFilePart
0x18009484e  xor     r8d, r8d; lpBuffer
0x180094851  xor     edx, edx; nBufferLength
0x180094853  mov     rcx, rsi; lpFileName
0x180094856  call    cs:__imp_GetFullPathNameW
0x18009485d  nop     dword ptr [rax+rax+00h]
0x180094862  mov     edi, eax
0x180094864  test    eax, eax
0x180094866  jz      loc_180094C8B
0x18009486c  mov     ecx, 56Eh
0x180094871  mov     [rsp+110h+var_E0], r12d
0x180094876  mov     [rsp+110h+var_DC], cx
0x18009487b  lea     ebx, [rcx+3]
0x18009487e  lea     edx, [rdi-1]; unsigned int
0x180094881  lea     rcx, [rbp+57h+lpBuffer]; this
0x180094885  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x18009488a  mov     [rsp+110h+var_E0], eax
0x18009488e  test    eax, eax
0x180094890  js      loc_1800949E8
0x180094896  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x18009489a  xor     r9d, r9d; lpFilePart
0x18009489d  mov     [rsp+110h+var_DC], bx
0x1800948a2  mov     rcx, rsi; lpFileName
0x1800948a5  mov     ebx, [rbp+57h+var_90+4]
0x1800948a8  lea     edx, [rbx+1]; nBufferLength
0x1800948ab  call    cs:__imp_GetFullPathNameW
0x1800948b2  nop     dword ptr [rax+rax+00h]
0x1800948b7  mov     edx, ebx; unsigned int
0x1800948b9  lea     rcx, [rbp+57h+lpBuffer]; this
0x1800948bd  mov     edi, eax
0x1800948bf  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800948c4  test    edi, edi
0x1800948c6  jz      loc_180094C5C
0x1800948cc  mov     eax, 574h
0x1800948d1  mov     [rsp+110h+var_E0], r12d
0x1800948d6  mov     [rsp+110h+var_DC], ax
0x1800948db  lea     ebx, [rax-3]
0x1800948de  cmp     edi, [rbp+57h+var_90+4]
0x1800948e1  ja      short loc_18009487E
0x1800948e3  mov     edx, edi; unsigned int
0x1800948e5  lea     rcx, [rbp+57h+lpBuffer]; this
0x1800948e9  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x1800948ee  mov     [rsp+110h+var_E0], eax
0x1800948f2  test    eax, eax
0x1800948f4  lea     eax, [rbx+6]
0x1800948f7  js      loc_180094CE2
0x1800948fd  mov     [rsp+110h+var_DC], ax
0x180094902  mov     rcx, cs:WPP_GLOBAL_Control
0x180094909  mov     rsi, [rbp+57h+lpBuffer]
0x18009490d  cmp     rcx, r13
0x180094910  jz      short loc_180094937
0x180094912  test    dword ptr [rcx+1Ch], 1000000h
0x180094919  jz      short loc_180094937
0x18009491b  mov     rcx, [rcx+10h]
0x18009491f  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180094926  mov     edx, 28h ; '('
0x18009492b  mov     dword ptr [rsp+110h+var_F0], edi
0x18009492f  mov     r9, rsi
0x180094932  call    WPP_SF_Sd
0x180094937  mov     edx, edi; unsigned int
0x180094939  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x18009493d  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180094942  mov     [rsp+110h+var_E0], eax
0x180094946  test    eax, eax
0x180094948  mov     eax, 580h
0x18009494d  js      loc_180094CE2
0x180094953  mov     rdx, [rbp+57h+lpszVolumePathName]; lpszVolumePathName
0x180094957  lea     r8d, [rdi+1]; cchBufferLength
0x18009495b  mov     rcx, rsi; lpszFileName
0x18009495e  mov     [rsp+110h+var_DC], ax
0x180094963  mov     ebx, 588h
0x180094968  call    cs:__imp_GetVolumePathNameW
0x18009496f  nop     dword ptr [rax+rax+00h]
0x180094974  mov     edx, [rbp+57h+var_A0+4]; unsigned int
0x180094977  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x18009497b  test    eax, eax
0x18009497d  jnz     short loc_1800949F2
0x18009497f  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180094984  call    cs:__imp_GetLastError
0x18009498b  nop     dword ptr [rax+rax+00h]
0x180094990  cmp     eax, 0CEh
0x180094995  jnz     short loc_1800949DF
0x180094997  mov     [rsp+110h+var_DC], bx
0x18009499c  mov     eax, 58Ah
0x1800949a1  lea     ebx, [rdi+rdi]
0x1800949a4  cmp     ebx, edi
0x1800949a6  jbe     short loc_1800949D2
0x1800949a8  mov     edx, ebx; unsigned int
0x1800949aa  mov     [rsp+110h+var_E0], r12d
0x1800949af  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x1800949b3  mov     [rsp+110h+var_DC], ax
0x1800949b8  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800949bd  mov     [rsp+110h+var_E0], eax
0x1800949c1  test    eax, eax
0x1800949c3  mov     eax, 58Bh
0x1800949c8  js      loc_180094CE2
0x1800949ce  mov     edi, ebx
0x1800949d0  jmp     short loc_180094953
0x1800949d2  mov     [rsp+110h+var_E0], 80070216h
0x1800949da  jmp     loc_180094CE2
0x1800949df  call    GetLastFailureAsHRESULT
0x1800949e4  mov     [rsp+110h+var_E0], eax
0x1800949e8  mov     [rsp+110h+var_DA], bx
0x1800949ed  jmp     loc_180094CE7
0x1800949f2  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800949f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800949fe  cmp     rcx, r13
0x180094a01  jz      short loc_180094A25
0x180094a03  test    dword ptr [rcx+1Ch], 1000000h
0x180094a0a  jz      short loc_180094A25
0x180094a0c  mov     r9, [rbp+57h+lpszVolumePathName]
0x180094a10  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180094a17  mov     rcx, [rcx+10h]
0x180094a1b  mov     edx, 29h ; ')'
0x180094a20  call    WPP_SF_S
0x180094a25  mov     eax, [rbp+57h+var_A0]
0x180094a28  lea     rcx, [rbp+57h+var_68]; this
0x180094a2c  lea     rdx, [rsi+rax*2]; unsigned __int16 *
0x180094a30  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180094a35  mov     [rsp+110h+var_E0], eax
0x180094a39  test    eax, eax
0x180094a3b  mov     eax, 596h
0x180094a40  js      loc_180094CE2
0x180094a46  mov     [rsp+110h+var_DC], ax
0x180094a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180094a52  cmp     rcx, r13
0x180094a55  jz      short loc_180094A79
0x180094a57  test    dword ptr [rcx+1Ch], 1000000h
0x180094a5e  jz      short loc_180094A79
0x180094a60  mov     r9, [rbp+57h+var_68]
0x180094a64  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180094a6b  mov     rcx, [rcx+10h]
0x180094a6f  mov     edx, 2Ah ; '*'
0x180094a74  call    WPP_SF_S
0x180094a79  mov     edx, 5Ch ; '\'; unsigned __int16
0x180094a7e  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x180094a82  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180094a87  mov     [rsp+110h+var_E0], eax
0x180094a8b  test    eax, eax
0x180094a8d  mov     eax, 5A1h
0x180094a92  js      loc_180094CE2
0x180094a98  mov     esi, 104h
0x180094a9d  mov     [rsp+110h+var_DC], ax
0x180094aa2  mov     edx, esi; unsigned int
0x180094aa4  lea     rcx, [rbp+57h+lpszVolumeName]; this
0x180094aa8  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180094aad  mov     [rsp+110h+var_E0], eax
0x180094ab1  test    eax, eax
0x180094ab3  mov     eax, 5A2h
0x180094ab8  js      loc_180094CE2
0x180094abe  mov     edi, [rbp+57h+var_70+4]
0x180094ac1  mov     rbx, [rbp+57h+lpszVolumePathName]
0x180094ac5  mov     rdx, [rbp+57h+lpszVolumeName]; lpszVolumeName
0x180094ac9  mov     rcx, rbx; lpszVolumeMountPoint
0x180094acc  mov     [rsp+110h+var_DC], ax
0x180094ad1  lea     r8d, [rdi+1]; cchBufferLength
0x180094ad5  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180094adc  nop     dword ptr [rax+rax+00h]
0x180094ae1  test    eax, eax
0x180094ae3  jnz     short loc_180094B2F
0x180094ae5  call    GetLastFailureAsHRESULT
0x180094aea  mov     ecx, 5A4h
0x180094aef  mov     [rsp+110h+var_E0], eax
0x180094af3  mov     [rsp+110h+var_DA], cx
0x180094af8  mov     rcx, cs:WPP_GLOBAL_Control
0x180094aff  cmp     rcx, r13
0x180094b02  jz      loc_180094CE7
0x180094b08  test    dword ptr [rcx+1Ch], 2000000h
0x180094b0f  jz      loc_180094CE7
0x180094b15  mov     dword ptr [rsp+110h+var_E8], eax
0x180094b19  lea     r9, aGetvolumenamef_2; "::GetVolumeNameForVolumeMountPointW( st"...
0x180094b20  mov     [rsp+110h+var_F0], rbx
0x180094b25  mov     edx, 2Bh ; '+'
0x180094b2a  jmp     loc_180094CC8
0x180094b2f  mov     ecx, 5A4h
0x180094b34  mov     [rsp+110h+var_E0], r12d
0x180094b39  mov     [rsp+110h+var_DC], cx
0x180094b3e  mov     edx, edi; unsigned int
0x180094b40  lea     rcx, [rbp+57h+lpszVolumeName]; this
0x180094b44  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180094b49  mov     edx, esi; unsigned int
0x180094b4b  lea     rcx, [rbp+57h+var_88]; this
0x180094b4f  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180094b54  mov     [rsp+110h+var_E0], eax
0x180094b58  test    eax, eax
0x180094b5a  mov     eax, 5A7h
0x180094b5f  js      loc_180094CE2
0x180094b65  mov     edi, [rbp+57h+var_80+4]
0x180094b68  mov     rdx, [rbp+57h+var_88]; lpszVolumeName
0x180094b6c  mov     rcx, [rbp+57h+lpszVolumeName]; lpszVolumeMountPoint
0x180094b70  mov     [rsp+110h+var_DC], ax
0x180094b75  lea     r8d, [rdi+1]; cchBufferLength
0x180094b79  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180094b80  nop     dword ptr [rax+rax+00h]
0x180094b85  test    eax, eax
0x180094b87  jnz     short loc_180094BD3
0x180094b89  call    GetLastFailureAsHRESULT
0x180094b8e  mov     ecx, 5A9h
0x180094b93  mov     [rsp+110h+var_E0], eax
0x180094b97  mov     [rsp+110h+var_DA], cx
0x180094b9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180094ba3  cmp     rcx, r13
0x180094ba6  jz      loc_180094CE7
0x180094bac  test    dword ptr [rcx+1Ch], 2000000h
0x180094bb3  jz      loc_180094CE7
0x180094bb9  mov     dword ptr [rsp+110h+var_E8], eax
0x180094bbd  lea     r9, aGetvolumenamef_1; "::GetVolumeNameForVolumeMountPointW( st"...
0x180094bc4  mov     [rsp+110h+var_F0], rbx
0x180094bc9  mov     edx, 2Ch ; ','
0x180094bce  jmp     loc_180094CC8
0x180094bd3  mov     ecx, 5A9h
0x180094bd8  mov     [rsp+110h+var_E0], r12d
0x180094bdd  mov     [rsp+110h+var_DC], cx
0x180094be2  mov     edx, edi; unsigned int
0x180094be4  lea     rcx, [rbp+57h+var_88]; this
0x180094be8  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180094bed  mov     rcx, cs:WPP_GLOBAL_Control
0x180094bf4  cmp     rcx, r13
0x180094bf7  jz      short loc_180094C1B
0x180094bf9  test    dword ptr [rcx+1Ch], 1000000h
0x180094c00  jz      short loc_180094C1B
0x180094c02  mov     r9, [rbp+57h+var_88]
0x180094c06  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180094c0d  mov     rcx, [rcx+10h]
0x180094c11  mov     edx, 2Dh ; '-'
0x180094c16  call    WPP_SF_S
0x180094c1b  test    r15, r15
0x180094c1e  jz      short loc_180094C42
0x180094c20  mov     rdx, [rbp+57h+var_88]; unsigned __int16 *
0x180094c24  mov     rcx, r15; this
0x180094c27  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180094c2c  mov     [rsp+110h+var_E0], eax
  ... truncated ...
```
