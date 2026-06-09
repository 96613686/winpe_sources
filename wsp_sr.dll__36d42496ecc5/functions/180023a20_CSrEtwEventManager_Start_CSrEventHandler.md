# CSrEtwEventManager::Start(CSrEventHandler *)

- ea: `0x180023a20`
- end: `0x180023acb`
- name: `?Start@CSrEtwEventManager@@QEAAKPEAVCSrEventHandler@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(CSrEtwEventManager *this, struct CSrEventHandler *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180018934`

## callees

- `0x180023a20`
- `0x180023ad4`
- `0x180023dcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a99`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023a8a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023a8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023a4b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023a4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023aba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023aba`

## pseudocode

```c
__int64 __fastcall CSrEtwEventManager::Start(CSrEtwEventManager *this, struct CSrEventHandler *a2)
{
  unsigned int started; // ebx
  HANDLE Thread; // rax

  if ( *((_BYTE *)this + 128) )
    return 50;
  started = 50;
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  if ( !*((_BYTE *)this + 128) )
  {
    *((_QWORD *)this + 17) = a2;
    started = CSrEtwEventManager::StartSession(this);
    if ( !started )
    {
      Thread = CreateThread(0, 0, EventsWorkerThread, this, 0, 0);
      *((_QWORD *)this + 15) = Thread;
      if ( Thread || (started = GetLastError()) == 0 )
        *((_BYTE *)this + 128) = 1;
      else
        CSrEtwEventManager::StopSession(this);
    }
  }
  ReleaseSRWLockExclusive((PSRWLOCK)this + 1);
  return started;
}

```

## disassembly

```asm
0x180023a20  push    rbx
0x180023a22  push    rbp
0x180023a23  push    rsi
0x180023a24  push    rdi
0x180023a25  sub     rsp, 38h
0x180023a29  cmp     byte ptr [rcx+80h], 0
0x180023a30  mov     rbp, rdx
0x180023a33  mov     rdi, rcx
0x180023a36  jz      short loc_180023A42
0x180023a38  mov     eax, 32h ; '2'
0x180023a3d  jmp     loc_180023AC2
0x180023a42  add     rcx, 8; SRWLock
0x180023a46  mov     ebx, 32h ; '2'
0x180023a4b  call    cs:__imp_AcquireSRWLockExclusive
0x180023a51  cmp     byte ptr [rdi+80h], 0
0x180023a58  jnz     short loc_180023AB6
0x180023a5a  mov     rcx, rdi; this
0x180023a5d  mov     [rdi+88h], rbp
0x180023a64  call    ?StartSession@CSrEtwEventManager@@AEAAKXZ; CSrEtwEventManager::StartSession(void)
0x180023a69  mov     ebx, eax
0x180023a6b  test    eax, eax
0x180023a6d  jnz     short loc_180023AB6
0x180023a6f  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180023a78  lea     r8, ?EventsWorkerThread@@YAKPEAX@Z; lpStartAddress
0x180023a7f  mov     r9, rdi; lpParameter
0x180023a82  mov     [rsp+58h+dwCreationFlags], eax; dwCreationFlags
0x180023a86  xor     edx, edx; dwStackSize
0x180023a88  xor     ecx, ecx; lpThreadAttributes
0x180023a8a  call    cs:__imp_CreateThread
0x180023a90  mov     [rdi+78h], rax
0x180023a94  test    rax, rax
0x180023a97  jnz     short loc_180023AAF
0x180023a99  call    cs:__imp_GetLastError
0x180023a9f  mov     ebx, eax
0x180023aa1  test    eax, eax
0x180023aa3  jz      short loc_180023AAF
0x180023aa5  mov     rcx, rdi; this
0x180023aa8  call    ?StopSession@CSrEtwEventManager@@AEAAKXZ; CSrEtwEventManager::StopSession(void)
0x180023aad  jmp     short loc_180023AB6
0x180023aaf  mov     byte ptr [rdi+80h], 1
0x180023ab6  lea     rcx, [rdi+8]; SRWLock
0x180023aba  call    cs:__imp_ReleaseSRWLockExclusive
0x180023ac0  mov     eax, ebx
0x180023ac2  add     rsp, 38h
0x180023ac6  pop     rdi
0x180023ac7  pop     rsi
0x180023ac8  pop     rbp
0x180023ac9  pop     rbx
0x180023aca  retn
```
