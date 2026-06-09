# VhdmpiCleanupSectorBitmapTracking(_VHD1_BACKING_STORE *)

- ea: `0x140025db0`
- end: `0x140025e6b`
- name: `?VhdmpiCleanupSectorBitmapTracking@@YAXPEAU_VHD1_BACKING_STORE@@@Z`
- size: `187`
- prototype: `void __fastcall(struct _VHD1_BACKING_STORE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003cba8`
- `0x1400e4a60`

## callees

- `0x140025db0`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140025dd2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140025dd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025dfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025e0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025e43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025dfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025e0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025e43`

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
0x140025db0  mov     [rsp+arg_0], rbx
0x140025db5  mov     [rsp+arg_8], rsi
0x140025dba  push    rdi
0x140025dbb  sub     rsp, 20h
0x140025dbf  cmp     byte ptr [rcx+11C0h], 0
0x140025dc6  mov     rdi, rcx
0x140025dc9  jz      short loc_140025DE5
0x140025dcb  add     rcx, 1140h; Lookaside
0x140025dd2  call    cs:__imp_ExDeleteNPagedLookasideList
0x140025dd9  nop     dword ptr [rax+rax+00h]
0x140025dde  mov     byte ptr [rdi+11C0h], 0
0x140025de5  mov     rsi, [rdi+1128h]
0x140025dec  test    rsi, rsi
0x140025def  jz      short loc_140025E20
0x140025df1  mov     rcx, [rsi]; P
0x140025df4  xor     edx, edx; Tag
0x140025df6  mov     rbx, [rsi+20h]
0x140025dfa  call    cs:__imp_ExFreePoolWithTag
0x140025e01  nop     dword ptr [rax+rax+00h]
0x140025e06  mov     rcx, [rsi+8]; P
0x140025e0a  xor     edx, edx; Tag
0x140025e0c  call    cs:__imp_ExFreePoolWithTag
0x140025e13  nop     dword ptr [rax+rax+00h]
0x140025e18  mov     rsi, rbx
0x140025e1b  test    rbx, rbx
0x140025e1e  jnz     short loc_140025DF1
0x140025e20  mov     rcx, [rdi+11C8h]; P
0x140025e27  mov     qword ptr [rdi+1128h], 0
0x140025e32  mov     dword ptr [rdi+1130h], 0
0x140025e3c  test    rcx, rcx
0x140025e3f  jz      short loc_140025E5A
0x140025e41  xor     edx, edx; Tag
0x140025e43  call    cs:__imp_ExFreePoolWithTag
0x140025e4a  nop     dword ptr [rax+rax+00h]
0x140025e4f  mov     qword ptr [rdi+11C8h], 0
0x140025e5a  mov     rbx, [rsp+28h+arg_0]
0x140025e5f  mov     rsi, [rsp+28h+arg_8]
0x140025e64  add     rsp, 20h
0x140025e68  pop     rdi
0x140025e69  retn
```
