# CProcessDump::AttachDumpToReport(ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18007f868`
- end: `0x18007fda2`
- name: `?AttachDumpToReport@CProcessDump@@QEAAJKPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1338`
- prototype: `__int64 __fastcall(enum _WER_DUMP_TYPE *this, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800360d0`
- `0x1800363fc`

## callees

- `0x180007db4`
- `0x180007de0`
- `0x180007e10`
- `0x180009ad4`
- `0x18000b880`
- `0x18000bbc0`
- `0x18000c390`
- `0x18000d590`
- `0x18001bbc4`
- `0x18001da80`
- `0x18001dfac`
- `0x18001f870`
- `0x18001fe24`
- `0x180027884`
- `0x18002ffc4`
- `0x180039f70`
- `0x18003bf14`
- `0x18003d990`
- `0x18003ec1c`
- `0x180044230`
- `0x180050db0`
- `0x180051efc`
- `0x180051fa4`
- `0x18007f560`
- `0x18007f868`
- `0x18007fda8`
- `0x180081bb0`
- `0x180081bdc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007fafd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18007fafd`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x18007f9d5`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x18007fd5a`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x18007f9d5`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x18007fd5a`

## string_xrefs

- `0x18007fc6c`: `Dump file could not be created: WerpGetPathOfWERTempDirectory %08X.`
- `0x18007fc94`: `Dump file could not be created: Failed to produce security attributes %08X.`
- `0x18007fc82`: `Couldn't write out the GameCore specific heap dump file path %08X.`
- `0x18007fc8b`: `Dump file could not be created: UtilGetTempFile %08X.`
- `0x18007fcf9`: `onecore\windows\feedback\core\werdll\lib\processdump.cpp`
- `0x18007fd38`: `Dump path could not be copied: %08X.`

## pseudocode

```c
__int64 __fastcall CProcessDump::AttachDumpToReport(enum _WER_DUMP_TYPE *this, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r15d
  int v6; // r14d
  wchar_t *v7; // rcx
  int v8; // ebx
  int Dump; // ebx
  int i; // r12d
  unsigned int v11; // esi
  int v12; // r13d
  int PathOfWERTempDirectory; // eax
  BOOL v14; // eax
  int NewRestrictedFileOrDirectorySecurityAttributes; // eax
  bool v16; // zf
  char v17; // al
  enum _WER_DUMP_TYPE v18; // ecx
  int v19; // eax
  const wchar_t *v20; // rax
  int TempFile; // eax
  __int64 v22; // rdx
  wil::details::in1diag3 *v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // eax
  char v27; // al
  int wMonth; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  void **v31; // [rsp+68h] [rbp-98h] BYREF
  void *v32; // [rsp+70h] [rbp-90h] BYREF
  __int64 v33; // [rsp+78h] [rbp-88h]
  struct _SECURITY_ATTRIBUTES v34; // [rsp+80h] [rbp-80h] BYREF
  __int128 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  __int128 v38; // [rsp+C0h] [rbp-40h]
  struct _SYSTEMTIME SystemTime; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t v40[264]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v41[528]; // [rsp+310h] [rbp+210h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+468h]

  v33 = a3;
  v4 = a2;
  v31 = &CFileByteStream::`vftable';
  v6 = 0;
  v32 = 0;
  v30 = 0;
  SystemTime = 0;
  if ( *this == WerDumpTypeNone )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2);
  if ( !*((_QWORD *)this + 14) && !*((_QWORD *)this + 96) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2);
  if ( !*((_DWORD *)this + 30) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2);
  if ( *((_DWORD *)this + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4909ce9a3d833966bf1277dfd490a226_Traceguids, v4);
  if ( *((_DWORD *)this + 42) != 3 )
    goto LABEL_77;
  if ( (this[31] & 1) != 0 )
    goto LABEL_20;
  CRegSetting::CRegSetting((CRegSetting *)&v34);
  wMonth = 0;
  if ( (int)CRegSetting::Initialize(&v34, 0, L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Debug", L"NoHeap") < 0
    || CRegSetting::Load((CRegSetting *)&v34, HKEY_LOCAL_MACHINE, 0x100u) < 0
    || (v8 = 1, !CRegSetting::GetDwordData((CRegSetting *)&v34)) )
  {
    v8 = 0;
  }
  CRegSetting::~CRegSetting((CRegSetting *)&v34);
  if ( v8 )
  {
LABEL_20:
    CProcessDump::LogTrace((CProcessDump *)this, 1u, L"Heapdump generation disabled by NoHeap flag.");
    Dump = -2147019873;
  }
  else
  {
LABEL_77:
    if ( (unsigned __int8)IsXerProgressCallbackPresent(v7, a2, a3, a4) )
      XerProgressCallback(1, *((int *)this + 42));
    for ( i = 0; i < 2; ++i )
    {
      if ( (v4 & 0x10) != 0 || *((int *)this + 44) < 0 )
        v6 = 1;
      if ( i == 1 )
      {
        v6 = 0;
        if ( (v4 & 0x60) != 0x40 || !*((_QWORD *)this + 96) )
          break;
        v11 = v4 & 0xFFFFFF8F | 0x20;
        v12 = 1;
      }
      else
      {
        v12 = 0;
        v11 = v4;
      }
      if ( *((_QWORD *)this + 2) )
      {
        PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v41, 260);
        Dump = PathOfWERTempDirectory;
        if ( PathOfWERTempDirectory < 0 )
        {
          CProcessDump::LogTrace(
            (CProcessDump *)this,
            0,
            L"Dump file could not be created: WerpGetPathOfWERTempDirectory %08X.",
            (unsigned int)PathOfWERTempDirectory);
          goto LABEL_65;
        }
      }
      v14 = *((_DWORD *)this + 21) || (v4 & 0x80u) != 0;
      *((_DWORD *)this + 21) = v14;
      if ( v6 )
      {
        Dump = CProcessDump::AddDumpFileToReport((CProcessDump *)this, 0, v12, v11);
        v6 = 0;
      }
      else
      {
        memset(&v34, 0, sizeof(v34));
        v35 = 0;
        v36 = 0;
        v37 = 0;
        v38 = 0;
        v34.nLength = 24;
        NewRestrictedFileOrDirectorySecurityAttributes = CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(
                                                           (struct CSecurityAttributes *)&v34,
                                                           0);
        Dump = NewRestrictedFileOrDirectorySecurityAttributes;
        v6 = 0;
        if ( NewRestrictedFileOrDirectorySecurityAttributes < 0 )
        {
          CProcessDump::LogTrace(
            (CProcessDump *)this,
            0,
            L"Dump file could not be created: Failed to produce security attributes %08X.",
            (unsigned int)NewRestrictedFileOrDirectorySecurityAttributes);
          goto LABEL_62;
        }
        if ( !(unsigned __int8)IsXerTransportEventUploadCompletePresent()
          || (v16 = CRegSetting::GetDwordData((CRegSetting *)(*((_QWORD *)this + 2) + 51680LL)) == 0, v17 = 1, v16) )
        {
          v17 = 0;
        }
        v18 = *((_DWORD *)this + 42);
        if ( v18 == WerDumpTypeHeapDump && v17 && *((_DWORD *)this + 21) )
        {
          GetSystemTime(&SystemTime);
          wMonth = SystemTime.wMonth;
          v19 = StringCchPrintfW(
                  v40,
                  0x104u,
                  L"\\\\?\\Wer:\\CrashDumps\\WER.%u%u%u%u%u%u%u%u.memory.protected.hdmp",
                  SystemTime.wYear);
          Dump = v19;
          if ( v19 < 0 )
          {
            CProcessDump::LogTrace(
              (CProcessDump *)this,
              0,
              L"Couldn't write out the GameCore specific heap dump file path %08X.",
              (unsigned int)v19);
LABEL_62:
            CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v34);
            goto LABEL_65;
          }
          CFileByteStream::OpenFile((CFileByteStream *)&v31, v40, 0xC0000000, 1u, &v34, 1u, 0x20000080u, 0);
        }
        else
        {
          v20 = CProcessDump::MapDumpFileExtension(v18, v12);
          TempFile = UtilGetTempFile(&v30, v41, v20, v40);
          Dump = TempFile;
          if ( TempFile < 0 )
          {
            CProcessDump::LogTrace(
              (CProcessDump *)this,
              0,
              L"Dump file could not be created: UtilGetTempFile %08X.",
              (unsigned int)TempFile);
            goto LABEL_62;
          }
          tlx::unique_any<tlx::file_handle_traits>::operator=(&v32, &v30);
        }
        Dump = CProcessDump::GenerateDump((CProcessDump *)this, (struct IWerByteStream *)&v31, v11, v32);
        if ( Dump < 0 )
          goto LABEL_62;
        if ( *((_DWORD *)this + 42) == 3 )
          *(_DWORD *)(*((_QWORD *)this + 2) + 6024LL) = 1;
        Dump = CProcessDump::AddDumpFileToReport((CProcessDump *)this, v40, v12, v11);
        CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v34);
      }
      if ( Dump < 0 )
      {
        CProcessDump::LogTrace((CProcessDump *)this, 0, L"Dump could not be added to report: %08X.", (unsigned int)Dump);
        goto LABEL_65;
      }
      *((_DWORD *)this + 1) = 1;
    }
    Dump = 0;
LABEL_65:
    CFileByteStream::Close((CFileByteStream *)&v31);
    if ( Dump >= 0 )
    {
      if ( v40[0] && v33 )
      {
        v27 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v33, v40);
        CProcessDump::LogTrace(
          (CProcessDump *)this,
          0,
          L"Dump path could not be copied: %08X.",
          v27 == 0 ? 0x8007000E : 0);
      }
    }
    else if ( v40[0] )
    {
      v26 = UtilDeleteFilePath(v40);
      v23 = retaddr;
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB10,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\processdump.cpp",
          (const char *)(unsigned int)v26,
          wMonth);
    }
    if ( (unsigned __int8)IsXerProgressCallbackPresent(v23, v22, v24, v25) )
      XerProgressCallback(2, Dump);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v30);
  CFileByteStream::~CFileByteStream((CFileByteStream *)&v31);
  return (unsigned int)Dump;
}

```

## disassembly

```asm
0x18007f868  mov     [rsp-8+arg_18], rbx
0x18007f86d  push    rbp
0x18007f86e  push    rsi
0x18007f86f  push    rdi
0x18007f870  push    r12
0x18007f872  push    r13
0x18007f874  push    r14
0x18007f876  push    r15
0x18007f878  lea     rbp, [rsp-430h]
0x18007f880  sub     rsp, 530h
0x18007f887  mov     rax, cs:__security_cookie
0x18007f88e  xor     rax, rsp
0x18007f891  mov     [rbp+460h+var_40], rax
0x18007f898  mov     [rsp+560h+var_4E8], r8
0x18007f89d  mov     r15d, edx
0x18007f8a0  mov     rdi, rcx
0x18007f8a3  lea     rax, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x18007f8aa  mov     [rsp+560h+var_4F8], rax
0x18007f8af  xor     r14d, r14d
0x18007f8b2  mov     [rsp+560h+var_4F0], r14
0x18007f8b7  mov     [rsp+560h+var_500], r14
0x18007f8bc  xorps   xmm0, xmm0
0x18007f8bf  movups  xmmword ptr [rbp+460h+SystemTime.wYear], xmm0
0x18007f8c3  cmp     [rcx], r14d
0x18007f8c6  jnz     short loc_18007F8CD
0x18007f8c8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007f8cd  cmp     [rdi+70h], r14
0x18007f8d1  jnz     short loc_18007F8E1
0x18007f8d3  cmp     [rdi+300h], r14
0x18007f8da  jnz     short loc_18007F8E1
0x18007f8dc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007f8e1  cmp     [rdi+78h], r14d
0x18007f8e5  jnz     short loc_18007F8EC
0x18007f8e7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007f8ec  cmp     [rdi+4], r14d
0x18007f8f0  jz      short loc_18007F8F7
0x18007f8f2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007f8f7  lea     rax, WPP_GLOBAL_Control
0x18007f8fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f905  cmp     rcx, rax
0x18007f908  jz      short loc_18007F928
0x18007f90a  test    byte ptr [rcx+1Ch], 4
0x18007f90e  jz      short loc_18007F928
0x18007f910  mov     edx, 0Ch
0x18007f915  mov     r9d, r15d
0x18007f918  lea     r8, WPP_4909ce9a3d833966bf1277dfd490a226_Traceguids
0x18007f91f  mov     rcx, [rcx+10h]
0x18007f923  call    WPP_SF_d
0x18007f928  cmp     dword ptr [rdi+0A8h], 3
0x18007f92f  jnz     loc_18007F9C0
0x18007f935  test    byte ptr [rdi+7Ch], 1
0x18007f939  jnz     short loc_18007F9A2
0x18007f93b  lea     rcx, [rbp+460h+var_4E0]; this
0x18007f93f  call    ??0CRegSetting@@QEAA@XZ; CRegSetting::CRegSetting(void)
0x18007f944  mov     [rsp+560h+var_540], r14
0x18007f949  lea     r9, aNoheap; "NoHeap"
0x18007f950  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\Windows E"...
0x18007f957  xor     edx, edx
0x18007f959  lea     rcx, [rbp+460h+var_4E0]
0x18007f95d  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x18007f962  test    eax, eax
0x18007f964  js      short loc_18007F992
0x18007f966  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18007f96d  mov     r8d, 100h; unsigned int
0x18007f973  lea     rcx, [rbp+460h+var_4E0]; this
0x18007f977  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x18007f97c  test    eax, eax
0x18007f97e  js      short loc_18007F992
0x18007f980  lea     rcx, [rbp+460h+var_4E0]; this
0x18007f984  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18007f989  test    eax, eax
0x18007f98b  mov     ebx, 1
0x18007f990  jnz     short loc_18007F995
0x18007f992  mov     ebx, r14d
0x18007f995  lea     rcx, [rbp+460h+var_4E0]; this
0x18007f999  call    ??1CRegSetting@@QEAA@XZ; CRegSetting::~CRegSetting(void)
0x18007f99e  test    ebx, ebx
0x18007f9a0  jz      short loc_18007F9C0
0x18007f9a2  lea     r8, aHeapdumpGenera; "Heapdump generation disabled by NoHeap "...
0x18007f9a9  mov     edx, 1; unsigned int
0x18007f9ae  mov     rcx, rdi; this
0x18007f9b1  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x18007f9b6  mov     ebx, 8007139Fh
0x18007f9bb  jmp     loc_18007FD61
0x18007f9c0  call    IsXerProgressCallbackPresent
0x18007f9c5  test    al, al
0x18007f9c7  jz      short loc_18007F9DB
0x18007f9c9  movsxd  rdx, dword ptr [rdi+0A8h]
0x18007f9d0  mov     ecx, 1
0x18007f9d5  call    cs:__imp_XerProgressCallback
0x18007f9db  mov     r12d, r14d
0x18007f9de  cmp     r12d, 2
0x18007f9e2  jge     loc_18007FCCA
0x18007f9e8  test    r15b, 10h
0x18007f9ec  jnz     short loc_18007F9F7
0x18007f9ee  cmp     [rdi+0B0h], r14d
0x18007f9f5  jge     short loc_18007F9FD
0x18007f9f7  mov     r14d, 1
0x18007f9fd  cmp     r12d, 1
0x18007fa01  jnz     short loc_18007FA2E
0x18007fa03  mov     eax, r15d
0x18007fa06  and     al, 60h
0x18007fa08  xor     r14d, r14d
0x18007fa0b  cmp     al, 40h ; '@'
0x18007fa0d  jnz     loc_18007FCCA
0x18007fa13  cmp     [rdi+300h], r14
0x18007fa1a  jz      loc_18007FCCA
0x18007fa20  mov     esi, r15d
0x18007fa23  and     esi, 0FFFFFFAFh
0x18007fa26  or      esi, 20h
0x18007fa29  mov     r13d, r12d
0x18007fa2c  jmp     short loc_18007FA34
0x18007fa2e  xor     r13d, r13d
0x18007fa31  mov     esi, r15d
0x18007fa34  cmp     qword ptr [rdi+10h], 0
0x18007fa39  jz      short loc_18007FA56
0x18007fa3b  mov     edx, 104h
0x18007fa40  lea     rcx, [rbp+460h+var_250]
0x18007fa47  call    WerpGetPathOfWERTempDirectory
0x18007fa4c  mov     ebx, eax
0x18007fa4e  test    eax, eax
0x18007fa50  js      loc_18007FC69
0x18007fa56  cmp     dword ptr [rdi+54h], 0
0x18007fa5a  jnz     short loc_18007FA65
0x18007fa5c  test    r15b, r15b
0x18007fa5f  js      short loc_18007FA65
0x18007fa61  xor     eax, eax
0x18007fa63  jmp     short loc_18007FA6A
0x18007fa65  mov     eax, 1
0x18007fa6a  mov     [rdi+54h], eax
0x18007fa6d  test    r14d, r14d
0x18007fa70  jnz     loc_18007FC41
0x18007fa76  xorps   xmm0, xmm0
0x18007fa79  xor     eax, eax
0x18007fa7b  movups  xmmword ptr [rbp+460h+var_4E0.nLength], xmm0
0x18007fa7f  mov     qword ptr [rbp+460h+var_4E0.bInheritHandle], rax
0x18007fa83  xorps   xmm1, xmm1
0x18007fa86  movups  [rbp+460h+var_4C8], xmm1
0x18007fa8a  movups  [rbp+460h+var_4B8], xmm1
0x18007fa8e  mov     [rbp+460h+var_4A8], rax
0x18007fa92  movdqa  [rbp+460h+var_4A0], xmm0
0x18007fa97  mov     [rbp+460h+var_4E0.nLength], 18h
0x18007fa9e  xor     edx, edx; bool
0x18007faa0  lea     rcx, [rbp+460h+var_4E0]; this
0x18007faa4  call    ?GetNewRestrictedFileOrDirectorySecurityAttributes@CSecurityAttributes@@SAJAEAV1@_N@Z; CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(CSecurityAttributes &,bool)
0x18007faa9  mov     ebx, eax
0x18007faab  xor     r14d, r14d
0x18007faae  test    eax, eax
0x18007fab0  js      loc_18007FC94
0x18007fab6  call    IsXerTransportEventUploadCompletePresent
0x18007fabb  test    al, al
0x18007fabd  jz      short loc_18007FAD5
0x18007fabf  mov     rcx, [rdi+10h]
0x18007fac3  add     rcx, 0C9E0h; this
0x18007faca  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x18007facf  test    eax, eax
0x18007fad1  mov     al, 1
0x18007fad3  jnz     short loc_18007FAD8
0x18007fad5  mov     al, r14b
0x18007fad8  mov     ecx, [rdi+0A8h]; enum _WER_DUMP_TYPE
0x18007fade  cmp     ecx, 3
0x18007fae1  jnz     loc_18007FB9D
0x18007fae7  test    al, al
0x18007fae9  jz      loc_18007FB9D
0x18007faef  cmp     [rdi+54h], r14d
0x18007faf3  jz      loc_18007FB9D
0x18007faf9  lea     rcx, [rbp+460h+SystemTime]; lpSystemTime
0x18007fafd  call    cs:__imp_GetSystemTime
0x18007fb03  movzx   eax, [rbp+460h+SystemTime.wMilliseconds]
0x18007fb07  movzx   ecx, [rbp+460h+SystemTime.wSecond]
0x18007fb0b  movzx   edx, [rbp+460h+SystemTime.wMinute]
0x18007fb0f  movzx   r8d, [rbp+460h+SystemTime.wHour]
0x18007fb14  movzx   r10d, [rbp+460h+SystemTime.wDay]
0x18007fb19  movzx   r11d, [rbp+460h+SystemTime.wDayOfWeek]
0x18007fb1e  movzx   ebx, [rbp+460h+SystemTime.wMonth]
0x18007fb22  movzx   r9d, [rbp+460h+SystemTime.wYear]
0x18007fb27  mov     [rsp+560h+var_510], eax
0x18007fb2b  mov     [rsp+560h+var_518], ecx
0x18007fb2f  mov     [rsp+560h+var_520], edx
0x18007fb33  mov     dword ptr [rsp+560h+var_528], r8d
0x18007fb38  mov     [rsp+560h+var_530], r10d
0x18007fb3d  mov     [rsp+560h+var_538], r11d
0x18007fb42  mov     dword ptr [rsp+560h+var_540], ebx
0x18007fb46  lea     r8, aWerCrashdumpsW; "\\\\?\\Wer:\\CrashDumps\\WER.%u%u%u%u%u"...
0x18007fb4d  mov     edx, 104h; unsigned __int64
0x18007fb52  lea     rcx, [rbp+460h+var_460]; wchar_t *
0x18007fb56  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18007fb5b  mov     ebx, eax
0x18007fb5d  test    eax, eax
0x18007fb5f  js      loc_18007FC82
0x18007fb65  mov     [rsp+560h+var_528], r14; void *
0x18007fb6a  mov     [rsp+560h+var_530], 20000080h; unsigned int
0x18007fb72  mov     ecx, 1
0x18007fb77  mov     [rsp+560h+var_538], ecx; unsigned int
0x18007fb7b  lea     rax, [rbp+460h+var_4E0]
0x18007fb7f  mov     [rsp+560h+var_540], rax; struct _SECURITY_ATTRIBUTES *
0x18007fb84  mov     r9d, ecx; unsigned int
0x18007fb87  mov     r8d, 0C0000000h; unsigned int
0x18007fb8d  lea     rdx, [rbp+460h+var_460]; wchar_t *
0x18007fb91  lea     rcx, [rsp+560h+var_4F8]; this
0x18007fb96  call    ?OpenFile@CFileByteStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CFileByteStream::OpenFile(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18007fb9b  jmp     short loc_18007FBEC
0x18007fb9d  mov     edx, r13d; int
0x18007fba0  call    ?MapDumpFileExtension@CProcessDump@@SAPEB_WW4_WER_DUMP_TYPE@@H@Z; CProcessDump::MapDumpFileExtension(_WER_DUMP_TYPE,int)
0x18007fba5  mov     dword ptr [rsp+560h+var_528], r14d
0x18007fbaa  mov     [rsp+560h+var_530], 1
0x18007fbb2  lea     rcx, [rbp+460h+var_4E0]
0x18007fbb6  mov     qword ptr [rsp+560h+var_538], rcx
0x18007fbbb  lea     r9, [rbp+460h+var_460]
0x18007fbbf  mov     r8, rax
0x18007fbc2  lea     rdx, [rbp+460h+var_250]
0x18007fbc9  lea     rcx, [rsp+560h+var_500]
0x18007fbce  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007fbd3  mov     ebx, eax
0x18007fbd5  test    eax, eax
0x18007fbd7  js      loc_18007FC8B
0x18007fbdd  lea     rdx, [rsp+560h+var_500]
0x18007fbe2  lea     rcx, [rsp+560h+var_4F0]
0x18007fbe7  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x18007fbec  mov     r9, [rsp+560h+var_4F0]; void *
0x18007fbf1  mov     r8d, esi; unsigned int
0x18007fbf4  lea     rdx, [rsp+560h+var_4F8]; struct IWerByteStream *
0x18007fbf9  mov     rcx, rdi; this
0x18007fbfc  call    ?GenerateDump@CProcessDump@@AEAAJPEAUIWerByteStream@@KPEAX@Z; CProcessDump::GenerateDump(IWerByteStream *,ulong,void *)
0x18007fc01  mov     ebx, eax
0x18007fc03  test    eax, eax
0x18007fc05  js      loc_18007FCA9
0x18007fc0b  cmp     dword ptr [rdi+0A8h], 3
0x18007fc12  jnz     short loc_18007FC22
0x18007fc14  mov     rax, [rdi+10h]
0x18007fc18  mov     dword ptr [rax+1788h], 1
0x18007fc22  mov     r9d, esi; unsigned int
0x18007fc25  mov     r8d, r13d; int
0x18007fc28  lea     rdx, [rbp+460h+var_460]; wchar_t *
0x18007fc2c  mov     rcx, rdi; this
0x18007fc2f  call    ?AddDumpFileToReport@CProcessDump@@AEAAJPEB_WHK@Z; CProcessDump::AddDumpFileToReport(wchar_t const *,int,ulong)
0x18007fc34  mov     ebx, eax
0x18007fc36  lea     rcx, [rbp+460h+var_4E0]; this
0x18007fc3a  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18007fc3f  jmp     short loc_18007FC56
0x18007fc41  mov     r9d, esi; unsigned int
0x18007fc44  mov     r8d, r13d; int
0x18007fc47  xor     edx, edx; wchar_t *
0x18007fc49  mov     rcx, rdi; this
0x18007fc4c  call    ?AddDumpFileToReport@CProcessDump@@AEAAJPEB_WHK@Z; CProcessDump::AddDumpFileToReport(wchar_t const *,int,ulong)
0x18007fc51  mov     ebx, eax
0x18007fc53  xor     r14d, r14d
0x18007fc56  test    ebx, ebx
0x18007fc58  js      short loc_18007FCB4
0x18007fc5a  mov     dword ptr [rdi+4], 1
0x18007fc61  inc     r12d
0x18007fc64  jmp     loc_18007F9DE
0x18007fc69  mov     r9d, eax
0x18007fc6c  lea     r8, aDumpFileCouldN; "Dump file could not be created: WerpGet"...
0x18007fc73  xor     edx, edx; unsigned int
0x18007fc75  mov     rcx, rdi; this
0x18007fc78  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x18007fc7d  xor     r14d, r14d
0x18007fc80  jmp     short loc_18007FCCD
0x18007fc82  lea     r8, aCouldnTWriteOu; "Couldn't write out the GameCore specifi"...
0x18007fc89  jmp     short loc_18007FC9B
0x18007fc8b  lea     r8, aDumpFileCouldN_2; "Dump file could not be created: UtilGet"...
0x18007fc92  jmp     short loc_18007FC9B
0x18007fc94  lea     r8, aDumpFileCouldN_1; "Dump file could not be created: Failed "...
0x18007fc9b  mov     r9d, eax
0x18007fc9e  xor     edx, edx; unsigned int
0x18007fca0  mov     rcx, rdi; this
0x18007fca3  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x18007fca8  nop
0x18007fca9  lea     rcx, [rbp+460h+var_4E0]; this
0x18007fcad  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x18007fcb2  jmp     short loc_18007FCCD
0x18007fcb4  mov     r9d, ebx
0x18007fcb7  lea     r8, aDumpCouldNotBe_0; "Dump could not be added to report: %08X"...
0x18007fcbe  xor     edx, edx; unsigned int
0x18007fcc0  mov     rcx, rdi; this
0x18007fcc3  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x18007fcc8  jmp     short loc_18007FCCD
0x18007fcca  mov     ebx, r14d
0x18007fccd  lea     rcx, [rsp+560h+var_4F8]; this
0x18007fcd2  call    ?Close@CFileByteStream@@UEAAXXZ; CFileByteStream::Close(void)
0x18007fcd7  test    ebx, ebx
0x18007fcd9  jns     short loc_18007FD0C
0x18007fcdb  cmp     [rbp+460h+var_460], r14w
0x18007fce0  jz      short loc_18007FD49
0x18007fce2  lea     rcx, [rbp+460h+var_460]; wchar_t *
0x18007fce6  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x18007fceb  mov     rcx, [rbp+468h]; this
0x18007fcf2  test    eax, eax
0x18007fcf4  jns     short loc_18007FD49
0x18007fcf6  mov     r9d, eax; char *
0x18007fcf9  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werdl"...
0x18007fd00  mov     edx, 0B10h; void *
0x18007fd05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007fd0a  jmp     short loc_18007FD49
0x18007fd0c  cmp     [rbp+460h+var_460], r14w
0x18007fd11  jz      short loc_18007FD49
0x18007fd13  mov     rsi, [rsp+560h+var_4E8]
0x18007fd18  test    rsi, rsi
0x18007fd1b  jz      short loc_18007FD49
  ... truncated ...
```
