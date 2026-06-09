# CCompPort::Worker(void)

- ea: `0x180011bb0`
- end: `0x180011ce0`
- name: `?Worker@CCompPort@@AEAAKXZ`
- size: `304`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011cf0`

## callees

- `0x180011bb0`
- `0x180027900`
- `0x180030010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011bdf`
- `KERNEL32!EnterCriticalSection` at `0x180011bdf`
- `KERNEL32!LeaveCriticalSection` at `0x180011bff`
- `KERNEL32!LeaveCriticalSection` at `0x180011c97`
- `KERNEL32!LeaveCriticalSection` at `0x180011bff`
- `KERNEL32!LeaveCriticalSection` at `0x180011c97`
- `KERNEL32!GetLastError` at `0x180011c51`
- `KERNEL32!GetLastError` at `0x180011c7d`
- `KERNEL32!GetLastError` at `0x180011c51`
- `KERNEL32!GetLastError` at `0x180011c7d`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180011c1f`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180011c1f`

## string_xrefs

- `0x180011cbb`: `onecore\base\Eco\WDS\wdslib\common\inc\locks.h`

## pseudocode

```c
__int64 __fastcall CCompPort::Worker(LPCRITICAL_SECTION lpCriticalSection)
{
  DWORD LastError; // esi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r15
  BOOL QueuedCompletionStatus; // eax
  unsigned __int64 v5; // r14
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp+30h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int64 CompletionKey; // [rsp+70h] [rbp+40h] BYREF

  LastError = 0;
  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  for ( Overlapped = 0;
        ;
        (*(void (__fastcall **)(unsigned __int64, _QWORD, _QWORD, LPOVERLAPPED))(*(_QWORD *)v5 + 8LL))(
          v5,
          LastError,
          NumberOfBytesTransferred,
          Overlapped) )
  {
    while ( 1 )
    {
      EnterCriticalSection(lpCriticalSection);
      DebugInfo = lpCriticalSection[1].DebugInfo;
      LeaveCriticalSection(lpCriticalSection);
      QueuedCompletionStatus = GetQueuedCompletionStatus(
                                 DebugInfo,
                                 &NumberOfBytesTransferred,
                                 &CompletionKey,
                                 &Overlapped,
                                 0xFFFFFFFF);
      v5 = CompletionKey;
      if ( !QueuedCompletionStatus )
        break;
      if ( (const ULONG_PTR *)CompletionKey == &CCompPort::TerminationKey )
        return LastError;
      (*(void (__fastcall **)(unsigned __int64, _QWORD, _QWORD, LPOVERLAPPED))(*(_QWORD *)CompletionKey + 8LL))(
        CompletionKey,
        0,
        NumberOfBytesTransferred,
        Overlapped);
    }
    if ( !Overlapped )
      break;
    LastError = GetLastError();
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180011bb0  mov     [rsp-28h+arg_18], rbx
0x180011bb5  push    rbp
0x180011bb6  push    rsi
0x180011bb7  push    rdi
0x180011bb8  push    r14
0x180011bba  push    r15
0x180011bbc  mov     rbp, rsp
0x180011bbf  sub     rsp, 30h
0x180011bc3  xor     esi, esi
0x180011bc5  mov     rdi, rcx
0x180011bc8  and     [rbp+NumberOfBytesTransferred], esi
0x180011bcb  and     [rbp+CompletionKey], rsi
0x180011bcf  and     [rbp+Overlapped], rsi
0x180011bd3  xor     ebx, ebx
0x180011bd5  mov     r14d, ebx
0x180011bd8  test    ebx, ebx
0x180011bda  jnz     short loc_180011BEB
0x180011bdc  mov     rcx, rdi; lpCriticalSection
0x180011bdf  call    cs:__imp_EnterCriticalSection
0x180011be6  nop     dword ptr [rax+rax+00h]
0x180011beb  mov     r15, [rdi+28h]
0x180011bef  add     ebx, 1
0x180011bf2  jz      short loc_180011C0B
0x180011bf4  mov     ebx, r14d
0x180011bf7  test    r14d, r14d
0x180011bfa  jnz     short loc_180011C0B
0x180011bfc  mov     rcx, rdi; lpCriticalSection
0x180011bff  call    cs:__imp_LeaveCriticalSection
0x180011c06  nop     dword ptr [rax+rax+00h]
0x180011c0b  or      [rsp+30h+var_10], 0FFFFFFFFh
0x180011c10  lea     r9, [rbp+Overlapped]; lpOverlapped
0x180011c14  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x180011c18  mov     rcx, r15; CompletionPort
0x180011c1b  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180011c1f  call    cs:__imp_GetQueuedCompletionStatus
0x180011c26  nop     dword ptr [rax+rax+00h]
0x180011c2b  mov     r14, [rbp+CompletionKey]
0x180011c2f  test    eax, eax
0x180011c31  jz      short loc_180011C4A
0x180011c33  lea     rax, ?TerminationKey@CCompPort@@0_KB; unsigned __int64 const CCompPort::TerminationKey
0x180011c3a  cmp     r14, rax
0x180011c3d  jz      short loc_180011C8B
0x180011c3f  mov     rax, [r14]
0x180011c42  xor     edx, edx
0x180011c44  mov     rax, [rax+8]
0x180011c48  jmp     short loc_180011C68
0x180011c4a  cmp     [rbp+Overlapped], 0
0x180011c4f  jz      short loc_180011C7D
0x180011c51  call    cs:__imp_GetLastError
0x180011c58  nop     dword ptr [rax+rax+00h]
0x180011c5d  mov     rdx, [r14]
0x180011c60  mov     esi, eax
0x180011c62  mov     rax, [rdx+8]
0x180011c66  mov     edx, esi
0x180011c68  mov     r8d, [rbp+NumberOfBytesTransferred]
0x180011c6c  mov     rcx, r14
0x180011c6f  mov     r9, [rbp+Overlapped]
0x180011c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c78  jmp     loc_180011BD5
0x180011c7d  call    cs:__imp_GetLastError
0x180011c84  nop     dword ptr [rax+rax+00h]
0x180011c89  mov     esi, eax
0x180011c8b  test    ebx, ebx
0x180011c8d  jz      short loc_180011CCC
0x180011c8f  add     ebx, 0FFFFFFFFh
0x180011c92  jnz     short loc_180011CA5
0x180011c94  mov     rcx, rdi; lpCriticalSection
0x180011c97  call    cs:__imp_LeaveCriticalSection
0x180011c9e  nop     dword ptr [rax+rax+00h]
0x180011ca3  jmp     short loc_180011CCC
0x180011ca5  test    ebx, ebx
0x180011ca7  jz      short loc_180011CCC
0x180011ca9  and     [rsp+30h+var_10], 0
0x180011cae  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x180011cb5  mov     r9d, 1; int
0x180011cbb  lea     rcx, aOnecoreBaseEco_20; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x180011cc2  mov     edx, 16Bh; unsigned int
0x180011cc7  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180011ccc  mov     rbx, [rsp+30h+arg_18]
0x180011cd1  mov     eax, esi
0x180011cd3  add     rsp, 30h
0x180011cd7  pop     r15
0x180011cd9  pop     r14
0x180011cdb  pop     rdi
0x180011cdc  pop     rsi
0x180011cdd  pop     rbp
0x180011cde  retn
```
