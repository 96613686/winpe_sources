# CUserList::Get(bool,ulong *,GINA_USER_INFORMATION * *)

- ea: `0x180034f50`
- end: `0x180035440`
- name: `?Get@CUserList@@SAJ_NPEAKPEAPEAUGINA_USER_INFORMATION@@@Z`
- size: `1264`
- prototype: `__int64 __fastcall(bool, unsigned int *, struct GINA_USER_INFORMATION **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180032dd4`

## callees

- `0x18000dad0`
- `0x18000dafc`
- `0x180034a70`
- `0x180034b44`
- `0x180034bb4`
- `0x180034f50`
- `0x180035998`
- `0x180035a8c`
- `0x180035c50`
- `0x180035dfc`
- `0x180035eec`
- `0x18007727e`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800351f2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800351f2`
- `samcli!NetQueryDisplayInformation` at `0x180035127`
- `samcli!NetQueryDisplayInformation` at `0x180035127`
- `netutils!NetApiBufferFree` at `0x180035325`
- `netutils!NetApiBufferFree` at `0x180035325`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180035210`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180035270`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800352a0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180035371`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180035210`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180035270`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800352a0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180035371`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800352d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800353c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800353f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800352d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800353c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800353f2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800350b7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800350b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180035025`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180035025`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034fd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034fd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800350dd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800350dd`
- `ADVAPI32!GetUserNameW` at `0x180035152`
- `ADVAPI32!GetUserNameW` at `0x180035152`

## pseudocode

```c
__int64 __fastcall CUserList::Get(char a1, unsigned int *a2, struct GINA_USER_INFORMATION **a3)
{
  struct GINA_USER_INFORMATION **v3; // r12
  unsigned int *v4; // r15
  int v5; // edi
  WCHAR *v6; // rsi
  DWORD v7; // ebx
  struct GINA_USER_INFORMATION *v8; // rbx
  signed int v9; // edi
  DWORD v10; // eax
  DWORD v11; // r13d
  unsigned __int64 v12; // rax
  int v13; // ecx
  DWORD v14; // edx
  int v15; // r15d
  int v16; // ebx
  char v17; // r12
  __int64 v18; // r14
  void *v19; // rsi
  unsigned __int64 v20; // rdx
  const WCHAR *v21; // rcx
  struct _NET_DISPLAY_USER *v22; // rcx
  int v23; // r15d
  signed int v24; // esi
  char *v25; // r12
  void *v26; // rax
  void *v27; // r14
  __int128 v28; // xmm6
  __int128 v29; // xmm7
  __int64 v30; // rcx
  __int64 v32; // [rsp+68h] [rbp-A0h] BYREF
  PVOID SortedBuffer; // [rsp+70h] [rbp-98h] BYREF
  DWORD ReturnedEntryCount; // [rsp+78h] [rbp-90h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-8Ch] BYREF
  DWORD cValues; // [rsp+80h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+84h] [rbp-84h] BYREF
  DWORD cchValueName; // [rsp+88h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-78h] BYREF
  void *lpMem; // [rsp+98h] [rbp-70h] BYREF
  int v41; // [rsp+A0h] [rbp-68h]
  struct GINA_USER_INFORMATION **v42; // [rsp+A8h] [rbp-60h]
  unsigned int *v43; // [rsp+B0h] [rbp-58h]
  WCHAR Buffer[264]; // [rsp+B8h] [rbp-50h] BYREF

  v42 = a3;
  v3 = a3;
  v43 = a2;
  v4 = a2;
  LOBYTE(v32) = a1;
  ReturnedEntryCount = 0;
  SortedBuffer = 0;
  lpMem = 0;
  v41 = 0;
  hKey = 0;
  v5 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\SpecialAccounts\\UserList",
          0,
          1u,
          &hKey) )
  {
    cValues = 0;
    if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0) )
    {
      if ( cValues )
      {
        lpMem = operator new(saturated_mul(cValues, 0x208u));
        v6 = (WCHAR *)lpMem;
        if ( lpMem )
        {
          v7 = 0;
          if ( cValues )
          {
            do
            {
              Type = 0;
              cchValueName = 257;
              cbData = 4;
              if ( !RegEnumValueW(hKey, v7, &v6[260 * v5 + 2], &cchValueName, 0, &Type, (LPBYTE)&v6[260 * v5], &cbData)
                && Type == 4 )
              {
                ++v5;
              }
              ++v7;
            }
            while ( v7 < cValues );
            v41 = v5;
          }
        }
      }
    }
    RegCloseKey(hKey);
  }
  v8 = 0;
  Type = 0;
  hKey = 0;
  v9 = 0;
  CUserList::DetermineWellKnownAccountNames();
  SortedBuffer = 0;
  v10 = NetQueryDisplayInformation(0, 1u, 0, 0x64u, 0x12C28u, &ReturnedEntryCount, &SortedBuffer);
  cbData = v10;
  v11 = v10;
  if ( !v10 || v10 == 234 )
  {
    cchValueName = 257;
    if ( !GetUserNameW(Buffer, &cchValueName) )
      Buffer[0] = 0;
    v12 = -1;
    do
      ++v12;
    while ( Buffer[v12] );
    v13 = v12;
    if ( v12 > 0x7FFFFFFF )
      v13 = -1;
    v14 = ReturnedEntryCount;
    v15 = 0;
    if ( v12 <= 0x7FFFFFFF )
      v15 = v13;
    v16 = ReturnedEntryCount - 1;
    if ( (int)(ReturnedEntryCount - 1) >= 0 )
    {
      v17 = v32;
      v18 = v16;
      while ( 1 )
      {
        v19 = CUserList::ConvertNameToSID(*((LPCWSTR *)SortedBuffer + 5 * v18));
        if ( v19 )
          break;
LABEL_44:
        --v18;
        if ( --v16 < 0 )
        {
          v14 = ReturnedEntryCount;
          v11 = cbData;
          v3 = v42;
          goto LABEL_46;
        }
      }
      v20 = -1;
      v21 = (const WCHAR *)*((_QWORD *)SortedBuffer + 5 * v18);
      do
        ++v20;
      while ( v21[v20] );
      if ( v20 > 0x7FFFFFFF || CompareStringOrdinal(v21, v20, Buffer, v15, 1) == 2 )
      {
LABEL_43:
        LocalFree(v19);
        goto LABEL_44;
      }
      LOBYTE(v32) = 0;
      if ( EqualSid(v19, &CUserList::s_SIDAdministrator) && (int)IsAdministratorDisabled(&v32) >= 0 )
      {
        if ( (_BYTE)v32 )
        {
LABEL_41:
          v22 = (struct _NET_DISPLAY_USER *)SortedBuffer;
          goto LABEL_42;
        }
        v22 = (struct _NET_DISPLAY_USER *)SortedBuffer;
      }
      else
      {
        v22 = (struct _NET_DISPLAY_USER *)SortedBuffer;
        if ( (*((_BYTE *)SortedBuffer + 40 * v18 + 16) & 2) != 0 )
          goto LABEL_42;
      }
      if ( (v22[v18].usri1_flags & 0x10) == 0 )
      {
        if ( !CSpecialAccounts::_IterateAccounts((CSpecialAccounts *)&lpMem, v22[v18].usri1_name, 0)
          && (!v17 || !EqualSid(v19, &CUserList::s_SIDGuest))
          && (CSpecialAccounts::_IterateAccounts(
                (CSpecialAccounts *)&lpMem,
                *((const unsigned __int16 **)SortedBuffer + 5 * v18),
                1u)
           || EqualSid(v19, &CUserList::s_SIDGuest)
           || CUserList::IsUserMemberOfLocalKnownGroup(*((LPCWSTR *)SortedBuffer + 5 * v18))) )
        {
          goto LABEL_43;
        }
        goto LABEL_41;
      }
LABEL_42:
      CUserList::DeleteEnumerateUsers(v22, &ReturnedEntryCount, v16);
      goto LABEL_43;
    }
LABEL_46:
    if ( CUserList::ParseDisplayInformation(
           (const struct _NET_DISPLAY_USER *)SortedBuffer,
           v14,
           (struct GINA_USER_INFORMATION **)&hKey,
           &Type) )
    {
      v9 = Type;
      v8 = (struct GINA_USER_INFORMATION *)hKey;
    }
    else
    {
      v11 = 14;
      v8 = 0;
      v9 = 0;
    }
    NetApiBufferFree(SortedBuffer);
    if ( !v11 )
    {
      CUserList::Sort(v8, v9);
      v23 = 0;
      v24 = 0;
      do
      {
        if ( v24 >= v9 )
          break;
        v25 = (char *)v8 + 32 * v24;
        v26 = CUserList::ConvertNameToSID(*(LPCWSTR *)v25);
        v27 = v26;
        if ( v26 )
        {
          if ( EqualSid(v26, &CUserList::s_SIDGuest) )
          {
            v28 = *(_OWORD *)v25;
            v29 = *((_OWORD *)v25 + 1);
            v23 = 1;
            memmove_0(v25, (char *)v8 + 32 * v24 + 32, 32LL * (unsigned int)(v9 - v24 - 1));
            v30 = 32LL * (unsigned int)(v9 - 1);
            *(_OWORD *)((char *)v8 + v30) = v28;
            *(_OWORD *)((char *)v8 + v30 + 16) = v29;
          }
          else
          {
            v23 = 0;
          }
          LocalFree(v27);
        }
        ++v24;
      }
      while ( !v23 );
      v3 = v42;
    }
    v4 = v43;
  }
  if ( v3 )
  {
    *v3 = v8;
  }
  else if ( v8 )
  {
    LocalFree(v8);
  }
  if ( v4 )
    *v4 = v9;
  operator delete(lpMem);
  return v11;
}

```

## disassembly

```asm
0x180034f50  mov     rax, rsp
0x180034f53  mov     [rax+8], rbx
0x180034f57  push    rbp
0x180034f58  push    rsi
0x180034f59  push    rdi
0x180034f5a  push    r12
0x180034f5c  push    r13
0x180034f5e  push    r14
0x180034f60  push    r15
0x180034f62  lea     rbp, [rax-228h]
0x180034f69  sub     rsp, 2F0h
0x180034f70  movaps  xmmword ptr [rax-48h], xmm6
0x180034f74  movaps  xmmword ptr [rax-58h], xmm7
0x180034f78  mov     rax, cs:__security_cookie
0x180034f7f  xor     rax, rsp
0x180034f82  mov     [rbp+220h+var_60], rax
0x180034f89  xor     r14d, r14d
0x180034f8c  mov     [rbp+220h+var_280], r8
0x180034f90  mov     r12, r8
0x180034f93  mov     [rbp+220h+var_278], rdx
0x180034f97  mov     r15, rdx
0x180034f9a  mov     byte ptr [rsp+320h+var_2C0], cl
0x180034f9e  lea     rax, [rbp+220h+hKey]
0x180034fa2  mov     [rsp+320h+ReturnedEntryCount], r14d
0x180034fa7  lea     r9d, [r14+1]; samDesired
0x180034fab  mov     [rsp+320h+SortedBuffer], r14
0x180034fb0  xor     r8d, r8d; ulOptions
0x180034fb3  mov     [rbp+220h+lpMem], r14
0x180034fb7  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180034fbe  mov     [rbp+220h+var_288], r14d
0x180034fc2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034fc9  mov     [rbp+220h+hKey], r14
0x180034fcd  mov     edi, r14d
0x180034fd0  mov     [rsp+320h+phkResult], rax; phkResult
0x180034fd5  call    cs:__imp_RegOpenKeyExW
0x180034fdb  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180034fdf  test    eax, eax
0x180034fe1  jnz     loc_1800350E3
0x180034fe7  mov     rcx, [rbp+220h+hKey]; hKey
0x180034feb  lea     rax, [rsp+320h+cValues]
0x180034ff0  mov     [rsp+320h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180034ff5  xor     r9d, r9d; lpReserved
0x180034ff8  mov     [rsp+320h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180034ffd  xor     r8d, r8d; lpcchClass
0x180035000  mov     [rsp+320h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180035005  xor     edx, edx; lpClass
0x180035007  mov     [rsp+320h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18003500c  mov     [rsp+320h+lpcValues], rax; lpcValues
0x180035011  mov     [rsp+320h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180035016  mov     [rsp+320h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18003501b  mov     [rsp+320h+phkResult], r14; lpcSubKeys
0x180035020  mov     [rsp+320h+cValues], r14d
0x180035025  call    cs:__imp_RegQueryInfoKeyW
0x18003502b  test    eax, eax
0x18003502d  jnz     loc_1800350D9
0x180035033  mov     eax, [rsp+320h+cValues]
0x180035037  test    eax, eax
0x180035039  jz      loc_1800350D9
0x18003503f  mov     ecx, eax
0x180035041  mov     eax, 208h
0x180035046  mul     rcx
0x180035049  cmovb   rax, rsi
0x18003504d  mov     rcx, rax; unsigned __int64
0x180035050  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035055  mov     [rbp+220h+lpMem], rax
0x180035059  mov     rsi, rax
0x18003505c  test    rax, rax
0x18003505f  jz      short loc_1800350D5
0x180035061  mov     ebx, r14d
0x180035064  cmp     [rsp+320h+cValues], r14d
0x180035069  jbe     short loc_1800350D5
0x18003506b  lea     rcx, [rsp+320h+cbData]
0x180035070  mov     eax, edi
0x180035072  mov     [rsp+320h+lpcValues], rcx; lpcbData
0x180035077  lea     r9, [rbp+220h+cchValueName]; lpcchValueName
0x18003507b  mov     rcx, [rbp+220h+hKey]; hKey
0x18003507f  mov     edx, ebx; dwIndex
0x180035081  imul    rax, 208h
0x180035088  mov     [rsp+320h+Type], r14d
0x18003508d  add     rax, rsi
0x180035090  mov     [rbp+220h+cchValueName], 101h
0x180035097  mov     [rsp+320h+lpcbMaxClassLen], rax; lpData
0x18003509c  mov     [rsp+320h+cbData], 4
0x1800350a4  lea     r8, [rax+4]; lpValueName
0x1800350a8  lea     rax, [rsp+320h+Type]
0x1800350ad  mov     [rsp+320h+lpcbMaxSubKeyLen], rax; lpType
0x1800350b2  mov     [rsp+320h+phkResult], r14; lpReserved
0x1800350b7  call    cs:__imp_RegEnumValueW
0x1800350bd  test    eax, eax
0x1800350bf  jnz     short loc_1800350CA
0x1800350c1  cmp     [rsp+320h+Type], 4
0x1800350c6  jnz     short loc_1800350CA
0x1800350c8  inc     edi
0x1800350ca  inc     ebx
0x1800350cc  cmp     ebx, [rsp+320h+cValues]
0x1800350d0  jb      short loc_18003506B
0x1800350d2  mov     [rbp+220h+var_288], edi
0x1800350d5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800350d9  mov     rcx, [rbp+220h+hKey]; hKey
0x1800350dd  call    cs:__imp_RegCloseKey
0x1800350e3  mov     rbx, r14
0x1800350e6  mov     [rsp+320h+Type], r14d
0x1800350eb  mov     [rbp+220h+hKey], rbx
0x1800350ef  mov     edi, r14d
0x1800350f2  call    ?DetermineWellKnownAccountNames@CUserList@@CAXXZ; CUserList::DetermineWellKnownAccountNames(void)
0x1800350f7  lea     rax, [rsp+320h+SortedBuffer]
0x1800350fc  mov     [rsp+320h+SortedBuffer], r14
0x180035101  mov     [rsp+320h+lpcbMaxClassLen], rax; SortedBuffer
0x180035106  mov     r9d, 64h ; 'd'; EntriesRequested
0x18003510c  lea     rax, [rsp+320h+ReturnedEntryCount]
0x180035111  xor     r8d, r8d; Index
0x180035114  mov     [rsp+320h+lpcbMaxSubKeyLen], rax; ReturnedEntryCount
0x180035119  xor     ecx, ecx; ServerName
0x18003511b  mov     dword ptr [rsp+320h+phkResult], 12C28h; PreferredMaximumLength
0x180035123  lea     edx, [r9-63h]; Level
0x180035127  call    cs:__imp_NetQueryDisplayInformation
0x18003512d  mov     [rsp+320h+cbData], eax
0x180035131  mov     r13d, eax
0x180035134  test    eax, eax
0x180035136  jz      short loc_180035143
0x180035138  cmp     eax, 0EAh
0x18003513d  jnz     loc_1800353DF
0x180035143  lea     rdx, [rbp+220h+cchValueName]; pcbBuffer
0x180035147  mov     [rbp+220h+cchValueName], 101h
0x18003514e  lea     rcx, [rbp+220h+Buffer]; lpBuffer
0x180035152  call    cs:__imp_GetUserNameW
0x180035158  test    eax, eax
0x18003515a  jnz     short loc_180035161
0x18003515c  mov     [rbp+220h+Buffer], r14w
0x180035161  lea     rcx, [rbp+220h+Buffer]
0x180035165  mov     rax, rsi
0x180035168  inc     rax
0x18003516b  cmp     [rcx+rax*2], r14w
0x180035170  jnz     short loc_180035168
0x180035172  mov     edx, 7FFFFFFFh
0x180035177  mov     ecx, eax
0x180035179  cmp     rax, rdx
0x18003517c  jbe     short loc_180035180
0x18003517e  mov     ecx, esi
0x180035180  mov     edx, [rsp+320h+ReturnedEntryCount]
0x180035184  mov     r15d, r14d
0x180035187  cmovbe  r15d, ecx
0x18003518b  lea     ebx, [rdx-1]
0x18003518e  test    ebx, ebx
0x180035190  js      loc_1800352F3
0x180035196  mov     r12b, byte ptr [rsp+320h+var_2C0]
0x18003519b  xor     r13d, r13d
0x18003519e  movsxd  r14, ebx
0x1800351a1  mov     rcx, [rsp+320h+SortedBuffer]
0x1800351a6  lea     rdi, [r14+r14*4]
0x1800351aa  mov     rcx, [rcx+rdi*8]; lpAccountName
0x1800351ae  call    ?ConvertNameToSID@CUserList@@CAPEAXPEBG@Z; CUserList::ConvertNameToSID(ushort const *)
0x1800351b3  mov     rsi, rax
0x1800351b6  test    rax, rax
0x1800351b9  jz      loc_1800352D7
0x1800351bf  mov     rcx, [rsp+320h+SortedBuffer]
0x1800351c4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800351c8  mov     rcx, [rcx+rdi*8]; lpString1
0x1800351cc  inc     rdx; cchCount1
0x1800351cf  cmp     [rcx+rdx*2], r13w
0x1800351d4  jnz     short loc_1800351CC
0x1800351d6  cmp     rdx, 7FFFFFFFh
0x1800351dd  ja      loc_1800352CE
0x1800351e3  mov     r9d, r15d; cchCount2
0x1800351e6  mov     dword ptr [rsp+320h+phkResult], 1; bIgnoreCase
0x1800351ee  lea     r8, [rbp+220h+Buffer]; lpString2
0x1800351f2  call    cs:__imp_CompareStringOrdinal
0x1800351f8  cmp     eax, 2
0x1800351fb  jz      loc_1800352CE
0x180035201  lea     rdx, ?s_SIDAdministrator@CUserList@@0PAEA; pSid2
0x180035208  mov     byte ptr [rsp+320h+var_2C0], r13b
0x18003520d  mov     rcx, rsi; pSid1
0x180035210  call    cs:__imp_EqualSid
0x180035216  test    eax, eax
0x180035218  jz      short loc_18003523A
0x18003521a  lea     rcx, [rsp+320h+var_2C0]
0x18003521f  call    _IsAdministratorDisabled
0x180035224  test    eax, eax
0x180035226  js      short loc_18003523A
0x180035228  cmp     byte ptr [rsp+320h+var_2C0], r13b
0x18003522d  jnz     loc_1800352BC
0x180035233  mov     rcx, [rsp+320h+SortedBuffer]
0x180035238  jmp     short loc_180035246
0x18003523a  mov     rcx, [rsp+320h+SortedBuffer]
0x18003523f  test    byte ptr [rcx+rdi*8+10h], 2
0x180035244  jnz     short loc_1800352C1
0x180035246  test    byte ptr [rcx+rdi*8+10h], 10h
0x18003524b  jnz     short loc_1800352C1
0x18003524d  mov     rdx, [rcx+rdi*8]; unsigned __int16 *
0x180035251  xor     r8d, r8d; unsigned int
0x180035254  lea     rcx, [rbp+220h+lpMem]; this
0x180035258  call    ?_IterateAccounts@CSpecialAccounts@@AEBA_NPEBGK@Z; CSpecialAccounts::_IterateAccounts(ushort const *,ulong)
0x18003525d  test    al, al
0x18003525f  jnz     short loc_1800352BC
0x180035261  test    r12b, r12b
0x180035264  jz      short loc_18003527A
0x180035266  lea     rdx, ?s_SIDGuest@CUserList@@0PAEA; pSid2
0x18003526d  mov     rcx, rsi; pSid1
0x180035270  call    cs:__imp_EqualSid
0x180035276  test    eax, eax
0x180035278  jnz     short loc_1800352BC
0x18003527a  mov     rdx, [rsp+320h+SortedBuffer]
0x18003527f  lea     rcx, [rbp+220h+lpMem]; this
0x180035283  mov     r8d, 1; unsigned int
0x180035289  mov     rdx, [rdx+rdi*8]; unsigned __int16 *
0x18003528d  call    ?_IterateAccounts@CSpecialAccounts@@AEBA_NPEBGK@Z; CSpecialAccounts::_IterateAccounts(ushort const *,ulong)
0x180035292  test    al, al
0x180035294  jnz     short loc_1800352CE
0x180035296  lea     rdx, ?s_SIDGuest@CUserList@@0PAEA; pSid2
0x18003529d  mov     rcx, rsi; pSid1
0x1800352a0  call    cs:__imp_EqualSid
0x1800352a6  test    eax, eax
0x1800352a8  jnz     short loc_1800352CE
0x1800352aa  mov     rcx, [rsp+320h+SortedBuffer]
0x1800352af  mov     rcx, [rcx+rdi*8]; username
0x1800352b3  call    ?IsUserMemberOfLocalKnownGroup@CUserList@@CA_NPEBG@Z; CUserList::IsUserMemberOfLocalKnownGroup(ushort const *)
0x1800352b8  test    al, al
0x1800352ba  jnz     short loc_1800352CE
0x1800352bc  mov     rcx, [rsp+320h+SortedBuffer]; struct _NET_DISPLAY_USER *
0x1800352c1  mov     r8d, ebx; int
0x1800352c4  lea     rdx, [rsp+320h+ReturnedEntryCount]; unsigned int *
0x1800352c9  call    ?DeleteEnumerateUsers@CUserList@@CAXPEAU_NET_DISPLAY_USER@@AEAKH@Z; CUserList::DeleteEnumerateUsers(_NET_DISPLAY_USER *,ulong &,int)
0x1800352ce  mov     rcx, rsi; hMem
0x1800352d1  call    cs:__imp_LocalFree
0x1800352d7  dec     r14
0x1800352da  sub     ebx, 1
0x1800352dd  jns     loc_1800351A1
0x1800352e3  mov     edx, [rsp+320h+ReturnedEntryCount]; unsigned int
0x1800352e7  xor     r14d, r14d
0x1800352ea  mov     r13d, [rsp+320h+cbData]
0x1800352ef  mov     r12, [rbp+220h+var_280]
0x1800352f3  mov     rcx, [rsp+320h+SortedBuffer]; struct _NET_DISPLAY_USER *
0x1800352f8  lea     r9, [rsp+320h+Type]; unsigned int *
0x1800352fd  lea     r8, [rbp+220h+hKey]; struct GINA_USER_INFORMATION **
0x180035301  call    ?ParseDisplayInformation@CUserList@@CA_NPEBU_NET_DISPLAY_USER@@KAEAPEAUGINA_USER_INFORMATION@@AEAK@Z; CUserList::ParseDisplayInformation(_NET_DISPLAY_USER const *,ulong,GINA_USER_INFORMATION * &,ulong &)
0x180035306  test    al, al
0x180035308  jnz     short loc_180035318
0x18003530a  mov     r13d, 0Eh
0x180035310  mov     rbx, r14
0x180035313  mov     edi, r14d
0x180035316  jmp     short loc_180035320
0x180035318  mov     edi, [rsp+320h+Type]
0x18003531c  mov     rbx, [rbp+220h+hKey]
0x180035320  mov     rcx, [rsp+320h+SortedBuffer]; Buffer
0x180035325  call    cs:__imp_NetApiBufferFree
0x18003532b  test    r13d, r13d
0x18003532e  jnz     loc_1800353DB
0x180035334  mov     edx, edi; unsigned int
0x180035336  mov     rcx, rbx; struct GINA_USER_INFORMATION *
0x180035339  call    ?Sort@CUserList@@CAXPEAUGINA_USER_INFORMATION@@K@Z; CUserList::Sort(GINA_USER_INFORMATION *,ulong)
0x18003533e  mov     r15d, r14d
0x180035341  mov     esi, r14d
0x180035344  cmp     esi, edi
0x180035346  jge     loc_1800353D7
0x18003534c  movsxd  r12, esi
0x18003534f  shl     r12, 5
0x180035353  add     r12, rbx
0x180035356  mov     rcx, [r12]; lpAccountName
0x18003535a  call    ?ConvertNameToSID@CUserList@@CAPEAXPEBG@Z; CUserList::ConvertNameToSID(ushort const *)
0x18003535f  mov     r14, rax
0x180035362  test    rax, rax
0x180035365  jz      short loc_1800353CC
0x180035367  lea     rdx, ?s_SIDGuest@CUserList@@0PAEA; pSid2
0x18003536e  mov     rcx, rax; pSid1
0x180035371  call    cs:__imp_EqualSid
0x180035377  test    eax, eax
0x180035379  jz      short loc_1800353C0
0x18003537b  movups  xmm6, xmmword ptr [r12]
0x180035380  mov     r8d, edi
0x180035383  lea     eax, [rsi+1]
0x180035386  movups  xmm7, xmmword ptr [r12+10h]
0x18003538c  sub     r8d, esi
0x18003538f  movsxd  rdx, eax
0x180035392  dec     r8d
0x180035395  shl     rdx, 5
0x180035399  shl     r8, 5; Size
0x18003539d  add     rdx, rbx; Src
0x1800353a0  mov     rcx, r12; void *
0x1800353a3  mov     r15d, 1
0x1800353a9  call    memmove_0
0x1800353ae  lea     ecx, [rdi-1]
0x1800353b1  shl     rcx, 5
0x1800353b5  movups  xmmword ptr [rcx+rbx], xmm6
0x1800353b9  movups  xmmword ptr [rcx+rbx+10h], xmm7
0x1800353be  jmp     short loc_1800353C3
0x1800353c0  xor     r15d, r15d
0x1800353c3  mov     rcx, r14; hMem
0x1800353c6  call    cs:__imp_LocalFree
0x1800353cc  inc     esi
0x1800353ce  test    r15d, r15d
0x1800353d1  jz      loc_180035344
0x1800353d7  mov     r12, [rbp+220h+var_280]
0x1800353db  mov     r15, [rbp+220h+var_278]
0x1800353df  test    r12, r12
0x1800353e2  jz      short loc_1800353EA
0x1800353e4  mov     [r12], rbx
0x1800353e8  jmp     short loc_1800353F8
0x1800353ea  test    rbx, rbx
0x1800353ed  jz      short loc_1800353F8
0x1800353ef  mov     rcx, rbx; hMem
  ... truncated ...
```
