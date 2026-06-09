# SCEventsReleaseCriticalSections(void)

- ea: `0x180017088`
- end: `0x1800170f1`
- name: `?SCEventsReleaseCriticalSections@@YAXXZ`
- size: `105`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001210`

## callees

- `0x180017088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001709c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800170bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800170dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001709c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800170bc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800170dc`

## pseudocode

```c
void SCEventsReleaseCriticalSections(void)
{
  if ( dword_180045A28 )
  {
    DeleteCriticalSection(&stru_1800455F0);
    dword_180045A28 = 0;
  }
  if ( dword_180045A10 )
  {
    DeleteCriticalSection(&CriticalSection);
    dword_180045A10 = 0;
  }
  if ( dword_180045A2C )
  {
    DeleteCriticalSection(&stru_1800455C8);
    dword_180045A2C = 0;
  }
}

```

## disassembly

```asm
0x180017088  sub     rsp, 28h
0x18001708c  cmp     cs:dword_180045A28, 0
0x180017093  jz      short loc_1800170AC
0x180017095  lea     rcx, stru_1800455F0; lpCriticalSection
0x18001709c  call    cs:__imp_DeleteCriticalSection
0x1800170a2  mov     cs:dword_180045A28, 0
0x1800170ac  cmp     cs:dword_180045A10, 0
0x1800170b3  jz      short loc_1800170CC
0x1800170b5  lea     rcx, CriticalSection; lpCriticalSection
0x1800170bc  call    cs:__imp_DeleteCriticalSection
0x1800170c2  mov     cs:dword_180045A10, 0
0x1800170cc  cmp     cs:dword_180045A2C, 0
0x1800170d3  jz      short loc_1800170EC
0x1800170d5  lea     rcx, stru_1800455C8; lpCriticalSection
0x1800170dc  call    cs:__imp_DeleteCriticalSection
0x1800170e2  mov     cs:dword_180045A2C, 0
0x1800170ec  add     rsp, 28h
0x1800170f0  retn
```
