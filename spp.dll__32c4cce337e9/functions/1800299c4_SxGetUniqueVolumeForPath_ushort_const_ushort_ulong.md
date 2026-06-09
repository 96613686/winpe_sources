# SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)

- ea: `0x1800299c4`
- end: `0x180029cd7`
- name: `?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z`
- size: `787`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPWSTR lpszVolumeName, DWORD cchBufferLength)`
- caller_count: `7`
- callee_count: `11`
- tags: `reparse_path`

## callers

- `0x180007cb0`
- `0x18000e7b0`
- `0x180010514`
- `0x180019bb4`
- `0x18001ac40`
- `0x18002849c`
- `0x18002a778`

## callees

- `0x180020908`
- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x1800299c4`
- `0x18002d6e8`
- `0x18003532c`
- `0x1800353c4`
- `0x180035b00`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x180029b33`
- `KERNEL32!GetVolumePathNameW` at `0x180029b33`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180029bbd`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180029c36`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180029bbd`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180029c36`

## string_xrefs

- `0x180029a33`: `SxGetUniqueVolumeForPath`
- `0x180029b73`: `::GetVolumePathName( strPath, STRING_CCH_PARAM( wszRootPath ) )`
- `0x180029c06`: `::GetVolumeNameForVolumeMountPoint( wszRootPath, STRING_CCH_PARAM( wszVolume ) )`
- `0x180029c7a`: `::GetVolumeNameForVolumeMountPoint( wszVolume, pwszUnique, cchUnique )`

## pseudocode

```c
__int64 __fastcall SxGetUniqueVolumeForPath(const unsigned __int16 *a1, LPWSTR lpszVolumeName, DWORD cchBufferLength)
{
  __int16 v6; // ax
  int LastFailureAsHRESULT; // ebx
  unsigned __int16 v8; // dx
  __int16 v9; // ax
  LPCWSTR v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v18; // [rsp+34h] [rbp-CCh]
  __int16 v19; // [rsp+36h] [rbp-CAh]
  LPCWSTR lpszFileName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h]
  WCHAR szVolumePathName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szVolumeName[264]; // [rsp+290h] [rbp+190h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "SxGetUniqueVolumeForPath", 510, 1);
  v21 = 0;
  lpszFileName = &FileName;
  memset_0(szVolumePathName, 0, 0x20Au);
  memset_0(szVolumeName, 0, 0x20Au);
  v6 = 516;
  if ( !a1 )
    goto LABEL_5;
  v18 = 516;
  if ( !lpszVolumeName )
  {
    v6 = 517;
LABEL_5:
    LastFailureAsHRESULT = -2147024809;
    v19 = v6;
LABEL_26:
    v17 = LastFailureAsHRESULT;
    goto LABEL_27;
  }
  v17 = 0;
  v18 = 518;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)&lpszFileName, a1);
  v17 = LastFailureAsHRESULT;
  v9 = 520;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_9;
  v18 = 520;
  v6 = 521;
  if ( !(_DWORD)v21 )
    goto LABEL_5;
  v17 = 0;
  v18 = 521;
  LastFailureAsHRESULT = CBsString::Trailing((CBsString *)&lpszFileName, v8);
  v17 = LastFailureAsHRESULT;
  v9 = 523;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_9:
    v19 = v9;
  }
  else
  {
    v10 = lpszFileName;
    v18 = 523;
    if ( GetVolumePathNameW(lpszFileName, szVolumePathName, 0x105u) )
    {
      v17 = 0;
      v18 = 529;
      if ( GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x105u) )
      {
        v17 = 0;
        v18 = 536;
        if ( GetVolumeNameForVolumeMountPointW(szVolumeName, lpszVolumeName, cchBufferLength) )
        {
          LastFailureAsHRESULT = 0;
          v18 = 542;
          goto LABEL_26;
        }
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13);
        v17 = LastFailureAsHRESULT;
        v19 = 542;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
            (unsigned int)"::GetVolumeNameForVolumeMountPoint( wszVolume, pwszUnique, cchUnique )",
            (__int64)szVolumeName,
            LastFailureAsHRESULT);
          goto LABEL_16;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
        v17 = LastFailureAsHRESULT;
        v19 = 536;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
            (unsigned int)"::GetVolumeNameForVolumeMountPoint( wszRootPath, STRING_CCH_PARAM( wszVolume ) )",
            (__int64)szVolumePathName,
            LastFailureAsHRESULT);
          goto LABEL_16;
        }
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
      v17 = LastFailureAsHRESULT;
      v19 = 529;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"::GetVolumePathName( strPath, STRING_CCH_PARAM( wszRootPath ) )",
          (__int64)v10,
          LastFailureAsHRESULT);
LABEL_16:
        LastFailureAsHRESULT = v17;
      }
    }
  }
LABEL_27:
  CBsString::_Release((unsigned __int16 **)&lpszFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17, v14, v15);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800299c4  mov     [rsp-8+arg_18], rbx
0x1800299c9  push    rbp
0x1800299ca  push    rsi
0x1800299cb  push    rdi
0x1800299cc  push    r12
0x1800299ce  push    r14
0x1800299d0  lea     rbp, [rsp-3B0h]
0x1800299d8  sub     rsp, 4B0h
0x1800299df  mov     rax, cs:__security_cookie
0x1800299e6  xor     rax, rsp
0x1800299e9  mov     [rbp+3D0h+var_30], rax
0x1800299f0  mov     r14d, r8d
0x1800299f3  mov     rsi, rdx
0x1800299f6  mov     rbx, rcx
0x1800299f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a00  lea     r12, WPP_GLOBAL_Control
0x180029a07  cmp     rcx, r12
0x180029a0a  jz      short loc_180029A2D
0x180029a0c  test    dword ptr [rcx+1Ch], 20000000h
0x180029a13  jz      short loc_180029A2D
0x180029a15  mov     rcx, [rcx+10h]
0x180029a19  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180029a20  mov     edx, 12h
0x180029a25  mov     r9, rbx
0x180029a28  call    WPP_SF_S
0x180029a2d  mov     r9d, 1; unsigned __int16
0x180029a33  lea     rdx, aSxgetuniquevol; "SxGetUniqueVolumeForPath"
0x180029a3a  mov     r8d, 1FEh; unsigned __int16
0x180029a40  lea     rcx, [rsp+4D0h+var_4A0]; this
0x180029a45  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180029a4a  lea     rax, FileName
0x180029a51  mov     [rsp+4D0h+var_460], 0
0x180029a5a  mov     edi, 20Ah
0x180029a5f  mov     [rsp+4D0h+lpszFileName], rax
0x180029a64  mov     r8d, edi; Size
0x180029a67  lea     rcx, [rbp+3D0h+szVolumePathName]; void *
0x180029a6b  xor     edx, edx; Val
0x180029a6d  call    memset_0
0x180029a72  mov     r8d, edi; Size
0x180029a75  lea     rcx, [rbp+3D0h+szVolumeName]; void *
0x180029a7c  xor     edx, edx; Val
0x180029a7e  call    memset_0
0x180029a83  lea     eax, [rdi-6]
0x180029a86  test    rbx, rbx
0x180029a89  jnz     short loc_180029A9A
0x180029a8b  mov     ebx, 80070057h
0x180029a90  mov     [rsp+4D0h+var_49A], ax
0x180029a95  jmp     loc_180029C97
0x180029a9a  mov     [rsp+4D0h+var_49C], ax
0x180029a9f  test    rsi, rsi
0x180029aa2  jnz     short loc_180029AAB
0x180029aa4  mov     eax, 205h
0x180029aa9  jmp     short loc_180029A8B
0x180029aab  mov     eax, 206h
0x180029ab0  mov     [rsp+4D0h+var_4A0], 0
0x180029ab8  mov     rdx, rbx; unsigned __int16 *
0x180029abb  mov     [rsp+4D0h+var_49C], ax
0x180029ac0  lea     rcx, [rsp+4D0h+lpszFileName]; this
0x180029ac5  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180029aca  mov     ebx, eax
0x180029acc  mov     [rsp+4D0h+var_4A0], eax
0x180029ad0  test    eax, eax
0x180029ad2  mov     eax, 208h
0x180029ad7  jns     short loc_180029AE3
0x180029ad9  mov     [rsp+4D0h+var_49A], ax
0x180029ade  jmp     loc_180029C9B
0x180029ae3  cmp     dword ptr [rsp+4D0h+var_460], 0
0x180029ae8  mov     [rsp+4D0h+var_49C], ax
0x180029aed  mov     eax, 209h
0x180029af2  jz      short loc_180029A8B
0x180029af4  lea     rcx, [rsp+4D0h+lpszFileName]; this
0x180029af9  mov     [rsp+4D0h+var_4A0], 0
0x180029b01  mov     [rsp+4D0h+var_49C], ax
0x180029b06  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180029b0b  mov     ebx, eax
0x180029b0d  mov     [rsp+4D0h+var_4A0], eax
0x180029b11  test    eax, eax
0x180029b13  mov     eax, 20Bh
0x180029b18  js      short loc_180029AD9
0x180029b1a  mov     rdi, [rsp+4D0h+lpszFileName]
0x180029b1f  lea     rdx, [rbp+3D0h+szVolumePathName]; lpszVolumePathName
0x180029b23  mov     ebx, 105h
0x180029b28  mov     [rsp+4D0h+var_49C], ax
0x180029b2d  mov     r8d, ebx; cchBufferLength
0x180029b30  mov     rcx, rdi; lpszFileName
0x180029b33  call    cs:__imp_GetVolumePathNameW
0x180029b39  test    eax, eax
0x180029b3b  jnz     short loc_180029B9D
0x180029b3d  call    GetLastFailureAsHRESULT
0x180029b42  mov     ebx, eax
0x180029b44  mov     [rsp+4D0h+var_4A0], eax
0x180029b48  mov     eax, 211h
0x180029b4d  mov     [rsp+4D0h+var_49A], ax
0x180029b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b59  cmp     rcx, r12
0x180029b5c  jz      loc_180029C9B
0x180029b62  test    dword ptr [rcx+1Ch], 2000000h
0x180029b69  jz      loc_180029C9B
0x180029b6f  mov     [rsp+4D0h+var_4A8], ebx
0x180029b73  lea     r9, aGetvolumepathn; "::GetVolumePathName( strPath, STRING_CC"...
0x180029b7a  mov     [rsp+4D0h+var_4B0], rdi
0x180029b7f  mov     edx, 13h
0x180029b84  mov     rcx, [rcx+10h]
0x180029b88  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180029b8f  call    WPP_SF_sSd
0x180029b94  mov     ebx, [rsp+4D0h+var_4A0]
0x180029b98  jmp     loc_180029C9B
0x180029b9d  mov     eax, 211h
0x180029ba2  mov     [rsp+4D0h+var_4A0], 0
0x180029baa  mov     r8d, ebx; cchBufferLength
0x180029bad  mov     [rsp+4D0h+var_49C], ax
0x180029bb2  lea     rdx, [rbp+3D0h+szVolumeName]; lpszVolumeName
0x180029bb9  lea     rcx, [rbp+3D0h+szVolumePathName]; lpszVolumeMountPoint
0x180029bbd  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180029bc3  test    eax, eax
0x180029bc5  jnz     short loc_180029C17
0x180029bc7  call    GetLastFailureAsHRESULT
0x180029bcc  mov     ebx, eax
0x180029bce  mov     [rsp+4D0h+var_4A0], eax
0x180029bd2  mov     eax, 218h
0x180029bd7  mov     [rsp+4D0h+var_49A], ax
0x180029bdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180029be3  cmp     rcx, r12
0x180029be6  jz      loc_180029C9B
0x180029bec  test    dword ptr [rcx+1Ch], 2000000h
0x180029bf3  jz      loc_180029C9B
0x180029bf9  lea     rax, [rbp+3D0h+szVolumePathName]
0x180029bfd  mov     [rsp+4D0h+var_4A8], ebx
0x180029c01  mov     [rsp+4D0h+var_4B0], rax
0x180029c06  lea     r9, aGetvolumenamef_0; "::GetVolumeNameForVolumeMountPoint( wsz"...
0x180029c0d  mov     edx, 14h
0x180029c12  jmp     loc_180029B84
0x180029c17  mov     eax, 218h
0x180029c1c  mov     [rsp+4D0h+var_4A0], 0
0x180029c24  mov     r8d, r14d; cchBufferLength
0x180029c27  mov     [rsp+4D0h+var_49C], ax
0x180029c2c  mov     rdx, rsi; lpszVolumeName
0x180029c2f  lea     rcx, [rbp+3D0h+szVolumeName]; lpszVolumeMountPoint
0x180029c36  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180029c3c  test    eax, eax
0x180029c3e  jnz     short loc_180029C8B
0x180029c40  call    GetLastFailureAsHRESULT
0x180029c45  mov     ebx, eax
0x180029c47  mov     [rsp+4D0h+var_4A0], eax
0x180029c4b  mov     eax, 21Eh
0x180029c50  mov     [rsp+4D0h+var_49A], ax
0x180029c55  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c5c  cmp     rcx, r12
0x180029c5f  jz      short loc_180029C9B
0x180029c61  test    dword ptr [rcx+1Ch], 2000000h
0x180029c68  jz      short loc_180029C9B
0x180029c6a  lea     rax, [rbp+3D0h+szVolumeName]
0x180029c71  mov     [rsp+4D0h+var_4A8], ebx
0x180029c75  mov     [rsp+4D0h+var_4B0], rax
0x180029c7a  lea     r9, aGetvolumenamef; "::GetVolumeNameForVolumeMountPoint( wsz"...
0x180029c81  mov     edx, 15h
0x180029c86  jmp     loc_180029B84
0x180029c8b  mov     eax, 21Eh
0x180029c90  xor     ebx, ebx
0x180029c92  mov     [rsp+4D0h+var_49C], ax
0x180029c97  mov     [rsp+4D0h+var_4A0], ebx
0x180029c9b  lea     rcx, [rsp+4D0h+lpszFileName]; this
0x180029ca0  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180029ca5  lea     rcx, [rsp+4D0h+var_4A0]; this
0x180029caa  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180029caf  mov     eax, ebx
0x180029cb1  mov     rcx, [rbp+3D0h+var_30]
0x180029cb8  xor     rcx, rsp; StackCookie
0x180029cbb  call    __security_check_cookie
0x180029cc0  mov     rbx, [rsp+4D0h+arg_18]
0x180029cc8  add     rsp, 4B0h
0x180029ccf  pop     r14
0x180029cd1  pop     r12
0x180029cd3  pop     rdi
0x180029cd4  pop     rsi
0x180029cd5  pop     rbp
0x180029cd6  retn
```
