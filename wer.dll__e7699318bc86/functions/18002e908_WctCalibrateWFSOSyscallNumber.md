# WctCalibrateWFSOSyscallNumber

- ea: `0x18002e908`
- end: `0x18002eab7`
- name: `WctCalibrateWFSOSyscallNumber`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18005ec8c`

## callees

- `0x180004bb4`
- `0x180007e34`
- `0x18001fe24`
- `0x18002e908`
- `0x180050db0`
- `0x18005f104`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002e9cf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002e9cf`
- `ntdll!NtQueryInformationThread` at `0x18002ea1a`
- `ntdll!NtQueryInformationThread` at `0x18002ea1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ea45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ea45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e997`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002e997`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002ea39`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002ea39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ea7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ea91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ea7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ea91`

## pseudocode

```c
__int64 WctCalibrateWFSOSyscallNumber()
{
  HANDLE v0; // rbx
  unsigned int v1; // edi
  HANDLE EventW; // rax
  void *v3; // rsi
  unsigned __int64 v4; // r14
  HANDLE v5; // rax
  DWORD ThreadId; // [rsp+30h] [rbp-49h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-45h] BYREF
  HANDLE ThreadHandle; // [rsp+38h] [rbp-41h] BYREF
  _OWORD Parameter[3]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v11; // [rsp+70h] [rbp-9h]
  __int128 ThreadInformation; // [rsp+78h] [rbp-1h] BYREF
  __int64 v13; // [rsp+88h] [rbp+Fh]

  ReturnLength = 0;
  v0 = 0;
  v13 = 0;
  ThreadHandle = 0;
  v1 = -1;
  ThreadInformation = 0;
  ThreadId = 0;
  memset(Parameter, 0, sizeof(Parameter));
  v11 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  EventW = CreateEventW(0, 1, 0, 0);
  v3 = EventW;
  v4 = (unsigned __int64)EventW + 1;
  if ( (unsigned __int64)EventW + 1 > 1 )
  {
    *(_QWORD *)&Parameter[0] = EventW;
    v5 = CreateThread(0, 0, WctSyscallCalibratorThreadProc, Parameter, 0, &ThreadId);
    tlx::unique_any<tlx::file_handle_traits>::reset(&ThreadHandle, v5);
    v0 = ThreadHandle;
    if ( (unsigned __int64)ThreadHandle + 1 > 1 )
    {
      if ( (unsigned int)WctWaitUntilThreadIsBlocked(ThreadId)
        && NtQueryInformationThread(v0, ThreadLastSystemCall, &ThreadInformation, 0x18u, &ReturnLength) >= 0
        && ReturnLength == 24
        && WORD4(ThreadInformation) )
      {
        v1 = WORD4(ThreadInformation);
      }
      SetEvent(*(HANDLE *)&Parameter[0]);
      WaitForSingleObject(v0, 0xFFFFFFFF);
    }
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v1);
  if ( v4 > 1 )
    CloseHandle(v3);
  if ( (unsigned __int64)v0 + 1 > 1 )
    CloseHandle(v0);
  return v1;
}

```

## disassembly

```asm
0x18002e908  push    rbp
0x18002e90a  push    rbx
0x18002e90b  push    rsi
0x18002e90c  push    rdi
0x18002e90d  push    r12
0x18002e90f  push    r14
0x18002e911  push    r15
0x18002e913  lea     rbp, [rsp-27h]
0x18002e918  sub     rsp, 0A0h
0x18002e91f  mov     rax, cs:__security_cookie
0x18002e926  xor     rax, rsp
0x18002e929  mov     [rbp+57h+var_40], rax
0x18002e92d  xor     r15d, r15d
0x18002e930  xorps   xmm0, xmm0
0x18002e933  xor     eax, eax
0x18002e935  mov     [rbp+57h+ReturnLength], r15d
0x18002e939  mov     ebx, r15d
0x18002e93c  mov     [rbp+57h+var_48], rax
0x18002e940  mov     [rbp+57h+ThreadHandle], rbx
0x18002e944  or      edi, 0FFFFFFFFh
0x18002e947  movups  [rbp+57h+ThreadInformation], xmm0
0x18002e94b  mov     [rbp+57h+ThreadId], r15d
0x18002e94f  movups  [rbp+57h+Parameter], xmm0
0x18002e953  mov     [rbp+57h+var_60], rax
0x18002e957  movups  [rbp+57h+var_80], xmm0
0x18002e95b  movups  [rbp+57h+var_70], xmm0
0x18002e95f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e966  lea     r12, WPP_GLOBAL_Control
0x18002e96d  cmp     rcx, r12
0x18002e970  jz      short loc_18002E98B
0x18002e972  test    byte ptr [rcx+1Ch], 4
0x18002e976  jz      short loc_18002E98B
0x18002e978  mov     rcx, [rcx+10h]
0x18002e97c  lea     edx, [rax+10h]
0x18002e97f  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18002e986  call    WPP_SF_
0x18002e98b  xor     r9d, r9d; lpName
0x18002e98e  xor     r8d, r8d; bInitialState
0x18002e991  xor     ecx, ecx; lpEventAttributes
0x18002e993  lea     edx, [r9+1]; bManualReset
0x18002e997  call    cs:__imp_CreateEventW
0x18002e99d  mov     rsi, rax
0x18002e9a0  lea     r14, [rax+1]
0x18002e9a4  cmp     r14, 1
0x18002e9a8  jbe     loc_18002EA4B
0x18002e9ae  mov     qword ptr [rbp+57h+Parameter], rax
0x18002e9b2  lea     r9, [rbp+57h+Parameter]; lpParameter
0x18002e9b6  lea     rax, [rbp+57h+ThreadId]
0x18002e9ba  xor     edx, edx; dwStackSize
0x18002e9bc  mov     [rsp+0D0h+lpThreadId], rax; lpThreadId
0x18002e9c1  lea     r8, WctSyscallCalibratorThreadProc; lpStartAddress
0x18002e9c8  xor     ecx, ecx; lpThreadAttributes
0x18002e9ca  mov     [rsp+0D0h+dwCreationFlags], r15d; dwCreationFlags
0x18002e9cf  call    cs:__imp_CreateThread
0x18002e9d5  mov     rdx, rax
0x18002e9d8  lea     rcx, [rbp+57h+ThreadHandle]
0x18002e9dc  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18002e9e1  mov     rbx, [rbp+57h+ThreadHandle]
0x18002e9e5  lea     rax, [rbx+1]
0x18002e9e9  cmp     rax, 1
0x18002e9ed  jbe     short loc_18002EA4B
0x18002e9ef  mov     ecx, [rbp+57h+ThreadId]; unsigned int
0x18002e9f2  mov     edx, 6
0x18002e9f7  call    WctWaitUntilThreadIsBlocked
0x18002e9fc  test    eax, eax
0x18002e9fe  jz      short loc_18002EA35
0x18002ea00  mov     r9d, 18h; ThreadInformationLength
0x18002ea06  lea     rax, [rbp+57h+ReturnLength]
0x18002ea0a  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18002ea0e  mov     qword ptr [rsp+0D0h+dwCreationFlags], rax; ReturnLength
0x18002ea13  mov     rcx, rbx; ThreadHandle
0x18002ea16  lea     edx, [r9-3]; ThreadInformationClass
0x18002ea1a  call    cs:__imp_NtQueryInformationThread
0x18002ea20  test    eax, eax
0x18002ea22  js      short loc_18002EA35
0x18002ea24  cmp     [rbp+57h+ReturnLength], 18h
0x18002ea28  jnz     short loc_18002EA35
0x18002ea2a  movzx   eax, word ptr [rbp+57h+ThreadInformation+8]
0x18002ea2e  test    ax, ax
0x18002ea31  jz      short loc_18002EA35
0x18002ea33  mov     edi, eax
0x18002ea35  mov     rcx, qword ptr [rbp+57h+Parameter]; hEvent
0x18002ea39  call    cs:__imp_SetEvent
0x18002ea3f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002ea42  mov     rcx, rbx; hHandle
0x18002ea45  call    cs:__imp_WaitForSingleObject
0x18002ea4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea52  cmp     rcx, r12
0x18002ea55  jz      short loc_18002EA75
0x18002ea57  test    byte ptr [rcx+1Ch], 4
0x18002ea5b  jz      short loc_18002EA75
0x18002ea5d  mov     rcx, [rcx+10h]
0x18002ea61  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18002ea68  mov     edx, 11h
0x18002ea6d  mov     r9d, edi
0x18002ea70  call    WPP_SF_d
0x18002ea75  cmp     r14, 1
0x18002ea79  jbe     short loc_18002EA84
0x18002ea7b  mov     rcx, rsi; hObject
0x18002ea7e  call    cs:__imp_CloseHandle
0x18002ea84  lea     rdx, [rbx+1]
0x18002ea88  cmp     rdx, 1
0x18002ea8c  jbe     short loc_18002EA97
0x18002ea8e  mov     rcx, rbx; hObject
0x18002ea91  call    cs:__imp_CloseHandle
0x18002ea97  mov     eax, edi
0x18002ea99  mov     rcx, [rbp+57h+var_40]
0x18002ea9d  xor     rcx, rsp; StackCookie
0x18002eaa0  call    __security_check_cookie
0x18002eaa5  add     rsp, 0A0h
0x18002eaac  pop     r15
0x18002eaae  pop     r14
0x18002eab0  pop     r12
0x18002eab2  pop     rdi
0x18002eab3  pop     rsi
0x18002eab4  pop     rbx
0x18002eab5  pop     rbp
0x18002eab6  retn
```
