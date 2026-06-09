# CHttp2SendContext::CompleteIo(ulong)

- ea: `0x180034ba4`
- end: `0x180034c1d`
- name: `?CompleteIo@CHttp2SendContext@@QEAAXK@Z`
- size: `121`
- prototype: `void __fastcall(CHttp2SendContext *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d3c0`
- `0x18002e68c`
- `0x18002f0d4`
- `0x18002fc50`
- `0x180035d3c`
- `0x180090674`

## callees

- `0x180034ba4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034bc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034bc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180034be9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180034be9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180034c07`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180034c07`

## pseudocode

```c
void __fastcall CHttp2SendContext::CompleteIo(RTL_SRWLOCK *this, int a2)
{
  int v4; // edi

  if ( (unsigned int)(HIDWORD(this->Ptr) - 1) <= 1 )
  {
    v4 = 0;
    AcquireSRWLockExclusive(this + 3);
    if ( !LODWORD(this[18].Ptr) )
    {
      LODWORD(this[18].Ptr) = 1;
      v4 = 1;
    }
    ReleaseSRWLockExclusive(this + 3);
    if ( v4 )
    {
      LODWORD(this[6].Ptr) = a2;
      _InterlockedIncrement((volatile signed __int32 *)this);
      SubmitThreadpoolWork(*((PTP_WORK *)this[7].Ptr + 1));
    }
  }
}

```

## disassembly

```asm
0x180034ba4  push    rbx
0x180034ba6  push    rbp
0x180034ba7  push    rsi
0x180034ba8  push    rdi
0x180034ba9  sub     rsp, 28h
0x180034bad  mov     eax, [rcx+4]
0x180034bb0  mov     ebp, edx
0x180034bb2  dec     eax
0x180034bb4  mov     rbx, rcx
0x180034bb7  cmp     eax, 1
0x180034bba  ja      short loc_180034C13
0x180034bbc  add     rcx, 18h; SRWLock
0x180034bc0  xor     edi, edi
0x180034bc2  call    cs:__imp_AcquireSRWLockExclusive
0x180034bc9  nop     dword ptr [rax+rax+00h]
0x180034bce  cmp     [rbx+90h], edi
0x180034bd4  jnz     short loc_180034BE5
0x180034bd6  mov     dword ptr [rbx+90h], 1
0x180034be0  mov     edi, 1
0x180034be5  lea     rcx, [rbx+18h]; SRWLock
0x180034be9  call    cs:__imp_ReleaseSRWLockExclusive
0x180034bf0  nop     dword ptr [rax+rax+00h]
0x180034bf5  test    edi, edi
0x180034bf7  jz      short loc_180034C13
0x180034bf9  mov     [rbx+30h], ebp
0x180034bfc  lock inc dword ptr [rbx]
0x180034bff  mov     rcx, [rbx+38h]
0x180034c03  mov     rcx, [rcx+8]; pwk
0x180034c07  call    cs:__imp_SubmitThreadpoolWork
0x180034c0e  nop     dword ptr [rax+rax+00h]
0x180034c13  add     rsp, 28h
0x180034c17  pop     rdi
0x180034c18  pop     rsi
0x180034c19  pop     rbp
0x180034c1a  pop     rbx
0x180034c1b  retn
```
