# DPA_LocalFreeCB<_SID>(_SID *,void *)

- ea: `0x18000d8e0`
- end: `0x18000d8f4`
- name: `??$DPA_LocalFreeCB@U_SID@@@@YAHPEAU_SID@@PEAX@Z`
- size: `20`
- prototype: `int __stdcall(void *p, void *pData)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d8e4`

## pseudocode

```c
__int64 __fastcall DPA_LocalFreeCB<_SID>(void *p, void *pData)
{
  LocalFree(p);
  return 1;
}

```

## disassembly

```asm
0x18000d8e0  sub     rsp, 28h
0x18000d8e4  call    cs:__imp_LocalFree
0x18000d8ea  mov     eax, 1
0x18000d8ef  add     rsp, 28h
0x18000d8f3  retn
```
