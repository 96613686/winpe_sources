# DumpLogFileList

- ea: `0x140041870`
- end: `0x140041b2c`
- name: `DumpLogFileList`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x140042a48`

## callees

- `0x140003611`
- `0x140004170`
- `0x140004348`
- `0x1400085b4`
- `0x140017af0`
- `0x14001827c`
- `0x14003a150`
- `0x14003fa8c`
- `0x140040d28`
- `0x140041870`
- `0x14004fe00`
- `0x140113220`

## import_xrefs

- `ADVAPI32!OpenTraceW` at `0x140041971`
- `ADVAPI32!OpenTraceW` at `0x140041971`
- `ADVAPI32!CloseTrace` at `0x1400419e5`
- `ADVAPI32!CloseTrace` at `0x1400419e5`
- `ADVAPI32!ProcessTrace` at `0x1400419cf`
- `ADVAPI32!ProcessTrace` at `0x1400419cf`
- `KERNEL32!GetLastError` at `0x140041afc`
- `KERNEL32!GetLastError` at `0x140041afc`

## string_xrefs

- `0x140041b07`: `cannot open trace file '%s'`

## pseudocode

```c
__int64 __fastcall DumpLogFileList(_QWORD *a1)
{
  __int64 v2; // rdi
  __int64 v3; // rcx
  _EVENT_TRACE_LOGFILEW *p_Logfile; // rax
  __int64 v5; // rax
  __int64 *v6; // rax
  __int64 *v7; // rax
  __int64 *v8; // rbx
  unsigned __int16 v9; // r9
  const unsigned __int16 *v10; // rax
  __int64 *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v16; // rbx
  ULONG64 HandleArray; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C8h]
  __int64 v19; // [rsp+48h] [rbp-C0h]
  __int64 v20; // [rsp+50h] [rbp-B8h]
  __int64 v21; // [rsp+58h] [rbp-B0h]
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+68h] [rbp-A0h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  v2 = (__int64)(a1[1] - *a1) >> 3;
  v19 = 0;
  v21 = 0;
  HandleArray = -1;
  v18 = 0;
  v20 = 0;
  while ( 1 )
  {
    if ( --v2 == -1 )
    {
      v14 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
      std::basic_ostream<unsigned short>::flush(v14 + 240);
      return 0;
    }
    v3 = 448;
    p_Logfile = &Logfile;
    do
    {
      LOBYTE(p_Logfile->LogFileName) = 0;
      p_Logfile = (_EVENT_TRACE_LOGFILEW *)((char *)p_Logfile + 1);
      --v3;
    }
    while ( v3 );
    Logfile.LogFileName = *(LPWSTR *)(*(_QWORD *)(*a1 + 8 * v2) + 24LL);
    Logfile.EventCallback = (PEVENT_CALLBACK)EventRecordCallback;
    Logfile.Context = &HandleArray;
    v19 = 0;
    v21 = 0;
    Logfile.LogFileMode = 0x10000000;
    HandleArray = -1;
    v18 = 0;
    v20 = 0;
    HandleArray = OpenTraceW(&Logfile);
    if ( HandleArray == -1 )
      break;
    v5 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
    v6 = (__int64 *)std::operator<<<unsigned short,std::char_traits<unsigned short>>(
                      v5 + 240,
                      "\n> WinSAT Run Time Log from : ");
    v7 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
           v6,
           *(_QWORD *)(*(_QWORD *)(*a1 + 8 * v2) + 24LL));
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, "\n");
    if ( ProcessTrace(&HandleArray, 1u, 0, 0) )
    {
      Record_Win32Error_w("base\\winsat\\exe\\viewlog.cpp", *(_QWORD *)(*(_QWORD *)(*a1 + 8 * v2) + 24LL));
      return 2147500037LL;
    }
    if ( CloseTrace(HandleArray) )
      return 2147500037LL;
    if ( !HIDWORD(v18) )
    {
      v8 = (__int64 *)(CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw)
                     + 240);
      v10 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\viewlog.cpp", (const char *)0x45D, 10185, v9);
      v11 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, (__int64)v10);
      std::endl(v11);
    }
    if ( App::s_Verbose )
    {
      v12 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
      mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>::pfx(
        v12,
        L"%u total events, %u winsat events in %s\n",
        (unsigned int)v18,
        HIDWORD(v18),
        *(_QWORD *)(*(_QWORD *)(*a1 + 8 * v2) + 24LL));
    }
    if ( v2 )
    {
      v13 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->((__int64)&mlib::stdoutw);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13 + 240);
    }
  }
  v16 = *(_QWORD *)(*(_QWORD *)(*a1 + 8 * v2) + 24LL);
  GetLastError();
  Record_Win32Error_w("base\\winsat\\exe\\viewlog.cpp", v16);
  return 2147500037LL;
}

```

## disassembly

```asm
0x140041870  mov     rax, rsp
0x140041873  mov     [rax+10h], rbx
0x140041877  mov     [rax+18h], rsi
0x14004187b  push    rbp
0x14004187c  push    rdi
0x14004187d  push    r12
0x14004187f  lea     rbp, [rax-158h]
0x140041886  sub     rsp, 240h
0x14004188d  movaps  xmmword ptr [rax-28h], xmm6
0x140041891  mov     rax, cs:__security_cookie
0x140041898  xor     rax, rsp
0x14004189b  mov     [rbp+150h+var_30], rax
0x1400418a2  mov     rsi, rcx
0x1400418a5  xor     edx, edx; Val
0x1400418a7  lea     rcx, [rsp+250h+Logfile]; void *
0x1400418ac  mov     r8d, 1C0h; Size
0x1400418b2  call    memset_0
0x1400418b7  mov     rdi, [rsi+8]
0x1400418bb  lea     r12, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x1400418c2  sub     rdi, [rsi]
0x1400418c5  xorps   xmm6, xmm6
0x1400418c8  sar     rdi, 3
0x1400418cc  mov     ebx, 0F0h
0x1400418d1  movsd   [rsp+250h+var_210], xmm6
0x1400418d7  movsd   [rsp+250h+var_200], xmm6
0x1400418dd  mov     [rsp+250h+HandleArray], 0FFFFFFFFFFFFFFFFh
0x1400418e6  mov     [rsp+250h+var_218], 0
0x1400418ef  mov     [rsp+250h+var_208], 0
0x1400418f8  jmp     loc_140041A87
0x1400418fd  mov     ecx, 1C0h
0x140041902  lea     rax, [rsp+250h+Logfile]
0x140041907  mov     byte ptr [rax], 0
0x14004190a  inc     rax
0x14004190d  sub     rcx, 1
0x140041911  jnz     short loc_140041907
0x140041913  mov     rax, [rsi]
0x140041916  mov     rcx, [rax+rdi*8]
0x14004191a  mov     rax, [rcx+18h]
0x14004191e  lea     rcx, [rsp+250h+Logfile]; Logfile
0x140041923  mov     [rsp+250h+Logfile.LogFileName], rax
0x140041928  lea     rax, EventRecordCallback
0x14004192f  mov     qword ptr [rbp+150h+Logfile.1A8h], rax
0x140041936  lea     rax, [rsp+250h+HandleArray]
0x14004193b  mov     [rbp+150h+Logfile.Context], rax
0x140041942  movsd   [rsp+250h+var_210], xmm6
0x140041948  movsd   [rsp+250h+var_200], xmm6
0x14004194e  mov     dword ptr [rsp+250h+Logfile.1Ch], 10000000h
0x140041956  mov     [rsp+250h+HandleArray], 0FFFFFFFFFFFFFFFFh
0x14004195f  mov     [rsp+250h+var_218], 0
0x140041968  mov     [rsp+250h+var_208], 0
0x140041971  call    cs:__imp_OpenTraceW
0x140041977  mov     [rsp+250h+HandleArray], rax
0x14004197c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140041980  jz      loc_140041AF1
0x140041986  mov     rcx, r12
0x140041989  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14004198e  lea     rdx, aWinsatRunTimeL; "\n> WinSAT Run Time Log from : "
0x140041995  lea     rcx, [rbx+rax]
0x140041999  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x14004199e  mov     rcx, [rsi]
0x1400419a1  mov     rdx, [rcx+rdi*8]
0x1400419a5  mov     rcx, rax
0x1400419a8  mov     rdx, [rdx+18h]
0x1400419ac  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400419b1  mov     rcx, rax
0x1400419b4  lea     rdx, asc_14012B93C; "\n"
0x1400419bb  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x1400419c0  xor     r9d, r9d; EndTime
0x1400419c3  lea     rcx, [rsp+250h+HandleArray]; HandleArray
0x1400419c8  xor     r8d, r8d; StartTime
0x1400419cb  lea     edx, [r9+1]; HandleCount
0x1400419cf  call    cs:__imp_ProcessTrace
0x1400419d5  mov     r8d, eax
0x1400419d8  test    eax, eax
0x1400419da  jnz     loc_140041AD3
0x1400419e0  mov     rcx, [rsp+250h+HandleArray]; TraceHandle
0x1400419e5  call    cs:__imp_CloseTrace
0x1400419eb  test    eax, eax
0x1400419ed  jnz     loc_140041B22
0x1400419f3  cmp     dword ptr [rsp+250h+var_218+4], eax
0x1400419f7  jnz     short loc_140041A37
0x1400419f9  mov     rcx, r12
0x1400419fc  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140041a01  mov     edx, 45Dh; char *
0x140041a06  lea     rcx, aBaseWinsatExeV; "base\\winsat\\exe\\viewlog.cpp"
0x140041a0d  mov     r8d, 27C9h; int
0x140041a13  lea     rbx, [rax+0F0h]
0x140041a1a  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x140041a1f  mov     rdx, rax
0x140041a22  mov     rcx, rbx
0x140041a25  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140041a2a  mov     rcx, rax
0x140041a2d  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140041a32  mov     ebx, 0F0h
0x140041a37  cmp     cs:?s_Verbose@App@@2_NA, 0; bool App::s_Verbose
0x140041a3e  jz      short loc_140041A71
0x140041a40  mov     rcx, r12
0x140041a43  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140041a48  mov     rcx, [rsi]
0x140041a4b  mov     r9d, dword ptr [rsp+250h+var_218+4]
0x140041a50  mov     r8d, dword ptr [rsp+250h+var_218]
0x140041a55  mov     rdx, [rcx+rdi*8]
0x140041a59  mov     rcx, [rdx+18h]
0x140041a5d  lea     rdx, aUTotalEventsUW; "%u total events, %u winsat events in %s"...
0x140041a64  mov     qword ptr [rsp+250h+var_230], rcx
0x140041a69  mov     rcx, rax
0x140041a6c  call    ?pfx@?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@QEAAHPEBGZZ; mlib::handle_ostreamT<ushort,std::char_traits<ushort>>::pfx(ushort const *,...)
0x140041a71  test    rdi, rdi
0x140041a74  jz      short loc_140041A87
0x140041a76  mov     rcx, r12
0x140041a79  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140041a7e  lea     rcx, [rbx+rax]
0x140041a82  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@D@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char)
0x140041a87  dec     rdi
0x140041a8a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140041a8e  jnz     loc_1400418FD
0x140041a94  mov     rcx, r12
0x140041a97  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140041a9c  lea     rcx, [rbx+rax]
0x140041aa0  call    ?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x140041aa5  xor     eax, eax
0x140041aa7  mov     rcx, [rbp+150h+var_30]
0x140041aae  xor     rcx, rsp; StackCookie
0x140041ab1  call    __security_check_cookie
0x140041ab6  lea     r11, [rsp+250h+var_10]
0x140041abe  mov     rbx, [r11+28h]
0x140041ac2  mov     rsi, [r11+30h]
0x140041ac6  movaps  xmm6, xmmword ptr [r11-10h]
0x140041acb  mov     rsp, r11
0x140041ace  pop     r12
0x140041ad0  pop     rdi
0x140041ad1  pop     rbp
0x140041ad2  retn
0x140041ad3  mov     rax, [rsi]
0x140041ad6  lea     r9, aCannotProcessT_0; "cannot process trace file '%s'"
0x140041add  mov     rdx, [rax+rdi*8]
0x140041ae1  mov     rax, [rdx+18h]
0x140041ae5  mov     edx, 454h
0x140041aea  mov     qword ptr [rsp+250h+var_230], rax
0x140041aef  jmp     short loc_140041B16
0x140041af1  mov     rax, [rsi]
0x140041af4  mov     rcx, [rax+rdi*8]
0x140041af8  mov     rbx, [rcx+18h]
0x140041afc  call    cs:__imp_GetLastError
0x140041b02  mov     qword ptr [rsp+250h+var_230], rbx; char
0x140041b07  lea     r9, aCannotOpenTrac; "cannot open trace file '%s'"
0x140041b0e  mov     r8d, eax
0x140041b11  mov     edx, 44Bh
0x140041b16  lea     rcx, aBaseWinsatExeV; "base\\winsat\\exe\\viewlog.cpp"
0x140041b1d  call    Record_Win32Error_w
0x140041b22  mov     eax, 80004005h
0x140041b27  jmp     loc_140041AA7
```
