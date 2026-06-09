# __AllocStdCallThunk_cmn(void)

- ea: `0x18000e8c0`
- end: `0x18000e97a`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ea20`

## callees

- `0x18000e8c0`
- `0x18000e9a4`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000e90d`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18000e90d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000e941`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x18000e941`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000e8e6`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000e928`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000e8e6`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18000e928`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000e95d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18000e95d`

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
0x18000e8c0  mov     [rsp+arg_0], rbx
0x18000e8c5  push    rdi
0x18000e8c6  sub     rsp, 20h
0x18000e8ca  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x18000e8d1  test    rcx, rcx
0x18000e8d4  jnz     short loc_18000E8E6
0x18000e8d6  call    __InitializeThunkPool
0x18000e8db  test    eax, eax
0x18000e8dd  jz      short loc_18000E91B
0x18000e8df  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18000e8e6  call    cs:__imp_InterlockedPopEntrySList
0x18000e8ec  xor     ecx, ecx; lpAddress
0x18000e8ee  test    rax, rax
0x18000e8f1  jz      short loc_18000E8FF
0x18000e8f3  xorps   xmm0, xmm0
0x18000e8f6  movups  xmmword ptr [rax], xmm0
0x18000e8f9  mov     [rax+0Eh], rcx
0x18000e8fd  jmp     short loc_18000E96F
0x18000e8ff  mov     edx, 1000h; dwSize
0x18000e904  mov     r9d, 40h ; '@'; flProtect
0x18000e90a  mov     r8d, edx; flAllocationType
0x18000e90d  call    cs:__imp_VirtualAlloc
0x18000e913  mov     rbx, rax
0x18000e916  test    rax, rax
0x18000e919  jnz     short loc_18000E91F
0x18000e91b  xor     eax, eax
0x18000e91d  jmp     short loc_18000E96F
0x18000e91f  mov     eax, [rax]
0x18000e921  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18000e928  call    cs:__imp_InterlockedPopEntrySList
0x18000e92e  mov     rdi, rax
0x18000e931  test    rax, rax
0x18000e934  jz      short loc_18000E94C
0x18000e936  xor     edx, edx; dwSize
0x18000e938  mov     r8d, 8000h; dwFreeType
0x18000e93e  mov     rcx, rbx; lpAddress
0x18000e941  call    cs:__imp_VirtualFree
0x18000e947  mov     rax, rdi
0x18000e94a  jmp     short loc_18000E96F
0x18000e94c  lea     rdi, [rbx+0FE0h]
0x18000e953  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18000e95a  mov     rdx, rbx; ListEntry
0x18000e95d  call    cs:__imp_InterlockedPushEntrySList
0x18000e963  add     rbx, 20h ; ' '
0x18000e967  cmp     rbx, rdi
0x18000e96a  jb      short loc_18000E953
0x18000e96c  mov     rax, rbx
0x18000e96f  mov     rbx, [rsp+28h+arg_0]
0x18000e974  add     rsp, 20h
0x18000e978  pop     rdi
0x18000e979  retn
```
