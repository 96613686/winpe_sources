# CheckWinIniForAssocs

- ea: `0x1805b32c0`
- end: `0x1805b36f7`
- name: `CheckWinIniForAssocs`
- size: `1079`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800f8980`
- `0x1801006a0`
- `0x180133f50`
- `0x180135090`
- `0x18015c5a0`
- `0x1801720f0`
- `0x1801bc4d4`
- `0x180228b30`
- `0x1803b1f60`
- `0x1805b1b78`
- `0x1805b2008`
- `0x1805b32c0`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1805b335f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1805b33cc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1805b335f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1805b33cc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805b34cf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805b34fc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805b3556`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805b3583`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805b34cf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805b34fc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805b3556`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1805b3583`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805b36c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1805b36c9`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1805b35dc`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1805b35ef`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1805b35dc`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x1805b35ef`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1805b34e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1805b356d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1805b34e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1805b356d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1805b3424`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1805b3424`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileSectionW` at `0x1805b3328`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileSectionW` at `0x1805b3328`
- `api-ms-win-core-registry-l2-1-0!RegSetValueW` at `0x1805b3528`
- `api-ms-win-core-registry-l2-1-0!RegSetValueW` at `0x1805b3678`
- `api-ms-win-core-registry-l2-1-0!RegSetValueW` at `0x1805b3528`
- `api-ms-win-core-registry-l2-1-0!RegSetValueW` at `0x1805b3678`

## string_xrefs

- `0x1805b3646`: `\shell\open\command`
- `0x1805b331e`: `Extensions`
- `0x1805b348f`: `Software\Microsoft\Windows\CurrentVersion\Extensions`
- `0x1805b34ab`: `Software\Microsoft\Windows\CurrentVersion\Extensions`
- `0x1805b359f`: `Software\Microsoft\Windows\CurrentVersion\Extensions`

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
  LPWSTR lpReturnedString[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszStr1[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Data[264]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 pvData[264]; // [rsp+460h] [rbp+360h] BYREF
  WCHAR pszPath[264]; // [rsp+670h] [rbp+570h] BYREF

  lpReturnedString[0] = 0;
  wcscpy(pszStr1, L".");
  result = (HLOCAL)_AllocArray<unsigned short,CTLocalAllocPolicy>(a1, 64, 4096, lpReturnedString);
  if ( (int)result >= 0 )
  {
    if ( (int)GetProfileSectionW(L"Extensions", lpReturnedString[0], 0x1000u) < 4094 )
    {
      i = lpReturnedString[0];
      v3 = 0;
      if ( *lpReturnedString[0] )
      {
        do
        {
          v4 = StrChrW(i, 0x3Du);
          if ( v4 )
          {
            pszStr1[0] = 46;
            StringCchCopyNW(&pszStr1[1], 0x103u, i, v4 - i);
            v6 = -1;
            do
              ++v6;
            while ( pszStr1[v6] );
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
                    if ( !(unsigned int)ReservedExtension(pszStr1) )
                    {
                      if ( Reg_ShellOpenForExtension(pszStr1, Data, v9, pvData, cbData, i) )
                      {
                        if ( !(unsigned int)RegGetValueString(
                                              HKEY_LOCAL_MACHINE,
                                              L"Software\\Microsoft\\Windows\\CurrentVersion\\Extensions",
                                              pszStr1,
                                              pvData,
                                              260) )
                          SHRegSetString(
                            HKEY_LOCAL_MACHINE,
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\Extensions",
                            pszStr1,
                            i);
                      }
                      else
                      {
                        if ( !StrCmpICW(pszStr1, L".dgw") )
                        {
                          FileNameW = PathFindFileNameW(Data);
                          if ( !StrCmpICW(FileNameW, L"designw.exe ") )
                          {
                            RegSetValueW(HKEY_CLASSES_ROOT, pszStr1, 1u, L"HDesign", 0);
                            StringCchCopyW(pvData, 0x104u, L"HDesign");
                          }
                        }
                        if ( StrCmpICW(pszStr1, L".WOC")
                          || (v11 = PathFindFileNameW(Data), StrCmpICW(v11, L"WINORG.EXE ")) )
                        {
                          SHRegSetString(
                            HKEY_LOCAL_MACHINE,
                            L"Software\\Microsoft\\Windows\\CurrentVersion\\Extensions",
                            pszStr1,
                            i);
                          StringCchCatW(Data, 0x104u, L"%1");
                          v12 = v8 + 1;
                          v13 = *v12;
                          if ( *v12 )
                          {
                            v14 = pszStr1;
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
                            StringCchCopyW(pszStr1, 0x104u, pvData);
                          StringCchCatW(pszStr1, 0x104u, L"\\shell\\open\\command");
                          RegSetValueW(HKEY_CLASSES_ROOT, pszStr1, 1u, Data, 0);
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
    return LocalFree(lpReturnedString[0]);
  }
  return result;
}

```

## disassembly

```asm
0x1805b32c0  push    rbp
0x1805b32c2  push    rbx
0x1805b32c3  push    rsi
0x1805b32c4  push    rdi
0x1805b32c5  push    r12
0x1805b32c7  push    r13
0x1805b32c9  push    r14
0x1805b32cb  lea     rbp, [rsp-790h]
0x1805b32d3  sub     rsp, 890h
0x1805b32da  mov     rax, cs:__security_cookie
0x1805b32e1  xor     rax, rsp
0x1805b32e4  mov     [rbp+7C0h+var_40], rax
0x1805b32eb  xor     r12d, r12d
0x1805b32ee  lea     r9, [rsp+8C0h+lpReturnedString]
0x1805b32f3  mov     ebx, 1000h
0x1805b32f8  mov     [rsp+8C0h+lpReturnedString], r12
0x1805b32fd  mov     r8d, ebx
0x1805b3300  lea     esi, [r12+2Eh]
0x1805b3305  lea     edx, [rsi+12h]
0x1805b3308  mov     dword ptr [rsp+8C0h+pszStr1], esi
0x1805b330c  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1805b3311  test    eax, eax
0x1805b3313  js      loc_1805B36D5
0x1805b3319  mov     rdx, [rsp+8C0h+lpReturnedString]; lpReturnedString
0x1805b331e  lea     rcx, AppName; "Extensions"
0x1805b3325  mov     r8d, ebx; nSize
0x1805b3328  call    cs:__imp_GetProfileSectionW
0x1805b332f  nop     dword ptr [rax+rax+00h]
0x1805b3334  cmp     eax, 0FFEh
0x1805b3339  jge     loc_1805B36C4
0x1805b333f  mov     rdi, [rsp+8C0h+lpReturnedString]
0x1805b3344  mov     ebx, r12d
0x1805b3347  cmp     [rdi], r12w
0x1805b334b  jz      loc_1805B36C4
0x1805b3351  mov     r13d, 104h
0x1805b3357  mov     edx, 3Dh ; '='; wMatch
0x1805b335c  mov     rcx, rdi; pszStart
0x1805b335f  call    cs:__imp_StrChrW
0x1805b3366  nop     dword ptr [rax+rax+00h]
0x1805b336b  mov     r10, rax
0x1805b336e  test    rax, rax
0x1805b3371  jz      loc_1805B368E
0x1805b3377  mov     r9, rax
0x1805b337a  mov     [rsp+8C0h+pszStr1], si
0x1805b337f  sub     r9, rdi
0x1805b3382  lea     rcx, [rsp+8C0h+pszStr1+2]; unsigned __int16 *
0x1805b3387  sar     r9, 1; unsigned __int64
0x1805b338a  mov     r8, rdi; unsigned __int16 *
0x1805b338d  mov     edx, 103h; unsigned __int64
0x1805b3392  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1805b3397  or      rax, 0FFFFFFFFFFFFFFFFh
0x1805b339b  lea     r11, [rsp+8C0h+pszStr1]
0x1805b33a0  inc     rax
0x1805b33a3  cmp     [r11+rax*2], r12w
0x1805b33a8  jnz     short loc_1805B33A0
0x1805b33aa  cmp     rax, 4
0x1805b33ae  ja      loc_1805B368E
0x1805b33b4  lea     rdi, [r10+2]
0x1805b33b8  jmp     short loc_1805B33BE
0x1805b33ba  add     rdi, 2
0x1805b33be  cmp     word ptr [rdi], 20h ; ' '
0x1805b33c2  jz      short loc_1805B33BA
0x1805b33c4  mov     edx, 5Eh ; '^'; wMatch
0x1805b33c9  mov     rcx, rdi; pszStart
0x1805b33cc  call    cs:__imp_StrChrW
0x1805b33d3  nop     dword ptr [rax+rax+00h]
0x1805b33d8  mov     rsi, rax
0x1805b33db  test    rax, rax
0x1805b33de  jz      loc_1805B3689
0x1805b33e4  mov     r9, rax
0x1805b33e7  lea     rcx, [rbp+7C0h+Data]; unsigned __int16 *
0x1805b33ee  sub     r9, rdi
0x1805b33f1  mov     r8, rdi; unsigned __int16 *
0x1805b33f4  sar     r9, 1; unsigned __int64
0x1805b33f7  mov     rdx, r13; unsigned __int64
0x1805b33fa  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1805b33ff  lea     r8, [rbp+7C0h+Data]; unsigned __int16 *
0x1805b3406  mov     rdx, r13; unsigned __int64
0x1805b3409  lea     rcx, [rbp+7C0h+pszPath]; unsigned __int16 *
0x1805b3410  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805b3415  test    eax, eax
0x1805b3417  js      loc_1805B3689
0x1805b341d  lea     rcx, [rbp+7C0h+pszPath]; pszPath
0x1805b3424  call    cs:__imp_PathRemoveBlanksW
0x1805b342b  nop     dword ptr [rax+rax+00h]
0x1805b3430  lea     rcx, [rbp+7C0h+pszPath]; pszPath
0x1805b3437  call    PathIsExe
0x1805b343c  test    eax, eax
0x1805b343e  jz      loc_1805B3689
0x1805b3444  lea     rcx, [rsp+8C0h+pszStr1]; unsigned __int16 *
0x1805b3449  call    ?ReservedExtension@@YAHPEBG@Z; ReservedExtension(ushort const *)
0x1805b344e  test    eax, eax
0x1805b3450  jnz     loc_1805B3689
0x1805b3456  lea     r9, [rbp+7C0h+pvData]; unsigned __int16 *
0x1805b345d  mov     [rsp+8C0h+var_898], rdi; unsigned __int16 *
0x1805b3462  lea     rdx, [rbp+7C0h+Data]; unsigned __int16 *
0x1805b3469  lea     rcx, [rsp+8C0h+pszStr1]; unsigned __int16 *
0x1805b346e  call    ?Reg_ShellOpenForExtension@@YAHPEBGPEAGH1H0@Z; Reg_ShellOpenForExtension(ushort const *,ushort *,int,ushort *,int,ushort const *)
0x1805b3473  test    eax, eax
0x1805b3475  jz      short loc_1805B34C3
0x1805b3477  lea     r9, [rbp+7C0h+pvData]; pvData
0x1805b347e  mov     [rsp+8C0h+cbData], r13d; int
0x1805b3483  lea     r8, [rsp+8C0h+pszStr1]; lpValue
0x1805b3488  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1805b348f  lea     rdx, aSoftwareMicros_134; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1805b3496  call    RegGetValueString
0x1805b349b  test    eax, eax
0x1805b349d  jnz     loc_1805B3689
0x1805b34a3  mov     r9, rdi; unsigned __int16 *
0x1805b34a6  lea     r8, [rsp+8C0h+pszStr1]; unsigned __int16 *
0x1805b34ab  lea     rdx, aSoftwareMicros_134; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1805b34b2  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1805b34b9  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1805b34be  jmp     loc_1805B3689
0x1805b34c3  lea     rdx, aDgw; ".dgw"
0x1805b34ca  lea     rcx, [rsp+8C0h+pszStr1]; pszStr1
0x1805b34cf  call    cs:__imp_StrCmpICW
0x1805b34d6  nop     dword ptr [rax+rax+00h]
0x1805b34db  test    eax, eax
0x1805b34dd  jnz     short loc_1805B354A
0x1805b34df  lea     rcx, [rbp+7C0h+Data]; pszPath
0x1805b34e6  call    cs:__imp_PathFindFileNameW
0x1805b34ed  nop     dword ptr [rax+rax+00h]
0x1805b34f2  mov     rcx, rax; pszStr1
0x1805b34f5  lea     rdx, aDesignwExe; "designw.exe "
0x1805b34fc  call    cs:__imp_StrCmpICW
0x1805b3503  nop     dword ptr [rax+rax+00h]
0x1805b3508  test    eax, eax
0x1805b350a  jnz     short loc_1805B354A
0x1805b350c  lea     r9, aHdesign; "HDesign"
0x1805b3513  mov     [rsp+8C0h+cbData], r12d; cbData
0x1805b3518  lea     r8d, [rax+1]; dwType
0x1805b351c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1805b3523  lea     rdx, [rsp+8C0h+pszStr1]; lpSubKey
0x1805b3528  call    cs:__imp_RegSetValueW
0x1805b352f  nop     dword ptr [rax+rax+00h]
0x1805b3534  lea     r8, aHdesign; "HDesign"
0x1805b353b  mov     rdx, r13; unsigned __int64
0x1805b353e  lea     rcx, [rbp+7C0h+pvData]; unsigned __int16 *
0x1805b3545  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805b354a  lea     rdx, aWoc; ".WOC"
0x1805b3551  lea     rcx, [rsp+8C0h+pszStr1]; pszStr1
0x1805b3556  call    cs:__imp_StrCmpICW
0x1805b355d  nop     dword ptr [rax+rax+00h]
0x1805b3562  test    eax, eax
0x1805b3564  jnz     short loc_1805B3597
0x1805b3566  lea     rcx, [rbp+7C0h+Data]; pszPath
0x1805b356d  call    cs:__imp_PathFindFileNameW
0x1805b3574  nop     dword ptr [rax+rax+00h]
0x1805b3579  mov     rcx, rax; pszStr1
0x1805b357c  lea     rdx, aWinorgExe; "WINORG.EXE "
0x1805b3583  call    cs:__imp_StrCmpICW
0x1805b358a  nop     dword ptr [rax+rax+00h]
0x1805b358f  test    eax, eax
0x1805b3591  jz      loc_1805B3689
0x1805b3597  mov     r9, rdi; unsigned __int16 *
0x1805b359a  lea     r8, [rsp+8C0h+pszStr1]; unsigned __int16 *
0x1805b359f  lea     rdx, aSoftwareMicros_134; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1805b35a6  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1805b35ad  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1805b35b2  lea     r8, cText; "%1"
0x1805b35b9  mov     rdx, r13; unsigned __int64
0x1805b35bc  lea     rcx, [rbp+7C0h+Data]; unsigned __int16 *
0x1805b35c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1805b35c8  add     rsi, 2
0x1805b35cc  movzx   eax, word ptr [rsi]
0x1805b35cf  test    ax, ax
0x1805b35d2  jz      short loc_1805B3628
0x1805b35d4  lea     r14, [rsp+8C0h+pszStr1]
0x1805b35d9  movzx   ecx, ax; lpsz
0x1805b35dc  call    cs:__imp_CharLowerW
0x1805b35e3  nop     dword ptr [rax+rax+00h]
0x1805b35e8  movzx   ecx, word ptr [r14]; lpsz
0x1805b35ec  mov     rbx, rax
0x1805b35ef  call    cs:__imp_CharLowerW
0x1805b35f6  nop     dword ptr [rax+rax+00h]
0x1805b35fb  cmp     bx, ax
0x1805b35fe  jnz     short loc_1805B3610
0x1805b3600  add     rsi, 2
0x1805b3604  add     r14, 2
0x1805b3608  movzx   eax, word ptr [rsi]
0x1805b360b  test    ax, ax
0x1805b360e  jnz     short loc_1805B35D9
0x1805b3610  cmp     [rsi], r12w
0x1805b3614  jz      short loc_1805B3628
0x1805b3616  mov     r8, rsi; unsigned __int16 *
0x1805b3619  lea     rcx, [rbp+7C0h+Data]; unsigned __int16 *
0x1805b3620  mov     rdx, r13; unsigned __int64
0x1805b3623  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1805b3628  cmp     [rbp+7C0h+pvData], r12w
0x1805b3630  jz      short loc_1805B3646
0x1805b3632  lea     r8, [rbp+7C0h+pvData]; unsigned __int16 *
0x1805b3639  mov     rdx, r13; unsigned __int64
0x1805b363c  lea     rcx, [rsp+8C0h+pszStr1]; unsigned __int16 *
0x1805b3641  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1805b3646  lea     r8, aShellOpenComma; "\\shell\\open\\command"
0x1805b364d  mov     rdx, r13; unsigned __int64
0x1805b3650  lea     rcx, [rsp+8C0h+pszStr1]; unsigned __int16 *
0x1805b3655  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1805b365a  lea     r9, [rbp+7C0h+Data]; lpData
0x1805b3661  mov     [rsp+8C0h+cbData], r12d; cbData
0x1805b3666  mov     r8d, 1; dwType
0x1805b366c  lea     rdx, [rsp+8C0h+pszStr1]; lpSubKey
0x1805b3671  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1805b3678  call    cs:__imp_RegSetValueW
0x1805b367f  nop     dword ptr [rax+rax+00h]
0x1805b3684  mov     ebx, 1
0x1805b3689  mov     esi, 2Eh ; '.'
0x1805b368e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1805b3692  inc     rax
0x1805b3695  cmp     [rdi+rax*2], r12w
0x1805b369a  jnz     short loc_1805B3692
0x1805b369c  lea     rdi, [rdi+rax*2]
0x1805b36a0  add     rdi, 2
0x1805b36a4  cmp     [rdi], r12w
0x1805b36a8  jnz     loc_1805B3357
0x1805b36ae  test    ebx, ebx
0x1805b36b0  jz      short loc_1805B36C4
0x1805b36b2  xor     r9d, r9d; dwItem2
0x1805b36b5  xor     r8d, r8d; dwItem1
0x1805b36b8  xor     edx, edx; uFlags
0x1805b36ba  mov     ecx, 8000000h; wEventId
0x1805b36bf  call    SHChangeNotify
0x1805b36c4  mov     rcx, [rsp+8C0h+lpReturnedString]; hMem
0x1805b36c9  call    cs:__imp_LocalFree
0x1805b36d0  nop     dword ptr [rax+rax+00h]
0x1805b36d5  mov     rcx, [rbp+7C0h+var_40]
0x1805b36dc  xor     rcx, rsp; StackCookie
0x1805b36df  call    __security_check_cookie
0x1805b36e4  add     rsp, 890h
0x1805b36eb  pop     r14
0x1805b36ed  pop     r13
0x1805b36ef  pop     r12
0x1805b36f1  pop     rdi
0x1805b36f2  pop     rsi
0x1805b36f3  pop     rbx
0x1805b36f4  pop     rbp
0x1805b36f5  retn
```
