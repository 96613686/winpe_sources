# CCompPort::Shutdown(void)

- ea: `0x180011a90`
- end: `0x180011ba7`
- name: `?Shutdown@CCompPort@@QEAAKXZ`
- size: `279`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800117d0`

## callees

- `0x180011a90`
- `0x18002e468`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011aac`
- `KERNEL32!EnterCriticalSection` at `0x180011aac`
- `KERNEL32!LeaveCriticalSection` at `0x180011ad3`
- `KERNEL32!LeaveCriticalSection` at `0x180011ad3`
- `KERNEL32!GetLastError` at `0x180011b97`
- `KERNEL32!GetLastError` at `0x180011b97`
- `KERNEL32!CloseHandle` at `0x180011b44`
- `KERNEL32!CloseHandle` at `0x180011b6d`
- `KERNEL32!CloseHandle` at `0x180011b44`
- `KERNEL32!CloseHandle` at `0x180011b6d`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180011b01`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180011b01`
- `KERNEL32!WaitForMultipleObjects` at `0x180011b2a`
- `KERNEL32!WaitForMultipleObjects` at `0x180011b2a`

## pseudocode

```c
__int64 __fastcall CCompPort::Shutdown(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 OwningThread_low; // rsi
  unsigned int v3; // edi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r14
  HANDLE *v5; // rbp
  unsigned int v6; // ebx
  HANDLE *v7; // rbx

  EnterCriticalSection(lpCriticalSection);
  OwningThread_low = LODWORD(lpCriticalSection[1].OwningThread);
  v3 = 0;
  DebugInfo = lpCriticalSection[1].DebugInfo;
  v5 = *(HANDLE **)&lpCriticalSection[1].LockCount;
  *(_QWORD *)&lpCriticalSection[1].LockCount = 0;
  LODWORD(lpCriticalSection[1].OwningThread) = 0;
  lpCriticalSection[1].DebugInfo = 0;
  LeaveCriticalSection(lpCriticalSection);
  if ( DebugInfo && (_DWORD)OwningThread_low )
  {
    v6 = 0;
    do
    {
      if ( !PostQueuedCompletionStatus(DebugInfo, 0, (ULONG_PTR)&CCompPort::TerminationKey, 0) )
        return GetLastError();
      ++v6;
    }
    while ( v6 < (unsigned int)OwningThread_low );
    if ( WaitForMultipleObjects(OwningThread_low, v5, 1, 0xFFFFFFFF) )
      return GetLastError();
    v7 = v5;
    do
    {
      CloseHandle(*v7);
      *v7++ = 0;
      --OwningThread_low;
    }
    while ( OwningThread_low );
    if ( v5 )
      operator delete(v5);
    CloseHandle(DebugInfo);
  }
  return v3;
}

```

## disassembly

```asm
0x180011a90  mov     rax, rsp
0x180011a93  mov     [rax+8], rbx
0x180011a97  mov     [rax+10h], rbp
0x180011a9b  mov     [rax+18h], rsi
0x180011a9f  mov     [rax+20h], rdi
0x180011aa3  push    r14
0x180011aa5  sub     rsp, 20h
0x180011aa9  mov     rbx, rcx
0x180011aac  call    cs:__imp_EnterCriticalSection
0x180011ab3  nop     dword ptr [rax+rax+00h]
0x180011ab8  mov     esi, [rbx+38h]
0x180011abb  xor     edi, edi
0x180011abd  mov     r14, [rbx+28h]
0x180011ac1  mov     rcx, rbx; lpCriticalSection
0x180011ac4  mov     rbp, [rbx+30h]
0x180011ac8  mov     [rbx+30h], rdi
0x180011acc  mov     [rbx+38h], edi
0x180011acf  mov     [rbx+28h], rdi
0x180011ad3  call    cs:__imp_LeaveCriticalSection
0x180011ada  nop     dword ptr [rax+rax+00h]
0x180011adf  test    r14, r14
0x180011ae2  jz      loc_180011B79
0x180011ae8  test    esi, esi
0x180011aea  jz      loc_180011B79
0x180011af0  mov     ebx, edi
0x180011af2  xor     r9d, r9d; lpOverlapped
0x180011af5  lea     r8, ?TerminationKey@CCompPort@@0_KB; dwCompletionKey
0x180011afc  xor     edx, edx; dwNumberOfBytesTransferred
0x180011afe  mov     rcx, r14; CompletionPort
0x180011b01  call    cs:__imp_PostQueuedCompletionStatus
0x180011b08  nop     dword ptr [rax+rax+00h]
0x180011b0d  test    eax, eax
0x180011b0f  jz      loc_180011B97
0x180011b15  inc     ebx
0x180011b17  cmp     ebx, esi
0x180011b19  jb      short loc_180011AF2
0x180011b1b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180011b1f  mov     r8d, 1; bWaitAll
0x180011b25  mov     rdx, rbp; lpHandles
0x180011b28  mov     ecx, esi; nCount
0x180011b2a  call    cs:__imp_WaitForMultipleObjects
0x180011b31  nop     dword ptr [rax+rax+00h]
0x180011b36  test    eax, eax
0x180011b38  jnz     short loc_180011B97
0x180011b3a  test    esi, esi
0x180011b3c  jz      short loc_180011B5D
0x180011b3e  mov     rbx, rbp
0x180011b41  mov     rcx, [rbx]; hObject
0x180011b44  call    cs:__imp_CloseHandle
0x180011b4b  nop     dword ptr [rax+rax+00h]
0x180011b50  mov     [rbx], rdi
0x180011b53  lea     rbx, [rbx+8]
0x180011b57  sub     rsi, 1
0x180011b5b  jnz     short loc_180011B41
0x180011b5d  test    rbp, rbp
0x180011b60  jz      short loc_180011B6A
0x180011b62  mov     rcx, rbp; lpMem
0x180011b65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011b6a  mov     rcx, r14; hObject
0x180011b6d  call    cs:__imp_CloseHandle
0x180011b74  nop     dword ptr [rax+rax+00h]
0x180011b79  mov     rbx, [rsp+28h+arg_0]
0x180011b7e  mov     eax, edi
0x180011b80  mov     rdi, [rsp+28h+arg_18]
0x180011b85  mov     rbp, [rsp+28h+arg_8]
0x180011b8a  mov     rsi, [rsp+28h+arg_10]
0x180011b8f  add     rsp, 20h
0x180011b93  pop     r14
0x180011b95  retn
0x180011b97  call    cs:__imp_GetLastError
0x180011b9e  nop     dword ptr [rax+rax+00h]
0x180011ba3  mov     edi, eax
0x180011ba5  jmp     short loc_180011B79
```
