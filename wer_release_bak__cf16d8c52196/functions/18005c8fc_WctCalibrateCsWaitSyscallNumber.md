# WctCalibrateCsWaitSyscallNumber

- ea: `0x18005c8fc`
- end: `0x18005cb09`
- name: `WctCalibrateCsWaitSyscallNumber`
- size: `525`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18005ec8c`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x180007e34`
- `0x18001fe24`
- `0x180050db0`
- `0x18005c8fc`
- `0x18005f104`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005ca12`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005ca12`
- `ntdll!NtQueryInformationThread` at `0x18005ca5d`
- `ntdll!NtQueryInformationThread` at `0x18005ca5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c9ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005c9ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ca7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ca9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ca7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ca9d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005c9e5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005c9e5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ca91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ca91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005c985`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005c985`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005ca86`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005ca86`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005caa7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005caa7`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v2);
    v1 = v2;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4c32fa7a72a13340317baef891270170_Traceguids, 0xFFFFFFFFLL);
    v1 = -1;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v8);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&ThreadHandle);
  return v1;
}

```

## disassembly

```asm
0x18005c8fc  push    rbp
0x18005c8fe  push    rbx
0x18005c8ff  push    rsi
0x18005c900  push    rdi
0x18005c901  push    r12
0x18005c903  push    r14
0x18005c905  lea     rbp, [rsp-2Fh]
0x18005c90a  sub     rsp, 0A8h
0x18005c911  mov     rax, cs:__security_cookie
0x18005c918  xor     rax, rsp
0x18005c91b  mov     [rbp+57h+var_38], rax
0x18005c91f  xorps   xmm0, xmm0
0x18005c922  xor     eax, eax
0x18005c924  xor     r14d, r14d
0x18005c927  mov     [rbp+57h+var_40], rax
0x18005c92b  mov     [rbp+57h+ReturnLength], r14d
0x18005c92f  mov     [rbp+57h+ThreadId], r14d
0x18005c933  mov     [rbp+57h+ThreadHandle], r14
0x18005c937  mov     [rbp+57h+var_98], r14
0x18005c93b  movups  [rbp+57h+ThreadInformation], xmm0
0x18005c93f  mov     [rbp+57h+hEvent], rax
0x18005c943  movups  xmmword ptr [rbp+57h+CriticalSection], xmm0
0x18005c947  movups  xmmword ptr [rbp+57h+CriticalSection+10h], xmm0
0x18005c94b  movups  xmmword ptr [rbp+57h+CriticalSection+20h], xmm0
0x18005c94f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c956  lea     r12, WPP_GLOBAL_Control
0x18005c95d  cmp     rcx, r12
0x18005c960  jz      short loc_18005C97B
0x18005c962  test    byte ptr [rcx+1Ch], 4
0x18005c966  jz      short loc_18005C97B
0x18005c968  mov     rcx, [rcx+10h]
0x18005c96c  lea     edx, [rax+12h]
0x18005c96f  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005c976  call    WPP_SF_
0x18005c97b  xor     r9d, r9d; lpName
0x18005c97e  xor     r8d, r8d; bInitialState
0x18005c981  xor     edx, edx; bManualReset
0x18005c983  xor     ecx, ecx; lpEventAttributes
0x18005c985  call    cs:__imp_CreateEventW
0x18005c98b  mov     rdx, rax
0x18005c98e  lea     rcx, [rbp+57h+var_98]
0x18005c992  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005c997  mov     rax, [rbp+57h+var_98]
0x18005c99b  lea     rcx, [rax+1]
0x18005c99f  cmp     rcx, 1
0x18005c9a3  ja      short loc_18005C9D8
0x18005c9a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c9ac  cmp     rcx, r12
0x18005c9af  jz      short loc_18005C9D0
0x18005c9b1  test    byte ptr [rcx+1Ch], 4
0x18005c9b5  jz      short loc_18005C9D0
0x18005c9b7  mov     rcx, [rcx+10h]
0x18005c9bb  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005c9c2  mov     edx, 13h
0x18005c9c7  or      r9d, 0FFFFFFFFh
0x18005c9cb  call    WPP_SF_d
0x18005c9d0  or      edi, 0FFFFFFFFh
0x18005c9d3  jmp     loc_18005CAD9
0x18005c9d8  or      edi, 0FFFFFFFFh
0x18005c9db  mov     [rbp+57h+hEvent], rax
0x18005c9df  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18005c9e3  mov     esi, edi
0x18005c9e5  call    cs:__imp_InitializeCriticalSection
0x18005c9eb  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18005c9ef  call    cs:__imp_EnterCriticalSection
0x18005c9f5  lea     rax, [rbp+57h+ThreadId]
0x18005c9f9  xor     edx, edx; dwStackSize
0x18005c9fb  mov     [rsp+0D0h+lpThreadId], rax; lpThreadId
0x18005ca00  lea     r9, [rbp+57h+CriticalSection]; lpParameter
0x18005ca04  lea     r8, WctSyscallCalibratorThreadProc; lpStartAddress
0x18005ca0b  mov     [rsp+0D0h+dwCreationFlags], r14d; dwCreationFlags
0x18005ca10  xor     ecx, ecx; lpThreadAttributes
0x18005ca12  call    cs:__imp_CreateThread
0x18005ca18  mov     rdx, rax
0x18005ca1b  lea     rcx, [rbp+57h+ThreadHandle]
0x18005ca1f  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18005ca24  mov     rbx, [rbp+57h+ThreadHandle]
0x18005ca28  lea     rax, [rbx+1]
0x18005ca2c  cmp     rax, 1
0x18005ca30  jbe     short loc_18005CA99
0x18005ca32  mov     ecx, [rbp+57h+ThreadId]; unsigned int
0x18005ca35  mov     edx, 25h ; '%'
0x18005ca3a  call    WctWaitUntilThreadIsBlocked
0x18005ca3f  test    eax, eax
0x18005ca41  jz      short loc_18005CA78
0x18005ca43  mov     r9d, 18h; ThreadInformationLength
0x18005ca49  lea     rax, [rbp+57h+ReturnLength]
0x18005ca4d  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18005ca51  mov     qword ptr [rsp+0D0h+dwCreationFlags], rax; ReturnLength
0x18005ca56  mov     rcx, rbx; ThreadHandle
0x18005ca59  lea     edx, [r9-3]; ThreadInformationClass
0x18005ca5d  call    cs:__imp_NtQueryInformationThread
0x18005ca63  test    eax, eax
0x18005ca65  js      short loc_18005CA78
0x18005ca67  cmp     [rbp+57h+ReturnLength], 18h
0x18005ca6b  jnz     short loc_18005CA78
0x18005ca6d  movzx   eax, word ptr [rbp+57h+ThreadInformation+8]
0x18005ca71  test    ax, ax
0x18005ca74  jz      short loc_18005CA78
0x18005ca76  mov     esi, eax
0x18005ca78  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18005ca7c  call    cs:__imp_LeaveCriticalSection
0x18005ca82  mov     rcx, [rbp+57h+hEvent]; hEvent
0x18005ca86  call    cs:__imp_SetEvent
0x18005ca8c  mov     edx, edi; dwMilliseconds
0x18005ca8e  mov     rcx, rbx; hHandle
0x18005ca91  call    cs:__imp_WaitForSingleObject
0x18005ca97  jmp     short loc_18005CAA3
0x18005ca99  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18005ca9d  call    cs:__imp_LeaveCriticalSection
0x18005caa3  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18005caa7  call    cs:__imp_DeleteCriticalSection
0x18005caad  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cab4  cmp     rcx, r12
0x18005cab7  jz      short loc_18005CAD7
0x18005cab9  test    byte ptr [rcx+1Ch], 4
0x18005cabd  jz      short loc_18005CAD7
0x18005cabf  mov     rcx, [rcx+10h]
0x18005cac3  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005caca  mov     edx, 14h
0x18005cacf  mov     r9d, esi
0x18005cad2  call    WPP_SF_d
0x18005cad7  mov     edi, esi
0x18005cad9  lea     rcx, [rbp+57h+var_98]
0x18005cadd  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005cae2  lea     rcx, [rbp+57h+ThreadHandle]
0x18005cae6  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18005caeb  mov     eax, edi
0x18005caed  mov     rcx, [rbp+57h+var_38]
0x18005caf1  xor     rcx, rsp; StackCookie
0x18005caf4  call    __security_check_cookie
0x18005caf9  add     rsp, 0A8h
0x18005cb00  pop     r14
0x18005cb02  pop     r12
0x18005cb04  pop     rdi
0x18005cb05  pop     rsi
0x18005cb06  pop     rbx
0x18005cb07  pop     rbp
0x18005cb08  retn
```
