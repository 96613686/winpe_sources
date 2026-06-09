# InitializeListNetwork(void)

- ea: `0x18000d140`
- end: `0x18000d20b`
- name: `?InitializeListNetwork@@YAJXZ`
- size: `203`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c078`

## callees

- `0x18000d140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d19b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d19b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1d6`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d14b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d15f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d14b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d15f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d173`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d1ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d1ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d1ed`

## pseudocode

```c
__int64 InitializeListNetwork(void)
{
  InitializeCriticalSection(&stru_1800452F8);
  InitializeCriticalSection(&stru_180045330);
  EnterCriticalSection(&stru_1800452F8);
  qword_1800452F0 = (__int64)&qword_1800452E8;
  qword_1800452E8 = (struct _SSDPNetwork *)&qword_1800452E8;
  LeaveCriticalSection(&stru_1800452F8);
  EnterCriticalSection(&stru_180045330);
  qword_180045328 = (__int64)&qword_180045320;
  qword_180045320 = (struct _SSDPNetwork *)&qword_180045320;
  LeaveCriticalSection(&stru_180045330);
  return 0;
}

```

## disassembly

```asm
0x18000d140  sub     rsp, 28h
0x18000d144  lea     rcx, stru_1800452F8; lpCriticalSection
0x18000d14b  call    cs:__imp_InitializeCriticalSection
0x18000d152  nop     dword ptr [rax+rax+00h]
0x18000d157  nop
0x18000d158  lea     rcx, stru_180045330; lpCriticalSection
0x18000d15f  call    cs:__imp_InitializeCriticalSection
0x18000d166  nop     dword ptr [rax+rax+00h]
0x18000d16b  nop
0x18000d16c  lea     rcx, stru_1800452F8; lpCriticalSection
0x18000d173  call    cs:__imp_EnterCriticalSection
0x18000d17a  nop     dword ptr [rax+rax+00h]
0x18000d17f  lea     rax, qword_1800452E8
0x18000d186  mov     cs:qword_1800452F0, rax
0x18000d18d  mov     cs:qword_1800452E8, rax
0x18000d194  lea     rcx, stru_1800452F8; lpCriticalSection
0x18000d19b  call    cs:__imp_LeaveCriticalSection
0x18000d1a2  nop     dword ptr [rax+rax+00h]
0x18000d1a7  lea     rcx, stru_180045330; lpCriticalSection
0x18000d1ae  call    cs:__imp_EnterCriticalSection
0x18000d1b5  nop     dword ptr [rax+rax+00h]
0x18000d1ba  lea     rax, qword_180045320
0x18000d1c1  mov     cs:qword_180045328, rax
0x18000d1c8  mov     cs:qword_180045320, rax
0x18000d1cf  lea     rcx, stru_180045330; lpCriticalSection
0x18000d1d6  call    cs:__imp_LeaveCriticalSection
0x18000d1dd  nop     dword ptr [rax+rax+00h]
0x18000d1e2  xor     eax, eax
0x18000d1e4  jmp     short loc_18000D205
0x18000d1e6  lea     rcx, stru_1800452F8; lpCriticalSection
0x18000d1ed  call    cs:__imp_DeleteCriticalSection
0x18000d1f4  nop     dword ptr [rax+rax+00h]
0x18000d1f9  mov     eax, 8007000Eh
0x18000d1fe  jmp     short loc_18000D205
0x18000d200  mov     eax, 8007000Eh
0x18000d205  add     rsp, 28h
0x18000d209  retn
0x180037e4c  push    rbp
0x180037e4e  sub     rsp, 20h
0x180037e52  mov     rbp, rdx
0x180037e55  mov     rax, [rcx]
0x180037e58  xor     ecx, ecx
0x180037e5a  cmp     dword ptr [rax], 0C0000017h
0x180037e60  setz    cl
0x180037e63  mov     eax, ecx
0x180037e65  add     rsp, 20h
0x180037e69  pop     rbp
0x180037e6a  retn
0x180037e6c  push    rbp
0x180037e6e  sub     rsp, 20h
0x180037e72  mov     rbp, rdx
0x180037e75  mov     rax, [rcx]
0x180037e78  xor     ecx, ecx
0x180037e7a  cmp     dword ptr [rax], 0C0000017h
0x180037e80  setz    cl
0x180037e83  mov     eax, ecx
0x180037e85  add     rsp, 20h
0x180037e89  pop     rbp
0x180037e8a  retn
```
