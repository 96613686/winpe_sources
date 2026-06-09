# SxCrackPath(ushort const *,CBsString *,CBsString *)

- ea: `0x180027eac`
- end: `0x180028494`
- name: `?SxCrackPath@@YAJPEBGPEAVCBsString@@1@Z`
- size: `1512`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, struct CBsString *this, struct CBsString *)`
- caller_count: `3`
- callee_count: `16`
- tags: `reparse_path, installer_update`

## callers

- `0x180012fe0`
- `0x18001faf8`
- `0x180024640`

## callees

- `0x180020908`
- `0x180020968`
- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x180027eac`
- `0x18002b4a0`
- `0x18002d6e8`
- `0x180034ed4`
- `0x180034f54`
- `0x180034fe4`
- `0x18003532c`
- `0x18003536c`
- `0x1800353c4`
- `0x18003540c`
- `0x180035b00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800280ee`
- `KERNEL32!GetLastError` at `0x1800280ee`
- `KERNEL32!GetVolumePathNameW` at `0x1800280d8`
- `KERNEL32!GetVolumePathNameW` at `0x1800280d8`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180028234`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800282d2`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180028234`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800282d2`
- `KERNEL32!GetFullPathNameW` at `0x180027fd2`
- `KERNEL32!GetFullPathNameW` at `0x180028021`
- `KERNEL32!GetFullPathNameW` at `0x180027fd2`
- `KERNEL32!GetFullPathNameW` at `0x180028021`

## string_xrefs

- `0x180027f0b`: `SxCrackPath`
- `0x18002840f`: `dwPathLength != 0`
- `0x180028272`: `::GetVolumeNameForVolumeMountPointW( strMountPoint, strTwice.GetBuffer(), strTwice.GetAllocLength() + 1 )`
- `0x180028310`: `::GetVolumeNameForVolumeMountPointW( strTwice, strVolume.GetBuffer(), strVolume.GetAllocLength() + 1 )`

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
  unsigned __int16 v15; // dx
  unsigned int v16; // edi
  LPWSTR v17; // rbx
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // edi
  __int64 v21; // rcx
  int v22; // eax
  int LastFailureAsHRESULT; // eax
  _QWORD *v24; // rcx
  int v25; // edx
  unsigned int v26; // ebx
  __int64 v27; // rdx
  __int64 v28; // r8
  int v30; // [rsp+30h] [rbp-89h] BYREF
  __int16 v31; // [rsp+34h] [rbp-85h]
  __int16 v32; // [rsp+36h] [rbp-83h]
  LPWSTR lpszVolumePathName; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v34[2]; // [rsp+70h] [rbp-49h]
  LPWSTR lpBuffer; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v36[2]; // [rsp+80h] [rbp-39h]
  LPWSTR v37; // [rsp+88h] [rbp-31h] BYREF
  unsigned int v38[2]; // [rsp+90h] [rbp-29h]
  LPWSTR lpszVolumeName; // [rsp+98h] [rbp-21h] BYREF
  unsigned int v40[2]; // [rsp+A0h] [rbp-19h]
  unsigned __int16 *v41[2]; // [rsp+A8h] [rbp-11h] BYREF
  LPCWSTR lpFileName[11]; // [rsp+B8h] [rbp-1h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_Sqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, (_DWORD)a3, (_DWORD)lpSrc, (char)this, (char)a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v30, "SxCrackPath", 1369, 1);
  lpFileName[0] = &FileName;
  lpBuffer = (LPWSTR)&FileName;
  lpszVolumePathName = (LPWSTR)&FileName;
  v41[0] = (unsigned __int16 *)&FileName;
  lpszVolumeName = (LPWSTR)&FileName;
  v37 = (LPWSTR)&FileName;
  v6 = 1380;
  lpFileName[1] = 0;
  *(_QWORD *)v36 = 0;
  *(_QWORD *)v34 = 0;
  v41[1] = 0;
  *(_QWORD *)v40 = 0;
  *(_QWORD *)v38 = 0;
  if ( !lpSrc )
  {
    v30 = -2147024809;
    goto LABEL_62;
  }
  v30 = 0;
  v31 = 1380;
  v30 = CBsString::ExpandEnvironmentStringsW((CBsString *)lpFileName, lpSrc);
  v6 = 1382;
  if ( v30 < 0 )
  {
LABEL_62:
    v32 = v6;
    goto LABEL_63;
  }
  v31 = 1382;
  v7 = lpFileName[0];
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, lpFileName[0]);
  FullPathNameW = GetFullPathNameW(v7, 0, 0, 0);
  if ( FullPathNameW )
  {
    v30 = 0;
    v31 = 1390;
    v10 = 1393;
    do
    {
      v30 = CBsString::ExtendBuffer((CBsString *)&lpBuffer, FullPathNameW - 1);
      if ( v30 < 0 )
      {
LABEL_26:
        v32 = v10;
        goto LABEL_63;
      }
      v31 = 1393;
      v11 = v36[1];
      FullPathNameW = GetFullPathNameW(v7, v36[1] + 1, lpBuffer, 0);
      CBsString::BoundUpdateLength((CBsString *)&lpBuffer, v11);
      if ( !FullPathNameW )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
        v30 = LastFailureAsHRESULT;
        v32 = 1396;
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          v25 = 39;
          goto LABEL_59;
        }
        goto LABEL_63;
      }
      v30 = 0;
      v31 = 1396;
      v10 = 1393;
    }
    while ( FullPathNameW > v36[1] );
    v30 = CBsString::SetLength((CBsString *)&lpBuffer, FullPathNameW);
    v6 = 1399;
    if ( v30 < 0 )
      goto LABEL_62;
    v31 = 1399;
    v13 = lpBuffer;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
        (_DWORD)lpBuffer,
        FullPathNameW);
    v30 = CBsString::ExtendBuffer((CBsString *)&lpszVolumePathName, FullPathNameW);
    v6 = 1408;
    if ( v30 < 0 )
      goto LABEL_62;
    while ( 1 )
    {
      v31 = v6;
      v10 = 1416;
      if ( GetVolumePathNameW(v13, lpszVolumePathName, FullPathNameW + 1) )
        break;
      CBsString::BoundUpdateLength((CBsString *)&lpszVolumePathName, v34[1]);
      if ( GetLastError() != 206 )
      {
        v30 = GetLastFailureAsHRESULT(v14);
        goto LABEL_26;
      }
      v31 = 1416;
      v6 = 1418;
      if ( 2 * FullPathNameW <= FullPathNameW )
      {
        v30 = -2147024362;
        goto LABEL_62;
      }
      v30 = 0;
      v31 = 1418;
      v30 = CBsString::ExtendBuffer((CBsString *)&lpszVolumePathName, 2 * FullPathNameW);
      v6 = 1419;
      if ( v30 < 0 )
        goto LABEL_62;
      FullPathNameW *= 2;
    }
    CBsString::BoundUpdateLength((CBsString *)&lpszVolumePathName, v34[1]);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
        lpszVolumePathName);
    v30 = CBsString::Set((CBsString *)v41, &v13[v34[0]]);
    v6 = 1430;
    if ( v30 < 0 )
      goto LABEL_62;
    v31 = 1430;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, v41[0]);
    v30 = CBsString::Trailing((CBsString *)&lpszVolumePathName, v15);
    v6 = 1441;
    if ( v30 < 0 )
      goto LABEL_62;
    v31 = 1441;
    v30 = CBsString::ExtendBuffer((CBsString *)&lpszVolumeName, 0x104u);
    v6 = 1442;
    if ( v30 < 0 )
      goto LABEL_62;
    v16 = v40[1];
    v17 = lpszVolumePathName;
    v31 = 1442;
    if ( GetVolumeNameForVolumeMountPointW(lpszVolumePathName, lpszVolumeName, v40[1] + 1) )
    {
      v30 = 0;
      v31 = 1444;
      CBsString::BoundUpdateLength((CBsString *)&lpszVolumeName, v16);
      v30 = CBsString::ExtendBuffer((CBsString *)&v37, 0x104u);
      v6 = 1447;
      if ( v30 < 0 )
        goto LABEL_62;
      v20 = v38[1];
      v31 = 1447;
      if ( GetVolumeNameForVolumeMountPointW(lpszVolumeName, v37, v38[1] + 1) )
      {
        v30 = 0;
        v31 = 1449;
        CBsString::BoundUpdateLength((CBsString *)&v37, v20);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000000) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, v37);
        if ( this )
        {
          v30 = CBsString::Set(this, v37);
          v6 = 1459;
          if ( v30 < 0 )
            goto LABEL_62;
          v31 = 1459;
        }
        if ( a3 )
          CBsString::Transfer((CBsString *)v41, a3);
      }
      else
      {
        v22 = GetLastFailureAsHRESULT(v21);
        v30 = v22;
        v32 = 1449;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
            (unsigned int)"::GetVolumeNameForVolumeMountPointW( strTwice, strVolume.GetBuffer(), strVolume.GetAllocLength() + 1 )",
            (__int64)v17,
            v22);
      }
    }
    else
    {
      v19 = GetLastFailureAsHRESULT(v18);
      v30 = v19;
      v32 = 1444;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"::GetVolumeNameForVolumeMountPointW( strMountPoint, strTwice.GetBuffer(), strTwice.GetAllocLength() + 1 )",
          (__int64)v17,
          v19);
    }
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
    v30 = LastFailureAsHRESULT;
    v32 = 1390;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v25 = 38;
LABEL_59:
      WPP_SF_sSd(
        v24[2],
        v25,
        (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
        (unsigned int)"dwPathLength != 0",
        (__int64)v7,
        LastFailureAsHRESULT);
    }
  }
LABEL_63:
  v26 = v30;
  CBsString::_Release(&v37);
  CBsString::_Release(&lpszVolumeName);
  CBsString::_Release(v41);
  CBsString::_Release(&lpszVolumePathName);
  CBsString::_Release(&lpBuffer);
  CBsString::_Release((unsigned __int16 **)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v30, v27, v28);
  return v26;
}

```

## disassembly

```asm
0x180027eac  push    rbp
0x180027eae  push    rbx
0x180027eaf  push    rsi
0x180027eb0  push    rdi
0x180027eb1  push    r12
0x180027eb3  push    r13
0x180027eb5  push    r14
0x180027eb7  push    r15
0x180027eb9  lea     rbp, [rsp-1Fh]
0x180027ebe  sub     rsp, 0D8h
0x180027ec5  mov     r14, r8
0x180027ec8  mov     r15, rdx
0x180027ecb  mov     rbx, rcx
0x180027ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ed5  lea     r13, WPP_GLOBAL_Control
0x180027edc  cmp     rcx, r13
0x180027edf  jz      short loc_180027F05
0x180027ee1  test    dword ptr [rcx+1Ch], 20000000h
0x180027ee8  jz      short loc_180027F05
0x180027eea  mov     rcx, [rcx+10h]
0x180027eee  mov     edx, 24h ; '$'
0x180027ef3  mov     [rsp+110h+var_E8], r8
0x180027ef8  mov     r9, rbx
0x180027efb  mov     [rsp+110h+var_F0], r15
0x180027f00  call    WPP_SF_Sqq
0x180027f05  mov     r9d, 1; unsigned __int16
0x180027f0b  lea     rdx, aSxcrackpath; "SxCrackPath"
0x180027f12  mov     r8d, 559h; unsigned __int16
0x180027f18  lea     rcx, [rsp+110h+var_E0]; this
0x180027f1d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180027f22  lea     rax, FileName
0x180027f29  xor     r12d, r12d
0x180027f2c  mov     [rbp+57h+lpFileName], rax
0x180027f30  mov     [rbp+57h+lpBuffer], rax
0x180027f34  mov     [rbp+57h+lpszVolumePathName], rax
0x180027f38  mov     [rbp+57h+var_68], rax
0x180027f3c  mov     [rbp+57h+lpszVolumeName], rax
0x180027f40  mov     [rbp+57h+var_88], rax
0x180027f44  mov     eax, 564h
0x180027f49  mov     [rbp+57h+var_50], r12
0x180027f4d  mov     qword ptr [rbp+57h+var_90], r12
0x180027f51  mov     qword ptr [rbp+57h+var_A0], r12
0x180027f55  mov     [rbp+57h+var_60], r12
0x180027f59  mov     qword ptr [rbp+57h+var_70], r12
0x180027f5d  mov     qword ptr [rbp+57h+var_80], r12
0x180027f61  test    rbx, rbx
0x180027f64  jz      loc_18002842D
0x180027f6a  mov     rdx, rbx; lpSrc
0x180027f6d  mov     [rsp+110h+var_E0], r12d
0x180027f72  lea     rcx, [rbp+57h+lpFileName]; this
0x180027f76  mov     [rsp+110h+var_DC], ax
0x180027f7b  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x180027f80  mov     [rsp+110h+var_E0], eax
0x180027f84  test    eax, eax
0x180027f86  mov     eax, 566h
0x180027f8b  js      loc_180028435
0x180027f91  mov     [rsp+110h+var_DC], ax
0x180027f96  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f9d  mov     rsi, [rbp+57h+lpFileName]
0x180027fa1  cmp     rcx, r13
0x180027fa4  jz      short loc_180027FC7
0x180027fa6  test    dword ptr [rcx+1Ch], 1000000h
0x180027fad  jz      short loc_180027FC7
0x180027faf  mov     rcx, [rcx+10h]
0x180027fb3  lea     edx, [r12+25h]
0x180027fb8  mov     r9, rsi
0x180027fbb  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180027fc2  call    WPP_SF_S
0x180027fc7  xor     r9d, r9d; lpFilePart
0x180027fca  xor     r8d, r8d; lpBuffer
0x180027fcd  xor     edx, edx; nBufferLength
0x180027fcf  mov     rcx, rsi; lpFileName
0x180027fd2  call    cs:__imp_GetFullPathNameW
0x180027fd8  mov     edi, eax
0x180027fda  test    eax, eax
0x180027fdc  jz      loc_1800283DE
0x180027fe2  mov     ecx, 56Eh
0x180027fe7  mov     [rsp+110h+var_E0], r12d
0x180027fec  mov     [rsp+110h+var_DC], cx
0x180027ff1  lea     ebx, [rcx+3]
0x180027ff4  lea     edx, [rdi-1]; unsigned int
0x180027ff7  lea     rcx, [rbp+57h+lpBuffer]; this
0x180027ffb  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180028000  mov     [rsp+110h+var_E0], eax
0x180028004  test    eax, eax
0x180028006  js      loc_18002814C
0x18002800c  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x180028010  xor     r9d, r9d; lpFilePart
0x180028013  mov     [rsp+110h+var_DC], bx
0x180028018  mov     rcx, rsi; lpFileName
0x18002801b  mov     ebx, [rbp+57h+var_90+4]
0x18002801e  lea     edx, [rbx+1]; nBufferLength
0x180028021  call    cs:__imp_GetFullPathNameW
0x180028027  mov     edx, ebx; unsigned int
0x180028029  lea     rcx, [rbp+57h+lpBuffer]; this
0x18002802d  mov     edi, eax
0x18002802f  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180028034  test    edi, edi
0x180028036  jz      loc_1800283AF
0x18002803c  mov     eax, 574h
0x180028041  mov     [rsp+110h+var_E0], r12d
0x180028046  mov     [rsp+110h+var_DC], ax
0x18002804b  lea     ebx, [rax-3]
0x18002804e  cmp     edi, [rbp+57h+var_90+4]
0x180028051  ja      short loc_180027FF4
0x180028053  mov     edx, edi; unsigned int
0x180028055  lea     rcx, [rbp+57h+lpBuffer]; this
0x180028059  call    ?SetLength@CBsString@@QEAAJK@Z; CBsString::SetLength(ulong)
0x18002805e  mov     [rsp+110h+var_E0], eax
0x180028062  test    eax, eax
0x180028064  lea     eax, [rbx+6]
0x180028067  js      loc_180028435
0x18002806d  mov     [rsp+110h+var_DC], ax
0x180028072  mov     rcx, cs:WPP_GLOBAL_Control
0x180028079  mov     rsi, [rbp+57h+lpBuffer]
0x18002807d  cmp     rcx, r13
0x180028080  jz      short loc_1800280A7
0x180028082  test    dword ptr [rcx+1Ch], 1000000h
0x180028089  jz      short loc_1800280A7
0x18002808b  mov     rcx, [rcx+10h]
0x18002808f  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180028096  mov     edx, 28h ; '('
0x18002809b  mov     dword ptr [rsp+110h+var_F0], edi
0x18002809f  mov     r9, rsi
0x1800280a2  call    WPP_SF_Sd
0x1800280a7  mov     edx, edi; unsigned int
0x1800280a9  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x1800280ad  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800280b2  mov     [rsp+110h+var_E0], eax
0x1800280b6  test    eax, eax
0x1800280b8  mov     eax, 580h
0x1800280bd  js      loc_180028435
0x1800280c3  mov     rdx, [rbp+57h+lpszVolumePathName]; lpszVolumePathName
0x1800280c7  lea     r8d, [rdi+1]; cchBufferLength
0x1800280cb  mov     rcx, rsi; lpszFileName
0x1800280ce  mov     [rsp+110h+var_DC], ax
0x1800280d3  mov     ebx, 588h
0x1800280d8  call    cs:__imp_GetVolumePathNameW
0x1800280de  mov     edx, [rbp+57h+var_A0+4]; unsigned int
0x1800280e1  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x1800280e5  test    eax, eax
0x1800280e7  jnz     short loc_180028156
0x1800280e9  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800280ee  call    cs:__imp_GetLastError
0x1800280f4  cmp     eax, 0CEh
0x1800280f9  jnz     short loc_180028143
0x1800280fb  mov     [rsp+110h+var_DC], bx
0x180028100  mov     eax, 58Ah
0x180028105  lea     ebx, [rdi+rdi]
0x180028108  cmp     ebx, edi
0x18002810a  jbe     short loc_180028136
0x18002810c  mov     edx, ebx; unsigned int
0x18002810e  mov     [rsp+110h+var_E0], r12d
0x180028113  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x180028117  mov     [rsp+110h+var_DC], ax
0x18002811c  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x180028121  mov     [rsp+110h+var_E0], eax
0x180028125  test    eax, eax
0x180028127  mov     eax, 58Bh
0x18002812c  js      loc_180028435
0x180028132  mov     edi, ebx
0x180028134  jmp     short loc_1800280C3
0x180028136  mov     [rsp+110h+var_E0], 80070216h
0x18002813e  jmp     loc_180028435
0x180028143  call    GetLastFailureAsHRESULT
0x180028148  mov     [rsp+110h+var_E0], eax
0x18002814c  mov     [rsp+110h+var_DA], bx
0x180028151  jmp     loc_18002843A
0x180028156  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x18002815b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028162  cmp     rcx, r13
0x180028165  jz      short loc_180028189
0x180028167  test    dword ptr [rcx+1Ch], 1000000h
0x18002816e  jz      short loc_180028189
0x180028170  mov     r9, [rbp+57h+lpszVolumePathName]
0x180028174  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18002817b  mov     rcx, [rcx+10h]
0x18002817f  mov     edx, 29h ; ')'
0x180028184  call    WPP_SF_S
0x180028189  mov     eax, [rbp+57h+var_A0]
0x18002818c  lea     rcx, [rbp+57h+var_68]; this
0x180028190  lea     rdx, [rsi+rax*2]; unsigned __int16 *
0x180028194  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180028199  mov     [rsp+110h+var_E0], eax
0x18002819d  test    eax, eax
0x18002819f  mov     eax, 596h
0x1800281a4  js      loc_180028435
0x1800281aa  mov     [rsp+110h+var_DC], ax
0x1800281af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281b6  cmp     rcx, r13
0x1800281b9  jz      short loc_1800281DD
0x1800281bb  test    dword ptr [rcx+1Ch], 1000000h
0x1800281c2  jz      short loc_1800281DD
0x1800281c4  mov     r9, [rbp+57h+var_68]
0x1800281c8  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x1800281cf  mov     rcx, [rcx+10h]
0x1800281d3  mov     edx, 2Ah ; '*'
0x1800281d8  call    WPP_SF_S
0x1800281dd  lea     rcx, [rbp+57h+lpszVolumePathName]; this
0x1800281e1  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x1800281e6  mov     [rsp+110h+var_E0], eax
0x1800281ea  test    eax, eax
0x1800281ec  mov     eax, 5A1h
0x1800281f1  js      loc_180028435
0x1800281f7  mov     esi, 104h
0x1800281fc  mov     [rsp+110h+var_DC], ax
0x180028201  mov     edx, esi; unsigned int
0x180028203  lea     rcx, [rbp+57h+lpszVolumeName]; this
0x180028207  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x18002820c  mov     [rsp+110h+var_E0], eax
0x180028210  test    eax, eax
0x180028212  mov     eax, 5A2h
0x180028217  js      loc_180028435
0x18002821d  mov     edi, [rbp+57h+var_70+4]
0x180028220  mov     rbx, [rbp+57h+lpszVolumePathName]
0x180028224  mov     rdx, [rbp+57h+lpszVolumeName]; lpszVolumeName
0x180028228  mov     rcx, rbx; lpszVolumeMountPoint
0x18002822b  mov     [rsp+110h+var_DC], ax
0x180028230  lea     r8d, [rdi+1]; cchBufferLength
0x180028234  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18002823a  test    eax, eax
0x18002823c  jnz     short loc_180028288
0x18002823e  call    GetLastFailureAsHRESULT
0x180028243  mov     ecx, 5A4h
0x180028248  mov     [rsp+110h+var_E0], eax
0x18002824c  mov     [rsp+110h+var_DA], cx
0x180028251  mov     rcx, cs:WPP_GLOBAL_Control
0x180028258  cmp     rcx, r13
0x18002825b  jz      loc_18002843A
0x180028261  test    dword ptr [rcx+1Ch], 2000000h
0x180028268  jz      loc_18002843A
0x18002826e  mov     dword ptr [rsp+110h+var_E8], eax
0x180028272  lea     r9, aGetvolumenamef_2; "::GetVolumeNameForVolumeMountPointW( st"...
0x180028279  mov     [rsp+110h+var_F0], rbx
0x18002827e  mov     edx, 2Bh ; '+'
0x180028283  jmp     loc_18002841B
0x180028288  mov     ecx, 5A4h
0x18002828d  mov     [rsp+110h+var_E0], r12d
0x180028292  mov     [rsp+110h+var_DC], cx
0x180028297  mov     edx, edi; unsigned int
0x180028299  lea     rcx, [rbp+57h+lpszVolumeName]; this
0x18002829d  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x1800282a2  mov     edx, esi; unsigned int
0x1800282a4  lea     rcx, [rbp+57h+var_88]; this
0x1800282a8  call    ?ExtendBuffer@CBsString@@QEAAJK@Z; CBsString::ExtendBuffer(ulong)
0x1800282ad  mov     [rsp+110h+var_E0], eax
0x1800282b1  test    eax, eax
0x1800282b3  mov     eax, 5A7h
0x1800282b8  js      loc_180028435
0x1800282be  mov     edi, [rbp+57h+var_80+4]
0x1800282c1  mov     rdx, [rbp+57h+var_88]; lpszVolumeName
0x1800282c5  mov     rcx, [rbp+57h+lpszVolumeName]; lpszVolumeMountPoint
0x1800282c9  mov     [rsp+110h+var_DC], ax
0x1800282ce  lea     r8d, [rdi+1]; cchBufferLength
0x1800282d2  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800282d8  test    eax, eax
0x1800282da  jnz     short loc_180028326
0x1800282dc  call    GetLastFailureAsHRESULT
0x1800282e1  mov     ecx, 5A9h
0x1800282e6  mov     [rsp+110h+var_E0], eax
0x1800282ea  mov     [rsp+110h+var_DA], cx
0x1800282ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282f6  cmp     rcx, r13
0x1800282f9  jz      loc_18002843A
0x1800282ff  test    dword ptr [rcx+1Ch], 2000000h
0x180028306  jz      loc_18002843A
0x18002830c  mov     dword ptr [rsp+110h+var_E8], eax
0x180028310  lea     r9, aGetvolumenamef_1; "::GetVolumeNameForVolumeMountPointW( st"...
0x180028317  mov     [rsp+110h+var_F0], rbx
0x18002831c  mov     edx, 2Ch ; ','
0x180028321  jmp     loc_18002841B
0x180028326  mov     ecx, 5A9h
0x18002832b  mov     [rsp+110h+var_E0], r12d
0x180028330  mov     [rsp+110h+var_DC], cx
0x180028335  mov     edx, edi; unsigned int
0x180028337  lea     rcx, [rbp+57h+var_88]; this
0x18002833b  call    ?BoundUpdateLength@CBsString@@QEAAXK@Z; CBsString::BoundUpdateLength(ulong)
0x180028340  mov     rcx, cs:WPP_GLOBAL_Control
0x180028347  cmp     rcx, r13
0x18002834a  jz      short loc_18002836E
0x18002834c  test    dword ptr [rcx+1Ch], 1000000h
0x180028353  jz      short loc_18002836E
0x180028355  mov     r9, [rbp+57h+var_88]
0x180028359  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180028360  mov     rcx, [rcx+10h]
0x180028364  mov     edx, 2Dh ; '-'
0x180028369  call    WPP_SF_S
0x18002836e  test    r15, r15
0x180028371  jz      short loc_180028395
0x180028373  mov     rdx, [rbp+57h+var_88]; unsigned __int16 *
0x180028377  mov     rcx, r15; this
0x18002837a  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002837f  mov     [rsp+110h+var_E0], eax
0x180028383  test    eax, eax
0x180028385  mov     eax, 5B3h
0x18002838a  js      loc_180028435
0x180028390  mov     [rsp+110h+var_DC], ax
0x180028395  test    r14, r14
0x180028398  jz      loc_18002843A
0x18002839e  mov     rdx, r14; struct CBsString *
  ... truncated ...
```
