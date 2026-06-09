# CReaderWriterLock3::WriteLock(void)

- ea: `0x180023054`
- end: `0x1800230d5`
- name: `?WriteLock@CReaderWriterLock3@@QEAAXXZ`
- size: `129`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022778`
- `0x180022930`
- `0x180022e00`
- `0x180056bd4`
- `0x180056d94`
- `0x1800570f8`

## callees

- `0x180023054`
- `0x180057b08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023081`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800230a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023081`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800230a2`

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
0x180023054  push    rbx
0x180023056  sub     rsp, 20h
0x18002305a  mov     eax, [rcx+4]
0x18002305d  mov     rbx, rcx
0x180023060  test    eax, eax
0x180023062  jnz     short loc_1800230A2
0x180023064  mov     ecx, [rcx]
0x180023066  test    cx, cx
0x180023069  jnz     short loc_1800230A2
0x18002306b  lea     edx, [rcx+10000h]
0x180023071  mov     eax, ecx
0x180023073  or      edx, 0FFFFh
0x180023079  lock cmpxchg [rbx], edx
0x18002307d  cmp     ecx, eax
0x18002307f  jnz     short loc_1800230A2
0x180023081  call    cs:__imp_GetCurrentThreadId
0x180023088  nop     dword ptr [rax+rax+00h]
0x18002308d  mov     edx, 0FFFFFFFh
0x180023092  and     eax, edx
0x180023094  bts     eax, 1Ch
0x180023098  xchg    eax, [rbx+4]
0x18002309b  add     rsp, 20h
0x18002309f  pop     rbx
0x1800230a0  retn
0x1800230a2  call    cs:__imp_GetCurrentThreadId
0x1800230a9  nop     dword ptr [rax+rax+00h]
0x1800230ae  mov     ecx, [rbx+4]
0x1800230b1  mov     edx, 0FFFFFFFh
0x1800230b6  and     eax, edx
0x1800230b8  and     ecx, edx
0x1800230ba  cmp     ecx, eax
0x1800230bc  jnz     short loc_1800230C8
0x1800230be  mov     eax, [rbx+4]
0x1800230c1  add     eax, 10000000h
0x1800230c6  jmp     short loc_180023098
0x1800230c8  mov     rcx, rbx; this
0x1800230cb  add     rsp, 20h
0x1800230cf  pop     rbx
0x1800230d0  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
```
