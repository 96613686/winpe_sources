# _InitRestrictedProcess(void * *,void * *)

- ea: `0x18003cf38`
- end: `0x18003d11e`
- name: `?_InitRestrictedProcess@@YAJPEAPEAX0@Z`
- size: `486`
- prototype: `__int64 __fastcall(void **, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180016c80`
- `0x18003cea0`

## callees

- `0x18003cf38`
- `0x18003d244`
- `0x180054130`
- `0x180054ad4`
- `0x1800d8f90`
- `0x1800d9100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d014`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d014`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003cfa5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003cfa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cf8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003cf8c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18003d0af`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18003d0af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cfdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cfdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003d0e8`

## pseudocode

```c
__int64 __fastcall _InitRestrictedProcess(void **a1, void **a2)
{
  HANDLE CurrentProcess; // rax
  int Error; // ebx
  const unsigned __int16 *v6; // rcx
  unsigned int v7; // r8d
  HANDLE EventW; // rdi
  HANDLE hThread; // rcx
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hToken; // [rsp+68h] [rbp-98h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR CommandLine[264]; // [rsp+100h] [rbp+0h] BYREF

  *a1 = 0;
  *a2 = 0;
  hToken = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x8Bu, &TokenHandle) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    Error = _CreateRestrictedTokenFromSpecifiedToken((void *)0x2000, TokenHandle, &hToken);
    CloseHandle(TokenHandle);
    if ( Error >= 0 )
    {
      Error = _GetCommandLine(v6, CommandLine, v7);
      if ( Error >= 0 )
      {
        EventW = CreateEventW(0, 0, 0, L"22d8c27b-47a1-48d1-ad08-7da7abd79617");
        if ( EventW || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          *(_QWORD *)&StartupInfo.cb = 104;
          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
          memset_0(&StartupInfo.lpReserved, 0, 0x60u);
          StartupInfo.dwFlags = 128;
          if ( CreateProcessAsUserW(hToken, 0, CommandLine, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
          {
            Error = 0;
LABEL_10:
            hThread = ProcessInformation.hThread;
            *a1 = ProcessInformation.hProcess;
            *a2 = EventW;
LABEL_13:
            CloseHandle(hThread);
            return (unsigned int)Error;
          }
          Error = ResultFromKnownLastError();
          if ( Error >= 0 )
            goto LABEL_10;
          if ( EventW )
          {
            hThread = EventW;
            goto LABEL_13;
          }
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18003cf38  mov     [rsp-8+arg_10], rbx
0x18003cf3d  mov     [rsp-8+arg_18], rsi
0x18003cf42  push    rbp
0x18003cf43  push    rdi
0x18003cf44  push    r14
0x18003cf46  lea     rbp, [rsp-220h]
0x18003cf4e  sub     rsp, 320h
0x18003cf55  mov     rax, cs:__security_cookie
0x18003cf5c  xor     rax, rsp
0x18003cf5f  mov     [rbp+230h+var_20], rax
0x18003cf66  mov     qword ptr [rcx], 0
0x18003cf6d  mov     r14, rdx
0x18003cf70  mov     qword ptr [rdx], 0
0x18003cf77  mov     rsi, rcx
0x18003cf7a  mov     [rsp+330h+hToken], 0
0x18003cf83  mov     [rsp+330h+TokenHandle], 0
0x18003cf8c  call    cs:__imp_GetCurrentProcess
0x18003cf93  nop     dword ptr [rax+rax+00h]
0x18003cf98  lea     r8, [rsp+330h+TokenHandle]; TokenHandle
0x18003cf9d  mov     edx, 8Bh; DesiredAccess
0x18003cfa2  mov     rcx, rax; ProcessHandle
0x18003cfa5  call    cs:__imp_OpenProcessToken
0x18003cfac  nop     dword ptr [rax+rax+00h]
0x18003cfb1  test    eax, eax
0x18003cfb3  jnz     short loc_18003CFC4
0x18003cfb5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003cfba  mov     ebx, eax
0x18003cfbc  test    eax, eax
0x18003cfbe  js      loc_18003D0F4
0x18003cfc4  mov     rdx, [rsp+330h+TokenHandle]; ExistingTokenHandle
0x18003cfc9  lea     r8, [rsp+330h+hToken]; void **
0x18003cfce  mov     ecx, 2000h; nSubAuthority0
0x18003cfd3  call    ?_CreateRestrictedTokenFromSpecifiedToken@@YAJKPEAXPEAPEAX@Z; _CreateRestrictedTokenFromSpecifiedToken(ulong,void *,void * *)
0x18003cfd8  mov     rcx, [rsp+330h+TokenHandle]; hObject
0x18003cfdd  mov     ebx, eax
0x18003cfdf  call    cs:__imp_CloseHandle
0x18003cfe6  nop     dword ptr [rax+rax+00h]
0x18003cfeb  test    ebx, ebx
0x18003cfed  js      loc_18003D0F4
0x18003cff3  lea     rdx, [rbp+230h+CommandLine]; unsigned __int16 *
0x18003cff7  call    ?_GetCommandLine@@YAJPEBGPEAGI@Z; _GetCommandLine(ushort const *,ushort *,uint)
0x18003cffc  mov     ebx, eax
0x18003cffe  test    eax, eax
0x18003d000  js      loc_18003D0F4
0x18003d006  lea     r9, a22d8c27b47a148; "22d8c27b-47a1-48d1-ad08-7da7abd79617"
0x18003d00d  xor     r8d, r8d; bInitialState
0x18003d010  xor     edx, edx; bManualReset
0x18003d012  xor     ecx, ecx; lpEventAttributes
0x18003d014  call    cs:__imp_CreateEventW
0x18003d01b  nop     dword ptr [rax+rax+00h]
0x18003d020  mov     rdi, rax
0x18003d023  test    rax, rax
0x18003d026  jnz     short loc_18003D037
0x18003d028  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003d02d  mov     ebx, eax
0x18003d02f  test    eax, eax
0x18003d031  js      loc_18003D0F4
0x18003d037  xor     eax, eax
0x18003d039  mov     qword ptr [rbp+230h+StartupInfo.cb], 68h ; 'h'
0x18003d041  xorps   xmm0, xmm0
0x18003d044  mov     qword ptr [rbp+230h+ProcessInformation.dwProcessId], rax
0x18003d048  xor     edx, edx; Val
0x18003d04a  lea     rcx, [rbp+230h+StartupInfo.lpReserved]; void *
0x18003d04e  movups  xmmword ptr [rsp+330h+ProcessInformation.hProcess], xmm0
0x18003d053  lea     r8d, [rax+60h]; Size
0x18003d057  call    memset_0
0x18003d05c  mov     rcx, [rsp+330h+hToken]; hToken
0x18003d061  lea     rax, [rsp+330h+ProcessInformation]
0x18003d066  mov     [rsp+330h+lpProcessInformation], rax; lpProcessInformation
0x18003d06b  lea     r8, [rbp+230h+CommandLine]; lpCommandLine
0x18003d06f  lea     rax, [rbp+230h+StartupInfo]
0x18003d073  mov     [rbp+230h+StartupInfo.dwFlags], 80h
0x18003d07a  mov     [rsp+330h+lpStartupInfo], rax; lpStartupInfo
0x18003d07f  xor     r9d, r9d; lpProcessAttributes
0x18003d082  mov     [rsp+330h+lpCurrentDirectory], 0; lpCurrentDirectory
0x18003d08b  xor     edx, edx; lpApplicationName
0x18003d08d  mov     [rsp+330h+lpEnvironment], 0; lpEnvironment
0x18003d096  mov     [rsp+330h+dwCreationFlags], 0; dwCreationFlags
0x18003d09e  mov     [rsp+330h+bInheritHandles], 0; bInheritHandles
0x18003d0a6  mov     [rsp+330h+lpThreadAttributes], 0; lpThreadAttributes
0x18003d0af  call    cs:__imp_CreateProcessAsUserW
0x18003d0b6  nop     dword ptr [rax+rax+00h]
0x18003d0bb  test    eax, eax
0x18003d0bd  jz      short loc_18003D0C3
0x18003d0bf  xor     ebx, ebx
0x18003d0c1  jmp     short loc_18003D0CE
0x18003d0c3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003d0c8  mov     ebx, eax
0x18003d0ca  test    eax, eax
0x18003d0cc  js      short loc_18003D0E0
0x18003d0ce  mov     rax, [rsp+330h+ProcessInformation.hProcess]
0x18003d0d3  mov     rcx, [rsp+330h+ProcessInformation.hThread]
0x18003d0d8  mov     [rsi], rax
0x18003d0db  mov     [r14], rdi
0x18003d0de  jmp     short loc_18003D0E8
0x18003d0e0  test    rdi, rdi
0x18003d0e3  jz      short loc_18003D0F4
0x18003d0e5  mov     rcx, rdi; hObject
0x18003d0e8  call    cs:__imp_CloseHandle
0x18003d0ef  nop     dword ptr [rax+rax+00h]
0x18003d0f4  mov     eax, ebx
0x18003d0f6  mov     rcx, [rbp+230h+var_20]
0x18003d0fd  xor     rcx, rsp; StackCookie
0x18003d100  call    __security_check_cookie
0x18003d105  lea     r11, [rsp+330h+var_10]
0x18003d10d  mov     rbx, [r11+30h]
0x18003d111  mov     rsi, [r11+38h]
0x18003d115  mov     rsp, r11
0x18003d118  pop     r14
0x18003d11a  pop     rdi
0x18003d11b  pop     rbp
0x18003d11c  retn
```
