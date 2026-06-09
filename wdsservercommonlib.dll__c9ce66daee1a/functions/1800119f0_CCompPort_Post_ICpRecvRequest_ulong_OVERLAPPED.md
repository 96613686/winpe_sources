# CCompPort::Post(ICpRecvRequest *,ulong,_OVERLAPPED *)

- ea: `0x1800119f0`
- end: `0x180011a7e`
- name: `?Post@CCompPort@@QEAAKPEAVICpRecvRequest@@KPEAU_OVERLAPPED@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, ULONG_PTR dwCompletionKey, DWORD dwNumberOfBytesTransferred, LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800119f0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011a17`
- `KERNEL32!EnterCriticalSection` at `0x180011a17`
- `KERNEL32!LeaveCriticalSection` at `0x180011a2a`
- `KERNEL32!LeaveCriticalSection` at `0x180011a2a`
- `KERNEL32!GetLastError` at `0x180011a52`
- `KERNEL32!GetLastError` at `0x180011a52`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180011a42`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180011a42`

## pseudocode

```c
__int64 __fastcall CCompPort::Post(
        LPCRITICAL_SECTION lpCriticalSection,
        ULONG_PTR dwCompletionKey,
        DWORD dwNumberOfBytesTransferred,
        LPOVERLAPPED lpOverlapped)
{
  unsigned int v8; // r15d
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rbx

  v8 = 0;
  EnterCriticalSection(lpCriticalSection);
  DebugInfo = lpCriticalSection[1].DebugInfo;
  LeaveCriticalSection(lpCriticalSection);
  if ( !PostQueuedCompletionStatus(DebugInfo, dwNumberOfBytesTransferred, dwCompletionKey, lpOverlapped) )
    return GetLastError();
  return v8;
}

```

## disassembly

```asm
0x1800119f0  mov     [rsp+arg_0], rbx
0x1800119f5  mov     [rsp+arg_8], rbp
0x1800119fa  mov     [rsp+arg_10], rsi
0x1800119ff  push    rdi
0x180011a00  push    r14
0x180011a02  push    r15
0x180011a04  sub     rsp, 20h
0x180011a08  mov     rbp, r9
0x180011a0b  mov     r14d, r8d
0x180011a0e  mov     rsi, rdx
0x180011a11  mov     rdi, rcx
0x180011a14  xor     r15d, r15d
0x180011a17  call    cs:__imp_EnterCriticalSection
0x180011a1e  nop     dword ptr [rax+rax+00h]
0x180011a23  mov     rbx, [rdi+28h]
0x180011a27  mov     rcx, rdi; lpCriticalSection
0x180011a2a  call    cs:__imp_LeaveCriticalSection
0x180011a31  nop     dword ptr [rax+rax+00h]
0x180011a36  mov     r9, rbp; lpOverlapped
0x180011a39  mov     r8, rsi; dwCompletionKey
0x180011a3c  mov     edx, r14d; dwNumberOfBytesTransferred
0x180011a3f  mov     rcx, rbx; CompletionPort
0x180011a42  call    cs:__imp_PostQueuedCompletionStatus
0x180011a49  nop     dword ptr [rax+rax+00h]
0x180011a4e  test    eax, eax
0x180011a50  jnz     short loc_180011A61
0x180011a52  call    cs:__imp_GetLastError
0x180011a59  nop     dword ptr [rax+rax+00h]
0x180011a5e  mov     r15d, eax
0x180011a61  mov     rbx, [rsp+38h+arg_0]
0x180011a66  mov     eax, r15d
0x180011a69  mov     rbp, [rsp+38h+arg_8]
0x180011a6e  mov     rsi, [rsp+38h+arg_10]
0x180011a73  add     rsp, 20h
0x180011a77  pop     r15
0x180011a79  pop     r14
0x180011a7b  pop     rdi
0x180011a7c  retn
```
