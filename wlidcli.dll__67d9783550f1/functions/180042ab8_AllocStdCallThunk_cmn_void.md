# __AllocStdCallThunk_cmn(void)

- ea: `0x180042ab8`
- end: `0x180042b72`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `PSLIST_ENTRY(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180042c18`

## callees

- `0x180042ab8`
- `0x180042b9c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180042b39`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180042b39`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180042b05`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180042b05`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180042ade`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180042b20`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180042ade`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180042b20`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180042b55`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180042b55`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180042ab8  mov     [rsp+arg_0], rbx
0x180042abd  push    rdi
0x180042abe  sub     rsp, 20h
0x180042ac2  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x180042ac9  test    rcx, rcx
0x180042acc  jnz     short loc_180042ADE
0x180042ace  call    __InitializeThunkPool
0x180042ad3  test    eax, eax
0x180042ad5  jz      short loc_180042B13
0x180042ad7  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180042ade  call    cs:__imp_InterlockedPopEntrySList
0x180042ae4  xor     ecx, ecx; lpAddress
0x180042ae6  test    rax, rax
0x180042ae9  jz      short loc_180042AF7
0x180042aeb  xorps   xmm0, xmm0
0x180042aee  movups  xmmword ptr [rax], xmm0
0x180042af1  mov     [rax+0Eh], rcx
0x180042af5  jmp     short loc_180042B67
0x180042af7  mov     edx, 1000h; dwSize
0x180042afc  mov     r9d, 40h ; '@'; flProtect
0x180042b02  mov     r8d, edx; flAllocationType
0x180042b05  call    cs:__imp_VirtualAlloc
0x180042b0b  mov     rbx, rax
0x180042b0e  test    rax, rax
0x180042b11  jnz     short loc_180042B17
0x180042b13  xor     eax, eax
0x180042b15  jmp     short loc_180042B67
0x180042b17  mov     eax, [rax]
0x180042b19  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180042b20  call    cs:__imp_InterlockedPopEntrySList
0x180042b26  mov     rdi, rax
0x180042b29  test    rax, rax
0x180042b2c  jz      short loc_180042B44
0x180042b2e  xor     edx, edx; dwSize
0x180042b30  mov     r8d, 8000h; dwFreeType
0x180042b36  mov     rcx, rbx; lpAddress
0x180042b39  call    cs:__imp_VirtualFree
0x180042b3f  mov     rax, rdi
0x180042b42  jmp     short loc_180042B67
0x180042b44  lea     rdi, [rbx+0FE0h]
0x180042b4b  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180042b52  mov     rdx, rbx; ListEntry
0x180042b55  call    cs:__imp_InterlockedPushEntrySList
0x180042b5b  add     rbx, 20h ; ' '
0x180042b5f  cmp     rbx, rdi
0x180042b62  jb      short loc_180042B4B
0x180042b64  mov     rax, rbx
0x180042b67  mov     rbx, [rsp+28h+arg_0]
0x180042b6c  add     rsp, 20h
0x180042b70  pop     rdi
0x180042b71  retn
```
