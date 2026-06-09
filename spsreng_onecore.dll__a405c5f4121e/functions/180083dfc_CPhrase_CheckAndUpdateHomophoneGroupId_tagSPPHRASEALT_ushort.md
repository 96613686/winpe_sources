# CPhrase::CheckAndUpdateHomophoneGroupId(tagSPPHRASEALT *,ushort)

- ea: `0x180083dfc`
- end: `0x180083e7f`
- name: `?CheckAndUpdateHomophoneGroupId@CPhrase@@QEAAJPEAUtagSPPHRASEALT@@G@Z`
- size: `131`
- prototype: `__int64 __fastcall(CPhrase *__hidden this, struct tagSPPHRASEALT *, unsigned __int16)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18007a314`
- `0x18007afec`

## callees

- `0x180083dfc`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083e6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083e6d`

## pseudocode

```c
__int64 __fastcall CPhrase::CheckAndUpdateHomophoneGroupId(CPhrase *this, struct tagSPPHRASEALT *a2, __int16 a3)
{
  ISpPhraseBuilder *pPhrase; // rbx
  int v6; // edi
  void *v7; // rcx
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  pv = this;
  pPhrase = a2->pPhrase;
  pv = 0;
  v6 = ((__int64 (__fastcall *)(ISpPhraseBuilder *, LPVOID *))pPhrase->lpVtbl->GetPhrase)(pPhrase, &pv);
  if ( v6 >= 0 )
  {
    v7 = pv;
    if ( *((_WORD *)pv + 3) == a3 )
      goto LABEL_6;
    *((_WORD *)pv + 3) = a3;
    v6 = ((__int64 (__fastcall *)(ISpPhraseBuilder *, LPVOID))pPhrase->lpVtbl->InitFromPhrase)(pPhrase, pv);
    if ( v6 >= 0 )
      a2->pPhrase = pPhrase;
  }
  v7 = pv;
LABEL_6:
  if ( v7 )
    CoTaskMemFree(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180083dfc  mov     [rsp+pv], rcx
0x180083e01  push    rbx
0x180083e02  push    rsi
0x180083e03  push    rdi
0x180083e04  push    r14
0x180083e06  sub     rsp, 28h
0x180083e0a  mov     rbx, [rdx]
0x180083e0d  mov     r14, rdx
0x180083e10  mov     [rsp+48h+pv], 0
0x180083e19  lea     rdx, [rsp+48h+pv]
0x180083e1e  mov     rcx, rbx
0x180083e21  movzx   esi, r8w
0x180083e25  mov     rax, [rbx]
0x180083e28  mov     rax, [rax+18h]
0x180083e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083e31  mov     edi, eax
0x180083e33  test    eax, eax
0x180083e35  js      short loc_180083E63
0x180083e37  mov     rcx, [rsp+48h+pv]
0x180083e3c  cmp     [rcx+6], si
0x180083e40  jz      short loc_180083E68
0x180083e42  mov     [rcx+6], si
0x180083e46  mov     rcx, rbx
0x180083e49  mov     rax, [rbx]
0x180083e4c  mov     rdx, [rsp+48h+pv]
0x180083e51  mov     rax, [rax+38h]
0x180083e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083e5a  mov     edi, eax
0x180083e5c  test    eax, eax
0x180083e5e  js      short loc_180083E63
0x180083e60  mov     [r14], rbx
0x180083e63  mov     rcx, [rsp+48h+pv]; pv
0x180083e68  test    rcx, rcx
0x180083e6b  jz      short loc_180083E73
0x180083e6d  call    cs:__imp_CoTaskMemFree
0x180083e73  mov     eax, edi
0x180083e75  add     rsp, 28h
0x180083e79  pop     r14
0x180083e7b  pop     rdi
0x180083e7c  pop     rsi
0x180083e7d  pop     rbx
0x180083e7e  retn
```
