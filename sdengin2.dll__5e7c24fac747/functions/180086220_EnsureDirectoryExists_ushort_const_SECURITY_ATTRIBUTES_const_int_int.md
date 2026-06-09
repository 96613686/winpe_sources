# EnsureDirectoryExists(ushort const *,_SECURITY_ATTRIBUTES const *,int,int)

- ea: `0x180086220`
- end: `0x18008686e`
- name: `?EnsureDirectoryExists@@YAJPEBGPEBU_SECURITY_ATTRIBUTES@@HH@Z`
- size: `1614`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPSECURITY_ATTRIBUTES lpSecurityAttributes, int, int)`
- caller_count: `8`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001b0fc`
- `0x180029e88`
- `0x1800361a0`
- `0x180036d10`
- `0x1800370d8`
- `0x18004d448`
- `0x1800b4064`
- `0x1800b512c`

## callees

- `0x180008240`
- `0x180008458`
- `0x180014394`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180086220`
- `0x1800870e8`
- `0x180088e40`
- `0x1800897e0`
- `0x180089ab4`
- `0x18008f5d0`
- `0x180099484`
- `0x180099d1c`
- `0x18009a24c`
- `0x18009a26c`
- `0x18009a608`
- `0x18009ae34`
- `0x1800c97fe`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180086697`
- `KERNEL32!CreateFileW` at `0x180086697`
- `KERNEL32!GetLastError` at `0x180086428`
- `KERNEL32!GetLastError` at `0x18008647b`
- `KERNEL32!GetLastError` at `0x1800865a8`
- `KERNEL32!GetLastError` at `0x180086660`
- `KERNEL32!GetLastError` at `0x180086428`
- `KERNEL32!GetLastError` at `0x18008647b`
- `KERNEL32!GetLastError` at `0x1800865a8`
- `KERNEL32!GetLastError` at `0x180086660`
- `KERNEL32!CloseHandle` at `0x18008653d`
- `KERNEL32!CloseHandle` at `0x1800866bd`
- `KERNEL32!CloseHandle` at `0x18008653d`
- `KERNEL32!CloseHandle` at `0x1800866bd`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008641a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008646d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180086653`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800867b6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008641a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18008646d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180086653`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800867b6`

## string_xrefs

- `0x18008624b`: `EnsureDirectoryExists`
- `0x1800866ed`: `Created`
- `0x1800866e3`: `Already existed`

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
  String1[0] = (wchar_t *)qword_1800E8530;
  lpPathName[0] = (LPCWSTR)qword_1800E8530;
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
0x180086220  mov     rax, rsp
0x180086223  mov     [rax+10h], rbx
0x180086227  mov     [rax+20h], rsi
0x18008622b  mov     [rax+18h], r8d
0x18008622f  push    rbp
0x180086230  push    rdi
0x180086231  push    r12
0x180086233  push    r14
0x180086235  push    r15
0x180086237  lea     rbp, [rax-5Fh]
0x18008623b  sub     rsp, 0C0h
0x180086242  mov     r12d, r9d
0x180086245  mov     rsi, rdx
0x180086248  mov     rdi, rcx
0x18008624b  lea     rdx, aEnsuredirector_0; "EnsureDirectoryExists"
0x180086252  mov     r9d, 1; unsigned __int16
0x180086258  lea     rcx, [rbp+57h+var_A0]; this
0x18008625c  mov     r8d, 174h; unsigned __int16
0x180086262  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180086267  xor     r15d, r15d
0x18008626a  lea     rax, qword_1800E8530
0x180086271  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180086275  mov     [rbp+57h+String1], rax
0x180086279  mov     [rbp+57h+lpPathName], rax
0x18008627d  mov     eax, 17Dh
0x180086282  mov     [rbp+57h+var_60], r15
0x180086286  mov     rbx, rcx
0x180086289  mov     [rbp+57h+var_50], r15
0x18008628d  mov     [rbp+57h+pOwner], r15
0x180086291  mov     [rbp+57h+var_40], r15d
0x180086295  mov     [rbp+57h+pDacl], r15
0x180086299  mov     [rbp+57h+var_30], r15
0x18008629d  mov     [rbp+57h+var_28], r15
0x1800862a1  test    rdi, rdi
0x1800862a4  jz      loc_18008651B
0x1800862aa  mov     [rbp+57h+var_9C], ax
0x1800862ae  mov     rax, rcx
0x1800862b1  inc     rax
0x1800862b4  cmp     [rdi+rax*2], r15w
0x1800862b9  jnz     short loc_1800862B1
0x1800862bb  cmp     rax, 3
0x1800862bf  mov     eax, 17Fh
0x1800862c4  jb      loc_180086855
0x1800862ca  mov     rdx, rdi; unsigned __int16 *
0x1800862cd  mov     [rbp+57h+var_A0], r15d
0x1800862d1  lea     rcx, [rbp+57h+String1]; this
0x1800862d5  mov     [rbp+57h+var_9C], ax
0x1800862d9  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x1800862de  mov     edi, eax
0x1800862e0  mov     [rbp+57h+var_A0], eax
0x1800862e3  test    eax, eax
0x1800862e5  mov     eax, 182h
0x1800862ea  js      loc_180086523
0x1800862f0  lea     rcx, [rbp+57h+String1]; this
0x1800862f4  mov     [rbp+57h+var_9C], ax
0x1800862f8  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x1800862fd  lea     rcx, [rbp+57h+String1]; this
0x180086301  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x180086306  mov     edi, eax
0x180086308  mov     [rbp+57h+var_A0], eax
0x18008630b  test    eax, eax
0x18008630d  mov     eax, 185h
0x180086312  js      loc_180086523
0x180086318  mov     r14, [rbp+57h+String1]
0x18008631c  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x180086323  mov     edi, 8
0x180086328  mov     [rbp+57h+var_9C], ax
0x18008632c  mov     r8d, edi; MaxCount
0x18008632f  mov     rcx, r14; String1
0x180086332  call    wcsncmp_0
0x180086337  test    eax, eax
0x180086339  jnz     short loc_180086396
0x18008633b  lea     edx, [rdi+54h]; unsigned __int16
0x18008633e  mov     r8d, edi; unsigned int
0x180086341  lea     rcx, [rbp+57h+String1]; this
0x180086345  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x18008634a  or      r15d, 0FFFFFFFFh
0x18008634e  mov     ecx, 18Bh
0x180086353  cmp     eax, r15d
0x180086356  jz      short loc_180086385
0x180086358  mov     [rbp+57h+var_9C], cx
0x18008635c  lea     r8d, [rax+1]; unsigned int
0x180086360  lea     rcx, [rbp+57h+String1]; this
0x180086364  mov     [rbp+57h+var_A0], 0
0x18008636b  lea     edx, [rdi+54h]; unsigned __int16
0x18008636e  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x180086373  mov     edi, eax
0x180086375  mov     ecx, 18Eh
0x18008637a  cmp     eax, r15d
0x18008637d  jz      short loc_180086385
0x18008637f  mov     [rbp+57h+var_9C], cx
0x180086383  jmp     short loc_1800863DC
0x180086385  mov     edi, 80070003h
0x18008638a  mov     [rbp+57h+var_9A], cx
0x18008638e  mov     [rbp+57h+var_A0], edi
0x180086391  jmp     loc_180086527
0x180086396  mov     edi, 4
0x18008639b  lea     rdx, asc_1800E6C70; "\\\\?\\"
0x1800863a2  mov     r8d, edi; MaxCount
0x1800863a5  mov     rcx, r14; String1
0x1800863a8  call    wcsncmp_0
0x1800863ad  test    eax, eax
0x1800863af  jnz     loc_18008685F
0x1800863b5  lea     edx, [rdi+58h]; unsigned __int16
0x1800863b8  mov     r8d, edi; unsigned int
0x1800863bb  lea     rcx, [rbp+57h+String1]; this
0x1800863bf  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x1800863c4  or      r15d, 0FFFFFFFFh
0x1800863c8  mov     edi, eax
0x1800863ca  cmp     eax, r15d
0x1800863cd  mov     eax, 194h
0x1800863d2  jz      loc_180086855
0x1800863d8  mov     [rbp+57h+var_9C], ax
0x1800863dc  mov     [rbp+57h+var_A0], 0
0x1800863e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800863ea  lea     rax, WPP_GLOBAL_Control
0x1800863f1  cmp     rcx, rax
0x1800863f4  jz      short loc_180086414
0x1800863f6  test    byte ptr [rcx+1Ch], 2
0x1800863fa  jz      short loc_180086414
0x1800863fc  mov     rcx, [rcx+10h]
0x180086400  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180086407  mov     edx, 14h
0x18008640c  mov     r9, r14
0x18008640f  call    WPP_SF_S
0x180086414  mov     rdx, rsi; lpSecurityAttributes
0x180086417  mov     rcx, r14; lpPathName
0x18008641a  call    cs:__imp_CreateDirectoryW
0x180086420  test    eax, eax
0x180086422  jnz     loc_18008681C
0x180086428  call    cs:__imp_GetLastError
0x18008642e  cmp     eax, 40h ; '@'
0x180086431  jnz     short loc_18008647B
0x180086433  mov     rcx, cs:WPP_GLOBAL_Control
0x18008643a  lea     rax, WPP_GLOBAL_Control
0x180086441  cmp     rcx, rax
0x180086444  jz      short loc_180086467
0x180086446  test    dword ptr [rcx+1Ch], 2000000h
0x18008644d  jz      short loc_180086467
0x18008644f  mov     rcx, [rcx+10h]
0x180086453  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x18008645a  mov     edx, 15h
0x18008645f  mov     r9, r14
0x180086462  call    WPP_SF_S
0x180086467  mov     rdx, rsi; lpSecurityAttributes
0x18008646a  mov     rcx, r14; lpPathName
0x18008646d  call    cs:__imp_CreateDirectoryW
0x180086473  test    eax, eax
0x180086475  jnz     loc_18008681C
0x18008647b  call    cs:__imp_GetLastError
0x180086481  cmp     eax, 0B7h
0x180086486  jnz     loc_18008658C
0x18008648c  test    r12d, r12d
0x18008648f  jz      loc_18008657C
0x180086495  test    rsi, rsi
0x180086498  jz      short loc_180086516
0x18008649a  mov     rdx, [rsi+8]; Src
0x18008649e  test    rdx, rdx
0x1800864a1  jz      short loc_180086516
0x1800864a3  mov     eax, 1AAh
0x1800864a8  mov     [rbp+57h+var_A0], 0
0x1800864af  lea     rcx, [rbp+57h+pOwner]; pOwner
0x1800864b3  mov     [rbp+57h+var_9C], ax
0x1800864b7  call    ?Initialize@CSdSecurityDescriptorInfo@@QEAAJPEAX@Z; CSdSecurityDescriptorInfo::Initialize(void *)
0x1800864bc  mov     edi, eax
0x1800864be  mov     [rbp+57h+var_A0], eax
0x1800864c1  test    eax, eax
0x1800864c3  mov     eax, 1ABh
0x1800864c8  js      short loc_180086523
0x1800864ca  mov     r8, [rbp+57h+pDacl]; pDacl
0x1800864ce  mov     rcx, r14; lpFileName
0x1800864d1  mov     rdx, [rbp+57h+pOwner]; psidOwner
0x1800864d5  mov     [rbp+57h+var_9C], ax
0x1800864d9  call    ?SetSecurityInfo@@YAJPEBGQEAXQEAU_ACL@@@Z; SetSecurityInfo(ushort const *,void * const,_ACL * const)
0x1800864de  mov     edi, eax
0x1800864e0  mov     [rbp+57h+var_A0], eax
0x1800864e3  test    eax, eax
0x1800864e5  mov     eax, 1ACh
0x1800864ea  js      short loc_180086523
0x1800864ec  cmp     [rbp+57h+arg_10], 0
0x1800864f0  mov     [rbp+57h+var_9C], ax
0x1800864f4  jz      loc_18008657C
0x1800864fa  mov     rdx, [rsi+8]; pSecurityDescriptor
0x1800864fe  mov     rcx, r14; pObjectName
0x180086501  call    ?_PropagateInheritedAces@@YAJPEBGQEAX@Z; _PropagateInheritedAces(ushort const *,void * const)
0x180086506  mov     [rbp+57h+var_A0], eax
0x180086509  mov     edi, eax
0x18008650b  test    eax, eax
0x18008650d  jns     short loc_18008657C
0x18008650f  mov     eax, 1B1h
0x180086514  jmp     short loc_180086523
0x180086516  mov     eax, 1AAh
0x18008651b  mov     edi, 80070057h
0x180086520  mov     [rbp+57h+var_A0], edi
0x180086523  mov     [rbp+57h+var_9A], ax
0x180086527  lea     rcx, [rbp+57h+pOwner]; this
0x18008652b  call    ??1CSdSecurityDescriptorInfo@@QEAA@XZ; CSdSecurityDescriptorInfo::~CSdSecurityDescriptorInfo(void)
0x180086530  lea     rcx, [rbx-1]
0x180086534  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180086538  ja      short loc_180086543
0x18008653a  mov     rcx, rbx; hObject
0x18008653d  call    cs:__imp_CloseHandle
0x180086543  lea     rcx, [rbp+57h+lpPathName]; this
0x180086547  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18008654c  lea     rcx, [rbp+57h+String1]; this
0x180086550  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180086555  lea     rcx, [rbp+57h+var_A0]; this
0x180086559  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008655e  lea     r11, [rsp+0E0h+var_20]
0x180086566  mov     eax, edi
0x180086568  mov     rbx, [r11+38h]
0x18008656c  mov     rsi, [r11+48h]
0x180086570  mov     rsp, r11
0x180086573  pop     r15
0x180086575  pop     r14
0x180086577  pop     r12
0x180086579  pop     rdi
0x18008657a  pop     rbp
0x18008657b  retn
0x18008657c  mov     eax, 1B5h
0x180086581  xor     edi, edi
0x180086583  mov     [rbp+57h+var_9C], ax
0x180086587  mov     [rbp+57h+var_A0], edi
0x18008658a  jmp     short loc_180086527
0x18008658c  mov     rax, cs:WPP_GLOBAL_Control
0x180086593  lea     rcx, WPP_GLOBAL_Control
0x18008659a  cmp     rax, rcx
0x18008659d  jz      short loc_1800865D1
0x18008659f  test    dword ptr [rax+1Ch], 10000000h
0x1800865a6  jz      short loc_1800865D1
0x1800865a8  call    cs:__imp_GetLastError
0x1800865ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800865b5  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x1800865bc  mov     edx, 16h
0x1800865c1  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1800865c5  mov     r9, r14
0x1800865c8  mov     rcx, [rcx+10h]
0x1800865cc  call    WPP_SF_Sd
0x1800865d1  lea     r8d, [rdi+1]; unsigned int
0x1800865d5  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800865da  lea     rcx, [rbp+57h+String1]; this
0x1800865de  call    ?Find@CBsString@@QEBAJGK@Z; CBsString::Find(ushort,ulong)
0x1800865e3  cmp     eax, r15d
0x1800865e6  mov     ebx, eax
0x1800865e8  mov     [rbp+57h+arg_0], eax
0x1800865eb  jz      loc_18008677F
0x1800865f1  mov     r8d, eax; unsigned int
0x1800865f4  lea     rcx, [rbp+57h+lpPathName]; this
0x1800865f8  mov     rdx, r14; unsigned __int16 *
0x1800865fb  mov     r15d, 1C9h
0x180086601  call    ?Set@CBsString@@QEAAJPEBGK@Z; CBsString::Set(ushort const *,ulong)
0x180086606  mov     [rbp+57h+var_A0], eax
0x180086609  mov     edi, eax
0x18008660b  test    eax, eax
0x18008660d  js      loc_180086771
0x180086613  mov     [rbp+57h+var_9C], r15w
0x180086618  mov     rcx, cs:WPP_GLOBAL_Control
0x18008661f  lea     rax, WPP_GLOBAL_Control
0x180086626  mov     r12, [rbp+57h+lpPathName]
0x18008662a  cmp     rcx, rax
0x18008662d  jz      short loc_18008664D
0x18008662f  test    byte ptr [rcx+1Ch], 2
0x180086633  jz      short loc_18008664D
0x180086635  mov     rcx, [rcx+10h]
0x180086639  lea     r8, WPP_df8cd073d3d8361ada3b590c76323716_Traceguids
0x180086640  mov     edx, 17h
0x180086645  mov     r9, r12
0x180086648  call    WPP_SF_S
0x18008664d  mov     rdx, rsi; lpSecurityAttributes
0x180086650  mov     rcx, r12; lpPathName
0x180086653  call    cs:__imp_CreateDirectoryW
0x180086659  mov     r15d, eax
0x18008665c  test    eax, eax
0x18008665e  jnz     short loc_1800866C6
0x180086660  call    cs:__imp_GetLastError
0x180086666  mov     edi, eax
0x180086668  cmp     eax, 0B7h
0x18008666d  jz      short loc_1800866C6
0x18008666f  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x180086678  lea     r8d, [r15+7]; dwShareMode
0x18008667c  mov     [rsp+0E0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180086684  xor     r9d, r9d; lpSecurityAttributes
0x180086687  mov     edx, 100000h; dwDesiredAccess
0x18008668c  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180086694  mov     rcx, r12; lpFileName
0x180086697  call    cs:__imp_CreateFileW
0x18008669d  mov     rbx, rax
0x1800866a0  dec     rax
0x1800866a3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800866a7  ja      loc_18008675A
0x1800866ad  mov     eax, 1DCh
0x1800866b2  mov     [rbp+57h+var_A0], r15d
0x1800866b6  mov     rcx, rbx; hObject
0x1800866b9  mov     [rbp+57h+var_9C], ax
0x1800866bd  call    cs:__imp_CloseHandle
0x1800866c3  mov     ebx, [rbp+57h+arg_0]
0x1800866c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800866cd  lea     rax, WPP_GLOBAL_Control
0x1800866d4  cmp     rcx, rax
0x1800866d7  jz      short loc_180086709
  ... truncated ...
```
