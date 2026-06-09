# PfTaskUpdateTaskSettings

- ea: `0x18005ec74`
- end: `0x18005ecf5`
- name: `PfTaskUpdateTaskSettings`
- size: `129`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18007abe0`
- `0x180083b00`
- `0x1800a3490`
- `0x1800a6088`
- `0x1800a6758`

## callees

- `0x18005ec74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ecc6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005ecc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ecb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ecd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ecb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ecd0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ece2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ece2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005eca8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005eca8`

## pseudocode

```c
__int64 __fastcall PfTaskUpdateTaskSettings(__int64 a1, __int64 a2, __int64 a3)
{
  HANDLE Thread; // rax
  void *v4; // rdi
  DWORD LastError; // ebx
  _QWORD v7[3]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v8; // [rsp+48h] [rbp-10h]

  v7[0] = a1;
  v7[1] = a2;
  v7[2] = a3;
  v8 = 0;
  Thread = CreateThread(0, 0, PfTaskUpdateTaskSettingsWorker, v7, 0, 0);
  v4 = Thread;
  if ( Thread )
  {
    if ( WaitForSingleObject(Thread, 0xFFFFFFFF) )
      LastError = GetLastError();
    else
      LastError = (unsigned __int16)v8;
    CloseHandle(v4);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18005ec74  mov     rax, rsp
0x18005ec77  mov     [rax+8], rbx
0x18005ec7b  push    rdi
0x18005ec7c  sub     rsp, 50h
0x18005ec80  xor     ebx, ebx
0x18005ec82  mov     [rax-28h], rcx
0x18005ec86  mov     [rax-20h], rdx
0x18005ec8a  lea     r9, [rax-28h]; lpParameter
0x18005ec8e  mov     [rax-18h], r8
0x18005ec92  xor     edx, edx; dwStackSize
0x18005ec94  mov     [rax-30h], rbx
0x18005ec98  lea     r8, ?PfTaskUpdateTaskSettingsWorker@@YAKPEAX@Z; lpStartAddress
0x18005ec9f  xor     ecx, ecx; lpThreadAttributes
0x18005eca1  mov     [rax-38h], ebx
0x18005eca4  mov     [rax-10h], rbx
0x18005eca8  call    cs:__imp_CreateThread
0x18005ecae  mov     rdi, rax
0x18005ecb1  test    rax, rax
0x18005ecb4  jnz     short loc_18005ECC0
0x18005ecb6  call    cs:__imp_GetLastError
0x18005ecbc  mov     ebx, eax
0x18005ecbe  jmp     short loc_18005ECE8
0x18005ecc0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18005ecc3  mov     rcx, rdi; hHandle
0x18005ecc6  call    cs:__imp_WaitForSingleObject
0x18005eccc  test    eax, eax
0x18005ecce  jz      short loc_18005ECDA
0x18005ecd0  call    cs:__imp_GetLastError
0x18005ecd6  mov     ebx, eax
0x18005ecd8  jmp     short loc_18005ECDF
0x18005ecda  movzx   ebx, word ptr [rsp+58h+var_10]
0x18005ecdf  mov     rcx, rdi; hObject
0x18005ece2  call    cs:__imp_CloseHandle
0x18005ece8  mov     eax, ebx
0x18005ecea  mov     rbx, [rsp+58h+arg_0]
0x18005ecef  add     rsp, 50h
0x18005ecf3  pop     rdi
0x18005ecf4  retn
```
