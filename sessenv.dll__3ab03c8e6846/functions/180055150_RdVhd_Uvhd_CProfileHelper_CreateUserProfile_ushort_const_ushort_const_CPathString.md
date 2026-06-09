# RdVhd::Uvhd::CProfileHelper::CreateUserProfile(ushort const *,ushort const *,CPathString *)

- ea: `0x180055150`
- end: `0x1800554e7`
- name: `?CreateUserProfile@CProfileHelper@Uvhd@RdVhd@@UEBAJPEBG0PEAVCPathString@@@Z`
- size: `919`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CProfileHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct CPathString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180054fe0`

## callees

- `0x1800141e8`
- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x180032808`
- `0x1800488e4`
- `0x180048b28`
- `0x180055150`
- `0x180057110`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180055224`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180055224`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800552b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800552b6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005547b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005547b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800552c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800552c4`

## string_xrefs

- `0x180055196`: `szUserSID`
- `0x18005520f`: `pstrUserProfileDirectory`
- `0x18005521b`: `userenv.dll`
- `0x1800552ac`: `CreateProfile`
- `0x1800553ad`: `Local User Profile for user %s already exists, use existing directory`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CProfileHelper::CreateUserProfile(
        RdVhd::Uvhd::CProfileHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct CPathString *a4)
{
  RdVhd::Uvhd::CUvhdDiskManager *v8; // rcx
  __int64 v9; // rdx
  const wchar_t *v10; // r9
  signed int UserProfileDirectoryW; // ebx
  HMODULE Library; // rbp
  signed int LastError; // eax
  FARPROC ProcAddress; // r15
  signed int v15; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v16; // rcx
  __int64 v17; // rdx
  unsigned int BufferLength; // esi
  __int64 v19; // rcx
  __int64 Buffer; // rax
  int v21; // edx
  int v22; // r8d

  if ( !a2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 47;
    v10 = L"szUserSID";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v8 + 2), v9, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, v10);
LABEL_7:
    LOWORD(UserProfileDirectoryW) = 87;
    return (unsigned __int16)UserProfileDirectoryW | 0xD08C0000;
  }
  if ( !a3 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 48;
    v10 = L"szUsername";
    goto LABEL_6;
  }
  if ( !a4 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 49;
    v10 = L"pstrUserProfileDirectory";
    goto LABEL_6;
  }
  Library = LoadLibraryExW(L"userenv.dll", 0, 0);
  if ( Library )
    goto LABEL_29;
  LastError = GetLastError();
  UserProfileDirectoryW = LastError;
  if ( LastError && (LastError & 0xFFFF0000) == 0 )
  {
    if ( LastError > 0 )
      UserProfileDirectoryW = (unsigned __int16)LastError | 0x80070000;
    UserProfileDirectoryW = UserProfileDirectoryW & 0x8000FFFF | 0x502B0000;
  }
  if ( UserProfileDirectoryW >= 0 )
  {
LABEL_29:
    ProcAddress = GetProcAddress(Library, "CreateProfile");
    if ( ProcAddress )
      goto LABEL_40;
    v15 = GetLastError();
    UserProfileDirectoryW = v15;
    if ( v15 && (v15 & 0xFFFF0000) == 0 )
    {
      if ( v15 > 0 )
        UserProfileDirectoryW = (unsigned __int16)v15 | 0x80070000;
      UserProfileDirectoryW = UserProfileDirectoryW & 0x8000FFFF | 0x502C0000;
    }
    if ( UserProfileDirectoryW >= 0 )
    {
LABEL_40:
      BufferLength = 260;
      UserProfileDirectoryW = CBaseStringT<unsigned short>::EnsureSpace(a4, 260);
      if ( UserProfileDirectoryW >= 0 )
      {
        if ( (unsigned int)CBaseStringT<unsigned short>::GetBufferLength(a4) < 0x104 )
          BufferLength = CBaseStringT<unsigned short>::GetBufferLength(v19);
        Buffer = CBaseStringT<unsigned short>::GetBuffer(a4);
        UserProfileDirectoryW = ((__int64 (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, __int64, _QWORD))ProcAddress)(
                                  a2,
                                  a3,
                                  Buffer,
                                  BufferLength);
        if ( UserProfileDirectoryW == -2147024713 )
        {
          _TraceNrmRdvVmEx(
            L"UVHD",
            -2147024713,
            L"Local User Profile for user %s already exists, use existing directory",
            a3);
          UserProfileDirectoryW = RdVhd::Uvhd::CProfileHelper::GetUserProfileDirectoryW(this, a2, 1, a4);
          if ( UserProfileDirectoryW < 0 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v17 = 53;
              goto LABEL_63;
            }
            goto LABEL_64;
          }
        }
        else if ( UserProfileDirectoryW < 0 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v17 = 54;
            goto LABEL_63;
          }
          goto LABEL_64;
        }
        UserProfileDirectoryW = CBaseStringT<unsigned short>::SetLength(a4);
        if ( UserProfileDirectoryW < 0 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v17 = 55;
            goto LABEL_63;
          }
        }
        goto LABEL_64;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 52;
        goto LABEL_63;
      }
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = 51;
LABEL_63:
        WPP_SF_d(
          *((_QWORD *)v16 + 2),
          v17,
          WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids,
          (unsigned int)UserProfileDirectoryW);
      }
    }
LABEL_64:
    if ( Library )
      FreeLibrary(Library);
    if ( UserProfileDirectoryW >= 0 )
      return (unsigned int)UserProfileDirectoryW;
    goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids,
      (unsigned int)UserProfileDirectoryW);
  }
LABEL_67:
  v21 = HIWORD(UserProfileDirectoryW) & 0x7FF;
  if ( (UserProfileDirectoryW & 0x78000000) != 0x50000000 )
    v21 = 0;
  if ( !v21 )
  {
    v22 = (UserProfileDirectoryW >> 16) & 0x1FFF;
    if ( v22 == 7 || !v22 && (UserProfileDirectoryW & 0x10000000) == 0 )
    {
      UserProfileDirectoryW = (unsigned __int16)UserProfileDirectoryW;
      if ( (_WORD)UserProfileDirectoryW )
        return (unsigned __int16)UserProfileDirectoryW | 0xD08C0000;
    }
  }
  return (unsigned int)UserProfileDirectoryW;
}

```

## disassembly

```asm
0x180055150  push    rbx
0x180055152  push    rbp
0x180055153  push    rsi
0x180055154  push    rdi
0x180055155  push    r12
0x180055157  push    r13
0x180055159  push    r14
0x18005515b  push    r15
0x18005515d  sub     rsp, 38h
0x180055161  mov     rdi, r9
0x180055164  mov     r14, r8
0x180055167  mov     r12, rdx
0x18005516a  mov     r13, rcx
0x18005516d  test    rdx, rdx
0x180055170  jnz     short loc_1800551B7
0x180055172  mov     rcx, cs:WPP_GLOBAL_Control
0x180055179  lea     rax, WPP_GLOBAL_Control
0x180055180  cmp     rcx, rax
0x180055183  jz      short loc_1800551AD
0x180055185  test    byte ptr [rcx+1Ch], 4
0x180055189  jz      short loc_1800551AD
0x18005518b  cmp     byte ptr [rcx+19h], 2
0x18005518f  jb      short loc_1800551AD
0x180055191  lea     edx, [r12+2Fh]
0x180055196  lea     r9, aSzusersid_0; "szUserSID"
0x18005519d  mov     rcx, [rcx+10h]
0x1800551a1  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x1800551a8  call    WPP_SF_S
0x1800551ad  mov     ebx, 57h ; 'W'
0x1800551b2  jmp     loc_1800554CB
0x1800551b7  test    r14, r14
0x1800551ba  jnz     short loc_1800551E8
0x1800551bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800551c3  lea     rax, WPP_GLOBAL_Control
0x1800551ca  cmp     rcx, rax
0x1800551cd  jz      short loc_1800551AD
0x1800551cf  test    byte ptr [rcx+1Ch], 4
0x1800551d3  jz      short loc_1800551AD
0x1800551d5  cmp     byte ptr [rcx+19h], 2
0x1800551d9  jb      short loc_1800551AD
0x1800551db  lea     edx, [r14+30h]
0x1800551df  lea     r9, aSzusername; "szUsername"
0x1800551e6  jmp     short loc_18005519D
0x1800551e8  test    rdi, rdi
0x1800551eb  jnz     short loc_180055218
0x1800551ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800551f4  lea     rax, WPP_GLOBAL_Control
0x1800551fb  cmp     rcx, rax
0x1800551fe  jz      short loc_1800551AD
0x180055200  test    byte ptr [rcx+1Ch], 4
0x180055204  jz      short loc_1800551AD
0x180055206  cmp     byte ptr [rcx+19h], 2
0x18005520a  jb      short loc_1800551AD
0x18005520c  lea     edx, [rdi+31h]
0x18005520f  lea     r9, aPstruserprofil_1; "pstrUserProfileDirectory"
0x180055216  jmp     short loc_18005519D
0x180055218  xor     r8d, r8d; dwFlags
0x18005521b  lea     rcx, aUserenvDll_0; "userenv.dll"
0x180055222  xor     edx, edx; hFile
0x180055224  call    cs:__imp_LoadLibraryExW
0x18005522a  mov     rbp, rax
0x18005522d  mov     esi, 0FFFF0000h
0x180055232  test    rax, rax
0x180055235  jnz     short loc_1800552AC
0x180055237  call    cs:__imp_GetLastError
0x18005523d  mov     ebx, eax
0x18005523f  test    eax, eax
0x180055241  jz      short loc_180055260
0x180055243  test    esi, eax
0x180055245  jnz     short loc_180055260
0x180055247  test    eax, eax
0x180055249  jle     short loc_180055254
0x18005524b  movzx   ebx, ax
0x18005524e  or      ebx, 80070000h
0x180055254  and     ebx, 0D02BFFFFh
0x18005525a  or      ebx, 502B0000h
0x180055260  test    ebx, ebx
0x180055262  jns     short loc_1800552AC
0x180055264  mov     rcx, cs:WPP_GLOBAL_Control
0x18005526b  lea     rax, WPP_GLOBAL_Control
0x180055272  cmp     rcx, rax
0x180055275  jz      loc_180055485
0x18005527b  test    byte ptr [rcx+1Ch], 4
0x18005527f  jz      loc_180055485
0x180055285  cmp     byte ptr [rcx+19h], 2
0x180055289  jb      loc_180055485
0x18005528f  mov     rcx, [rcx+10h]
0x180055293  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x18005529a  mov     edx, 32h ; '2'
0x18005529f  mov     r9d, ebx
0x1800552a2  call    WPP_SF_d
0x1800552a7  jmp     loc_180055485
0x1800552ac  lea     rdx, aCreateprofile; "CreateProfile"
0x1800552b3  mov     rcx, rbp; hModule
0x1800552b6  call    cs:__imp_GetProcAddress
0x1800552bc  mov     r15, rax
0x1800552bf  test    rax, rax
0x1800552c2  jnz     short loc_180055326
0x1800552c4  call    cs:__imp_GetLastError
0x1800552ca  mov     ebx, eax
0x1800552cc  test    eax, eax
0x1800552ce  jz      short loc_1800552ED
0x1800552d0  test    esi, eax
0x1800552d2  jnz     short loc_1800552ED
0x1800552d4  test    eax, eax
0x1800552d6  jle     short loc_1800552E1
0x1800552d8  movzx   ebx, ax
0x1800552db  or      ebx, 80070000h
0x1800552e1  and     ebx, 0D02CFFFFh
0x1800552e7  or      ebx, 502C0000h
0x1800552ed  test    ebx, ebx
0x1800552ef  jns     short loc_180055326
0x1800552f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800552f8  lea     rax, WPP_GLOBAL_Control
0x1800552ff  cmp     rcx, rax
0x180055302  jz      loc_180055473
0x180055308  test    byte ptr [rcx+1Ch], 4
0x18005530c  jz      loc_180055473
0x180055312  cmp     byte ptr [rcx+19h], 2
0x180055316  jb      loc_180055473
0x18005531c  mov     edx, 33h ; '3'
0x180055321  jmp     loc_180055460
0x180055326  mov     esi, 104h
0x18005532b  mov     rcx, rdi
0x18005532e  mov     edx, esi
0x180055330  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180055335  mov     ebx, eax
0x180055337  test    eax, eax
0x180055339  jns     short loc_180055370
0x18005533b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055342  lea     rax, WPP_GLOBAL_Control
0x180055349  cmp     rcx, rax
0x18005534c  jz      loc_180055473
0x180055352  test    byte ptr [rcx+1Ch], 4
0x180055356  jz      loc_180055473
0x18005535c  cmp     byte ptr [rcx+19h], 2
0x180055360  jb      loc_180055473
0x180055366  mov     edx, 34h ; '4'
0x18005536b  jmp     loc_180055460
0x180055370  mov     rcx, rdi
0x180055373  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180055378  cmp     eax, esi
0x18005537a  jnb     short loc_180055383
0x18005537c  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x180055381  mov     esi, eax
0x180055383  mov     rcx, rdi
0x180055386  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x18005538b  mov     r8, rax
0x18005538e  mov     r9d, esi
0x180055391  mov     rax, r15
0x180055394  mov     rdx, r14
0x180055397  mov     rcx, r12
0x18005539a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005539f  mov     edx, 800700B7h; int
0x1800553a4  mov     ebx, eax
0x1800553a6  cmp     eax, edx
0x1800553a8  jnz     short loc_180055404
0x1800553aa  mov     r9, r14
0x1800553ad  lea     r8, aLocalUserProfi_1; "Local User Profile for user %s already "...
0x1800553b4  lea     rcx, aUvhd; "UVHD"
0x1800553bb  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800553c0  mov     r9, rdi; struct CPathString *
0x1800553c3  mov     r8d, 1; int
0x1800553c9  mov     rdx, r12; unsigned __int16 *
0x1800553cc  mov     rcx, r13; this
0x1800553cf  call    ?GetUserProfileDirectoryW@CProfileHelper@Uvhd@RdVhd@@UEBAJPEBGHPEAVCPathString@@@Z; RdVhd::Uvhd::CProfileHelper::GetUserProfileDirectoryW(ushort const *,int,CPathString *)
0x1800553d4  mov     ebx, eax
0x1800553d6  test    eax, eax
0x1800553d8  jns     short loc_18005542E
0x1800553da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800553e1  lea     rax, WPP_GLOBAL_Control
0x1800553e8  cmp     rcx, rax
0x1800553eb  jz      loc_180055473
0x1800553f1  test    byte ptr [rcx+1Ch], 4
0x1800553f5  jz      short loc_180055473
0x1800553f7  cmp     byte ptr [rcx+19h], 2
0x1800553fb  jb      short loc_180055473
0x1800553fd  mov     edx, 35h ; '5'
0x180055402  jmp     short loc_180055460
0x180055404  test    ebx, ebx
0x180055406  jns     short loc_18005542E
0x180055408  mov     rcx, cs:WPP_GLOBAL_Control
0x18005540f  lea     rax, WPP_GLOBAL_Control
0x180055416  cmp     rcx, rax
0x180055419  jz      short loc_180055473
0x18005541b  test    byte ptr [rcx+1Ch], 4
0x18005541f  jz      short loc_180055473
0x180055421  cmp     byte ptr [rcx+19h], 2
0x180055425  jb      short loc_180055473
0x180055427  mov     edx, 36h ; '6'
0x18005542c  jmp     short loc_180055460
0x18005542e  mov     rcx, rdi
0x180055431  call    ?SetLength@?$CBaseStringT@G@@QEAAJXZ; CBaseStringT<ushort>::SetLength(void)
0x180055436  mov     ebx, eax
0x180055438  test    eax, eax
0x18005543a  jns     short loc_180055473
0x18005543c  mov     rcx, cs:WPP_GLOBAL_Control
0x180055443  lea     rax, WPP_GLOBAL_Control
0x18005544a  cmp     rcx, rax
0x18005544d  jz      short loc_180055473
0x18005544f  test    byte ptr [rcx+1Ch], 4
0x180055453  jz      short loc_180055473
0x180055455  cmp     byte ptr [rcx+19h], 2
0x180055459  jb      short loc_180055473
0x18005545b  mov     edx, 37h ; '7'
0x180055460  mov     rcx, [rcx+10h]
0x180055464  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x18005546b  mov     r9d, ebx
0x18005546e  call    WPP_SF_d
0x180055473  test    rbp, rbp
0x180055476  jz      short loc_180055481
0x180055478  mov     rcx, rbp; hLibModule
0x18005547b  call    cs:__imp_FreeLibrary
0x180055481  test    ebx, ebx
0x180055483  jns     short loc_1800554D4
0x180055485  xor     eax, eax
0x180055487  mov     r8d, ebx
0x18005548a  sar     r8d, 10h
0x18005548e  mov     ecx, ebx
0x180055490  and     ecx, 78000000h
0x180055496  mov     edx, r8d
0x180055499  and     edx, 7FFh
0x18005549f  cmp     ecx, 50000000h
0x1800554a5  cmovnz  edx, eax
0x1800554a8  test    edx, edx
0x1800554aa  jnz     short loc_1800554D4
0x1800554ac  and     r8d, 1FFFh
0x1800554b3  cmp     r8d, 7
0x1800554b7  jz      short loc_1800554C4
0x1800554b9  test    r8d, r8d
0x1800554bc  jnz     short loc_1800554D4
0x1800554be  bt      ebx, 1Ch
0x1800554c2  jb      short loc_1800554D4
0x1800554c4  movzx   ebx, bx
0x1800554c7  test    ebx, ebx
0x1800554c9  jz      short loc_1800554D4
0x1800554cb  movzx   ebx, bx
0x1800554ce  or      ebx, 0D08C0000h
0x1800554d4  mov     eax, ebx
0x1800554d6  add     rsp, 38h
0x1800554da  pop     r15
0x1800554dc  pop     r14
0x1800554de  pop     r13
0x1800554e0  pop     r12
0x1800554e2  pop     rdi
0x1800554e3  pop     rsi
0x1800554e4  pop     rbp
0x1800554e5  pop     rbx
0x1800554e6  retn
```
