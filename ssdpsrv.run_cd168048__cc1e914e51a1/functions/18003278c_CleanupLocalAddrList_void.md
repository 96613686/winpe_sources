# CleanupLocalAddrList(void)

- ea: `0x18003278c`
- end: `0x18003280f`
- name: `?CleanupLocalAddrList@@YAXXZ`
- size: `131`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002f900`

## callees

- `0x18003278c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800327c2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800327c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800327ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800327ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800327a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800327a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800327fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800327fd`

## pseudocode

```c
void CleanupLocalAddrList(void)
{
  if ( dword_180045714 )
  {
    EnterCriticalSection(&s_csPipValid);
    dword_180045714 = 0;
    if ( Block )
    {
      free(Block);
      Block = 0;
    }
    dword_180045728 = 0;
    LeaveCriticalSection(&s_csPipValid);
    DeleteCriticalSection(&s_csPipValid);
  }
}

```

## disassembly

```asm
0x18003278c  sub     rsp, 28h
0x180032790  cmp     cs:dword_180045714, 0
0x180032797  jz      short loc_180032809
0x180032799  lea     rcx, ?s_csPipValid@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800327a0  call    cs:__imp_EnterCriticalSection
0x1800327a7  nop     dword ptr [rax+rax+00h]
0x1800327ac  mov     rcx, cs:Block; Block
0x1800327b3  mov     cs:dword_180045714, 0
0x1800327bd  test    rcx, rcx
0x1800327c0  jz      short loc_1800327D9
0x1800327c2  call    cs:__imp_free
0x1800327c9  nop     dword ptr [rax+rax+00h]
0x1800327ce  mov     cs:Block, 0
0x1800327d9  lea     rcx, ?s_csPipValid@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800327e0  mov     cs:dword_180045728, 0
0x1800327ea  call    cs:__imp_LeaveCriticalSection
0x1800327f1  nop     dword ptr [rax+rax+00h]
0x1800327f6  lea     rcx, ?s_csPipValid@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800327fd  call    cs:__imp_DeleteCriticalSection
0x180032804  nop     dword ptr [rax+rax+00h]
0x180032809  add     rsp, 28h
0x18003280d  retn
```
