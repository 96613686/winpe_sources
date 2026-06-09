# WP_RECYCLER::~WP_RECYCLER(void)

- ea: `0x180002f44`
- end: `0x180002f7e`
- name: `??1WP_RECYCLER@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c20`

## callees

- `0x180002f44`
- `0x180008c60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002f5e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002f5e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002f77`

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
0x180002f44  push    rbx
0x180002f46  sub     rsp, 20h
0x180002f4a  mov     rbx, rcx
0x180002f4d  call    ?TerminateInstance@WP_RECYCLER@@QEAAXXZ; WP_RECYCLER::TerminateInstance(void)
0x180002f52  cmp     dword ptr [rbx+0B4h], 0
0x180002f59  jz      short loc_180002F6E
0x180002f5b  mov     rcx, rbx; lpCriticalSection
0x180002f5e  call    cs:__imp_DeleteCriticalSection
0x180002f64  mov     dword ptr [rbx+0B4h], 0
0x180002f6e  lea     rcx, [rbx+50h]
0x180002f72  add     rsp, 20h
0x180002f76  pop     rbx
0x180002f77  jmp     cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
```
