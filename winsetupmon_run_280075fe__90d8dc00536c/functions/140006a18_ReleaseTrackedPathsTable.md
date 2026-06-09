# ReleaseTrackedPathsTable

- ea: `0x140006a18`
- end: `0x140006b67`
- name: `ReleaseTrackedPathsTable`
- size: `335`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006f78`
- `0x140007800`

## callees

- `0x140006a18`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x140006a30`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140006b3e`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140006a30`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140006b3e`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140006a57`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x140006a57`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006a7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006a99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006ab8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006ad7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006af0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006b14`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006b29`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006a7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006a99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006ab8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006ad7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006af0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006b14`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006b29`

## pseudocode

```c
PUNICODE_PREFIX_TABLE_ENTRY ReleaseTrackedPathsTable()
{
  PUNICODE_PREFIX_TABLE_ENTRY result; // rax
  struct _UNICODE_PREFIX_TABLE_ENTRY *i; // rdi
  struct _RTL_SPLAY_LINKS *RightChild; // rcx
  struct _RTL_SPLAY_LINKS *v3; // rcx
  struct _RTL_SPLAY_LINKS *LeftChild; // rcx
  struct _RTL_SPLAY_LINKS *v5; // rcx
  struct _RTL_SPLAY_LINKS *Parent; // rbx
  struct _UNICODE_PREFIX_TABLE_ENTRY *NextPrefixTree; // rcx

  result = RtlNextUnicodePrefix(&g_TrackingInfo, 1u);
  for ( i = result; result; i = result )
  {
    RtlRemoveUnicodePrefix(&g_TrackingInfo, i);
    while ( 1 )
    {
      Parent = i[1].Links.Parent;
      if ( !Parent )
        break;
      i[1].Links.Parent = Parent->Parent;
      RightChild = Parent[2].RightChild;
      if ( RightChild )
      {
        ExFreePoolWithTag(RightChild, 0x6E6D7377u);
        Parent[2].RightChild = 0;
      }
      v3 = Parent[2].Parent;
      if ( v3 )
      {
        ExFreePoolWithTag(v3, 0x6E6D7377u);
        Parent[2].Parent = 0;
      }
      LeftChild = Parent[1].LeftChild;
      if ( LeftChild )
      {
        ExFreePoolWithTag(LeftChild, 0x6E6D7377u);
        Parent[1].LeftChild = 0;
      }
      v5 = Parent->RightChild;
      if ( v5 )
      {
        ExFreePoolWithTag(v5, 0x6E6D7377u);
        Parent->RightChild = 0;
      }
      ExFreePoolWithTag(Parent, 0x6E6D7377u);
    }
    NextPrefixTree = i[1].NextPrefixTree;
    if ( NextPrefixTree )
    {
      ExFreePoolWithTag(NextPrefixTree, 0x6E6D7377u);
      i[1].NextPrefixTree = 0;
    }
    ExFreePoolWithTag(i, 0x6E6D7377u);
    result = RtlNextUnicodePrefix(&g_TrackingInfo, 0);
  }
  return result;
}

```

## disassembly

```asm
0x140006a18  mov     [rsp+arg_0], rbx
0x140006a1d  mov     [rsp+arg_8], rbp
0x140006a22  push    rdi
0x140006a23  sub     rsp, 20h
0x140006a27  mov     dl, 1; Restart
0x140006a29  lea     rcx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; PrefixTable
0x140006a30  call    cs:__imp_RtlNextUnicodePrefix
0x140006a37  nop     dword ptr [rax+rax+00h]
0x140006a3c  mov     rdi, rax
0x140006a3f  test    rax, rax
0x140006a42  jz      loc_140006B56
0x140006a48  mov     ebp, 6E6D7377h
0x140006a4d  mov     rdx, rdi; PrefixTableEntry
0x140006a50  lea     rcx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; PrefixTable
0x140006a57  call    cs:__imp_RtlRemoveUnicodePrefix
0x140006a5e  nop     dword ptr [rax+rax+00h]
0x140006a63  jmp     loc_140006AFC
0x140006a68  mov     rax, [rbx]
0x140006a6b  mov     [rdi+50h], rax
0x140006a6f  mov     rcx, [rbx+40h]; P
0x140006a73  test    rcx, rcx
0x140006a76  jz      short loc_140006A8E
0x140006a78  mov     edx, ebp; Tag
0x140006a7a  call    cs:__imp_ExFreePoolWithTag
0x140006a81  nop     dword ptr [rax+rax+00h]
0x140006a86  mov     qword ptr [rbx+40h], 0
0x140006a8e  mov     rcx, [rbx+30h]; P
0x140006a92  test    rcx, rcx
0x140006a95  jz      short loc_140006AAD
0x140006a97  mov     edx, ebp; Tag
0x140006a99  call    cs:__imp_ExFreePoolWithTag
0x140006aa0  nop     dword ptr [rax+rax+00h]
0x140006aa5  mov     qword ptr [rbx+30h], 0
0x140006aad  mov     rcx, [rbx+20h]; P
0x140006ab1  test    rcx, rcx
0x140006ab4  jz      short loc_140006ACC
0x140006ab6  mov     edx, ebp; Tag
0x140006ab8  call    cs:__imp_ExFreePoolWithTag
0x140006abf  nop     dword ptr [rax+rax+00h]
0x140006ac4  mov     qword ptr [rbx+20h], 0
0x140006acc  mov     rcx, [rbx+10h]; P
0x140006ad0  test    rcx, rcx
0x140006ad3  jz      short loc_140006AEB
0x140006ad5  mov     edx, ebp; Tag
0x140006ad7  call    cs:__imp_ExFreePoolWithTag
0x140006ade  nop     dword ptr [rax+rax+00h]
0x140006ae3  mov     qword ptr [rbx+10h], 0
0x140006aeb  mov     edx, ebp; Tag
0x140006aed  mov     rcx, rbx; P
0x140006af0  call    cs:__imp_ExFreePoolWithTag
0x140006af7  nop     dword ptr [rax+rax+00h]
0x140006afc  mov     rbx, [rdi+50h]
0x140006b00  test    rbx, rbx
0x140006b03  jnz     loc_140006A68
0x140006b09  mov     rcx, [rdi+40h]; P
0x140006b0d  test    rcx, rcx
0x140006b10  jz      short loc_140006B24
0x140006b12  mov     edx, ebp; Tag
0x140006b14  call    cs:__imp_ExFreePoolWithTag
0x140006b1b  nop     dword ptr [rax+rax+00h]
0x140006b20  mov     [rdi+40h], rbx
0x140006b24  mov     edx, ebp; Tag
0x140006b26  mov     rcx, rdi; P
0x140006b29  call    cs:__imp_ExFreePoolWithTag
0x140006b30  nop     dword ptr [rax+rax+00h]
0x140006b35  xor     edx, edx; Restart
0x140006b37  lea     rcx, ?g_TrackingInfo@@3U_TRACKED_PATHS_TABLE@@A; PrefixTable
0x140006b3e  call    cs:__imp_RtlNextUnicodePrefix
0x140006b45  nop     dword ptr [rax+rax+00h]
0x140006b4a  mov     rdi, rax
0x140006b4d  test    rax, rax
0x140006b50  jnz     loc_140006A4D
0x140006b56  mov     rbx, [rsp+28h+arg_0]
0x140006b5b  mov     rbp, [rsp+28h+arg_8]
0x140006b60  add     rsp, 20h
0x140006b64  pop     rdi
0x140006b65  retn
```
