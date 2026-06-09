# __AllocStdCallThunk_cmn(void)

- ea: `0x14000d644`
- end: `0x14000d6fe`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d780`

## callees

- `0x14000d644`
- `0x14000d704`

## import_xrefs

- `KERNEL32!VirtualAlloc` at `0x14000d691`
- `KERNEL32!VirtualAlloc` at `0x14000d691`
- `KERNEL32!VirtualFree` at `0x14000d6c5`
- `KERNEL32!VirtualFree` at `0x14000d6c5`
- `KERNEL32!InterlockedPushEntrySList` at `0x14000d6e1`
- `KERNEL32!InterlockedPushEntrySList` at `0x14000d6e1`
- `KERNEL32!InterlockedPopEntrySList` at `0x14000d66a`
- `KERNEL32!InterlockedPopEntrySList` at `0x14000d6ac`
- `KERNEL32!InterlockedPopEntrySList` at `0x14000d66a`
- `KERNEL32!InterlockedPopEntrySList` at `0x14000d6ac`

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
0x14000d644  mov     [rsp+arg_0], rbx
0x14000d649  push    rdi
0x14000d64a  sub     rsp, 20h
0x14000d64e  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x14000d655  test    rcx, rcx
0x14000d658  jnz     short loc_14000D66A
0x14000d65a  call    __InitializeThunkPool
0x14000d65f  test    eax, eax
0x14000d661  jz      short loc_14000D69F
0x14000d663  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x14000d66a  call    cs:__imp_InterlockedPopEntrySList
0x14000d670  xor     ecx, ecx; lpAddress
0x14000d672  test    rax, rax
0x14000d675  jz      short loc_14000D683
0x14000d677  xorps   xmm0, xmm0
0x14000d67a  movups  xmmword ptr [rax], xmm0
0x14000d67d  mov     [rax+0Eh], rcx
0x14000d681  jmp     short loc_14000D6F3
0x14000d683  mov     edx, 1000h; dwSize
0x14000d688  mov     r9d, 40h ; '@'; flProtect
0x14000d68e  mov     r8d, edx; flAllocationType
0x14000d691  call    cs:__imp_VirtualAlloc
0x14000d697  mov     rbx, rax
0x14000d69a  test    rax, rax
0x14000d69d  jnz     short loc_14000D6A3
0x14000d69f  xor     eax, eax
0x14000d6a1  jmp     short loc_14000D6F3
0x14000d6a3  mov     eax, [rax]
0x14000d6a5  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x14000d6ac  call    cs:__imp_InterlockedPopEntrySList
0x14000d6b2  mov     rdi, rax
0x14000d6b5  test    rax, rax
0x14000d6b8  jz      short loc_14000D6D0
0x14000d6ba  xor     edx, edx; dwSize
0x14000d6bc  mov     r8d, 8000h; dwFreeType
0x14000d6c2  mov     rcx, rbx; lpAddress
0x14000d6c5  call    cs:__imp_VirtualFree
0x14000d6cb  mov     rax, rdi
0x14000d6ce  jmp     short loc_14000D6F3
0x14000d6d0  lea     rdi, [rbx+0FE0h]
0x14000d6d7  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x14000d6de  mov     rdx, rbx; ListEntry
0x14000d6e1  call    cs:__imp_InterlockedPushEntrySList
0x14000d6e7  add     rbx, 20h ; ' '
0x14000d6eb  cmp     rbx, rdi
0x14000d6ee  jb      short loc_14000D6D7
0x14000d6f0  mov     rax, rbx
0x14000d6f3  mov     rbx, [rsp+28h+arg_0]
0x14000d6f8  add     rsp, 20h
0x14000d6fc  pop     rdi
0x14000d6fd  retn
```
