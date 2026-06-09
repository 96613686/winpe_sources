# MpFgCleanup

- ea: `0x140085588`
- end: `0x1400856d9`
- name: `MpFgCleanup`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14007bef0`
- `0x14008f314`

## callees

- `0x140003460`
- `0x140066180`
- `0x140085588`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400855b9`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140085626`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400855b9`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140085626`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400855de`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140085658`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400855de`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x140085658`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400856a4`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400856a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400855cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400855f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008563a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400856bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400855cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400855f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008563a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400856bc`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14008568d`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14008568d`

## pseudocode

```c
void MpFgCleanup()
{
  struct _PAGED_LOOKASIDE_LIST *v0; // rcx
  struct _RTL_AVL_TABLE *v1; // rdi
  void *v2; // rbx
  _QWORD *v3; // rax
  struct _RTL_AVL_TABLE *Region; // rdi
  void *v5; // rbx
  __int64 v6; // rsi
  _QWORD *v7; // rax

  v0 = (struct _PAGED_LOOKASIDE_LIST *)DeferredContext;
  if ( DeferredContext )
  {
    v1 = (struct _RTL_AVL_TABLE *)*((_QWORD *)DeferredContext + 1);
    if ( v1 )
    {
      while ( 1 )
      {
        v3 = RtlEnumerateGenericTableAvl(v1, 1u);
        if ( !v3 )
          break;
        v2 = (void *)v3[2];
        RtlDeleteElementGenericTableAvl(v1, v3);
        ExFreePoolWithTag(v2, 0x6746504Du);
      }
      ExFreePoolWithTag(v1, 0x7046504Du);
      v0 = (struct _PAGED_LOOKASIDE_LIST *)DeferredContext;
    }
    Region = (struct _RTL_AVL_TABLE *)v0[2].L.ListHead.Region;
    if ( Region )
    {
      while ( 1 )
      {
        v7 = RtlEnumerateGenericTableAvl(Region, 1u);
        if ( !v7 )
          break;
        v5 = (void *)v7[6];
        v6 = v7[3];
        RtlDeleteElementGenericTableAvl(Region, v7);
        ExFreePoolWithTag(v5, 0x6746504Du);
        if ( v6 )
          MpFreeString(v6);
      }
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)DeferredContext + 3, Region);
      v0 = (struct _PAGED_LOOKASIDE_LIST *)DeferredContext;
    }
    ExDeletePagedLookasideList(v0 + 3);
    ExDeleteResourceLite((PERESOURCE)((char *)DeferredContext + 16));
    ExFreePoolWithTag(DeferredContext, 0x6746504Du);
  }
}

```

## disassembly

```asm
0x140085588  mov     [rsp+arg_0], rbx
0x14008558d  mov     [rsp+arg_8], rsi
0x140085592  push    rdi
0x140085593  sub     rsp, 20h
0x140085597  mov     rcx, cs:DeferredContext
0x14008559e  test    rcx, rcx
0x1400855a1  jz      loc_1400856C8
0x1400855a7  mov     rdi, [rcx+8]
0x1400855ab  test    rdi, rdi
0x1400855ae  jz      short loc_14008560A
0x1400855b0  jmp     short loc_1400855D9
0x1400855b2  mov     rbx, [rax+10h]
0x1400855b6  mov     rdx, rax; Buffer
0x1400855b9  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400855c0  nop     dword ptr [rax+rax+00h]
0x1400855c5  mov     edx, 6746504Dh; Tag
0x1400855ca  mov     rcx, rbx; P
0x1400855cd  call    cs:__imp_ExFreePoolWithTag
0x1400855d4  nop     dword ptr [rax+rax+00h]
0x1400855d9  mov     dl, 1; Restart
0x1400855db  mov     rcx, rdi; Table
0x1400855de  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400855e5  nop     dword ptr [rax+rax+00h]
0x1400855ea  mov     rcx, rdi; P
0x1400855ed  test    rax, rax
0x1400855f0  jnz     short loc_1400855B2
0x1400855f2  mov     edx, 7046504Dh; Tag
0x1400855f7  call    cs:__imp_ExFreePoolWithTag
0x1400855fe  nop     dword ptr [rax+rax+00h]
0x140085603  mov     rcx, cs:DeferredContext
0x14008560a  mov     rdi, [rcx+108h]
0x140085611  test    rdi, rdi
0x140085614  jz      short loc_140085686
0x140085616  jmp     short loc_140085653
0x140085618  mov     rbx, [rax+30h]
0x14008561c  mov     rdx, rax; Buffer
0x14008561f  mov     rsi, [rax+18h]
0x140085623  mov     rcx, rdi; Table
0x140085626  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14008562d  nop     dword ptr [rax+rax+00h]
0x140085632  mov     edx, 6746504Dh; Tag
0x140085637  mov     rcx, rbx; P
0x14008563a  call    cs:__imp_ExFreePoolWithTag
0x140085641  nop     dword ptr [rax+rax+00h]
0x140085646  test    rsi, rsi
0x140085649  jz      short loc_140085653
0x14008564b  mov     rcx, rsi
0x14008564e  call    MpFreeString
0x140085653  mov     dl, 1; Restart
0x140085655  mov     rcx, rdi; Table
0x140085658  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14008565f  nop     dword ptr [rax+rax+00h]
0x140085664  test    rax, rax
0x140085667  jnz     short loc_140085618
0x140085669  mov     rcx, cs:DeferredContext
0x140085670  mov     rdx, rdi; Entry
0x140085673  add     rcx, 180h; Lookaside
0x14008567a  call    ExFreeToNPagedLookasideList
0x14008567f  mov     rcx, cs:DeferredContext
0x140085686  add     rcx, 180h; Lookaside
0x14008568d  call    cs:__imp_ExDeletePagedLookasideList
0x140085694  nop     dword ptr [rax+rax+00h]
0x140085699  mov     rcx, cs:DeferredContext
0x1400856a0  add     rcx, 10h; Resource
0x1400856a4  call    cs:__imp_ExDeleteResourceLite
0x1400856ab  nop     dword ptr [rax+rax+00h]
0x1400856b0  mov     rcx, cs:DeferredContext; P
0x1400856b7  mov     edx, 6746504Dh; Tag
0x1400856bc  call    cs:__imp_ExFreePoolWithTag
0x1400856c3  nop     dword ptr [rax+rax+00h]
0x1400856c8  mov     rbx, [rsp+28h+arg_0]
0x1400856cd  mov     rsi, [rsp+28h+arg_8]
0x1400856d2  add     rsp, 20h
0x1400856d6  pop     rdi
0x1400856d7  retn
```
