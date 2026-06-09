# ScRunAcceptBootPgm(void)

- ea: `0x140065d60`
- end: `0x140066108`
- name: `?ScRunAcceptBootPgm@@YAXXZ`
- size: `936`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400848e0`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x14000bcc4`
- `0x1400188fc`
- `0x14001f99c`
- `0x140021d08`
- `0x140064d34`
- `0x1400652c8`
- `0x140065d60`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140065db3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140065db3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065e04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065e12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065e04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006608a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006608a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140066080`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140066080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400660c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400660ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400660c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400660ca`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140065fd7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140065fd7`
- `ntdll!NtInitializeRegistry` at `0x140065e1f`
- `ntdll!NtInitializeRegistry` at `0x140065e1f`
- `ntdll!NtClose` at `0x140065f4f`
- `ntdll!NtClose` at `0x1400660ec`
- `ntdll!NtClose` at `0x140065f4f`
- `ntdll!NtClose` at `0x1400660ec`
- `ntdll!RtlNtStatusToDosError` at `0x140065f57`
- `ntdll!RtlNtStatusToDosError` at `0x1400660f4`
- `ntdll!RtlNtStatusToDosError` at `0x140065f57`
- `ntdll!RtlNtStatusToDosError` at `0x1400660f4`
- `ntdll!RtlFreeHeap` at `0x140065f6f`
- `ntdll!RtlFreeHeap` at `0x1400660e2`
- `ntdll!RtlFreeHeap` at `0x140065f6f`
- `ntdll!RtlFreeHeap` at `0x1400660e2`
- `ntdll!RtlAllocateHeap` at `0x140065ead`
- `ntdll!RtlAllocateHeap` at `0x140065ead`

## string_xrefs

- `0x140065f05`: `ImagePath`

## pseudocode

```c
void ScRunAcceptBootPgm(void)
{
  __int64 v0; // r8
  ULONG v1; // eax
  unsigned __int8 *Heap; // rax
  unsigned int *v3; // r8
  WCHAR *v4; // rdi
  unsigned int v5; // eax
  NTSTATUS v6; // eax
  unsigned int v7; // ecx
  const WCHAR *v8; // rsi
  DWORD LastError; // eax
  NTSTATUS v10; // eax
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-59h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-39h] BYREF
  unsigned int CommandLine; // [rsp+110h] [rbp+67h] BYREF
  unsigned int v14; // [rsp+118h] [rbp+6Fh] BYREF
  HANDLE Handle; // [rsp+120h] [rbp+77h] BYREF

  Handle = 0;
  CommandLine = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  if ( (MEMORY[0x7FFE02F0] & 0x10) != 0 )
  {
    ScDelayAndLowerCurrentThreadPriority();
    EnterCriticalSection(&ScBootConfigCriticalSection);
    ScGlobalLastKnownGood |= 4u;
    if ( (ScGlobalLastKnownGood & 8) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->UserInfo) & 0x20000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->StubInfo, 60, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
      }
      ScAcceptTheBoot();
      LeaveCriticalSection(&ScBootConfigCriticalSection);
      return;
    }
    LeaveCriticalSection(&ScBootConfigCriticalSection);
  }
  else
  {
    NtInitializeRegistry(0x1001u);
  }
  v1 = ScRegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\BootVerificationProgram",
         v0,
         0x20019u,
         (HKEY *)&Handle);
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_Sd(
        WPP_GLOBAL_Control->StubInfo,
        61,
        (unsigned int)WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids,
        (unsigned int)L"System\\CurrentControlSet\\Control\\BootVerificationProgram",
        v1);
    return;
  }
  v14 = 520;
  Heap = (unsigned __int8 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x410u);
  v4 = (WCHAR *)Heap;
  if ( Heap )
  {
    v5 = ScRegQueryValueExW((HKEY)Handle, L"ImagePath", v3, &CommandLine, Heap, &v14);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 63, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, v5);
      v6 = NtClose(Handle);
      RtlNtStatusToDosError(v6);
LABEL_22:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
      return;
    }
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 64, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, v4);
    v7 = CommandLine;
    if ( CommandLine - 1 <= 1 )
    {
      LOWORD(CommandLine) = 0;
      if ( v7 == 2 )
      {
        v8 = v4 + 260;
        if ( ExpandEnvironmentStringsW(v4, v4 + 260, 0x104u) > 0x104 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->StubInfo, 65, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
          }
          goto LABEL_22;
        }
      }
      else
      {
        v8 = v4;
      }
      StartupInfo.cb = 104;
      memset(&StartupInfo.lpReserved, 0, 52);
      *(_QWORD *)&StartupInfo.dwFlags = 128;
      StartupInfo.lpReserved2 = 0;
      if ( CreateProcessW(v8, (LPWSTR)&CommandLine, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
      {
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
      }
      else
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 66, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids, LastError);
        }
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    v10 = NtClose(Handle);
    RtlNtStatusToDosError(v10);
    return;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->StubInfo, 62, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids);
}

```

## disassembly

```asm
0x140065d60  push    rbp
0x140065d62  push    rbx
0x140065d63  push    rsi
0x140065d64  push    rdi
0x140065d65  push    r15
0x140065d67  lea     rbp, [rsp-37h]
0x140065d6c  sub     rsp, 0E0h
0x140065d73  xor     r15d, r15d
0x140065d76  lea     rcx, [rbp+57h+StartupInfo]; void *
0x140065d7a  xorps   xmm0, xmm0
0x140065d7d  mov     [rbp+57h+Handle], r15
0x140065d81  xor     eax, eax
0x140065d83  mov     [rbp+57h+CommandLine], r15d
0x140065d87  xor     edx, edx; Val
0x140065d89  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x140065d8d  lea     r8d, [r15+68h]; Size
0x140065d91  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x140065d95  call    memset
0x140065d9a  test    byte ptr ds:7FFE02F0h, 10h
0x140065da2  jz      short loc_140065E1A
0x140065da4  call    ?ScDelayAndLowerCurrentThreadPriority@@YAXK@Z; ScDelayAndLowerCurrentThreadPriority(ulong)
0x140065da9  lea     rdi, ?ScBootConfigCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ScBootConfigCriticalSection
0x140065db0  mov     rcx, rdi; lpCriticalSection
0x140065db3  call    cs:__imp_EnterCriticalSection
0x140065db9  mov     eax, cs:?ScGlobalLastKnownGood@@3KA; ulong ScGlobalLastKnownGood
0x140065dbf  or      eax, 4
0x140065dc2  mov     cs:?ScGlobalLastKnownGood@@3KA, eax; ulong ScGlobalLastKnownGood
0x140065dc8  test    al, 8
0x140065dca  jz      short loc_140065E0F
0x140065dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x140065dd3  lea     rbx, WPP_GLOBAL_Control
0x140065dda  cmp     rcx, rbx
0x140065ddd  jz      short loc_140065DFC
0x140065ddf  test    dword ptr [rcx+1Ch], 20000h
0x140065de6  jz      short loc_140065DFC
0x140065de8  mov     rcx, [rcx+10h]
0x140065dec  lea     edx, [r15+3Ch]
0x140065df0  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140065df7  call    WPP_SF_
0x140065dfc  call    ?ScAcceptTheBoot@@YAKXZ; ScAcceptTheBoot(void)
0x140065e01  mov     rcx, rdi; lpCriticalSection
0x140065e04  call    cs:__imp_LeaveCriticalSection
0x140065e0a  jmp     loc_1400660FA
0x140065e0f  mov     rcx, rdi; lpCriticalSection
0x140065e12  call    cs:__imp_LeaveCriticalSection
0x140065e18  jmp     short loc_140065E25
0x140065e1a  mov     ecx, 1001h; Flag
0x140065e1f  call    cs:__imp_NtInitializeRegistry
0x140065e25  lea     rax, [rbp+57h+Handle]
0x140065e29  mov     r9d, 20019h; unsigned int
0x140065e2f  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Control\\Boo"...
0x140065e36  mov     qword ptr [rsp+100h+bInheritHandles], rax; HKEY *
0x140065e3b  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140065e42  call    ?ScRegOpenKeyExW@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ScRegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140065e47  test    eax, eax
0x140065e49  jz      short loc_140065E91
0x140065e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140065e52  lea     rbx, WPP_GLOBAL_Control
0x140065e59  cmp     rcx, rbx
0x140065e5c  jz      loc_1400660FA
0x140065e62  test    byte ptr [rcx+1Ch], 4
0x140065e66  jz      loc_1400660FA
0x140065e6c  mov     rcx, [rcx+10h]
0x140065e70  lea     r9, aSystemCurrentc_16; "System\\CurrentControlSet\\Control\\Boo"...
0x140065e77  mov     edx, 3Dh ; '='
0x140065e7c  mov     [rsp+100h+bInheritHandles], eax
0x140065e80  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140065e87  call    WPP_SF_Sd
0x140065e8c  jmp     loc_1400660FA
0x140065e91  mov     rcx, gs:60h
0x140065e9a  xor     edx, edx; Flags
0x140065e9c  mov     r8d, 410h; Size
0x140065ea2  mov     [rbp+57h+arg_8], 208h
0x140065ea9  mov     rcx, [rcx+30h]; HeapHandle
0x140065ead  call    cs:__imp_RtlAllocateHeap
0x140065eb3  mov     rdi, rax
0x140065eb6  test    rax, rax
0x140065eb9  jnz     short loc_140065EF4
0x140065ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x140065ec2  lea     rbx, WPP_GLOBAL_Control
0x140065ec9  cmp     rcx, rbx
0x140065ecc  jz      loc_1400660FA
0x140065ed2  test    byte ptr [rcx+1Ch], 4
0x140065ed6  jz      loc_1400660FA
0x140065edc  mov     rcx, [rcx+10h]
0x140065ee0  lea     edx, [rax+3Eh]
0x140065ee3  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140065eea  call    WPP_SF_
0x140065eef  jmp     loc_1400660FA
0x140065ef4  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140065ef8  lea     rax, [rbp+57h+arg_8]
0x140065efc  mov     qword ptr [rsp+100h+dwCreationFlags], rax; unsigned int *
0x140065f01  lea     r9, [rbp+57h+CommandLine]; unsigned int *
0x140065f05  lea     rdx, aImagepath_0; "ImagePath"
0x140065f0c  mov     qword ptr [rsp+100h+bInheritHandles], rdi; unsigned __int8 *
0x140065f11  call    ?ScRegQueryValueExW@@YAKPEAUHKEY__@@PEBGPEAK2PEAE2@Z; ScRegQueryValueExW(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *)
0x140065f16  test    eax, eax
0x140065f18  jz      short loc_140065F7A
0x140065f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140065f21  lea     rbx, WPP_GLOBAL_Control
0x140065f28  cmp     rcx, rbx
0x140065f2b  jz      short loc_140065F4B
0x140065f2d  test    byte ptr [rcx+1Ch], 4
0x140065f31  jz      short loc_140065F4B
0x140065f33  mov     rcx, [rcx+10h]
0x140065f37  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140065f3e  mov     edx, 3Fh ; '?'
0x140065f43  mov     r9d, eax
0x140065f46  call    WPP_SF_d
0x140065f4b  mov     rcx, [rbp+57h+Handle]; Handle
0x140065f4f  call    cs:__imp_NtClose
0x140065f55  mov     ecx, eax; Status
0x140065f57  call    cs:__imp_RtlNtStatusToDosError
0x140065f5d  mov     rcx, gs:60h
0x140065f66  mov     r8, rdi; P
0x140065f69  xor     edx, edx; Flags
0x140065f6b  mov     rcx, [rcx+30h]; HeapHandle
0x140065f6f  call    cs:__imp_RtlFreeHeap
0x140065f75  jmp     loc_1400660FA
0x140065f7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140065f81  lea     rbx, WPP_GLOBAL_Control
0x140065f88  cmp     rcx, rbx
0x140065f8b  jz      short loc_140065FAB
0x140065f8d  test    byte ptr [rcx+1Ch], 4
0x140065f91  jz      short loc_140065FAB
0x140065f93  mov     rcx, [rcx+10h]
0x140065f97  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140065f9e  mov     edx, 40h ; '@'
0x140065fa3  mov     r9, rdi
0x140065fa6  call    WPP_SF_S
0x140065fab  mov     ecx, [rbp+57h+CommandLine]
0x140065fae  lea     eax, [rcx-1]
0x140065fb1  cmp     eax, 1
0x140065fb4  ja      loc_1400660D0
0x140065fba  mov     word ptr [rbp+57h+CommandLine], r15w
0x140065fbf  cmp     ecx, 2
0x140065fc2  jnz     short loc_140066018
0x140065fc4  lea     rsi, [rdi+208h]
0x140065fcb  mov     r8d, 104h; nSize
0x140065fd1  mov     rdx, rsi; lpDst
0x140065fd4  mov     rcx, rdi; lpSrc
0x140065fd7  call    cs:__imp_ExpandEnvironmentStringsW
0x140065fdd  cmp     eax, 104h
0x140065fe2  jbe     short loc_14006601B
0x140065fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x140065feb  cmp     rcx, rbx
0x140065fee  jz      loc_140065F5D
0x140065ff4  test    byte ptr [rcx+1Ch], 1
0x140065ff8  jz      loc_140065F5D
0x140065ffe  mov     rcx, [rcx+10h]
0x140066002  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x140066009  mov     edx, 41h ; 'A'
0x14006600e  call    WPP_SF_
0x140066013  jmp     loc_140065F5D
0x140066018  mov     rsi, rdi
0x14006601b  lea     rax, [rbp+57h+ProcessInformation]
0x14006601f  mov     [rbp+57h+StartupInfo.cb], 68h ; 'h'
0x140066026  mov     [rsp+100h+lpProcessInformation], rax; lpProcessInformation
0x14006602b  lea     rdx, [rbp+57h+CommandLine]; lpCommandLine
0x14006602f  lea     rax, [rbp+57h+StartupInfo]
0x140066033  mov     [rbp+57h+StartupInfo.lpReserved], r15
0x140066037  mov     [rsp+100h+lpStartupInfo], rax; lpStartupInfo
0x14006603c  xorps   xmm0, xmm0
0x14006603f  mov     [rsp+100h+lpCurrentDirectory], r15; lpCurrentDirectory
0x140066044  xor     r9d, r9d; lpThreadAttributes
0x140066047  mov     [rsp+100h+lpEnvironment], r15; lpEnvironment
0x14006604c  xor     r8d, r8d; lpProcessAttributes
0x14006604f  mov     [rsp+100h+dwCreationFlags], 8; dwCreationFlags
0x140066057  mov     rcx, rsi; lpApplicationName
0x14006605a  mov     [rsp+100h+bInheritHandles], r15d; bInheritHandles
0x14006605f  movdqa  xmmword ptr [rbp+57h+StartupInfo.lpDesktop], xmm0
0x140066064  mov     qword ptr [rbp+57h+StartupInfo.dwX], r15
0x140066068  mov     qword ptr [rbp+57h+StartupInfo.dwXSize], r15
0x14006606c  mov     qword ptr [rbp+57h+StartupInfo.dwXCountChars], r15
0x140066070  mov     [rbp+57h+StartupInfo.dwFillAttribute], r15d
0x140066074  mov     qword ptr [rbp+57h+StartupInfo.dwFlags], 80h
0x14006607c  mov     [rbp+57h+StartupInfo.lpReserved2], r15
0x140066080  call    cs:__imp_CreateProcessW
0x140066086  test    eax, eax
0x140066088  jnz     short loc_1400660BC
0x14006608a  call    cs:__imp_GetLastError
0x140066090  mov     rcx, cs:WPP_GLOBAL_Control
0x140066097  cmp     rcx, rbx
0x14006609a  jz      short loc_1400660D0
0x14006609c  test    byte ptr [rcx+1Ch], 1
0x1400660a0  jz      short loc_1400660D0
0x1400660a2  mov     rcx, [rcx+10h]
0x1400660a6  lea     r8, WPP_1af9861440053f7472b6b75dd72fc49f_Traceguids
0x1400660ad  mov     edx, 42h ; 'B'
0x1400660b2  mov     r9d, eax
0x1400660b5  call    WPP_SF_d
0x1400660ba  jmp     short loc_1400660D0
0x1400660bc  mov     rcx, [rbp+57h+ProcessInformation.hProcess]; hObject
0x1400660c0  call    cs:__imp_CloseHandle
0x1400660c6  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x1400660ca  call    cs:__imp_CloseHandle
0x1400660d0  mov     rcx, gs:60h
0x1400660d9  mov     r8, rdi; P
0x1400660dc  xor     edx, edx; Flags
0x1400660de  mov     rcx, [rcx+30h]; HeapHandle
0x1400660e2  call    cs:__imp_RtlFreeHeap
0x1400660e8  mov     rcx, [rbp+57h+Handle]; Handle
0x1400660ec  call    cs:__imp_NtClose
0x1400660f2  mov     ecx, eax; Status
0x1400660f4  call    cs:__imp_RtlNtStatusToDosError
0x1400660fa  add     rsp, 0E0h
0x140066101  pop     r15
0x140066103  pop     rdi
0x140066104  pop     rsi
0x140066105  pop     rbx
0x140066106  pop     rbp
0x140066107  retn
```
