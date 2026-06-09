# ReleaseReadLock

- ea: `0x180015100`
- end: `0x180015171`
- name: `ReleaseReadLock`
- size: `113`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: ``

## callers

- `0x1800039a0`
- `0x180006250`
- `0x180006990`
- `0x180007050`
- `0x1800071a0`
- `0x18000a450`
- `0x18000a770`
- `0x18000ae90`
- `0x18000b2d8`
- `0x18000cee0`
- `0x180011850`
- `0x180012800`
- `0x1800134c0`
- `0x180013930`
- `0x180014580`
- `0x180014970`
- `0x180016a40`
- `0x180017a44`
- `0x180018070`
- `0x18001958c`
- `0x180019de0`
- `0x18001a360`
- `0x18001af20`
- `0x18001e77c`
- `0x18001e8d4`
- `0x18001ed64`

## callees

- `0x180015100`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001512d`
- `KERNEL32!EnterCriticalSection` at `0x18001512d`
- `KERNEL32!LeaveCriticalSection` at `0x18001516a`
- `KERNEL32!SetEvent` at `0x180015120`
- `KERNEL32!SetEvent` at `0x180015120`

## pseudocode

```c
void __fastcall ReleaseReadLock(__int64 a1)
{
  _QWORD *v2; // rdx

  if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)a1 + 48LL)) < 0 )
    SetEvent(*(HANDLE *)(*(_QWORD *)a1 + 56LL));
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
0x180015100  push    rbx
0x180015102  sub     rsp, 20h
0x180015106  mov     rdx, [rcx]
0x180015109  mov     rbx, rcx
0x18001510c  or      eax, 0FFFFFFFFh
0x18001510f  lock xadd [rdx+30h], eax
0x180015114  cmp     eax, 1
0x180015117  jns     short loc_180015126
0x180015119  mov     rcx, [rcx]
0x18001511c  mov     rcx, [rcx+38h]; hEvent
0x180015120  call    cs:__imp_SetEvent
0x180015126  lea     rcx, CriticalSection; lpCriticalSection
0x18001512d  call    cs:__imp_EnterCriticalSection
0x180015133  mov     rdx, [rbx]
0x180015136  or      eax, 0FFFFFFFFh
0x180015139  lock xadd [rdx+40h], eax
0x18001513e  cmp     eax, 1
0x180015141  jnz     short loc_18001515E
0x180015143  mov     rdx, [rbx]
0x180015146  mov     rax, cs:lpMem
0x18001514d  mov     [rdx], rax
0x180015150  mov     cs:lpMem, rdx
0x180015157  mov     qword ptr [rbx], 0
0x18001515e  lea     rcx, CriticalSection
0x180015165  add     rsp, 20h
0x180015169  pop     rbx
0x18001516a  jmp     cs:__imp_LeaveCriticalSection
```
