# ReleaseWriteLock

- ea: `0x180015178`
- end: `0x1800151e3`
- name: `ReleaseWriteLock`
- size: `107`
- prototype: ``
- caller_count: `41`
- callee_count: `1`
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
- `0x18000cf90`
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

- `0x180015178`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001519f`
- `KERNEL32!EnterCriticalSection` at `0x18001519f`
- `KERNEL32!LeaveCriticalSection` at `0x180015192`
- `KERNEL32!LeaveCriticalSection` at `0x180015192`
- `KERNEL32!LeaveCriticalSection` at `0x1800151dc`

## pseudocode

```c
void __fastcall ReleaseWriteLock(__int64 a1)
{
  _QWORD *v2; // rdx

  *(_DWORD *)(*(_QWORD *)a1 + 48LL) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)a1 + 8LL));
  EnterCriticalSection(&CriticalSection);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)a1 + 64LL), 0xFFFFFFFF) == 1 )
  {
    v2 = *(_QWORD **)a1;
    *v2 = lpMem;
    lpMem = v2;
    *(_QWORD *)a1 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180015178  push    rbx
0x18001517a  sub     rsp, 20h
0x18001517e  mov     rax, [rcx]
0x180015181  mov     rbx, rcx
0x180015184  mov     dword ptr [rax+30h], 0
0x18001518b  mov     rcx, [rcx]
0x18001518e  add     rcx, 8; lpCriticalSection
0x180015192  call    cs:__imp_LeaveCriticalSection
0x180015198  lea     rcx, CriticalSection; lpCriticalSection
0x18001519f  call    cs:__imp_EnterCriticalSection
0x1800151a5  mov     rdx, [rbx]
0x1800151a8  or      eax, 0FFFFFFFFh
0x1800151ab  lock xadd [rdx+40h], eax
0x1800151b0  cmp     eax, 1
0x1800151b3  jnz     short loc_1800151D0
0x1800151b5  mov     rdx, [rbx]
0x1800151b8  mov     rax, cs:lpMem
0x1800151bf  mov     [rdx], rax
0x1800151c2  mov     cs:lpMem, rdx
0x1800151c9  mov     qword ptr [rbx], 0
0x1800151d0  lea     rcx, CriticalSection
0x1800151d7  add     rsp, 20h
0x1800151db  pop     rbx
0x1800151dc  jmp     cs:__imp_LeaveCriticalSection
```
