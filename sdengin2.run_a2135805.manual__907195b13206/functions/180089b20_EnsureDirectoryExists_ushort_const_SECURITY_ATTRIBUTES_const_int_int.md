# EnsureDirectoryExists(ushort const *,_SECURITY_ATTRIBUTES const *,int,int)

- ea: `0x180089b20`
- end: `0x18008a1b1`
- name: `?EnsureDirectoryExists@@YAJPEBGPEBU_SECURITY_ATTRIBUTES@@HH@Z`
- size: `1681`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPSECURITY_ATTRIBUTES lpSecurityAttributes, int, int)`
- caller_count: `8`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001bba8`
- `0x18002af08`
- `0x180037600`
- `0x1800381b0`
- `0x180038578`
- `0x18004f1c8`
- `0x1800b9a24`
- `0x1800bab44`

## callees

- `0x1800083e4`
- `0x180008620`
- `0x180014c30`
- `0x180072e08`
- `0x180072f14`
- `0x180089b20`
- `0x18008aa6c`
- `0x18008c900`
- `0x18008d33c`
- `0x18008d660`
- `0x1800935fc`
- `0x18009da98`
- `0x18009e380`
- `0x18009e904`
- `0x18009e924`
- `0x18009ece8`
- `0x18009f560`
- `0x1800cf58e`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180089fc8`
- `KERNEL32!CreateFileW` at `0x180089fc8`
- `KERNEL32!GetLastError` at `0x180089d2e`
- `KERNEL32!GetLastError` at `0x180089d8d`
- `KERNEL32!GetLastError` at `0x180089ec7`
- `KERNEL32!GetLastError` at `0x180089f8b`
- `KERNEL32!GetLastError` at `0x180089d2e`
- `KERNEL32!GetLastError` at `0x180089d8d`
- `KERNEL32!GetLastError` at `0x180089ec7`
- `KERNEL32!GetLastError` at `0x180089f8b`
- `KERNEL32!CloseHandle` at `0x180089e55`
- `KERNEL32!CloseHandle` at `0x180089ff4`
- `KERNEL32!CloseHandle` at `0x180089e55`
- `KERNEL32!CloseHandle` at `0x180089ff4`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180089d1a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180089d79`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180089f78`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008a0f3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180089d1a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180089d79`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180089f78`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008a0f3`

## string_xrefs

- `0x180089b4b`: `EnsureDirectoryExists`
- `0x18008a02a`: `Created`
- `0x18008a020`: `Already existed`

## pseudocode

```c
__int64 __fastcall EnsureDirectoryExists(
        const unsigned __int16 *a1,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        int a3,
        int a4)
{
  __int16 v7; // ax
  __int64 FileW; // rbx
  unsigned __int64 v9; // rax
  bool v10; // cf
  unsigned __int16 v11; // dx
  signed int LastFailureAsHRESULT; // edi
  wchar_t *v13; // r14
  int v14; // eax
  __int16 v15; // cx
  int v16; // edi
  void *v17; // rdx
  __int16 v19; // ax
  char LastError; // al
  unsigned int v21; // eax
  bool i; // zf
  unsigned int v23; // ebx
  WCHAR *v24; // r12
  BOOL DirectoryW; // r15d
  const char *v26; // r9
  void *v27; // rdx
  __int64 v28; // rcx
  void *v29; // rdx
  void *lpSecurityDescriptor; // rdx
  int v31; // [rsp+48h] [rbp-49h] BYREF
  __int16 v32; // [rsp+4Ch] [rbp-45h]
  __int16 v33; // [rsp+4Eh] [rbp-43h]
  wchar_t *String1[2]; // [rsp+80h] [rbp-11h] BYREF
  LPCWSTR lpPathName[2]; // [rsp+90h] [rbp-1h] BYREF
  PSID pOwner; // [rsp+A0h] [rbp+Fh] BYREF
  int v37; // [rsp+A8h] [rbp+17h]
  PACL pDacl; // [rsp+B0h] [rbp+1Fh]
  __int64 v39; // [rsp+B8h] [rbp+27h]
  __int64 v40; // [rsp+C0h] [rbp+2Fh]
  unsigned int v41; // [rsp+F8h] [rbp+67h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v31, "EnsureDirectoryExists", 0x174u, 1u);
  String1[0] = (wchar_t *)qword_1800EE510;
  lpPathName[0] = (LPCWSTR)qword_1800EE510;
  v7 = 381;
  String1[1] = 0;
  FileW = -1;
  lpPathName[1] = 0;
  pOwner = 0;
  v37 = 0;
  pDacl = 0;
  v39 = 0;
  v40 = 0;
  if ( !a1 )
    goto LABEL_34;
  v32 = 381;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  v10 = v9 < 3;
  v7 = 383;
  if ( v10 )
    goto LABEL_89;
  v31 = 0;
  v32 = 383;
  LastFailureAsHRESULT = CBsString::Set((CBsString *)String1, a1);
  v31 = LastFailureAsHRESULT;
  v7 = 386;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_36;
  v32 = 386;
  CBsString::UnTrailing((CBsString *)String1, v11);
  LastFailureAsHRESULT = CBsString::AntiCanonicalize((CBsString *)String1);
  v31 = LastFailureAsHRESULT;
  v7 = 389;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_36;
  v13 = String1[0];
  v32 = 389;
  if ( !wcsncmp_0(String1[0], L"\\\\?\\UNC\\", 8u) )
  {
    v14 = CBsString::Find((CBsString *)String1, 0x5Cu, 8u);
    v15 = 395;
    if ( v14 == -1
      || (v32 = 395, v31 = 0, v16 = CBsString::Find((CBsString *)String1, 0x5Cu, v14 + 1), v15 = 398, v16 == -1) )
    {
      LastFailureAsHRESULT = -2147024893;
      v33 = v15;
      v31 = -2147024893;
      goto LABEL_37;
    }
    v32 = 398;
    goto LABEL_15;
  }
  if ( wcsncmp_0(v13, L"\\\\?\\", 4u) )
  {
    LastFailureAsHRESULT = -2147024893;
    v7 = 408;
    goto LABEL_35;
  }
  v16 = CBsString::Find((CBsString *)String1, 0x5Cu, 4u);
  v7 = 404;
  if ( v16 == -1 )
  {
LABEL_89:
    LastFailureAsHRESULT = -2147024893;
    goto LABEL_35;
  }
  v32 = 404;
LABEL_15:
  v31 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids, v13);
  if ( CreateDirectoryW(v13, lpSecurityAttributes) )
    goto LABEL_93;
  if ( GetLastError() == 64 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids, v13);
    if ( CreateDirectoryW(v13, lpSecurityAttributes) )
    {
LABEL_93:
      if ( a3 )
      {
        if ( lpSecurityAttributes )
        {
          lpSecurityDescriptor = lpSecurityAttributes->lpSecurityDescriptor;
          if ( lpSecurityDescriptor )
          {
            v31 = _PropagateInheritedAces(v13, lpSecurityDescriptor);
            LastFailureAsHRESULT = v31;
            if ( v31 < 0 )
            {
              v7 = 445;
              goto LABEL_36;
            }
          }
        }
      }
      v19 = 448;
      goto LABEL_41;
    }
  }
  if ( GetLastError() == 183 )
  {
    if ( !a4 )
    {
LABEL_40:
      v19 = 437;
LABEL_41:
      LastFailureAsHRESULT = 0;
      v32 = v19;
      v31 = 0;
      goto LABEL_37;
    }
    if ( lpSecurityAttributes )
    {
      v17 = lpSecurityAttributes->lpSecurityDescriptor;
      if ( v17 )
      {
        v31 = 0;
        v32 = 426;
        LastFailureAsHRESULT = CSdSecurityDescriptorInfo::Initialize(&pOwner, v17);
        v31 = LastFailureAsHRESULT;
        v7 = 427;
        if ( LastFailureAsHRESULT < 0 )
          goto LABEL_36;
        v32 = 427;
        LastFailureAsHRESULT = SetSecurityInfo(v13, pOwner, pDacl);
        v31 = LastFailureAsHRESULT;
        v7 = 428;
        if ( LastFailureAsHRESULT < 0 )
          goto LABEL_36;
        v32 = 428;
        if ( a3 )
        {
          v31 = _PropagateInheritedAces(v13, lpSecurityAttributes->lpSecurityDescriptor);
          LastFailureAsHRESULT = v31;
          if ( v31 < 0 )
          {
            v7 = 433;
            goto LABEL_36;
          }
        }
        goto LABEL_40;
      }
    }
    v7 = 426;
LABEL_34:
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_df8cd073d3d8361ada3b590c76323716_Traceguids,
      (_DWORD)v13,
      LastError);
  }
  v21 = CBsString::Find((CBsString *)String1, 0x5Cu, v16 + 1);
  for ( i = v21 == -1; ; i = v21 == -1 )
  {
    v23 = v21;
    v41 = v21;
    if ( i )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids, v13);
      if ( CreateDirectoryW(v13, lpSecurityAttributes) )
      {
        LastFailureAsHRESULT = 0;
        v31 = 0;
        v32 = 495;
        if ( !a3 )
          goto LABEL_71;
        if ( !lpSecurityAttributes )
          goto LABEL_71;
        v29 = lpSecurityAttributes->lpSecurityDescriptor;
        if ( !v29 )
          goto LABEL_71;
        LastFailureAsHRESULT = _PropagateInheritedAces(v13, v29);
        v31 = LastFailureAsHRESULT;
        v7 = 499;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v32 = 499;
          goto LABEL_71;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v28);
        v31 = LastFailureAsHRESULT;
        v7 = 495;
      }
LABEL_77:
      FileW = -1;
      goto LABEL_36;
    }
    v31 = CBsString::Set((CBsString *)lpPathName, v13, v21);
    LastFailureAsHRESULT = v31;
    if ( v31 < 0 )
    {
      v33 = 457;
LABEL_71:
      FileW = -1;
      goto LABEL_37;
    }
    v32 = 457;
    v24 = (WCHAR *)lpPathName[0];
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids, lpPathName[0]);
    DirectoryW = CreateDirectoryW(v24, lpSecurityAttributes);
    if ( !DirectoryW )
    {
      LastFailureAsHRESULT = GetLastError();
      if ( LastFailureAsHRESULT != 183 )
        break;
    }
LABEL_55:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v26 = "Created";
      if ( !DirectoryW )
        v26 = "Already existed";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids, v26);
    }
    if ( DirectoryW )
    {
      if ( a3 )
      {
        if ( lpSecurityAttributes )
        {
          v27 = lpSecurityAttributes->lpSecurityDescriptor;
          if ( v27 )
          {
            LastFailureAsHRESULT = _PropagateInheritedAces(v24, v27);
            v31 = LastFailureAsHRESULT;
            v7 = 487;
            if ( LastFailureAsHRESULT < 0 )
              goto LABEL_77;
            v32 = 487;
          }
        }
      }
    }
    v21 = CBsString::Find((CBsString *)String1, 0x5Cu, v23 + 1);
  }
  FileW = (__int64)CreateFileW(v24, 0x100000u, DirectoryW + 7, 0, 3u, 0x2000000u, 0);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v31 = DirectoryW;
    v32 = 476;
    CloseHandle((HANDLE)FileW);
    v23 = v41;
    goto LABEL_55;
  }
  if ( LastFailureAsHRESULT > 0 )
    LastFailureAsHRESULT = (unsigned __int16)LastFailureAsHRESULT | 0x80070000;
  v7 = 476;
LABEL_35:
  v31 = LastFailureAsHRESULT;
LABEL_36:
  v33 = v7;
LABEL_37:
  CSdSecurityDescriptorInfo::~CSdSecurityDescriptorInfo((CSdSecurityDescriptorInfo *)&pOwner);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CBsString::_Release((CBsString *)lpPathName);
  CBsString::_Release((CBsString *)String1);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v31);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180089b20  mov     rax, rsp
0x180089b23  mov     [rax+10h], rbx
0x180089b27  mov     [rax+20h], rsi
0x180089b2b  mov     [rax+18h], r8d
0x180089b2f  push    rbp
0x180089b30  push    rdi
0x180089b31  push    r12
0x180089b33  push    r14
0x180089b35  push    r15
0x180089b37  lea     rbp, [rax-5Fh]
0x180089b3b  sub     rsp, 0C0h
0x180089b42  mov     r12d, r9d
0x180089b45  mov     rsi, rdx
0x180089b48  mov     rdi, rcx
0x180089b4b  lea     rdx, aEnsuredirector_0; "EnsureDirectoryExists"
0x180089b52  mov     r9d, 1; unsigned __int16
0x180089b58  lea     rcx, [rbp+57h+var_A0]; this
0x180089b5c  mov     r8d, 174h; unsigned __int16
0x180089b62  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180089b67  xor     r15d, r15d
0x180089b6a  lea     rax, qword_1800EE510
0x180089b71  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180089b75  mov     [rbp+57h+String1], rax
0x180089b79  mov     [rbp+57h+lpPathName], rax
0x180089b7d  mov     eax, 17Dh
0x180089b82  mov     [rbp+57h+var_60], r15
0x180089b86  mov     rbx, rcx
0x180089b89  mov     [rbp+57h+var_50], r15
0x180089b8d  mov     [rbp+57h+pOwner], r15
0x180089b91  mov     [rbp+57h+var_40], r15d
0x180089b95  mov     [rbp+57h+pDacl], r15
0x180089b99  mov     [rbp+57h+var_30], r15
0x180089b9d  mov     [rbp+57h+var_28], r15
0x180089ba1  test    rdi, rdi
0x180089ba4  jz      loc_180089E33
0x180089baa  mov     [rbp+57h+var_9C], ax
0x180089bae  mov     rax, rcx
0x180089bb1  inc     rax
0x180089bb4  cmp     [rdi+rax*2], r15w
0x180089bb9  jnz     short loc_180089BB1
0x180089bbb  cmp     rax, 3
0x180089bbf  mov     eax, 17Fh
0x180089bc4  jb      loc_18008A198
0x180089bca  mov     rdx, rdi; unsigned __int16 *
0x180089bcd  mov     [rbp+57h+var_A0], r15d
0x180089bd1  lea     rcx, [rbp+57h+String1]; this
0x180089bd5  mov     [rbp+57h+var_9C], ax
0x180089bd9  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180089bde  mov     edi, eax
0x180089be0  mov     [rbp+57h+var_A0], eax
0x180089be3  test    eax, eax
0x180089be5  mov     eax, 182h
0x180089bea  js      loc_180089E3B
0x180089bf0  lea     rcx, [rbp+57h+String1]; this
0x180089bf4  mov     [rbp+57h+var_9C], ax
0x180089bf8  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x180089bfd  lea     rcx, [rbp+57h+String1]; this
0x180089c01  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x180089c06  mov     edi, eax
0x180089c08  mov     [rbp+57h+var_A0], eax
0x180089c0b  test    eax, eax
0x180089c0d  mov     eax, 185h
0x180089c12  js      loc_180089E3B
0x180089c18  mov     r14, [rbp+57h+String1]
0x180089c1c  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x180089c23  mov     edi, 8
0x180089c28  mov     [rbp+57h+var_9C], ax
0x180089c2c  mov     r8d, edi; MaxCount
0x180089c2f  mov     rcx, r14; String1
0x180089c32  call    wcsncmp_0
0x180089c37  test    eax, eax
0x180089c39  jnz     short loc_180089C96
0x180089c3b  lea     edx, [rdi+54h]; unsigned __int16
0x180089c3e  mov     r8d, edi; unsigned int
0x180089c41  lea     rcx, [rbp+57h+String1]; this
0x180089c45  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x180089c4a  or      r15d, 0FFFFFFFFh
0x180089c4e  mov     ecx, 18Bh
0x180089c53  cmp     eax, r15d
0x180089c56  jz      short loc_180089C85
0x180089c58  mov     [rbp+57h+var_9C], cx
0x180089c5c  lea     r8d, [rax+1]; unsigned int
0x180089c60  lea     rcx, [rbp+57h+String1]; this
0x180089c64  mov     [rbp+57h+var_A0], 0
0x180089c6b  lea     edx, [rdi+54h]; unsigned __int16
0x180089c6e  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x180089c73  mov     edi, eax
0x180089c75  mov     ecx, 18Eh
0x180089c7a  cmp     eax, r15d
0x180089c7d  jz      short loc_180089C85
0x180089c7f  mov     [rbp+57h+var_9C], cx
0x180089c83  jmp     short loc_180089CDC
0x180089c85  mov     edi, 80070003h
0x180089c8a  mov     [rbp+57h+var_9A], cx
0x180089c8e  mov     [rbp+57h+var_A0], edi
0x180089c91  jmp     loc_180089E3F
0x180089c96  mov     edi, 4
0x180089c9b  lea     rdx, asc_1800ECC50; "\\\\?\\"
0x180089ca2  mov     r8d, edi; MaxCount
0x180089ca5  mov     rcx, r14; String1
0x180089ca8  call    wcsncmp_0
0x180089cad  test    eax, eax
0x180089caf  jnz     loc_18008A1A2
0x180089cb5  lea     edx, [rdi+58h]; unsigned __int16
0x180089cb8  mov     r8d, edi; unsigned int
0x180089cbb  lea     rcx, [rbp+57h+String1]; this
0x180089cbf  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x180089cc4  or      r15d, 0FFFFFFFFh
0x180089cc8  mov     edi, eax
0x180089cca  cmp     eax, r15d
0x180089ccd  mov     eax, 194h
0x180089cd2  jz      loc_18008A198
0x180089cd8  mov     [rbp+57h+var_9C], ax
0x180089cdc  mov     [rbp+57h+var_A0], 0
0x180089ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180089cea  lea     rax, WPP_GLOBAL_Control
0x180089cf1  cmp     rcx, rax
0x180089cf4  jz      short loc_180089D14
0x180089cf6  test    byte ptr [rcx+1Ch], 2
0x180089cfa  jz      short loc_180089D14
0x180089cfc  mov     rcx, [rcx+10h]
0x180089d00  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180089d07  mov     edx, 14h
0x180089d0c  mov     r9, r14
0x180089d0f  call    WPP_SF_S
0x180089d14  mov     rdx, rsi; lpSecurityAttributes
0x180089d17  mov     rcx, r14; lpPathName
0x180089d1a  call    cs:__imp_CreateDirectoryW
0x180089d21  nop     dword ptr [rax+rax+00h]
0x180089d26  test    eax, eax
0x180089d28  jnz     loc_18008A15F
0x180089d2e  call    cs:__imp_GetLastError
0x180089d35  nop     dword ptr [rax+rax+00h]
0x180089d3a  cmp     eax, 40h ; '@'
0x180089d3d  jnz     short loc_180089D8D
0x180089d3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180089d46  lea     rax, WPP_GLOBAL_Control
0x180089d4d  cmp     rcx, rax
0x180089d50  jz      short loc_180089D73
0x180089d52  test    dword ptr [rcx+1Ch], 2000000h
0x180089d59  jz      short loc_180089D73
0x180089d5b  mov     rcx, [rcx+10h]
0x180089d5f  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180089d66  mov     edx, 15h
0x180089d6b  mov     r9, r14
0x180089d6e  call    WPP_SF_S
0x180089d73  mov     rdx, rsi; lpSecurityAttributes
0x180089d76  mov     rcx, r14; lpPathName
0x180089d79  call    cs:__imp_CreateDirectoryW
0x180089d80  nop     dword ptr [rax+rax+00h]
0x180089d85  test    eax, eax
0x180089d87  jnz     loc_18008A15F
0x180089d8d  call    cs:__imp_GetLastError
0x180089d94  nop     dword ptr [rax+rax+00h]
0x180089d99  cmp     eax, 0B7h
0x180089d9e  jnz     loc_180089EAB
0x180089da4  test    r12d, r12d
0x180089da7  jz      loc_180089E9B
0x180089dad  test    rsi, rsi
0x180089db0  jz      short loc_180089E2E
0x180089db2  mov     rdx, [rsi+8]; Src
0x180089db6  test    rdx, rdx
0x180089db9  jz      short loc_180089E2E
0x180089dbb  mov     eax, 1AAh
0x180089dc0  mov     [rbp+57h+var_A0], 0
0x180089dc7  lea     rcx, [rbp+57h+pOwner]; pOwner
0x180089dcb  mov     [rbp+57h+var_9C], ax
0x180089dcf  call    ?Initialize@CSdSecurityDescriptorInfo@@QEAAJPEAX@Z; CSdSecurityDescriptorInfo::Initialize(void *)
0x180089dd4  mov     edi, eax
0x180089dd6  mov     [rbp+57h+var_A0], eax
0x180089dd9  test    eax, eax
0x180089ddb  mov     eax, 1ABh
0x180089de0  js      short loc_180089E3B
0x180089de2  mov     r8, [rbp+57h+pDacl]; pDacl
0x180089de6  mov     rcx, r14; lpFileName
0x180089de9  mov     rdx, [rbp+57h+pOwner]; psidOwner
0x180089ded  mov     [rbp+57h+var_9C], ax
0x180089df1  call    ?SetSecurityInfo@@YAJPEBGQEAXQEAU_ACL@@@Z; SetSecurityInfo(ushort const *,void * const,_ACL * const)
0x180089df6  mov     edi, eax
0x180089df8  mov     [rbp+57h+var_A0], eax
0x180089dfb  test    eax, eax
0x180089dfd  mov     eax, 1ACh
0x180089e02  js      short loc_180089E3B
0x180089e04  cmp     [rbp+57h+arg_10], 0
0x180089e08  mov     [rbp+57h+var_9C], ax
0x180089e0c  jz      loc_180089E9B
0x180089e12  mov     rdx, [rsi+8]; pSecurityDescriptor
0x180089e16  mov     rcx, r14; pObjectName
0x180089e19  call    ?_PropagateInheritedAces@@YAJPEBGQEAX@Z; _PropagateInheritedAces(ushort const *,void * const)
0x180089e1e  mov     [rbp+57h+var_A0], eax
0x180089e21  mov     edi, eax
0x180089e23  test    eax, eax
0x180089e25  jns     short loc_180089E9B
0x180089e27  mov     eax, 1B1h
0x180089e2c  jmp     short loc_180089E3B
0x180089e2e  mov     eax, 1AAh
0x180089e33  mov     edi, 80070057h
0x180089e38  mov     [rbp+57h+var_A0], edi
0x180089e3b  mov     [rbp+57h+var_9A], ax
0x180089e3f  lea     rcx, [rbp+57h+pOwner]; this
0x180089e43  call    ??1CSdSecurityDescriptorInfo@@QEAA@XZ; CSdSecurityDescriptorInfo::~CSdSecurityDescriptorInfo(void)
0x180089e48  lea     rcx, [rbx-1]
0x180089e4c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180089e50  ja      short loc_180089E61
0x180089e52  mov     rcx, rbx; hObject
0x180089e55  call    cs:__imp_CloseHandle
0x180089e5c  nop     dword ptr [rax+rax+00h]
0x180089e61  lea     rcx, [rbp+57h+lpPathName]; this
0x180089e65  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180089e6a  lea     rcx, [rbp+57h+String1]; this
0x180089e6e  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180089e73  lea     rcx, [rbp+57h+var_A0]; this
0x180089e77  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180089e7c  lea     r11, [rsp+0E0h+var_20]
0x180089e84  mov     eax, edi
0x180089e86  mov     rbx, [r11+38h]
0x180089e8a  mov     rsi, [r11+48h]
0x180089e8e  mov     rsp, r11
0x180089e91  pop     r15
0x180089e93  pop     r14
0x180089e95  pop     r12
0x180089e97  pop     rdi
0x180089e98  pop     rbp
0x180089e99  retn
0x180089e9b  mov     eax, 1B5h
0x180089ea0  xor     edi, edi
0x180089ea2  mov     [rbp+57h+var_9C], ax
0x180089ea6  mov     [rbp+57h+var_A0], edi
0x180089ea9  jmp     short loc_180089E3F
0x180089eab  mov     rax, cs:WPP_GLOBAL_Control
0x180089eb2  lea     rcx, WPP_GLOBAL_Control
0x180089eb9  cmp     rax, rcx
0x180089ebc  jz      short loc_180089EF6
0x180089ebe  test    dword ptr [rax+1Ch], 10000000h
0x180089ec5  jz      short loc_180089EF6
0x180089ec7  call    cs:__imp_GetLastError
0x180089ece  nop     dword ptr [rax+rax+00h]
0x180089ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180089eda  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180089ee1  mov     edx, 16h
0x180089ee6  mov     [rsp+0E0h+dwCreationDisposition], eax
0x180089eea  mov     r9, r14
0x180089eed  mov     rcx, [rcx+10h]
0x180089ef1  call    WPP_SF_Sd
0x180089ef6  lea     r8d, [rdi+1]; unsigned int
0x180089efa  mov     edx, 5Ch ; '\'; unsigned __int16
0x180089eff  lea     rcx, [rbp+57h+String1]; this
0x180089f03  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x180089f08  cmp     eax, r15d
0x180089f0b  mov     ebx, eax
0x180089f0d  mov     [rbp+57h+arg_0], eax
0x180089f10  jz      loc_18008A0BC
0x180089f16  mov     r8d, eax; unsigned int
0x180089f19  lea     rcx, [rbp+57h+lpPathName]; this
0x180089f1d  mov     rdx, r14; unsigned __int16 *
0x180089f20  mov     r15d, 1C9h
0x180089f26  call    ?Set@CBsString@@QEAAJPEBGK@Z; CBsString::Set(ushort const *,ulong)
0x180089f2b  mov     [rbp+57h+var_A0], eax
0x180089f2e  mov     edi, eax
0x180089f30  test    eax, eax
0x180089f32  js      loc_18008A0AE
0x180089f38  mov     [rbp+57h+var_9C], r15w
0x180089f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180089f44  lea     rax, WPP_GLOBAL_Control
0x180089f4b  mov     r12, [rbp+57h+lpPathName]
0x180089f4f  cmp     rcx, rax
0x180089f52  jz      short loc_180089F72
0x180089f54  test    byte ptr [rcx+1Ch], 2
0x180089f58  jz      short loc_180089F72
0x180089f5a  mov     rcx, [rcx+10h]
0x180089f5e  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180089f65  mov     edx, 17h
0x180089f6a  mov     r9, r12
0x180089f6d  call    WPP_SF_S
0x180089f72  mov     rdx, rsi; lpSecurityAttributes
0x180089f75  mov     rcx, r12; lpPathName
0x180089f78  call    cs:__imp_CreateDirectoryW
0x180089f7f  nop     dword ptr [rax+rax+00h]
0x180089f84  mov     r15d, eax
0x180089f87  test    eax, eax
0x180089f89  jnz     short loc_18008A003
0x180089f8b  call    cs:__imp_GetLastError
0x180089f92  nop     dword ptr [rax+rax+00h]
0x180089f97  mov     edi, eax
0x180089f99  cmp     eax, 0B7h
0x180089f9e  jz      short loc_18008A003
0x180089fa0  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x180089fa9  lea     r8d, [r15+7]; dwShareMode
0x180089fad  mov     [rsp+0E0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180089fb5  xor     r9d, r9d; lpSecurityAttributes
0x180089fb8  mov     edx, 100000h; dwDesiredAccess
0x180089fbd  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180089fc5  mov     rcx, r12; lpFileName
0x180089fc8  call    cs:__imp_CreateFileW
0x180089fcf  nop     dword ptr [rax+rax+00h]
0x180089fd4  mov     rbx, rax
0x180089fd7  dec     rax
0x180089fda  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180089fde  ja      loc_18008A097
0x180089fe4  mov     eax, 1DCh
  ... truncated ...
```
