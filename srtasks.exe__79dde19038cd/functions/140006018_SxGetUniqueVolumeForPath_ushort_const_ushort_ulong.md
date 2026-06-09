# SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)

- ea: `0x140006018`
- end: `0x14000632b`
- name: `?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z`
- size: `787`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPWSTR lpszVolumeName)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path`

## callers

- `0x140005eb0`
- `0x140006334`

## callees

- `0x1400054f4`
- `0x140005658`
- `0x140006018`
- `0x140006cc8`
- `0x14000e324`
- `0x14000e41c`
- `0x14000fe8c`
- `0x140010324`
- `0x140010744`
- `0x14001094e`
- `0x140010980`

## import_xrefs

- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140006210`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140006289`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140006210`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x140006289`
- `KERNEL32!GetVolumePathNameW` at `0x140006186`
- `KERNEL32!GetVolumePathNameW` at `0x140006186`

## string_xrefs

- `0x140006086`: `SxGetUniqueVolumeForPath`
- `0x1400061c6`: `::GetVolumePathName( strPath, STRING_CCH_PARAM( wszRootPath ) )`
- `0x140006259`: `::GetVolumeNameForVolumeMountPoint( wszRootPath, STRING_CCH_PARAM( wszVolume ) )`
- `0x1400062cd`: `::GetVolumeNameForVolumeMountPoint( wszVolume, pwszUnique, cchUnique )`

## pseudocode

```c
__int64 __fastcall SxGetUniqueVolumeForPath(const unsigned __int16 *a1, LPWSTR lpszVolumeName)
{
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  unsigned __int16 v6; // dx
  __int16 v7; // ax
  LPCWSTR v8; // rdi
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v11; // [rsp+34h] [rbp-CCh]
  __int16 v12; // [rsp+36h] [rbp-CAh]
  LPCWSTR lpszFileName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v14; // [rsp+70h] [rbp-90h]
  WCHAR szVolumePathName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR szVolumeName[264]; // [rsp+290h] [rbp+190h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids, a1);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "SxGetUniqueVolumeForPath", 0x1FEu, 1u);
  v14 = 0;
  lpszFileName = (LPCWSTR)qword_140013960;
  memset_0(szVolumePathName, 0, 0x20Au);
  memset_0(szVolumeName, 0, 0x20Au);
  v4 = 516;
  if ( !a1 )
    goto LABEL_5;
  v11 = 516;
  if ( !lpszVolumeName )
  {
    v4 = 517;
LABEL_5:
    LastFailureAsHRESULT = -2147024809;
    v12 = v4;
LABEL_26:
    v10 = LastFailureAsHRESULT;
    goto LABEL_27;
  }
  v10 = 0;
  v11 = 518;
  LastFailureAsHRESULT = CBsString::Append((CBsString *)&lpszFileName, a1);
  v10 = LastFailureAsHRESULT;
  v7 = 520;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_9;
  v11 = 520;
  v4 = 521;
  if ( !(_DWORD)v14 )
    goto LABEL_5;
  v10 = 0;
  v11 = 521;
  LastFailureAsHRESULT = CBsString::Trailing((CBsString *)&lpszFileName, v6);
  v10 = LastFailureAsHRESULT;
  v7 = 523;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_9:
    v12 = v7;
  }
  else
  {
    v8 = lpszFileName;
    v11 = 523;
    if ( GetVolumePathNameW(lpszFileName, szVolumePathName, 0x105u) )
    {
      v10 = 0;
      v11 = 529;
      if ( GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x105u) )
      {
        v10 = 0;
        v11 = 536;
        if ( GetVolumeNameForVolumeMountPointW(szVolumeName, lpszVolumeName, 0x105u) )
        {
          LastFailureAsHRESULT = 0;
          v11 = 542;
          goto LABEL_26;
        }
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v10 = LastFailureAsHRESULT;
        v12 = 542;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
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
        LastFailureAsHRESULT = GetLastFailureAsHRESULT();
        v10 = LastFailureAsHRESULT;
        v12 = 536;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
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
      LastFailureAsHRESULT = GetLastFailureAsHRESULT();
      v10 = LastFailureAsHRESULT;
      v12 = 529;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_sSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
          (unsigned int)"::GetVolumePathName( strPath, STRING_CCH_PARAM( wszRootPath ) )",
          (__int64)v8,
          LastFailureAsHRESULT);
LABEL_16:
        LastFailureAsHRESULT = v10;
      }
    }
  }
LABEL_27:
  CBsString::_Release((CBsString *)&lpszFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x140006018  mov     [rsp-8+arg_10], rbx
0x14000601d  mov     [rsp-8+arg_18], rsi
0x140006022  push    rbp
0x140006023  push    rdi
0x140006024  push    r15
0x140006026  lea     rbp, [rsp-3B0h]
0x14000602e  sub     rsp, 4B0h
0x140006035  mov     rax, cs:__security_cookie
0x14000603c  xor     rax, rsp
0x14000603f  mov     [rbp+3C0h+var_20], rax
0x140006046  mov     rsi, rdx
0x140006049  mov     rbx, rcx
0x14000604c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006053  lea     r15, WPP_GLOBAL_Control
0x14000605a  cmp     rcx, r15
0x14000605d  jz      short loc_140006080
0x14000605f  test    dword ptr [rcx+1Ch], 20000000h
0x140006066  jz      short loc_140006080
0x140006068  mov     rcx, [rcx+10h]
0x14000606c  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x140006073  mov     edx, 12h
0x140006078  mov     r9, rbx
0x14000607b  call    WPP_SF_S
0x140006080  mov     r9d, 1; unsigned __int16
0x140006086  lea     rdx, aSxgetuniquevol; "SxGetUniqueVolumeForPath"
0x14000608d  mov     r8d, 1FEh; unsigned __int16
0x140006093  lea     rcx, [rsp+4C0h+var_490]; this
0x140006098  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000609d  lea     rax, qword_140013960
0x1400060a4  mov     [rsp+4C0h+var_450], 0
0x1400060ad  mov     edi, 20Ah
0x1400060b2  mov     [rsp+4C0h+lpszFileName], rax
0x1400060b7  mov     r8d, edi; Size
0x1400060ba  lea     rcx, [rbp+3C0h+szVolumePathName]; void *
0x1400060be  xor     edx, edx; Val
0x1400060c0  call    memset_0
0x1400060c5  mov     r8d, edi; Size
0x1400060c8  lea     rcx, [rbp+3C0h+szVolumeName]; void *
0x1400060cf  xor     edx, edx; Val
0x1400060d1  call    memset_0
0x1400060d6  lea     eax, [rdi-6]
0x1400060d9  test    rbx, rbx
0x1400060dc  jnz     short loc_1400060ED
0x1400060de  mov     ebx, 80070057h
0x1400060e3  mov     [rsp+4C0h+var_48A], ax
0x1400060e8  jmp     loc_1400062EA
0x1400060ed  mov     [rsp+4C0h+var_48C], ax
0x1400060f2  test    rsi, rsi
0x1400060f5  jnz     short loc_1400060FE
0x1400060f7  mov     eax, 205h
0x1400060fc  jmp     short loc_1400060DE
0x1400060fe  mov     eax, 206h
0x140006103  mov     [rsp+4C0h+var_490], 0
0x14000610b  mov     [rsp+4C0h+var_48C], ax
0x140006110  mov     rdx, rbx; unsigned __int16 *
0x140006113  lea     rcx, [rsp+4C0h+lpszFileName]; this
0x140006118  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x14000611d  mov     ebx, eax
0x14000611f  mov     [rsp+4C0h+var_490], eax
0x140006123  test    eax, eax
0x140006125  mov     eax, 208h
0x14000612a  jns     short loc_140006136
0x14000612c  mov     [rsp+4C0h+var_48A], ax
0x140006131  jmp     loc_1400062EE
0x140006136  cmp     dword ptr [rsp+4C0h+var_450], 0
0x14000613b  mov     [rsp+4C0h+var_48C], ax
0x140006140  mov     eax, 209h
0x140006145  jz      short loc_1400060DE
0x140006147  lea     rcx, [rsp+4C0h+lpszFileName]; this
0x14000614c  mov     [rsp+4C0h+var_490], 0
0x140006154  mov     [rsp+4C0h+var_48C], ax
0x140006159  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x14000615e  mov     ebx, eax
0x140006160  mov     [rsp+4C0h+var_490], eax
0x140006164  test    eax, eax
0x140006166  mov     eax, 20Bh
0x14000616b  js      short loc_14000612C
0x14000616d  mov     rdi, [rsp+4C0h+lpszFileName]
0x140006172  lea     rdx, [rbp+3C0h+szVolumePathName]; lpszVolumePathName
0x140006176  mov     ebx, 105h
0x14000617b  mov     [rsp+4C0h+var_48C], ax
0x140006180  mov     r8d, ebx; cchBufferLength
0x140006183  mov     rcx, rdi; lpszFileName
0x140006186  call    cs:__imp_GetVolumePathNameW
0x14000618c  test    eax, eax
0x14000618e  jnz     short loc_1400061F0
0x140006190  call    GetLastFailureAsHRESULT
0x140006195  mov     ebx, eax
0x140006197  mov     [rsp+4C0h+var_490], eax
0x14000619b  mov     eax, 211h
0x1400061a0  mov     [rsp+4C0h+var_48A], ax
0x1400061a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400061ac  cmp     rcx, r15
0x1400061af  jz      loc_1400062EE
0x1400061b5  test    dword ptr [rcx+1Ch], 2000000h
0x1400061bc  jz      loc_1400062EE
0x1400061c2  mov     [rsp+4C0h+var_498], ebx
0x1400061c6  lea     r9, aGetvolumepathn; "::GetVolumePathName( strPath, STRING_CC"...
0x1400061cd  mov     [rsp+4C0h+var_4A0], rdi
0x1400061d2  mov     edx, 13h
0x1400061d7  mov     rcx, [rcx+10h]
0x1400061db  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x1400061e2  call    WPP_SF_sSd
0x1400061e7  mov     ebx, [rsp+4C0h+var_490]
0x1400061eb  jmp     loc_1400062EE
0x1400061f0  mov     eax, 211h
0x1400061f5  mov     [rsp+4C0h+var_490], 0
0x1400061fd  mov     r8d, ebx; cchBufferLength
0x140006200  mov     [rsp+4C0h+var_48C], ax
0x140006205  lea     rdx, [rbp+3C0h+szVolumeName]; lpszVolumeName
0x14000620c  lea     rcx, [rbp+3C0h+szVolumePathName]; lpszVolumeMountPoint
0x140006210  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x140006216  test    eax, eax
0x140006218  jnz     short loc_14000626A
0x14000621a  call    GetLastFailureAsHRESULT
0x14000621f  mov     ebx, eax
0x140006221  mov     [rsp+4C0h+var_490], eax
0x140006225  mov     eax, 218h
0x14000622a  mov     [rsp+4C0h+var_48A], ax
0x14000622f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006236  cmp     rcx, r15
0x140006239  jz      loc_1400062EE
0x14000623f  test    dword ptr [rcx+1Ch], 2000000h
0x140006246  jz      loc_1400062EE
0x14000624c  lea     rax, [rbp+3C0h+szVolumePathName]
0x140006250  mov     [rsp+4C0h+var_498], ebx
0x140006254  mov     [rsp+4C0h+var_4A0], rax
0x140006259  lea     r9, aGetvolumenamef_0; "::GetVolumeNameForVolumeMountPoint( wsz"...
0x140006260  mov     edx, 14h
0x140006265  jmp     loc_1400061D7
0x14000626a  mov     eax, 218h
0x14000626f  mov     [rsp+4C0h+var_490], 0
0x140006277  mov     r8d, ebx; cchBufferLength
0x14000627a  mov     [rsp+4C0h+var_48C], ax
0x14000627f  mov     rdx, rsi; lpszVolumeName
0x140006282  lea     rcx, [rbp+3C0h+szVolumeName]; lpszVolumeMountPoint
0x140006289  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14000628f  test    eax, eax
0x140006291  jnz     short loc_1400062DE
0x140006293  call    GetLastFailureAsHRESULT
0x140006298  mov     ebx, eax
0x14000629a  mov     [rsp+4C0h+var_490], eax
0x14000629e  mov     eax, 21Eh
0x1400062a3  mov     [rsp+4C0h+var_48A], ax
0x1400062a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062af  cmp     rcx, r15
0x1400062b2  jz      short loc_1400062EE
0x1400062b4  test    dword ptr [rcx+1Ch], 2000000h
0x1400062bb  jz      short loc_1400062EE
0x1400062bd  lea     rax, [rbp+3C0h+szVolumeName]
0x1400062c4  mov     [rsp+4C0h+var_498], ebx
0x1400062c8  mov     [rsp+4C0h+var_4A0], rax
0x1400062cd  lea     r9, aGetvolumenamef; "::GetVolumeNameForVolumeMountPoint( wsz"...
0x1400062d4  mov     edx, 15h
0x1400062d9  jmp     loc_1400061D7
0x1400062de  mov     eax, 21Eh
0x1400062e3  xor     ebx, ebx
0x1400062e5  mov     [rsp+4C0h+var_48C], ax
0x1400062ea  mov     [rsp+4C0h+var_490], ebx
0x1400062ee  lea     rcx, [rsp+4C0h+lpszFileName]; this
0x1400062f3  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1400062f8  lea     rcx, [rsp+4C0h+var_490]; this
0x1400062fd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140006302  mov     eax, ebx
0x140006304  mov     rcx, [rbp+3C0h+var_20]
0x14000630b  xor     rcx, rsp; StackCookie
0x14000630e  call    __security_check_cookie
0x140006313  lea     r11, [rsp+4C0h+var_10]
0x14000631b  mov     rbx, [r11+30h]
0x14000631f  mov     rsi, [r11+38h]
0x140006323  mov     rsp, r11
0x140006326  pop     r15
0x140006328  pop     rdi
0x140006329  pop     rbp
0x14000632a  retn
```
