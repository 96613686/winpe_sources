# RdVhd::Uvhd::CUvhdDiskManager::AssignUvhdVolumeToUser(ushort const *,ushort const *)

- ea: `0x18004fe5c`
- end: `0x180050350`
- name: `?AssignUvhdVolumeToUser@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBG0@Z`
- size: `1268`
- prototype: `int(RdVhd::Uvhd::CUvhdDiskManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180050c6c`

## callees

- `0x180004db0`
- `0x1800141e8`
- `0x180019b38`
- `0x18003114c`
- `0x180031178`
- `0x180035db4`
- `0x1800488e4`
- `0x180048ab0`
- `0x180048b28`
- `0x18004fe5c`
- `0x1800549f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800501de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050270`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800501de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050270`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050310`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050310`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005031f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005031f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180050266`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180050266`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800501cf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800501cf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180050127`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180050127`

## string_xrefs

- `0x18004ff4e`: `szUserSID`
- `0x18004ff04`: `szUvhdVolumeRootPath`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::AssignUvhdVolumeToUser(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  RdVhd::Uvhd::CUvhdDiskManager *v5; // rcx
  __int64 v6; // rdx
  const wchar_t *v7; // r9
  signed int v8; // ebx
  int v9; // r9d
  int v10; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v11; // rcx
  __int64 v12; // rdx
  const WCHAR *v13; // rax
  signed int LastError; // eax
  const WCHAR *v15; // rax
  HANDLE v16; // r14
  signed int v17; // eax
  __int64 v18; // rax
  int v19; // edi
  signed int v20; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v21; // rcx
  __int64 v22; // rdx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-39h] BYREF
  const int *v25; // [rsp+58h] [rbp-21h] BYREF
  int v26; // [rsp+60h] [rbp-19h]
  __int64 v27; // [rsp+64h] [rbp-15h]
  int v28; // [rsp+6Ch] [rbp-Dh]
  __int64 v29; // [rsp+70h] [rbp-9h]
  int v30; // [rsp+78h] [rbp-1h]
  void **v31; // [rsp+80h] [rbp+7h] BYREF
  int v32; // [rsp+88h] [rbp+Fh]
  __int64 v33; // [rsp+8Ch] [rbp+13h]
  int v34; // [rsp+94h] [rbp+1Bh]
  __int64 v35; // [rsp+98h] [rbp+1Fh]
  int v36; // [rsp+A0h] [rbp+27h]
  DWORD NumberOfBytesWritten; // [rsp+F0h] [rbp+77h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+F8h] [rbp+7Fh] BYREF

  v33 = 128;
  v35 = 0;
  v31 = &CPathString::`vftable';
  v34 = 0;
  v36 = 0x8000000;
  v25 = &CBaseStringT<unsigned short>::`vftable';
  v32 = 0;
  SecurityDescriptor = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  NumberOfBytesWritten = 0;
  v27 = 128;
  v29 = 0;
  v28 = 0;
  v30 = 0x8000000;
  v26 = 0;
  if ( !a3 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 155;
    v7 = L"szUvhdVolumeRootPath";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v5 + 2), v6, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v7);
LABEL_7:
    v8 = -2147024809;
    goto LABEL_82;
  }
  if ( !a2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v6 = 156;
    v7 = L"szUserSID";
    goto LABEL_6;
  }
  v8 = RdVhd::Uvhd::CUvhdDiskManager::SetUvhdVolumePermissions(this, a2, a3);
  _TraceNrmRdvVmEx(L"UVHD", v8, L"SetUvhdVolumePermissions(%s)", a3);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        157,
        (unsigned int)WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
        v9,
        v8);
    }
    goto LABEL_82;
  }
  v8 = CPathString::BuildPath((CPathString *)&v31, a3, L"Uvhd-Binding");
  if ( v8 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_82;
    }
    v12 = 158;
    goto LABEL_23;
  }
  v8 = CBaseStringT<unsigned short>::Append(&v25, L"D:P(A;;FA;;;SY)(A;;FR;;;", 24);
  if ( v8 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_82;
    }
    v12 = 159;
    goto LABEL_23;
  }
  v8 = CBaseStringT<unsigned short>::Append(&v25, a2);
  if ( v8 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_82;
    }
    v12 = 160;
    goto LABEL_23;
  }
  v8 = CBaseStringT<unsigned short>::Append(&v25, L")", 1);
  if ( v8 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_82;
    }
    v12 = 161;
    goto LABEL_23;
  }
  v13 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v25);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v13, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v8 = v8 & 0x8000FFFF | 0x50570000;
    }
    if ( v8 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      v12 = 162;
      goto LABEL_23;
    }
  }
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 0;
  v15 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v31);
  v16 = CreateFileW(v15, 0x1F01FFu, 0, &SecurityAttributes, 1u, 6u, 0);
  if ( v16 == (HANDLE)-1LL )
  {
    v17 = GetLastError();
    v8 = v17;
    if ( v17 && (v17 & 0xFFFF0000) == 0 )
    {
      if ( v17 > 0 )
        v8 = (unsigned __int16)v17 | 0x80070000;
      v8 = v8 & 0x8000FFFF | 0x50580000;
    }
    if ( v8 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      v12 = 163;
LABEL_23:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, (unsigned int)v8);
      goto LABEL_82;
    }
  }
  v18 = -1;
  do
    ++v18;
  while ( a2[v18] );
  v19 = 2 * v18;
  if ( WriteFile(v16, a2, 2 * v18, &NumberOfBytesWritten, 0) )
    goto LABEL_77;
  v20 = GetLastError();
  v8 = v20;
  if ( v20 && (v20 & 0xFFFF0000) == 0 )
  {
    if ( v20 > 0 )
      v8 = (unsigned __int16)v20 | 0x80070000;
    v8 = v8 & 0x8000FFFF | 0x50590000;
  }
  if ( v8 >= 0 )
  {
LABEL_77:
    if ( NumberOfBytesWritten != v19 )
    {
      v8 = -796786659;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = 165;
        goto LABEL_79;
      }
    }
  }
  else
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = 164;
LABEL_79:
      WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, (unsigned int)v8);
    }
  }
  if ( v16 != (HANDLE)-1LL )
    CloseHandle(v16);
LABEL_82:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  CPathString::~CPathString((CPathString *)&v25);
  CPathString::~CPathString((CPathString *)&v31);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004fe5c  mov     [rsp-8+arg_0], rbx
0x18004fe61  push    rbp
0x18004fe62  push    rsi
0x18004fe63  push    rdi
0x18004fe64  push    r14
0x18004fe66  push    r15
0x18004fe68  lea     rbp, [rsp-37h]
0x18004fe6d  sub     rsp, 0B0h
0x18004fe74  xor     r15d, r15d
0x18004fe77  mov     [rbp+57h+var_44], 80h
0x18004fe7f  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x18004fe86  mov     [rbp+57h+var_38], r15
0x18004fe8a  mov     [rbp+57h+var_50], rax
0x18004fe8e  mov     rsi, rdx
0x18004fe91  xor     eax, eax
0x18004fe93  mov     [rbp+57h+var_3C], r15d
0x18004fe97  mov     edx, 8000000h
0x18004fe9c  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18004fea0  lea     rax, ??_7?$CBaseStringT@G@@6B@; const CBaseStringT<ushort>::`vftable'
0x18004fea7  mov     [rbp+57h+var_30], edx
0x18004feaa  xorps   xmm0, xmm0
0x18004fead  mov     [rbp+57h+var_78], rax
0x18004feb1  mov     rdi, r8
0x18004feb4  mov     [rbp+57h+var_48], r15d
0x18004feb8  mov     [rbp+57h+SecurityDescriptor], r15
0x18004febc  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x18004fec0  mov     [rbp+57h+NumberOfBytesWritten], r15d
0x18004fec4  mov     [rbp+57h+var_6C], 80h
0x18004fecc  mov     [rbp+57h+var_60], r15
0x18004fed0  mov     [rbp+57h+var_64], r15d
0x18004fed4  mov     [rbp+57h+var_58], edx
0x18004fed7  mov     [rbp+57h+var_70], r15d
0x18004fedb  test    r8, r8
0x18004fede  jnz     short loc_18004FF25
0x18004fee0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fee7  lea     rax, WPP_GLOBAL_Control
0x18004feee  cmp     rcx, rax
0x18004fef1  jz      short loc_18004FF1B
0x18004fef3  test    byte ptr [rcx+1Ch], 4
0x18004fef7  jz      short loc_18004FF1B
0x18004fef9  cmp     byte ptr [rcx+19h], 2
0x18004fefd  jb      short loc_18004FF1B
0x18004feff  mov     edx, 9Bh
0x18004ff04  lea     r9, aSzuvhdvolumero; "szUvhdVolumeRootPath"
0x18004ff0b  mov     rcx, [rcx+10h]
0x18004ff0f  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x18004ff16  call    WPP_SF_S
0x18004ff1b  mov     ebx, 80070057h
0x18004ff20  jmp     loc_180050316
0x18004ff25  test    rsi, rsi
0x18004ff28  jnz     short loc_18004FF57
0x18004ff2a  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18004ff31  lea     rax, WPP_GLOBAL_Control
0x18004ff38  cmp     rcx, rax
0x18004ff3b  jz      short loc_18004FF1B
0x18004ff3d  test    byte ptr [rcx+1Ch], 4
0x18004ff41  jz      short loc_18004FF1B
0x18004ff43  cmp     byte ptr [rcx+19h], 2
0x18004ff47  jb      short loc_18004FF1B
0x18004ff49  mov     edx, 9Ch
0x18004ff4e  lea     r9, aSzusersid_0; "szUserSID"
0x18004ff55  jmp     short loc_18004FF0B
0x18004ff57  mov     rdx, rsi; unsigned __int16 *
0x18004ff5a  call    ?SetUvhdVolumePermissions@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBG0@Z; RdVhd::Uvhd::CUvhdDiskManager::SetUvhdVolumePermissions(ushort const *,ushort const *)
0x18004ff5f  mov     r9, rdi
0x18004ff62  lea     r8, aSetuvhdvolumep; "SetUvhdVolumePermissions(%s)"
0x18004ff69  mov     edx, eax; int
0x18004ff6b  lea     rcx, aUvhd; "UVHD"
0x18004ff72  mov     ebx, eax
0x18004ff74  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x18004ff79  test    eax, eax
0x18004ff7b  jns     short loc_18004FFC6
0x18004ff7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ff84  lea     rax, WPP_GLOBAL_Control
0x18004ff8b  cmp     rcx, rax
0x18004ff8e  jz      loc_180050316
0x18004ff94  test    byte ptr [rcx+1Ch], 4
0x18004ff98  jz      loc_180050316
0x18004ff9e  cmp     byte ptr [rcx+19h], 2
0x18004ffa2  jb      loc_180050316
0x18004ffa8  mov     rcx, [rcx+10h]
0x18004ffac  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x18004ffb3  mov     edx, 9Dh
0x18004ffb8  mov     [rsp+0D0h+dwCreationDisposition], ebx
0x18004ffbc  call    WPP_SF_Sd
0x18004ffc1  jmp     loc_180050316
0x18004ffc6  lea     r8, aUvhdBinding; "Uvhd-Binding"
0x18004ffcd  mov     rdx, rdi; unsigned __int16 *
0x18004ffd0  lea     rcx, [rbp+57h+var_50]; this
0x18004ffd4  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x18004ffd9  mov     ebx, eax
0x18004ffdb  test    eax, eax
0x18004ffdd  jns     short loc_180050027
0x18004ffdf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ffe6  lea     rax, WPP_GLOBAL_Control
0x18004ffed  cmp     rcx, rax
0x18004fff0  jz      loc_180050316
0x18004fff6  test    byte ptr [rcx+1Ch], 4
0x18004fffa  jz      loc_180050316
0x180050000  cmp     byte ptr [rcx+19h], 2
0x180050004  jb      loc_180050316
0x18005000a  mov     edx, 9Eh
0x18005000f  mov     rcx, [rcx+10h]
0x180050013  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x18005001a  mov     r9d, ebx
0x18005001d  call    WPP_SF_d
0x180050022  jmp     loc_180050316
0x180050027  mov     r14d, 18h
0x18005002d  lea     rdx, aDPAFaSyAFr; "D:P(A;;FA;;;SY)(A;;FR;;;"
0x180050034  mov     r8d, r14d
0x180050037  lea     rcx, [rbp+57h+var_78]
0x18005003b  call    ?Append@?$CBaseStringT@G@@QEAAJPEBGK@Z; CBaseStringT<ushort>::Append(ushort const *,ulong)
0x180050040  mov     ebx, eax
0x180050042  test    eax, eax
0x180050044  jns     short loc_180050078
0x180050046  mov     rcx, cs:WPP_GLOBAL_Control
0x18005004d  lea     rax, WPP_GLOBAL_Control
0x180050054  cmp     rcx, rax
0x180050057  jz      loc_180050316
0x18005005d  test    byte ptr [rcx+1Ch], 4
0x180050061  jz      loc_180050316
0x180050067  cmp     byte ptr [rcx+19h], 2
0x18005006b  jb      loc_180050316
0x180050071  mov     edx, 9Fh
0x180050076  jmp     short loc_18005000F
0x180050078  mov     rdx, rsi
0x18005007b  lea     rcx, [rbp+57h+var_78]
0x18005007f  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x180050084  mov     ebx, eax
0x180050086  test    eax, eax
0x180050088  jns     short loc_1800500BF
0x18005008a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050091  lea     rax, WPP_GLOBAL_Control
0x180050098  cmp     rcx, rax
0x18005009b  jz      loc_180050316
0x1800500a1  test    byte ptr [rcx+1Ch], 4
0x1800500a5  jz      loc_180050316
0x1800500ab  cmp     byte ptr [rcx+19h], 2
0x1800500af  jb      loc_180050316
0x1800500b5  mov     edx, 0A0h
0x1800500ba  jmp     loc_18005000F
0x1800500bf  mov     edi, 1
0x1800500c4  lea     rdx, asc_180075E68; ")"
0x1800500cb  mov     r8d, edi
0x1800500ce  lea     rcx, [rbp+57h+var_78]
0x1800500d2  call    ?Append@?$CBaseStringT@G@@QEAAJPEBGK@Z; CBaseStringT<ushort>::Append(ushort const *,ulong)
0x1800500d7  mov     ebx, eax
0x1800500d9  test    eax, eax
0x1800500db  jns     short loc_180050112
0x1800500dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800500e4  lea     rax, WPP_GLOBAL_Control
0x1800500eb  cmp     rcx, rax
0x1800500ee  jz      loc_180050316
0x1800500f4  test    byte ptr [rcx+1Ch], 4
0x1800500f8  jz      loc_180050316
0x1800500fe  cmp     byte ptr [rcx+19h], 2
0x180050102  jb      loc_180050316
0x180050108  mov     edx, 0A1h
0x18005010d  jmp     loc_18005000F
0x180050112  lea     rcx, [rbp+57h+var_78]
0x180050116  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18005011b  mov     rcx, rax; StringSecurityDescriptor
0x18005011e  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180050122  xor     r9d, r9d; SecurityDescriptorSize
0x180050125  mov     edx, edi; StringSDRevision
0x180050127  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005012d  test    eax, eax
0x18005012f  jnz     short loc_180050196
0x180050131  call    cs:__imp_GetLastError
0x180050137  mov     ebx, eax
0x180050139  test    eax, eax
0x18005013b  jz      short loc_18005015D
0x18005013d  test    eax, 0FFFF0000h
0x180050142  jnz     short loc_18005015D
0x180050144  test    eax, eax
0x180050146  jle     short loc_180050151
0x180050148  movzx   ebx, ax
0x18005014b  or      ebx, 80070000h
0x180050151  and     ebx, 0D057FFFFh
0x180050157  or      ebx, 50570000h
0x18005015d  test    ebx, ebx
0x18005015f  jns     short loc_180050196
0x180050161  mov     rcx, cs:WPP_GLOBAL_Control
0x180050168  lea     rax, WPP_GLOBAL_Control
0x18005016f  cmp     rcx, rax
0x180050172  jz      loc_180050316
0x180050178  test    byte ptr [rcx+1Ch], 4
0x18005017c  jz      loc_180050316
0x180050182  cmp     byte ptr [rcx+19h], 2
0x180050186  jb      loc_180050316
0x18005018c  mov     edx, 0A2h
0x180050191  jmp     loc_18005000F
0x180050196  mov     rax, [rbp+57h+SecurityDescriptor]
0x18005019a  lea     rcx, [rbp+57h+var_50]
0x18005019e  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800501a2  mov     [rbp+57h+SecurityAttributes.nLength], r14d
0x1800501a6  mov     [rbp+57h+SecurityAttributes.bInheritHandle], r15d
0x1800501aa  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800501af  mov     [rsp+0D0h+hTemplateFile], r15; hTemplateFile
0x1800501b4  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x1800501b8  mov     rcx, rax; lpFileName
0x1800501bb  mov     [rsp+0D0h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x1800501c3  xor     r8d, r8d; dwShareMode
0x1800501c6  mov     [rsp+0D0h+dwCreationDisposition], edi; dwCreationDisposition
0x1800501ca  mov     edx, 1F01FFh; dwDesiredAccess
0x1800501cf  call    cs:__imp_CreateFileW
0x1800501d5  mov     r14, rax
0x1800501d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800501dc  jnz     short loc_180050243
0x1800501de  call    cs:__imp_GetLastError
0x1800501e4  mov     ebx, eax
0x1800501e6  test    eax, eax
0x1800501e8  jz      short loc_18005020A
0x1800501ea  test    eax, 0FFFF0000h
0x1800501ef  jnz     short loc_18005020A
0x1800501f1  test    eax, eax
0x1800501f3  jle     short loc_1800501FE
0x1800501f5  movzx   ebx, ax
0x1800501f8  or      ebx, 80070000h
0x1800501fe  and     ebx, 0D058FFFFh
0x180050204  or      ebx, 50580000h
0x18005020a  test    ebx, ebx
0x18005020c  jns     short loc_180050243
0x18005020e  mov     rcx, cs:WPP_GLOBAL_Control
0x180050215  lea     rax, WPP_GLOBAL_Control
0x18005021c  cmp     rcx, rax
0x18005021f  jz      loc_180050316
0x180050225  test    byte ptr [rcx+1Ch], 4
0x180050229  jz      loc_180050316
0x18005022f  cmp     byte ptr [rcx+19h], 2
0x180050233  jb      loc_180050316
0x180050239  mov     edx, 0A3h
0x18005023e  jmp     loc_18005000F
0x180050243  or      rax, 0FFFFFFFFFFFFFFFFh
0x180050247  inc     rax
0x18005024a  cmp     [rsi+rax*2], r15w
0x18005024f  jnz     short loc_180050247
0x180050251  lea     edi, [rax+rax]
0x180050254  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r15; lpOverlapped
0x180050259  mov     r8d, edi; nNumberOfBytesToWrite
0x18005025c  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180050260  mov     rdx, rsi; lpBuffer
0x180050263  mov     rcx, r14; hFile
0x180050266  call    cs:__imp_WriteFile
0x18005026c  test    eax, eax
0x18005026e  jnz     short loc_1800502C6
0x180050270  call    cs:__imp_GetLastError
0x180050276  mov     ebx, eax
0x180050278  test    eax, eax
0x18005027a  jz      short loc_18005029C
0x18005027c  test    eax, 0FFFF0000h
0x180050281  jnz     short loc_18005029C
0x180050283  test    eax, eax
0x180050285  jle     short loc_180050290
0x180050287  movzx   ebx, ax
0x18005028a  or      ebx, 80070000h
0x180050290  and     ebx, 0D059FFFFh
0x180050296  or      ebx, 50590000h
0x18005029c  test    ebx, ebx
0x18005029e  jns     short loc_1800502C6
0x1800502a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800502a7  lea     rax, WPP_GLOBAL_Control
0x1800502ae  cmp     rcx, rax
0x1800502b1  jz      short loc_180050307
0x1800502b3  test    byte ptr [rcx+1Ch], 4
0x1800502b7  jz      short loc_180050307
0x1800502b9  cmp     byte ptr [rcx+19h], 2
0x1800502bd  jb      short loc_180050307
0x1800502bf  mov     edx, 0A4h
0x1800502c4  jmp     short loc_1800502F4
0x1800502c6  cmp     [rbp+57h+NumberOfBytesWritten], edi
0x1800502c9  jz      short loc_180050307
0x1800502cb  mov     ebx, 0D082001Dh
0x1800502d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800502d7  lea     rax, WPP_GLOBAL_Control
0x1800502de  cmp     rcx, rax
0x1800502e1  jz      short loc_180050307
0x1800502e3  test    byte ptr [rcx+1Ch], 4
0x1800502e7  jz      short loc_180050307
0x1800502e9  cmp     byte ptr [rcx+19h], 2
0x1800502ed  jb      short loc_180050307
0x1800502ef  mov     edx, 0A5h
0x1800502f4  mov     rcx, [rcx+10h]
0x1800502f8  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800502ff  mov     r9d, ebx
0x180050302  call    WPP_SF_d
0x180050307  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18005030b  jz      short loc_180050316
0x18005030d  mov     rcx, r14; hObject
0x180050310  call    cs:__imp_CloseHandle
0x180050316  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18005031a  test    rcx, rcx
0x18005031d  jz      short loc_180050325
0x18005031f  call    cs:__imp_LocalFree
0x180050325  lea     rcx, [rbp+57h+var_78]; this
0x180050329  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18005032e  lea     rcx, [rbp+57h+var_50]; this
0x180050332  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180050337  mov     eax, ebx
0x180050339  mov     rbx, [rsp+0D0h+arg_0]
  ... truncated ...
```
