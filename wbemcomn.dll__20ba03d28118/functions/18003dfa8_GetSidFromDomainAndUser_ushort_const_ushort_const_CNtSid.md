# GetSidFromDomainAndUser(ushort const *,ushort const *,CNtSid * *)

- ea: `0x18003dfa8`
- end: `0x18003e4d7`
- name: `?GetSidFromDomainAndUser@@YAJPEBG0PEAPEAVCNtSid@@@Z`
- size: `1327`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct CNtSid **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003eff4`

## callees

- `0x18000a290`
- `0x180011e40`
- `0x180013564`
- `0x180014120`
- `0x1800154d0`
- `0x18001c340`
- `0x18001c4d0`
- `0x18001c56c`
- `0x18002a1ac`
- `0x180039f70`
- `0x18003dfa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e1d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e2fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e1d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e2fa`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18003e1cf`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18003e2f0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18003e1cf`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x18003e2f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetSidFromDomainAndUser(unsigned __int16 *a1, const unsigned __int16 *a2, struct CNtSid **a3)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // r15
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rsi
  unsigned int v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  signed int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  signed int v20; // eax
  signed int v21; // eax
  signed int LastError; // eax
  void *v23; // rax
  void *v24; // rbx
  void *v25; // rax
  signed int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  CNtSid *v30; // rax
  struct CNtSid *v31; // rbx
  enum _SID_NAME_USE peUse; // [rsp+30h] [rbp-40h] BYREF
  CNtSid *v34; // [rsp+38h] [rbp-38h]
  void *v35[2]; // [rsp+40h] [rbp-30h] BYREF
  void *v36[2]; // [rsp+50h] [rbp-20h] BYREF
  void *v37[2]; // [rsp+60h] [rbp-10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+B8h] [rbp+48h] BYREF
  DWORD cbSid; // [rsp+C8h] [rbp+58h] BYREF

  if ( a2 && *a2 )
  {
    v6 = 2;
    if ( a1 && *a1 )
    {
      v7 = -1;
      do
        ++v7;
      while ( a1[v7] );
      v6 = v7 + 2;
    }
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v9 = v8 + v6;
    v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v8 + v6, 2u));
    v11 = v10;
    if ( !v10 )
    {
      v12 = -2147217402;
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041006);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 63;
        v15 = 2147749894LL;
LABEL_83:
        WPP_SF_D(v13[2], v14, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v15);
        return v12;
      }
      return v12;
    }
    v37[0] = v10;
    v37[1] = 0;
    *v10 = 0;
    if ( a1 && *a1 )
    {
      v16 = StringCchCopyW(v10, v9, a1);
      v12 = v16;
      if ( v16 < 0 )
      {
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v16);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_24;
        }
        v18 = 64;
        goto LABEL_22;
      }
      v20 = StringCchCatW(v11, v9, L"\\");
      v12 = v20;
      if ( v20 < 0 )
      {
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v20);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_24;
        }
        v18 = 65;
        goto LABEL_22;
      }
    }
    v21 = StringCchCatW(v11, v9, a2);
    v12 = v21;
    if ( v21 < 0 )
    {
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v21);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_24;
      }
      v18 = 66;
      goto LABEL_22;
    }
    cbSid = 0;
    cchReferencedDomainName = 0;
    peUse = 0;
    LookupAccountNameLocalW(v11, 0, &cbSid, 0, &cchReferencedDomainName, &peUse);
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError == 122 )
    {
      v23 = CWin32DefaultArena::WbemMemAlloc(cbSid);
      v24 = v23;
      if ( !v23 )
      {
        v12 = -2147217402;
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041006);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_24;
        }
        v18 = 67;
        v19 = 2147749894LL;
        goto LABEL_23;
      }
      v35[0] = v23;
      v35[1] = 0;
      v25 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(cchReferencedDomainName, 2u));
      if ( !v25 )
      {
        v12 = -2147217402;
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041006);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids,
            2147749894LL);
        }
        goto LABEL_46;
      }
      v36[0] = v25;
      v36[1] = 0;
      if ( !LookupAccountNameLocalW(v11, v24, &cbSid, (LPWSTR)v25, &cchReferencedDomainName, &peUse) )
      {
        v26 = GetLastError();
        v12 = v26;
        if ( v26 > 0 )
          v12 = (unsigned __int16)v26 | 0x80070000;
        if ( (v12 & 0x80000000) != 0 )
          CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v12);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_57;
        }
        v28 = 69;
        v29 = v12;
        goto LABEL_56;
      }
      v30 = (CNtSid *)CWin32DefaultArena::WbemMemAlloc(0x10u);
      v34 = v30;
      if ( v30 )
        v31 = CNtSid::CNtSid(v30, v24);
      else
        v31 = 0;
      if ( v31 )
      {
        if ( (unsigned int)CNtSid::IsValid(v31) )
        {
          *a3 = v31;
          v12 = 0;
          CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v36);
          CVectorDeleteMe<char>::~CVectorDeleteMe<char>(v35);
          goto LABEL_75;
        }
        CNtSid::`scalar deleting destructor'((void **)v31);
      }
      v12 = -2147217402;
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041006);
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_57;
      }
      v28 = 70;
      v29 = 2147749894LL;
LABEL_56:
      WPP_SF_D(v27[2], v28, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v29);
LABEL_57:
      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v36);
LABEL_46:
      CVectorDeleteMe<char>::~CVectorDeleteMe<char>(v35);
      goto LABEL_24;
    }
    if ( LastError )
    {
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( (v12 & 0x80000000) == 0 )
        goto LABEL_75;
    }
    else
    {
      v12 = -2147217379;
    }
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v12);
LABEL_75:
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_24;
    }
    v18 = 71;
LABEL_22:
    v19 = v12;
LABEL_23:
    WPP_SF_D(v17[2], v18, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v19);
LABEL_24:
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v37);
    return v12;
  }
  v12 = -2147217400;
  CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, 0x80041008);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 62;
    v15 = 2147749896LL;
    goto LABEL_83;
  }
  return v12;
}

```

## disassembly

```asm
0x18003dfa8  mov     [rsp-38h+arg_0], rbx
0x18003dfad  push    rbp
0x18003dfae  push    rsi
0x18003dfaf  push    rdi
0x18003dfb0  push    r12
0x18003dfb2  push    r13
0x18003dfb4  push    r14
0x18003dfb6  push    r15
0x18003dfb8  mov     rbp, rsp
0x18003dfbb  sub     rsp, 70h
0x18003dfbf  mov     r12, r8
0x18003dfc2  mov     r14, rdx
0x18003dfc5  mov     rbx, rcx
0x18003dfc8  xor     r13d, r13d
0x18003dfcb  test    rdx, rdx
0x18003dfce  jz      loc_18003E46D
0x18003dfd4  cmp     [rdx], r13w
0x18003dfd8  jz      loc_18003E46D
0x18003dfde  lea     edi, [r13+2]
0x18003dfe2  mov     ecx, edi
0x18003dfe4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003dfe8  test    rbx, rbx
0x18003dfeb  jz      short loc_18003E004
0x18003dfed  cmp     [rbx], r13w
0x18003dff1  jz      short loc_18003E004
0x18003dff3  mov     rax, r8
0x18003dff6  inc     rax
0x18003dff9  cmp     [rbx+rax*2], r13w
0x18003dffe  jnz     short loc_18003DFF6
0x18003e000  lea     rcx, [rax+2]
0x18003e004  mov     rax, r8
0x18003e007  inc     rax
0x18003e00a  cmp     [rdx+rax*2], r13w
0x18003e00f  jnz     short loc_18003E007
0x18003e011  lea     r15, [rax+rcx]
0x18003e015  mov     rax, rdi
0x18003e018  mul     r15
0x18003e01b  cmovb   rax, r8
0x18003e01f  mov     rcx, rax; unsigned __int64
0x18003e022  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003e027  mov     rsi, rax
0x18003e02a  test    rax, rax
0x18003e02d  jnz     short loc_18003E07B
0x18003e02f  mov     ebx, 80041006h
0x18003e034  mov     edx, ebx; int
0x18003e036  lea     rcx, qword_18006A9C0; this
0x18003e03d  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e042  lea     rax, WPP_GLOBAL_Control
0x18003e049  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e050  cmp     rcx, rax
0x18003e053  jz      loc_18003E4BD
0x18003e059  test    byte ptr [rcx+1Ch], 1
0x18003e05d  jz      loc_18003E4BD
0x18003e063  cmp     [rcx+19h], dil
0x18003e067  jb      loc_18003E4BD
0x18003e06d  lea     edx, [rsi+3Fh]
0x18003e070  mov     r9d, 80041006h
0x18003e076  jmp     loc_18003E4AD
0x18003e07b  mov     [rbp+var_10], rsi
0x18003e07f  mov     [rbp+var_8], r13
0x18003e083  mov     [rax], r13w
0x18003e087  test    rbx, rbx
0x18003e08a  jz      loc_18003E14E
0x18003e090  cmp     [rbx], r13w
0x18003e094  jz      loc_18003E14E
0x18003e09a  mov     r8, rbx; unsigned __int16 *
0x18003e09d  mov     rdx, r15; unsigned __int64
0x18003e0a0  mov     rcx, rsi; unsigned __int16 *
0x18003e0a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003e0a8  mov     ebx, eax
0x18003e0aa  test    eax, eax
0x18003e0ac  jns     short loc_18003E102
0x18003e0ae  mov     edx, eax; int
0x18003e0b0  lea     rcx, qword_18006A9C0; this
0x18003e0b7  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e0bc  lea     rax, WPP_GLOBAL_Control
0x18003e0c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e0ca  cmp     rcx, rax
0x18003e0cd  jz      short loc_18003E0F4
0x18003e0cf  test    byte ptr [rcx+1Ch], 1
0x18003e0d3  jz      short loc_18003E0F4
0x18003e0d5  cmp     [rcx+19h], dil
0x18003e0d9  jb      short loc_18003E0F4
0x18003e0db  mov     edx, 40h ; '@'
0x18003e0e0  mov     r9d, ebx
0x18003e0e3  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003e0ea  mov     rcx, [rcx+10h]
0x18003e0ee  call    WPP_SF_D
0x18003e0f3  nop
0x18003e0f4  lea     rcx, [rbp+var_10]
0x18003e0f8  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18003e0fd  jmp     loc_18003E4BD
0x18003e102  lea     r8, asc_18004CC00; "\\"
0x18003e109  mov     rdx, r15; unsigned __int64
0x18003e10c  mov     rcx, rsi; unsigned __int16 *
0x18003e10f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003e114  mov     ebx, eax
0x18003e116  test    eax, eax
0x18003e118  jns     short loc_18003E14E
0x18003e11a  mov     edx, eax; int
0x18003e11c  lea     rcx, qword_18006A9C0; this
0x18003e123  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e128  lea     rax, WPP_GLOBAL_Control
0x18003e12f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e136  cmp     rcx, rax
0x18003e139  jz      short loc_18003E0F4
0x18003e13b  test    byte ptr [rcx+1Ch], 1
0x18003e13f  jz      short loc_18003E0F4
0x18003e141  cmp     [rcx+19h], dil
0x18003e145  jb      short loc_18003E0F4
0x18003e147  mov     edx, 41h ; 'A'
0x18003e14c  jmp     short loc_18003E0E0
0x18003e14e  mov     r8, r14; unsigned __int16 *
0x18003e151  mov     rdx, r15; unsigned __int64
0x18003e154  mov     rcx, rsi; unsigned __int16 *
0x18003e157  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003e15c  mov     ebx, eax
0x18003e15e  test    eax, eax
0x18003e160  jns     short loc_18003E1A5
0x18003e162  mov     edx, eax; int
0x18003e164  lea     rcx, qword_18006A9C0; this
0x18003e16b  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e170  lea     rax, WPP_GLOBAL_Control
0x18003e177  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e17e  cmp     rcx, rax
0x18003e181  jz      loc_18003E0F4
0x18003e187  test    byte ptr [rcx+1Ch], 1
0x18003e18b  jz      loc_18003E0F4
0x18003e191  cmp     [rcx+19h], dil
0x18003e195  jb      loc_18003E0F4
0x18003e19b  mov     edx, 42h ; 'B'
0x18003e1a0  jmp     loc_18003E0E0
0x18003e1a5  mov     [rbp+cbSid], r13d
0x18003e1a9  mov     [rbp+arg_8], r13d
0x18003e1ad  mov     [rbp+var_40], r13d
0x18003e1b1  lea     rax, [rbp+var_40]
0x18003e1b5  mov     [rsp+70h+peUse], rax; peUse
0x18003e1ba  lea     rax, [rbp+arg_8]
0x18003e1be  mov     [rsp+70h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18003e1c3  xor     r9d, r9d; ReferencedDomainName
0x18003e1c6  lea     r8, [rbp+cbSid]; cbSid
0x18003e1ca  xor     edx, edx; Sid
0x18003e1cc  mov     rcx, rsi; lpAccountName
0x18003e1cf  call    cs:__imp_LookupAccountNameLocalW
0x18003e1d5  call    cs:__imp_GetLastError
0x18003e1db  mov     ebx, eax
0x18003e1dd  cmp     eax, 7Ah ; 'z'
0x18003e1e0  jnz     loc_18003E410
0x18003e1e6  mov     ecx, [rbp+cbSid]; unsigned __int64
0x18003e1e9  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003e1ee  mov     rbx, rax
0x18003e1f1  test    rax, rax
0x18003e1f4  jnz     short loc_18003E244
0x18003e1f6  mov     ebx, 80041006h
0x18003e1fb  mov     edx, ebx; int
0x18003e1fd  lea     rcx, qword_18006A9C0; this
0x18003e204  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e209  lea     rax, WPP_GLOBAL_Control
0x18003e210  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e217  cmp     rcx, rax
0x18003e21a  jz      loc_18003E0F4
0x18003e220  test    byte ptr [rcx+1Ch], 1
0x18003e224  jz      loc_18003E0F4
0x18003e22a  cmp     [rcx+19h], dil
0x18003e22e  jb      loc_18003E0F4
0x18003e234  mov     edx, 43h ; 'C'
0x18003e239  mov     r9d, 80041006h
0x18003e23f  jmp     loc_18003E0E3
0x18003e244  mov     [rbp+var_30], rbx
0x18003e248  mov     [rbp+var_28], r13
0x18003e24c  mov     ecx, [rbp+arg_8]
0x18003e24f  mov     rax, rdi
0x18003e252  mul     rcx
0x18003e255  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003e25c  cmovb   rax, rcx
0x18003e260  mov     rcx, rax; unsigned __int64
0x18003e263  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003e268  test    rax, rax
0x18003e26b  jnz     short loc_18003E2C9
0x18003e26d  mov     ebx, 80041006h
0x18003e272  mov     edx, ebx; int
0x18003e274  lea     rcx, qword_18006A9C0; this
0x18003e27b  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e280  lea     rax, WPP_GLOBAL_Control
0x18003e287  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e28e  cmp     rcx, rax
0x18003e291  jz      short loc_18003E2BB
0x18003e293  test    byte ptr [rcx+1Ch], 1
0x18003e297  jz      short loc_18003E2BB
0x18003e299  cmp     [rcx+19h], dil
0x18003e29d  jb      short loc_18003E2BB
0x18003e29f  mov     edx, 44h ; 'D'
0x18003e2a4  mov     r9d, 80041006h
0x18003e2aa  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003e2b1  mov     rcx, [rcx+10h]
0x18003e2b5  call    WPP_SF_D
0x18003e2ba  nop
0x18003e2bb  lea     rcx, [rbp+var_30]
0x18003e2bf  call    ??1?$CVectorDeleteMe@D@@QEAA@XZ; CVectorDeleteMe<char>::~CVectorDeleteMe<char>(void)
0x18003e2c4  jmp     loc_18003E0F4
0x18003e2c9  mov     [rbp+var_20], rax
0x18003e2cd  mov     [rbp+var_18], r13
0x18003e2d1  lea     rcx, [rbp+var_40]
0x18003e2d5  mov     [rsp+70h+peUse], rcx; peUse
0x18003e2da  lea     rcx, [rbp+arg_8]
0x18003e2de  mov     [rsp+70h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18003e2e3  mov     r9, rax; ReferencedDomainName
0x18003e2e6  lea     r8, [rbp+cbSid]; cbSid
0x18003e2ea  mov     rdx, rbx; Sid
0x18003e2ed  mov     rcx, rsi; lpAccountName
0x18003e2f0  call    cs:__imp_LookupAccountNameLocalW
0x18003e2f6  test    eax, eax
0x18003e2f8  jnz     short loc_18003E367
0x18003e2fa  call    cs:__imp_GetLastError
0x18003e300  mov     ebx, eax
0x18003e302  test    eax, eax
0x18003e304  jle     short loc_18003E30F
0x18003e306  movzx   ebx, ax
0x18003e309  or      ebx, 80070000h
0x18003e30f  test    ebx, ebx
0x18003e311  jns     short loc_18003E321
0x18003e313  mov     edx, ebx; int
0x18003e315  lea     rcx, qword_18006A9C0; this
0x18003e31c  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e321  lea     rax, WPP_GLOBAL_Control
0x18003e328  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e32f  cmp     rcx, rax
0x18003e332  jz      short loc_18003E359
0x18003e334  test    byte ptr [rcx+1Ch], 1
0x18003e338  jz      short loc_18003E359
0x18003e33a  cmp     [rcx+19h], dil
0x18003e33e  jb      short loc_18003E359
0x18003e340  mov     edx, 45h ; 'E'
0x18003e345  mov     r9d, ebx
0x18003e348  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003e34f  mov     rcx, [rcx+10h]
0x18003e353  call    WPP_SF_D
0x18003e358  nop
0x18003e359  lea     rcx, [rbp+var_20]
0x18003e35d  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18003e362  jmp     loc_18003E2BB
0x18003e367  mov     ecx, 10h; unsigned __int64
0x18003e36c  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003e371  mov     [rbp+var_38], rax
0x18003e375  test    rax, rax
0x18003e378  jz      short loc_18003E38A
0x18003e37a  mov     rdx, rbx; void *
0x18003e37d  mov     rcx, rax; this
0x18003e380  call    ??0CNtSid@@QEAA@PEAX@Z; CNtSid::CNtSid(void *)
0x18003e385  mov     rbx, rax
0x18003e388  jmp     short loc_18003E38D
0x18003e38a  mov     rbx, r13
0x18003e38d  test    rbx, rbx
0x18003e390  jz      short loc_18003E3C2
0x18003e392  mov     rcx, rbx; this
0x18003e395  call    ?IsValid@CNtSid@@QEAAHXZ; CNtSid::IsValid(void)
0x18003e39a  test    eax, eax
0x18003e39c  jz      short loc_18003E3BA
0x18003e39e  mov     [r12], rbx
0x18003e3a2  mov     ebx, r13d
0x18003e3a5  lea     rcx, [rbp+var_20]
0x18003e3a9  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18003e3ae  nop
0x18003e3af  lea     rcx, [rbp+var_30]
0x18003e3b3  call    ??1?$CVectorDeleteMe@D@@QEAA@XZ; CVectorDeleteMe<char>::~CVectorDeleteMe<char>(void)
0x18003e3b8  jmp     short loc_18003E438
0x18003e3ba  mov     rcx, rbx; this
0x18003e3bd  call    ??_GCNtSid@@QEAAPEAXI@Z; CNtSid::`scalar deleting destructor'(uint)
0x18003e3c2  mov     ebx, 80041006h
0x18003e3c7  mov     edx, ebx; int
0x18003e3c9  lea     rcx, qword_18006A9C0; this
0x18003e3d0  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e3d5  lea     rax, WPP_GLOBAL_Control
0x18003e3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e3e3  cmp     rcx, rax
0x18003e3e6  jz      loc_18003E359
0x18003e3ec  test    byte ptr [rcx+1Ch], 1
0x18003e3f0  jz      loc_18003E359
0x18003e3f6  cmp     [rcx+19h], dil
0x18003e3fa  jb      loc_18003E359
0x18003e400  mov     edx, 46h ; 'F'
0x18003e405  mov     r9d, 80041006h
0x18003e40b  jmp     loc_18003E348
0x18003e410  test    eax, eax
0x18003e412  jnz     short loc_18003E41B
0x18003e414  mov     ebx, 8004101Dh
0x18003e419  jmp     short loc_18003E42A
0x18003e41b  jle     short loc_18003E426
0x18003e41d  movzx   ebx, ax
0x18003e420  or      ebx, 80070000h
0x18003e426  test    ebx, ebx
0x18003e428  jns     short loc_18003E438
0x18003e42a  mov     edx, ebx; int
0x18003e42c  lea     rcx, qword_18006A9C0; this
0x18003e433  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003e438  lea     rax, WPP_GLOBAL_Control
0x18003e43f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e446  cmp     rcx, rax
0x18003e449  jz      loc_18003E0F4
0x18003e44f  test    byte ptr [rcx+1Ch], 1
  ... truncated ...
```
