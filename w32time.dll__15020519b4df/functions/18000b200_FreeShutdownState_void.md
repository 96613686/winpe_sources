# FreeShutdownState(void)

- ea: `0x18000b200`
- end: `0x18000b25a`
- name: `?FreeShutdownState@@YAXXZ`
- size: `90`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009a80`
- `0x180039100`

## callees

- `0x18000b200`
- `0x18003dd2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b242`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b242`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b219`

## pseudocode

```c
void FreeShutdownState(void)
{
  if ( g_shutdown )
  {
    DeleteCriticalSection(&stru_1800A3638);
    g_shutdown = 0;
  }
  if ( qword_1800A3660 )
    CloseHandle(qword_1800A3660);
  memset_0(&g_shutdown, 0, 0x58u);
}

```

## disassembly

```asm
0x18000b200  sub     rsp, 28h
0x18000b204  cmp     cs:?g_shutdown@@3UShutdownInfo@@A, 0; ShutdownInfo g_shutdown
0x18000b20b  jnz     short loc_18000B23B
0x18000b20d  mov     rcx, cs:qword_1800A3660; hObject
0x18000b214  test    rcx, rcx
0x18000b217  jz      short loc_18000B225
0x18000b219  call    cs:__imp_CloseHandle
0x18000b220  nop     dword ptr [rax+rax+00h]
0x18000b225  xor     edx, edx; Val
0x18000b227  lea     rcx, ?g_shutdown@@3UShutdownInfo@@A; void *
0x18000b22e  lea     r8d, [rdx+58h]; Size
0x18000b232  add     rsp, 28h
0x18000b236  jmp     memset_0
0x18000b23b  lea     rcx, stru_1800A3638; lpCriticalSection
0x18000b242  call    cs:__imp_DeleteCriticalSection
0x18000b249  nop     dword ptr [rax+rax+00h]
0x18000b24e  mov     cs:?g_shutdown@@3UShutdownInfo@@A, 0; ShutdownInfo g_shutdown
0x18000b258  jmp     short loc_18000B20D
```
