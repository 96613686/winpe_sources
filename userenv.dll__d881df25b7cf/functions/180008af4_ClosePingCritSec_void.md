# ClosePingCritSec(void)

- ea: `0x180008af4`
- end: `0x180008b36`
- name: `?ClosePingCritSec@@YAXXZ`
- size: `66`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d4e0`

## callees

- `0x180008af4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008b0a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008b0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b1d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b1d`

## pseudocode

```c
void ClosePingCritSec(void)
{
  if ( g_PingCritSec )
  {
    DeleteCriticalSection(g_PingCritSec);
    LocalFree(g_PingCritSec);
    g_PingCritSec = 0;
  }
}

```

## disassembly

```asm
0x180008af4  sub     rsp, 28h
0x180008af8  mov     rcx, cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA; lpCriticalSection
0x180008aff  test    rcx, rcx
0x180008b02  jnz     short loc_180008B0A
0x180008b04  add     rsp, 28h
0x180008b08  retn
0x180008b0a  call    cs:__imp_DeleteCriticalSection
0x180008b11  nop     dword ptr [rax+rax+00h]
0x180008b16  mov     rcx, cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA; hMem
0x180008b1d  call    cs:__imp_LocalFree
0x180008b24  nop     dword ptr [rax+rax+00h]
0x180008b29  mov     cs:?g_PingCritSec@@3PEAU_RTL_CRITICAL_SECTION@@EA, 0; _RTL_CRITICAL_SECTION * g_PingCritSec
0x180008b34  jmp     short loc_180008B04
```
