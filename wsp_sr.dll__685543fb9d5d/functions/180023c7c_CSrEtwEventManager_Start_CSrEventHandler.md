# CSrEtwEventManager::Start(CSrEventHandler *)

- ea: `0x180023c7c`
- end: `0x180023d40`
- name: `?Start@CSrEtwEventManager@@QEAAKPEAVCSrEventHandler@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(CSrEtwEventManager *this, struct CSrEventHandler *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001881c`

## callees

- `0x180023c7c`
- `0x180023d48`
- `0x180024088`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d01`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023cec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023cec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023ca7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180023ca7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023d28`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180023d28`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180023c7c  push    rbx
0x180023c7e  push    rbp
0x180023c7f  push    rsi
0x180023c80  push    rdi
0x180023c81  sub     rsp, 38h
0x180023c85  cmp     byte ptr [rcx+80h], 0
0x180023c8c  mov     rbp, rdx
0x180023c8f  mov     rdi, rcx
0x180023c92  jz      short loc_180023C9E
0x180023c94  mov     eax, 32h ; '2'
0x180023c99  jmp     loc_180023D36
0x180023c9e  add     rcx, 8; SRWLock
0x180023ca2  mov     ebx, 32h ; '2'
0x180023ca7  call    cs:__imp_AcquireSRWLockExclusive
0x180023cae  nop     dword ptr [rax+rax+00h]
0x180023cb3  cmp     byte ptr [rdi+80h], 0
0x180023cba  jnz     short loc_180023D24
0x180023cbc  mov     rcx, rdi; this
0x180023cbf  mov     [rdi+88h], rbp
0x180023cc6  call    ?StartSession@CSrEtwEventManager@@AEAAKXZ; CSrEtwEventManager::StartSession(void)
0x180023ccb  mov     ebx, eax
0x180023ccd  test    eax, eax
0x180023ccf  jnz     short loc_180023D24
0x180023cd1  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180023cda  lea     r8, ?EventsWorkerThread@@YAKPEAX@Z; lpStartAddress
0x180023ce1  mov     r9, rdi; lpParameter
0x180023ce4  mov     [rsp+58h+dwCreationFlags], eax; dwCreationFlags
0x180023ce8  xor     edx, edx; dwStackSize
0x180023cea  xor     ecx, ecx; lpThreadAttributes
0x180023cec  call    cs:__imp_CreateThread
0x180023cf3  nop     dword ptr [rax+rax+00h]
0x180023cf8  mov     [rdi+78h], rax
0x180023cfc  test    rax, rax
0x180023cff  jnz     short loc_180023D1D
0x180023d01  call    cs:__imp_GetLastError
0x180023d08  nop     dword ptr [rax+rax+00h]
0x180023d0d  mov     ebx, eax
0x180023d0f  test    eax, eax
0x180023d11  jz      short loc_180023D1D
0x180023d13  mov     rcx, rdi; this
0x180023d16  call    ?StopSession@CSrEtwEventManager@@AEAAKXZ; CSrEtwEventManager::StopSession(void)
0x180023d1b  jmp     short loc_180023D24
0x180023d1d  mov     byte ptr [rdi+80h], 1
0x180023d24  lea     rcx, [rdi+8]; SRWLock
0x180023d28  call    cs:__imp_ReleaseSRWLockExclusive
0x180023d2f  nop     dword ptr [rax+rax+00h]
0x180023d34  mov     eax, ebx
0x180023d36  add     rsp, 38h
0x180023d3a  pop     rdi
0x180023d3b  pop     rsi
0x180023d3c  pop     rbp
0x180023d3d  pop     rbx
0x180023d3e  retn
```
