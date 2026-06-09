# CIntProv::ReadLastBackup(Registry &,CWbemObject *)

- ea: `0x180099d30`
- end: `0x18009a045`
- name: `?ReadLastBackup@CIntProv@@QEAAJAEAVRegistry@@PEAVCWbemObject@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CIntProv *__hidden this, struct Registry *, struct CWbemObject *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180098ab4`

## callees

- `0x18000b140`
- `0x18001cce0`
- `0x18001d390`
- `0x18005fc58`
- `0x180098e60`
- `0x180099d30`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180099de7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180099de7`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180099f88`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180099f88`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180099f60`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180099f60`
- `wbemcomn!?SetBSTR@CVar@@QEAAHPEAG@Z` at `0x180099fc6`
- `wbemcomn!?SetBSTR@CVar@@QEAAHPEAG@Z` at `0x180099fc6`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180099d77`
- `wbemcomn!?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z` at `0x180099d77`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180099fb6`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180099fb6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180099ff6`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180099ff6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180099e09`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180099e09`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180099f6f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009a00b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009a015`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180099f6f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009a00b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18009a015`
- `wbemcomn!GetMemLogObject` at `0x180099d81`
- `wbemcomn!GetMemLogObject` at `0x180099e17`
- `wbemcomn!GetMemLogObject` at `0x180099e98`
- `wbemcomn!GetMemLogObject` at `0x180099ef1`
- `wbemcomn!GetMemLogObject` at `0x180099d81`
- `wbemcomn!GetMemLogObject` at `0x180099e17`
- `wbemcomn!GetMemLogObject` at `0x180099e98`
- `wbemcomn!GetMemLogObject` at `0x180099ef1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180099d91`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180099e27`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180099ea3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180099efc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180099d91`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180099e27`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180099ea3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180099efc`

## string_xrefs

- `0x180099d70`: `Repository Directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CIntProv::ReadLastBackup(CIntProv *this, struct Registry *a2, struct CWbemObject *a3)
{
  CMemoryLog *v4; // rax
  WCHAR *v6; // rbx
  unsigned __int64 v7; // r15
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  CMemoryLog *v10; // rax
  unsigned int DateTime; // edi
  int v12; // edi
  CMemoryLog *MemLogObject; // rax
  int v14; // edi
  CMemoryLog *v15; // rax
  HANDLE FileW; // rax
  bool v17; // dl
  unsigned __int64 v18; // r9
  LPCWSTR lpString; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v20[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v21[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v23[40]; // [rsp+C0h] [rbp-40h] BYREF

  lpString = 0;
  if ( !Registry::GetStr(a2, L"Repository Directory", (unsigned __int16 **)&lpString) )
  {
    v6 = (WCHAR *)lpString;
    v20[1] = lpString;
    v7 = lstrlenW(lpString) + 10;
    v8 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v7, 2u));
    v9 = v8;
    if ( v8 )
    {
      v20[2] = v8;
      v12 = StringCchCopyW(v8, v7, lpString);
      if ( v12 < 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v12);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            WPP_74d77713876d364524dd83337d5790f1_Traceguids,
            (unsigned int)v12);
        }
      }
      v14 = StringCchCatW(v9, v7, L"\\cim.rec");
      if ( v14 < 0 )
      {
        v15 = GetMemLogObject();
        CMemoryLog::Write(v15, v14);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            WPP_74d77713876d364524dd83337d5790f1_Traceguids,
            (unsigned int)v14);
        }
      }
      memset(&FileInformation, 0, sizeof(FileInformation));
      FileW = CreateFileW(v9, 0, 3u, 0, 3u, 0, 0);
      if ( FileW != (HANDLE)-1LL )
      {
        v20[0] = FileW;
        if ( GetFileInformationByHandle(FileW, &FileInformation) )
        {
          DateTime = GetDateTime(&FileInformation.ftLastWriteTime, v17, v23, v18);
          if ( !DateTime )
          {
            CVar::CVar((CVar *)v21);
            CVar::SetBSTR((CVar *)v21, v23);
            DateTime = (*(__int64 (__fastcall **)(struct CWbemObject *, const wchar_t *, _BYTE *, __int64))(*(_QWORD *)a3 + 872LL))(
                         a3,
                         L"BackupLastTime",
                         v21,
                         101);
            CVar::~CVar((CVar *)v21);
          }
          CCloseMe::~CCloseMe((CCloseMe *)v20);
          CWin32DefaultArena::WbemMemFree(v9);
          goto LABEL_29;
        }
        CCloseMe::~CCloseMe((CCloseMe *)v20);
      }
      CWin32DefaultArena::WbemMemFree(v9);
      DateTime = 0;
    }
    else
    {
      v10 = GetMemLogObject();
      DateTime = -2147217402;
      CMemoryLog::Write(v10, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_74d77713876d364524dd83337d5790f1_Traceguids, 2147749894LL);
      }
    }
LABEL_29:
    CWin32DefaultArena::WbemMemFree(v6);
    return DateTime;
  }
  v4 = GetMemLogObject();
  CMemoryLog::Write(v4, -2147217407);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_74d77713876d364524dd83337d5790f1_Traceguids, 2147749889LL);
  }
  return 2147749889LL;
}

```

## disassembly

```asm
0x180099d30  mov     [rsp-8+arg_0], rbx
0x180099d35  mov     [rsp-8+arg_18], rsi
0x180099d3a  push    rbp
0x180099d3b  push    rdi
0x180099d3c  push    r12
0x180099d3e  push    r14
0x180099d40  push    r15
0x180099d42  lea     rbp, [rsp-20h]
0x180099d47  sub     rsp, 120h
0x180099d4e  mov     rax, cs:__security_cookie
0x180099d55  xor     rax, rsp
0x180099d58  mov     [rbp+40h+var_30], rax
0x180099d5c  mov     r12, r8
0x180099d5f  mov     rcx, rdx
0x180099d62  mov     [rsp+140h+lpString], 0
0x180099d6b  lea     r8, [rsp+140h+lpString]
0x180099d70  lea     rdx, aRepositoryDire; "Repository Directory"
0x180099d77  call    cs:__imp_?GetStr@Registry@@QEAAHPEBGPEAPEAG@Z; Registry::GetStr(ushort const *,ushort * *)
0x180099d7d  test    eax, eax
0x180099d7f  jz      short loc_180099DD8
0x180099d81  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180099d87  mov     ebx, 80041001h
0x180099d8c  mov     edx, ebx
0x180099d8e  mov     rcx, rax
0x180099d91  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180099d97  lea     r14, WPP_GLOBAL_Control
0x180099d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180099da5  cmp     rcx, r14
0x180099da8  jz      short loc_180099DD1
0x180099daa  test    byte ptr [rcx+1Ch], 1
0x180099dae  jz      short loc_180099DD1
0x180099db0  cmp     byte ptr [rcx+19h], 2
0x180099db4  jb      short loc_180099DD1
0x180099db6  mov     edx, 1Eh
0x180099dbb  mov     r9d, 80041001h
0x180099dc1  lea     r8, WPP_74d77713876d364524dd83337d5790f1_Traceguids
0x180099dc8  mov     rcx, [rcx+10h]
0x180099dcc  call    WPP_SF_d
0x180099dd1  mov     eax, ebx
0x180099dd3  jmp     loc_18009A01D
0x180099dd8  mov     rbx, [rsp+140h+lpString]
0x180099ddd  mov     [rsp+140h+var_F0], rbx
0x180099de2  mov     rcx, [rsp+140h+lpString]; lpString
0x180099de7  call    cs:__imp_lstrlenW
0x180099ded  add     eax, 0Ah
0x180099df0  movsxd  r15, eax
0x180099df3  mov     eax, 2
0x180099df8  mul     r15
0x180099dfb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180099e02  cmovb   rax, rcx
0x180099e06  mov     rcx, rax
0x180099e09  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180099e0f  mov     rsi, rax
0x180099e12  test    rax, rax
0x180099e15  jnz     short loc_180099E76
0x180099e17  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180099e1d  mov     edi, 80041006h
0x180099e22  mov     edx, edi
0x180099e24  mov     rcx, rax
0x180099e27  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180099e2d  lea     r14, WPP_GLOBAL_Control
0x180099e34  mov     rcx, cs:WPP_GLOBAL_Control
0x180099e3b  cmp     rcx, r14
0x180099e3e  jz      loc_18009A012
0x180099e44  test    byte ptr [rcx+1Ch], 1
0x180099e48  jz      loc_18009A012
0x180099e4e  cmp     byte ptr [rcx+19h], 2
0x180099e52  jb      loc_18009A012
0x180099e58  lea     edx, [rsi+1Fh]
0x180099e5b  mov     r9d, 80041006h
0x180099e61  lea     r8, WPP_74d77713876d364524dd83337d5790f1_Traceguids
0x180099e68  mov     rcx, [rcx+10h]
0x180099e6c  call    WPP_SF_d
0x180099e71  jmp     loc_18009A012
0x180099e76  mov     [rsp+140h+var_E8], rsi
0x180099e7b  mov     r8, [rsp+140h+lpString]; unsigned __int16 *
0x180099e80  mov     rdx, r15; unsigned __int64
0x180099e83  mov     rcx, rsi; unsigned __int16 *
0x180099e86  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180099e8b  mov     edi, eax
0x180099e8d  lea     r14, WPP_GLOBAL_Control
0x180099e94  test    eax, eax
0x180099e96  jns     short loc_180099ED9
0x180099e98  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180099e9e  mov     edx, edi
0x180099ea0  mov     rcx, rax
0x180099ea3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180099ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x180099eb0  cmp     rcx, r14
0x180099eb3  jz      short loc_180099ED9
0x180099eb5  test    byte ptr [rcx+1Ch], 1
0x180099eb9  jz      short loc_180099ED9
0x180099ebb  cmp     byte ptr [rcx+19h], 2
0x180099ebf  jb      short loc_180099ED9
0x180099ec1  mov     edx, 20h ; ' '
0x180099ec6  mov     r9d, edi
0x180099ec9  lea     r8, WPP_74d77713876d364524dd83337d5790f1_Traceguids
0x180099ed0  mov     rcx, [rcx+10h]
0x180099ed4  call    WPP_SF_d
0x180099ed9  lea     r8, aCimRec; "\\cim.rec"
0x180099ee0  mov     rdx, r15; unsigned __int64
0x180099ee3  mov     rcx, rsi; unsigned __int16 *
0x180099ee6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180099eeb  mov     edi, eax
0x180099eed  test    eax, eax
0x180099eef  jns     short loc_180099F32
0x180099ef1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180099ef7  mov     edx, edi
0x180099ef9  mov     rcx, rax
0x180099efc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180099f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180099f09  cmp     rcx, r14
0x180099f0c  jz      short loc_180099F32
0x180099f0e  test    byte ptr [rcx+1Ch], 1
0x180099f12  jz      short loc_180099F32
0x180099f14  cmp     byte ptr [rcx+19h], 2
0x180099f18  jb      short loc_180099F32
0x180099f1a  mov     edx, 21h ; '!'
0x180099f1f  mov     r9d, edi
0x180099f22  lea     r8, WPP_74d77713876d364524dd83337d5790f1_Traceguids
0x180099f29  mov     rcx, [rcx+10h]
0x180099f2d  call    WPP_SF_d
0x180099f32  xorps   xmm0, xmm0
0x180099f35  xor     eax, eax
0x180099f37  movups  xmmword ptr [rbp+40h+FileInformation.dwFileAttributes], xmm0
0x180099f3b  movups  xmmword ptr [rbp+40h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180099f3f  movups  xmmword ptr [rbp+40h+FileInformation.nFileSizeHigh], xmm0
0x180099f43  mov     [rbp+40h+FileInformation.nFileIndexLow], eax
0x180099f46  mov     [rsp+140h+hTemplateFile], rax; hTemplateFile
0x180099f4b  mov     [rsp+140h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180099f4f  lea     r8d, [rax+3]; dwShareMode
0x180099f53  mov     [rsp+140h+dwCreationDisposition], r8d; dwCreationDisposition
0x180099f58  xor     r9d, r9d; lpSecurityAttributes
0x180099f5b  xor     edx, edx; dwDesiredAccess
0x180099f5d  mov     rcx, rsi; lpFileName
0x180099f60  call    cs:__imp_CreateFileW
0x180099f66  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180099f6a  jnz     short loc_180099F7C
0x180099f6c  mov     rcx, rsi
0x180099f6f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180099f75  xor     edi, edi
0x180099f77  jmp     loc_18009A012
0x180099f7c  mov     [rsp+140h+var_F8], rax
0x180099f81  lea     rdx, [rbp+40h+FileInformation]; lpFileInformation
0x180099f85  mov     rcx, rax; hFile
0x180099f88  call    cs:__imp_GetFileInformationByHandle
0x180099f8e  test    eax, eax
0x180099f90  jnz     short loc_180099F9E
0x180099f92  lea     rcx, [rsp+140h+var_F8]; this
0x180099f97  call    ??1CCloseMe@@QEAA@XZ; CCloseMe::~CCloseMe(void)
0x180099f9c  jmp     short loc_180099F6C
0x180099f9e  lea     r8, [rbp+40h+var_80]; unsigned __int16 *
0x180099fa2  lea     rcx, [rbp+40h+FileInformation.ftLastWriteTime]; struct _FILETIME *
0x180099fa6  call    ?GetDateTime@@YAJPEAU_FILETIME@@_NPEAG_K@Z; GetDateTime(_FILETIME *,bool,ushort *,unsigned __int64)
0x180099fab  mov     edi, eax
0x180099fad  test    eax, eax
0x180099faf  jnz     short loc_180099FFD
0x180099fb1  lea     rcx, [rsp+140h+var_E0]
0x180099fb6  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180099fbc  nop
0x180099fbd  lea     rdx, [rbp+40h+var_80]
0x180099fc1  lea     rcx, [rsp+140h+var_E0]
0x180099fc6  call    cs:__imp_?SetBSTR@CVar@@QEAAHPEAG@Z; CVar::SetBSTR(ushort *)
0x180099fcc  mov     rax, [r12]
0x180099fd0  lea     r9d, [rdi+65h]
0x180099fd4  lea     r8, [rsp+140h+var_E0]
0x180099fd9  lea     rdx, aBackuplasttime; "BackupLastTime"
0x180099fe0  mov     rcx, r12
0x180099fe3  mov     rax, [rax+368h]
0x180099fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099fef  mov     edi, eax
0x180099ff1  lea     rcx, [rsp+140h+var_E0]
0x180099ff6  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180099ffc  nop
0x180099ffd  lea     rcx, [rsp+140h+var_F8]; this
0x18009a002  call    ??1CCloseMe@@QEAA@XZ; CCloseMe::~CCloseMe(void)
0x18009a007  nop
0x18009a008  mov     rcx, rsi
0x18009a00b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18009a011  nop
0x18009a012  mov     rcx, rbx
0x18009a015  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18009a01b  mov     eax, edi
0x18009a01d  mov     rcx, [rbp+40h+var_30]
0x18009a021  xor     rcx, rsp; StackCookie
0x18009a024  call    __security_check_cookie
0x18009a029  lea     r11, [rsp+140h+var_20]
0x18009a031  mov     rbx, [r11+30h]
0x18009a035  mov     rsi, [r11+48h]
0x18009a039  mov     rsp, r11
0x18009a03c  pop     r15
0x18009a03e  pop     r14
0x18009a040  pop     r12
0x18009a042  pop     rdi
0x18009a043  pop     rbp
0x18009a044  retn
```
