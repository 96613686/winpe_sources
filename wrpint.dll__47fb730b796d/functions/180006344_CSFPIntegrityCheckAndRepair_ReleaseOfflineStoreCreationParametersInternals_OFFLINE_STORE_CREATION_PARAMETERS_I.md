# CSFPIntegrityCheckAndRepair::ReleaseOfflineStoreCreationParametersInternals(_OFFLINE_STORE_CREATION_PARAMETERS *,IMalloc *)

- ea: `0x180006344`
- end: `0x1800064e3`
- name: `?ReleaseOfflineStoreCreationParametersInternals@CSFPIntegrityCheckAndRepair@@AEAAJPEAU_OFFLINE_STORE_CREATION_PARAMETERS@@PEAUIMalloc@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *__hidden this, struct _OFFLINE_STORE_CREATION_PARAMETERS *, struct IMalloc *)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002a50`
- `0x180005260`
- `0x1800056a0`

## callees

- `0x180006344`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::ReleaseOfflineStoreCreationParametersInternals(
        CSFPIntegrityCheckAndRepair *this,
        struct _OFFLINE_STORE_CREATION_PARAMETERS *a2,
        struct IMalloc *a3)
{
  __int64 v3; // rdi

  v3 = qword_18002B8B0;
  (*(void (__fastcall **)(__int64, struct _OFFLINE_STORE_CREATION_PARAMETERS *, struct IMalloc *))(*(_QWORD *)qword_18002B8B0
                                                                                                 + 8LL))(
    qword_18002B8B0,
    a2,
    a3);
  if ( *((_QWORD *)a2 + 2) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 2) = 0;
  }
  if ( *((_QWORD *)a2 + 3) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 3) = 0;
  }
  if ( *((_QWORD *)a2 + 4) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 4) = 0;
  }
  if ( *((_QWORD *)a2 + 5) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 5) = 0;
  }
  if ( *((_QWORD *)a2 + 6) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 6) = 0;
  }
  if ( *((_QWORD *)a2 + 7) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 7) = 0;
  }
  if ( *((_QWORD *)a2 + 8) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 8) = 0;
  }
  if ( *((_QWORD *)a2 + 9) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 9) = 0;
  }
  if ( *((_QWORD *)a2 + 10) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 10) = 0;
  }
  if ( *((_QWORD *)a2 + 11) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 11) = 0;
  }
  if ( *((_QWORD *)a2 + 13) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
    *((_QWORD *)a2 + 13) = 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  return 0;
}

```

## disassembly

```asm
0x180006344  mov     [rsp+arg_0], rbx
0x180006349  push    rdi
0x18000634a  sub     rsp, 20h
0x18000634e  mov     rdi, cs:qword_18002B8B0
0x180006355  mov     rbx, rdx
0x180006358  mov     rcx, rdi
0x18000635b  mov     rax, [rdi]
0x18000635e  mov     rax, [rax+8]
0x180006362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006367  mov     rdx, [rbx+10h]
0x18000636b  test    rdx, rdx
0x18000636e  jz      short loc_180006387
0x180006370  mov     rax, [rdi]
0x180006373  mov     rcx, rdi
0x180006376  mov     rax, [rax+28h]
0x18000637a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000637f  mov     qword ptr [rbx+10h], 0
0x180006387  mov     rdx, [rbx+18h]
0x18000638b  test    rdx, rdx
0x18000638e  jz      short loc_1800063A7
0x180006390  mov     rax, [rdi]
0x180006393  mov     rcx, rdi
0x180006396  mov     rax, [rax+28h]
0x18000639a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000639f  mov     qword ptr [rbx+18h], 0
0x1800063a7  mov     rdx, [rbx+20h]
0x1800063ab  test    rdx, rdx
0x1800063ae  jz      short loc_1800063C7
0x1800063b0  mov     rax, [rdi]
0x1800063b3  mov     rcx, rdi
0x1800063b6  mov     rax, [rax+28h]
0x1800063ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063bf  mov     qword ptr [rbx+20h], 0
0x1800063c7  mov     rdx, [rbx+28h]
0x1800063cb  test    rdx, rdx
0x1800063ce  jz      short loc_1800063E7
0x1800063d0  mov     rax, [rdi]
0x1800063d3  mov     rcx, rdi
0x1800063d6  mov     rax, [rax+28h]
0x1800063da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063df  mov     qword ptr [rbx+28h], 0
0x1800063e7  mov     rdx, [rbx+30h]
0x1800063eb  test    rdx, rdx
0x1800063ee  jz      short loc_180006407
0x1800063f0  mov     rax, [rdi]
0x1800063f3  mov     rcx, rdi
0x1800063f6  mov     rax, [rax+28h]
0x1800063fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ff  mov     qword ptr [rbx+30h], 0
0x180006407  mov     rdx, [rbx+38h]
0x18000640b  test    rdx, rdx
0x18000640e  jz      short loc_180006427
0x180006410  mov     rax, [rdi]
0x180006413  mov     rcx, rdi
0x180006416  mov     rax, [rax+28h]
0x18000641a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000641f  mov     qword ptr [rbx+38h], 0
0x180006427  mov     rdx, [rbx+40h]
0x18000642b  test    rdx, rdx
0x18000642e  jz      short loc_180006447
0x180006430  mov     rax, [rdi]
0x180006433  mov     rcx, rdi
0x180006436  mov     rax, [rax+28h]
0x18000643a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000643f  mov     qword ptr [rbx+40h], 0
0x180006447  mov     rdx, [rbx+48h]
0x18000644b  test    rdx, rdx
0x18000644e  jz      short loc_180006467
0x180006450  mov     rax, [rdi]
0x180006453  mov     rcx, rdi
0x180006456  mov     rax, [rax+28h]
0x18000645a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000645f  mov     qword ptr [rbx+48h], 0
0x180006467  mov     rdx, [rbx+50h]
0x18000646b  test    rdx, rdx
0x18000646e  jz      short loc_180006487
0x180006470  mov     rax, [rdi]
0x180006473  mov     rcx, rdi
0x180006476  mov     rax, [rax+28h]
0x18000647a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000647f  mov     qword ptr [rbx+50h], 0
0x180006487  mov     rdx, [rbx+58h]
0x18000648b  test    rdx, rdx
0x18000648e  jz      short loc_1800064A7
0x180006490  mov     rax, [rdi]
0x180006493  mov     rcx, rdi
0x180006496  mov     rax, [rax+28h]
0x18000649a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000649f  mov     qword ptr [rbx+58h], 0
0x1800064a7  mov     rdx, [rbx+68h]
0x1800064ab  test    rdx, rdx
0x1800064ae  jz      short loc_1800064C7
0x1800064b0  mov     rax, [rdi]
0x1800064b3  mov     rcx, rdi
0x1800064b6  mov     rax, [rax+28h]
0x1800064ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064bf  mov     qword ptr [rbx+68h], 0
0x1800064c7  mov     rax, [rdi]
0x1800064ca  mov     rcx, rdi
0x1800064cd  mov     rax, [rax+10h]
0x1800064d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d6  mov     rbx, [rsp+28h+arg_0]
0x1800064db  xor     eax, eax
0x1800064dd  add     rsp, 20h
0x1800064e1  pop     rdi
0x1800064e2  retn
```
