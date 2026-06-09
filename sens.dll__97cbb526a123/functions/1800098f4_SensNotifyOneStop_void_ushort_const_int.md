# SensNotifyOneStop(void *,ushort const *,int)

- ea: `0x1800098f4`
- end: `0x180009a2b`
- name: `?SensNotifyOneStop@@YAJPEAXPEBGH@Z`
- size: `311`
- prototype: `signed int __fastcall(HANDLE hToken, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004fac`

## callees

- `0x180004c20`
- `0x1800098f4`
- `0x18000a766`
- `0x18000a7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800099d5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800099d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800099eb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800099c3`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800099c3`

## pseudocode

```c
signed int __fastcall SensNotifyOneStop(HANDLE hToken, const unsigned __int16 *a2)
{
  signed int result; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  WCHAR CommandLine[256]; // [rsp+F0h] [rbp-10h] BYREF

  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  StringCchCopyW(CommandLine, 0x100u, L"mobsync.exe /logoff");
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  memset(&StartupInfo.lpReserved, 0, 40);
  StartupInfo.dwFlags = 0;
  *(_DWORD *)&StartupInfo.wShowWindow = 5;
  StartupInfo.lpReserved2 = 0;
  if ( CreateProcessAsUserW(hToken, 0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
    CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800098f4  mov     [rsp-8+arg_8], rbx
0x1800098f9  mov     [rsp-8+arg_10], rdi
0x1800098fe  push    rbp
0x1800098ff  lea     rbp, [rsp-200h]
0x180009907  sub     rsp, 300h
0x18000990e  mov     rax, cs:__security_cookie
0x180009915  xor     rax, rsp
0x180009918  mov     [rbp+200h+var_10], rax
0x18000991f  mov     rbx, rcx
0x180009922  mov     edi, 68h ; 'h'
0x180009927  mov     r8d, edi; Size
0x18000992a  lea     rcx, [rbp+200h+StartupInfo]; void *
0x18000992e  xor     edx, edx; Val
0x180009930  call    memset_0
0x180009935  xor     eax, eax
0x180009937  lea     r8, aMobsyncExeLogo; "mobsync.exe /logoff"
0x18000993e  xorps   xmm0, xmm0
0x180009941  mov     qword ptr [rsp+300h+ProcessInformation.dwProcessId], rax
0x180009946  mov     edx, 100h; unsigned __int64
0x18000994b  lea     rcx, [rbp+200h+CommandLine]; unsigned __int16 *
0x18000994f  movups  xmmword ptr [rsp+300h+ProcessInformation.hProcess], xmm0
0x180009954  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009959  mov     r8d, edi; Size
0x18000995c  lea     rcx, [rbp+200h+StartupInfo]; void *
0x180009960  xor     edx, edx; Val
0x180009962  call    memset_0
0x180009967  lea     rax, [rsp+300h+ProcessInformation]
0x18000996c  mov     [rbp+200h+StartupInfo.cb], edi
0x18000996f  xor     edi, edi
0x180009971  mov     [rsp+300h+lpProcessInformation], rax; lpProcessInformation
0x180009976  lea     rax, [rbp+200h+StartupInfo]
0x18000997a  mov     [rbp+200h+StartupInfo.lpReserved], rdi
0x18000997e  mov     [rsp+300h+lpStartupInfo], rax; lpStartupInfo
0x180009983  lea     r8, [rbp+200h+CommandLine]; lpCommandLine
0x180009987  mov     [rsp+300h+lpCurrentDirectory], rdi; lpCurrentDirectory
0x18000998c  xorps   xmm0, xmm0
0x18000998f  mov     [rsp+300h+lpEnvironment], rdi; lpEnvironment
0x180009994  xor     r9d, r9d; lpProcessAttributes
0x180009997  mov     [rsp+300h+dwCreationFlags], edi; dwCreationFlags
0x18000999b  xor     edx, edx; lpApplicationName
0x18000999d  mov     [rsp+300h+bInheritHandles], edi; bInheritHandles
0x1800099a1  mov     rcx, rbx; hToken
0x1800099a4  mov     [rsp+300h+lpThreadAttributes], rdi; lpThreadAttributes
0x1800099a9  mov     [rbp+200h+StartupInfo.lpTitle], rdi
0x1800099ad  mov     [rbp+200h+StartupInfo.lpDesktop], rdi
0x1800099b1  movups  xmmword ptr [rbp+200h+StartupInfo.dwX], xmm0
0x1800099b5  mov     [rbp+200h+StartupInfo.dwFlags], edi
0x1800099b8  mov     dword ptr [rbp+200h+StartupInfo.wShowWindow], 5
0x1800099bf  mov     [rbp+200h+StartupInfo.lpReserved2], rdi
0x1800099c3  call    cs:__imp_CreateProcessAsUserW
0x1800099c9  test    eax, eax
0x1800099cb  jz      short loc_1800099F5
0x1800099cd  mov     rcx, [rsp+300h+ProcessInformation.hProcess]; hHandle
0x1800099d2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800099d5  call    cs:__imp_WaitForSingleObject
0x1800099db  mov     rcx, [rsp+300h+ProcessInformation.hProcess]; hObject
0x1800099e0  call    cs:__imp_CloseHandle
0x1800099e6  mov     rcx, [rsp+300h+ProcessInformation.hThread]; hObject
0x1800099eb  call    cs:__imp_CloseHandle
0x1800099f1  xor     eax, eax
0x1800099f3  jmp     short loc_180009A07
0x1800099f5  call    cs:__imp_GetLastError
0x1800099fb  test    eax, eax
0x1800099fd  jle     short loc_180009A07
0x1800099ff  movzx   eax, ax
0x180009a02  or      eax, 80070000h
0x180009a07  mov     rcx, [rbp+200h+var_10]
0x180009a0e  xor     rcx, rsp; StackCookie
0x180009a11  call    __security_check_cookie
0x180009a16  lea     r11, [rsp+300h+var_s0]
0x180009a1e  mov     rbx, [r11+18h]
0x180009a22  mov     rdi, [r11+20h]
0x180009a26  mov     rsp, r11
0x180009a29  pop     rbp
0x180009a2a  retn
```
