# Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(ushort *,ulong &)

- ea: `0x18001f6b4`
- end: `0x18001f7cd`
- name: `?ExecuteProcess@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEAGAEAK@Z`
- size: `281`
- prototype: `int(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f284`

## callees

- `0x18000abd4`
- `0x18001f6b4`
- `0x1800319ae`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001f74f`
- `KERNEL32!WaitForSingleObject` at `0x18001f74f`
- `KERNEL32!CloseHandle` at `0x18001f79c`
- `KERNEL32!CloseHandle` at `0x18001f7ad`
- `KERNEL32!CloseHandle` at `0x18001f79c`
- `KERNEL32!CloseHandle` at `0x18001f7ad`
- `KERNEL32!GetExitCodeProcess` at `0x18001f769`
- `KERNEL32!GetExitCodeProcess` at `0x18001f769`
- `KERNEL32!CreateProcessW` at `0x18001f730`
- `KERNEL32!CreateProcessW` at `0x18001f730`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::ExecuteProcess(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  HANDLE hProcess; // rcx
  signed int Error; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-98h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-78h] BYREF

  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(0, a2, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    return ATL::AtlHresultFromLastError();
  if ( !WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF)
    && (hProcess = ProcessInformation.hProcess, *a3 = 0, GetExitCodeProcess(hProcess, a3)) )
  {
    Error = *a3 != 0 ? 0x80004005 : 0;
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
    if ( Error >= 0 )
      Error = -2147418113;
  }
  CloseHandle(ProcessInformation.hProcess);
  CloseHandle(ProcessInformation.hThread);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001f6b4  mov     [rsp+arg_0], rbx
0x18001f6b9  push    rdi
0x18001f6ba  sub     rsp, 0E0h
0x18001f6c1  mov     rbx, rdx
0x18001f6c4  mov     qword ptr [rsp+0E8h+StartupInfo.cb], 68h ; 'h'
0x18001f6cd  xor     edx, edx; Val
0x18001f6cf  lea     rcx, [rsp+0E8h+StartupInfo.lpReserved]; void *
0x18001f6d4  mov     rdi, r8
0x18001f6d7  lea     r8d, [rdx+60h]; Size
0x18001f6db  call    memset_0
0x18001f6e0  xor     eax, eax
0x18001f6e2  xorps   xmm0, xmm0
0x18001f6e5  mov     qword ptr [rsp+0E8h+ProcessInformation.dwProcessId], rax
0x18001f6ea  xor     r9d, r9d; lpThreadAttributes
0x18001f6ed  lea     rax, [rsp+0E8h+ProcessInformation]
0x18001f6f2  xor     r8d, r8d; lpProcessAttributes
0x18001f6f5  mov     [rsp+0E8h+lpProcessInformation], rax; lpProcessInformation
0x18001f6fa  mov     rdx, rbx; lpCommandLine
0x18001f6fd  lea     rax, [rsp+0E8h+StartupInfo]
0x18001f702  xor     ecx, ecx; lpApplicationName
0x18001f704  mov     [rsp+0E8h+lpStartupInfo], rax; lpStartupInfo
0x18001f709  mov     [rsp+0E8h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18001f712  mov     [rsp+0E8h+lpEnvironment], 0; lpEnvironment
0x18001f71b  mov     [rsp+0E8h+dwCreationFlags], 8000000h; dwCreationFlags
0x18001f723  mov     [rsp+0E8h+bInheritHandles], 0; bInheritHandles
0x18001f72b  movups  xmmword ptr [rsp+0E8h+ProcessInformation.hProcess], xmm0
0x18001f730  call    cs:__imp_CreateProcessW
0x18001f737  nop     dword ptr [rax+rax+00h]
0x18001f73c  test    eax, eax
0x18001f73e  jnz     short loc_18001F747
0x18001f740  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001f745  jmp     short loc_18001F7BB
0x18001f747  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hHandle
0x18001f74c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001f74f  call    cs:__imp_WaitForSingleObject
0x18001f756  nop     dword ptr [rax+rax+00h]
0x18001f75b  test    eax, eax
0x18001f75d  jnz     short loc_18001F779
0x18001f75f  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hProcess
0x18001f764  mov     rdx, rdi; lpExitCode
0x18001f767  mov     [rdi], eax
0x18001f769  call    cs:__imp_GetExitCodeProcess
0x18001f770  nop     dword ptr [rax+rax+00h]
0x18001f775  test    eax, eax
0x18001f777  jnz     short loc_18001F78B
0x18001f779  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001f77e  mov     ebx, eax
0x18001f780  test    eax, eax
0x18001f782  js      short loc_18001F797
0x18001f784  mov     ebx, 8000FFFFh
0x18001f789  jmp     short loc_18001F797
0x18001f78b  mov     eax, [rdi]
0x18001f78d  neg     eax
0x18001f78f  sbb     ebx, ebx
0x18001f791  and     ebx, 80004005h
0x18001f797  mov     rcx, [rsp+0E8h+ProcessInformation.hProcess]; hObject
0x18001f79c  call    cs:__imp_CloseHandle
0x18001f7a3  nop     dword ptr [rax+rax+00h]
0x18001f7a8  mov     rcx, [rsp+0E8h+ProcessInformation.hThread]; hObject
0x18001f7ad  call    cs:__imp_CloseHandle
0x18001f7b4  nop     dword ptr [rax+rax+00h]
0x18001f7b9  mov     eax, ebx
0x18001f7bb  mov     rbx, [rsp+0E8h+arg_0]
0x18001f7c3  add     rsp, 0E0h
0x18001f7ca  pop     rdi
0x18001f7cb  retn
```
