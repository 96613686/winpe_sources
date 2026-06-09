# RdVhd::Uvhd::CUvhdDiskManager::DestroyUvhdForUser(ushort const *,ushort const *)

- ea: `0x180052020`
- end: `0x1800521f8`
- name: `?DestroyUvhdForUser@CUvhdDiskManager@Uvhd@RdVhd@@UEBAJPEBG0@Z`
- size: `472`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdDiskManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004db0`
- `0x180019b38`
- `0x1800488e4`
- `0x180048b28`
- `0x180052020`
- `0x180052aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005217f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005217f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180052126`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180052126`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180052175`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180052175`

## string_xrefs

- `0x180052082`: `szUserSID`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::DestroyUvhdForUser(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  RdVhd::Uvhd::CUvhdDiskManager *v3; // rcx
  __int64 v4; // rdx
  const wchar_t *v5; // r9
  signed int UvhdFilePathForUser; // ebx
  RdVhd::Uvhd::CUvhdDiskManager *v7; // rcx
  __int64 v8; // rdx
  const WCHAR *v9; // rax
  const WCHAR *v10; // rax
  signed int LastError; // eax
  void **v13; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+28h] [rbp-30h]
  __int64 v15; // [rsp+2Ch] [rbp-2Ch]
  int v16; // [rsp+34h] [rbp-24h]
  __int64 v17; // [rsp+38h] [rbp-20h]
  int v18; // [rsp+40h] [rbp-18h]

  v15 = 128;
  v17 = 0;
  v16 = 0;
  v18 = 0x8000000;
  v14 = 0;
  v13 = &CPathString::`vftable';
  if ( !a2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v4 = 59;
    v5 = L"szUserSID";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v3 + 2), v4, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v5);
LABEL_7:
    UvhdFilePathForUser = -2147024809;
    goto LABEL_35;
  }
  if ( !a3 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v4 = 60;
    v5 = L"szUvhdShareUrl";
    goto LABEL_6;
  }
  UvhdFilePathForUser = RdVhd::Uvhd::CUvhdDiskManager::GetUvhdFilePathForUser(this, a2, a3, (struct CPathString *)&v13);
  if ( UvhdFilePathForUser >= 0 )
  {
    v9 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v13);
    if ( GetFileAttributesW(v9) == -1 )
    {
      UvhdFilePathForUser = -800325630;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 62;
        goto LABEL_34;
      }
    }
    else
    {
      v10 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v13);
      if ( !DeleteFileW(v10) )
      {
        LastError = GetLastError();
        UvhdFilePathForUser = LastError;
        if ( LastError && (LastError & 0xFFFF0000) == 0 )
        {
          if ( LastError > 0 )
            UvhdFilePathForUser = (unsigned __int16)LastError | 0x80070000;
          UvhdFilePathForUser = UvhdFilePathForUser & 0x8000FFFF | 0x504D0000;
        }
        if ( UvhdFilePathForUser < 0 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 63;
            goto LABEL_34;
          }
        }
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 61;
LABEL_34:
      WPP_SF_d(
        *((_QWORD *)v7 + 2),
        v8,
        WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
        (unsigned int)UvhdFilePathForUser);
    }
  }
LABEL_35:
  CPathString::~CPathString((CPathString *)&v13);
  return (unsigned int)UvhdFilePathForUser;
}

```

## disassembly

```asm
0x180052020  mov     rax, rsp
0x180052023  push    rbx
0x180052024  sub     rsp, 50h
0x180052028  mov     qword ptr [rax-2Ch], 80h
0x180052030  mov     qword ptr [rax-20h], 0
0x180052038  mov     dword ptr [rax-24h], 0
0x18005203f  mov     dword ptr [rax-18h], 8000000h
0x180052046  mov     dword ptr [rax-30h], 0
0x18005204d  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180052054  mov     [rsp+58h+var_38], rax
0x180052059  test    rdx, rdx
0x18005205c  jnz     short loc_1800520A3
0x18005205e  mov     rcx, cs:WPP_GLOBAL_Control
0x180052065  lea     rax, WPP_GLOBAL_Control
0x18005206c  cmp     rcx, rax
0x18005206f  jz      short loc_180052099
0x180052071  test    byte ptr [rcx+1Ch], 4
0x180052075  jz      short loc_180052099
0x180052077  cmp     byte ptr [rcx+19h], 2
0x18005207b  jb      short loc_180052099
0x18005207d  mov     edx, 3Bh ; ';'
0x180052082  lea     r9, aSzusersid_0; "szUserSID"
0x180052089  mov     rcx, [rcx+10h]
0x18005208d  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180052094  call    WPP_SF_S
0x180052099  mov     ebx, 80070057h
0x18005209e  jmp     loc_1800521E6
0x1800520a3  test    r8, r8
0x1800520a6  jnz     short loc_1800520D4
0x1800520a8  mov     rcx, cs:WPP_GLOBAL_Control; this
0x1800520af  lea     rax, WPP_GLOBAL_Control
0x1800520b6  cmp     rcx, rax
0x1800520b9  jz      short loc_180052099
0x1800520bb  test    byte ptr [rcx+1Ch], 4
0x1800520bf  jz      short loc_180052099
0x1800520c1  cmp     byte ptr [rcx+19h], 2
0x1800520c5  jb      short loc_180052099
0x1800520c7  lea     edx, [r8+3Ch]; unsigned __int16 *
0x1800520cb  lea     r9, aSzuvhdshareurl; "szUvhdShareUrl"
0x1800520d2  jmp     short loc_180052089
0x1800520d4  lea     r9, [rsp+58h+var_38]; struct CPathString *
0x1800520d9  call    ?GetUvhdFilePathForUser@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBG0PEAVCPathString@@@Z; RdVhd::Uvhd::CUvhdDiskManager::GetUvhdFilePathForUser(ushort const *,ushort const *,CPathString *)
0x1800520de  mov     ebx, eax
0x1800520e0  test    eax, eax
0x1800520e2  jns     short loc_180052119
0x1800520e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800520eb  lea     rax, WPP_GLOBAL_Control
0x1800520f2  cmp     rcx, rax
0x1800520f5  jz      loc_1800521E6
0x1800520fb  test    byte ptr [rcx+1Ch], 4
0x1800520ff  jz      loc_1800521E6
0x180052105  cmp     byte ptr [rcx+19h], 2
0x180052109  jb      loc_1800521E6
0x18005210f  mov     edx, 3Dh ; '='
0x180052114  jmp     loc_1800521D3
0x180052119  lea     rcx, [rsp+58h+var_38]
0x18005211e  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180052123  mov     rcx, rax; lpFileName
0x180052126  call    cs:__imp_GetFileAttributesW
0x18005212c  cmp     eax, 0FFFFFFFFh
0x18005212f  jnz     short loc_180052168
0x180052131  mov     ebx, 0D04C0002h
0x180052136  mov     rcx, cs:WPP_GLOBAL_Control
0x18005213d  lea     rax, WPP_GLOBAL_Control
0x180052144  cmp     rcx, rax
0x180052147  jz      loc_1800521E6
0x18005214d  test    byte ptr [rcx+1Ch], 4
0x180052151  jz      loc_1800521E6
0x180052157  cmp     byte ptr [rcx+19h], 2
0x18005215b  jb      loc_1800521E6
0x180052161  mov     edx, 3Eh ; '>'
0x180052166  jmp     short loc_1800521D3
0x180052168  lea     rcx, [rsp+58h+var_38]
0x18005216d  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180052172  mov     rcx, rax; lpFileName
0x180052175  call    cs:__imp_DeleteFileW
0x18005217b  test    eax, eax
0x18005217d  jnz     short loc_1800521E6
0x18005217f  call    cs:__imp_GetLastError
0x180052185  mov     ebx, eax
0x180052187  test    eax, eax
0x180052189  jz      short loc_1800521AB
0x18005218b  test    eax, 0FFFF0000h
0x180052190  jnz     short loc_1800521AB
0x180052192  test    eax, eax
0x180052194  jle     short loc_18005219F
0x180052196  movzx   ebx, ax
0x180052199  or      ebx, 80070000h
0x18005219f  and     ebx, 0D04DFFFFh
0x1800521a5  or      ebx, 504D0000h
0x1800521ab  test    ebx, ebx
0x1800521ad  jns     short loc_1800521E6
0x1800521af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800521b6  lea     rax, WPP_GLOBAL_Control
0x1800521bd  cmp     rcx, rax
0x1800521c0  jz      short loc_1800521E6
0x1800521c2  test    byte ptr [rcx+1Ch], 4
0x1800521c6  jz      short loc_1800521E6
0x1800521c8  cmp     byte ptr [rcx+19h], 2
0x1800521cc  jb      short loc_1800521E6
0x1800521ce  mov     edx, 3Fh ; '?'
0x1800521d3  mov     rcx, [rcx+10h]
0x1800521d7  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800521de  mov     r9d, ebx
0x1800521e1  call    WPP_SF_d
0x1800521e6  lea     rcx, [rsp+58h+var_38]; this
0x1800521eb  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800521f0  mov     eax, ebx
0x1800521f2  add     rsp, 50h
0x1800521f6  pop     rbx
0x1800521f7  retn
```
