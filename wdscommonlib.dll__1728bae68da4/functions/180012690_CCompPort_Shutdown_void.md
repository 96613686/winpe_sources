# CCompPort::Shutdown(void)

- ea: `0x180012690`
- end: `0x1800127ae`
- name: `?Shutdown@CCompPort@@QEAAKXZ`
- size: `286`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800123d0`

## callees

- `0x180012690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012765`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012765`
- `KERNEL32!EnterCriticalSection` at `0x1800126ac`
- `KERNEL32!EnterCriticalSection` at `0x1800126ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800126d3`
- `KERNEL32!LeaveCriticalSection` at `0x1800126d3`
- `KERNEL32!GetLastError` at `0x18001279e`
- `KERNEL32!GetLastError` at `0x18001279e`
- `KERNEL32!CloseHandle` at `0x180012744`
- `KERNEL32!CloseHandle` at `0x180012774`
- `KERNEL32!CloseHandle` at `0x180012744`
- `KERNEL32!CloseHandle` at `0x180012774`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180012701`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180012701`
- `KERNEL32!WaitForMultipleObjects` at `0x18001272a`
- `KERNEL32!WaitForMultipleObjects` at `0x18001272a`

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
0x180012690  mov     rax, rsp
0x180012693  mov     [rax+8], rbx
0x180012697  mov     [rax+10h], rbp
0x18001269b  mov     [rax+18h], rsi
0x18001269f  mov     [rax+20h], rdi
0x1800126a3  push    r14
0x1800126a5  sub     rsp, 20h
0x1800126a9  mov     rbx, rcx
0x1800126ac  call    cs:__imp_EnterCriticalSection
0x1800126b3  nop     dword ptr [rax+rax+00h]
0x1800126b8  mov     esi, [rbx+38h]
0x1800126bb  xor     edi, edi
0x1800126bd  mov     r14, [rbx+28h]
0x1800126c1  mov     rcx, rbx; lpCriticalSection
0x1800126c4  mov     rbp, [rbx+30h]
0x1800126c8  mov     [rbx+30h], rdi
0x1800126cc  mov     [rbx+38h], edi
0x1800126cf  mov     [rbx+28h], rdi
0x1800126d3  call    cs:__imp_LeaveCriticalSection
0x1800126da  nop     dword ptr [rax+rax+00h]
0x1800126df  test    r14, r14
0x1800126e2  jz      loc_180012780
0x1800126e8  test    esi, esi
0x1800126ea  jz      loc_180012780
0x1800126f0  mov     ebx, edi
0x1800126f2  xor     r9d, r9d; lpOverlapped
0x1800126f5  lea     r8, ?TerminationKey@CCompPort@@0_KB; dwCompletionKey
0x1800126fc  xor     edx, edx; dwNumberOfBytesTransferred
0x1800126fe  mov     rcx, r14; CompletionPort
0x180012701  call    cs:__imp_PostQueuedCompletionStatus
0x180012708  nop     dword ptr [rax+rax+00h]
0x18001270d  test    eax, eax
0x18001270f  jz      loc_18001279E
0x180012715  inc     ebx
0x180012717  cmp     ebx, esi
0x180012719  jb      short loc_1800126F2
0x18001271b  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001271f  mov     r8d, 1; bWaitAll
0x180012725  mov     rdx, rbp; lpHandles
0x180012728  mov     ecx, esi; nCount
0x18001272a  call    cs:__imp_WaitForMultipleObjects
0x180012731  nop     dword ptr [rax+rax+00h]
0x180012736  test    eax, eax
0x180012738  jnz     short loc_18001279E
0x18001273a  test    esi, esi
0x18001273c  jz      short loc_18001275D
0x18001273e  mov     rbx, rbp
0x180012741  mov     rcx, [rbx]; hObject
0x180012744  call    cs:__imp_CloseHandle
0x18001274b  nop     dword ptr [rax+rax+00h]
0x180012750  mov     [rbx], rdi
0x180012753  lea     rbx, [rbx+8]
0x180012757  sub     rsi, 1
0x18001275b  jnz     short loc_180012741
0x18001275d  test    rbp, rbp
0x180012760  jz      short loc_180012771
0x180012762  mov     rcx, rbp
0x180012765  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001276c  nop     dword ptr [rax+rax+00h]
0x180012771  mov     rcx, r14; hObject
0x180012774  call    cs:__imp_CloseHandle
0x18001277b  nop     dword ptr [rax+rax+00h]
0x180012780  mov     rbx, [rsp+28h+arg_0]
0x180012785  mov     eax, edi
0x180012787  mov     rdi, [rsp+28h+arg_18]
0x18001278c  mov     rbp, [rsp+28h+arg_8]
0x180012791  mov     rsi, [rsp+28h+arg_10]
0x180012796  add     rsp, 20h
0x18001279a  pop     r14
0x18001279c  retn
0x18001279e  call    cs:__imp_GetLastError
0x1800127a5  nop     dword ptr [rax+rax+00h]
0x1800127aa  mov     edi, eax
0x1800127ac  jmp     short loc_180012780
```
