# SxCrackPath(ushort const *,CBsString *,CBsString *)

- ea: `0x18009063c`
- end: `0x180090c29`
- name: `?SxCrackPath@@YAJPEBGPEAVCBsString@@1@Z`
- size: `1517`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, struct CBsString *this, struct CBsString *)`
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, installer_update`

## callers

- `0x180038fc8`

## callees

- `0x180008240`
- `0x180014394`
- `0x1800145f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18009063c`
- `0x18009386c`
- `0x1800998c8`
- `0x180099bf4`
- `0x180099c84`
- `0x18009a24c`
- `0x18009a354`
- `0x18009a3ac`
- `0x18009a3f0`
- `0x18009ae34`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009087e`
- `KERNEL32!GetLastError` at `0x18009087e`
- `KERNEL32!GetVolumePathNameW` at `0x180090868`
- `KERNEL32!GetVolumePathNameW` at `0x180090868`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800909c9`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180090a67`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800909c9`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180090a67`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180090762`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800907b1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180090762`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800907b1`

## string_xrefs

- `0x18009069b`: `SxCrackPath`
- `0x180090ba4`: `dwPathLength != 0`
- `0x180090a07`: `::GetVolumeNameForVolumeMountPointW( strMountPoint, strTwice.GetBuffer(), strTwice.GetAllocLength() + 1 )`
- `0x180090aa5`: `::GetVolumeNameForVolumeMountPointW( strTwice, strVolume.GetBuffer(), strVolume.GetAllocLength() + 1 )`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "SxCrackPath", 1369, 1);
  lpFileName[0] = (LPCWSTR)qword_1800E8530;
  lpBuffer = (LPWSTR)qword_1800E8530;
  lpszVolumePathName = (LPWSTR)qword_1800E8530;
  v38[0] = qword_1800E8530;
  lpszVolumeName = (LPWSTR)qword_1800E8530;
  v34 = (LPWSTR)qword_1800E8530;
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
0x18009063c  push    rbp
0x18009063e  push    rbx
0x18009063f  push    rsi
0x180090640  push    rdi
0x180090641  push    r12
0x180090643  push    r13
0x180090645  push    r14
0x180090647  push    r15
0x180090649  lea     rbp, [rsp-1Fh]
0x18009064e  sub     rsp, 0D8h
0x180090655  mov     r14, r8
0x180090658  mov     r15, rdx
0x18009065b  mov     rbx, rcx
0x18009065e  mov     rcx, cs:WPP_GLOBAL_Control
0x180090665  lea     r13, WPP_GLOBAL_Control
0x18009066c  cmp     rcx, r13
0x18009066f  jz      short loc_180090695
0x180090671  test    dword ptr [rcx+1Ch], 20000000h
0x180090678  jz      short loc_180090695
0x18009067a  mov     rcx, [rcx+10h]
0x18009067e  mov     edx, 24h ; '$'
0x180090683  mov     [rsp+110h+var_E8], r8
0x180090688  mov     r9, rbx
0x18009068b  mov     [rsp+110h+var_F0], r15
0x180090690  call    WPP_SF_Sqq
0x180090695  mov     r9d, 1; unsigned __int16
0x18009069b  lea     rdx, aSxcrackpath; "SxCrackPath"
0x1800906a2  mov     r8d, 559h; unsigned __int16
0x1800906a8  lea     rcx, [rsp+110h+var_E0]; this
0x1800906ad  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800906b2  lea     rax, qword_1800E8530
0x1800906b9  xor     r12d, r12d
0x1800906bc  mov     [rbp+57h+lpFileName], rax
0x1800906c0  mov     [rbp+57h+lpBuffer], rax
0x1800906c4  mov     [rbp+57h+lpszVolumePathName], rax
0x1800906c8  mov     [rbp+57h+var_68], rax
0x1800906cc  mov     [rbp+57h+lpszVolumeName], rax
0x1800906d0  mov     [rbp+57h+var_88], rax
0x1800906d4  mov     eax, 564h
0x1800906d9  mov     [rbp+57h+var_50], r12
0x1800906dd  mov     qword ptr [rbp+57h+var_90], r12
0x1800906e1  mov     qword ptr [rbp+57h+var_A0], r12
0x1800906e5  mov     [rbp+57h+var_60], r12
0x1800906e9  mov     qword ptr [rbp+57h+var_70], r12
0x1800906ed  mov     qword ptr [rbp+57h+var_80], r12
0x1800906f1  test    rbx, rbx
0x1800906f4  jz      loc_180090BC2
0x1800906fa  mov     rdx, rbx; lpSrc
0x1800906fd  mov     [rsp+110h+var_E0], r12d
0x180090702  lea     rcx, [rbp+57h+lpFileName]; this
0x180090706  mov     [rsp+110h+var_DC], ax
0x18009070b  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x180090710  mov     [rsp+110h+var_E0], eax
0x180090714  test    eax, eax
0x180090716  mov     eax, 566h
0x18009071b  js      loc_180090BCA
0x180090721  mov     [rsp+110h+var_DC], ax
0x180090726  mov     rcx, cs:WPP_GLOBAL_Control
0x18009072d  mov     rsi, [rbp+57h+lpFileName]
0x180090731  cmp     rcx, r13
0x180090734  jz      short loc_180090757
0x180090736  test    dword ptr [rcx+1Ch], 1000000h
0x18009073d  jz      short loc_180090757
0x18009073f  mov     rcx, [rcx+10h]
0x180090743  lea     edx, [r12+25h]
0x180090748  mov     r9, rsi
0x18009074b  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180090752  call    WPP_SF_S
0x180090757  xor     r9d, r9d; lpFilePart
0x18009075a  xor     r8d, r8d; lpBuffer
0x18009075d  xor     edx, edx; nBufferLength
0x18009075f  mov     rcx, rsi; lpFileName
0x180090762  call    cs:__imp_GetFullPathNameW
0x180090768  mov     edi, eax
0x18009076a  test    eax, eax
0x18009076c  jz      loc_180090B73
0x180090772  mov     ecx, 56Eh
0x180090777  mov     [rsp+110h+var_E0], r12d
0x18009077c  mov     [rsp+110h+var_DC], cx
0x180090781  lea     ebx, [rcx+3]
0x180090784  lea     edx, [rdi-1]; unsigned int
0x180090787  lea     rcx, [rbp+57h+lpBuffer]; this
0x18009078b  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180090790  mov     [rsp+110h+var_E0], eax
0x180090794  test    eax, eax
0x180090796  js      loc_1800908DC
0x18009079c  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x1800907a0  xor     r9d, r9d; lpFilePart
0x1800907a3  mov     [rsp+110h+var_DC], bx
0x1800907a8  mov     rcx, rsi; lpFileName
0x1800907ab  mov     ebx, [rbp+57h+var_90+4]
0x1800907ae  lea     edx, [rbx+1]; nBufferLength
0x1800907b1  call    cs:__imp_GetFullPathNameW
0x1800907b7  mov     edx, ebx; unsigned int
0x1800907b9  lea     rcx, [rbp+57h+lpBuffer]; this
0x1800907bd  mov     edi, eax
0x1800907bf  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800907c4  test    edi, edi
0x1800907c6  jz      loc_180090B44
0x1800907cc  mov     eax, 574h
0x1800907d1  mov     [rsp+110h+var_E0], r12d
0x1800907d6  mov     [rsp+110h+var_DC], ax
0x1800907db  lea     ebx, [rax-3]
0x1800907de  cmp     edi, [rbp+57h+var_90+4]
0x1800907e1  ja      short loc_180090784
0x1800907e3  mov     edx, edi; unsigned int
0x1800907e5  lea     rcx, [rbp+57h+lpBuffer]; this
0x1800907e9  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x1800907ee  mov     [rsp+110h+var_E0], eax
0x1800907f2  test    eax, eax
0x1800907f4  lea     eax, [rbx+6]
0x1800907f7  js      loc_180090BCA
0x1800907fd  mov     [rsp+110h+var_DC], ax
0x180090802  mov     rcx, cs:WPP_GLOBAL_Control
0x180090809  mov     rsi, [rbp+57h+lpBuffer]
0x18009080d  cmp     rcx, r13
0x180090810  jz      short loc_180090837
0x180090812  test    dword ptr [rcx+1Ch], 1000000h
0x180090819  jz      short loc_180090837
0x18009081b  mov     rcx, [rcx+10h]
0x18009081f  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180090826  mov     edx, 28h ; '('
0x18009082b  mov     dword ptr [rsp+110h+var_F0], edi
0x18009082f  mov     r9, rsi
0x180090832  call    WPP_SF_Sd
0x180090837  mov     edx, edi; unsigned int
0x180090839  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x18009083d  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180090842  mov     [rsp+110h+var_E0], eax
0x180090846  test    eax, eax
0x180090848  mov     eax, 580h
0x18009084d  js      loc_180090BCA
0x180090853  mov     rdx, [rbp+57h+lpszVolumePathName]; lpszVolumePathName
0x180090857  lea     r8d, [rdi+1]; cchBufferLength
0x18009085b  mov     rcx, rsi; lpszFileName
0x18009085e  mov     [rsp+110h+var_DC], ax
0x180090863  mov     ebx, 588h
0x180090868  call    cs:__imp_GetVolumePathNameW
0x18009086e  mov     edx, [rbp+57h+var_A0+4]; unsigned int
0x180090871  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x180090875  test    eax, eax
0x180090877  jnz     short loc_1800908E6
0x180090879  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x18009087e  call    cs:__imp_GetLastError
0x180090884  cmp     eax, 0CEh
0x180090889  jnz     short loc_1800908D3
0x18009088b  mov     [rsp+110h+var_DC], bx
0x180090890  mov     eax, 58Ah
0x180090895  lea     ebx, [rdi+rdi]
0x180090898  cmp     ebx, edi
0x18009089a  jbe     short loc_1800908C6
0x18009089c  mov     edx, ebx; unsigned int
0x18009089e  mov     [rsp+110h+var_E0], r12d
0x1800908a3  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x1800908a7  mov     [rsp+110h+var_DC], ax
0x1800908ac  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800908b1  mov     [rsp+110h+var_E0], eax
0x1800908b5  test    eax, eax
0x1800908b7  mov     eax, 58Bh
0x1800908bc  js      loc_180090BCA
0x1800908c2  mov     edi, ebx
0x1800908c4  jmp     short loc_180090853
0x1800908c6  mov     [rsp+110h+var_E0], 80070216h
0x1800908ce  jmp     loc_180090BCA
0x1800908d3  call    GetLastFailureAsHRESULT
0x1800908d8  mov     [rsp+110h+var_E0], eax
0x1800908dc  mov     [rsp+110h+var_DA], bx
0x1800908e1  jmp     loc_180090BCF
0x1800908e6  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800908eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800908f2  cmp     rcx, r13
0x1800908f5  jz      short loc_180090919
0x1800908f7  test    dword ptr [rcx+1Ch], 1000000h
0x1800908fe  jz      short loc_180090919
0x180090900  mov     r9, [rbp+57h+lpszVolumePathName]
0x180090904  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18009090b  mov     rcx, [rcx+10h]
0x18009090f  mov     edx, 29h ; ')'
0x180090914  call    WPP_SF_S
0x180090919  mov     eax, [rbp+57h+var_A0]
0x18009091c  lea     rcx, [rbp+57h+var_68]; this
0x180090920  lea     rdx, [rsi+rax*2]; unsigned __int16 *
0x180090924  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180090929  mov     [rsp+110h+var_E0], eax
0x18009092d  test    eax, eax
0x18009092f  mov     eax, 596h
0x180090934  js      loc_180090BCA
0x18009093a  mov     [rsp+110h+var_DC], ax
0x18009093f  mov     rcx, cs:WPP_GLOBAL_Control
0x180090946  cmp     rcx, r13
0x180090949  jz      short loc_18009096D
0x18009094b  test    dword ptr [rcx+1Ch], 1000000h
0x180090952  jz      short loc_18009096D
0x180090954  mov     r9, [rbp+57h+var_68]
0x180090958  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18009095f  mov     rcx, [rcx+10h]
0x180090963  mov     edx, 2Ah ; '*'
0x180090968  call    WPP_SF_S
0x18009096d  mov     edx, 5Ch ; '\'; unsigned __int16
0x180090972  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x180090976  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18009097b  mov     [rsp+110h+var_E0], eax
0x18009097f  test    eax, eax
0x180090981  mov     eax, 5A1h
0x180090986  js      loc_180090BCA
0x18009098c  mov     esi, 104h
0x180090991  mov     [rsp+110h+var_DC], ax
0x180090996  mov     edx, esi; unsigned int
0x180090998  lea     rcx, [rbp+57h+lpszVolumeName]; this
0x18009099c  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800909a1  mov     [rsp+110h+var_E0], eax
0x1800909a5  test    eax, eax
0x1800909a7  mov     eax, 5A2h
0x1800909ac  js      loc_180090BCA
0x1800909b2  mov     edi, [rbp+57h+var_70+4]
0x1800909b5  mov     rbx, [rbp+57h+lpszVolumePathName]
0x1800909b9  mov     rdx, [rbp+57h+lpszVolumeName]; lpszVolumeName
0x1800909bd  mov     rcx, rbx; lpszVolumeMountPoint
0x1800909c0  mov     [rsp+110h+var_DC], ax
0x1800909c5  lea     r8d, [rdi+1]; cchBufferLength
0x1800909c9  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800909cf  test    eax, eax
0x1800909d1  jnz     short loc_180090A1D
0x1800909d3  call    GetLastFailureAsHRESULT
0x1800909d8  mov     ecx, 5A4h
0x1800909dd  mov     [rsp+110h+var_E0], eax
0x1800909e1  mov     [rsp+110h+var_DA], cx
0x1800909e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800909ed  cmp     rcx, r13
0x1800909f0  jz      loc_180090BCF
0x1800909f6  test    dword ptr [rcx+1Ch], 2000000h
0x1800909fd  jz      loc_180090BCF
0x180090a03  mov     dword ptr [rsp+110h+var_E8], eax
0x180090a07  lea     r9, aGetvolumenamef_2; "::GetVolumeNameForVolumeMountPointW( st"...
0x180090a0e  mov     [rsp+110h+var_F0], rbx
0x180090a13  mov     edx, 2Bh ; '+'
0x180090a18  jmp     loc_180090BB0
0x180090a1d  mov     ecx, 5A4h
0x180090a22  mov     [rsp+110h+var_E0], r12d
0x180090a27  mov     [rsp+110h+var_DC], cx
0x180090a2c  mov     edx, edi; unsigned int
0x180090a2e  lea     rcx, [rbp+57h+lpszVolumeName]; this
0x180090a32  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180090a37  mov     edx, esi; unsigned int
0x180090a39  lea     rcx, [rbp+57h+var_88]; this
0x180090a3d  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180090a42  mov     [rsp+110h+var_E0], eax
0x180090a46  test    eax, eax
0x180090a48  mov     eax, 5A7h
0x180090a4d  js      loc_180090BCA
0x180090a53  mov     edi, [rbp+57h+var_80+4]
0x180090a56  mov     rdx, [rbp+57h+var_88]; lpszVolumeName
0x180090a5a  mov     rcx, [rbp+57h+lpszVolumeName]; lpszVolumeMountPoint
0x180090a5e  mov     [rsp+110h+var_DC], ax
0x180090a63  lea     r8d, [rdi+1]; cchBufferLength
0x180090a67  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180090a6d  test    eax, eax
0x180090a6f  jnz     short loc_180090ABB
0x180090a71  call    GetLastFailureAsHRESULT
0x180090a76  mov     ecx, 5A9h
0x180090a7b  mov     [rsp+110h+var_E0], eax
0x180090a7f  mov     [rsp+110h+var_DA], cx
0x180090a84  mov     rcx, cs:WPP_GLOBAL_Control
0x180090a8b  cmp     rcx, r13
0x180090a8e  jz      loc_180090BCF
0x180090a94  test    dword ptr [rcx+1Ch], 2000000h
0x180090a9b  jz      loc_180090BCF
0x180090aa1  mov     dword ptr [rsp+110h+var_E8], eax
0x180090aa5  lea     r9, aGetvolumenamef_1; "::GetVolumeNameForVolumeMountPointW( st"...
0x180090aac  mov     [rsp+110h+var_F0], rbx
0x180090ab1  mov     edx, 2Ch ; ','
0x180090ab6  jmp     loc_180090BB0
0x180090abb  mov     ecx, 5A9h
0x180090ac0  mov     [rsp+110h+var_E0], r12d
0x180090ac5  mov     [rsp+110h+var_DC], cx
0x180090aca  mov     edx, edi; unsigned int
0x180090acc  lea     rcx, [rbp+57h+var_88]; this
0x180090ad0  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180090ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x180090adc  cmp     rcx, r13
0x180090adf  jz      short loc_180090B03
0x180090ae1  test    dword ptr [rcx+1Ch], 1000000h
0x180090ae8  jz      short loc_180090B03
0x180090aea  mov     r9, [rbp+57h+var_88]
0x180090aee  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180090af5  mov     rcx, [rcx+10h]
0x180090af9  mov     edx, 2Dh ; '-'
0x180090afe  call    WPP_SF_S
0x180090b03  test    r15, r15
0x180090b06  jz      short loc_180090B2A
0x180090b08  mov     rdx, [rbp+57h+var_88]; unsigned __int16 *
0x180090b0c  mov     rcx, r15; this
0x180090b0f  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180090b14  mov     [rsp+110h+var_E0], eax
0x180090b18  test    eax, eax
0x180090b1a  mov     eax, 5B3h
0x180090b1f  js      loc_180090BCA
0x180090b25  mov     [rsp+110h+var_DC], ax
0x180090b2a  test    r14, r14
0x180090b2d  jz      loc_180090BCF
  ... truncated ...
```
