# CProcessDump::AttachDumpToReport(ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x180083350`
- end: `0x180083838`
- name: `?AttachDumpToReport@CProcessDump@@QEAAJKPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1256`
- prototype: `__int64 __fastcall(CProcessDump *this)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800380d4`
- `0x180038404`

## callees

- `0x180007f74`
- `0x180007fa0`
- `0x180007fd8`
- `0x180008298`
- `0x18000ad98`
- `0x18000da00`
- `0x18001e0a8`
- `0x18001e658`
- `0x180020680`
- `0x180028760`
- `0x1800318c8`
- `0x18003be90`
- `0x18003de9c`
- `0x18003f9a0`
- `0x180040bfc`
- `0x180046150`
- `0x180053300`
- `0x18005446c`
- `0x180054514`
- `0x180083038`
- `0x180083350`
- `0x180083840`
- `0x1800857c4`
- `0x1800857f0`
- `0x1800a96e4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180083585`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180083585`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180083459`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x1800837e9`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180083459`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x1800837e9`

## string_xrefs

- `0x1800836fb`: `Dump file could not be created: WerpGetPathOfWERTempDirectory %08X.`
- `0x180083723`: `Dump file could not be created: Failed to produce security attributes %08X.`
- `0x180083711`: `Couldn't write out the GameCore specific heap dump file path %08X.`
- `0x18008371a`: `Dump file could not be created: UtilGetTempFile %08X.`
- `0x180083788`: `onecore\windows\feedback\core\werdll\lib\processdump.cpp`
- `0x1800837c7`: `Dump path could not be copied: %08X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProcessDump::AttachDumpToReport(enum _WER_DUMP_TYPE *this, __int64 a2, void *a3)
{
  unsigned int v3; // r15d
  int v5; // r14d
  int Dump; // ebx
  int i; // r12d
  unsigned int v8; // esi
  int v9; // r13d
  int PathOfWERTempDirectory; // eax
  BOOL v11; // eax
  int NewRestrictedFileOrDirectorySecurityAttributes; // eax
  bool v13; // zf
  char v14; // al
  enum _WER_DUMP_TYPE v15; // ecx
  int v16; // eax
  const size_t *v17; // rax
  int TempFile; // eax
  wil::details::in1diag3 *v19; // rcx
  int v20; // eax
  char v21; // al
  struct _SECURITY_ATTRIBUTES *v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  void **v25; // [rsp+68h] [rbp-98h] BYREF
  void *v26; // [rsp+70h] [rbp-90h] BYREF
  void *v27; // [rsp+78h] [rbp-88h]
  struct _SECURITY_ATTRIBUTES v28; // [rsp+80h] [rbp-80h] BYREF
  __int128 v29; // [rsp+98h] [rbp-68h]
  __int128 v30; // [rsp+A8h] [rbp-58h]
  __int64 v31; // [rsp+B8h] [rbp-48h]
  __int128 v32; // [rsp+C0h] [rbp-40h]
  struct _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t v34[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR v35[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+448h]

  v27 = a3;
  v3 = a2;
  v25 = &CFileByteStream::`vftable';
  v5 = 0;
  v26 = 0;
  v24 = 0;
  SystemTime = 0;
  if ( *this == WerDumpTypeNone )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( !*((_QWORD *)this + 14) && !*((_QWORD *)this + 96) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( !*((_DWORD *)this + 30) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( *((_DWORD *)this + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4909ce9a3d833966bf1277dfd490a226_Traceguids, v3);
  if ( *((_DWORD *)this + 42) == 3 && ((this[31] & 1) != 0 || (unsigned int)UtilDebugNoHeap()) )
  {
    CProcessDump::LogTrace((CProcessDump *)this, 1u, L"Heapdump generation disabled by NoHeap flag.");
    Dump = -2147019873;
  }
  else
  {
    if ( (unsigned __int8)((__int64 (*)(void))IsXerProgressCallbackPresent)() )
      XerProgressCallback(1);
    for ( i = 0; i < 2; ++i )
    {
      if ( (v3 & 0x10) != 0 || *((int *)this + 44) < 0 )
        v5 = 1;
      if ( i == 1 )
      {
        v5 = 0;
        if ( (v3 & 0x60) != 0x40 || !*((_QWORD *)this + 96) )
          break;
        v8 = v3 & 0xFFFFFF8F | 0x20;
        v9 = 1;
      }
      else
      {
        v9 = 0;
        v8 = v3;
      }
      if ( *((_QWORD *)this + 2) )
      {
        PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v35, 260);
        Dump = PathOfWERTempDirectory;
        if ( PathOfWERTempDirectory < 0 )
        {
          CProcessDump::LogTrace(
            (CProcessDump *)this,
            0,
            L"Dump file could not be created: WerpGetPathOfWERTempDirectory %08X.",
            (unsigned int)PathOfWERTempDirectory);
          goto LABEL_61;
        }
      }
      v11 = *((_DWORD *)this + 21) || (v3 & 0x80u) != 0;
      *((_DWORD *)this + 21) = v11;
      if ( v5 )
      {
        Dump = CProcessDump::AddDumpFileToReport((CProcessDump *)this, 0, v9, v8);
        v5 = 0;
      }
      else
      {
        memset(&v28, 0, sizeof(v28));
        v29 = 0;
        v30 = 0;
        v31 = 0;
        v32 = 0;
        v28.nLength = 24;
        NewRestrictedFileOrDirectorySecurityAttributes = CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(
                                                           (struct CSecurityAttributes *)&v28,
                                                           0);
        Dump = NewRestrictedFileOrDirectorySecurityAttributes;
        v5 = 0;
        if ( NewRestrictedFileOrDirectorySecurityAttributes < 0 )
        {
          CProcessDump::LogTrace(
            (CProcessDump *)this,
            0,
            L"Dump file could not be created: Failed to produce security attributes %08X.",
            (unsigned int)NewRestrictedFileOrDirectorySecurityAttributes);
          goto LABEL_58;
        }
        if ( !(unsigned __int8)IsXerTransportEventUploadCompletePresent()
          || (v13 = CRegSetting::GetDwordData((CRegSetting *)(*((_QWORD *)this + 2) + 51680LL)) == 0, v14 = 1, v13) )
        {
          v14 = 0;
        }
        v15 = *((_DWORD *)this + 42);
        if ( v15 == WerDumpTypeHeapDump && v14 && *((_DWORD *)this + 21) )
        {
          GetSystemTime(&SystemTime);
          LODWORD(v23) = SystemTime.wMonth;
          v16 = StringCchPrintfW(
                  v34,
                  0x104u,
                  L"\\\\?\\Wer:\\CrashDumps\\WER.%u%u%u%u%u%u%u%u.memory.protected.hdmp",
                  SystemTime.wYear);
          Dump = v16;
          if ( v16 < 0 )
          {
            CProcessDump::LogTrace(
              (CProcessDump *)this,
              0,
              L"Couldn't write out the GameCore specific heap dump file path %08X.",
              (unsigned int)v16);
LABEL_58:
            CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v28);
            goto LABEL_61;
          }
          CFileByteStream::OpenFile((CFileByteStream *)&v25, v34, 0xC0000000, 1u, &v28, 1u, 0x20000080u, 0);
        }
        else
        {
          v17 = (const size_t *)CProcessDump::MapDumpFileExtension(v15, v9);
          TempFile = UtilGetTempFile((__int64)&v24, v35, v17, v34, (__int64)v23, &v28, 1u, 0);
          Dump = TempFile;
          if ( TempFile < 0 )
          {
            CProcessDump::LogTrace(
              (CProcessDump *)this,
              0,
              L"Dump file could not be created: UtilGetTempFile %08X.",
              (unsigned int)TempFile);
            goto LABEL_58;
          }
          tlx::unique_any<tlx::file_handle_traits>::operator=(&v26, &v24);
        }
        Dump = CProcessDump::GenerateDump((CProcessDump *)this, (struct IWerByteStream *)&v25, v8, v26);
        if ( Dump < 0 )
          goto LABEL_58;
        if ( *((_DWORD *)this + 42) == 3 )
          *(_DWORD *)(*((_QWORD *)this + 2) + 6024LL) = 1;
        Dump = CProcessDump::AddDumpFileToReport((CProcessDump *)this, v34, v9, v8);
        CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&v28);
      }
      if ( Dump < 0 )
      {
        CProcessDump::LogTrace((CProcessDump *)this, 0, L"Dump could not be added to report: %08X.", (unsigned int)Dump);
        goto LABEL_61;
      }
      *((_DWORD *)this + 1) = 1;
    }
    Dump = 0;
LABEL_61:
    CFileByteStream::Close((CFileByteStream *)&v25);
    if ( Dump >= 0 )
    {
      if ( v34[0] && v27 )
      {
        v21 = utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v27, v34);
        CProcessDump::LogTrace(
          (CProcessDump *)this,
          0,
          L"Dump path could not be copied: %08X.",
          v21 == 0 ? 0x8007000E : 0);
      }
    }
    else if ( v34[0] )
    {
      v20 = UtilDeleteFilePath(v34);
      v19 = retaddr;
      if ( v20 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB10,
          (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\processdump.cpp",
          (const char *)(unsigned int)v20,
          (int)v23);
    }
    if ( (unsigned __int8)IsXerProgressCallbackPresent(v19) )
      XerProgressCallback(2);
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v24);
  CFileByteStream::~CFileByteStream((CFileByteStream *)&v25);
  return (unsigned int)Dump;
}

```

## disassembly

```asm
0x180083350  mov     [rsp-8+arg_18], rbx
0x180083355  push    rbp
0x180083356  push    rsi
0x180083357  push    rdi
0x180083358  push    r12
0x18008335a  push    r13
0x18008335c  push    r14
0x18008335e  push    r15
0x180083360  lea     rbp, [rsp-410h]
0x180083368  sub     rsp, 510h
0x18008336f  mov     rax, cs:__security_cookie
0x180083376  xor     rax, rsp
0x180083379  mov     [rbp+440h+var_40], rax
0x180083380  mov     [rsp+540h+var_4C8], r8
0x180083385  mov     r15d, edx
0x180083388  mov     rdi, rcx
0x18008338b  lea     rax, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x180083392  mov     [rsp+540h+var_4D8], rax
0x180083397  xor     r14d, r14d
0x18008339a  mov     [rsp+540h+var_4D0], r14
0x18008339f  mov     [rsp+540h+var_4E0], r14
0x1800833a4  xorps   xmm0, xmm0
0x1800833a7  movups  xmmword ptr [rbp+440h+SystemTime.wYear], xmm0
0x1800833ab  cmp     [rcx], r14d
0x1800833ae  jnz     short loc_1800833B5
0x1800833b0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800833b5  cmp     [rdi+70h], r14
0x1800833b9  jnz     short loc_1800833C9
0x1800833bb  cmp     [rdi+300h], r14
0x1800833c2  jnz     short loc_1800833C9
0x1800833c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800833c9  cmp     [rdi+78h], r14d
0x1800833cd  jnz     short loc_1800833D4
0x1800833cf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800833d4  cmp     [rdi+4], r14d
0x1800833d8  jz      short loc_1800833DF
0x1800833da  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800833df  lea     rax, WPP_GLOBAL_Control
0x1800833e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800833ed  cmp     rcx, rax
0x1800833f0  jz      short loc_180083410
0x1800833f2  test    byte ptr [rcx+1Ch], 4
0x1800833f6  jz      short loc_180083410
0x1800833f8  mov     edx, 0Ch
0x1800833fd  mov     r9d, r15d
0x180083400  lea     r8, WPP_4909ce9a3d833966bf1277dfd490a226_Traceguids
0x180083407  mov     rcx, [rcx+10h]
0x18008340b  call    WPP_SF_d
0x180083410  mov     ebx, 1
0x180083415  cmp     dword ptr [rdi+0A8h], 3
0x18008341c  jnz     short loc_180083447
0x18008341e  test    [rdi+7Ch], bl
0x180083421  jnz     short loc_18008342C
0x180083423  call    ?UtilDebugNoHeap@@YAHXZ; UtilDebugNoHeap(void)
0x180083428  test    eax, eax
0x18008342a  jz      short loc_180083447
0x18008342c  lea     r8, aHeapdumpGenera; "Heapdump generation disabled by NoHeap "...
0x180083433  mov     edx, ebx; unsigned int
0x180083435  mov     rcx, rdi; this
0x180083438  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x18008343d  mov     ebx, 8007139Fh
0x180083442  jmp     loc_1800837F6
0x180083447  call    IsXerProgressCallbackPresent
0x18008344c  test    al, al
0x18008344e  jz      short loc_180083465
0x180083450  movsxd  rdx, dword ptr [rdi+0A8h]
0x180083457  mov     ecx, ebx
0x180083459  call    cs:__imp_XerProgressCallback
0x180083460  nop     dword ptr [rax+rax+00h]
0x180083465  mov     r12d, r14d
0x180083468  cmp     r12d, 2
0x18008346c  jge     loc_180083759
0x180083472  test    r15b, 10h
0x180083476  jnz     short loc_180083481
0x180083478  cmp     [rdi+0B0h], r14d
0x18008347f  jge     short loc_180083484
0x180083481  mov     r14d, ebx
0x180083484  cmp     r12d, ebx
0x180083487  jnz     short loc_1800834B4
0x180083489  mov     eax, r15d
0x18008348c  and     al, 60h
0x18008348e  xor     r14d, r14d
0x180083491  cmp     al, 40h ; '@'
0x180083493  jnz     loc_180083759
0x180083499  cmp     [rdi+300h], r14
0x1800834a0  jz      loc_180083759
0x1800834a6  mov     esi, r15d
0x1800834a9  and     esi, 0FFFFFFAFh
0x1800834ac  or      esi, 20h
0x1800834af  mov     r13d, ebx
0x1800834b2  jmp     short loc_1800834BA
0x1800834b4  xor     r13d, r13d
0x1800834b7  mov     esi, r15d
0x1800834ba  cmp     qword ptr [rdi+10h], 0
0x1800834bf  jz      short loc_1800834E1
0x1800834c1  mov     edx, 104h
0x1800834c6  lea     rcx, [rbp+440h+var_250]
0x1800834cd  call    WerpGetPathOfWERTempDirectory
0x1800834d2  mov     ebx, eax
0x1800834d4  test    eax, eax
0x1800834d6  js      loc_1800836F8
0x1800834dc  mov     ebx, 1
0x1800834e1  cmp     dword ptr [rdi+54h], 0
0x1800834e5  jnz     short loc_1800834F0
0x1800834e7  test    r15b, r15b
0x1800834ea  js      short loc_1800834F0
0x1800834ec  xor     eax, eax
0x1800834ee  jmp     short loc_1800834F2
0x1800834f0  mov     eax, ebx
0x1800834f2  mov     [rdi+54h], eax
0x1800834f5  test    r14d, r14d
0x1800834f8  jnz     loc_1800836CF
0x1800834fe  xorps   xmm0, xmm0
0x180083501  xor     eax, eax
0x180083503  movups  xmmword ptr [rbp+440h+var_4C0.nLength], xmm0
0x180083507  mov     qword ptr [rbp+440h+var_4C0.bInheritHandle], rax
0x18008350b  xorps   xmm1, xmm1
0x18008350e  movups  [rbp+440h+var_4A8], xmm1
0x180083512  movups  [rbp+440h+var_498], xmm1
0x180083516  mov     [rbp+440h+var_488], rax
0x18008351a  movdqa  [rbp+440h+var_480], xmm0
0x18008351f  mov     [rbp+440h+var_4C0.nLength], 18h
0x180083526  xor     edx, edx; bool
0x180083528  lea     rcx, [rbp+440h+var_4C0]; this
0x18008352c  call    ?GetNewRestrictedFileOrDirectorySecurityAttributes@CSecurityAttributes@@SAJAEAV1@_N@Z; CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(CSecurityAttributes &,bool)
0x180083531  mov     ebx, eax
0x180083533  xor     r14d, r14d
0x180083536  test    eax, eax
0x180083538  js      loc_180083723
0x18008353e  call    IsXerTransportEventUploadCompletePresent
0x180083543  test    al, al
0x180083545  jz      short loc_18008355D
0x180083547  mov     rcx, [rdi+10h]
0x18008354b  add     rcx, 0C9E0h; this
0x180083552  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x180083557  test    eax, eax
0x180083559  mov     al, 1
0x18008355b  jnz     short loc_180083560
0x18008355d  mov     al, r14b
0x180083560  mov     ecx, [rdi+0A8h]; enum _WER_DUMP_TYPE
0x180083566  cmp     ecx, 3
0x180083569  jnz     loc_18008362B
0x18008356f  test    al, al
0x180083571  jz      loc_18008362B
0x180083577  cmp     [rdi+54h], r14d
0x18008357b  jz      loc_18008362B
0x180083581  lea     rcx, [rbp+440h+SystemTime]; lpSystemTime
0x180083585  call    cs:__imp_GetSystemTime
0x18008358c  nop     dword ptr [rax+rax+00h]
0x180083591  movzx   eax, [rbp+440h+SystemTime.wMilliseconds]
0x180083595  movzx   ecx, [rbp+440h+SystemTime.wSecond]
0x180083599  movzx   edx, [rbp+440h+SystemTime.wMinute]
0x18008359d  movzx   r8d, [rbp+440h+SystemTime.wHour]
0x1800835a2  movzx   r10d, [rbp+440h+SystemTime.wDay]
0x1800835a7  movzx   r11d, [rbp+440h+SystemTime.wDayOfWeek]
0x1800835ac  movzx   ebx, [rbp+440h+SystemTime.wMonth]
0x1800835b0  movzx   r9d, [rbp+440h+SystemTime.wYear]
0x1800835b5  mov     [rsp+540h+var_4F0], eax
0x1800835b9  mov     [rsp+540h+var_4F8], ecx
0x1800835bd  mov     [rsp+540h+var_500], edx
0x1800835c1  mov     dword ptr [rsp+540h+var_508], r8d
0x1800835c6  mov     [rsp+540h+var_510], r10d
0x1800835cb  mov     [rsp+540h+var_518], r11d
0x1800835d0  mov     dword ptr [rsp+540h+var_520], ebx
0x1800835d4  lea     r8, aWerCrashdumpsW; "\\\\?\\Wer:\\CrashDumps\\WER.%u%u%u%u%u"...
0x1800835db  mov     edx, 104h; unsigned __int64
0x1800835e0  lea     rcx, [rbp+440h+var_460]; wchar_t *
0x1800835e4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800835e9  mov     ebx, eax
0x1800835eb  test    eax, eax
0x1800835ed  js      loc_180083711
0x1800835f3  mov     [rsp+540h+var_508], r14; void *
0x1800835f8  mov     [rsp+540h+var_510], 20000080h; unsigned int
0x180083600  mov     ecx, 1
0x180083605  mov     [rsp+540h+var_518], ecx; unsigned int
0x180083609  lea     rax, [rbp+440h+var_4C0]
0x18008360d  mov     [rsp+540h+var_520], rax; struct _SECURITY_ATTRIBUTES *
0x180083612  mov     r9d, ecx; unsigned int
0x180083615  mov     r8d, 0C0000000h; unsigned int
0x18008361b  lea     rdx, [rbp+440h+var_460]; wchar_t *
0x18008361f  lea     rcx, [rsp+540h+var_4D8]; this
0x180083624  call    ?OpenFile@CFileByteStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; CFileByteStream::OpenFile(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x180083629  jmp     short loc_18008367A
0x18008362b  mov     edx, r13d; int
0x18008362e  call    ?MapDumpFileExtension@CProcessDump@@SAPEB_WW4_WER_DUMP_TYPE@@H@Z; CProcessDump::MapDumpFileExtension(_WER_DUMP_TYPE,int)
0x180083633  mov     dword ptr [rsp+540h+var_508], r14d
0x180083638  mov     [rsp+540h+var_510], 1
0x180083640  lea     rcx, [rbp+440h+var_4C0]
0x180083644  mov     qword ptr [rsp+540h+var_518], rcx
0x180083649  lea     r9, [rbp+440h+var_460]
0x18008364d  mov     r8, rax
0x180083650  lea     rdx, [rbp+440h+var_250]
0x180083657  lea     rcx, [rsp+540h+var_4E0]
0x18008365c  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180083661  mov     ebx, eax
0x180083663  test    eax, eax
0x180083665  js      loc_18008371A
0x18008366b  lea     rdx, [rsp+540h+var_4E0]
0x180083670  lea     rcx, [rsp+540h+var_4D0]
0x180083675  call    ??4?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::file_handle_traits>::operator=(tlx::unique_any<tlx::file_handle_traits> &&)
0x18008367a  mov     r9, [rsp+540h+var_4D0]; void *
0x18008367f  mov     r8d, esi; unsigned int
0x180083682  lea     rdx, [rsp+540h+var_4D8]; struct IWerByteStream *
0x180083687  mov     rcx, rdi; this
0x18008368a  call    ?GenerateDump@CProcessDump@@AEAAJPEAUIWerByteStream@@KPEAX@Z; CProcessDump::GenerateDump(IWerByteStream *,ulong,void *)
0x18008368f  mov     ebx, eax
0x180083691  test    eax, eax
0x180083693  js      loc_180083738
0x180083699  cmp     dword ptr [rdi+0A8h], 3
0x1800836a0  jnz     short loc_1800836B0
0x1800836a2  mov     rax, [rdi+10h]
0x1800836a6  mov     dword ptr [rax+1788h], 1
0x1800836b0  mov     r9d, esi; unsigned int
0x1800836b3  mov     r8d, r13d; int
0x1800836b6  lea     rdx, [rbp+440h+var_460]; wchar_t *
0x1800836ba  mov     rcx, rdi; this
0x1800836bd  call    ?AddDumpFileToReport@CProcessDump@@AEAAJPEB_WHK@Z; CProcessDump::AddDumpFileToReport(wchar_t const *,int,ulong)
0x1800836c2  mov     ebx, eax
0x1800836c4  lea     rcx, [rbp+440h+var_4C0]; this
0x1800836c8  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x1800836cd  jmp     short loc_1800836E4
0x1800836cf  mov     r9d, esi; unsigned int
0x1800836d2  mov     r8d, r13d; int
0x1800836d5  xor     edx, edx; wchar_t *
0x1800836d7  mov     rcx, rdi; this
0x1800836da  call    ?AddDumpFileToReport@CProcessDump@@AEAAJPEB_WHK@Z; CProcessDump::AddDumpFileToReport(wchar_t const *,int,ulong)
0x1800836df  mov     ebx, eax
0x1800836e1  xor     r14d, r14d
0x1800836e4  test    ebx, ebx
0x1800836e6  js      short loc_180083743
0x1800836e8  mov     ebx, 1
0x1800836ed  mov     [rdi+4], ebx
0x1800836f0  add     r12d, ebx
0x1800836f3  jmp     loc_180083468
0x1800836f8  mov     r9d, eax
0x1800836fb  lea     r8, aDumpFileCouldN; "Dump file could not be created: WerpGet"...
0x180083702  xor     edx, edx; unsigned int
0x180083704  mov     rcx, rdi; this
0x180083707  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x18008370c  xor     r14d, r14d
0x18008370f  jmp     short loc_18008375C
0x180083711  lea     r8, aCouldnTWriteOu; "Couldn't write out the GameCore specifi"...
0x180083718  jmp     short loc_18008372A
0x18008371a  lea     r8, aDumpFileCouldN_2; "Dump file could not be created: UtilGet"...
0x180083721  jmp     short loc_18008372A
0x180083723  lea     r8, aDumpFileCouldN_1; "Dump file could not be created: Failed "...
0x18008372a  mov     r9d, eax
0x18008372d  xor     edx, edx; unsigned int
0x18008372f  mov     rcx, rdi; this
0x180083732  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x180083737  nop
0x180083738  lea     rcx, [rbp+440h+var_4C0]; this
0x18008373c  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x180083741  jmp     short loc_18008375C
0x180083743  mov     r9d, ebx
0x180083746  lea     r8, aDumpCouldNotBe_0; "Dump could not be added to report: %08X"...
0x18008374d  xor     edx, edx; unsigned int
0x18008374f  mov     rcx, rdi; this
0x180083752  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x180083757  jmp     short loc_18008375C
0x180083759  mov     ebx, r14d
0x18008375c  lea     rcx, [rsp+540h+var_4D8]; this
0x180083761  call    ?Close@CFileByteStream@@UEAAXXZ; CFileByteStream::Close(void)
0x180083766  test    ebx, ebx
0x180083768  jns     short loc_18008379B
0x18008376a  cmp     [rbp+440h+var_460], r14w
0x18008376f  jz      short loc_1800837D8
0x180083771  lea     rcx, [rbp+440h+var_460]; wchar_t *
0x180083775  call    ?UtilDeleteFilePath@@YAJPEB_W@Z; UtilDeleteFilePath(wchar_t const *)
0x18008377a  mov     rcx, [rbp+448h]; this
0x180083781  test    eax, eax
0x180083783  jns     short loc_1800837D8
0x180083785  mov     r9d, eax; char *
0x180083788  lea     r8, aOnecoreWindows_10; "onecore\\windows\\feedback\\core\\werdl"...
0x18008378f  mov     edx, 0B10h; void *
0x180083794  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180083799  jmp     short loc_1800837D8
0x18008379b  cmp     [rbp+440h+var_460], r14w
0x1800837a0  jz      short loc_1800837D8
0x1800837a2  mov     rsi, [rsp+540h+var_4C8]
0x1800837a7  test    rsi, rsi
0x1800837aa  jz      short loc_1800837D8
0x1800837ac  lea     rdx, [rbp+440h+var_460]
0x1800837b0  mov     rcx, rsi
0x1800837b3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800837b8  neg     al
0x1800837ba  sbb     r9d, r9d
0x1800837bd  not     r9d
0x1800837c0  and     r9d, 8007000Eh
0x1800837c7  lea     r8, aDumpPathCouldN; "Dump path could not be copied: %08X."
0x1800837ce  xor     edx, edx; unsigned int
0x1800837d0  mov     rcx, rdi; this
0x1800837d3  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x1800837d8  call    IsXerProgressCallbackPresent
0x1800837dd  test    al, al
0x1800837df  jz      short loc_1800837F6
0x1800837e1  movsxd  rdx, ebx
0x1800837e4  mov     ecx, 2
0x1800837e9  call    cs:__imp_XerProgressCallback
0x1800837f0  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
