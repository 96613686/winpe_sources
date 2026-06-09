# WcFreeEnumContexts

- ea: `0x140002048`
- end: `0x1400020bb`
- name: `WcFreeEnumContexts`
- size: `115`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140014c90`
- `0x1400154ac`
- `0x1400300b0`

## callees

- `0x140002048`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000209a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000209a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000206b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000206b`

## pseudocode

```c
void __fastcall WcFreeEnumContexts(_QWORD **a1)
{
  _QWORD *v2; // rbx
  void *v3; // rcx
  __int64 v4; // rax
  _QWORD *v5; // rcx

  while ( 1 )
  {
    v2 = *a1;
    if ( *a1 == a1 )
      break;
    v3 = (void *)v2[9];
    if ( v3 )
      ExFreePoolWithTag(v3, 0x6E654357u);
    v4 = *v2;
    if ( *(_QWORD **)(*v2 + 8LL) != v2 || (v5 = (_QWORD *)v2[1], (_QWORD *)*v5 != v2) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    ExFreeToPagedLookasideList(&Lookaside, v2);
  }
}

```

## disassembly

```asm
0x140002048  mov     [rsp+arg_0], rbx
0x14000204d  push    rdi
0x14000204e  sub     rsp, 20h
0x140002052  mov     rdi, rcx
0x140002055  mov     rbx, [rdi]
0x140002058  cmp     rbx, rdi
0x14000205b  jz      short loc_1400020A8
0x14000205d  mov     rcx, [rbx+48h]; P
0x140002061  test    rcx, rcx
0x140002064  jz      short loc_140002077
0x140002066  mov     edx, 6E654357h; Tag
0x14000206b  call    cs:__imp_ExFreePoolWithTag
0x140002072  nop     dword ptr [rax+rax+00h]
0x140002077  mov     rax, [rbx]
0x14000207a  cmp     [rax+8], rbx
0x14000207e  jnz     short loc_1400020B4
0x140002080  mov     rcx, [rbx+8]
0x140002084  cmp     [rcx], rbx
0x140002087  jnz     short loc_1400020B4
0x140002089  mov     [rcx], rax
0x14000208c  mov     rdx, rbx; Entry
0x14000208f  mov     [rax+8], rcx
0x140002093  lea     rcx, Lookaside; Lookaside
0x14000209a  call    cs:__imp_ExFreeToPagedLookasideList
0x1400020a1  nop     dword ptr [rax+rax+00h]
0x1400020a6  jmp     short loc_140002055
0x1400020a8  mov     rbx, [rsp+28h+arg_0]
0x1400020ad  add     rsp, 20h
0x1400020b1  pop     rdi
0x1400020b2  retn
0x1400020b4  mov     ecx, 3
0x1400020b9  int     29h; Win8: RtlFailFast(ecx)
```
