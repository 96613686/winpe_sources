# CReaderWriterLock3::WriteLock(void)

- ea: `0x180025700`
- end: `0x180025781`
- name: `?WriteLock@CReaderWriterLock3@@QEAAXXZ`
- size: `129`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d89c`
- `0x18001fc70`
- `0x18002552c`
- `0x1800367e4`
- `0x180036ce0`
- `0x180037044`

## callees

- `0x180025700`
- `0x180037ca0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002572d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002574e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002572d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002574e`

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
0x180025700  push    rbx
0x180025702  sub     rsp, 20h
0x180025706  mov     eax, [rcx+4]
0x180025709  mov     rbx, rcx
0x18002570c  test    eax, eax
0x18002570e  jnz     short loc_18002574E
0x180025710  mov     ecx, [rcx]
0x180025712  test    cx, cx
0x180025715  jnz     short loc_18002574E
0x180025717  lea     edx, [rcx+10000h]
0x18002571d  mov     eax, ecx
0x18002571f  or      edx, 0FFFFh
0x180025725  lock cmpxchg [rbx], edx
0x180025729  cmp     ecx, eax
0x18002572b  jnz     short loc_18002574E
0x18002572d  call    cs:__imp_GetCurrentThreadId
0x180025734  nop     dword ptr [rax+rax+00h]
0x180025739  mov     edx, 0FFFFFFFh
0x18002573e  and     eax, edx
0x180025740  bts     eax, 1Ch
0x180025744  xchg    eax, [rbx+4]
0x180025747  add     rsp, 20h
0x18002574b  pop     rbx
0x18002574c  retn
0x18002574e  call    cs:__imp_GetCurrentThreadId
0x180025755  nop     dword ptr [rax+rax+00h]
0x18002575a  mov     ecx, [rbx+4]
0x18002575d  mov     edx, 0FFFFFFFh
0x180025762  and     eax, edx
0x180025764  and     ecx, edx
0x180025766  cmp     ecx, eax
0x180025768  jnz     short loc_180025774
0x18002576a  mov     eax, [rbx+4]
0x18002576d  add     eax, 10000000h
0x180025772  jmp     short loc_180025744
0x180025774  mov     rcx, rbx; this
0x180025777  add     rsp, 20h
0x18002577b  pop     rbx
0x18002577c  jmp     ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
```
