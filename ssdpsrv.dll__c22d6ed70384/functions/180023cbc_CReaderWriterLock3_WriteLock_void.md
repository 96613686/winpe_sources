# CReaderWriterLock3::WriteLock(void)

- ea: `0x180023cbc`
- end: `0x180023d30`
- name: `?WriteLock@CReaderWriterLock3@@QEAAXXZ`
- size: `116`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c440`
- `0x18001e724`
- `0x180023ae8`
- `0x180033d28`
- `0x1800341e0`
- `0x180034544`

## callees

- `0x180023cbc`
- `0x180035154`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023ce9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023d03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023ce9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023d03`

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
0x180023cbc  push    rbx
0x180023cbe  sub     rsp, 20h
0x180023cc2  mov     eax, [rcx+4]
0x180023cc5  mov     rbx, rcx
0x180023cc8  test    eax, eax
0x180023cca  jnz     short loc_180023D03
0x180023ccc  mov     ecx, [rcx]
0x180023cce  test    cx, cx
0x180023cd1  jnz     short loc_180023D03
0x180023cd3  lea     edx, [rcx+10000h]
0x180023cd9  mov     eax, ecx
0x180023cdb  or      edx, 0FFFFh
0x180023ce1  lock cmpxchg [rbx], edx
0x180023ce5  cmp     ecx, eax
0x180023ce7  jnz     short loc_180023D03
0x180023ce9  call    cs:__imp_GetCurrentThreadId
0x180023cef  mov     edx, 0FFFFFFFh
0x180023cf4  and     eax, edx
0x180023cf6  bts     eax, 1Ch
0x180023cfa  xchg    eax, [rbx+4]
0x180023cfd  add     rsp, 20h
0x180023d01  pop     rbx
0x180023d02  retn
0x180023d03  call    cs:__imp_GetCurrentThreadId
0x180023d09  mov     ecx, [rbx+4]
0x180023d0c  mov     edx, 0FFFFFFFh
0x180023d11  and     eax, edx
0x180023d13  and     ecx, edx
0x180023d15  cmp     ecx, eax
0x180023d17  jnz     short loc_180023D23
0x180023d19  mov     eax, [rbx+4]
0x180023d1c  add     eax, 10000000h
0x180023d21  jmp     short loc_180023CFA
0x180023d23  mov     rcx, rbx; this
0x180023d26  add     rsp, 20h
0x180023d2a  pop     rbx
0x180023d2b  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
```
