# AcquireWriteLock

- ea: `0x180014d2c`
- end: `0x180014dd1`
- name: `AcquireWriteLock`
- size: `165`
- prototype: ``
- caller_count: `40`
- callee_count: `2`
- tags: ``

## callers

- `0x180002dd0`
- `0x180003a20`
- `0x180003e30`
- `0x180003f10`
- `0x18000ae90`
- `0x18000b440`
- `0x18000c560`
- `0x18000ce00`
- `0x18000cee0`
- `0x18000d8c0`
- `0x18000d9d0`
- `0x180011850`
- `0x180012620`
- `0x180012800`
- `0x180014200`
- `0x180014580`
- `0x180014970`
- `0x1800151ec`
- `0x1800155fc`
- `0x1800158cc`
- `0x180015a8c`
- `0x180015f54`
- `0x180016a40`
- `0x180016d00`
- `0x180017f48`
- `0x180018070`
- `0x180018dd4`
- `0x18001958c`
- `0x180019de0`
- `0x18001a360`
- `0x18001af20`
- `0x18001bfd4`
- `0x18001c1a8`
- `0x18001ca9c`
- `0x18001d1ec`
- `0x18001d378`
- `0x18001decc`
- `0x18001e374`
- `0x18001e77c`
- `0x18001ed64`

## callees

- `0x180014d2c`
- `0x180014dd8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180014d42`
- `KERNEL32!EnterCriticalSection` at `0x180014d81`
- `KERNEL32!EnterCriticalSection` at `0x180014d42`
- `KERNEL32!EnterCriticalSection` at `0x180014d81`
- `KERNEL32!LeaveCriticalSection` at `0x180014d74`
- `KERNEL32!LeaveCriticalSection` at `0x180014dc9`
- `KERNEL32!LeaveCriticalSection` at `0x180014d74`
- `KERNEL32!LeaveCriticalSection` at `0x180014dc9`
- `KERNEL32!WaitForSingleObject` at `0x180014da1`
- `KERNEL32!WaitForSingleObject` at `0x180014da1`

## pseudocode

```c
__int64 __fastcall AcquireWriteLock(_QWORD *a1)
{
  unsigned int v2; // edi
  LPVOID v3; // rcx

  v2 = 0;
  EnterCriticalSection(&CriticalSection);
  if ( !*a1 )
  {
    v3 = lpMem;
    if ( lpMem )
    {
      lpMem = *(LPVOID *)lpMem;
      *a1 = v3;
    }
    else
    {
      v2 = CreateReadWriteLock(a1);
      if ( v2 )
      {
        LeaveCriticalSection(&CriticalSection);
        return v2;
      }
    }
  }
  _InterlockedIncrement((volatile signed __int32 *)(*a1 + 64LL));
  LeaveCriticalSection(&CriticalSection);
  EnterCriticalSection((LPCRITICAL_SECTION)(*a1 + 8LL));
  if ( _InterlockedDecrement((volatile signed __int32 *)(*a1 + 48LL)) >= 0 )
    WaitForSingleObject(*(HANDLE *)(*a1 + 56LL), 0xFFFFFFFF);
  return v2;
}

```

## disassembly

```asm
0x180014d2c  mov     [rsp+arg_0], rbx
0x180014d31  push    rdi
0x180014d32  sub     rsp, 20h
0x180014d36  mov     rbx, rcx
0x180014d39  xor     edi, edi
0x180014d3b  lea     rcx, CriticalSection; lpCriticalSection
0x180014d42  call    cs:__imp_EnterCriticalSection
0x180014d48  cmp     [rbx], rdi
0x180014d4b  jnz     short loc_180014D66
0x180014d4d  mov     rcx, cs:lpMem
0x180014d54  test    rcx, rcx
0x180014d57  jz      short loc_180014DB4
0x180014d59  mov     rax, [rcx]
0x180014d5c  mov     cs:lpMem, rax
0x180014d63  mov     [rbx], rcx
0x180014d66  mov     rax, [rbx]
0x180014d69  lock inc dword ptr [rax+40h]
0x180014d6d  lea     rcx, CriticalSection; lpCriticalSection
0x180014d74  call    cs:__imp_LeaveCriticalSection
0x180014d7a  mov     rcx, [rbx]
0x180014d7d  add     rcx, 8; lpCriticalSection
0x180014d81  call    cs:__imp_EnterCriticalSection
0x180014d87  mov     rcx, [rbx]
0x180014d8a  or      eax, 0FFFFFFFFh
0x180014d8d  lock xadd [rcx+30h], eax
0x180014d92  cmp     eax, 1
0x180014d95  js      short loc_180014DA7
0x180014d97  mov     rcx, [rbx]
0x180014d9a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014d9d  mov     rcx, [rcx+38h]; hHandle
0x180014da1  call    cs:__imp_WaitForSingleObject
0x180014da7  mov     rbx, [rsp+28h+arg_0]
0x180014dac  mov     eax, edi
0x180014dae  add     rsp, 20h
0x180014db2  pop     rdi
0x180014db3  retn
0x180014db4  mov     rcx, rbx
0x180014db7  call    CreateReadWriteLock
0x180014dbc  mov     edi, eax
0x180014dbe  test    eax, eax
0x180014dc0  jz      short loc_180014D66
0x180014dc2  lea     rcx, CriticalSection; lpCriticalSection
0x180014dc9  call    cs:__imp_LeaveCriticalSection
0x180014dcf  jmp     short loc_180014DA7
```
