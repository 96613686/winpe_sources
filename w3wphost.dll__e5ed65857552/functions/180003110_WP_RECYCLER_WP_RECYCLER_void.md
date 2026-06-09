# WP_RECYCLER::~WP_RECYCLER(void)

- ea: `0x180003110`
- end: `0x180003155`
- name: `??1WP_RECYCLER@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002dbc`

## callees

- `0x180003110`
- `0x180009640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000312a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000312a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003149`

## pseudocode

```c
void __fastcall WP_RECYCLER::~WP_RECYCLER(WP_RECYCLER *lpCriticalSection)
{
  WP_RECYCLER::TerminateInstance(lpCriticalSection);
  if ( *((_DWORD *)lpCriticalSection + 45) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)lpCriticalSection);
    *((_DWORD *)lpCriticalSection + 45) = 0;
  }
  BUFFER::~BUFFER((WP_RECYCLER *)((char *)lpCriticalSection + 80));
}

```

## disassembly

```asm
0x180003110  push    rbx
0x180003112  sub     rsp, 20h
0x180003116  mov     rbx, rcx
0x180003119  call    ?TerminateInstance@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateInstance(void)
0x18000311e  cmp     dword ptr [rbx+0B4h], 0
0x180003125  jz      short loc_180003140
0x180003127  mov     rcx, rbx; lpCriticalSection
0x18000312a  call    cs:__imp_DeleteCriticalSection
0x180003131  nop     dword ptr [rax+rax+00h]
0x180003136  mov     dword ptr [rbx+0B4h], 0
0x180003140  lea     rcx, [rbx+50h]
0x180003144  add     rsp, 20h
0x180003148  pop     rbx
0x180003149  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
