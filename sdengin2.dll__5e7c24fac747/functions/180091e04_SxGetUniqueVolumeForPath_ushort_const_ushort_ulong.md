# SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)

- ea: `0x180091e04`
- end: `0x18009211c`
- name: `?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z`
- size: `792`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPWSTR lpszVolumeName, unsigned int)`
- caller_count: `4`
- callee_count: `11`
- tags: `reparse_path`

## callers

- `0x18000f2b4`
- `0x180016f28`
- `0x18008b390`
- `0x180090c30`

## callees

- `0x180008240`
- `0x1800145f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x180091e04`
- `0x18009a24c`
- `0x18009a3ac`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x180091f77`
- `KERNEL32!GetVolumePathNameW` at `0x180091f77`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180092001`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18009207a`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180092001`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18009207a`

## string_xrefs

- `0x180091e72`: `SxGetUniqueVolumeForPath`
- `0x180091fb7`: `::GetVolumePathName( strPath, STRING_CCH_PARAM( wszRootPath ) )`
- `0x18009204a`: `::GetVolumeNameForVolumeMountPoint( wszRootPath, STRING_CCH_PARAM( wszVolume ) )`
- `0x1800920be`: `::GetVolumeNameForVolumeMountPoint( wszVolume, pwszUnique, cchUnique )`

## pseudocode

```c
__int64 __fastcall SxGetUniqueVolumeForPath(const unsigned __int16 *a1, LPWSTR lpszVolumeName)
{
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  __int16 v6; // ax
  LPCWSTR v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v13; // [rsp+34h] [rbp-CCh]
  __int16 v14; // [rsp+36h] [rbp-CAh]
  LPCWSTR lpszFileName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v16; // [rsp+70h] [rbp-90h]
  WCHAR szVolumePathName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szVolumeName[264]; // [rsp+290h] [rbp+190h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxGetUniqueVolumeForPath", 510, 1);
  v16 = 0;
  lpszFileName = (LPCWSTR)qword_1800E8530;
  memset_0(szVolumePathName, 0, 0x20Au);
  memset_0(szVolumeName, 0, 0x20Au);
  v4 = 516;
  if ( !a1 )
    goto LABEL_5;
  v13 = 516;
  if ( !lpszVolumeName )
  {
    v4 = 517;
LABEL_5:
    LastFailureAsHRESULT = -2147024809;
    v14 = v4;
LABEL_26:
    v12 = LastFailureAsHRESULT;
    goto LABEL_27;
  }
  v12 = 0;
  v13 = 518;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)&lpszFileName, a1);
  v12 = LastFailureAsHRESULT;
  v6 = 520;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_9;
  v13 = 520;
  v4 = 521;
  if ( !(_DWORD)v16 )
    goto LABEL_5;
  v12 = 0;
  v13 = 521;
  LastFailureAsHRESULT = CBsString::Trailing((CBsString *)&lpszFileName, 0x5Cu);
  v12 = LastFailureAsHRESULT;
  v6 = 523;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_9:
    v14 = v6;
  }
  else
  {
    v7 = lpszFileName;
    v13 = 523;
    if ( GetVolumePathNameW(lpszFileName, szVolumePathName, 0x105u) )
    {
      v12 = 0;
      v13 = 529;
      if ( GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x105u) )
      {
        v12 = 0;
        v13 = 536;
        if ( GetVolumeNameForVolumeMountPointW(szVolumeName, lpszVolumeName, 0x105u) )
        {
          LastFailureAsHRESULT = 0;
          v13 = 542;
          goto LABEL_26;
        }
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
        v12 = LastFailureAsHRESULT;
        v14 = 542;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
            (unsigned int)"::GetVolumeNameForVolumeMountPoint( wszVolume, pwszUnique, cchUnique )",
            (__int64)szVolumeName,
            LastFailureAsHRESULT);
          goto LABEL_16;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
        v12 = LastFailureAsHRESULT;
        v14 = 536;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          WPP_SF_sSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
            (unsigned int)"::GetVolumeNameForVolumeMountPoint( wszRootPath, STRING_CCH_PARAM( wszVolume ) )",
            (__int64)szVolumePathName,
            LastFailureAsHRESULT);
          goto LABEL_16;
        }
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
      v12 = LastFailureAsHRESULT;
      v14 = 529;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"::GetVolumePathName( strPath, STRING_CCH_PARAM( wszRootPath ) )",
          (__int64)v7,
          LastFailureAsHRESULT);
LABEL_16:
        LastFailureAsHRESULT = v12;
      }
    }
  }
LABEL_27:
  CBsString::_Release((CBsString *)&lpszFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v12);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180091e04  mov     [rsp-8+arg_10], rbx
0x180091e09  mov     [rsp-8+arg_18], rsi
0x180091e0e  push    rbp
0x180091e0f  push    rdi
0x180091e10  push    r15
0x180091e12  lea     rbp, [rsp-3B0h]
0x180091e1a  sub     rsp, 4B0h
0x180091e21  mov     rax, cs:__security_cookie
0x180091e28  xor     rax, rsp
0x180091e2b  mov     [rbp+3C0h+var_20], rax
0x180091e32  mov     rsi, rdx
0x180091e35  mov     rbx, rcx
0x180091e38  mov     rcx, cs:WPP_GLOBAL_Control
0x180091e3f  lea     r15, WPP_GLOBAL_Control
0x180091e46  cmp     rcx, r15
0x180091e49  jz      short loc_180091E6C
0x180091e4b  test    dword ptr [rcx+1Ch], 20000000h
0x180091e52  jz      short loc_180091E6C
0x180091e54  mov     rcx, [rcx+10h]
0x180091e58  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180091e5f  mov     edx, 12h
0x180091e64  mov     r9, rbx
0x180091e67  call    WPP_SF_S
0x180091e6c  mov     r9d, 1; unsigned __int16
0x180091e72  lea     rdx, aSxgetuniquevol; "SxGetUniqueVolumeForPath"
0x180091e79  mov     r8d, 1FEh; unsigned __int16
0x180091e7f  lea     rcx, [rsp+4C0h+var_490]; this
0x180091e84  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180091e89  lea     rax, qword_1800E8530
0x180091e90  mov     [rsp+4C0h+var_450], 0
0x180091e99  mov     edi, 20Ah
0x180091e9e  mov     [rsp+4C0h+lpszFileName], rax
0x180091ea3  mov     r8d, edi; Size
0x180091ea6  lea     rcx, [rbp+3C0h+szVolumePathName]; void *
0x180091eaa  xor     edx, edx; Val
0x180091eac  call    memset_0
0x180091eb1  mov     r8d, edi; Size
0x180091eb4  lea     rcx, [rbp+3C0h+szVolumeName]; void *
0x180091ebb  xor     edx, edx; Val
0x180091ebd  call    memset_0
0x180091ec2  lea     eax, [rdi-6]
0x180091ec5  test    rbx, rbx
0x180091ec8  jnz     short loc_180091ED9
0x180091eca  mov     ebx, 80070057h
0x180091ecf  mov     [rsp+4C0h+var_48A], ax
0x180091ed4  jmp     loc_1800920DB
0x180091ed9  mov     [rsp+4C0h+var_48C], ax
0x180091ede  test    rsi, rsi
0x180091ee1  jnz     short loc_180091EEA
0x180091ee3  mov     eax, 205h
0x180091ee8  jmp     short loc_180091ECA
0x180091eea  mov     eax, 206h
0x180091eef  mov     [rsp+4C0h+var_490], 0
0x180091ef7  mov     rdx, rbx; unsigned __int16 *
0x180091efa  mov     [rsp+4C0h+var_48C], ax
0x180091eff  lea     rcx, [rsp+4C0h+lpszFileName]; this
0x180091f04  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180091f09  mov     ebx, eax
0x180091f0b  mov     [rsp+4C0h+var_490], eax
0x180091f0f  test    eax, eax
0x180091f11  mov     eax, 208h
0x180091f16  jns     short loc_180091F22
0x180091f18  mov     [rsp+4C0h+var_48A], ax
0x180091f1d  jmp     loc_1800920DF
0x180091f22  cmp     dword ptr [rsp+4C0h+var_450], 0
0x180091f27  mov     [rsp+4C0h+var_48C], ax
0x180091f2c  mov     eax, 209h
0x180091f31  jz      short loc_180091ECA
0x180091f33  mov     edx, 5Ch ; '\'; unsigned __int16
0x180091f38  mov     [rsp+4C0h+var_490], 0
0x180091f40  lea     rcx, [rsp+4C0h+lpszFileName]; this
0x180091f45  mov     [rsp+4C0h+var_48C], ax
0x180091f4a  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x180091f4f  mov     ebx, eax
0x180091f51  mov     [rsp+4C0h+var_490], eax
0x180091f55  test    eax, eax
0x180091f57  mov     eax, 20Bh
0x180091f5c  js      short loc_180091F18
0x180091f5e  mov     rdi, [rsp+4C0h+lpszFileName]
0x180091f63  lea     rdx, [rbp+3C0h+szVolumePathName]; lpszVolumePathName
0x180091f67  mov     ebx, 105h
0x180091f6c  mov     [rsp+4C0h+var_48C], ax
0x180091f71  mov     r8d, ebx; cchBufferLength
0x180091f74  mov     rcx, rdi; lpszFileName
0x180091f77  call    cs:__imp_GetVolumePathNameW
0x180091f7d  test    eax, eax
0x180091f7f  jnz     short loc_180091FE1
0x180091f81  call    GetLastFailureAsHRESULT
0x180091f86  mov     ebx, eax
0x180091f88  mov     [rsp+4C0h+var_490], eax
0x180091f8c  mov     eax, 211h
0x180091f91  mov     [rsp+4C0h+var_48A], ax
0x180091f96  mov     rcx, cs:WPP_GLOBAL_Control
0x180091f9d  cmp     rcx, r15
0x180091fa0  jz      loc_1800920DF
0x180091fa6  test    dword ptr [rcx+1Ch], 2000000h
0x180091fad  jz      loc_1800920DF
0x180091fb3  mov     [rsp+4C0h+var_498], ebx
0x180091fb7  lea     r9, aGetvolumepathn_0; "::GetVolumePathName( strPath, STRING_CC"...
0x180091fbe  mov     [rsp+4C0h+var_4A0], rdi
0x180091fc3  mov     edx, 13h
0x180091fc8  mov     rcx, [rcx+10h]
0x180091fcc  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180091fd3  call    WPP_SF_sSd
0x180091fd8  mov     ebx, [rsp+4C0h+var_490]
0x180091fdc  jmp     loc_1800920DF
0x180091fe1  mov     eax, 211h
0x180091fe6  mov     [rsp+4C0h+var_490], 0
0x180091fee  mov     r8d, ebx; cchBufferLength
0x180091ff1  mov     [rsp+4C0h+var_48C], ax
0x180091ff6  lea     rdx, [rbp+3C0h+szVolumeName]; lpszVolumeName
0x180091ffd  lea     rcx, [rbp+3C0h+szVolumePathName]; lpszVolumeMountPoint
0x180092001  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180092007  test    eax, eax
0x180092009  jnz     short loc_18009205B
0x18009200b  call    GetLastFailureAsHRESULT
0x180092010  mov     ebx, eax
0x180092012  mov     [rsp+4C0h+var_490], eax
0x180092016  mov     eax, 218h
0x18009201b  mov     [rsp+4C0h+var_48A], ax
0x180092020  mov     rcx, cs:WPP_GLOBAL_Control
0x180092027  cmp     rcx, r15
0x18009202a  jz      loc_1800920DF
0x180092030  test    dword ptr [rcx+1Ch], 2000000h
0x180092037  jz      loc_1800920DF
0x18009203d  lea     rax, [rbp+3C0h+szVolumePathName]
0x180092041  mov     [rsp+4C0h+var_498], ebx
0x180092045  mov     [rsp+4C0h+var_4A0], rax
0x18009204a  lea     r9, aGetvolumenamef_0; "::GetVolumeNameForVolumeMountPoint( wsz"...
0x180092051  mov     edx, 14h
0x180092056  jmp     loc_180091FC8
0x18009205b  mov     eax, 218h
0x180092060  mov     [rsp+4C0h+var_490], 0
0x180092068  mov     r8d, ebx; cchBufferLength
0x18009206b  mov     [rsp+4C0h+var_48C], ax
0x180092070  mov     rdx, rsi; lpszVolumeName
0x180092073  lea     rcx, [rbp+3C0h+szVolumeName]; lpszVolumeMountPoint
0x18009207a  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180092080  test    eax, eax
0x180092082  jnz     short loc_1800920CF
0x180092084  call    GetLastFailureAsHRESULT
0x180092089  mov     ebx, eax
0x18009208b  mov     [rsp+4C0h+var_490], eax
0x18009208f  mov     eax, 21Eh
0x180092094  mov     [rsp+4C0h+var_48A], ax
0x180092099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800920a0  cmp     rcx, r15
0x1800920a3  jz      short loc_1800920DF
0x1800920a5  test    dword ptr [rcx+1Ch], 2000000h
0x1800920ac  jz      short loc_1800920DF
0x1800920ae  lea     rax, [rbp+3C0h+szVolumeName]
0x1800920b5  mov     [rsp+4C0h+var_498], ebx
0x1800920b9  mov     [rsp+4C0h+var_4A0], rax
0x1800920be  lea     r9, aGetvolumenamef; "::GetVolumeNameForVolumeMountPoint( wsz"...
0x1800920c5  mov     edx, 15h
0x1800920ca  jmp     loc_180091FC8
0x1800920cf  mov     eax, 21Eh
0x1800920d4  xor     ebx, ebx
0x1800920d6  mov     [rsp+4C0h+var_48C], ax
0x1800920db  mov     [rsp+4C0h+var_490], ebx
0x1800920df  lea     rcx, [rsp+4C0h+lpszFileName]; this
0x1800920e4  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800920e9  lea     rcx, [rsp+4C0h+var_490]; this
0x1800920ee  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800920f3  mov     eax, ebx
0x1800920f5  mov     rcx, [rbp+3C0h+var_20]
0x1800920fc  xor     rcx, rsp; StackCookie
0x1800920ff  call    __security_check_cookie
0x180092104  lea     r11, [rsp+4C0h+var_10]
0x18009210c  mov     rbx, [r11+30h]
0x180092110  mov     rsi, [r11+38h]
0x180092114  mov     rsp, r11
0x180092117  pop     r15
0x180092119  pop     rdi
0x18009211a  pop     rbp
0x18009211b  retn
```
