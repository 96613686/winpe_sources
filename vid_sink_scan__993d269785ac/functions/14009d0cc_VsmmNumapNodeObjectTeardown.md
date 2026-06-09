# VsmmNumapNodeObjectTeardown

- ea: `0x14009d0cc`
- end: `0x14009d14c`
- name: `VsmmNumapNodeObjectTeardown`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14009c528`
- `0x14009cf64`

## callees

- `0x14009a07c`
- `0x14009c728`
- `0x14009d0cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14009d0ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d0ee`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14009d11f`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14009d11f`

## pseudocode

```c
__int64 __fastcall VsmmNumapNodeObjectTeardown(__int64 a1)
{
  int v2; // edi
  void *v3; // rcx

  v2 = 0;
  v3 = *(void **)(a1 + 16);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0x6D4D6456u);
    *(_QWORD *)(a1 + 16) = 0;
    *(_WORD *)(a1 + 24) = 0;
  }
  VsmmNumapBackingTeardown(a1);
  do
    ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 224 + 96LL * v2++));
  while ( v2 != 2 );
  return VidStatisticsDataTeardown((PFAST_MUTEX)(a1 + 72));
}

```

## disassembly

```asm
0x14009d0cc  mov     [rsp+arg_0], rbx
0x14009d0d1  mov     [rsp+arg_8], rsi
0x14009d0d6  push    rdi
0x14009d0d7  sub     rsp, 20h
0x14009d0db  mov     rbx, rcx
0x14009d0de  xor     edi, edi
0x14009d0e0  mov     rcx, [rcx+10h]; P
0x14009d0e4  test    rcx, rcx
0x14009d0e7  jz      short loc_14009D102
0x14009d0e9  mov     edx, 6D4D6456h; Tag
0x14009d0ee  call    cs:__imp_ExFreePoolWithTag
0x14009d0f5  nop     dword ptr [rax+rax+00h]
0x14009d0fa  mov     [rbx+10h], rdi
0x14009d0fe  mov     [rbx+18h], di
0x14009d102  mov     rcx, rbx
0x14009d105  call    VsmmNumapBackingTeardown
0x14009d10a  lea     rsi, [rbx+0E0h]
0x14009d111  movsxd  rax, edi
0x14009d114  lea     rcx, [rax+rax*2]
0x14009d118  shl     rcx, 5
0x14009d11c  add     rcx, rsi; Lookaside
0x14009d11f  call    cs:__imp_ExDeleteLookasideListEx
0x14009d126  nop     dword ptr [rax+rax+00h]
0x14009d12b  inc     edi
0x14009d12d  cmp     edi, 2
0x14009d130  jnz     short loc_14009D111
0x14009d132  lea     rcx, [rbx+48h]; FastMutex
0x14009d136  call    VidStatisticsDataTeardown
0x14009d13b  mov     rbx, [rsp+28h+arg_0]
0x14009d140  mov     rsi, [rsp+28h+arg_8]
0x14009d145  add     rsp, 20h
0x14009d149  pop     rdi
0x14009d14a  retn
```
