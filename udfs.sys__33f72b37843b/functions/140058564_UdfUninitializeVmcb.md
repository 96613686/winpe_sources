# UdfUninitializeVmcb

- ea: `0x140058564`
- end: `0x140058621`
- name: `UdfUninitializeVmcb`
- size: `189`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140009730`
- `0x14002c008`

## callees

- `0x14000ca54`
- `0x14001c080`
- `0x140058564`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400585de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400585de`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400585ee`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400585fe`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400585ee`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400585fe`
- `ntoskrnl!FsRtlUninitializeMcb` at `0x1400585b1`
- `ntoskrnl!FsRtlUninitializeMcb` at `0x1400585c4`
- `ntoskrnl!FsRtlUninitializeMcb` at `0x1400585b1`
- `ntoskrnl!FsRtlUninitializeMcb` at `0x1400585c4`

## pseudocode

```c
int *__fastcall UdfUninitializeVmcb(char *a1)
{
  int *result; // rax
  void *v3; // rcx

  result = &WPP_GLOBAL_Control;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x400000) != 0 )
  {
    result = (int *)WPP_SF_q(
                      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                      12,
                      WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids,
                      a1);
  }
  if ( a1[396] )
  {
    FsRtlUninitializeMcb((PMCB)(a1 + 216));
    FsRtlUninitializeMcb((PMCB)(a1 + 248));
    v3 = (void *)*((_QWORD *)a1 + 41);
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
    ExDeleteResourceLite((PERESOURCE)(a1 + 8));
    ExDeleteResourceLite((PERESOURCE)(a1 + 112));
    return (int *)memset(a1, 0, 0x1A0u);
  }
  return result;
}

```

## disassembly

```asm
0x140058564  push    rbx
0x140058566  sub     rsp, 20h
0x14005856a  mov     rbx, rcx
0x14005856d  mov     rcx, cs:WPP_GLOBAL_Control
0x140058574  lea     rax, WPP_GLOBAL_Control
0x14005857b  cmp     rcx, rax
0x14005857e  jz      short loc_1400585A1
0x140058580  test    dword ptr [rcx+2Ch], 400000h
0x140058587  jz      short loc_1400585A1
0x140058589  mov     rcx, [rcx+18h]
0x14005858d  lea     r8, WPP_c4c254f43dbb37edeabcdd77880d9f11_Traceguids
0x140058594  mov     edx, 0Ch
0x140058599  mov     r9, rbx
0x14005859c  call    WPP_SF_q
0x1400585a1  cmp     byte ptr [rbx+18Ch], 0
0x1400585a8  jz      short loc_14005861A
0x1400585aa  lea     rcx, [rbx+0D8h]; Mcb
0x1400585b1  call    cs:__imp_FsRtlUninitializeMcb
0x1400585b8  nop     dword ptr [rax+rax+00h]
0x1400585bd  lea     rcx, [rbx+0F8h]; Mcb
0x1400585c4  call    cs:__imp_FsRtlUninitializeMcb
0x1400585cb  nop     dword ptr [rax+rax+00h]
0x1400585d0  mov     rcx, [rbx+148h]; P
0x1400585d7  test    rcx, rcx
0x1400585da  jz      short loc_1400585EA
0x1400585dc  xor     edx, edx; Tag
0x1400585de  call    cs:__imp_ExFreePoolWithTag
0x1400585e5  nop     dword ptr [rax+rax+00h]
0x1400585ea  lea     rcx, [rbx+8]; Resource
0x1400585ee  call    cs:__imp_ExDeleteResourceLite
0x1400585f5  nop     dword ptr [rax+rax+00h]
0x1400585fa  lea     rcx, [rbx+70h]; Resource
0x1400585fe  call    cs:__imp_ExDeleteResourceLite
0x140058605  nop     dword ptr [rax+rax+00h]
0x14005860a  xor     edx, edx; Val
0x14005860c  mov     r8d, 1A0h; Size
0x140058612  mov     rcx, rbx; void *
0x140058615  call    memset
0x14005861a  add     rsp, 20h
0x14005861e  pop     rbx
0x14005861f  retn
```
