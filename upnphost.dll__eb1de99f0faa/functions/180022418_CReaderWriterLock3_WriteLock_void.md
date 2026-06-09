# CReaderWriterLock3::WriteLock(void)

- ea: `0x180022418`
- end: `0x18002248c`
- name: `?WriteLock@CReaderWriterLock3@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021b80`
- `0x180021d38`
- `0x1800221cc`
- `0x180053284`
- `0x180053444`
- `0x1800537a8`

## callees

- `0x180022418`
- `0x180054170`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022445`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002245f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022445`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002245f`

## pseudocode

```c
void __fastcall CReaderWriterLock3::WriteLock(CReaderWriterLock3 *this)
{
  signed __int32 v2; // ecx
  DWORD v3; // eax

  if ( !*((_DWORD *)this + 1) )
  {
    v2 = *(_DWORD *)this;
    if ( !(_WORD)v2 && v2 == _InterlockedCompareExchange((volatile signed __int32 *)this, (v2 + 0x10000) | 0xFFFF, v2) )
    {
      v3 = GetCurrentThreadId() & 0xFFFFFFF | 0x10000000;
LABEL_5:
      _InterlockedExchange((volatile __int32 *)this + 1, v3);
      return;
    }
  }
  if ( (*((_DWORD *)this + 1) & 0xFFFFFFF) == (GetCurrentThreadId() & 0xFFFFFFF) )
  {
    v3 = *((_DWORD *)this + 1) + 0x10000000;
    goto LABEL_5;
  }
  CReaderWriterLock3::_WriteLockSpin(this);
}

```

## disassembly

```asm
0x180022418  push    rbx
0x18002241a  sub     rsp, 20h
0x18002241e  mov     eax, [rcx+4]
0x180022421  mov     rbx, rcx
0x180022424  test    eax, eax
0x180022426  jnz     short loc_18002245F
0x180022428  mov     ecx, [rcx]
0x18002242a  test    cx, cx
0x18002242d  jnz     short loc_18002245F
0x18002242f  lea     edx, [rcx+10000h]
0x180022435  mov     eax, ecx
0x180022437  or      edx, 0FFFFh
0x18002243d  lock cmpxchg [rbx], edx
0x180022441  cmp     ecx, eax
0x180022443  jnz     short loc_18002245F
0x180022445  call    cs:__imp_GetCurrentThreadId
0x18002244b  mov     edx, 0FFFFFFFh
0x180022450  and     eax, edx
0x180022452  bts     eax, 1Ch
0x180022456  xchg    eax, [rbx+4]
0x180022459  add     rsp, 20h
0x18002245d  pop     rbx
0x18002245e  retn
0x18002245f  call    cs:__imp_GetCurrentThreadId
0x180022465  mov     ecx, [rbx+4]
0x180022468  mov     edx, 0FFFFFFFh
0x18002246d  and     eax, edx
0x18002246f  and     ecx, edx
0x180022471  cmp     ecx, eax
0x180022473  jnz     short loc_18002247F
0x180022475  mov     eax, [rbx+4]
0x180022478  add     eax, 10000000h
0x18002247d  jmp     short loc_180022456
0x18002247f  mov     rcx, rbx; this
0x180022482  add     rsp, 20h
0x180022486  pop     rbx
0x180022487  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
```
