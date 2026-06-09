# RdVhd::Uvhd::CDirectoryHelper::MoveIntoCleanupFolder(ushort const *)

- ea: `0x18004eb08`
- end: `0x18004ef23`
- name: `?MoveIntoCleanupFolder@CDirectoryHelper@Uvhd@RdVhd@@AEAAJPEBG@Z`
- size: `1051`
- prototype: `int(RdVhd::Uvhd::CDirectoryHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18004da10`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x1800198a4`
- `0x180019b38`
- `0x18001a280`
- `0x18003114c`
- `0x180035d40`
- `0x1800488e4`
- `0x180048944`
- `0x180048b28`
- `0x18004e2a0`
- `0x18004eb08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18004ec17`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18004ec17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004edab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004edab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ed81`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ed9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ee35`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ee51`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ed81`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ed9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ee35`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ee51`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004ee2f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004ee2f`
- `RPCRT4!RpcStringFreeW` at `0x18004eec1`
- `RPCRT4!RpcStringFreeW` at `0x18004eec1`
- `RPCRT4!UuidToStringW` at `0x18004ecdc`
- `RPCRT4!UuidToStringW` at `0x18004ecdc`
- `RPCRT4!UuidCreate` at `0x18004ec77`
- `RPCRT4!UuidCreate` at `0x18004ec77`

## string_xrefs

- `0x18004ebaf`: `szPath`
- `0x18004edd2`: `MoveFile(%s, %s) failed with AccessDenied. Sleeping and retrying.`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CDirectoryHelper::MoveIntoCleanupFolder(
        RdVhd::Uvhd::CDirectoryHelper *this,
        const unsigned __int16 *a2)
{
  signed int v4; // edi
  int v5; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  wchar_t *v9; // rax
  const unsigned __int16 *v10; // rax
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  const unsigned __int16 *v13; // rax
  RdVhd::Uvhd::CDirectoryHelper *v14; // rcx
  int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // rax
  const unsigned __int16 *v18; // rax
  RdVhd::Uvhd::CDirectoryHelper *v19; // rcx
  int v20; // ebx
  signed int LastError; // eax
  int v22; // eax
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-50h] BYREF
  void **v25; // [rsp+38h] [rbp-48h] BYREF
  int v26; // [rsp+40h] [rbp-40h]
  __int64 v27; // [rsp+44h] [rbp-3Ch]
  int v28; // [rsp+4Ch] [rbp-34h]
  __int64 v29; // [rsp+50h] [rbp-30h]
  int v30; // [rsp+58h] [rbp-28h]
  UUID Uuid; // [rsp+60h] [rbp-20h] BYREF

  StringUuid = 0;
  v27 = 128;
  Uuid = 0;
  v25 = &CPathString::`vftable';
  v29 = 0;
  v28 = 0;
  v30 = 0x8000000;
  v26 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, L"szPath");
    }
    v4 = -2147024809;
    goto LABEL_65;
  }
  v5 = RdVhd::Uvhd::CDirectoryHelper::EnsureCleanupFolder(this);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v7 = 81;
LABEL_12:
    v8 = (unsigned int)v5;
LABEL_64:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids, v8);
    goto LABEL_65;
  }
  v9 = wcsrchr(a2, 0x5Cu);
  if ( v9 )
    v10 = v9 + 1;
  else
    v10 = a2;
  v5 = CPathString::BuildPath((CPathString *)&v25, (RdVhd::Uvhd::CDirectoryHelper *)((char *)this + 8), v10);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v7 = 82;
    goto LABEL_12;
  }
  v11 = UuidCreate(&Uuid);
  v4 = v11;
  if ( v11 )
  {
    if ( (v11 & 0xFFFF0000) == 0 )
    {
      if ( v11 > 0 )
        v4 = v11 | 0x80070000;
      v4 = v4 & 0x8000FFFF | 0x500E0000;
    }
    if ( v4 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v7 = 83;
      goto LABEL_63;
    }
  }
  v12 = UuidToStringW(&Uuid, &StringUuid);
  v4 = v12;
  if ( v12 )
  {
    if ( (v12 & 0xFFFF0000) == 0 )
    {
      if ( v12 > 0 )
        v4 = v12 | 0x80070000;
      v4 = v4 & 0x8000FFFF | 0x500F0000;
    }
    if ( v4 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v7 = 84;
      goto LABEL_63;
    }
  }
  v4 = CBaseStringT<unsigned short>::Append(&v25, StringUuid);
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_65;
    }
    v7 = 85;
    goto LABEL_63;
  }
  GetTickCount();
  v13 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v25);
  v15 = RdVhd::Uvhd::CDirectoryHelper::MoveFileW(v14, a2, v13);
  GetTickCount();
  if ( !v15 )
  {
    if ( GetLastError() != 5 )
      goto LABEL_53;
    v16 = CBaseStringT<unsigned short>::PContents(&v25);
    _TraceNrmRdvVmEx(L"UVHD", v4, L"MoveFile(%s, %s) failed with AccessDenied. Sleeping and retrying.", a2, v16);
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v17 = CBaseStringT<unsigned short>::PContents(&v25);
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids,
        (_DWORD)a2,
        v17);
    }
    Sleep(0x3E8u);
    GetTickCount();
    v18 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v25);
    v20 = RdVhd::Uvhd::CDirectoryHelper::MoveFileW(v19, a2, v18);
    GetTickCount();
    if ( !v20 )
    {
LABEL_53:
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError && (LastError & 0xFFFF0000) == 0 )
      {
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        v4 = v4 & 0x8000FFFF | 0x50100000;
      }
      if ( v4 < 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 87;
LABEL_63:
          v8 = (unsigned int)v4;
          goto LABEL_64;
        }
      }
    }
  }
LABEL_65:
  if ( StringUuid )
  {
    v22 = RpcStringFreeW(&StringUuid);
    if ( v22 && (v22 & 0xFFFF0000) == 0 )
    {
      if ( v22 > 0 )
        v22 |= 0x80070000;
      v22 = v22 & 0x8000FFFF | 0x50110000;
    }
    StringUuid = 0;
    if ( v4 < 0 )
      v22 = v4;
    v4 = v22;
  }
  CPathString::~CPathString((CPathString *)&v25);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004eb08  mov     [rsp-28h+arg_10], rbx
0x18004eb0d  mov     [rsp-28h+arg_18], rsi
0x18004eb12  push    rbp
0x18004eb13  push    rdi
0x18004eb14  push    r12
0x18004eb16  push    r13
0x18004eb18  push    r14
0x18004eb1a  mov     rbp, rsp
0x18004eb1d  sub     rsp, 80h
0x18004eb24  mov     rax, cs:__security_cookie
0x18004eb2b  xor     rax, rsp
0x18004eb2e  mov     [rbp+var_10], rax
0x18004eb32  xorps   xmm0, xmm0
0x18004eb35  mov     [rbp+StringUuid], 0
0x18004eb3d  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x18004eb44  mov     [rbp+var_3C], 80h
0x18004eb4c  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18004eb50  mov     [rbp+var_48], rax
0x18004eb54  mov     r14, rdx
0x18004eb57  mov     rbx, rcx
0x18004eb5a  mov     [rbp+var_30], 0
0x18004eb62  mov     [rbp+var_34], 0
0x18004eb69  mov     [rbp+var_28], 8000000h
0x18004eb70  mov     [rbp+var_40], 0
0x18004eb77  mov     r12d, 0FFFF0000h
0x18004eb7d  mov     r13d, 80070000h
0x18004eb83  test    rdx, rdx
0x18004eb86  jnz     short loc_18004EBCC
0x18004eb88  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eb8f  lea     rsi, WPP_GLOBAL_Control
0x18004eb96  cmp     rcx, rsi
0x18004eb99  jz      short loc_18004EBC2
0x18004eb9b  test    byte ptr [rcx+1Ch], 4
0x18004eb9f  jz      short loc_18004EBC2
0x18004eba1  cmp     byte ptr [rcx+19h], 2
0x18004eba5  jb      short loc_18004EBC2
0x18004eba7  mov     rcx, [rcx+10h]
0x18004ebab  lea     edx, [r14+50h]
0x18004ebaf  lea     r9, aSzpath; "szPath"
0x18004ebb6  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004ebbd  call    WPP_SF_S
0x18004ebc2  mov     edi, 80070057h
0x18004ebc7  jmp     loc_18004EEB6
0x18004ebcc  call    ?EnsureCleanupFolder@CDirectoryHelper@Uvhd@RdVhd@@AEAAJXZ; RdVhd::Uvhd::CDirectoryHelper::EnsureCleanupFolder(void)
0x18004ebd1  mov     edi, eax
0x18004ebd3  test    eax, eax
0x18004ebd5  jns     short loc_18004EC0F
0x18004ebd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ebde  lea     rsi, WPP_GLOBAL_Control
0x18004ebe5  cmp     rcx, rsi
0x18004ebe8  jz      loc_18004EEB6
0x18004ebee  test    byte ptr [rcx+1Ch], 4
0x18004ebf2  jz      loc_18004EEB6
0x18004ebf8  cmp     byte ptr [rcx+19h], 2
0x18004ebfc  jb      loc_18004EEB6
0x18004ec02  mov     edx, 51h ; 'Q'
0x18004ec07  mov     r9d, eax
0x18004ec0a  jmp     loc_18004EEA6
0x18004ec0f  mov     edx, 5Ch ; '\'; Ch
0x18004ec14  mov     rcx, r14; Str
0x18004ec17  call    cs:__imp_wcsrchr
0x18004ec1d  test    rax, rax
0x18004ec20  jz      short loc_18004EC28
0x18004ec22  add     rax, 2
0x18004ec26  jmp     short loc_18004EC2B
0x18004ec28  mov     rax, r14
0x18004ec2b  lea     rdx, [rbx+8]; struct CPathString *
0x18004ec2f  mov     r8, rax; unsigned __int16 *
0x18004ec32  lea     rcx, [rbp+var_48]; this
0x18004ec36  call    ?BuildPath@CPathString@@QEAAJAEBV1@PEBG@Z; CPathString::BuildPath(CPathString const &,ushort const *)
0x18004ec3b  mov     edi, eax
0x18004ec3d  test    eax, eax
0x18004ec3f  jns     short loc_18004EC73
0x18004ec41  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ec48  lea     rsi, WPP_GLOBAL_Control
0x18004ec4f  cmp     rcx, rsi
0x18004ec52  jz      loc_18004EEB6
0x18004ec58  test    byte ptr [rcx+1Ch], 4
0x18004ec5c  jz      loc_18004EEB6
0x18004ec62  cmp     byte ptr [rcx+19h], 2
0x18004ec66  jb      loc_18004EEB6
0x18004ec6c  mov     edx, 52h ; 'R'
0x18004ec71  jmp     short loc_18004EC07
0x18004ec73  lea     rcx, [rbp+Uuid]; Uuid
0x18004ec77  call    cs:__imp_UuidCreate
0x18004ec7d  mov     edi, eax
0x18004ec7f  test    eax, eax
0x18004ec81  jz      short loc_18004ECD4
0x18004ec83  test    r12d, eax
0x18004ec86  jnz     short loc_18004EC9B
0x18004ec88  test    eax, eax
0x18004ec8a  jle     short loc_18004EC8F
0x18004ec8c  or      edi, r13d
0x18004ec8f  and     edi, 0D00EFFFFh
0x18004ec95  or      edi, 500E0000h
0x18004ec9b  test    edi, edi
0x18004ec9d  jns     short loc_18004ECD4
0x18004ec9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eca6  lea     rsi, WPP_GLOBAL_Control
0x18004ecad  cmp     rcx, rsi
0x18004ecb0  jz      loc_18004EEB6
0x18004ecb6  test    byte ptr [rcx+1Ch], 4
0x18004ecba  jz      loc_18004EEB6
0x18004ecc0  cmp     byte ptr [rcx+19h], 2
0x18004ecc4  jb      loc_18004EEB6
0x18004ecca  mov     edx, 53h ; 'S'
0x18004eccf  jmp     loc_18004EEA3
0x18004ecd4  lea     rdx, [rbp+StringUuid]; StringUuid
0x18004ecd8  lea     rcx, [rbp+Uuid]; Uuid
0x18004ecdc  call    cs:__imp_UuidToStringW
0x18004ece2  mov     edi, eax
0x18004ece4  test    eax, eax
0x18004ece6  jz      short loc_18004ED39
0x18004ece8  test    r12d, eax
0x18004eceb  jnz     short loc_18004ED00
0x18004eced  test    eax, eax
0x18004ecef  jle     short loc_18004ECF4
0x18004ecf1  or      edi, r13d
0x18004ecf4  and     edi, 0D00FFFFFh
0x18004ecfa  or      edi, 500F0000h
0x18004ed00  test    edi, edi
0x18004ed02  jns     short loc_18004ED39
0x18004ed04  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ed0b  lea     rsi, WPP_GLOBAL_Control
0x18004ed12  cmp     rcx, rsi
0x18004ed15  jz      loc_18004EEB6
0x18004ed1b  test    byte ptr [rcx+1Ch], 4
0x18004ed1f  jz      loc_18004EEB6
0x18004ed25  cmp     byte ptr [rcx+19h], 2
0x18004ed29  jb      loc_18004EEB6
0x18004ed2f  mov     edx, 54h ; 'T'
0x18004ed34  jmp     loc_18004EEA3
0x18004ed39  mov     rdx, [rbp+StringUuid]
0x18004ed3d  lea     rcx, [rbp+var_48]
0x18004ed41  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x18004ed46  mov     edi, eax
0x18004ed48  test    eax, eax
0x18004ed4a  jns     short loc_18004ED81
0x18004ed4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ed53  lea     rsi, WPP_GLOBAL_Control
0x18004ed5a  cmp     rcx, rsi
0x18004ed5d  jz      loc_18004EEB6
0x18004ed63  test    byte ptr [rcx+1Ch], 4
0x18004ed67  jz      loc_18004EEB6
0x18004ed6d  cmp     byte ptr [rcx+19h], 2
0x18004ed71  jb      loc_18004EEB6
0x18004ed77  mov     edx, 55h ; 'U'
0x18004ed7c  jmp     loc_18004EEA3
0x18004ed81  call    cs:__imp_GetTickCount
0x18004ed87  lea     rcx, [rbp+var_48]
0x18004ed8b  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004ed90  mov     r8, rax; unsigned __int16 *
0x18004ed93  mov     rdx, r14; unsigned __int16 *
0x18004ed96  call    ?MoveFileW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBG0@Z; RdVhd::Uvhd::CDirectoryHelper::MoveFileW(ushort const *,ushort const *)
0x18004ed9b  mov     ebx, eax
0x18004ed9d  call    cs:__imp_GetTickCount
0x18004eda3  test    ebx, ebx
0x18004eda5  jnz     loc_18004EEB6
0x18004edab  call    cs:__imp_GetLastError
0x18004edb1  lea     rsi, WPP_GLOBAL_Control
0x18004edb8  cmp     eax, 5
0x18004edbb  jnz     loc_18004EE5B
0x18004edc1  lea     rcx, [rbp+var_48]
0x18004edc5  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004edca  mov     r9, r14
0x18004edcd  mov     [rsp+80h+var_60], rax
0x18004edd2  lea     r8, aMovefileSSFail; "MoveFile(%s, %s) failed with AccessDeni"...
0x18004edd9  mov     edx, edi; int
0x18004eddb  lea     rcx, aUvhd; "UVHD"
0x18004ede2  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18004ede7  mov     rax, cs:WPP_GLOBAL_Control
0x18004edee  cmp     rax, rsi
0x18004edf1  jz      short loc_18004EE2A
0x18004edf3  test    byte ptr [rax+1Ch], 4
0x18004edf7  jz      short loc_18004EE2A
0x18004edf9  cmp     byte ptr [rax+19h], 3
0x18004edfd  jb      short loc_18004EE2A
0x18004edff  lea     rcx, [rbp+var_48]
0x18004ee03  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004ee08  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ee0f  lea     edx, [rbx+56h]
0x18004ee12  mov     r9, r14
0x18004ee15  mov     [rsp+80h+var_60], rax
0x18004ee1a  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004ee21  mov     rcx, [rcx+10h]
0x18004ee25  call    WPP_SF_SS
0x18004ee2a  mov     ecx, 3E8h; dwMilliseconds
0x18004ee2f  call    cs:__imp_Sleep
0x18004ee35  call    cs:__imp_GetTickCount
0x18004ee3b  lea     rcx, [rbp+var_48]
0x18004ee3f  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004ee44  mov     r8, rax; unsigned __int16 *
0x18004ee47  mov     rdx, r14; unsigned __int16 *
0x18004ee4a  call    ?MoveFileW@CDirectoryHelper@Uvhd@RdVhd@@AEBAHPEBG0@Z; RdVhd::Uvhd::CDirectoryHelper::MoveFileW(ushort const *,ushort const *)
0x18004ee4f  mov     ebx, eax
0x18004ee51  call    cs:__imp_GetTickCount
0x18004ee57  test    ebx, ebx
0x18004ee59  jnz     short loc_18004EEB6
0x18004ee5b  call    cs:__imp_GetLastError
0x18004ee61  mov     edi, eax
0x18004ee63  test    eax, eax
0x18004ee65  jz      short loc_18004EE82
0x18004ee67  test    r12d, eax
0x18004ee6a  jnz     short loc_18004EE82
0x18004ee6c  test    eax, eax
0x18004ee6e  jle     short loc_18004EE76
0x18004ee70  movzx   edi, ax
0x18004ee73  or      edi, r13d
0x18004ee76  and     edi, 0D010FFFFh
0x18004ee7c  or      edi, 50100000h
0x18004ee82  test    edi, edi
0x18004ee84  jns     short loc_18004EEB6
0x18004ee86  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ee8d  cmp     rcx, rsi
0x18004ee90  jz      short loc_18004EEB6
0x18004ee92  test    byte ptr [rcx+1Ch], 4
0x18004ee96  jz      short loc_18004EEB6
0x18004ee98  cmp     byte ptr [rcx+19h], 2
0x18004ee9c  jb      short loc_18004EEB6
0x18004ee9e  mov     edx, 57h ; 'W'
0x18004eea3  mov     r9d, edi
0x18004eea6  mov     rcx, [rcx+10h]
0x18004eeaa  lea     r8, WPP_895bf00a56d83773722d199a1df9f3e1_Traceguids
0x18004eeb1  call    WPP_SF_d
0x18004eeb6  cmp     [rbp+StringUuid], 0
0x18004eebb  jz      short loc_18004EEF0
0x18004eebd  lea     rcx, [rbp+StringUuid]; String
0x18004eec1  call    cs:__imp_RpcStringFreeW
0x18004eec7  test    eax, eax
0x18004eec9  jz      short loc_18004EEE1
0x18004eecb  test    r12d, eax
0x18004eece  jnz     short loc_18004EEE1
0x18004eed0  test    eax, eax
0x18004eed2  jle     short loc_18004EED7
0x18004eed4  or      eax, r13d
0x18004eed7  and     eax, 0D011FFFFh
0x18004eedc  or      eax, 50110000h
0x18004eee1  test    edi, edi
0x18004eee3  mov     [rbp+StringUuid], 0
0x18004eeeb  cmovs   eax, edi
0x18004eeee  mov     edi, eax
0x18004eef0  lea     rcx, [rbp+var_48]; this
0x18004eef4  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18004eef9  mov     eax, edi
0x18004eefb  mov     rcx, [rbp+var_10]
0x18004eeff  xor     rcx, rsp; StackCookie
0x18004ef02  call    __security_check_cookie
0x18004ef07  lea     r11, [rsp+80h+var_s0]
0x18004ef0f  mov     rbx, [r11+40h]
0x18004ef13  mov     rsi, [r11+48h]
0x18004ef17  mov     rsp, r11
0x18004ef1a  pop     r14
0x18004ef1c  pop     r13
0x18004ef1e  pop     r12
0x18004ef20  pop     rdi
0x18004ef21  pop     rbp
0x18004ef22  retn
```
