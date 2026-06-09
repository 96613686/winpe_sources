# ExecuteBackgroundProcess(ushort const *,ushort const *,bool,ulong *)

- ea: `0x180011f20`
- end: `0x18001207e`
- name: `?ExecuteBackgroundProcess@@YAJPEBG0_NPEAK@Z`
- size: `350`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, LPCWSTR, char, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180010fc0`

## callees

- `0x180011f20`
- `0x180012084`
- `0x18001afe2`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001205d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180012066`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001205d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180012066`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012019`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fe7`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001200c`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001200c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180011fdd`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180011fdd`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001202b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001202b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012053`

## pseudocode

```c
__int64 __fastcall ExecuteBackgroundProcess(LPCWSTR lpSrc, LPCWSTR a2, char a3, unsigned int *a4)
{
  LPWSTR v8; // rdi
  signed int v9; // ebx
  signed int LastError; // eax
  LPWSTR lpCommandLine; // [rsp+50h] [rbp-79h] BYREF
  LPCWSTR lpApplicationName; // [rsp+58h] [rbp-71h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-69h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-49h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v8 = 0;
  lpApplicationName = 0;
  lpCommandLine = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v9 = ExpandEnvironmentStringsHelper(lpSrc, (unsigned __int16 **)&lpApplicationName, 0);
  if ( v9 >= 0 )
  {
    v9 = ExpandEnvironmentStringsHelper(a2, &lpCommandLine, 0);
    if ( v9 < 0 )
    {
      v8 = lpCommandLine;
    }
    else
    {
      StartupInfo.cb = 104;
      v8 = lpCommandLine;
      if ( !CreateProcessW(lpApplicationName, lpCommandLine, 0, 0, 1, 8u, 0, 0, &StartupInfo, &ProcessInformation)
        || (a3 || a4)
        && (ResumeThread(ProcessInformation.hThread), WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF), a4)
        && !GetExitCodeProcess(ProcessInformation.hProcess, a4) )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  operator delete[]((void *)lpApplicationName);
  operator delete[](v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011f20  push    rbp
0x180011f22  push    rbx
0x180011f23  push    rsi
0x180011f24  push    rdi
0x180011f25  push    r14
0x180011f27  push    r15
0x180011f29  lea     rbp, [rsp-2Fh]
0x180011f2e  sub     rsp, 0F8h
0x180011f35  mov     r15, rdx
0x180011f38  mov     r14b, r8b
0x180011f3b  xor     edx, edx; Val
0x180011f3d  mov     rbx, rcx
0x180011f40  lea     rcx, [rbp+57h+StartupInfo]; void *
0x180011f44  mov     rsi, r9
0x180011f47  lea     r8d, [rdx+68h]; Size
0x180011f4b  call    memset_0
0x180011f50  xor     eax, eax
0x180011f52  lea     rdx, [rbp+57h+lpApplicationName]; unsigned __int16 **
0x180011f56  xorps   xmm0, xmm0
0x180011f59  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180011f5d  xor     edi, edi
0x180011f5f  mov     [rbp+57h+lpApplicationName], rax
0x180011f63  xor     r8d, r8d; unsigned int *
0x180011f66  mov     [rbp+57h+lpCommandLine], rdi
0x180011f6a  mov     rcx, rbx; lpSrc
0x180011f6d  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180011f71  call    ?ExpandEnvironmentStringsHelper@@YAJPEBGPEAPEAGPEAK@Z; ExpandEnvironmentStringsHelper(ushort const *,ushort * *,ulong *)
0x180011f76  mov     ebx, eax
0x180011f78  test    eax, eax
0x180011f7a  js      loc_18001203B
0x180011f80  xor     r8d, r8d; unsigned int *
0x180011f83  lea     rdx, [rbp+57h+lpCommandLine]; unsigned __int16 **
0x180011f87  mov     rcx, r15; lpSrc
0x180011f8a  call    ?ExpandEnvironmentStringsHelper@@YAJPEBGPEAPEAGPEAK@Z; ExpandEnvironmentStringsHelper(ushort const *,ushort * *,ulong *)
0x180011f8f  mov     ebx, eax
0x180011f91  test    eax, eax
0x180011f93  js      loc_180012037
0x180011f99  mov     rcx, [rbp+57h+lpApplicationName]; lpApplicationName
0x180011f9d  lea     rax, [rbp+57h+ProcessInformation]
0x180011fa1  mov     [rsp+120h+lpProcessInformation], rax; lpProcessInformation
0x180011fa6  xor     r9d, r9d; lpThreadAttributes
0x180011fa9  lea     rax, [rbp+57h+StartupInfo]
0x180011fad  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x180011fb4  mov     [rsp+120h+lpStartupInfo], rax; lpStartupInfo
0x180011fb9  xor     r8d, r8d; lpProcessAttributes
0x180011fbc  mov     [rsp+120h+lpCurrentDirectory], rdi; lpCurrentDirectory
0x180011fc1  mov     [rsp+120h+lpEnvironment], rdi; lpEnvironment
0x180011fc6  mov     rdi, [rbp+57h+lpCommandLine]
0x180011fca  mov     rdx, rdi; lpCommandLine
0x180011fcd  mov     [rsp+120h+dwCreationFlags], 8; dwCreationFlags
0x180011fd5  mov     [rsp+120h+bInheritHandles], 1; bInheritHandles
0x180011fdd  call    cs:__imp_CreateProcessW
0x180011fe3  test    eax, eax
0x180011fe5  jnz     short loc_180011FFE
0x180011fe7  call    cs:__imp_GetLastError
0x180011fed  mov     ebx, eax
0x180011fef  test    eax, eax
0x180011ff1  jle     short loc_18001203B
0x180011ff3  movzx   ebx, ax
0x180011ff6  or      ebx, 80070000h
0x180011ffc  jmp     short loc_18001203B
0x180011ffe  test    r14b, r14b
0x180012001  jnz     short loc_180012008
0x180012003  test    rsi, rsi
0x180012006  jz      short loc_18001203B
0x180012008  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hThread
0x18001200c  call    cs:__imp_ResumeThread
0x180012012  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x180012016  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180012019  call    cs:__imp_WaitForSingleObject
0x18001201f  test    rsi, rsi
0x180012022  jz      short loc_18001203B
0x180012024  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x180012028  mov     rdx, rsi; lpExitCode
0x18001202b  call    cs:__imp_GetExitCodeProcess
0x180012031  test    eax, eax
0x180012033  jnz     short loc_18001203B
0x180012035  jmp     short loc_180011FE7
0x180012037  mov     rdi, [rbp+57h+lpCommandLine]
0x18001203b  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18001203f  test    rcx, rcx
0x180012042  jz      short loc_18001204A
0x180012044  call    cs:__imp_CloseHandle
0x18001204a  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18001204e  test    rcx, rcx
0x180012051  jz      short loc_180012059
0x180012053  call    cs:__imp_CloseHandle
0x180012059  mov     rcx, [rbp+57h+lpApplicationName]
0x18001205d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180012063  mov     rcx, rdi
0x180012066  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001206c  mov     eax, ebx
0x18001206e  add     rsp, 0F8h
0x180012075  pop     r15
0x180012077  pop     r14
0x180012079  pop     rdi
0x18001207a  pop     rsi
0x18001207b  pop     rbx
0x18001207c  pop     rbp
0x18001207d  retn
```
