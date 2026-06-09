# WctCalibrateCsWaitSyscallNumber

- ea: `0x18005edfc`
- end: `0x18005f046`
- name: `WctCalibrateCsWaitSyscallNumber`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180061330`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180008004`
- `0x180020680`
- `0x180053300`
- `0x18005edfc`
- `0x18006180c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005ef24`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005ef24`
- `ntdll!NtQueryInformationThread` at `0x18005ef75`
- `ntdll!NtQueryInformationThread` at `0x18005ef75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005eefb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005eefb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ef9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005efcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ef9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005efcd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005eeeb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005eeeb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005efbb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005efbb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005ee85`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005ee85`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005efaa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005efaa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005efdd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005efdd`

## pseudocode

```c
__int64 WctCalibrateCsWaitSyscallNumber()
{
  HANDLE EventW; // rax
  unsigned int v1; // edi
  unsigned int v2; // esi
  HANDLE v3; // rax
  HANDLE v4; // rbx
  DWORD ThreadId; // [rsp+30h] [rbp-49h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-45h] BYREF
  void *v8; // [rsp+38h] [rbp-41h] BYREF
  HANDLE ThreadHandle; // [rsp+40h] [rbp-39h] BYREF
  _QWORD CriticalSection[6]; // [rsp+48h] [rbp-31h] BYREF
  HANDLE hEvent; // [rsp+78h] [rbp-1h]
  __int128 ThreadInformation; // [rsp+80h] [rbp+7h] BYREF
  __int64 v13; // [rsp+90h] [rbp+17h]

  v13 = 0;
  ReturnLength = 0;
  ThreadId = 0;
  ThreadHandle = 0;
  v8 = 0;
  ThreadInformation = 0;
  hEvent = 0;
  memset(CriticalSection, 0, sizeof(CriticalSection));
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  EventW = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&v8, EventW);
  if ( (unsigned __int64)v8 + 1 > 1 )
  {
    hEvent = v8;
    v2 = -1;
    InitializeCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    EnterCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    v3 = CreateThread(0, 0, WctSyscallCalibratorThreadProc, CriticalSection, 0, &ThreadId);
    tlx::unique_any<tlx::file_handle_traits>::reset(&ThreadHandle, v3);
    v4 = ThreadHandle;
    if ( (unsigned __int64)ThreadHandle + 1 <= 1 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    }
    else
    {
      if ( (unsigned int)WctWaitUntilThreadIsBlocked(ThreadId)
        && NtQueryInformationThread(v4, ThreadLastSystemCall, &ThreadInformation, 0x18u, &ReturnLength) >= 0
        && ReturnLength == 24
        && WORD4(ThreadInformation) )
      {
        v2 = WORD4(ThreadInformation);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
      SetEvent(hEvent);
      WaitForSingleObject(v4, 0xFFFFFFFF);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v2);
    v1 = v2;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, 0xFFFFFFFFLL);
    v1 = -1;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v8);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&ThreadHandle);
  return v1;
}

```

## disassembly

```asm
0x18005edfc  push    rbp
0x18005edfe  push    rbx
0x18005edff  push    rsi
0x18005ee00  push    rdi
0x18005ee01  push    r12
0x18005ee03  push    r14
0x18005ee05  lea     rbp, [rsp-2Fh]
0x18005ee0a  sub     rsp, 0A8h
0x18005ee11  mov     rax, cs:__security_cookie
0x18005ee18  xor     rax, rsp
0x18005ee1b  mov     [rbp+57h+var_38], rax
0x18005ee1f  xorps   xmm0, xmm0
0x18005ee22  xor     eax, eax
0x18005ee24  xor     r14d, r14d
0x18005ee27  mov     [rbp+57h+var_40], rax
0x18005ee2b  mov     [rbp+57h+ReturnLength], r14d
0x18005ee2f  mov     [rbp+57h+ThreadId], r14d
0x18005ee33  mov     [rbp+57h+ThreadHandle], r14
0x18005ee37  mov     [rbp+57h+var_98], r14
0x18005ee3b  movups  [rbp+57h+ThreadInformation], xmm0
0x18005ee3f  mov     [rbp+57h+hEvent], rax
0x18005ee43  movups  xmmword ptr [rbp+57h+CriticalSection], xmm0
0x18005ee47  movups  xmmword ptr [rbp+57h+CriticalSection+10h], xmm0
0x18005ee4b  movups  xmmword ptr [rbp+57h+CriticalSection+20h], xmm0
0x18005ee4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ee56  lea     r12, WPP_GLOBAL_Control
0x18005ee5d  cmp     rcx, r12
0x18005ee60  jz      short loc_18005EE7B
0x18005ee62  test    byte ptr [rcx+1Ch], 4
0x18005ee66  jz      short loc_18005EE7B
0x18005ee68  mov     rcx, [rcx+10h]
0x18005ee6c  lea     edx, [rax+12h]
0x18005ee6f  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005ee76  call    WPP_SF_
0x18005ee7b  xor     r9d, r9d; lpName
0x18005ee7e  xor     r8d, r8d; bInitialState
0x18005ee81  xor     edx, edx; bManualReset
0x18005ee83  xor     ecx, ecx; lpEventAttributes
0x18005ee85  call    cs:__imp_CreateEventW
0x18005ee8c  nop     dword ptr [rax+rax+00h]
0x18005ee91  mov     rdx, rax
0x18005ee94  lea     rcx, [rbp+57h+var_98]
0x18005ee98  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005ee9d  mov     rax, [rbp+57h+var_98]
0x18005eea1  lea     rcx, [rax+1]
0x18005eea5  cmp     rcx, 1
0x18005eea9  ja      short loc_18005EEDE
0x18005eeab  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eeb2  cmp     rcx, r12
0x18005eeb5  jz      short loc_18005EED6
0x18005eeb7  test    byte ptr [rcx+1Ch], 4
0x18005eebb  jz      short loc_18005EED6
0x18005eebd  mov     rcx, [rcx+10h]
0x18005eec1  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005eec8  mov     edx, 13h
0x18005eecd  or      r9d, 0FFFFFFFFh
0x18005eed1  call    WPP_SF_d
0x18005eed6  or      edi, 0FFFFFFFFh
0x18005eed9  jmp     loc_18005F015
0x18005eede  or      edi, 0FFFFFFFFh
0x18005eee1  mov     [rbp+57h+hEvent], rax
0x18005eee5  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18005eee9  mov     esi, edi
0x18005eeeb  call    cs:__imp_InitializeCriticalSection
0x18005eef2  nop     dword ptr [rax+rax+00h]
0x18005eef7  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18005eefb  call    cs:__imp_EnterCriticalSection
0x18005ef02  nop     dword ptr [rax+rax+00h]
0x18005ef07  lea     rax, [rbp+57h+ThreadId]
0x18005ef0b  xor     edx, edx; dwStackSize
0x18005ef0d  mov     [rsp+0D0h+lpThreadId], rax; lpThreadId
0x18005ef12  lea     r9, [rbp+57h+CriticalSection]; lpParameter
0x18005ef16  lea     r8, WctSyscallCalibratorThreadProc; lpStartAddress
0x18005ef1d  mov     [rsp+0D0h+dwCreationFlags], r14d; dwCreationFlags
0x18005ef22  xor     ecx, ecx; lpThreadAttributes
0x18005ef24  call    cs:__imp_CreateThread
0x18005ef2b  nop     dword ptr [rax+rax+00h]
0x18005ef30  mov     rdx, rax
0x18005ef33  lea     rcx, [rbp+57h+ThreadHandle]
0x18005ef37  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005ef3c  mov     rbx, [rbp+57h+ThreadHandle]
0x18005ef40  lea     rax, [rbx+1]
0x18005ef44  cmp     rax, 1
0x18005ef48  jbe     short loc_18005EFC9
0x18005ef4a  mov     ecx, [rbp+57h+ThreadId]; unsigned int
0x18005ef4d  mov     edx, 25h ; '%'
0x18005ef52  call    WctWaitUntilThreadIsBlocked
0x18005ef57  test    eax, eax
0x18005ef59  jz      short loc_18005EF96
0x18005ef5b  mov     r9d, 18h; ThreadInformationLength
0x18005ef61  lea     rax, [rbp+57h+ReturnLength]
0x18005ef65  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18005ef69  mov     qword ptr [rsp+0D0h+dwCreationFlags], rax; ReturnLength
0x18005ef6e  mov     rcx, rbx; ThreadHandle
0x18005ef71  lea     edx, [r9-3]; ThreadInformationClass
0x18005ef75  call    cs:__imp_NtQueryInformationThread
0x18005ef7c  nop     dword ptr [rax+rax+00h]
0x18005ef81  test    eax, eax
0x18005ef83  js      short loc_18005EF96
0x18005ef85  cmp     [rbp+57h+ReturnLength], 18h
0x18005ef89  jnz     short loc_18005EF96
0x18005ef8b  movzx   eax, word ptr [rbp+57h+ThreadInformation+8]
0x18005ef8f  test    ax, ax
0x18005ef92  jz      short loc_18005EF96
0x18005ef94  mov     esi, eax
0x18005ef96  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18005ef9a  call    cs:__imp_LeaveCriticalSection
0x18005efa1  nop     dword ptr [rax+rax+00h]
0x18005efa6  mov     rcx, [rbp+57h+hEvent]; hEvent
0x18005efaa  call    cs:__imp_SetEvent
0x18005efb1  nop     dword ptr [rax+rax+00h]
0x18005efb6  mov     edx, edi; dwMilliseconds
0x18005efb8  mov     rcx, rbx; hHandle
0x18005efbb  call    cs:__imp_WaitForSingleObject
0x18005efc2  nop     dword ptr [rax+rax+00h]
0x18005efc7  jmp     short loc_18005EFD9
0x18005efc9  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18005efcd  call    cs:__imp_LeaveCriticalSection
0x18005efd4  nop     dword ptr [rax+rax+00h]
0x18005efd9  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18005efdd  call    cs:__imp_DeleteCriticalSection
0x18005efe4  nop     dword ptr [rax+rax+00h]
0x18005efe9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eff0  cmp     rcx, r12
0x18005eff3  jz      short loc_18005F013
0x18005eff5  test    byte ptr [rcx+1Ch], 4
0x18005eff9  jz      short loc_18005F013
0x18005effb  mov     rcx, [rcx+10h]
0x18005efff  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005f006  mov     edx, 14h
0x18005f00b  mov     r9d, esi
0x18005f00e  call    WPP_SF_d
0x18005f013  mov     edi, esi
0x18005f015  lea     rcx, [rbp+57h+var_98]
0x18005f019  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005f01e  lea     rcx, [rbp+57h+ThreadHandle]
0x18005f022  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005f027  mov     eax, edi
0x18005f029  mov     rcx, [rbp+57h+var_38]
0x18005f02d  xor     rcx, rsp; StackCookie
0x18005f030  call    __security_check_cookie
0x18005f035  add     rsp, 0A8h
0x18005f03c  pop     r14
0x18005f03e  pop     r12
0x18005f040  pop     rdi
0x18005f041  pop     rsi
0x18005f042  pop     rbx
0x18005f043  pop     rbp
0x18005f044  retn
```
