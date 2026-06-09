# LaunchExe(ushort *,ushort *)

- ea: `0x18003a67c`
- end: `0x18003a789`
- name: `?LaunchExe@@YAJPEAG0@Z`
- size: `269`
- prototype: `__int64 __fastcall(LPCWSTR lpApplicationName, LPWSTR lpCommandLine)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180037324`

## callees

- `0x18003a67c`
- `0x18004d350`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18003a759`
- `KERNEL32!CloseHandle` at `0x18003a768`
- `KERNEL32!CloseHandle` at `0x18003a759`
- `KERNEL32!CloseHandle` at `0x18003a768`
- `KERNEL32!WaitForSingleObject` at `0x18003a71e`
- `KERNEL32!WaitForSingleObject` at `0x18003a71e`
- `KERNEL32!GetExitCodeProcess` at `0x18003a731`
- `KERNEL32!GetExitCodeProcess` at `0x18003a731`
- `KERNEL32!CreateProcessW` at `0x18003a704`
- `KERNEL32!CreateProcessW` at `0x18003a704`
- `KERNEL32!GetFileAttributesW` at `0x18003a69f`
- `KERNEL32!GetFileAttributesW` at `0x18003a69f`

## pseudocode

```c
__int64 __fastcall LaunchExe(LPCWSTR lpApplicationName, LPWSTR lpCommandLine)
{
  unsigned int LastWin32Error; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+58h] [rbp-39h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+78h] [rbp-19h] BYREF
  DWORD ExitCode; // [rsp+108h] [rbp+77h] BYREF

  LastWin32Error = 0;
  if ( GetFileAttributesW(lpApplicationName) == -1 )
    return 0;
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( CreateProcessW(lpApplicationName, lpCommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation)
    && WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) != -1
    && GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
  {
    if ( ExitCode )
    {
      LastWin32Error = (unsigned __int16)ExitCode | 0x80070000;
      if ( (int)ExitCode <= 0 )
        LastWin32Error = ExitCode;
    }
  }
  else
  {
    LastWin32Error = GetLastWin32Error();
  }
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003a67c  mov     rax, rsp
0x18003a67f  mov     [rax+8], rbx
0x18003a683  mov     [rax+10h], rsi
0x18003a687  mov     [rax+20h], rdi
0x18003a68b  push    rbp
0x18003a68c  lea     rbp, [rax-5Fh]
0x18003a690  sub     rsp, 0E0h
0x18003a697  mov     rsi, rdx
0x18003a69a  mov     rdi, rcx
0x18003a69d  xor     ebx, ebx
0x18003a69f  call    cs:__imp_GetFileAttributesW
0x18003a6a5  cmp     eax, 0FFFFFFFFh
0x18003a6a8  jnz     short loc_18003A6B1
0x18003a6aa  xor     eax, eax
0x18003a6ac  jmp     loc_18003A770
0x18003a6b1  xor     edx, edx; Val
0x18003a6b3  lea     rcx, [rbp+57h+StartupInfo+4]; void *
0x18003a6b7  lea     r8d, [rdx+64h]; Size
0x18003a6bb  call    memset_0
0x18003a6c0  xor     eax, eax
0x18003a6c2  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x18003a6c9  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x18003a6cd  xorps   xmm0, xmm0
0x18003a6d0  lea     rax, [rbp+57h+ProcessInformation]
0x18003a6d4  xor     r9d, r9d; lpThreadAttributes
0x18003a6d7  mov     [rsp+0E0h+lpProcessInformation], rax; lpProcessInformation
0x18003a6dc  xor     r8d, r8d; lpProcessAttributes
0x18003a6df  lea     rax, [rbp+57h+StartupInfo]
0x18003a6e3  mov     rdx, rsi; lpCommandLine
0x18003a6e6  mov     [rsp+0E0h+lpStartupInfo], rax; lpStartupInfo
0x18003a6eb  mov     rcx, rdi; lpApplicationName
0x18003a6ee  and     [rsp+0E0h+var_A8], rbx
0x18003a6f3  and     [rsp+0E0h+var_B0], rbx
0x18003a6f8  and     dword ptr [rsp+0E0h+var_B8], ebx
0x18003a6fc  and     [rsp+0E0h+var_C0], ebx
0x18003a700  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x18003a704  call    cs:__imp_CreateProcessW
0x18003a70a  test    eax, eax
0x18003a70c  jnz     short loc_18003A717
0x18003a70e  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003a713  mov     ebx, eax
0x18003a715  jmp     short loc_18003A750
0x18003a717  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hHandle
0x18003a71b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003a71e  call    cs:__imp_WaitForSingleObject
0x18003a724  cmp     eax, 0FFFFFFFFh
0x18003a727  jz      short loc_18003A70E
0x18003a729  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hProcess
0x18003a72d  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x18003a731  call    cs:__imp_GetExitCodeProcess
0x18003a737  test    eax, eax
0x18003a739  jz      short loc_18003A70E
0x18003a73b  mov     eax, [rbp+57h+ExitCode]
0x18003a73e  test    eax, eax
0x18003a740  jz      short loc_18003A750
0x18003a742  movzx   ebx, ax
0x18003a745  or      ebx, 80070000h
0x18003a74b  test    eax, eax
0x18003a74d  cmovle  ebx, eax
0x18003a750  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x18003a754  test    rcx, rcx
0x18003a757  jz      short loc_18003A75F
0x18003a759  call    cs:__imp_CloseHandle
0x18003a75f  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x18003a763  test    rcx, rcx
0x18003a766  jz      short loc_18003A76E
0x18003a768  call    cs:__imp_CloseHandle
0x18003a76e  mov     eax, ebx
0x18003a770  lea     r11, [rsp+0E0h+var_s0]
0x18003a778  mov     rbx, [r11+10h]
0x18003a77c  mov     rsi, [r11+18h]
0x18003a780  mov     rdi, [r11+28h]
0x18003a784  mov     rsp, r11
0x18003a787  pop     rbp
0x18003a788  retn
```
