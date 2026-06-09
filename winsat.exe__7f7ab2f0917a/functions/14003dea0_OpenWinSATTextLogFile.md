# OpenWinSATTextLogFile

- ea: `0x14003dea0`
- end: `0x14003e0d4`
- name: `OpenWinSATTextLogFile`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14003dbb4`

## callees

- `0x140005f4c`
- `0x1400084ec`
- `0x14000d4f0`
- `0x140015c28`
- `0x140016264`
- `0x140016d04`
- `0x14003dea0`
- `0x14003ec14`
- `0x140047ef4`
- `0x140113220`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14003df64`
- `KERNEL32!CreateFileW` at `0x14003df64`
- `KERNEL32!GetFileSizeEx` at `0x14003df86`
- `KERNEL32!GetFileSizeEx` at `0x14003df86`
- `KERNEL32!EnterCriticalSection` at `0x14003dfe4`
- `KERNEL32!EnterCriticalSection` at `0x14003dfe4`
- `KERNEL32!LeaveCriticalSection` at `0x14003e030`
- `KERNEL32!LeaveCriticalSection` at `0x14003e030`
- `KERNEL32!SetFilePointer` at `0x14003dfba`
- `KERNEL32!SetFilePointer` at `0x14003dfba`
- `KERNEL32!SetEndOfFile` at `0x14003dfa5`
- `KERNEL32!SetEndOfFile` at `0x14003dfa5`
- `KERNEL32!GetLocalTime` at `0x14003e041`
- `KERNEL32!GetLocalTime` at `0x14003e041`
- `KERNEL32!GetTimeFormatW` at `0x14003e06b`
- `KERNEL32!GetTimeFormatW` at `0x14003e06b`
- `KERNEL32!FlushFileBuffers` at `0x14003e023`
- `KERNEL32!FlushFileBuffers` at `0x14003e023`
- `KERNEL32!CloseHandle` at `0x14003dfcc`
- `KERNEL32!CloseHandle` at `0x14003dfcc`
- `KERNEL32!WriteFile` at `0x14003e016`
- `KERNEL32!WriteFile` at `0x14003e016`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 OpenWinSATTextLogFile()
{
  __int64 v0; // rax
  __int64 v1; // r8
  HANDLE FileW; // rax
  bool v3; // zf
  __int64 v5; // [rsp+40h] [rbp-40h] BYREF
  __int64 v6; // [rsp+48h] [rbp-38h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-30h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v5,
    260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v6,
    260);
  if ( (unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::GetEnvironmentVariableW(&v6)
    || (v0 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
               &v6,
               L"\\"),
        !mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator unsigned __int64(v0)) )
  {
    if ( (int)GetWinSATDir(&v5) < 0 )
      goto LABEL_17;
  }
  else
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::assign(
      (__int64)&v5,
      *(_QWORD *)(v6 + 24),
      v1);
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
    &v5,
    L"\\winsat.log");
  FileW = CreateFileW(*(LPCWSTR *)(v5 + 24), 0x40000000u, 1u, 0, 4u, 0x80000000, 0);
  hFile = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    FileSize.QuadPart = 0;
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      if ( FileSize.QuadPart <= 102400 )
        v3 = SetFilePointer(hFile, 0, 0, 2u) == -1;
      else
        v3 = !SetEndOfFile(hFile);
      if ( v3 )
      {
        CloseHandle(hFile);
        hFile = (HANDLE)-1LL;
      }
      EnterCriticalSection(&stru_1401C6570);
      if ( hFile != (HANDLE)-1LL && FileSize.QuadPart > 0 )
      {
        NumberOfBytesWritten = 0;
        WriteFile(hFile, "\r\n", 2u, &NumberOfBytesWritten, 0);
        FlushFileBuffers(hFile);
      }
      LeaveCriticalSection(&stru_1401C6570);
    }
    SystemTime = 0;
    GetLocalTime(&SystemTime);
    GetTimeFormatW(0x400u, 8u, &SystemTime, 0, &TimeStr, 128);
    Log_Text_F(
      "base\\winsat\\exe\\logging.cpp",
      841,
      "--- START %d\\%d\\%d %S ---",
      SystemTime.wYear,
      SystemTime.wMonth,
      SystemTime.wDay,
      &TimeStr);
  }
LABEL_17:
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v6);
  return mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v5);
}

```

## disassembly

```asm
0x14003dea0  mov     [rsp-8+arg_0], rbx
0x14003dea5  push    rbp
0x14003dea6  mov     rbp, rsp
0x14003dea9  sub     rsp, 80h
0x14003deb0  mov     rax, cs:__security_cookie
0x14003deb7  xor     rax, rsp
0x14003deba  mov     [rbp+var_10], rax
0x14003debe  mov     ebx, 104h
0x14003dec3  mov     edx, ebx
0x14003dec5  lea     rcx, [rbp+var_40]
0x14003dec9  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x14003dece  nop
0x14003decf  mov     edx, ebx
0x14003ded1  lea     rcx, [rbp+var_38]
0x14003ded5  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x14003deda  nop
0x14003dedb  lea     rcx, [rbp+var_38]
0x14003dedf  call    ?GetEnvironmentVariableW@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAKPEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::GetEnvironmentVariableW(ushort const *)
0x14003dee4  xor     ebx, ebx
0x14003dee6  test    eax, eax
0x14003dee8  jnz     short loc_14003DF1A
0x14003deea  lea     rdx, asc_14012B310; "\\"
0x14003def1  lea     rcx, [rbp+var_38]
0x14003def5  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x14003defa  mov     rcx, rax
0x14003defd  call    ??B?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_KXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator unsigned __int64(void)
0x14003df02  test    rax, rax
0x14003df05  jz      short loc_14003DF1A
0x14003df07  mov     rdx, [rbp+var_38]
0x14003df0b  mov     rdx, [rdx+18h]
0x14003df0f  lea     rcx, [rbp+var_40]
0x14003df13  call    ?assign@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)
0x14003df18  jmp     short loc_14003DF2B
0x14003df1a  lea     rcx, [rbp+var_40]
0x14003df1e  call    ?GetWinSATDir@@YAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; GetWinSATDir(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x14003df23  test    eax, eax
0x14003df25  js      loc_14003E0A4
0x14003df2b  lea     rdx, aWinsatLog; "\\winsat.log"
0x14003df32  lea     rcx, [rbp+var_40]
0x14003df36  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x14003df3b  mov     [rsp+80h+hTemplateFile], rbx; hTemplateFile
0x14003df40  mov     [rsp+80h+dwFlagsAndAttributes], 80000000h; dwFlagsAndAttributes
0x14003df48  mov     [rsp+80h+dwCreationDisposition], 4; dwCreationDisposition
0x14003df50  xor     r9d, r9d; lpSecurityAttributes
0x14003df53  mov     edx, 40000000h; dwDesiredAccess
0x14003df58  lea     r8d, [r9+1]; dwShareMode
0x14003df5c  mov     rcx, [rbp+var_40]
0x14003df60  mov     rcx, [rcx+18h]; lpFileName
0x14003df64  call    cs:__imp_CreateFileW
0x14003df6a  mov     cs:hFile, rax
0x14003df71  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14003df75  jz      loc_14003E0A4
0x14003df7b  mov     qword ptr [rbp+FileSize], rbx
0x14003df7f  lea     rdx, [rbp+FileSize]; lpFileSize
0x14003df83  mov     rcx, rax; hFile
0x14003df86  call    cs:__imp_GetFileSizeEx
0x14003df8c  test    eax, eax
0x14003df8e  jz      loc_14003E036
0x14003df94  mov     rcx, cs:hFile; hFile
0x14003df9b  cmp     qword ptr [rbp+FileSize], 19000h
0x14003dfa3  jle     short loc_14003DFAF
0x14003dfa5  call    cs:__imp_SetEndOfFile
0x14003dfab  test    eax, eax
0x14003dfad  jmp     short loc_14003DFC3
0x14003dfaf  mov     r9d, 2; dwMoveMethod
0x14003dfb5  xor     r8d, r8d; lpDistanceToMoveHigh
0x14003dfb8  xor     edx, edx; lDistanceToMove
0x14003dfba  call    cs:__imp_SetFilePointer
0x14003dfc0  cmp     eax, 0FFFFFFFFh
0x14003dfc3  jnz     short loc_14003DFDD
0x14003dfc5  mov     rcx, cs:hFile; hObject
0x14003dfcc  call    cs:__imp_CloseHandle
0x14003dfd2  mov     cs:hFile, 0FFFFFFFFFFFFFFFFh
0x14003dfdd  lea     rcx, stru_1401C6570; lpCriticalSection
0x14003dfe4  call    cs:__imp_EnterCriticalSection
0x14003dfea  mov     rcx, cs:hFile; hFile
0x14003dff1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14003dff5  jz      short loc_14003E029
0x14003dff7  cmp     qword ptr [rbp+FileSize], rbx
0x14003dffb  jle     short loc_14003E029
0x14003dffd  mov     [rbp+NumberOfBytesWritten], ebx
0x14003e000  mov     qword ptr [rsp+80h+dwCreationDisposition], rbx; lpOverlapped
0x14003e005  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14003e009  mov     r8d, 2; nNumberOfBytesToWrite
0x14003e00f  lea     rdx, asc_140139658; "\r\n"
0x14003e016  call    cs:__imp_WriteFile
0x14003e01c  mov     rcx, cs:hFile; hFile
0x14003e023  call    cs:__imp_FlushFileBuffers
0x14003e029  lea     rcx, stru_1401C6570; lpCriticalSection
0x14003e030  call    cs:__imp_LeaveCriticalSection
0x14003e036  xorps   xmm0, xmm0
0x14003e039  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x14003e03d  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x14003e041  call    cs:__imp_GetLocalTime
0x14003e047  mov     [rsp+80h+dwFlagsAndAttributes], 80h; cchTime
0x14003e04f  lea     rbx, TimeStr
0x14003e056  mov     qword ptr [rsp+80h+dwCreationDisposition], rbx; lpTimeStr
0x14003e05b  xor     r9d, r9d; lpFormat
0x14003e05e  lea     r8, [rbp+SystemTime]; lpTime
0x14003e062  lea     edx, [r9+8]; dwFlags
0x14003e066  mov     ecx, 400h; Locale
0x14003e06b  call    cs:__imp_GetTimeFormatW
0x14003e071  movzx   eax, [rbp+SystemTime.wDay]
0x14003e075  movzx   ecx, [rbp+SystemTime.wMonth]
0x14003e079  movzx   r9d, [rbp+SystemTime.wYear]
0x14003e07e  mov     [rsp+80h+hTemplateFile], rbx
0x14003e083  mov     [rsp+80h+dwFlagsAndAttributes], eax
0x14003e087  mov     [rsp+80h+dwCreationDisposition], ecx
0x14003e08b  lea     r8, aStartDDDS; "--- START %d\\%d\\%d %S ---"
0x14003e092  mov     edx, 349h
0x14003e097  lea     rcx, aBaseWinsatExeL; "base\\winsat\\exe\\logging.cpp"
0x14003e09e  call    Log_Text_F
0x14003e0a3  nop
0x14003e0a4  lea     rcx, [rbp+var_38]
0x14003e0a8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003e0ad  nop
0x14003e0ae  lea     rcx, [rbp+var_40]
0x14003e0b2  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x14003e0b7  mov     rcx, [rbp+var_10]
0x14003e0bb  xor     rcx, rsp; StackCookie
0x14003e0be  call    __security_check_cookie
0x14003e0c3  mov     rbx, [rsp+80h+arg_0]
0x14003e0cb  add     rsp, 80h
0x14003e0d2  pop     rbp
0x14003e0d3  retn
```
