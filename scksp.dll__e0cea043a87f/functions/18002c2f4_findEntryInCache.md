# findEntryInCache

- ea: `0x18002c2f4`
- end: `0x18002c381`
- name: `findEntryInCache`
- size: `141`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002c108`

## callees

- `0x18002c2f4`
- `0x18002c388`
- `0x18003c21a`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c365`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c365`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c316`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c316`

## pseudocode

```c
__int64 __fastcall findEntryInCache(wchar_t *String1)
{
  __int64 result; // rax
  __int64 v3; // rbx
  unsigned int v4; // esi
  __int64 v5; // rdi
  __int64 v6; // rbp

  result = getCache();
  v3 = result;
  if ( result )
  {
    AcquireSRWLockShared(g_pHandleCacheLock);
    v4 = 0;
    while ( 1 )
    {
      v5 = 224LL * v4;
      v6 = *(_QWORD *)(v5 + v3);
      if ( v6 )
      {
        if ( !wcsncmp_0(String1, (const wchar_t *)(v5 + v3 + 24), 0x21u)
          && !*(_DWORD *)(v5 + v3 + 20)
          && !*(_DWORD *)(v5 + v3 + 16) )
        {
          break;
        }
      }
      if ( (int)++v4 >= 8 )
      {
        v6 = 0;
        goto LABEL_9;
      }
    }
    _InterlockedIncrement64((volatile signed __int64 *)(v5 + v3 + 8));
LABEL_9:
    ReleaseSRWLockShared(g_pHandleCacheLock);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x18002c2f4  push    rbx
0x18002c2f6  push    rbp
0x18002c2f7  push    rsi
0x18002c2f8  push    rdi
0x18002c2f9  push    r14
0x18002c2fb  sub     rsp, 20h
0x18002c2ff  mov     r14, rcx
0x18002c302  call    getCache
0x18002c307  mov     rbx, rax
0x18002c30a  test    rax, rax
0x18002c30d  jz      short loc_18002C36E
0x18002c30f  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x18002c316  call    cs:__imp_AcquireSRWLockShared
0x18002c31c  xor     esi, esi
0x18002c31e  mov     eax, esi
0x18002c320  imul    rdi, rax, 0E0h
0x18002c327  mov     rbp, [rdi+rbx]
0x18002c32b  test    rbp, rbp
0x18002c32e  jz      short loc_18002C355
0x18002c330  lea     rdx, [rbx+18h]
0x18002c334  mov     r8d, 21h ; '!'; MaxCount
0x18002c33a  add     rdx, rdi; String2
0x18002c33d  mov     rcx, r14; String1
0x18002c340  call    wcsncmp_0
0x18002c345  test    eax, eax
0x18002c347  jnz     short loc_18002C355
0x18002c349  cmp     [rdi+rbx+14h], eax
0x18002c34d  jnz     short loc_18002C355
0x18002c34f  cmp     [rdi+rbx+10h], eax
0x18002c353  jz      short loc_18002C379
0x18002c355  inc     esi
0x18002c357  cmp     esi, 8
0x18002c35a  jl      short loc_18002C31E
0x18002c35c  xor     ebp, ebp
0x18002c35e  mov     rcx, cs:g_pHandleCacheLock; SRWLock
0x18002c365  call    cs:__imp_ReleaseSRWLockShared
0x18002c36b  mov     rax, rbp
0x18002c36e  add     rsp, 20h
0x18002c372  pop     r14
0x18002c374  pop     rdi
0x18002c375  pop     rsi
0x18002c376  pop     rbp
0x18002c377  pop     rbx
0x18002c378  retn
0x18002c379  lock inc qword ptr [rdi+rbx+8]
0x18002c37f  jmp     short loc_18002C35E
```
