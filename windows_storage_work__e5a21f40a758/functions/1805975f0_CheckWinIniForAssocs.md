# CheckWinIniForAssocs

- ea: `0x1805975f0`
- end: `0x180597a09`
- name: `CheckWinIniForAssocs`
- size: `1049`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800186d0`
- `0x18007e0a0`
- `0x1800a0ff0`
- `0x1800a3080`
- `0x1800a60f0`
- `0x1800aa710`
- `0x180120884`
- `0x180152670`
- `0x1803a4cb0`
- `0x180596060`
- `0x1805975f0`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180597689`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1805976f0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180597689`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1805976f0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059779d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180597824`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180597845`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180597893`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805978b4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18059779d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180597824`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180597845`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180597893`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805978b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805979e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805979e2`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180597907`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180597914`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180597907`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180597914`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180597835`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1805978a4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180597835`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1805978a4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x180597742`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x180597779`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x180597742`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x180597779`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileSectionW` at `0x180597658`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileSectionW` at `0x180597658`
- `api-ms-win-core-registry-l2-1-0!RegSetValueW` at `0x18059786b`
- `api-ms-win-core-registry-l2-1-0!RegSetValueW` at `0x180597997`
- `api-ms-win-core-registry-l2-1-0!RegSetValueW` at `0x18059786b`
- `api-ms-win-core-registry-l2-1-0!RegSetValueW` at `0x180597997`

## string_xrefs

- `0x1805977e4`: `Software\Microsoft\Windows\CurrentVersion\Extensions`
- `0x180597800`: `Software\Microsoft\Windows\CurrentVersion\Extensions`
- `0x1805978ca`: `Software\Microsoft\Windows\CurrentVersion\Extensions`
- `0x18059764e`: `Extensions`
- `0x180597965`: `\shell\open\command`

## pseudocode

```c
HLOCAL __fastcall CheckWinIniForAssocs(__int64 a1)
{
  HLOCAL result; // rax
  const WCHAR *i; // rdi
  int v3; // ebx
  PWSTR v4; // rax
  __int64 v5; // r10
  unsigned __int64 v6; // rax
  PWSTR v7; // rax
  PWSTR v8; // rsi
  __int64 v9; // r8
  const WCHAR *FileNameW; // rax
  const WCHAR *v11; // rax
  const unsigned __int16 *v12; // rsi
  unsigned __int16 v13; // ax
  WCHAR *v14; // r14
  unsigned __int16 v15; // bx
  __int64 v16; // rax
  DWORD cbData; // [rsp+20h] [rbp-E0h]
  LPWSTR lpReturnedString; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszStr1[12]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Data[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 pvData[264]; // [rsp+470h] [rbp+370h] BYREF
  WCHAR pszPath[264]; // [rsp+680h] [rbp+580h] BYREF

  lpReturnedString = 0;
  wcscpy(SubKey, L".");
  result = (HLOCAL)_AllocArray<unsigned short,CTLocalAllocPolicy>(a1, 64, 4096, &lpReturnedString);
  if ( (int)result >= 0 )
  {
    if ( (int)GetProfileSectionW(L"Extensions", lpReturnedString, 0x1000u) < 4094 )
    {
      i = lpReturnedString;
      v3 = 0;
      if ( *lpReturnedString )
      {
        do
        {
          v4 = StrChrW(i, 0x3Du);
          if ( v4 )
          {
            SubKey[0] = 46;
            StringCchCopyNW(&SubKey[1], 0x103u, i, v4 - i);
            v6 = -1;
            do
              ++v6;
            while ( SubKey[v6] );
            if ( v6 <= 4 )
            {
              for ( i = (const WCHAR *)(v5 + 2); *i == 32; ++i )
                ;
              v7 = StrChrW(i, 0x5Eu);
              v8 = v7;
              if ( v7 )
              {
                StringCchCopyNW(Data, 0x104u, i, v7 - i);
                if ( (int)StringCchCopyW(pszPath, 0x104u, Data) >= 0 )
                {
                  PathRemoveBlanksW(pszPath);
                  if ( PathIsExe(pszPath) )
                  {
                    if ( (int)StringCchCopyW(pszStr1, 5u, SubKey) < 0
                      || (PathRemoveBlanksW(pszStr1), !PathIsExe(pszStr1)) && StrCmpICW(pszStr1, L".lnk") )
                    {
                      if ( Reg_ShellOpenForExtension(SubKey, Data, v9, pvData, cbData, i) )
                      {
                        if ( !(unsigned int)RegGetValueString(
                                              HKEY_LOCAL_MACHINE,
                                              L"Software\\Microsoft\\Windows\\CurrentVersion\\Extensions",
                                              SubKey,
                                              pvData,
                                              260) )
                          SHRegSetString(
                            HKEY_LOCAL_MACHINE,
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\Extensions",
                            SubKey,
                            i);
                      }
                      else
                      {
                        if ( !StrCmpICW(SubKey, L".dgw") )
                        {
                          FileNameW = PathFindFileNameW(Data);
                          if ( !StrCmpICW(FileNameW, L"designw.exe ") )
                          {
                            RegSetValueW(HKEY_CLASSES_ROOT, SubKey, 1u, L"HDesign", 0);
                            StringCchCopyW(pvData, 0x104u, L"HDesign");
                          }
                        }
                        if ( StrCmpICW(SubKey, L".WOC")
                          || (v11 = PathFindFileNameW(Data), StrCmpICW(v11, L"WINORG.EXE ")) )
                        {
                          SHRegSetString(
                            HKEY_LOCAL_MACHINE,
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\Extensions",
                            SubKey,
                            i);
                          StringCchCatW(Data, 0x104u, L"%1");
                          v12 = v8 + 1;
                          v13 = *v12;
                          if ( *v12 )
                          {
                            v14 = SubKey;
                            do
                            {
                              v15 = (unsigned __int16)CharLowerW((LPWSTR)v13);
                              if ( v15 != (unsigned __int16)CharLowerW((LPWSTR)*v14) )
                                break;
                              ++v12;
                              ++v14;
                              v13 = *v12;
                            }
                            while ( *v12 );
                            if ( *v12 )
                              StringCchCatW(Data, 0x104u, v12);
                          }
                          if ( pvData[0] )
                            StringCchCopyW(SubKey, 0x104u, pvData);
                          StringCchCatW(SubKey, 0x104u, L"\\shell\\open\\command");
                          RegSetValueW(HKEY_CLASSES_ROOT, SubKey, 1u, Data, 0);
                          v3 = 1;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          v16 = -1;
          do
            ++v16;
          while ( i[v16] );
          i += v16 + 1;
        }
        while ( *i );
        if ( v3 )
          SHChangeNotify(0x8000000, 0, 0, 0);
      }
    }
    return LocalFree(lpReturnedString);
  }
  return result;
}

```

## disassembly

```asm
0x1805975f0  push    rbp
0x1805975f2  push    rbx
0x1805975f3  push    rsi
0x1805975f4  push    rdi
0x1805975f5  push    r12
0x1805975f7  push    r13
0x1805975f9  push    r14
0x1805975fb  lea     rbp, [rsp-7A0h]
0x180597603  sub     rsp, 8A0h
0x18059760a  mov     rax, cs:__security_cookie
0x180597611  xor     rax, rsp
0x180597614  mov     [rbp+7D0h+var_40], rax
0x18059761b  xor     r12d, r12d
0x18059761e  lea     r9, [rsp+8D0h+lpReturnedString]
0x180597623  mov     ebx, 1000h
0x180597628  mov     [rsp+8D0h+lpReturnedString], r12
0x18059762d  mov     r8d, ebx
0x180597630  lea     esi, [r12+2Eh]
0x180597635  lea     edx, [rsi+12h]
0x180597638  mov     dword ptr [rsp+8D0h+SubKey], esi
0x18059763c  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180597641  test    eax, eax
0x180597643  js      loc_1805979E8
0x180597649  mov     rdx, [rsp+8D0h+lpReturnedString]; lpReturnedString
0x18059764e  lea     rcx, AppName; "Extensions"
0x180597655  mov     r8d, ebx; nSize
0x180597658  call    cs:__imp_GetProfileSectionW
0x18059765e  cmp     eax, 0FFEh
0x180597663  jge     loc_1805979DD
0x180597669  mov     rdi, [rsp+8D0h+lpReturnedString]
0x18059766e  mov     ebx, r12d
0x180597671  cmp     [rdi], r12w
0x180597675  jz      loc_1805979DD
0x18059767b  mov     r13d, 104h
0x180597681  mov     edx, 3Dh ; '='; wMatch
0x180597686  mov     rcx, rdi; pszStart
0x180597689  call    cs:__imp_StrChrW
0x18059768f  mov     r10, rax
0x180597692  test    rax, rax
0x180597695  jz      loc_1805979A7
0x18059769b  mov     r9, rax
0x18059769e  mov     [rsp+8D0h+SubKey], si
0x1805976a3  sub     r9, rdi
0x1805976a6  lea     rcx, [rsp+8D0h+SubKey+2]; unsigned __int16 *
0x1805976ab  sar     r9, 1; unsigned __int64
0x1805976ae  mov     r8, rdi; unsigned __int16 *
0x1805976b1  mov     edx, 103h; unsigned __int64
0x1805976b6  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1805976bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1805976bf  lea     r11, [rsp+8D0h+SubKey]
0x1805976c4  inc     rax
0x1805976c7  cmp     [r11+rax*2], r12w
0x1805976cc  jnz     short loc_1805976C4
0x1805976ce  cmp     rax, 4
0x1805976d2  ja      loc_1805979A7
0x1805976d8  lea     rdi, [r10+2]
0x1805976dc  jmp     short loc_1805976E2
0x1805976de  add     rdi, 2
0x1805976e2  cmp     word ptr [rdi], 20h ; ' '
0x1805976e6  jz      short loc_1805976DE
0x1805976e8  mov     edx, 5Eh ; '^'; wMatch
0x1805976ed  mov     rcx, rdi; pszStart
0x1805976f0  call    cs:__imp_StrChrW
0x1805976f6  mov     rsi, rax
0x1805976f9  test    rax, rax
0x1805976fc  jz      loc_1805979A2
0x180597702  mov     r9, rax
0x180597705  lea     rcx, [rbp+7D0h+Data]; unsigned __int16 *
0x18059770c  sub     r9, rdi
0x18059770f  mov     r8, rdi; unsigned __int16 *
0x180597712  sar     r9, 1; unsigned __int64
0x180597715  mov     rdx, r13; unsigned __int64
0x180597718  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18059771d  lea     r8, [rbp+7D0h+Data]; unsigned __int16 *
0x180597724  mov     rdx, r13; unsigned __int64
0x180597727  lea     rcx, [rbp+7D0h+pszPath]; unsigned __int16 *
0x18059772e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180597733  test    eax, eax
0x180597735  js      loc_1805979A2
0x18059773b  lea     rcx, [rbp+7D0h+pszPath]; pszPath
0x180597742  call    cs:__imp_PathRemoveBlanksW
0x180597748  lea     rcx, [rbp+7D0h+pszPath]; pszPath
0x18059774f  call    PathIsExe
0x180597754  test    eax, eax
0x180597756  jz      loc_1805979A2
0x18059775c  lea     r8, [rsp+8D0h+SubKey]; unsigned __int16 *
0x180597761  mov     edx, 5; unsigned __int64
0x180597766  lea     rcx, [rsp+8D0h+pszStr1]; unsigned __int16 *
0x18059776b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180597770  test    eax, eax
0x180597772  js      short loc_1805977AB
0x180597774  lea     rcx, [rsp+8D0h+pszStr1]; pszPath
0x180597779  call    cs:__imp_PathRemoveBlanksW
0x18059777f  lea     rcx, [rsp+8D0h+pszStr1]; pszPath
0x180597784  call    PathIsExe
0x180597789  test    eax, eax
0x18059778b  jnz     loc_1805979A2
0x180597791  lea     rdx, pszExt; ".lnk"
0x180597798  lea     rcx, [rsp+8D0h+pszStr1]; pszStr1
0x18059779d  call    cs:__imp_StrCmpICW
0x1805977a3  test    eax, eax
0x1805977a5  jz      loc_1805979A2
0x1805977ab  lea     r9, [rbp+7D0h+pvData]; unsigned __int16 *
0x1805977b2  mov     [rsp+8D0h+var_8A8], rdi; unsigned __int16 *
0x1805977b7  lea     rdx, [rbp+7D0h+Data]; unsigned __int16 *
0x1805977be  lea     rcx, [rsp+8D0h+SubKey]; lpValue
0x1805977c3  call    ?Reg_ShellOpenForExtension@@YAHPEBGPEAGH1H0@Z; Reg_ShellOpenForExtension(ushort const *,ushort *,int,ushort *,int,ushort const *)
0x1805977c8  test    eax, eax
0x1805977ca  jz      short loc_180597818
0x1805977cc  lea     r9, [rbp+7D0h+pvData]; pvData
0x1805977d3  mov     [rsp+8D0h+cbData], r13d; int
0x1805977d8  lea     r8, [rsp+8D0h+SubKey]; lpValue
0x1805977dd  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1805977e4  lea     rdx, aSoftwareMicros_134; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1805977eb  call    RegGetValueString
0x1805977f0  test    eax, eax
0x1805977f2  jnz     loc_1805979A2
0x1805977f8  mov     r9, rdi; unsigned __int16 *
0x1805977fb  lea     r8, [rsp+8D0h+SubKey]; unsigned __int16 *
0x180597800  lea     rdx, aSoftwareMicros_134; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180597807  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18059780e  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180597813  jmp     loc_1805979A2
0x180597818  lea     rdx, aDgw; ".dgw"
0x18059781f  lea     rcx, [rsp+8D0h+SubKey]; pszStr1
0x180597824  call    cs:__imp_StrCmpICW
0x18059782a  test    eax, eax
0x18059782c  jnz     short loc_180597887
0x18059782e  lea     rcx, [rbp+7D0h+Data]; pszPath
0x180597835  call    cs:__imp_PathFindFileNameW
0x18059783b  mov     rcx, rax; pszStr1
0x18059783e  lea     rdx, aDesignwExe; "designw.exe "
0x180597845  call    cs:__imp_StrCmpICW
0x18059784b  test    eax, eax
0x18059784d  jnz     short loc_180597887
0x18059784f  lea     r9, aHdesign; "HDesign"
0x180597856  mov     [rsp+8D0h+cbData], r12d; cbData
0x18059785b  lea     r8d, [rax+1]; dwType
0x18059785f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180597866  lea     rdx, [rsp+8D0h+SubKey]; lpSubKey
0x18059786b  call    cs:__imp_RegSetValueW
0x180597871  lea     r8, aHdesign; "HDesign"
0x180597878  mov     rdx, r13; unsigned __int64
0x18059787b  lea     rcx, [rbp+7D0h+pvData]; unsigned __int16 *
0x180597882  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180597887  lea     rdx, aWoc; ".WOC"
0x18059788e  lea     rcx, [rsp+8D0h+SubKey]; pszStr1
0x180597893  call    cs:__imp_StrCmpICW
0x180597899  test    eax, eax
0x18059789b  jnz     short loc_1805978C2
0x18059789d  lea     rcx, [rbp+7D0h+Data]; pszPath
0x1805978a4  call    cs:__imp_PathFindFileNameW
0x1805978aa  mov     rcx, rax; pszStr1
0x1805978ad  lea     rdx, aWinorgExe; "WINORG.EXE "
0x1805978b4  call    cs:__imp_StrCmpICW
0x1805978ba  test    eax, eax
0x1805978bc  jz      loc_1805979A2
0x1805978c2  mov     r9, rdi; unsigned __int16 *
0x1805978c5  lea     r8, [rsp+8D0h+SubKey]; unsigned __int16 *
0x1805978ca  lea     rdx, aSoftwareMicros_134; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1805978d1  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1805978d8  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1805978dd  lea     r8, cText; "%1"
0x1805978e4  mov     rdx, r13; unsigned __int64
0x1805978e7  lea     rcx, [rbp+7D0h+Data]; unsigned __int16 *
0x1805978ee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1805978f3  add     rsi, 2
0x1805978f7  movzx   eax, word ptr [rsi]
0x1805978fa  test    ax, ax
0x1805978fd  jz      short loc_180597947
0x1805978ff  lea     r14, [rsp+8D0h+SubKey]
0x180597904  movzx   ecx, ax; lpsz
0x180597907  call    cs:__imp_CharLowerW
0x18059790d  movzx   ecx, word ptr [r14]; lpsz
0x180597911  mov     rbx, rax
0x180597914  call    cs:__imp_CharLowerW
0x18059791a  cmp     bx, ax
0x18059791d  jnz     short loc_18059792F
0x18059791f  add     rsi, 2
0x180597923  add     r14, 2
0x180597927  movzx   eax, word ptr [rsi]
0x18059792a  test    ax, ax
0x18059792d  jnz     short loc_180597904
0x18059792f  cmp     [rsi], r12w
0x180597933  jz      short loc_180597947
0x180597935  mov     r8, rsi; unsigned __int16 *
0x180597938  lea     rcx, [rbp+7D0h+Data]; unsigned __int16 *
0x18059793f  mov     rdx, r13; unsigned __int64
0x180597942  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180597947  cmp     [rbp+7D0h+pvData], r12w
0x18059794f  jz      short loc_180597965
0x180597951  lea     r8, [rbp+7D0h+pvData]; unsigned __int16 *
0x180597958  mov     rdx, r13; unsigned __int64
0x18059795b  lea     rcx, [rsp+8D0h+SubKey]; unsigned __int16 *
0x180597960  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180597965  lea     r8, aShellOpenComma; "\\shell\\open\\command"
0x18059796c  mov     rdx, r13; unsigned __int64
0x18059796f  lea     rcx, [rsp+8D0h+SubKey]; unsigned __int16 *
0x180597974  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180597979  lea     r9, [rbp+7D0h+Data]; lpData
0x180597980  mov     [rsp+8D0h+cbData], r12d; cbData
0x180597985  mov     r8d, 1; dwType
0x18059798b  lea     rdx, [rsp+8D0h+SubKey]; lpSubKey
0x180597990  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180597997  call    cs:__imp_RegSetValueW
0x18059799d  mov     ebx, 1
0x1805979a2  mov     esi, 2Eh ; '.'
0x1805979a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1805979ab  inc     rax
0x1805979ae  cmp     [rdi+rax*2], r12w
0x1805979b3  jnz     short loc_1805979AB
0x1805979b5  lea     rdi, [rdi+rax*2]
0x1805979b9  add     rdi, 2
0x1805979bd  cmp     [rdi], r12w
0x1805979c1  jnz     loc_180597681
0x1805979c7  test    ebx, ebx
0x1805979c9  jz      short loc_1805979DD
0x1805979cb  xor     r9d, r9d; dwItem2
0x1805979ce  xor     r8d, r8d; dwItem1
0x1805979d1  xor     edx, edx; uFlags
0x1805979d3  mov     ecx, 8000000h; wEventId
0x1805979d8  call    SHChangeNotify
0x1805979dd  mov     rcx, [rsp+8D0h+lpReturnedString]; hMem
0x1805979e2  call    cs:__imp_LocalFree
0x1805979e8  mov     rcx, [rbp+7D0h+var_40]
0x1805979ef  xor     rcx, rsp; StackCookie
0x1805979f2  call    __security_check_cookie
0x1805979f7  add     rsp, 8A0h
0x1805979fe  pop     r14
0x180597a00  pop     r13
0x180597a02  pop     r12
0x180597a04  pop     rdi
0x180597a05  pop     rsi
0x180597a06  pop     rbx
0x180597a07  pop     rbp
0x180597a08  retn
```
