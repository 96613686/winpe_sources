# PfsWorkerStop

- ea: `0x180059264`
- end: `0x1800592f2`
- name: `PfsWorkerStop`
- size: `142`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180057710`
- `0x180059164`
- `0x180064c68`
- `0x18006f4fc`
- `0x18006f950`
- `0x180071358`
- `0x18009e9f0`

## callees

- `0x180059264`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x1800592b2`
- `ntdll!NtSetInformationThread` at `0x1800592b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800592c9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800592c9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005928c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005928c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800592d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800592e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800592d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800592e1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800592bd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800592bd`

## pseudocode

```c
BOOL __fastcall PfsWorkerStop(__int64 a1, char a2)
{
  bool v2; // zf
  void *v5; // rcx
  BOOL result; // eax
  void *v7; // rcx
  int ThreadInformation; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD *)a1 == 0;
  ThreadInformation = 0;
  if ( !v2 )
  {
    *(_DWORD *)(a1 + 16) = 1;
    SetEvent(*(HANDLE *)(a1 + 8));
    if ( (a2 & 1) != 0 )
    {
      v5 = *(void **)a1;
      ThreadInformation = 2;
      NtSetInformationThread(v5, ThreadIoPriority, &ThreadInformation, 4u);
      SetThreadPriority(*(HANDLE *)a1, 0);
    }
    WaitForSingleObject(*(HANDLE *)a1, 0xFFFFFFFF);
    result = CloseHandle(*(HANDLE *)a1);
  }
  v7 = *(void **)(a1 + 8);
  if ( v7 )
    return CloseHandle(v7);
  return result;
}

```

## disassembly

```asm
0x180059264  mov     [rsp+arg_8], rbx
0x180059269  push    rdi
0x18005926a  sub     rsp, 20h
0x18005926e  cmp     qword ptr [rcx], 0
0x180059272  mov     edi, edx
0x180059274  mov     rbx, rcx
0x180059277  mov     [rsp+28h+ThreadInformation], 0
0x18005927f  jz      short loc_1800592D8
0x180059281  mov     dword ptr [rcx+10h], 1
0x180059288  mov     rcx, [rcx+8]; hEvent
0x18005928c  call    cs:__imp_SetEvent
0x180059292  test    dil, 1
0x180059296  jz      short loc_1800592C3
0x180059298  mov     rcx, [rbx]; ThreadHandle
0x18005929b  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x1800592a0  mov     r9d, 4; ThreadInformationLength
0x1800592a6  mov     [rsp+28h+ThreadInformation], 2
0x1800592ae  lea     edx, [r9+12h]; ThreadInformationClass
0x1800592b2  call    cs:__imp_NtSetInformationThread
0x1800592b8  mov     rcx, [rbx]; hThread
0x1800592bb  xor     edx, edx; nPriority
0x1800592bd  call    cs:__imp_SetThreadPriority
0x1800592c3  mov     rcx, [rbx]; hHandle
0x1800592c6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800592c9  call    cs:__imp_WaitForSingleObject
0x1800592cf  mov     rcx, [rbx]; hObject
0x1800592d2  call    cs:__imp_CloseHandle
0x1800592d8  mov     rcx, [rbx+8]; hObject
0x1800592dc  test    rcx, rcx
0x1800592df  jz      short loc_1800592E7
0x1800592e1  call    cs:__imp_CloseHandle
0x1800592e7  mov     rbx, [rsp+28h+arg_8]
0x1800592ec  add     rsp, 20h
0x1800592f0  pop     rdi
0x1800592f1  retn
```
