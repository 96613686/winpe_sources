# InpFreePacketProfilerLocked

- ea: `0x140008714`
- end: `0x140008794`
- name: `InpFreePacketProfilerLocked`
- size: `128`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140007984`

## callees

- `0x140008714`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140008739`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140008739`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008770`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008770`

## pseudocode

```c
void __fastcall InpFreePacketProfilerLocked(_QWORD *P)
{
  unsigned int v1; // edi
  char *v3; // rsi
  _QWORD **v4; // rcx
  PVOID *v5; // rdx

  v1 = 0;
  if ( *(_DWORD *)P )
  {
    v3 = (char *)(P + 8);
    do
      ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&v3[128 * (unsigned __int64)v1++]);
    while ( v1 < *(_DWORD *)P );
  }
  v4 = (_QWORD **)P[1];
  if ( v4[1] != P + 1 || (v5 = (PVOID *)P[2], *v5 != P + 1) )
    __fastfail(3u);
  *v5 = v4;
  v4[1] = v5;
  ExFreePoolWithTag(P, 0x6E696B56u);
}

```

## disassembly

```asm
0x140008714  mov     [rsp+arg_0], rbx
0x140008719  mov     [rsp+arg_8], rsi
0x14000871e  push    rdi
0x14000871f  sub     rsp, 20h
0x140008723  xor     edi, edi
0x140008725  mov     rbx, rcx
0x140008728  cmp     [rcx], edi
0x14000872a  jbe     short loc_14000874B
0x14000872c  lea     rsi, [rcx+40h]
0x140008730  mov     ecx, edi
0x140008732  shl     rcx, 7
0x140008736  add     rcx, rsi; Lookaside
0x140008739  call    cs:__imp_ExDeleteNPagedLookasideList
0x140008740  nop     dword ptr [rax+rax+00h]
0x140008745  inc     edi
0x140008747  cmp     edi, [rbx]
0x140008749  jb      short loc_140008730
0x14000874b  lea     rax, [rbx+8]
0x14000874f  mov     rcx, [rax]
0x140008752  cmp     [rcx+8], rax
0x140008756  jnz     short loc_14000878D
0x140008758  mov     rdx, [rax+8]
0x14000875c  cmp     [rdx], rax
0x14000875f  jnz     short loc_14000878D
0x140008761  mov     [rdx], rcx
0x140008764  mov     [rcx+8], rdx
0x140008768  mov     edx, 6E696B56h; Tag
0x14000876d  mov     rcx, rbx; P
0x140008770  call    cs:__imp_ExFreePoolWithTag
0x140008777  nop     dword ptr [rax+rax+00h]
0x14000877c  mov     rbx, [rsp+28h+arg_0]
0x140008781  mov     rsi, [rsp+28h+arg_8]
0x140008786  add     rsp, 20h
0x14000878a  pop     rdi
0x14000878b  retn
0x14000878d  mov     ecx, 3
0x140008792  int     29h; Win8: RtlFailFast(ecx)
```
