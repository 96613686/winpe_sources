# InitializeListNetwork(void)

- ea: `0x18000b71c`
- end: `0x18000b7bc`
- name: `?InitializeListNetwork@@YAJXZ`
- size: `160`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a768`

## callees

- `0x18000b71c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b765`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b794`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b765`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b794`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000b727`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000b735`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000b727`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000b735`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b743`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b772`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b743`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b772`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b7a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b7a5`

## pseudocode

```c
__int64 InitializeListNetwork(void)
{
  InitializeCriticalSection(&stru_180042200);
  InitializeCriticalSection(&stru_180042240);
  EnterCriticalSection(&stru_180042200);
  qword_1800421F8 = (__int64)&Block;
  Block = (struct _SSDPNetwork *)&Block;
  LeaveCriticalSection(&stru_180042200);
  EnterCriticalSection(&stru_180042240);
  qword_180042238 = (__int64)&qword_180042230;
  qword_180042230 = (struct _SSDPNetwork *)&qword_180042230;
  LeaveCriticalSection(&stru_180042240);
  return 0;
}

```

## disassembly

```asm
0x18000b71c  sub     rsp, 28h
0x18000b720  lea     rcx, stru_180042200; lpCriticalSection
0x18000b727  call    cs:__imp_InitializeCriticalSection
0x18000b72d  nop
0x18000b72e  lea     rcx, stru_180042240; lpCriticalSection
0x18000b735  call    cs:__imp_InitializeCriticalSection
0x18000b73b  nop
0x18000b73c  lea     rcx, stru_180042200; lpCriticalSection
0x18000b743  call    cs:__imp_EnterCriticalSection
0x18000b749  lea     rax, Block
0x18000b750  mov     cs:qword_1800421F8, rax
0x18000b757  mov     cs:Block, rax
0x18000b75e  lea     rcx, stru_180042200; lpCriticalSection
0x18000b765  call    cs:__imp_LeaveCriticalSection
0x18000b76b  lea     rcx, stru_180042240; lpCriticalSection
0x18000b772  call    cs:__imp_EnterCriticalSection
0x18000b778  lea     rax, qword_180042230
0x18000b77f  mov     cs:qword_180042238, rax
0x18000b786  mov     cs:qword_180042230, rax
0x18000b78d  lea     rcx, stru_180042240; lpCriticalSection
0x18000b794  call    cs:__imp_LeaveCriticalSection
0x18000b79a  xor     eax, eax
0x18000b79c  jmp     short loc_18000B7B7
0x18000b79e  lea     rcx, stru_180042200; lpCriticalSection
0x18000b7a5  call    cs:__imp_DeleteCriticalSection
0x18000b7ab  mov     eax, 8007000Eh
0x18000b7b0  jmp     short loc_18000B7B7
0x18000b7b2  mov     eax, 8007000Eh
0x18000b7b7  add     rsp, 28h
0x18000b7bb  retn
0x18003530c  push    rbp
0x18003530e  sub     rsp, 20h
0x180035312  mov     rbp, rdx
0x180035315  mov     rax, [rcx]
0x180035318  xor     ecx, ecx
0x18003531a  cmp     dword ptr [rax], 0C0000017h
0x180035320  setz    cl
0x180035323  mov     eax, ecx
0x180035325  add     rsp, 20h
0x180035329  pop     rbp
0x18003532a  retn
0x18003532c  push    rbp
0x18003532e  sub     rsp, 20h
0x180035332  mov     rbp, rdx
0x180035335  mov     rax, [rcx]
0x180035338  xor     ecx, ecx
0x18003533a  cmp     dword ptr [rax], 0C0000017h
0x180035340  setz    cl
0x180035343  mov     eax, ecx
0x180035345  add     rsp, 20h
0x180035349  pop     rbp
0x18003534a  retn
```
