# CCompPort::Attach(void *,ICpRecvRequest *)

- ea: `0x180012420`
- end: `0x18001249e`
- name: `?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z`
- size: `126`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, HANDLE FileHandle, ULONG_PTR CompletionKey)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012420`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001243f`
- `KERNEL32!EnterCriticalSection` at `0x18001243f`
- `KERNEL32!LeaveCriticalSection` at `0x18001247a`
- `KERNEL32!LeaveCriticalSection` at `0x18001247a`
- `KERNEL32!GetLastError` at `0x180012469`
- `KERNEL32!GetLastError` at `0x180012469`
- `KERNEL32!CreateIoCompletionPort` at `0x180012458`
- `KERNEL32!CreateIoCompletionPort` at `0x180012458`

## pseudocode

```c
__int64 __fastcall CCompPort::Attach(LPCRITICAL_SECTION lpCriticalSection, HANDLE FileHandle, ULONG_PTR CompletionKey)
{
  DWORD LastError; // esi

  LastError = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( !CreateIoCompletionPort(FileHandle, lpCriticalSection[1].DebugInfo, CompletionKey, 0) )
    LastError = GetLastError();
  LeaveCriticalSection(lpCriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x180012420  mov     [rsp+arg_0], rbx
0x180012425  mov     [rsp+arg_8], rbp
0x18001242a  mov     [rsp+arg_10], rsi
0x18001242f  push    rdi
0x180012430  sub     rsp, 20h
0x180012434  mov     rbx, r8
0x180012437  mov     rdi, rdx
0x18001243a  mov     rbp, rcx
0x18001243d  xor     esi, esi
0x18001243f  call    cs:__imp_EnterCriticalSection
0x180012446  nop     dword ptr [rax+rax+00h]
0x18001244b  mov     rdx, [rbp+28h]; ExistingCompletionPort
0x18001244f  xor     r9d, r9d; NumberOfConcurrentThreads
0x180012452  mov     r8, rbx; CompletionKey
0x180012455  mov     rcx, rdi; FileHandle
0x180012458  call    cs:__imp_CreateIoCompletionPort
0x18001245f  nop     dword ptr [rax+rax+00h]
0x180012464  test    rax, rax
0x180012467  jnz     short loc_180012477
0x180012469  call    cs:__imp_GetLastError
0x180012470  nop     dword ptr [rax+rax+00h]
0x180012475  mov     esi, eax
0x180012477  mov     rcx, rbp; lpCriticalSection
0x18001247a  call    cs:__imp_LeaveCriticalSection
0x180012481  nop     dword ptr [rax+rax+00h]
0x180012486  mov     rbx, [rsp+28h+arg_0]
0x18001248b  mov     eax, esi
0x18001248d  mov     rsi, [rsp+28h+arg_10]
0x180012492  mov     rbp, [rsp+28h+arg_8]
0x180012497  add     rsp, 20h
0x18001249b  pop     rdi
0x18001249c  retn
```
