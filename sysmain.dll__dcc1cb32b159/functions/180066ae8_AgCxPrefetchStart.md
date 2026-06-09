# AgCxPrefetchStart

- ea: `0x180066ae8`
- end: `0x180066ca4`
- name: `AgCxPrefetchStart`
- size: `444`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800aa7e0`
- `0x1800ab17c`

## callees

- `0x180016f10`
- `0x18003cbe4`
- `0x18003cffc`
- `0x180066ae8`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x180066c27`
- `ntdll!NtQueryInformationThread` at `0x180066c27`
- `ntdll!NtSetInformationThread` at `0x180066c43`
- `ntdll!NtSetInformationThread` at `0x180066c43`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180066b75`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180066b75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066be0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066be0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180066bd2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180066bd2`

## pseudocode

```c
DWORD __fastcall AgCxPrefetchStart(__int64 a1, _QWORD *a2, unsigned int a3)
{
  __int64 v3; // rsi
  __int64 v5; // rdx
  __int64 v8; // rax
  void *v9; // rcx
  __int64 v10; // rcx
  HANDLE Thread; // rdi
  __int64 v13; // rcx
  struct _RTL_CRITICAL_SECTION *v14; // r10
  int ThreadInformation; // [rsp+58h] [rbp+10h] BYREF
  __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  v3 = a2[1];
  v5 = 1;
  ThreadInformation = 0;
  do
  {
    v8 = 5 * v5++;
    v8 *= 2;
    *(_OWORD *)&a2[v8 + 475] = *(_OWORD *)(a2 + 475);
    *(_OWORD *)&a2[v8 + 477] = *(_OWORD *)(a2 + 477);
    *(_OWORD *)&a2[v8 + 479] = *(_OWORD *)(a2 + 479);
    *(_OWORD *)&a2[v8 + 481] = *(_OWORD *)(a2 + 481);
    *(_OWORD *)&a2[v8 + 483] = *(_OWORD *)(a2 + 483);
  }
  while ( v5 != 4 );
  v9 = (void *)a2[483];
  if ( v9 )
    ResetEvent(v9);
  *(_BYTE *)a2 = 1;
  if ( (*(_DWORD *)a2 & 0x20000) != 0 && (*((_BYTE *)a2 + 3804) & 4) != 0 )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL);
    if ( v10 )
      PfRbPrefetchEnable(*(_QWORD *)(v10 + 8) + 9920LL, 1);
  }
  Thread = CreateThread(0, 0, AgCxPrefetchThread, a2, 0, 0);
  if ( !Thread )
    return GetLastError();
  v13 = *(_DWORD *)a2 & 0x1C000;
  if ( (((_DWORD)v13 - 0x4000) & 0xFFFEBFFF) == 0
    && (_DWORD)v13 != 98304
    && NtQueryInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadActualBasePriority, &ThreadInformation, 4u, 0) >= 0 )
  {
    NtSetInformationThread(Thread, ThreadActualBasePriority, &ThreadInformation, 4u);
  }
  a2[2] = Thread;
  if ( v3 )
    *(_QWORD *)(v3 + 8) = a2;
  if ( a3 )
  {
    *(_DWORD *)a2 ^= (*(_DWORD *)a2 ^ (a3 << 8)) & 0x3F00;
    v16 = PfsActionItemGetCurrentTime(v13) + 50000000;
    PfsActionItemQueueEx(v14 + 43, a3, (unsigned __int64 *)&v16, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180066ae8  mov     [rsp+arg_0], rbx
0x180066aed  push    rbp
0x180066aee  push    rsi
0x180066aef  push    rdi
0x180066af0  sub     rsp, 30h
0x180066af4  mov     rsi, [rdx+8]
0x180066af8  mov     rbx, rdx
0x180066afb  mov     edx, 1
0x180066b00  mov     [rsp+48h+ThreadInformation], 0
0x180066b08  mov     ebp, r8d
0x180066b0b  mov     rdi, rcx
0x180066b0e  movups  xmm0, xmmword ptr [rbx+0ED8h]
0x180066b15  lea     rax, [rdx+rdx*4]
0x180066b19  inc     rdx
0x180066b1c  add     rax, rax
0x180066b1f  movups  xmmword ptr [rbx+rax*8+0ED8h], xmm0
0x180066b27  movups  xmm1, xmmword ptr [rbx+0EE8h]
0x180066b2e  movups  xmmword ptr [rbx+rax*8+0EE8h], xmm1
0x180066b36  movups  xmm0, xmmword ptr [rbx+0EF8h]
0x180066b3d  movups  xmmword ptr [rbx+rax*8+0EF8h], xmm0
0x180066b45  movups  xmm1, xmmword ptr [rbx+0F08h]
0x180066b4c  movups  xmmword ptr [rbx+rax*8+0F08h], xmm1
0x180066b54  movups  xmm0, xmmword ptr [rbx+0F18h]
0x180066b5b  movups  xmmword ptr [rbx+rax*8+0F18h], xmm0
0x180066b63  cmp     rdx, 4
0x180066b67  jnz     short loc_180066B0E
0x180066b69  mov     rcx, [rbx+0F18h]; hEvent
0x180066b70  test    rcx, rcx
0x180066b73  jz      short loc_180066B7B
0x180066b75  call    cs:__imp_ResetEvent
0x180066b7b  mov     byte ptr [rbx], 1
0x180066b7e  test    dword ptr [rbx], 20000h
0x180066b84  jz      short loc_180066BB3
0x180066b86  test    byte ptr [rbx+0EDCh], 4
0x180066b8d  jz      short loc_180066BB3
0x180066b8f  mov     rax, [rdi+18h]
0x180066b93  mov     rcx, [rax+10h]
0x180066b97  test    rcx, rcx
0x180066b9a  jz      short loc_180066BB3
0x180066b9c  mov     rcx, [rcx+8]
0x180066ba0  xor     r8d, r8d
0x180066ba3  add     rcx, 26C0h
0x180066baa  lea     edx, [r8+1]
0x180066bae  call    PfRbPrefetchEnable
0x180066bb3  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x180066bbc  lea     r8, AgCxPrefetchThread; lpStartAddress
0x180066bc3  mov     r9, rbx; lpParameter
0x180066bc6  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180066bce  xor     edx, edx; dwStackSize
0x180066bd0  xor     ecx, ecx; lpThreadAttributes
0x180066bd2  call    cs:__imp_CreateThread
0x180066bd8  mov     rdi, rax
0x180066bdb  test    rax, rax
0x180066bde  jnz     short loc_180066BEB
0x180066be0  call    cs:__imp_GetLastError
0x180066be6  jmp     loc_180066C97
0x180066beb  mov     ecx, [rbx]
0x180066bed  and     ecx, 1C000h
0x180066bf3  lea     eax, [rcx-4000h]
0x180066bf9  test    eax, 0FFFEBFFFh
0x180066bfe  jnz     short loc_180066C49
0x180066c00  cmp     ecx, 18000h
0x180066c06  jz      short loc_180066C49
0x180066c08  mov     r9d, 4; ThreadInformationLength
0x180066c0e  mov     qword ptr [rsp+48h+dwCreationFlags], 0; ReturnLength
0x180066c17  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x180066c1c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180066c23  lea     edx, [r9+15h]; ThreadInformationClass
0x180066c27  call    cs:__imp_NtQueryInformationThread
0x180066c2d  test    eax, eax
0x180066c2f  js      short loc_180066C49
0x180066c31  mov     r9d, 4; ThreadInformationLength
0x180066c37  lea     r8, [rsp+48h+ThreadInformation]; ThreadInformation
0x180066c3c  mov     rcx, rdi; ThreadHandle
0x180066c3f  lea     edx, [r9+15h]; ThreadInformationClass
0x180066c43  call    cs:__imp_NtSetInformationThread
0x180066c49  mov     [rbx+10h], rdi
0x180066c4d  test    rsi, rsi
0x180066c50  jz      short loc_180066C56
0x180066c52  mov     [rsi+8], rbx
0x180066c56  test    ebp, ebp
0x180066c58  jz      short loc_180066C95
0x180066c5a  mov     eax, ebp
0x180066c5c  shl     eax, 8
0x180066c5f  xor     eax, [rbx]
0x180066c61  and     eax, 3F00h
0x180066c66  xor     [rbx], eax
0x180066c68  mov     r10, cs:PfSvcGlobals
0x180066c6f  call    PfsActionItemGetCurrentTime
0x180066c74  add     rax, 2FAF080h
0x180066c7a  lea     r8, [rsp+48h+arg_18]
0x180066c7f  xor     r9d, r9d
0x180066c82  mov     [rsp+48h+arg_18], rax
0x180066c87  mov     edx, ebp
0x180066c89  lea     rcx, [r10+6B8h]; lpCriticalSection
0x180066c90  call    PfsActionItemQueueEx
0x180066c95  xor     eax, eax
0x180066c97  mov     rbx, [rsp+48h+arg_0]
0x180066c9c  add     rsp, 30h
0x180066ca0  pop     rdi
0x180066ca1  pop     rsi
0x180066ca2  pop     rbp
0x180066ca3  retn
```
