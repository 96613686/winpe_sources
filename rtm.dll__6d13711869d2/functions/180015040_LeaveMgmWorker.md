# LeaveMgmWorker

- ea: `0x180015040`
- end: `0x180015087`
- name: `LeaveMgmWorker`
- size: `71`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x180011850`
- `0x180012620`
- `0x180012800`
- `0x180012d80`
- `0x180012ed0`
- `0x180013020`
- `0x180013140`
- `0x180013260`
- `0x180013390`
- `0x1800134c0`
- `0x1800136d0`
- `0x1800137e0`
- `0x180013930`
- `0x180014200`
- `0x180014580`
- `0x180014970`
- `0x180016470`
- `0x1800167d0`
- `0x180018070`
- `0x180018c10`
- `0x180019de0`
- `0x18001a360`
- `0x18001af20`

## callees

- `0x180015040`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x18001506f`
- `KERNEL32!ReleaseSemaphore` at `0x18001506f`
- `KERNEL32!EnterCriticalSection` at `0x18001504b`
- `KERNEL32!EnterCriticalSection` at `0x18001504b`
- `KERNEL32!LeaveCriticalSection` at `0x180015080`

## pseudocode

```c
void LeaveMgmWorker()
{
  EnterCriticalSection(&ig);
  --dword_18002B918;
  if ( dword_18002B908 == 102 )
    ReleaseSemaphore(hSemaphore, 1, 0);
  LeaveCriticalSection(&ig);
}

```

## disassembly

```asm
0x180015040  sub     rsp, 28h
0x180015044  lea     rcx, ig; lpCriticalSection
0x18001504b  call    cs:__imp_EnterCriticalSection
0x180015051  mov     edx, 1; lReleaseCount
0x180015056  sub     cs:dword_18002B918, edx
0x18001505c  cmp     cs:dword_18002B908, 66h ; 'f'
0x180015063  jnz     short loc_180015075
0x180015065  mov     rcx, cs:hSemaphore; hSemaphore
0x18001506c  xor     r8d, r8d; lpPreviousCount
0x18001506f  call    cs:__imp_ReleaseSemaphore
0x180015075  lea     rcx, ig
0x18001507c  add     rsp, 28h
0x180015080  jmp     cs:__imp_LeaveCriticalSection
```
