# VhdmpiCleanupSectorBitmapTracking(_VHD1_BACKING_STORE *)

- ea: `0x140025990`
- end: `0x140025a4b`
- name: `?VhdmpiCleanupSectorBitmapTracking@@YAXPEAU_VHD1_BACKING_STORE@@@Z`
- size: `187`
- prototype: `void __fastcall(struct _VHD1_BACKING_STORE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003c7b8`
- `0x1400e4ad0`

## callees

- `0x140025990`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400259b2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400259b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400259da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400259ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025a23`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400259da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400259ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025a23`

## pseudocode

```c
void __fastcall VhdmpiCleanupSectorBitmapTracking(struct _VHD1_BACKING_STORE *a1)
{
  __int64 v2; // rsi
  __int64 v3; // rbx
  void *v4; // rcx

  if ( *((_BYTE *)a1 + 4544) )
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)a1 + 4416));
    *((_BYTE *)a1 + 4544) = 0;
  }
  v2 = *((_QWORD *)a1 + 549);
  if ( v2 )
  {
    do
    {
      v3 = *(_QWORD *)(v2 + 32);
      ExFreePoolWithTag(*(PVOID *)v2, 0);
      ExFreePoolWithTag(*(PVOID *)(v2 + 8), 0);
      v2 = v3;
    }
    while ( v3 );
  }
  v4 = (void *)*((_QWORD *)a1 + 569);
  *((_QWORD *)a1 + 549) = 0;
  *((_DWORD *)a1 + 1100) = 0;
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    *((_QWORD *)a1 + 569) = 0;
  }
}

```

## disassembly

```asm
0x140025990  mov     [rsp+arg_0], rbx
0x140025995  mov     [rsp+arg_8], rsi
0x14002599a  push    rdi
0x14002599b  sub     rsp, 20h
0x14002599f  cmp     byte ptr [rcx+11C0h], 0
0x1400259a6  mov     rdi, rcx
0x1400259a9  jz      short loc_1400259C5
0x1400259ab  add     rcx, 1140h; Lookaside
0x1400259b2  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400259b9  nop     dword ptr [rax+rax+00h]
0x1400259be  mov     byte ptr [rdi+11C0h], 0
0x1400259c5  mov     rsi, [rdi+1128h]
0x1400259cc  test    rsi, rsi
0x1400259cf  jz      short loc_140025A00
0x1400259d1  mov     rcx, [rsi]; P
0x1400259d4  xor     edx, edx; Tag
0x1400259d6  mov     rbx, [rsi+20h]
0x1400259da  call    cs:__imp_ExFreePoolWithTag
0x1400259e1  nop     dword ptr [rax+rax+00h]
0x1400259e6  mov     rcx, [rsi+8]; P
0x1400259ea  xor     edx, edx; Tag
0x1400259ec  call    cs:__imp_ExFreePoolWithTag
0x1400259f3  nop     dword ptr [rax+rax+00h]
0x1400259f8  mov     rsi, rbx
0x1400259fb  test    rbx, rbx
0x1400259fe  jnz     short loc_1400259D1
0x140025a00  mov     rcx, [rdi+11C8h]; P
0x140025a07  mov     qword ptr [rdi+1128h], 0
0x140025a12  mov     dword ptr [rdi+1130h], 0
0x140025a1c  test    rcx, rcx
0x140025a1f  jz      short loc_140025A3A
0x140025a21  xor     edx, edx; Tag
0x140025a23  call    cs:__imp_ExFreePoolWithTag
0x140025a2a  nop     dword ptr [rax+rax+00h]
0x140025a2f  mov     qword ptr [rdi+11C8h], 0
0x140025a3a  mov     rbx, [rsp+28h+arg_0]
0x140025a3f  mov     rsi, [rsp+28h+arg_8]
0x140025a44  add     rsp, 20h
0x140025a48  pop     rdi
0x140025a49  retn
```
