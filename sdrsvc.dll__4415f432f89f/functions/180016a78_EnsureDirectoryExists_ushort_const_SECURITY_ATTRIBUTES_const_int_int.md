# EnsureDirectoryExists(ushort const *,_SECURITY_ATTRIBUTES const *,int,int)

- ea: `0x180016a78`
- end: `0x180016f60`
- name: `?EnsureDirectoryExists@@YAJPEBGPEBU_SECURITY_ATTRIBUTES@@HH@Z`
- size: `1256`
- prototype: `__int64 __fastcall(unsigned __int16 *, const struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800148dc`

## callees

- `0x18000eabc`
- `0x180014f70`
- `0x18001507c`
- `0x18001586c`
- `0x180015974`
- `0x180016a78`
- `0x180017604`
- `0x18001c58c`
- `0x18001f4d4`
- `0x18001f624`
- `0x18001f674`
- `0x18001f8ac`
- `0x18001fe04`
- `0x180020488`
- `0x180021716`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016f29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016f29`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016dd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180016dd5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016c53`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016c9c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016d91`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016e9b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016c53`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016c9c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016d91`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180016e9b`

## string_xrefs

- `0x180016a94`: `EnsureDirectoryExists`
- `0x180016e2d`: `Created`
- `0x180016e23`: `Already existed`

## pseudocode

```c
__int64 __fastcall EnsureDirectoryExists(unsigned __int16 *a1, const struct _SECURITY_ATTRIBUTES *a2)
{
  LPCWSTR v3; // r12
  __int64 FileW; // rbx
  __int16 v5; // ax
  unsigned __int64 v6; // rax
  bool v7; // cf
  unsigned __int16 v8; // dx
  int LastFailureAsHRESULT; // edi
  const wchar_t *v10; // rsi
  unsigned __int16 v11; // dx
  int v12; // eax
  unsigned __int16 v13; // dx
  __int16 v14; // cx
  int v15; // edi
  unsigned __int16 v16; // dx
  unsigned __int16 v17; // dx
  __int16 v18; // ax
  char LastError; // al
  unsigned int v20; // r15d
  unsigned __int16 v21; // dx
  BOOL DirectoryW; // r13d
  const char *v23; // r9
  __int64 v24; // rcx
  int v26; // [rsp+40h] [rbp-69h] BYREF
  __int16 v27; // [rsp+44h] [rbp-65h]
  __int16 v28; // [rsp+46h] [rbp-63h]
  wchar_t *String1[2]; // [rsp+78h] [rbp-31h] BYREF
  LPCWSTR lpPathName; // [rsp+88h] [rbp-21h] BYREF
  __int64 v31; // [rsp+90h] [rbp-19h]
  __int64 v32; // [rsp+98h] [rbp-11h] BYREF
  int v33; // [rsp+A0h] [rbp-9h]
  __int64 v34; // [rsp+A8h] [rbp-1h]
  __int64 v35; // [rsp+B0h] [rbp+7h]
  __int64 v36; // [rsp+B8h] [rbp+Fh]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v26, "EnsureDirectoryExists", 372, 1);
  v3 = (LPCWSTR)qword_180028260;
  String1[0] = (wchar_t *)qword_180028260;
  String1[1] = 0;
  FileW = -1;
  lpPathName = (LPCWSTR)qword_180028260;
  v5 = 381;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  if ( !a1 )
  {
    LastFailureAsHRESULT = -2147024809;
    goto LABEL_62;
  }
  v27 = 381;
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  v7 = v6 < 3;
  v5 = 383;
  if ( v7 )
    goto LABEL_59;
  v26 = 0;
  v27 = 383;
  LastFailureAsHRESULT = CBsString::Append((CBsString *)String1, a1);
  v26 = LastFailureAsHRESULT;
  v5 = 386;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_63;
  v27 = 386;
  CBsString::UnTrailing((CBsString *)String1, v8);
  LastFailureAsHRESULT = CBsString::AntiCanonicalize((CBsString *)String1);
  v26 = LastFailureAsHRESULT;
  v5 = 389;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_63;
  v10 = String1[0];
  v27 = 389;
  if ( !wcsncmp_0(String1[0], L"\\\\?\\UNC\\", 8u) )
  {
    v12 = CBsString::Find((CBsString *)String1, v11, 8u);
    v14 = 395;
    if ( v12 == -1
      || (v27 = 395, v26 = 0, v15 = CBsString::Find((CBsString *)String1, v13, v12 + 1), v14 = 398, v15 == -1) )
    {
      LastFailureAsHRESULT = -2147024893;
      v28 = v14;
      v26 = -2147024893;
      goto LABEL_64;
    }
    v27 = 398;
    goto LABEL_15;
  }
  if ( wcsncmp_0(v10, L"\\\\?\\", 4u) )
  {
    LastFailureAsHRESULT = -2147024893;
    v5 = 408;
    goto LABEL_62;
  }
  v15 = CBsString::Find((CBsString *)String1, v16, 4u);
  v5 = 404;
  if ( v15 == -1 )
  {
LABEL_59:
    LastFailureAsHRESULT = -2147024893;
    goto LABEL_62;
  }
  v27 = 404;
LABEL_15:
  v26 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids, v10);
  if ( CreateDirectoryW(v10, 0) )
    goto LABEL_58;
  if ( GetLastError() == 64 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids, v10);
    if ( CreateDirectoryW(v10, 0) )
    {
LABEL_58:
      v18 = 448;
      goto LABEL_26;
    }
  }
  if ( GetLastError() == 183 )
  {
    v18 = 437;
LABEL_26:
    v26 = 0;
    LastFailureAsHRESULT = 0;
    v27 = v18;
    goto LABEL_64;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)WPP_df8cd073d3d8361ada3b590c76323716_Traceguids,
      (_DWORD)v10,
      LastError);
  }
  v20 = CBsString::Find((CBsString *)String1, v17, v15 + 1);
  if ( v20 == -1 )
  {
LABEL_47:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids, v10);
    if ( !CreateDirectoryW(v10, 0) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v24);
      v26 = LastFailureAsHRESULT;
      v5 = 495;
      FileW = -1;
      goto LABEL_63;
    }
    v26 = 0;
    v27 = 495;
    LastFailureAsHRESULT = 0;
LABEL_56:
    FileW = -1;
    goto LABEL_64;
  }
  while ( 1 )
  {
    if ( (_DWORD)v31 )
    {
      LODWORD(v31) = 0;
      *v3 = 0;
    }
    v26 = CBsString::Append((CBsString *)&lpPathName, v10, v20);
    LastFailureAsHRESULT = v26;
    if ( v26 < 0 )
    {
      v28 = 457;
      goto LABEL_56;
    }
    v27 = 457;
    v3 = lpPathName;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids, lpPathName);
    DirectoryW = CreateDirectoryW(v3, 0);
    if ( !DirectoryW )
    {
      LastFailureAsHRESULT = GetLastError();
      if ( LastFailureAsHRESULT != 183 )
        break;
    }
LABEL_41:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v23 = "Created";
      if ( !DirectoryW )
        v23 = "Already existed";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids, v23);
    }
    v20 = CBsString::Find((CBsString *)String1, v21, v20 + 1);
    if ( v20 == -1 )
      goto LABEL_47;
  }
  FileW = (__int64)CreateFileW(v3, 0x100000u, 7u, 0, 3u, 0x2000000u, 0);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v26 = 0;
    v27 = 476;
    CloseHandle((HANDLE)FileW);
    goto LABEL_41;
  }
  if ( LastFailureAsHRESULT > 0 )
    LastFailureAsHRESULT = (unsigned __int16)LastFailureAsHRESULT | 0x80070000;
  v5 = 476;
LABEL_62:
  v26 = LastFailureAsHRESULT;
LABEL_63:
  v28 = v5;
LABEL_64:
  CSdSecurityDescriptorInfo::~CSdSecurityDescriptorInfo((CSdSecurityDescriptorInfo *)&v32);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  CBsString::_Release((LPVOID *)&lpPathName);
  CBsString::_Release((LPVOID *)String1);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v26);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180016a78  push    rbp
0x180016a7a  push    rbx
0x180016a7b  push    rsi
0x180016a7c  push    rdi
0x180016a7d  push    r12
0x180016a7f  push    r13
0x180016a81  push    r14
0x180016a83  push    r15
0x180016a85  lea     rbp, [rsp-1Fh]
0x180016a8a  sub     rsp, 0C8h
0x180016a91  mov     rdi, rcx
0x180016a94  lea     rdx, aEnsuredirector; "EnsureDirectoryExists"
0x180016a9b  lea     rcx, [rbp+57h+var_C0]; this
0x180016a9f  mov     r9d, 1; unsigned __int16
0x180016aa5  mov     r8d, 174h; unsigned __int16
0x180016aab  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180016ab0  xor     r13d, r13d
0x180016ab3  lea     r12, qword_180028260
0x180016aba  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180016abe  mov     [rbp+57h+String1], r12
0x180016ac2  mov     [rbp+57h+var_80], r13
0x180016ac6  mov     rbx, rcx
0x180016ac9  mov     [rbp+57h+lpPathName], r12
0x180016acd  mov     eax, 17Dh
0x180016ad2  mov     [rbp+57h+var_70], r13
0x180016ad6  mov     [rbp+57h+var_68], r13
0x180016ada  mov     [rbp+57h+var_60], r13d
0x180016ade  mov     [rbp+57h+var_58], r13
0x180016ae2  mov     [rbp+57h+var_50], r13
0x180016ae6  mov     [rbp+57h+var_48], r13
0x180016aea  test    rdi, rdi
0x180016aed  jz      loc_180016F07
0x180016af3  mov     [rbp+57h+var_BC], ax
0x180016af7  mov     rax, rcx
0x180016afa  inc     rax
0x180016afd  cmp     [rdi+rax*2], r13w
0x180016b02  jnz     short loc_180016AFA
0x180016b04  cmp     rax, 3
0x180016b08  mov     eax, 17Fh
0x180016b0d  jb      loc_180016EF4
0x180016b13  mov     [rbp+57h+var_C0], r13d
0x180016b17  mov     [rbp+57h+var_BC], ax
0x180016b1b  mov     rdx, rdi; unsigned __int16 *
0x180016b1e  lea     rcx, [rbp+57h+String1]; this
0x180016b22  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180016b27  mov     edi, eax
0x180016b29  mov     [rbp+57h+var_C0], eax
0x180016b2c  test    eax, eax
0x180016b2e  mov     eax, 182h
0x180016b33  js      loc_180016F0F
0x180016b39  lea     rcx, [rbp+57h+String1]; this
0x180016b3d  mov     [rbp+57h+var_BC], ax
0x180016b41  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x180016b46  lea     rcx, [rbp+57h+String1]; this
0x180016b4a  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x180016b4f  mov     edi, eax
0x180016b51  mov     [rbp+57h+var_C0], eax
0x180016b54  test    eax, eax
0x180016b56  mov     eax, 185h
0x180016b5b  js      loc_180016F0F
0x180016b61  mov     rsi, [rbp+57h+String1]
0x180016b65  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x180016b6c  mov     edi, 8
0x180016b71  mov     [rbp+57h+var_BC], ax
0x180016b75  mov     r8d, edi; MaxCount
0x180016b78  mov     rcx, rsi; String1
0x180016b7b  call    wcsncmp_0
0x180016b80  test    eax, eax
0x180016b82  jnz     short loc_180016BD6
0x180016b84  mov     r8d, edi; unsigned int
0x180016b87  lea     rcx, [rbp+57h+String1]; this
0x180016b8b  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x180016b90  or      r14d, 0FFFFFFFFh
0x180016b94  mov     ecx, 18Bh
0x180016b99  cmp     eax, r14d
0x180016b9c  jz      short loc_180016BC5
0x180016b9e  mov     [rbp+57h+var_BC], cx
0x180016ba2  lea     r8d, [rax+1]; unsigned int
0x180016ba6  lea     rcx, [rbp+57h+String1]; this
0x180016baa  mov     [rbp+57h+var_C0], r13d
0x180016bae  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x180016bb3  mov     edi, eax
0x180016bb5  mov     ecx, 18Eh
0x180016bba  cmp     eax, r14d
0x180016bbd  jz      short loc_180016BC5
0x180016bbf  mov     [rbp+57h+var_BC], cx
0x180016bc3  jmp     short loc_180016C19
0x180016bc5  mov     edi, 80070003h
0x180016bca  mov     [rbp+57h+var_BA], cx
0x180016bce  mov     [rbp+57h+var_C0], edi
0x180016bd1  jmp     loc_180016F13
0x180016bd6  mov     edi, 4
0x180016bdb  lea     rdx, asc_180027700; "\\\\?\\"
0x180016be2  mov     r8d, edi; MaxCount
0x180016be5  mov     rcx, rsi; String1
0x180016be8  call    wcsncmp_0
0x180016bed  test    eax, eax
0x180016bef  jnz     loc_180016EFB
0x180016bf5  mov     r8d, edi; unsigned int
0x180016bf8  lea     rcx, [rbp+57h+String1]; this
0x180016bfc  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x180016c01  or      r14d, 0FFFFFFFFh
0x180016c05  mov     edi, eax
0x180016c07  cmp     eax, r14d
0x180016c0a  mov     eax, 194h
0x180016c0f  jz      loc_180016EF4
0x180016c15  mov     [rbp+57h+var_BC], ax
0x180016c19  mov     [rbp+57h+var_C0], r13d
0x180016c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c24  lea     r15, WPP_GLOBAL_Control
0x180016c2b  cmp     rcx, r15
0x180016c2e  jz      short loc_180016C4E
0x180016c30  test    byte ptr [rcx+1Ch], 2
0x180016c34  jz      short loc_180016C4E
0x180016c36  mov     rcx, [rcx+10h]
0x180016c3a  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180016c41  mov     edx, 14h
0x180016c46  mov     r9, rsi
0x180016c49  call    WPP_SF_S
0x180016c4e  xor     edx, edx; lpSecurityAttributes
0x180016c50  mov     rcx, rsi; lpPathName
0x180016c53  call    cs:__imp_CreateDirectoryW
0x180016c59  test    eax, eax
0x180016c5b  jnz     loc_180016EEA
0x180016c61  call    cs:__imp_GetLastError
0x180016c67  cmp     eax, 40h ; '@'
0x180016c6a  jnz     short loc_180016CAA
0x180016c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c73  cmp     rcx, r15
0x180016c76  jz      short loc_180016C97
0x180016c78  test    dword ptr [rcx+1Ch], 2000000h
0x180016c7f  jz      short loc_180016C97
0x180016c81  mov     rcx, [rcx+10h]
0x180016c85  lea     edx, [rax-2Bh]
0x180016c88  mov     r9, rsi
0x180016c8b  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180016c92  call    WPP_SF_S
0x180016c97  xor     edx, edx; lpSecurityAttributes
0x180016c99  mov     rcx, rsi; lpPathName
0x180016c9c  call    cs:__imp_CreateDirectoryW
0x180016ca2  test    eax, eax
0x180016ca4  jnz     loc_180016EEA
0x180016caa  call    cs:__imp_GetLastError
0x180016cb0  cmp     eax, 0B7h
0x180016cb5  jnz     short loc_180016CCC
0x180016cb7  mov     eax, 1B5h
0x180016cbc  mov     [rbp+57h+var_C0], r13d
0x180016cc0  mov     edi, r13d
0x180016cc3  mov     [rbp+57h+var_BC], ax
0x180016cc7  jmp     loc_180016F13
0x180016ccc  mov     rax, cs:WPP_GLOBAL_Control
0x180016cd3  cmp     rax, r15
0x180016cd6  jz      short loc_180016D0A
0x180016cd8  test    dword ptr [rax+1Ch], 10000000h
0x180016cdf  jz      short loc_180016D0A
0x180016ce1  call    cs:__imp_GetLastError
0x180016ce7  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cee  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180016cf5  mov     edx, 16h
0x180016cfa  mov     [rsp+100h+dwCreationDisposition], eax
0x180016cfe  mov     r9, rsi
0x180016d01  mov     rcx, [rcx+10h]
0x180016d05  call    WPP_SF_Sd
0x180016d0a  lea     r8d, [rdi+1]; unsigned int
0x180016d0e  lea     rcx, [rbp+57h+String1]; this
0x180016d12  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x180016d17  mov     r15d, eax
0x180016d1a  cmp     eax, r14d
0x180016d1d  jz      loc_180016E65
0x180016d23  mov     ebx, 1C9h
0x180016d28  cmp     dword ptr [rbp+57h+var_70], r13d
0x180016d2c  jz      short loc_180016D37
0x180016d2e  mov     dword ptr [rbp+57h+var_70], r13d
0x180016d32  mov     [r12], r13w
0x180016d37  mov     r8d, r15d; unsigned int
0x180016d3a  lea     rcx, [rbp+57h+lpPathName]; this
0x180016d3e  mov     rdx, rsi; unsigned __int16 *
0x180016d41  call    ?Append@CBsString@@QEAAJPEBGK@Z; CBsString::Append(ushort const *,ulong)
0x180016d46  mov     [rbp+57h+var_C0], eax
0x180016d49  mov     edi, eax
0x180016d4b  test    eax, eax
0x180016d4d  js      loc_180016ECE
0x180016d53  mov     [rbp+57h+var_BC], bx
0x180016d57  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d5e  lea     rax, WPP_GLOBAL_Control
0x180016d65  mov     r12, [rbp+57h+lpPathName]
0x180016d69  cmp     rcx, rax
0x180016d6c  jz      short loc_180016D8C
0x180016d6e  test    byte ptr [rcx+1Ch], 2
0x180016d72  jz      short loc_180016D8C
0x180016d74  mov     rcx, [rcx+10h]
0x180016d78  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180016d7f  mov     edx, 17h
0x180016d84  mov     r9, r12
0x180016d87  call    WPP_SF_S
0x180016d8c  xor     edx, edx; lpSecurityAttributes
0x180016d8e  mov     rcx, r12; lpPathName
0x180016d91  call    cs:__imp_CreateDirectoryW
0x180016d97  mov     r13d, eax
0x180016d9a  test    eax, eax
0x180016d9c  jnz     short loc_180016E06
0x180016d9e  call    cs:__imp_GetLastError
0x180016da4  mov     edi, eax
0x180016da6  cmp     eax, 0B7h
0x180016dab  jz      short loc_180016E06
0x180016dad  mov     [rsp+100h+hTemplateFile], 0; hTemplateFile
0x180016db6  lea     r8d, [r13+7]; dwShareMode
0x180016dba  mov     [rsp+100h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180016dc2  xor     r9d, r9d; lpSecurityAttributes
0x180016dc5  mov     edx, 100000h; dwDesiredAccess
0x180016dca  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x180016dd2  mov     rcx, r12; lpFileName
0x180016dd5  call    cs:__imp_CreateFileW
0x180016ddb  mov     rbx, rax
0x180016dde  dec     rax
0x180016de1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180016de5  ja      loc_180016EBA
0x180016deb  mov     eax, 1DCh
0x180016df0  mov     [rbp+57h+var_C0], r13d
0x180016df4  mov     rcx, rbx; hObject
0x180016df7  mov     [rbp+57h+var_BC], ax
0x180016dfb  call    cs:__imp_CloseHandle
0x180016e01  mov     ebx, 1C9h
0x180016e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e0d  lea     rax, WPP_GLOBAL_Control
0x180016e14  cmp     rcx, rax
0x180016e17  jz      short loc_180016E49
0x180016e19  test    byte ptr [rcx+1Ch], 2
0x180016e1d  jz      short loc_180016E49
0x180016e1f  mov     rcx, [rcx+10h]
0x180016e23  lea     rax, aAlreadyExisted; "Already existed"
0x180016e2a  test    r13d, r13d
0x180016e2d  lea     r9, aCreated; "Created"
0x180016e34  mov     edx, 18h
0x180016e39  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180016e40  cmovz   r9, rax
0x180016e44  call    WPP_SF_s
0x180016e49  lea     r8d, [r15+1]; unsigned int
0x180016e4d  lea     rcx, [rbp+57h+String1]; this
0x180016e51  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x180016e56  xor     r13d, r13d
0x180016e59  mov     r15d, eax
0x180016e5c  cmp     eax, r14d
0x180016e5f  jnz     loc_180016D28
0x180016e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e6c  lea     rax, WPP_GLOBAL_Control
0x180016e73  cmp     rcx, rax
0x180016e76  jz      short loc_180016E96
0x180016e78  test    byte ptr [rcx+1Ch], 2
0x180016e7c  jz      short loc_180016E96
0x180016e7e  mov     rcx, [rcx+10h]
0x180016e82  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180016e89  mov     edx, 19h
0x180016e8e  mov     r9, rsi
0x180016e91  call    WPP_SF_S
0x180016e96  xor     edx, edx; lpSecurityAttributes
0x180016e98  mov     rcx, rsi; lpPathName
0x180016e9b  call    cs:__imp_CreateDirectoryW
0x180016ea1  test    eax, eax
0x180016ea3  jnz     short loc_180016ED8
0x180016ea5  call    GetLastFailureAsHRESULT
0x180016eaa  mov     edi, eax
0x180016eac  mov     [rbp+57h+var_C0], eax
0x180016eaf  mov     eax, 1EFh
0x180016eb4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016eb8  jmp     short loc_180016F0F
0x180016eba  test    edi, edi
0x180016ebc  jle     short loc_180016EC7
0x180016ebe  movzx   edi, di
0x180016ec1  or      edi, 80070000h
0x180016ec7  mov     eax, 1DCh
0x180016ecc  jmp     short loc_180016F0C
0x180016ece  mov     [rbp+57h+var_BA], bx
0x180016ed2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016ed6  jmp     short loc_180016F13
0x180016ed8  mov     eax, 1EFh
0x180016edd  mov     [rbp+57h+var_C0], r13d
0x180016ee1  mov     [rbp+57h+var_BC], ax
0x180016ee5  mov     edi, r13d
0x180016ee8  jmp     short loc_180016ED2
0x180016eea  mov     eax, 1C0h
0x180016eef  jmp     loc_180016CBC
0x180016ef4  mov     edi, 80070003h
0x180016ef9  jmp     short loc_180016F0C
0x180016efb  mov     edi, 80070003h
0x180016f00  mov     eax, 198h
0x180016f05  jmp     short loc_180016F0C
0x180016f07  mov     edi, 80070057h
0x180016f0c  mov     [rbp+57h+var_C0], edi
0x180016f0f  mov     [rbp+57h+var_BA], ax
0x180016f13  lea     rcx, [rbp+57h+var_68]; this
0x180016f17  call    ??1CSdSecurityDescriptorInfo@@QEAA@XZ; CSdSecurityDescriptorInfo::~CSdSecurityDescriptorInfo(void)
0x180016f1c  lea     rcx, [rbx-1]
0x180016f20  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180016f24  ja      short loc_180016F2F
0x180016f26  mov     rcx, rbx; hObject
0x180016f29  call    cs:__imp_CloseHandle
0x180016f2f  lea     rcx, [rbp+57h+lpPathName]; this
0x180016f33  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180016f38  lea     rcx, [rbp+57h+String1]; this
  ... truncated ...
```
