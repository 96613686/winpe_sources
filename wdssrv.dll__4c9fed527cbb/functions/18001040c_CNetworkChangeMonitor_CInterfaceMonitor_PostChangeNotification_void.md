# CNetworkChangeMonitor<CInterfaceMonitor>::PostChangeNotification(void)

- ea: `0x18001040c`
- end: `0x18001052d`
- name: `?PostChangeNotification@?$CNetworkChangeMonitor@VCInterfaceMonitor@@@@AEAAKXZ`
- size: `289`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001010c`
- `0x180010640`

## callees

- `0x180003944`
- `0x18001040c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001050e`
- `KERNEL32!LeaveCriticalSection` at `0x18001050e`
- `KERNEL32!EnterCriticalSection` at `0x18001041e`
- `KERNEL32!EnterCriticalSection` at `0x18001041e`
- `KERNEL32!SetEvent` at `0x1800104ee`
- `KERNEL32!SetEvent` at `0x1800104ee`
- `WS2_32!WSAIoctl` at `0x180010484`
- `WS2_32!WSAIoctl` at `0x180010484`
- `WS2_32!__imp_WSAGetLastError` at `0x180010494`
- `WS2_32!__imp_WSAGetLastError` at `0x180010494`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800104cb`
- `WdsServerCommonLib!?ReaderLock@CMRSWLock@@QEAAXXZ` at `0x1800104cb`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x1800104fd`
- `WdsServerCommonLib!?ReaderRelease@CMRSWLock@@QEAAXXZ` at `0x1800104fd`

## pseudocode

```c
__int64 __fastcall CNetworkChangeMonitor<CInterfaceMonitor>::PostChangeNotification(
        LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  unsigned int Error; // eax
  __int64 v5; // rdx
  unsigned int v6; // esi

  EnterCriticalSection(lpCriticalSection);
  _InterlockedIncrement((volatile signed __int32 *)&lpCriticalSection[4].OwningThread);
  v2 = 0;
  if ( !(unsigned int)ElValidateWin32(0, v3, "base\\Eco\\WDS\\wdslib\\net\\NetChgMon.h", 306) )
  {
    if ( WSAIoctl(
           (SOCKET)lpCriticalSection[1].OwningThread,
           0x28000017u,
           0,
           0,
           0,
           0,
           (LPDWORD)&lpCriticalSection[4].LockCount,
           (LPWSAOVERLAPPED)&lpCriticalSection[3].LockCount,
           0) )
    {
      Error = WSAGetLastError();
      v6 = Error;
      if ( Error != 997 )
      {
        if ( Error )
        {
          ElValidateWin32(Error, v5, "base\\Eco\\WDS\\wdslib\\net\\NetChgMon.h", 323);
          CMRSWLock::ReaderLock((CMRSWLock *)&lpCriticalSection[4].SpinCount);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)&lpCriticalSection[4].OwningThread, 0xFFFFFFFF) == 1 )
            SetEvent(lpCriticalSection[4].LockSemaphore);
          CMRSWLock::ReaderRelease((CMRSWLock *)&lpCriticalSection[4].SpinCount);
          v2 = v6;
        }
      }
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x18001040c  mov     [rsp+arg_8], rbx
0x180010411  mov     [rsp+arg_10], rsi
0x180010416  push    rdi
0x180010417  sub     rsp, 50h
0x18001041b  mov     rdi, rcx
0x18001041e  call    cs:__imp_EnterCriticalSection
0x180010425  nop     dword ptr [rax+rax+00h]
0x18001042a  lock inc dword ptr [rdi+0B0h]
0x180010431  mov     r9d, 132h
0x180010437  lea     r8, aBaseEcoWdsWdsl_0; "base\\Eco\\WDS\\wdslib\\net\\NetChgMon."...
0x18001043e  xor     ecx, ecx
0x180010440  xor     ebx, ebx
0x180010442  call    ElValidateWin32
0x180010447  test    eax, eax
0x180010449  jnz     loc_18001050B
0x18001044f  mov     [rsp+58h+lpCompletionRoutine], rbx; lpCompletionRoutine
0x180010454  lea     rax, [rdi+80h]
0x18001045b  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x180010460  lea     rcx, [rdi+0A8h]
0x180010467  mov     [rsp+58h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x18001046c  xor     r9d, r9d; cbInBuffer
0x18001046f  mov     rcx, [rdi+38h]; s
0x180010473  xor     r8d, r8d; lpvInBuffer
0x180010476  mov     [rsp+58h+cbOutBuffer], ebx; cbOutBuffer
0x18001047a  mov     edx, 28000017h; dwIoControlCode
0x18001047f  mov     [rsp+58h+lpvOutBuffer], rbx; lpvOutBuffer
0x180010484  call    cs:__imp_WSAIoctl
0x18001048b  nop     dword ptr [rax+rax+00h]
0x180010490  test    eax, eax
0x180010492  jz      short loc_18001050B
0x180010494  call    cs:__imp_WSAGetLastError
0x18001049b  nop     dword ptr [rax+rax+00h]
0x1800104a0  mov     esi, eax
0x1800104a2  cmp     eax, 3E5h
0x1800104a7  jz      short loc_18001050B
0x1800104a9  test    eax, eax
0x1800104ab  jz      short loc_18001050B
0x1800104ad  mov     r9d, 143h
0x1800104b3  lea     r8, aBaseEcoWdsWdsl_0; "base\\Eco\\WDS\\wdslib\\net\\NetChgMon."...
0x1800104ba  mov     ecx, eax
0x1800104bc  call    ElValidateWin32
0x1800104c1  lea     rbx, [rdi+0C0h]
0x1800104c8  mov     rcx, rbx
0x1800104cb  call    cs:__imp_?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x1800104d2  nop     dword ptr [rax+rax+00h]
0x1800104d7  or      eax, 0FFFFFFFFh
0x1800104da  lock xadd [rdi+0B0h], eax
0x1800104e2  cmp     eax, 1
0x1800104e5  jnz     short loc_1800104FA
0x1800104e7  mov     rcx, [rdi+0B8h]; hEvent
0x1800104ee  call    cs:__imp_SetEvent
0x1800104f5  nop     dword ptr [rax+rax+00h]
0x1800104fa  mov     rcx, rbx
0x1800104fd  call    cs:__imp_?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x180010504  nop     dword ptr [rax+rax+00h]
0x180010509  mov     ebx, esi
0x18001050b  mov     rcx, rdi; lpCriticalSection
0x18001050e  call    cs:__imp_LeaveCriticalSection
0x180010515  nop     dword ptr [rax+rax+00h]
0x18001051a  mov     rsi, [rsp+58h+arg_10]
0x18001051f  mov     eax, ebx
0x180010521  mov     rbx, [rsp+58h+arg_8]
0x180010526  add     rsp, 50h
0x18001052a  pop     rdi
0x18001052b  retn
```
