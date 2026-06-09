# FreeAlternate(tagSPPHRASEALT *)

- ea: `0x18008352c`
- end: `0x180083571`
- name: `?FreeAlternate@@YAXPEAUtagSPPHRASEALT@@@Z`
- size: `69`
- prototype: `void __fastcall(struct tagSPPHRASEALT *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009cd0`
- `0x180079fd8`
- `0x18007a314`
- `0x180082b2c`
- `0x180082b8c`
- `0x180086274`

## callees

- `0x18008352c`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008355d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008355d`

## pseudocode

```c
void __fastcall FreeAlternate(struct tagSPPHRASEALT *a1)
{
  ISpPhraseBuilder *pPhrase; // rcx
  void *pvAltExtra; // rcx

  if ( a1 )
  {
    pPhrase = a1->pPhrase;
    if ( pPhrase )
    {
      ((void (__fastcall *)(ISpPhraseBuilder *))pPhrase->lpVtbl->Release)(pPhrase);
      a1->pPhrase = 0;
    }
    pvAltExtra = a1->pvAltExtra;
    if ( pvAltExtra )
    {
      CoTaskMemFree(pvAltExtra);
      a1->pvAltExtra = 0;
    }
  }
}

```

## disassembly

```asm
0x18008352c  test    rcx, rcx
0x18008352f  jz      short locret_180083570
0x180083531  push    rbx
0x180083532  sub     rsp, 20h
0x180083536  mov     rbx, rcx
0x180083539  mov     rcx, [rcx]
0x18008353c  test    rcx, rcx
0x18008353f  jz      short loc_180083554
0x180083541  mov     rax, [rcx]
0x180083544  mov     rax, [rax+10h]
0x180083548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008354d  mov     qword ptr [rbx], 0
0x180083554  mov     rcx, [rbx+18h]; pv
0x180083558  test    rcx, rcx
0x18008355b  jz      short loc_18008356B
0x18008355d  call    cs:__imp_CoTaskMemFree
0x180083563  mov     qword ptr [rbx+18h], 0
0x18008356b  add     rsp, 20h
0x18008356f  pop     rbx
0x180083570  retn
```
