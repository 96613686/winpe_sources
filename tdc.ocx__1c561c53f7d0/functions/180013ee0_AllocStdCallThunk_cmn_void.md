# __AllocStdCallThunk_cmn(void)

- ea: `0x180013ee0`
- end: `0x180013f9a`
- name: `?__AllocStdCallThunk_cmn@@YAPEAXXZ`
- size: `186`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001401c`

## callees

- `0x180013ee0`
- `0x180013fa0`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x180013f61`
- `KERNEL32!VirtualFree` at `0x180013f61`
- `KERNEL32!VirtualAlloc` at `0x180013f2d`
- `KERNEL32!VirtualAlloc` at `0x180013f2d`
- `KERNEL32!InterlockedPushEntrySList` at `0x180013f7d`
- `KERNEL32!InterlockedPushEntrySList` at `0x180013f7d`
- `KERNEL32!InterlockedPopEntrySList` at `0x180013f06`
- `KERNEL32!InterlockedPopEntrySList` at `0x180013f48`
- `KERNEL32!InterlockedPopEntrySList` at `0x180013f06`
- `KERNEL32!InterlockedPopEntrySList` at `0x180013f48`

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
0x180013ee0  mov     [rsp+arg_0], rbx
0x180013ee5  push    rdi
0x180013ee6  sub     rsp, 20h
0x180013eea  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; _SLIST_HEADER * __AtlThunkPool
0x180013ef1  test    rcx, rcx
0x180013ef4  jnz     short loc_180013F06
0x180013ef6  call    __InitializeThunkPool
0x180013efb  test    eax, eax
0x180013efd  jz      short loc_180013F3B
0x180013eff  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180013f06  call    cs:__imp_InterlockedPopEntrySList
0x180013f0c  xor     ecx, ecx; lpAddress
0x180013f0e  test    rax, rax
0x180013f11  jz      short loc_180013F1F
0x180013f13  xorps   xmm0, xmm0
0x180013f16  movups  xmmword ptr [rax], xmm0
0x180013f19  mov     [rax+0Eh], rcx
0x180013f1d  jmp     short loc_180013F8F
0x180013f1f  mov     edx, 1000h; dwSize
0x180013f24  mov     r9d, 40h ; '@'; flProtect
0x180013f2a  mov     r8d, edx; flAllocationType
0x180013f2d  call    cs:__imp_VirtualAlloc
0x180013f33  mov     rbx, rax
0x180013f36  test    rax, rax
0x180013f39  jnz     short loc_180013F3F
0x180013f3b  xor     eax, eax
0x180013f3d  jmp     short loc_180013F8F
0x180013f3f  mov     eax, [rax]
0x180013f41  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180013f48  call    cs:__imp_InterlockedPopEntrySList
0x180013f4e  mov     rdi, rax
0x180013f51  test    rax, rax
0x180013f54  jz      short loc_180013F6C
0x180013f56  xor     edx, edx; dwSize
0x180013f58  mov     r8d, 8000h; dwFreeType
0x180013f5e  mov     rcx, rbx; lpAddress
0x180013f61  call    cs:__imp_VirtualFree
0x180013f67  mov     rax, rdi
0x180013f6a  jmp     short loc_180013F8F
0x180013f6c  lea     rdi, [rbx+0FE0h]
0x180013f73  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x180013f7a  mov     rdx, rbx; ListEntry
0x180013f7d  call    cs:__imp_InterlockedPushEntrySList
0x180013f83  add     rbx, 20h ; ' '
0x180013f87  cmp     rbx, rdi
0x180013f8a  jb      short loc_180013F73
0x180013f8c  mov     rax, rbx
0x180013f8f  mov     rbx, [rsp+28h+arg_0]
0x180013f94  add     rsp, 20h
0x180013f98  pop     rdi
0x180013f99  retn
```
