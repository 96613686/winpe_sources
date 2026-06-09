# CCompPort::Attach(void *,ICpRecvRequest *)

- ea: `0x180011820`
- end: `0x18001189e`
- name: `?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z`
- size: `126`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, HANDLE FileHandle, ULONG_PTR CompletionKey)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011820`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001183f`
- `KERNEL32!EnterCriticalSection` at `0x18001183f`
- `KERNEL32!LeaveCriticalSection` at `0x18001187a`
- `KERNEL32!LeaveCriticalSection` at `0x18001187a`
- `KERNEL32!GetLastError` at `0x180011869`
- `KERNEL32!GetLastError` at `0x180011869`
- `KERNEL32!CreateIoCompletionPort` at `0x180011858`
- `KERNEL32!CreateIoCompletionPort` at `0x180011858`

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
0x180011820  mov     [rsp+arg_0], rbx
0x180011825  mov     [rsp+arg_8], rbp
0x18001182a  mov     [rsp+arg_10], rsi
0x18001182f  push    rdi
0x180011830  sub     rsp, 20h
0x180011834  mov     rbx, r8
0x180011837  mov     rdi, rdx
0x18001183a  mov     rbp, rcx
0x18001183d  xor     esi, esi
0x18001183f  call    cs:__imp_EnterCriticalSection
0x180011846  nop     dword ptr [rax+rax+00h]
0x18001184b  mov     rdx, [rbp+28h]; ExistingCompletionPort
0x18001184f  xor     r9d, r9d; NumberOfConcurrentThreads
0x180011852  mov     r8, rbx; CompletionKey
0x180011855  mov     rcx, rdi; FileHandle
0x180011858  call    cs:__imp_CreateIoCompletionPort
0x18001185f  nop     dword ptr [rax+rax+00h]
0x180011864  test    rax, rax
0x180011867  jnz     short loc_180011877
0x180011869  call    cs:__imp_GetLastError
0x180011870  nop     dword ptr [rax+rax+00h]
0x180011875  mov     esi, eax
0x180011877  mov     rcx, rbp; lpCriticalSection
0x18001187a  call    cs:__imp_LeaveCriticalSection
0x180011881  nop     dword ptr [rax+rax+00h]
0x180011886  mov     rbx, [rsp+28h+arg_0]
0x18001188b  mov     eax, esi
0x18001188d  mov     rsi, [rsp+28h+arg_10]
0x180011892  mov     rbp, [rsp+28h+arg_8]
0x180011897  add     rsp, 20h
0x18001189b  pop     rdi
0x18001189c  retn
```
