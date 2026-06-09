# SxGetUniqueVolumeForPath(ushort const *,ushort *,ulong)

- ea: `0x180095fd4`
- end: `0x1800962ff`
- name: `?SxGetUniqueVolumeForPath@@YAJPEBGPEAGK@Z`
- size: `811`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPWSTR lpszVolumeName, unsigned int)`
- caller_count: `4`
- callee_count: `11`
- tags: `reparse_path`

## callers

- `0x18000f8bc`
- `0x1800178cc`
- `0x18008f118`
- `0x180094d48`

## callees

- `0x1800083e4`
- `0x180014eac`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180095fd4`
- `0x18009e904`
- `0x18009ea6c`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!GetVolumePathNameW` at `0x180096147`
- `KERNEL32!GetVolumePathNameW` at `0x180096147`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800961d7`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180096256`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800961d7`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x180096256`

## string_xrefs

- `0x180096042`: `SxGetUniqueVolumeForPath`
- `0x18009618d`: `::GetVolumePathName( strPath, STRING_CCH_PARAM( wszRootPath ) )`
- `0x180096226`: `::GetVolumeNameForVolumeMountPoint( wszRootPath, STRING_CCH_PARAM( wszVolume ) )`
- `0x1800962a0`: `::GetVolumeNameForVolumeMountPoint( wszVolume, pwszUnique, cchUnique )`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v12, "SxGetUniqueVolumeForPath", 0x1FEu, 1u);
  v16 = 0;
  lpszFileName = (LPCWSTR)qword_1800EE510;
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
0x180095fd4  mov     [rsp-8+arg_10], rbx
0x180095fd9  mov     [rsp-8+arg_18], rsi
0x180095fde  push    rbp
0x180095fdf  push    rdi
0x180095fe0  push    r15
0x180095fe2  lea     rbp, [rsp-3B0h]
0x180095fea  sub     rsp, 4B0h
0x180095ff1  mov     rax, cs:__security_cookie
0x180095ff8  xor     rax, rsp
0x180095ffb  mov     [rbp+3C0h+var_20], rax
0x180096002  mov     rsi, rdx
0x180096005  mov     rbx, rcx
0x180096008  mov     rcx, cs:WPP_GLOBAL_Control
0x18009600f  lea     r15, WPP_GLOBAL_Control
0x180096016  cmp     rcx, r15
0x180096019  jz      short loc_18009603C
0x18009601b  test    dword ptr [rcx+1Ch], 20000000h
0x180096022  jz      short loc_18009603C
0x180096024  mov     rcx, [rcx+10h]
0x180096028  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18009602f  mov     edx, 12h
0x180096034  mov     r9, rbx
0x180096037  call    WPP_SF_S
0x18009603c  mov     r9d, 1; unsigned __int16
0x180096042  lea     rdx, aSxgetuniquevol; "SxGetUniqueVolumeForPath"
0x180096049  mov     r8d, 1FEh; unsigned __int16
0x18009604f  lea     rcx, [rsp+4C0h+var_490]; this
0x180096054  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180096059  lea     rax, qword_1800EE510
0x180096060  mov     [rsp+4C0h+var_450], 0
0x180096069  mov     edi, 20Ah
0x18009606e  mov     [rsp+4C0h+lpszFileName], rax
0x180096073  mov     r8d, edi; Size
0x180096076  lea     rcx, [rbp+3C0h+szVolumePathName]; void *
0x18009607a  xor     edx, edx; Val
0x18009607c  call    memset_0
0x180096081  mov     r8d, edi; Size
0x180096084  lea     rcx, [rbp+3C0h+szVolumeName]; void *
0x18009608b  xor     edx, edx; Val
0x18009608d  call    memset_0
0x180096092  lea     eax, [rdi-6]
0x180096095  test    rbx, rbx
0x180096098  jnz     short loc_1800960A9
0x18009609a  mov     ebx, 80070057h
0x18009609f  mov     [rsp+4C0h+var_48A], ax
0x1800960a4  jmp     loc_1800962BD
0x1800960a9  mov     [rsp+4C0h+var_48C], ax
0x1800960ae  test    rsi, rsi
0x1800960b1  jnz     short loc_1800960BA
0x1800960b3  mov     eax, 205h
0x1800960b8  jmp     short loc_18009609A
0x1800960ba  mov     eax, 206h
0x1800960bf  mov     [rsp+4C0h+var_490], 0
0x1800960c7  mov     rdx, rbx; unsigned __int16 *
0x1800960ca  mov     [rsp+4C0h+var_48C], ax
0x1800960cf  lea     rcx, [rsp+4C0h+lpszFileName]; this
0x1800960d4  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800960d9  mov     ebx, eax
0x1800960db  mov     [rsp+4C0h+var_490], eax
0x1800960df  test    eax, eax
0x1800960e1  mov     eax, 208h
0x1800960e6  jns     short loc_1800960F2
0x1800960e8  mov     [rsp+4C0h+var_48A], ax
0x1800960ed  jmp     loc_1800962C1
0x1800960f2  cmp     dword ptr [rsp+4C0h+var_450], 0
0x1800960f7  mov     [rsp+4C0h+var_48C], ax
0x1800960fc  mov     eax, 209h
0x180096101  jz      short loc_18009609A
0x180096103  mov     edx, 5Ch ; '\'; unsigned __int16
0x180096108  mov     [rsp+4C0h+var_490], 0
0x180096110  lea     rcx, [rsp+4C0h+lpszFileName]; this
0x180096115  mov     [rsp+4C0h+var_48C], ax
0x18009611a  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18009611f  mov     ebx, eax
0x180096121  mov     [rsp+4C0h+var_490], eax
0x180096125  test    eax, eax
0x180096127  mov     eax, 20Bh
0x18009612c  js      short loc_1800960E8
0x18009612e  mov     rdi, [rsp+4C0h+lpszFileName]
0x180096133  lea     rdx, [rbp+3C0h+szVolumePathName]; lpszVolumePathName
0x180096137  mov     ebx, 105h
0x18009613c  mov     [rsp+4C0h+var_48C], ax
0x180096141  mov     r8d, ebx; cchBufferLength
0x180096144  mov     rcx, rdi; lpszFileName
0x180096147  call    cs:__imp_GetVolumePathNameW
0x18009614e  nop     dword ptr [rax+rax+00h]
0x180096153  test    eax, eax
0x180096155  jnz     short loc_1800961B7
0x180096157  call    GetLastFailureAsHRESULT
0x18009615c  mov     ebx, eax
0x18009615e  mov     [rsp+4C0h+var_490], eax
0x180096162  mov     eax, 211h
0x180096167  mov     [rsp+4C0h+var_48A], ax
0x18009616c  mov     rcx, cs:WPP_GLOBAL_Control
0x180096173  cmp     rcx, r15
0x180096176  jz      loc_1800962C1
0x18009617c  test    dword ptr [rcx+1Ch], 2000000h
0x180096183  jz      loc_1800962C1
0x180096189  mov     [rsp+4C0h+var_498], ebx
0x18009618d  lea     r9, aGetvolumepathn_0; "::GetVolumePathName( strPath, STRING_CC"...
0x180096194  mov     [rsp+4C0h+var_4A0], rdi
0x180096199  mov     edx, 13h
0x18009619e  mov     rcx, [rcx+10h]
0x1800961a2  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x1800961a9  call    WPP_SF_sSd
0x1800961ae  mov     ebx, [rsp+4C0h+var_490]
0x1800961b2  jmp     loc_1800962C1
0x1800961b7  mov     eax, 211h
0x1800961bc  mov     [rsp+4C0h+var_490], 0
0x1800961c4  mov     r8d, ebx; cchBufferLength
0x1800961c7  mov     [rsp+4C0h+var_48C], ax
0x1800961cc  lea     rdx, [rbp+3C0h+szVolumeName]; lpszVolumeName
0x1800961d3  lea     rcx, [rbp+3C0h+szVolumePathName]; lpszVolumeMountPoint
0x1800961d7  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800961de  nop     dword ptr [rax+rax+00h]
0x1800961e3  test    eax, eax
0x1800961e5  jnz     short loc_180096237
0x1800961e7  call    GetLastFailureAsHRESULT
0x1800961ec  mov     ebx, eax
0x1800961ee  mov     [rsp+4C0h+var_490], eax
0x1800961f2  mov     eax, 218h
0x1800961f7  mov     [rsp+4C0h+var_48A], ax
0x1800961fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180096203  cmp     rcx, r15
0x180096206  jz      loc_1800962C1
0x18009620c  test    dword ptr [rcx+1Ch], 2000000h
0x180096213  jz      loc_1800962C1
0x180096219  lea     rax, [rbp+3C0h+szVolumePathName]
0x18009621d  mov     [rsp+4C0h+var_498], ebx
0x180096221  mov     [rsp+4C0h+var_4A0], rax
0x180096226  lea     r9, aGetvolumenamef_0; "::GetVolumeNameForVolumeMountPoint( wsz"...
0x18009622d  mov     edx, 14h
0x180096232  jmp     loc_18009619E
0x180096237  mov     eax, 218h
0x18009623c  mov     [rsp+4C0h+var_490], 0
0x180096244  mov     r8d, ebx; cchBufferLength
0x180096247  mov     [rsp+4C0h+var_48C], ax
0x18009624c  mov     rdx, rsi; lpszVolumeName
0x18009624f  lea     rcx, [rbp+3C0h+szVolumeName]; lpszVolumeMountPoint
0x180096256  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18009625d  nop     dword ptr [rax+rax+00h]
0x180096262  test    eax, eax
0x180096264  jnz     short loc_1800962B1
0x180096266  call    GetLastFailureAsHRESULT
0x18009626b  mov     ebx, eax
0x18009626d  mov     [rsp+4C0h+var_490], eax
0x180096271  mov     eax, 21Eh
0x180096276  mov     [rsp+4C0h+var_48A], ax
0x18009627b  mov     rcx, cs:WPP_GLOBAL_Control
0x180096282  cmp     rcx, r15
0x180096285  jz      short loc_1800962C1
0x180096287  test    dword ptr [rcx+1Ch], 2000000h
0x18009628e  jz      short loc_1800962C1
0x180096290  lea     rax, [rbp+3C0h+szVolumeName]
0x180096297  mov     [rsp+4C0h+var_498], ebx
0x18009629b  mov     [rsp+4C0h+var_4A0], rax
0x1800962a0  lea     r9, aGetvolumenamef; "::GetVolumeNameForVolumeMountPoint( wsz"...
0x1800962a7  mov     edx, 15h
0x1800962ac  jmp     loc_18009619E
0x1800962b1  mov     eax, 21Eh
0x1800962b6  xor     ebx, ebx
0x1800962b8  mov     [rsp+4C0h+var_48C], ax
0x1800962bd  mov     [rsp+4C0h+var_490], ebx
0x1800962c1  lea     rcx, [rsp+4C0h+lpszFileName]; this
0x1800962c6  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800962cb  lea     rcx, [rsp+4C0h+var_490]; this
0x1800962d0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800962d5  mov     eax, ebx
0x1800962d7  mov     rcx, [rbp+3C0h+var_20]
0x1800962de  xor     rcx, rsp; StackCookie
0x1800962e1  call    __security_check_cookie
0x1800962e6  lea     r11, [rsp+4C0h+var_10]
0x1800962ee  mov     rbx, [r11+30h]
0x1800962f2  mov     rsi, [r11+38h]
0x1800962f6  mov     rsp, r11
0x1800962f9  pop     r15
0x1800962fb  pop     rdi
0x1800962fc  pop     rbp
0x1800962fd  retn
```
