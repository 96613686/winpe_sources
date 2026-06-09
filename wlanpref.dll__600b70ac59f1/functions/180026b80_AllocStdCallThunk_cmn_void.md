# __AllocStdCallThunk_cmn(void)

- ea: `0x180026b80`
- end: `0x180026c3a`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026ce0`

## callees

- `0x180026b80`
- `0x180026c64`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180026c01`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180026c01`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180026bcd`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180026bcd`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180026ba6`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180026be8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180026ba6`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180026be8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180026c1d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180026c1d`

## pseudocode

```c
PSLIST_ENTRY __AllocStdCallThunk_cmn(void)
{
  union _SLIST_HEADER *v0; // rcx
  PSLIST_ENTRY result; // rax
  struct _SLIST_ENTRY *v2; // rbx
  PSLIST_ENTRY v3; // rdi
  struct _SLIST_ENTRY *v4; // rdi

  v0 = __AtlThunkPool;
  if ( !__AtlThunkPool )
  {
    if ( !(unsigned int)_InitializeThunkPool() )
      return 0;
    v0 = __AtlThunkPool;
  }
  result = InterlockedPopEntrySList(v0);
  if ( result )
  {
    *result = 0;
    *(struct _SLIST_ENTRY **)((char *)&result->Next + 14) = 0;
    return result;
  }
  v2 = (struct _SLIST_ENTRY *)VirtualAlloc(0, 0x1000u, 0x1000u, 0x40u);
  if ( !v2 )
    return 0;
  v3 = InterlockedPopEntrySList(__AtlThunkPool);
  if ( v3 )
  {
    VirtualFree(v2, 0, 0x8000u);
    return v3;
  }
  else
  {
    v4 = v2 + 254;
    do
    {
      InterlockedPushEntrySList(__AtlThunkPool, v2);
      v2 += 2;
    }
    while ( v2 < v4 );
    return v2;
  }
}

```

## disassembly

```asm
0x180026b80  mov     [rsp+arg_0], rbx
0x180026b85  push    rdi
0x180026b86  sub     rsp, 20h
0x180026b8a  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x180026b91  test    rcx, rcx
0x180026b94  jnz     short loc_180026BA6
0x180026b96  call    __InitializeThunkPool
0x180026b9b  test    eax, eax
0x180026b9d  jz      short loc_180026BDB
0x180026b9f  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180026ba6  call    cs:__imp_InterlockedPopEntrySList
0x180026bac  xor     ecx, ecx; lpAddress
0x180026bae  test    rax, rax
0x180026bb1  jz      short loc_180026BBF
0x180026bb3  xorps   xmm0, xmm0
0x180026bb6  movups  xmmword ptr [rax], xmm0
0x180026bb9  mov     [rax+0Eh], rcx
0x180026bbd  jmp     short loc_180026C2F
0x180026bbf  mov     edx, 1000h; dwSize
0x180026bc4  mov     r9d, 40h ; '@'; flProtect
0x180026bca  mov     r8d, edx; flAllocationType
0x180026bcd  call    cs:__imp_VirtualAlloc
0x180026bd3  mov     rbx, rax
0x180026bd6  test    rax, rax
0x180026bd9  jnz     short loc_180026BDF
0x180026bdb  xor     eax, eax
0x180026bdd  jmp     short loc_180026C2F
0x180026bdf  mov     eax, [rax]
0x180026be1  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180026be8  call    cs:__imp_InterlockedPopEntrySList
0x180026bee  mov     rdi, rax
0x180026bf1  test    rax, rax
0x180026bf4  jz      short loc_180026C0C
0x180026bf6  xor     edx, edx; dwSize
0x180026bf8  mov     r8d, 8000h; dwFreeType
0x180026bfe  mov     rcx, rbx; lpAddress
0x180026c01  call    cs:__imp_VirtualFree
0x180026c07  mov     rax, rdi
0x180026c0a  jmp     short loc_180026C2F
0x180026c0c  lea     rdi, [rbx+0FE0h]
0x180026c13  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180026c1a  mov     rdx, rbx; ListEntry
0x180026c1d  call    cs:__imp_InterlockedPushEntrySList
0x180026c23  add     rbx, 20h ; ' '
0x180026c27  cmp     rbx, rdi
0x180026c2a  jb      short loc_180026C13
0x180026c2c  mov     rax, rbx
0x180026c2f  mov     rbx, [rsp+28h+arg_0]
0x180026c34  add     rsp, 20h
0x180026c38  pop     rdi
0x180026c39  retn
```
