# CDPA<_SID,CTContainer_PolicyUnOwned<_SID>>::DestroyCallback(int (*)(_SID *,void *),void *)

- ea: `0x18000dd8c`
- end: `0x18000ddba`
- name: `?DestroyCallback@?$CDPA@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@QEAAXP6AHPEAU_SID@@PEAX@Z1@Z`
- size: `46`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000d994`
- `0x18000d9f8`
- `0x18000e6a0`
- `0x180014268`
- `0x1800142a0`
- `0x180014800`

## callees

- `0x18000bbd0`
- `0x18000dd8c`

## pseudocode

```c
void __fastcall CDPA<_SID,CTContainer_PolicyUnOwned<_SID>>::DestroyCallback(struct _DPA **a1)
{
  struct _DPA *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    g_pfn_DPA_DestroyCallback(v2, DPA_LocalFreeCB<_SID>, 0);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000dd8c  push    rbx
0x18000dd8e  sub     rsp, 20h
0x18000dd92  mov     rbx, rcx
0x18000dd95  mov     rcx, [rcx]; hdpa
0x18000dd98  test    rcx, rcx
0x18000dd9b  jz      short loc_18000DDB4
0x18000dd9d  xor     r8d, r8d; pData
0x18000dda0  lea     rdx, ??$DPA_LocalFreeCB@U_SID@@@@YAHPEAU_SID@@PEAX@Z; pfnCB
0x18000dda7  call    cs:g_pfn_DPA_DestroyCallback
0x18000ddad  mov     qword ptr [rbx], 0
0x18000ddb4  add     rsp, 20h
0x18000ddb8  pop     rbx
0x18000ddb9  retn
```
