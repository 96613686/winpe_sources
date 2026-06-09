# FreeSecurityDescriptors(_ACL * &,void * &)

- ea: `0x1800027c4`
- end: `0x180002809`
- name: `?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z`
- size: `69`
- prototype: `void __fastcall(struct _ACL **, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800024c4`
- `0x180003220`
- `0x1800039f0`
- `0x18000569c`
- `0x180006fbc`

## callees

- `0x1800027c4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800027dc`
- `KERNEL32!LocalFree` at `0x1800027f1`
- `KERNEL32!LocalFree` at `0x1800027dc`
- `KERNEL32!LocalFree` at `0x1800027f1`

## pseudocode

```c
void __fastcall FreeSecurityDescriptors(struct _ACL **a1, void **a2)
{
  void *v4; // rcx

  v4 = *a1;
  if ( v4 )
  {
    LocalFree(v4);
    *a1 = 0;
  }
  if ( *a2 )
  {
    LocalFree(*a2);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x1800027c4  mov     [rsp+arg_0], rbx
0x1800027c9  push    rdi
0x1800027ca  sub     rsp, 20h
0x1800027ce  mov     rdi, rcx
0x1800027d1  mov     rbx, rdx
0x1800027d4  mov     rcx, [rcx]; hMem
0x1800027d7  test    rcx, rcx
0x1800027da  jz      short loc_1800027E9
0x1800027dc  call    cs:__imp_LocalFree
0x1800027e2  mov     qword ptr [rdi], 0
0x1800027e9  mov     rcx, [rbx]; hMem
0x1800027ec  test    rcx, rcx
0x1800027ef  jz      short loc_1800027FE
0x1800027f1  call    cs:__imp_LocalFree
0x1800027f7  mov     qword ptr [rbx], 0
0x1800027fe  mov     rbx, [rsp+28h+arg_0]
0x180002803  add     rsp, 20h
0x180002807  pop     rdi
0x180002808  retn
```
