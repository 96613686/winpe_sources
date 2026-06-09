# CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::AppendPtr(_SID *,int *)

- ea: `0x1800092e0`
- end: `0x180009309`
- name: `?AppendPtr@?$CDPA_Base@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@QEAAJPEAU_SID@@PEAH@Z`
- size: `41`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007e40`
- `0x18000e3a0`
- `0x1800145c4`
- `0x180014b50`

## callees

- `0x180008300`

## pseudocode

```c
__int64 __fastcall CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::AppendPtr(HDPA *a1, void *a2)
{
  int inserted; // eax
  unsigned int v3; // ecx

  inserted = DPA_InsertPtr(*a1, 0x7FFFFFFF, a2);
  v3 = 0;
  if ( inserted == -1 )
    return (unsigned int)-2147024882;
  return v3;
}

```

## disassembly

```asm
0x1800092e0  sub     rsp, 28h
0x1800092e4  mov     rcx, [rcx]; hdpa
0x1800092e7  mov     r8, rdx; p
0x1800092ea  mov     edx, 7FFFFFFFh; i
0x1800092ef  call    cs:__imp_DPA_InsertPtr
0x1800092f5  xor     ecx, ecx
0x1800092f7  mov     edx, 8007000Eh
0x1800092fc  cmp     eax, 0FFFFFFFFh
0x1800092ff  cmovz   ecx, edx
0x180009302  mov     eax, ecx
0x180009304  add     rsp, 28h
0x180009308  retn
```
