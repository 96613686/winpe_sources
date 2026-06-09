# THREAD_POOL_DATA::ThreadPoolThread(void)

- ea: `0x180001090`
- end: `0x180001158`
- name: `?ThreadPoolThread@THREAD_POOL_DATA@@QEAAKXZ`
- size: `200`
- prototype: `unsigned int __fastcall(THREAD_POOL_DATA *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001090`
- `0x180001160`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001137`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800010d3`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800010d3`

## pseudocode

```c
__int64 __fastcall THREAD_POOL_DATA::ThreadPoolThread(THREAD_POOL_DATA *this)
{
  BOOL QueuedCompletionStatus; // eax
  unsigned int (*v3)(void *); // rdx
  DWORD LastError; // edi
  unsigned int v5; // ecx
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 CompletionKey; // [rsp+58h] [rbp+10h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+60h] [rbp+18h] BYREF

  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  while ( 1 )
  {
    Overlapped = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 6);
    QueuedCompletionStatus = GetQueuedCompletionStatus(
                               *((HANDLE *)this + 1),
                               &NumberOfBytesTransferred,
                               &CompletionKey,
                               &Overlapped,
                               *((_DWORD *)this + 15));
    _InterlockedDecrement((volatile signed __int32 *)this + 6);
    _InterlockedIncrement((volatile signed __int32 *)this + 5);
    if ( QueuedCompletionStatus )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( !Overlapped )
        goto LABEL_16;
    }
    if ( CompletionKey == -1 )
      break;
    if ( *((_DWORD *)this + 7)
      || *((_DWORD *)this + 21)
      || *((_DWORD *)this + 6)
      || (v5 = *((_DWORD *)this + 4), v5 >= *((_DWORD *)this + 14))
      || v5 >= *((_DWORD *)this + 13) )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, LPOVERLAPPED))CompletionKey)(
        LastError,
        NumberOfBytesTransferred,
        Overlapped);
    }
    else
    {
      THREAD_MANAGER::RequestThread(*((char **)this + 4), v3, this);
      ((void (__fastcall *)(_QWORD, _QWORD, LPOVERLAPPED))CompletionKey)(
        LastError,
        NumberOfBytesTransferred,
        Overlapped);
    }
    _InterlockedDecrement((volatile signed __int32 *)this + 5);
  }
  LastError = 0;
LABEL_16:
  _InterlockedDecrement((volatile signed __int32 *)this + 5);
  return LastError;
}

```

## disassembly

```asm
0x180001090  push    rbx
0x180001092  push    rsi
0x180001093  push    rdi
0x180001094  sub     rsp, 30h
0x180001098  xor     esi, esi
0x18000109a  mov     rbx, rcx
0x18000109d  mov     [rsp+48h+NumberOfBytesTransferred], esi
0x1800010a1  mov     [rsp+48h+CompletionKey], rsi
0x1800010a6  nop     word ptr [rax+rax+00000000h]
0x1800010b0  mov     [rsp+48h+Overlapped], rsi
0x1800010b5  lock inc dword ptr [rbx+18h]
0x1800010b9  mov     eax, [rbx+3Ch]
0x1800010bc  lea     r9, [rsp+48h+Overlapped]; lpOverlapped
0x1800010c1  mov     rcx, [rbx+8]; CompletionPort
0x1800010c5  lea     r8, [rsp+48h+CompletionKey]; lpCompletionKey
0x1800010ca  lea     rdx, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800010cf  mov     [rsp+48h+dwMilliseconds], eax; dwMilliseconds
0x1800010d3  call    cs:__imp_GetQueuedCompletionStatus
0x1800010d9  lock dec dword ptr [rbx+18h]
0x1800010dd  lock inc dword ptr [rbx+14h]
0x1800010e1  test    eax, eax
0x1800010e3  jz      short loc_180001137
0x1800010e5  mov     edi, esi
0x1800010e7  mov     rax, [rsp+48h+CompletionKey]
0x1800010ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800010f0  jz      short loc_180001148
0x1800010f2  cmp     [rbx+1Ch], esi
0x1800010f5  jnz     short loc_180001101
0x1800010f7  cmp     [rbx+54h], esi
0x1800010fa  jnz     short loc_180001101
0x1800010fc  cmp     [rbx+18h], esi
0x1800010ff  jz      short loc_180001117
0x180001101  mov     r8, [rsp+48h+Overlapped]
0x180001106  mov     ecx, edi
0x180001108  mov     edx, [rsp+48h+NumberOfBytesTransferred]
0x18000110c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001111  lock dec dword ptr [rbx+14h]
0x180001115  jmp     short loc_1800010B0
0x180001117  mov     ecx, [rbx+10h]
0x18000111a  cmp     ecx, [rbx+38h]
0x18000111d  jnb     short loc_180001101
0x18000111f  cmp     ecx, [rbx+34h]
0x180001122  jnb     short loc_180001101
0x180001124  mov     rcx, [rbx+20h]; Parameter
0x180001128  mov     r8, rbx; void *
0x18000112b  call    ?RequestThread@THREAD_MANAGER@@QEAAXP6AKPEAX@Z0@Z; THREAD_MANAGER::RequestThread(ulong (*)(void *),void *)
0x180001130  mov     rax, [rsp+48h+CompletionKey]
0x180001135  jmp     short loc_180001101
0x180001137  call    cs:__imp_GetLastError
0x18000113d  mov     edi, eax
0x18000113f  cmp     [rsp+48h+Overlapped], rsi
0x180001144  jnz     short loc_1800010E7
0x180001146  jmp     short loc_18000114A
0x180001148  mov     edi, esi
0x18000114a  lock dec dword ptr [rbx+14h]
0x18000114e  mov     eax, edi
0x180001150  add     rsp, 30h
0x180001154  pop     rdi
0x180001155  pop     rsi
0x180001156  pop     rbx
0x180001157  retn
```
