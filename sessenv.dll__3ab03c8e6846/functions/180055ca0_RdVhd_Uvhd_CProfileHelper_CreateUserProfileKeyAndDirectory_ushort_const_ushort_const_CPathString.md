# RdVhd::Uvhd::CProfileHelper::CreateUserProfileKeyAndDirectory(ushort const *,ushort const *,CPathString *)

- ea: `0x180055ca0`
- end: `0x1800561b7`
- name: `?CreateUserProfileKeyAndDirectory@CProfileHelper@Uvhd@RdVhd@@UEBAJPEBG0PEAVCPathString@@@Z`
- size: `1303`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CProfileHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct CPathString *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180019b38`
- `0x180043df0`
- `0x1800488e4`
- `0x180048ab0`
- `0x180048b28`
- `0x1800554f0`
- `0x1800558bc`
- `0x180055ca0`
- `0x180056af4`
- `0x180057110`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055e5c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180055ed9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180055ed9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056131`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056131`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180055e52`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180055e52`

## string_xrefs

- `0x180055d4d`: `szUserSID`
- `0x180055dc6`: `pstrUserProfileDirectory`
- `0x180055e04`: `Check that there is no local profile FAILED; SID: %s`
- `0x180055e8b`: `ConvertStringSidToSidW() FAILED; SID: %s`
- `0x180055ee8`: `Invalid Sid! SID: %s`
- `0x180055f43`: `CreateUserProfileDirectoryName() FAILED; SID: %s`
- `0x180056017`: `CreateDirectoryForUser() FAILED; SID: %s`
- `0x18005608d`: `CreateUserProfileKey() FAILED; SID: %s`
- `0x1800560d9`: `pstrUserProfileDirectory->Set() FAILED; SID: %s`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CProfileHelper::CreateUserProfileKeyAndDirectory(
        RdVhd::Uvhd::CProfileHelper *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct CPathString *a4)
{
  RdVhd::Uvhd::CUvhdDiskManager *v8; // rcx
  __int64 v9; // rdx
  const wchar_t *v10; // r9
  int UserProfileDirectoryW; // ebx
  int v12; // r9d
  RdVhd::Uvhd::CUvhdDiskManager *v13; // rcx
  int v14; // edx
  signed int LastError; // eax
  RdVhd::Uvhd::CProfileHelper *v16; // rcx
  int v17; // eax
  __int64 v18; // rax
  __int64 (__fastcall *v19)(__int64, __int64, const unsigned __int16 *, __int64); // r10
  __int64 v20; // r11
  int v21; // eax
  const unsigned __int16 *v22; // rax
  RdVhd::Uvhd::CProfileHelper *v23; // rcx
  const BYTE *v24; // r10
  void *v25; // r11
  int v26; // eax
  int v27; // eax
  int v28; // edx
  int v29; // r8d
  void **v31; // [rsp+30h] [rbp-50h] BYREF
  int v32; // [rsp+38h] [rbp-48h]
  __int64 v33; // [rsp+3Ch] [rbp-44h]
  int v34; // [rsp+44h] [rbp-3Ch]
  __int64 v35; // [rsp+48h] [rbp-38h]
  int v36; // [rsp+50h] [rbp-30h]
  void **v37; // [rsp+58h] [rbp-28h] BYREF
  int v38; // [rsp+60h] [rbp-20h]
  __int64 v39; // [rsp+64h] [rbp-1Ch]
  int v40; // [rsp+6Ch] [rbp-14h]
  __int64 v41; // [rsp+70h] [rbp-10h]
  int v42; // [rsp+78h] [rbp-8h]
  PSID Sid; // [rsp+B8h] [rbp+38h] BYREF

  v39 = 128;
  v41 = 0;
  v40 = 0;
  v42 = 0x8000000;
  v36 = 0x8000000;
  v38 = 0;
  v37 = &CPathString::`vftable';
  v33 = 128;
  v35 = 0;
  v34 = 0;
  v32 = 0;
  v31 = &CPathString::`vftable';
  Sid = 0;
  if ( !a2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v9 = 58;
    v10 = L"szUserSID";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v8 + 2), v9, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, v10);
LABEL_7:
    UserProfileDirectoryW = -2147024809;
    goto LABEL_69;
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
    v9 = 59;
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
    v9 = 60;
    v10 = L"pstrUserProfileDirectory";
    goto LABEL_6;
  }
  UserProfileDirectoryW = RdVhd::Uvhd::CProfileHelper::GetUserProfileDirectoryW(this, a2, 1, (struct CPathString *)&v31);
  if ( UserProfileDirectoryW < 0 )
  {
    if ( (_WORD)UserProfileDirectoryW == 2 )
      UserProfileDirectoryW = 0;
  }
  else
  {
    UserProfileDirectoryW = -802357065;
  }
  _TraceNrmRdvVmEx(L"UVHD", UserProfileDirectoryW, L"Check that there is no local profile FAILED; SID: %s", a2);
  if ( UserProfileDirectoryW >= 0 )
  {
    if ( ConvertStringSidToSidW(a2, &Sid) )
      goto LABEL_83;
    LastError = GetLastError();
    UserProfileDirectoryW = LastError;
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        UserProfileDirectoryW = (unsigned __int16)LastError | 0x80070000;
      UserProfileDirectoryW = UserProfileDirectoryW & 0x8000FFFF | 0x502E0000;
    }
    _TraceNrmRdvVmEx(L"UVHD", UserProfileDirectoryW, L"ConvertStringSidToSidW() FAILED; SID: %s", a2);
    if ( UserProfileDirectoryW >= 0 )
    {
LABEL_83:
      if ( IsValidSid(Sid) )
      {
        UserProfileDirectoryW = RdVhd::Uvhd::CProfileHelper::CreateUserProfileDirectoryName(
                                  this,
                                  a3,
                                  (struct CPathString *)&v31);
        _TraceNrmRdvVmEx(L"UVHD", UserProfileDirectoryW, L"CreateUserProfileDirectoryName() FAILED; SID: %s", a2);
        if ( v17 >= 0 )
        {
          UserProfileDirectoryW = RdVhd::Uvhd::CProfileHelper::GetProfileKeyName(v16, a2, (struct CPathString *)&v37);
          if ( UserProfileDirectoryW >= 0 )
          {
            v18 = CBaseStringT<unsigned short>::PContents(&v31);
            UserProfileDirectoryW = v19(v20, v18, a2, 1);
            _TraceNrmRdvVmEx(L"UVHD", UserProfileDirectoryW, L"CreateDirectoryForUser() FAILED; SID: %s", a2);
            if ( v21 >= 0 )
            {
              CBaseStringT<unsigned short>::PContents(&v31);
              v22 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v37);
              UserProfileDirectoryW = RdVhd::Uvhd::CProfileHelper::CreateUserProfileKey(v23, v22, v25, v24);
              _TraceNrmRdvVmEx(L"UVHD", UserProfileDirectoryW, L"CreateUserProfileKey() FAILED; SID: %s", a2);
              if ( v26 >= 0 )
              {
                UserProfileDirectoryW = CBaseStringT<unsigned short>::Set<unsigned short>(a4, &v31);
                _TraceNrmRdvVmEx(L"UVHD", UserProfileDirectoryW, L"pstrUserProfileDirectory->Set() FAILED; SID: %s", a2);
                if ( v27 < 0 )
                {
                  v13 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v14 = 68;
                    goto LABEL_68;
                  }
                }
              }
              else
              {
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v14 = 67;
                  goto LABEL_68;
                }
              }
            }
            else
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v14 = 66;
                goto LABEL_68;
              }
            }
          }
          else if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              65,
              WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids,
              (unsigned int)UserProfileDirectoryW);
          }
        }
        else
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = 64;
            goto LABEL_68;
          }
        }
      }
      else
      {
        UserProfileDirectoryW = -2147024809;
        _TraceNrmRdvVmEx(L"UVHD", -2147024809, L"Invalid Sid! SID: %s", a2);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = 63;
          goto LABEL_68;
        }
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 62;
        goto LABEL_68;
      }
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 61;
LABEL_68:
      WPP_SF_Sd(
        *((_QWORD *)v13 + 2),
        v14,
        (unsigned int)WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids,
        v12,
        UserProfileDirectoryW);
    }
  }
LABEL_69:
  if ( Sid )
    LocalFree(Sid);
  if ( UserProfileDirectoryW < 0 )
  {
    v28 = HIWORD(UserProfileDirectoryW) & 0x7FF;
    if ( (UserProfileDirectoryW & 0x78000000) != 0x50000000 )
      v28 = 0;
    if ( !v28 )
    {
      v29 = (UserProfileDirectoryW >> 16) & 0x1FFF;
      if ( v29 == 7 || !v29 && (UserProfileDirectoryW & 0x10000000) == 0 )
      {
        UserProfileDirectoryW = (unsigned __int16)UserProfileDirectoryW;
        if ( (_WORD)UserProfileDirectoryW )
          UserProfileDirectoryW = (unsigned __int16)UserProfileDirectoryW | 0xD08D0000;
      }
    }
  }
  CPathString::~CPathString((CPathString *)&v31);
  CPathString::~CPathString((CPathString *)&v37);
  return (unsigned int)UserProfileDirectoryW;
}

```

## disassembly

```asm
0x180055ca0  mov     [rsp-28h+arg_0], rbx
0x180055ca5  mov     [rsp-28h+arg_10], rsi
0x180055caa  push    rbp
0x180055cab  push    rdi
0x180055cac  push    r13
0x180055cae  push    r14
0x180055cb0  push    r15
0x180055cb2  mov     rbp, rsp
0x180055cb5  sub     rsp, 80h
0x180055cbc  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180055cc3  mov     [rbp+var_1C], 80h
0x180055ccb  mov     r14, rcx
0x180055cce  mov     [rbp+var_10], 0
0x180055cd6  mov     ecx, 8000000h
0x180055cdb  mov     [rbp+var_14], 0
0x180055ce2  mov     [rbp+var_8], ecx
0x180055ce5  mov     r15, r9
0x180055ce8  mov     [rbp+var_30], ecx
0x180055ceb  mov     rsi, r8
0x180055cee  mov     rdi, rdx
0x180055cf1  mov     [rbp+var_20], 0
0x180055cf8  mov     [rbp+var_28], rax
0x180055cfc  mov     [rbp+var_44], 80h
0x180055d04  mov     [rbp+var_38], 0
0x180055d0c  mov     [rbp+var_3C], 0
0x180055d13  mov     [rbp+var_48], 0
0x180055d1a  mov     [rbp+var_50], rax
0x180055d1e  mov     [rbp+Sid], 0
0x180055d26  test    rdx, rdx
0x180055d29  jnz     short loc_180055D6E
0x180055d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055d32  lea     rax, WPP_GLOBAL_Control
0x180055d39  cmp     rcx, rax
0x180055d3c  jz      short loc_180055D64
0x180055d3e  test    byte ptr [rcx+1Ch], 4
0x180055d42  jz      short loc_180055D64
0x180055d44  cmp     byte ptr [rcx+19h], 2
0x180055d48  jb      short loc_180055D64
0x180055d4a  lea     edx, [rdi+3Ah]
0x180055d4d  lea     r9, aSzusersid_0; "szUserSID"
0x180055d54  mov     rcx, [rcx+10h]
0x180055d58  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x180055d5f  call    WPP_SF_S
0x180055d64  mov     ebx, 80070057h
0x180055d69  jmp     loc_180056128
0x180055d6e  test    rsi, rsi
0x180055d71  jnz     short loc_180055D9E
0x180055d73  mov     rcx, cs:WPP_GLOBAL_Control
0x180055d7a  lea     rax, WPP_GLOBAL_Control
0x180055d81  cmp     rcx, rax
0x180055d84  jz      short loc_180055D64
0x180055d86  test    byte ptr [rcx+1Ch], 4
0x180055d8a  jz      short loc_180055D64
0x180055d8c  cmp     byte ptr [rcx+19h], 2
0x180055d90  jb      short loc_180055D64
0x180055d92  lea     edx, [rsi+3Bh]
0x180055d95  lea     r9, aSzusername; "szUsername"
0x180055d9c  jmp     short loc_180055D54
0x180055d9e  test    r15, r15
0x180055da1  jnz     short loc_180055DCF
0x180055da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180055daa  lea     rax, WPP_GLOBAL_Control
0x180055db1  cmp     rcx, rax
0x180055db4  jz      short loc_180055D64
0x180055db6  test    byte ptr [rcx+1Ch], 4
0x180055dba  jz      short loc_180055D64
0x180055dbc  cmp     byte ptr [rcx+19h], 2
0x180055dc0  jb      short loc_180055D64
0x180055dc2  lea     edx, [r15+3Ch]; unsigned __int16 *
0x180055dc6  lea     r9, aPstruserprofil_1; "pstrUserProfileDirectory"
0x180055dcd  jmp     short loc_180055D54
0x180055dcf  lea     r9, [rbp+var_50]; struct CPathString *
0x180055dd3  mov     r8d, 1; int
0x180055dd9  mov     rcx, r14; this
0x180055ddc  call    ?GetUserProfileDirectoryW@CProfileHelper@Uvhd@RdVhd@@UEBAJPEBGHPEAVCPathString@@@Z; RdVhd::Uvhd::CProfileHelper::GetUserProfileDirectoryW(ushort const *,int,CPathString *)
0x180055de1  mov     ebx, eax
0x180055de3  test    eax, eax
0x180055de5  js      short loc_180055DEE
0x180055de7  mov     ebx, 0D02D00B7h
0x180055dec  jmp     short loc_180055DF7
0x180055dee  xor     eax, eax
0x180055df0  cmp     bx, 2
0x180055df4  cmovz   ebx, eax
0x180055df7  lea     r13, aUvhd; "UVHD"
0x180055dfe  mov     r9, rdi
0x180055e01  mov     rcx, r13; unsigned __int16 *
0x180055e04  lea     r8, aCheckThatThere; "Check that there is no local profile FA"...
0x180055e0b  mov     edx, ebx; int
0x180055e0d  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180055e12  test    ebx, ebx
0x180055e14  jns     short loc_180055E4B
0x180055e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e1d  lea     rax, WPP_GLOBAL_Control
0x180055e24  cmp     rcx, rax
0x180055e27  jz      loc_180056128
0x180055e2d  test    byte ptr [rcx+1Ch], 4
0x180055e31  jz      loc_180056128
0x180055e37  cmp     byte ptr [rcx+19h], 2
0x180055e3b  jb      loc_180056128
0x180055e41  mov     edx, 3Dh ; '='
0x180055e46  jmp     loc_180056114
0x180055e4b  lea     rdx, [rbp+Sid]; Sid
0x180055e4f  mov     rcx, rdi; StringSid
0x180055e52  call    cs:__imp_ConvertStringSidToSidW
0x180055e58  test    eax, eax
0x180055e5a  jnz     short loc_180055ED5
0x180055e5c  call    cs:__imp_GetLastError
0x180055e62  mov     ebx, eax
0x180055e64  test    eax, eax
0x180055e66  jz      short loc_180055E88
0x180055e68  test    eax, 0FFFF0000h
0x180055e6d  jnz     short loc_180055E88
0x180055e6f  test    eax, eax
0x180055e71  jle     short loc_180055E7C
0x180055e73  movzx   ebx, ax
0x180055e76  or      ebx, 80070000h
0x180055e7c  and     ebx, 0D02EFFFFh
0x180055e82  or      ebx, 502E0000h
0x180055e88  mov     r9, rdi
0x180055e8b  lea     r8, aConvertstrings_5; "ConvertStringSidToSidW() FAILED; SID: %"...
0x180055e92  mov     edx, ebx; int
0x180055e94  mov     rcx, r13; unsigned __int16 *
0x180055e97  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180055e9c  test    ebx, ebx
0x180055e9e  jns     short loc_180055ED5
0x180055ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ea7  lea     rax, WPP_GLOBAL_Control
0x180055eae  cmp     rcx, rax
0x180055eb1  jz      loc_180056128
0x180055eb7  test    byte ptr [rcx+1Ch], 4
0x180055ebb  jz      loc_180056128
0x180055ec1  cmp     byte ptr [rcx+19h], 2
0x180055ec5  jb      loc_180056128
0x180055ecb  mov     edx, 3Eh ; '>'
0x180055ed0  jmp     loc_180056114
0x180055ed5  mov     rcx, [rbp+Sid]; pSid
0x180055ed9  call    cs:__imp_IsValidSid
0x180055edf  test    eax, eax
0x180055ee1  jnz     short loc_180055F31
0x180055ee3  mov     ebx, 80070057h
0x180055ee8  lea     r8, aInvalidSidSidS; "Invalid Sid! SID: %s"
0x180055eef  mov     edx, ebx; int
0x180055ef1  mov     r9, rdi
0x180055ef4  mov     rcx, r13; unsigned __int16 *
0x180055ef7  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180055efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f03  lea     rax, WPP_GLOBAL_Control
0x180055f0a  cmp     rcx, rax
0x180055f0d  jz      loc_180056128
0x180055f13  test    byte ptr [rcx+1Ch], 4
0x180055f17  jz      loc_180056128
0x180055f1d  cmp     byte ptr [rcx+19h], 2
0x180055f21  jb      loc_180056128
0x180055f27  mov     edx, 3Fh ; '?'
0x180055f2c  jmp     loc_180056114
0x180055f31  lea     r8, [rbp+var_50]; struct CPathString *
0x180055f35  mov     rdx, rsi; unsigned __int16 *
0x180055f38  mov     rcx, r14; this
0x180055f3b  call    ?CreateUserProfileDirectoryName@CProfileHelper@Uvhd@RdVhd@@AEBAJPEBGPEAVCPathString@@@Z; RdVhd::Uvhd::CProfileHelper::CreateUserProfileDirectoryName(ushort const *,CPathString *)
0x180055f40  mov     r9, rdi
0x180055f43  lea     r8, aCreateuserprof; "CreateUserProfileDirectoryName() FAILED"...
0x180055f4a  mov     edx, eax; int
0x180055f4c  mov     rcx, r13; unsigned __int16 *
0x180055f4f  mov     ebx, eax
0x180055f51  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180055f56  test    eax, eax
0x180055f58  jns     short loc_180055F8F
0x180055f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180055f61  lea     rax, WPP_GLOBAL_Control
0x180055f68  cmp     rcx, rax
0x180055f6b  jz      loc_180056128
0x180055f71  test    byte ptr [rcx+1Ch], 4
0x180055f75  jz      loc_180056128
0x180055f7b  cmp     byte ptr [rcx+19h], 2
0x180055f7f  jb      loc_180056128
0x180055f85  mov     edx, 40h ; '@'
0x180055f8a  jmp     loc_180056114
0x180055f8f  lea     r8, [rbp+var_28]; struct CPathString *
0x180055f93  mov     rdx, rdi; unsigned __int16 *
0x180055f96  call    ?GetProfileKeyName@CProfileHelper@Uvhd@RdVhd@@AEBAJPEBGAEAVCPathString@@@Z; RdVhd::Uvhd::CProfileHelper::GetProfileKeyName(ushort const *,CPathString &)
0x180055f9b  mov     ebx, eax
0x180055f9d  test    eax, eax
0x180055f9f  jns     short loc_180055FE9
0x180055fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180055fa8  lea     rax, WPP_GLOBAL_Control
0x180055faf  cmp     rcx, rax
0x180055fb2  jz      loc_180056128
0x180055fb8  test    byte ptr [rcx+1Ch], 4
0x180055fbc  jz      loc_180056128
0x180055fc2  cmp     byte ptr [rcx+19h], 2
0x180055fc6  jb      loc_180056128
0x180055fcc  mov     rcx, [rcx+10h]
0x180055fd0  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x180055fd7  mov     edx, 41h ; 'A'
0x180055fdc  mov     r9d, ebx
0x180055fdf  call    WPP_SF_d
0x180055fe4  jmp     loc_180056128
0x180055fe9  mov     r11, [r14+8]
0x180055fed  lea     rcx, [rbp+var_50]
0x180055ff1  mov     rax, [r11]
0x180055ff4  mov     r10, [rax+18h]
0x180055ff8  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180055ffd  mov     rdx, rax
0x180056000  mov     r9d, 1
0x180056006  mov     rax, r10
0x180056009  mov     r8, rdi
0x18005600c  mov     rcx, r11
0x18005600f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056014  mov     r9, rdi
0x180056017  lea     r8, aCreatedirector_2; "CreateDirectoryForUser() FAILED; SID: %"...
0x18005601e  mov     edx, eax; int
0x180056020  mov     rcx, r13; unsigned __int16 *
0x180056023  mov     ebx, eax
0x180056025  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18005602a  test    eax, eax
0x18005602c  jns     short loc_180056063
0x18005602e  mov     rcx, cs:WPP_GLOBAL_Control
0x180056035  lea     rax, WPP_GLOBAL_Control
0x18005603c  cmp     rcx, rax
0x18005603f  jz      loc_180056128
0x180056045  test    byte ptr [rcx+1Ch], 4
0x180056049  jz      loc_180056128
0x18005604f  cmp     byte ptr [rcx+19h], 2
0x180056053  jb      loc_180056128
0x180056059  mov     edx, 42h ; 'B'
0x18005605e  jmp     loc_180056114
0x180056063  lea     rcx, [rbp+var_50]
0x180056067  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18005606c  mov     r11, [rbp+Sid]
0x180056070  lea     rcx, [rbp+var_28]
0x180056074  mov     r10, rax
0x180056077  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18005607c  mov     r9, r10; unsigned __int16 *
0x18005607f  mov     r8, r11; void *
0x180056082  mov     rdx, rax; unsigned __int16 *
0x180056085  call    ?CreateUserProfileKey@CProfileHelper@Uvhd@RdVhd@@AEBAJPEBGPEAX0@Z; RdVhd::Uvhd::CProfileHelper::CreateUserProfileKey(ushort const *,void *,ushort const *)
0x18005608a  mov     r9, rdi
0x18005608d  lea     r8, aCreateuserprof_0; "CreateUserProfileKey() FAILED; SID: %s"
0x180056094  mov     edx, eax; int
0x180056096  mov     rcx, r13; unsigned __int16 *
0x180056099  mov     ebx, eax
0x18005609b  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800560a0  test    eax, eax
0x1800560a2  jns     short loc_1800560CA
0x1800560a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560ab  lea     rax, WPP_GLOBAL_Control
0x1800560b2  cmp     rcx, rax
0x1800560b5  jz      short loc_180056128
0x1800560b7  test    byte ptr [rcx+1Ch], 4
0x1800560bb  jz      short loc_180056128
0x1800560bd  cmp     byte ptr [rcx+19h], 2
0x1800560c1  jb      short loc_180056128
0x1800560c3  mov     edx, 43h ; 'C'
0x1800560c8  jmp     short loc_180056114
0x1800560ca  lea     rdx, [rbp+var_50]
0x1800560ce  mov     rcx, r15
0x1800560d1  call    ??$Set@G@?$CBaseStringT@G@@QEAAJAEBV0@@Z; CBaseStringT<ushort>::Set<ushort>(CBaseStringT<ushort> const &)
0x1800560d6  mov     r9, rdi
0x1800560d9  lea     r8, aPstruserprofil_0; "pstrUserProfileDirectory->Set() FAILED;"...
0x1800560e0  mov     edx, eax; int
0x1800560e2  mov     rcx, r13; unsigned __int16 *
0x1800560e5  mov     ebx, eax
0x1800560e7  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800560ec  test    eax, eax
0x1800560ee  jns     short loc_180056128
0x1800560f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800560f7  lea     rax, WPP_GLOBAL_Control
0x1800560fe  cmp     rcx, rax
0x180056101  jz      short loc_180056128
0x180056103  test    byte ptr [rcx+1Ch], 4
0x180056107  jz      short loc_180056128
0x180056109  cmp     byte ptr [rcx+19h], 2
0x18005610d  jb      short loc_180056128
0x18005610f  mov     edx, 44h ; 'D'
0x180056114  mov     rcx, [rcx+10h]
0x180056118  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x18005611f  mov     [rsp+80h+var_60], ebx
0x180056123  call    WPP_SF_Sd
0x180056128  mov     rcx, [rbp+Sid]; hMem
0x18005612c  test    rcx, rcx
0x18005612f  jz      short loc_180056137
0x180056131  call    cs:__imp_LocalFree
0x180056137  test    ebx, ebx
0x180056139  jns     short loc_180056187
0x18005613b  xor     eax, eax
0x18005613d  mov     r8d, ebx
0x180056140  sar     r8d, 10h
0x180056144  mov     ecx, ebx
0x180056146  and     ecx, 78000000h
0x18005614c  mov     edx, r8d
0x18005614f  and     edx, 7FFh
0x180056155  cmp     ecx, 50000000h
0x18005615b  cmovnz  edx, eax
0x18005615e  test    edx, edx
0x180056160  jnz     short loc_180056187
0x180056162  and     r8d, 1FFFh
0x180056169  cmp     r8d, 7
0x18005616d  jz      short loc_18005617A
0x18005616f  test    r8d, r8d
0x180056172  jnz     short loc_180056187
  ... truncated ...
```
