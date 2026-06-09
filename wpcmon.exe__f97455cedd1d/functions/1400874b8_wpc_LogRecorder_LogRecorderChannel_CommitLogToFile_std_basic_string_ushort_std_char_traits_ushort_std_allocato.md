# wpc::LogRecorder::LogRecorderChannel::CommitLogToFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1400874b8`
- end: `0x14008764a`
- name: `?CommitLogToFile@LogRecorderChannel@LogRecorder@wpc@@AEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400877a0`

## callees

- `0x140005530`
- `0x14000b744`
- `0x14000ccac`
- `0x14006803c`
- `0x140068dbc`
- `0x140084294`
- `0x140084318`
- `0x1400843fc`
- `0x140084ad0`
- `0x1400874b8`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x140087545`
- `KERNEL32!DeleteFileW` at `0x140087545`
- `KERNEL32!CompareFileTime` at `0x140087513`
- `KERNEL32!CompareFileTime` at `0x140087513`
- `KERNEL32!CloseHandle` at `0x1400875da`
- `KERNEL32!CloseHandle` at `0x1400875da`
- `KERNEL32!MoveFileW` at `0x140087567`
- `KERNEL32!MoveFileW` at `0x140087567`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall wpc::LogRecorder::LogRecorderChannel::CommitLogToFile(__int64 a1, _QWORD *a2)
{
  const FILETIME *v4; // rax
  const WCHAR *v5; // rcx
  const WCHAR *v6; // rdx
  const WCHAR *v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rdx
  HANDLE hObject; // [rsp+20h] [rbp-59h] BYREF
  FILETIME FileTime2; // [rsp+28h] [rbp-51h] BYREF
  int v13; // [rsp+30h] [rbp-49h]
  void **v14; // [rsp+38h] [rbp-41h] BYREF
  void **v15; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v16[16]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v17[16]; // [rsp+58h] [rbp-21h] BYREF
  _QWORD *v18; // [rsp+68h] [rbp-11h]
  LPCWSTR lpFileName[3]; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int64 v20; // [rsp+88h] [rbp+Fh]
  LPCWSTR lpExistingFileName[4]; // [rsp+90h] [rbp+17h] BYREF

  v18 = a2;
  DateTime::GetCurrent(&FileTime2);
  hObject = (HANDLE)12096000000000LL;
  v4 = (const FILETIME *)DateTime::operator+(a1 + 76, v17, &hObject);
  if ( CompareFileTime(v4, &FileTime2) < 0 )
  {
    std::wstring::wstring(lpFileName, a1 + 32);
    std::wstring::wstring(lpExistingFileName, a1);
    v5 = (const WCHAR *)lpFileName;
    if ( v20 > 7 )
      v5 = lpFileName[0];
    DeleteFileW(v5);
    v6 = (const WCHAR *)lpFileName;
    if ( v20 > 7 )
      v6 = lpFileName[0];
    v7 = (const WCHAR *)lpExistingFileName;
    if ( lpExistingFileName[3] > (LPCWSTR)7 )
      v7 = lpExistingFileName[0];
    MoveFileW(v7, v6);
    *(FILETIME *)(a1 + 76) = FileTime2;
    *(_DWORD *)(a1 + 84) = v13;
    std::wstring::~wstring(lpExistingFileName);
    std::wstring::~wstring(lpFileName);
  }
  v14 = &IO::OutputFile::`vftable'{for `OutputStream'};
  v15 = &IO::OutputFile::`vftable'{for `SeekableStream'};
  v8 = IO::File::Open(&hObject, a1, 1);
  std::shared_ptr<void>::shared_ptr<void>(v16, v8);
  if ( hObject && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  IO::OutputFile::Seek(&v15, 2);
  if ( a2[3] <= 7u )
    v9 = a2;
  else
    v9 = (_QWORD *)*a2;
  ((void (__fastcall *)(void ***, _QWORD *, __int64))v14[1])(&v14, v9, 2LL * a2[2]);
  IO::OutputFile::~OutputFile((IO::OutputFile *)&v14);
  return std::wstring::~wstring(a2);
}

```

## disassembly

```asm
0x1400874b8  mov     [rsp-8+arg_10], rbx
0x1400874bd  push    rbp
0x1400874be  push    rsi
0x1400874bf  push    rdi
0x1400874c0  lea     rbp, [rsp-47h]
0x1400874c5  sub     rsp, 0C0h
0x1400874cc  mov     rax, cs:__security_cookie
0x1400874d3  xor     rax, rsp
0x1400874d6  mov     [rbp+57h+var_20], rax
0x1400874da  mov     rbx, rdx
0x1400874dd  mov     rdi, rcx
0x1400874e0  mov     [rbp+57h+var_68], rdx
0x1400874e4  lea     rcx, [rbp+57h+FileTime2]
0x1400874e8  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x1400874ed  mov     rax, 0B0051C88000h
0x1400874f7  mov     [rbp+57h+hObject], rax
0x1400874fb  lea     r8, [rbp+57h+hObject]
0x1400874ff  lea     rdx, [rbp+57h+var_78]
0x140087503  lea     rcx, [rdi+4Ch]
0x140087507  call    ??HDateTime@@QEBA?AV0@AEBVTimeSpan@@@Z; DateTime::operator+(TimeSpan const &)
0x14008750c  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x140087510  mov     rcx, rax; lpFileTime1
0x140087513  call    cs:__imp_CompareFileTime
0x140087519  test    eax, eax
0x14008751b  jns     short loc_140087591
0x14008751d  lea     rdx, [rdi+20h]
0x140087521  lea     rcx, [rbp+57h+lpFileName]
0x140087525  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14008752a  nop
0x14008752b  mov     rdx, rdi
0x14008752e  lea     rcx, [rbp+57h+lpExistingFileName]
0x140087532  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140087537  lea     rcx, [rbp+57h+lpFileName]
0x14008753b  cmp     [rbp+57h+var_48], 7
0x140087540  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x140087545  call    cs:__imp_DeleteFileW
0x14008754b  lea     rdx, [rbp+57h+lpFileName]
0x14008754f  cmp     [rbp+57h+var_48], 7
0x140087554  cmova   rdx, [rbp+57h+lpFileName]; lpNewFileName
0x140087559  lea     rcx, [rbp+57h+lpExistingFileName]
0x14008755d  cmp     [rbp+57h+var_28], 7
0x140087562  cmova   rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x140087567  call    cs:__imp_MoveFileW
0x14008756d  movsd   xmm0, qword ptr [rbp+57h+FileTime2.dwLowDateTime]
0x140087572  movsd   qword ptr [rdi+4Ch], xmm0
0x140087577  mov     eax, [rbp+57h+var_A0]
0x14008757a  mov     [rdi+54h], eax
0x14008757d  lea     rcx, [rbp+57h+lpExistingFileName]
0x140087581  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140087586  nop
0x140087587  lea     rcx, [rbp+57h+lpFileName]
0x14008758b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140087590  nop
0x140087591  lea     rax, ??_7OutputFile@IO@@6BOutputStream@@@; const IO::OutputFile::`vftable'{for `OutputStream'}
0x140087598  mov     [rbp+57h+var_98], rax
0x14008759c  lea     rax, ??_7OutputFile@IO@@6BSeekableStream@@@; const IO::OutputFile::`vftable'{for `SeekableStream'}
0x1400875a3  mov     [rbp+57h+var_90], rax
0x1400875a7  mov     r8d, 1
0x1400875ad  mov     rdx, rdi
0x1400875b0  lea     rcx, [rbp+57h+hObject]
0x1400875b4  call    ?Open@File@IO@@YA?AV?$unique_ptr@XUHandleClose@Private@@@std@@AEBVPath@2@W4Access@12@@Z; IO::File::Open(IO::Path const &,IO::File::Access)
0x1400875b9  nop
0x1400875ba  mov     rdx, rax
0x1400875bd  lea     rcx, [rbp+57h+var_88]
0x1400875c1  call    ??$?0XUHandleClose@Private@@$0A@@?$shared_ptr@X@std@@QEAA@$$QEAV?$unique_ptr@XUHandleClose@Private@@@1@@Z; std::shared_ptr<void>::shared_ptr<void>(std::unique_ptr<void,Private::HandleClose> &&)
0x1400875c6  nop
0x1400875c7  mov     rcx, [rbp+57h+hObject]; hObject
0x1400875cb  test    rcx, rcx
0x1400875ce  jz      short loc_1400875E1
0x1400875d0  lea     rax, [rcx-1]
0x1400875d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400875d8  ja      short loc_1400875E1
0x1400875da  call    cs:__imp_CloseHandle
0x1400875e0  nop
0x1400875e1  xor     r8d, r8d
0x1400875e4  lea     edx, [r8+2]
0x1400875e8  lea     rcx, [rbp+57h+var_90]
0x1400875ec  call    ?Seek@OutputFile@IO@@UEAA_KW4Location@SeekableStream@@H@Z; IO::OutputFile::Seek(SeekableStream::Location,int)
0x1400875f1  mov     r8, [rbx+10h]
0x1400875f5  cmp     qword ptr [rbx+18h], 7
0x1400875fa  jbe     short loc_140087601
0x1400875fc  mov     rdx, [rbx]
0x1400875ff  jmp     short loc_140087604
0x140087601  mov     rdx, rbx
0x140087604  add     r8, r8
0x140087607  mov     rax, [rbp+57h+var_98]
0x14008760b  lea     rcx, [rbp+57h+var_98]
0x14008760f  mov     rax, [rax+8]
0x140087613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087618  nop
0x140087619  lea     rcx, [rbp+57h+var_98]; this
0x14008761d  call    ??1OutputFile@IO@@UEAA@XZ; IO::OutputFile::~OutputFile(void)
0x140087622  nop
0x140087623  mov     rcx, rbx
0x140087626  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008762b  mov     rcx, [rbp+57h+var_20]
0x14008762f  xor     rcx, rsp; StackCookie
0x140087632  call    __security_check_cookie
0x140087637  mov     rbx, [rsp+0D0h+arg_10]
0x14008763f  add     rsp, 0C0h
0x140087646  pop     rdi
0x140087647  pop     rsi
0x140087648  pop     rbp
0x140087649  retn
```
