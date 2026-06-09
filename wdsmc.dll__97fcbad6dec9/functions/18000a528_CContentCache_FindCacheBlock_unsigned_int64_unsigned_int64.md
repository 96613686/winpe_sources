# CContentCache::FindCacheBlock(unsigned __int64,unsigned __int64)

- ea: `0x18000a528`
- end: `0x18000a59d`
- name: `?FindCacheBlock@CContentCache@@AEAAPEAUCacheBlock@1@_K0@Z`
- size: `117`
- prototype: `struct CContentCache::CacheBlock *__fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a5a4`
- `0x18000d454`

## callees

- `0x18000a528`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000a57f`
- `KERNEL32!LeaveCriticalSection` at `0x18000a57f`
- `KERNEL32!EnterCriticalSection` at `0x18000a547`
- `KERNEL32!EnterCriticalSection` at `0x18000a547`

## pseudocode

```c
struct CContentCache::CacheBlock *__fastcall CContentCache::FindCacheBlock(
        LPCRITICAL_SECTION lpCriticalSection,
        unsigned __int64 a2,
        unsigned __int64 a3)
{
  __int64 v3; // rbx
  __int64 v7; // rax

  v3 = 0;
  EnterCriticalSection(lpCriticalSection);
  v7 = *(_QWORD *)&lpCriticalSection[5].LockCount;
  while ( v7 )
  {
    v3 = v7;
    v7 = *(_QWORD *)(v7 + 40);
    if ( *(_QWORD *)(v3 + 24) <= a2
      && a2 <= *(_QWORD *)(v3 + 32)
      && *(_QWORD *)(v3 + 24) <= a3
      && a3 <= *(_QWORD *)(v3 + 32) )
    {
      break;
    }
    v3 = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  return (struct CContentCache::CacheBlock *)v3;
}

```

## disassembly

```asm
0x18000a528  mov     [rsp+arg_0], rbx
0x18000a52d  mov     [rsp+arg_8], rbp
0x18000a532  mov     [rsp+arg_10], rsi
0x18000a537  push    rdi
0x18000a538  sub     rsp, 20h
0x18000a53c  xor     ebx, ebx
0x18000a53e  mov     rsi, r8
0x18000a541  mov     rbp, rdx
0x18000a544  mov     rdi, rcx
0x18000a547  call    cs:__imp_EnterCriticalSection
0x18000a54d  mov     rax, [rdi+0D0h]
0x18000a554  jmp     short loc_18000A577
0x18000a556  mov     rbx, rax
0x18000a559  mov     rax, [rax+28h]
0x18000a55d  cmp     [rbx+18h], rbp
0x18000a561  ja      short loc_18000A575
0x18000a563  cmp     rbp, [rbx+20h]
0x18000a567  ja      short loc_18000A575
0x18000a569  cmp     [rbx+18h], rsi
0x18000a56d  ja      short loc_18000A575
0x18000a56f  cmp     rsi, [rbx+20h]
0x18000a573  jbe     short loc_18000A57C
0x18000a575  xor     ebx, ebx
0x18000a577  test    rax, rax
0x18000a57a  jnz     short loc_18000A556
0x18000a57c  mov     rcx, rdi; lpCriticalSection
0x18000a57f  call    cs:__imp_LeaveCriticalSection
0x18000a585  mov     rbp, [rsp+28h+arg_8]
0x18000a58a  mov     rax, rbx
0x18000a58d  mov     rbx, [rsp+28h+arg_0]
0x18000a592  mov     rsi, [rsp+28h+arg_10]
0x18000a597  add     rsp, 20h
0x18000a59b  pop     rdi
0x18000a59c  retn
```
