# CWerService::SvcMergeETWLogs(_WERSVC_MSG *,_WERSVC_MSG *)

- ea: `0x180019728`
- end: `0x180019b2b`
- name: `?SvcMergeETWLogs@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z`
- size: `1027`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x180014fa4`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x1800035e8`
- `0x180004a44`
- `0x1800106f4`
- `0x180011ef8`
- `0x180012004`
- `0x180019728`
- `0x18003230c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019a3b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019842`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800198d4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019842`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800198d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019938`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019aac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019ac1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019938`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019aac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019ac1`
- `WerEtw!WerMergeEtlEx` at `0x18001996f`
- `WerEtw!WerMergeEtlEx` at `0x18001996f`
- `wer!WerpGetPathOfWERTempDirectory` at `0x1800197bd`
- `wer!WerpGetPathOfWERTempDirectory` at `0x1800197bd`

## pseudocode

```c
__int64 __fastcall CWerService::SvcMergeETWLogs(CWerService *this, struct _WERSVC_MSG *a2, struct _WERSVC_MSG *a3)
{
  void *v5; // r12
  void *v6; // r13
  __int64 v7; // rdi
  signed int PathOfWERTempDirectory; // ebx
  HANDLE FileW; // rax
  void *v10; // r15
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  HANDLE v13; // rax
  void *v14; // r14
  __int64 v15; // rcx
  LPCWSTR v16; // rdx
  WCHAR *v17; // rax
  WCHAR v18; // r8
  WCHAR *v19; // rcx
  signed int v20; // eax
  _QWORD *v21; // rcx
  int v22; // edx
  int v23; // r9d
  signed int LastError; // eax
  LPCWSTR v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v27[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v29[8]; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v30; // [rsp+80h] [rbp-80h]
  HANDLE v31; // [rsp+88h] [rbp-78h]
  _BYTE v32[2640]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[528]; // [rsp+AE0h] [rbp+9E0h] BYREF

  *((_WORD *)a2 + 283) = 0;
  *((_WORD *)a2 + 543) = 0;
  lpFileName[0] = v29;
  lpFileName[1] = v29;
  v29[0] = 0;
  v26[0] = v27;
  v26[1] = v27;
  v27[0] = 0;
  v5 = 0;
  v6 = 0;
  v30 = 0;
  v7 = 260;
  PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v33, 260);
  if ( PathOfWERTempDirectory < 0 )
    goto LABEL_39;
  PathOfWERTempDirectory = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             lpFileName,
                             L"%ws\\%ws",
                             v33,
                             (char *)a2 + 48);
  if ( PathOfWERTempDirectory < 0 )
    goto LABEL_39;
  PathOfWERTempDirectory = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             v26,
                             L"%ws\\%ws",
                             v33,
                             (char *)a2 + 568);
  if ( PathOfWERTempDirectory < 0 )
    goto LABEL_39;
  FileW = CreateFileW(lpFileName[0], 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  v10 = FileW;
  v5 = FileW;
  v31 = FileW;
  if ( (unsigned __int64)FileW + 1 <= 1 )
  {
    LastError = GetLastError();
    PathOfWERTempDirectory = LastError;
    if ( LastError > 0 )
      PathOfWERTempDirectory = (unsigned __int16)LastError | 0x80070000;
    if ( PathOfWERTempDirectory >= 0 )
      PathOfWERTempDirectory = -2147467259;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v22 = 124;
    v23 = (int)lpFileName[0];
LABEL_38:
    WPP_SF_Sd(v21[2], v22, (unsigned int)&WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, v23, PathOfWERTempDirectory);
    goto LABEL_39;
  }
  PathOfWERTempDirectory = UtilVerifyFilePath(lpFileName[0], FileW);
  if ( PathOfWERTempDirectory < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v12 = 125;
    goto LABEL_9;
  }
  v13 = CreateFileW(v26[0], 0xC0000000, 3u, 0, 3u, 0x80u, 0);
  v14 = v13;
  v6 = v13;
  v30 = v13;
  if ( (unsigned __int64)v13 + 1 <= 1 )
  {
    v20 = GetLastError();
    PathOfWERTempDirectory = v20;
    if ( v20 > 0 )
      PathOfWERTempDirectory = (unsigned __int16)v20 | 0x80070000;
    if ( PathOfWERTempDirectory >= 0 )
      PathOfWERTempDirectory = -2147467259;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v22 = 126;
    v23 = (int)v26[0];
    goto LABEL_38;
  }
  PathOfWERTempDirectory = UtilVerifyFilePath(v26[0], v13);
  if ( PathOfWERTempDirectory < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_39;
    v12 = 127;
LABEL_9:
    WPP_SF_d(v11[2], v12, &WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids, (unsigned int)PathOfWERTempDirectory);
    goto LABEL_39;
  }
  v5 = 0;
  CloseHandle(v10);
  v6 = 0;
  CloseHandle(v14);
  memset_0(v32, 0, sizeof(v32));
  PathOfWERTempDirectory = WerMergeEtlEx(lpFileName[0], v26[0], 0, v32);
  LogEtwSessionMerge((struct _WER_MERGE_TRACE_PROPERTIES *)v32, PathOfWERTempDirectory);
  if ( PathOfWERTempDirectory >= 0 )
  {
    v15 = 2147483646;
    v16 = v26[0];
    v17 = (WCHAR *)((char *)a3 + 568);
    do
    {
      if ( !v15 )
        break;
      v18 = *v16;
      if ( !*v16 )
        break;
      ++v16;
      *v17++ = v18;
      --v15;
      --v7;
    }
    while ( v7 );
    v19 = v17 - 1;
    if ( v7 )
      v19 = v17;
    *v19 = 0;
    PathOfWERTempDirectory = v7 == 0 ? 0x8007007A : 0;
    if ( v7 )
    {
      *((_DWORD *)a3 + 10) = -268304384;
      *((_DWORD *)a3 + 11) = 0;
      goto LABEL_40;
    }
  }
LABEL_39:
  *((_DWORD *)a3 + 10) = -268304383;
  *((_DWORD *)a3 + 11) = PathOfWERTempDirectory;
LABEL_40:
  if ( (unsigned __int64)v6 + 1 > 1 )
    CloseHandle(v6);
  if ( (unsigned __int64)v5 + 1 > 1 )
    CloseHandle(v5);
  if ( v26[0] != v27 )
    operator delete((void *)v26[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( lpFileName[0] != v29 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)PathOfWERTempDirectory;
}

```

## disassembly

```asm
0x180019728  mov     [rsp-8+arg_0], rbx
0x18001972d  push    rbp
0x18001972e  push    rsi
0x18001972f  push    rdi
0x180019730  push    r12
0x180019732  push    r13
0x180019734  push    r14
0x180019736  push    r15
0x180019738  lea     rbp, [rsp-0C00h]
0x180019740  sub     rsp, 0D00h
0x180019747  mov     rax, cs:__security_cookie
0x18001974e  xor     rax, rsp
0x180019751  mov     [rbp+0C30h+var_40], rax
0x180019758  mov     rsi, r8
0x18001975b  mov     r14, rdx
0x18001975e  xor     r15d, r15d
0x180019761  mov     [rdx+236h], r15w
0x180019769  mov     [rdx+43Eh], r15w
0x180019771  lea     rax, [rsp+0D30h+var_CC0]
0x180019776  mov     [rsp+0D30h+lpFileName], rax
0x18001977b  lea     rax, [rsp+0D30h+var_CC0]
0x180019780  mov     [rsp+0D30h+var_CC8], rax
0x180019785  mov     [rsp+0D30h+var_CC0], r15w
0x18001978b  lea     rax, [rsp+0D30h+var_CE0]
0x180019790  mov     [rsp+0D30h+var_CF0], rax
0x180019795  lea     rax, [rsp+0D30h+var_CE0]
0x18001979a  mov     [rsp+0D30h+var_CE8], rax
0x18001979f  mov     [rsp+0D30h+var_CE0], r15w
0x1800197a5  mov     r12d, r15d
0x1800197a8  mov     r13d, r15d
0x1800197ab  mov     [rbp+0C30h+var_CB0], r15
0x1800197af  mov     edi, 104h
0x1800197b4  mov     edx, edi
0x1800197b6  lea     rcx, [rbp+0C30h+var_250]
0x1800197bd  call    cs:__imp_WerpGetPathOfWERTempDirectory
0x1800197c3  mov     ebx, eax
0x1800197c5  test    eax, eax
0x1800197c7  js      loc_180019A95
0x1800197cd  lea     r9, [r14+30h]
0x1800197d1  lea     r8, [rbp+0C30h+var_250]
0x1800197d8  lea     rdx, aWsWs; "%ws\\%ws"
0x1800197df  lea     rcx, [rsp+0D30h+lpFileName]
0x1800197e4  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800197e9  mov     ebx, eax
0x1800197eb  test    eax, eax
0x1800197ed  js      loc_180019A95
0x1800197f3  lea     r9, [r14+238h]
0x1800197fa  lea     r8, [rbp+0C30h+var_250]
0x180019801  lea     rdx, aWsWs; "%ws\\%ws"
0x180019808  lea     rcx, [rsp+0D30h+var_CF0]
0x18001980d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180019812  mov     ebx, eax
0x180019814  test    eax, eax
0x180019816  js      loc_180019A95
0x18001981c  mov     [rsp+0D30h+hTemplateFile], r15; hTemplateFile
0x180019821  mov     [rsp+0D30h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180019829  lea     r14d, [r15+3]
0x18001982d  mov     [rsp+0D30h+dwCreationDisposition], r14d; dwCreationDisposition
0x180019832  xor     r9d, r9d; lpSecurityAttributes
0x180019835  mov     r8d, r14d; dwShareMode
0x180019838  mov     edx, 0C0000000h; dwDesiredAccess
0x18001983d  mov     rcx, [rsp+0D30h+lpFileName]; lpFileName
0x180019842  call    cs:__imp_CreateFileW
0x180019848  mov     r15, rax
0x18001984b  mov     r12, rax
0x18001984e  mov     [rbp+0C30h+var_CA8], rax
0x180019852  lea     rcx, [rax+1]
0x180019856  cmp     rcx, 1
0x18001985a  jbe     loc_180019A3B
0x180019860  mov     rdx, rax; void *
0x180019863  mov     rcx, [rsp+0D30h+lpFileName]; wchar_t *
0x180019868  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x18001986d  mov     ebx, eax
0x18001986f  xor     eax, eax
0x180019871  test    ebx, ebx
0x180019873  jns     short loc_1800198B2
0x180019875  lea     rax, WPP_GLOBAL_Control
0x18001987c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019883  cmp     rcx, rax
0x180019886  jz      loc_180019A95
0x18001988c  test    byte ptr [rcx+1Ch], 1
0x180019890  jz      loc_180019A95
0x180019896  lea     edx, [r13+7Dh]
0x18001989a  mov     r9d, ebx
0x18001989d  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x1800198a4  mov     rcx, [rcx+10h]
0x1800198a8  call    WPP_SF_d
0x1800198ad  jmp     loc_180019A95
0x1800198b2  mov     [rsp+0D30h+hTemplateFile], rax; hTemplateFile
0x1800198b7  mov     [rsp+0D30h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800198bf  mov     [rsp+0D30h+dwCreationDisposition], r14d; dwCreationDisposition
0x1800198c4  xor     r9d, r9d; lpSecurityAttributes
0x1800198c7  mov     r8d, r14d; dwShareMode
0x1800198ca  mov     edx, 0C0000000h; dwDesiredAccess
0x1800198cf  mov     rcx, [rsp+0D30h+var_CF0]; lpFileName
0x1800198d4  call    cs:__imp_CreateFileW
0x1800198da  mov     r14, rax
0x1800198dd  mov     r13, rax
0x1800198e0  mov     [rbp+0C30h+var_CB0], rax
0x1800198e4  lea     rcx, [rax+1]
0x1800198e8  cmp     rcx, 1
0x1800198ec  jbe     loc_1800199F7
0x1800198f2  mov     rdx, rax; void *
0x1800198f5  mov     rcx, [rsp+0D30h+var_CF0]; wchar_t *
0x1800198fa  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x1800198ff  mov     ebx, eax
0x180019901  xor     eax, eax
0x180019903  test    ebx, ebx
0x180019905  jns     short loc_180019932
0x180019907  lea     rax, WPP_GLOBAL_Control
0x18001990e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019915  cmp     rcx, rax
0x180019918  jz      loc_180019A95
0x18001991e  test    byte ptr [rcx+1Ch], 1
0x180019922  jz      loc_180019A95
0x180019928  mov     edx, 7Fh
0x18001992d  jmp     loc_18001989A
0x180019932  mov     r12, rax
0x180019935  mov     rcx, r15; hObject
0x180019938  call    cs:__imp_CloseHandle
0x18001993e  xor     r15d, r15d
0x180019941  mov     r13d, r15d
0x180019944  mov     rcx, r14; hObject
0x180019947  call    cs:__imp_CloseHandle
0x18001994d  xor     edx, edx; Val
0x18001994f  mov     r8d, 0A50h; Size
0x180019955  lea     rcx, [rbp+0C30h+var_CA0]; void *
0x180019959  call    memset_0
0x18001995e  lea     r9, [rbp+0C30h+var_CA0]
0x180019962  xor     r8d, r8d
0x180019965  mov     rdx, [rsp+0D30h+var_CF0]
0x18001996a  mov     rcx, [rsp+0D30h+lpFileName]
0x18001996f  call    cs:__imp_WerMergeEtlEx
0x180019975  mov     ebx, eax
0x180019977  mov     edx, eax; int
0x180019979  lea     rcx, [rbp+0C30h+var_CA0]; struct _WER_MERGE_TRACE_PROPERTIES *
0x18001997d  call    ?LogEtwSessionMerge@@YAXPEAU_WER_MERGE_TRACE_PROPERTIES@@J@Z; LogEtwSessionMerge(_WER_MERGE_TRACE_PROPERTIES *,long)
0x180019982  test    ebx, ebx
0x180019984  js      loc_180019A95
0x18001998a  mov     ecx, 7FFFFFFEh
0x18001998f  mov     rdx, [rsp+0D30h+var_CF0]
0x180019994  lea     rax, [rsi+238h]
0x18001999b  test    rcx, rcx
0x18001999e  jz      short loc_1800199BF
0x1800199a0  movzx   r8d, word ptr [rdx]
0x1800199a4  test    r8w, r8w
0x1800199a8  jz      short loc_1800199BF
0x1800199aa  add     rdx, 2
0x1800199ae  mov     [rax], r8w
0x1800199b2  add     rax, 2
0x1800199b6  dec     rcx
0x1800199b9  sub     rdi, 1
0x1800199bd  jnz     short loc_18001999B
0x1800199bf  lea     rcx, [rax-2]
0x1800199c3  test    rdi, rdi
0x1800199c6  cmovnz  rcx, rax
0x1800199ca  mov     [rcx], r15w
0x1800199ce  mov     rax, rdi
0x1800199d1  neg     rax
0x1800199d4  sbb     ebx, ebx
0x1800199d6  not     ebx
0x1800199d8  and     ebx, 8007007Ah
0x1800199de  test    rdi, rdi
0x1800199e1  jz      loc_180019A95
0x1800199e7  mov     dword ptr [rsi+28h], 0F0020000h
0x1800199ee  mov     [rsi+2Ch], r15d
0x1800199f2  jmp     loc_180019A9F
0x1800199f7  call    cs:__imp_GetLastError
0x1800199fd  mov     ebx, eax
0x1800199ff  test    eax, eax
0x180019a01  jle     short loc_180019A0C
0x180019a03  movzx   ebx, ax
0x180019a06  or      ebx, 80070000h
0x180019a0c  mov     eax, 80004005h
0x180019a11  test    ebx, ebx
0x180019a13  cmovns  ebx, eax
0x180019a16  lea     rax, WPP_GLOBAL_Control
0x180019a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a24  cmp     rcx, rax
0x180019a27  jz      short loc_180019A95
0x180019a29  test    byte ptr [rcx+1Ch], 1
0x180019a2d  jz      short loc_180019A91
0x180019a2f  mov     edx, 7Eh ; '~'
0x180019a34  mov     r9, [rsp+0D30h+var_CF0]
0x180019a39  jmp     short loc_180019A7D
0x180019a3b  call    cs:__imp_GetLastError
0x180019a41  mov     ebx, eax
0x180019a43  test    eax, eax
0x180019a45  jle     short loc_180019A50
0x180019a47  movzx   ebx, ax
0x180019a4a  or      ebx, 80070000h
0x180019a50  mov     eax, 80004005h
0x180019a55  test    ebx, ebx
0x180019a57  cmovns  ebx, eax
0x180019a5a  lea     rax, WPP_GLOBAL_Control
0x180019a61  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a68  cmp     rcx, rax
0x180019a6b  jz      short loc_180019A95
0x180019a6d  test    byte ptr [rcx+1Ch], 1
0x180019a71  jz      short loc_180019A91
0x180019a73  mov     edx, 7Ch ; '|'
0x180019a78  mov     r9, [rsp+0D30h+lpFileName]
0x180019a7d  mov     [rsp+0D30h+dwCreationDisposition], ebx
0x180019a81  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180019a88  mov     rcx, [rcx+10h]
0x180019a8c  call    WPP_SF_Sd
0x180019a91  test    ebx, ebx
0x180019a93  jns     short loc_180019A9F
0x180019a95  mov     dword ptr [rsi+28h], 0F0020001h
0x180019a9c  mov     [rsi+2Ch], ebx
0x180019a9f  lea     rax, [r13+1]
0x180019aa3  cmp     rax, 1
0x180019aa7  jbe     short loc_180019AB3
0x180019aa9  mov     rcx, r13; hObject
0x180019aac  call    cs:__imp_CloseHandle
0x180019ab2  nop
0x180019ab3  lea     rax, [r12+1]
0x180019ab8  cmp     rax, 1
0x180019abc  jbe     short loc_180019AC8
0x180019abe  mov     rcx, r12; hObject
0x180019ac1  call    cs:__imp_CloseHandle
0x180019ac7  nop
0x180019ac8  lea     rax, [rsp+0D30h+var_CE0]
0x180019acd  mov     rcx, [rsp+0D30h+var_CF0]; void *
0x180019ad2  cmp     rcx, rax
0x180019ad5  jz      short loc_180019AE4
0x180019ad7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019ade  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019ae3  nop
0x180019ae4  lea     rax, [rsp+0D30h+var_CC0]
0x180019ae9  mov     rcx, [rsp+0D30h+lpFileName]; void *
0x180019aee  cmp     rcx, rax
0x180019af1  jz      short loc_180019AFF
0x180019af3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019afa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019aff  mov     eax, ebx
0x180019b01  mov     rcx, [rbp+0C30h+var_40]
0x180019b08  xor     rcx, rsp; StackCookie
0x180019b0b  call    __security_check_cookie
0x180019b10  mov     rbx, [rsp+0D30h+arg_0]
0x180019b18  add     rsp, 0D00h
0x180019b1f  pop     r15
0x180019b21  pop     r14
0x180019b23  pop     r13
0x180019b25  pop     r12
0x180019b27  pop     rdi
0x180019b28  pop     rsi
0x180019b29  pop     rbp
0x180019b2a  retn
```
