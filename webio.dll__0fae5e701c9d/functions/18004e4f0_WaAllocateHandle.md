# WaAllocateHandle

- ea: `0x18004e4f0`
- end: `0x18004e59a`
- name: `WaAllocateHandle`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800829c0`

## callees

- `0x18004e4f0`
- `0x18004e5a0`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004e526`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18004e526`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004e53e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004e53e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e56a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e56a`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x18004e505`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x18004e505`

## pseudocode

```c
__int64 __fastcall WaAllocateHandle(struct _SLIST_ENTRY *a1, int a2, _QWORD *a3)
{
  unsigned __int8 CurrentProcessorNumber; // al
  unsigned int v7; // ebx
  union _SLIST_HEADER *v8; // r14
  PSLIST_ENTRY v9; // rax
  PSLIST_ENTRY v10; // rdi
  int v11; // eax
  __int64 result; // rax

  CurrentProcessorNumber = RtlGetCurrentProcessorNumber();
  v7 = CurrentProcessorNumber;
  v8 = (union _SLIST_HEADER *)((char *)WaHandleTable + 64 * (unsigned __int64)CurrentProcessorNumber);
  do
  {
    v9 = InterlockedPopEntrySList(v8 + 2);
    v10 = v9;
    if ( v9 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)&v9[1]);
      v11 = *((_DWORD *)&v10[1].Next + 2) + 1;
      v10->Next = a1;
      *((_DWORD *)&v10[1].Next + 2) = (a2 << 28) | v11 & 0xFFFFFFF;
      *a3 = *((_QWORD *)&v10[1].Next + 1);
      ReleaseSRWLockExclusive((PSRWLOCK)&v10[1]);
      return 0;
    }
    result = WapExpandHandleTable(v7);
  }
  while ( !(_DWORD)result );
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x18004e4f0  push    rbx
0x18004e4f2  push    rbp
0x18004e4f3  push    rsi
0x18004e4f4  push    rdi
0x18004e4f5  push    r14
0x18004e4f7  push    r15
0x18004e4f9  sub     rsp, 28h
0x18004e4fd  mov     rsi, r8
0x18004e500  mov     ebp, edx
0x18004e502  mov     r15, rcx
0x18004e505  call    cs:__imp_RtlGetCurrentProcessorNumber
0x18004e50c  nop     dword ptr [rax+rax+00h]
0x18004e511  movzx   ebx, al
0x18004e514  mov     r14d, ebx
0x18004e517  shl     r14, 6
0x18004e51b  add     r14, cs:WaHandleTable
0x18004e522  lea     rcx, [r14+20h]; ListHead
0x18004e526  call    cs:__imp_InterlockedPopEntrySList
0x18004e52d  nop     dword ptr [rax+rax+00h]
0x18004e532  mov     rdi, rax
0x18004e535  test    rax, rax
0x18004e538  jz      short loc_18004E586
0x18004e53a  lea     rcx, [rax+10h]; SRWLock
0x18004e53e  call    cs:__imp_AcquireSRWLockExclusive
0x18004e545  nop     dword ptr [rax+rax+00h]
0x18004e54a  mov     eax, [rdi+18h]
0x18004e54d  lea     rcx, [rdi+10h]; SRWLock
0x18004e551  inc     eax
0x18004e553  mov     [rdi], r15
0x18004e556  and     eax, 0FFFFFFFh
0x18004e55b  shl     ebp, 1Ch
0x18004e55e  or      eax, ebp
0x18004e560  mov     [rdi+18h], eax
0x18004e563  mov     rax, [rdi+18h]
0x18004e567  mov     [rsi], rax
0x18004e56a  call    cs:__imp_ReleaseSRWLockExclusive
0x18004e571  nop     dword ptr [rax+rax+00h]
0x18004e576  xor     eax, eax
0x18004e578  add     rsp, 28h
0x18004e57c  pop     r15
0x18004e57e  pop     r14
0x18004e580  pop     rdi
0x18004e581  pop     rsi
0x18004e582  pop     rbp
0x18004e583  pop     rbx
0x18004e584  retn
0x18004e586  mov     ecx, ebx
0x18004e588  call    WapExpandHandleTable
0x18004e58d  test    eax, eax
0x18004e58f  jz      short loc_18004E522
0x18004e591  mov     qword ptr [rsi], 0
0x18004e598  jmp     short loc_18004E578
```
