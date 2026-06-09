# CCompPort::Worker(void)

- ea: `0x1800127c0`
- end: `0x1800128f0`
- name: `?Worker@CCompPort@@AEAAKXZ`
- size: `304`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012900`

## callees

- `0x1800127c0`
- `0x180028a50`
- `0x180031010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800127ef`
- `KERNEL32!EnterCriticalSection` at `0x1800127ef`
- `KERNEL32!LeaveCriticalSection` at `0x18001280f`
- `KERNEL32!LeaveCriticalSection` at `0x1800128a7`
- `KERNEL32!LeaveCriticalSection` at `0x18001280f`
- `KERNEL32!LeaveCriticalSection` at `0x1800128a7`
- `KERNEL32!GetLastError` at `0x180012861`
- `KERNEL32!GetLastError` at `0x18001288d`
- `KERNEL32!GetLastError` at `0x180012861`
- `KERNEL32!GetLastError` at `0x18001288d`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18001282f`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18001282f`

## string_xrefs

- `0x1800128cb`: `onecore\base\Eco\WDS\wdslib\common\inc\locks.h`

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
0x1800127c0  mov     [rsp-28h+arg_18], rbx
0x1800127c5  push    rbp
0x1800127c6  push    rsi
0x1800127c7  push    rdi
0x1800127c8  push    r14
0x1800127ca  push    r15
0x1800127cc  mov     rbp, rsp
0x1800127cf  sub     rsp, 30h
0x1800127d3  xor     esi, esi
0x1800127d5  mov     rdi, rcx
0x1800127d8  and     [rbp+NumberOfBytesTransferred], esi
0x1800127db  and     [rbp+CompletionKey], rsi
0x1800127df  and     [rbp+Overlapped], rsi
0x1800127e3  xor     ebx, ebx
0x1800127e5  mov     r14d, ebx
0x1800127e8  test    ebx, ebx
0x1800127ea  jnz     short loc_1800127FB
0x1800127ec  mov     rcx, rdi; lpCriticalSection
0x1800127ef  call    cs:__imp_EnterCriticalSection
0x1800127f6  nop     dword ptr [rax+rax+00h]
0x1800127fb  mov     r15, [rdi+28h]
0x1800127ff  add     ebx, 1
0x180012802  jz      short loc_18001281B
0x180012804  mov     ebx, r14d
0x180012807  test    r14d, r14d
0x18001280a  jnz     short loc_18001281B
0x18001280c  mov     rcx, rdi; lpCriticalSection
0x18001280f  call    cs:__imp_LeaveCriticalSection
0x180012816  nop     dword ptr [rax+rax+00h]
0x18001281b  or      [rsp+30h+var_10], 0FFFFFFFFh
0x180012820  lea     r9, [rbp+Overlapped]; lpOverlapped
0x180012824  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x180012828  mov     rcx, r15; CompletionPort
0x18001282b  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18001282f  call    cs:__imp_GetQueuedCompletionStatus
0x180012836  nop     dword ptr [rax+rax+00h]
0x18001283b  mov     r14, [rbp+CompletionKey]
0x18001283f  test    eax, eax
0x180012841  jz      short loc_18001285A
0x180012843  lea     rax, ?TerminationKey@CCompPort@@0_KB; unsigned __int64 const CCompPort::TerminationKey
0x18001284a  cmp     r14, rax
0x18001284d  jz      short loc_18001289B
0x18001284f  mov     rax, [r14]
0x180012852  xor     edx, edx
0x180012854  mov     rax, [rax+8]
0x180012858  jmp     short loc_180012878
0x18001285a  cmp     [rbp+Overlapped], 0
0x18001285f  jz      short loc_18001288D
0x180012861  call    cs:__imp_GetLastError
0x180012868  nop     dword ptr [rax+rax+00h]
0x18001286d  mov     rdx, [r14]
0x180012870  mov     esi, eax
0x180012872  mov     rax, [rdx+8]
0x180012876  mov     edx, esi
0x180012878  mov     r8d, [rbp+NumberOfBytesTransferred]
0x18001287c  mov     rcx, r14
0x18001287f  mov     r9, [rbp+Overlapped]
0x180012883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012888  jmp     loc_1800127E5
0x18001288d  call    cs:__imp_GetLastError
0x180012894  nop     dword ptr [rax+rax+00h]
0x180012899  mov     esi, eax
0x18001289b  test    ebx, ebx
0x18001289d  jz      short loc_1800128DC
0x18001289f  add     ebx, 0FFFFFFFFh
0x1800128a2  jnz     short loc_1800128B5
0x1800128a4  mov     rcx, rdi; lpCriticalSection
0x1800128a7  call    cs:__imp_LeaveCriticalSection
0x1800128ae  nop     dword ptr [rax+rax+00h]
0x1800128b3  jmp     short loc_1800128DC
0x1800128b5  test    ebx, ebx
0x1800128b7  jz      short loc_1800128DC
0x1800128b9  and     [rsp+30h+var_10], 0
0x1800128be  lea     r8, aMUlockcount0; "m_uLockCount == 0"
0x1800128c5  mov     r9d, 1; int
0x1800128cb  lea     rcx, aOnecoreBaseEco_19; "onecore\\base\\Eco\\WDS\\wdslib\\common"...
0x1800128d2  mov     edx, 16Bh; unsigned int
0x1800128d7  call    ?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x1800128dc  mov     rbx, [rsp+30h+arg_18]
0x1800128e1  mov     eax, esi
0x1800128e3  add     rsp, 30h
0x1800128e7  pop     r15
0x1800128e9  pop     r14
0x1800128eb  pop     rdi
0x1800128ec  pop     rsi
0x1800128ed  pop     rbp
0x1800128ee  retn
```
