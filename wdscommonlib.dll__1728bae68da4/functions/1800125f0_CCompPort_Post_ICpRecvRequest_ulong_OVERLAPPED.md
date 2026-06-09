# CCompPort::Post(ICpRecvRequest *,ulong,_OVERLAPPED *)

- ea: `0x1800125f0`
- end: `0x18001267e`
- name: `?Post@CCompPort@@QEAAKPEAVICpRecvRequest@@KPEAU_OVERLAPPED@@@Z`
- size: `142`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, ULONG_PTR dwCompletionKey, DWORD dwNumberOfBytesTransferred, LPOVERLAPPED lpOverlapped)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800125f0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180012617`
- `KERNEL32!EnterCriticalSection` at `0x180012617`
- `KERNEL32!LeaveCriticalSection` at `0x18001262a`
- `KERNEL32!LeaveCriticalSection` at `0x18001262a`
- `KERNEL32!GetLastError` at `0x180012652`
- `KERNEL32!GetLastError` at `0x180012652`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180012642`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180012642`

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
0x1800125f0  mov     [rsp+arg_0], rbx
0x1800125f5  mov     [rsp+arg_8], rbp
0x1800125fa  mov     [rsp+arg_10], rsi
0x1800125ff  push    rdi
0x180012600  push    r14
0x180012602  push    r15
0x180012604  sub     rsp, 20h
0x180012608  mov     rbp, r9
0x18001260b  mov     r14d, r8d
0x18001260e  mov     rsi, rdx
0x180012611  mov     rdi, rcx
0x180012614  xor     r15d, r15d
0x180012617  call    cs:__imp_EnterCriticalSection
0x18001261e  nop     dword ptr [rax+rax+00h]
0x180012623  mov     rbx, [rdi+28h]
0x180012627  mov     rcx, rdi; lpCriticalSection
0x18001262a  call    cs:__imp_LeaveCriticalSection
0x180012631  nop     dword ptr [rax+rax+00h]
0x180012636  mov     r9, rbp; lpOverlapped
0x180012639  mov     r8, rsi; dwCompletionKey
0x18001263c  mov     edx, r14d; dwNumberOfBytesTransferred
0x18001263f  mov     rcx, rbx; CompletionPort
0x180012642  call    cs:__imp_PostQueuedCompletionStatus
0x180012649  nop     dword ptr [rax+rax+00h]
0x18001264e  test    eax, eax
0x180012650  jnz     short loc_180012661
0x180012652  call    cs:__imp_GetLastError
0x180012659  nop     dword ptr [rax+rax+00h]
0x18001265e  mov     r15d, eax
0x180012661  mov     rbx, [rsp+38h+arg_0]
0x180012666  mov     eax, r15d
0x180012669  mov     rbp, [rsp+38h+arg_8]
0x18001266e  mov     rsi, [rsp+38h+arg_10]
0x180012673  add     rsp, 20h
0x180012677  pop     r15
0x180012679  pop     r14
0x18001267b  pop     rdi
0x18001267c  retn
```
