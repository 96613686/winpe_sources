# CGlobalThumbsDBStore::_Reset(IStorage *,ushort *,CGlobalThumbsDBStore::STORAGEMODE,TRIBIT)

- ea: `0x18001fe54`
- end: `0x18001ff01`
- name: `?_Reset@CGlobalThumbsDBStore@@AEAAXPEAUIStorage@@PEAGW4STORAGEMODE@1@W4TRIBIT@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f78c`
- `0x18001fce4`
- `0x180024cbc`

## callees

- `0x18001fe54`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fea9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fea9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fe75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fe75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001feb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001feb7`
- `SHELL32!SHChangeNotify` at `0x18001fef9`
- `SHELL32!SHChangeNotify` at `0x18001fef9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CGlobalThumbsDBStore::_Reset(__int64 a1, __int64 a2, __int64 a3, int a4, int a5)
{
  __int64 v9; // r15
  void *v10; // r12
  int v11; // r13d

  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  v9 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  v10 = *(void **)(a1 + 24);
  v11 = *(_DWORD *)(a1 + 32);
  *(_QWORD *)(a1 + 16) = a2;
  *(_QWORD *)(a1 + 24) = a3;
  *(_DWORD *)(a1 + 32) = a4;
  *(_DWORD *)(a1 + 36) = a5;
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
  if ( v10 && v11 == 1 )
    SHChangeNotify(0x2000, 5u, v10, 0);
  CoTaskMemFree(v10);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
}

```

## disassembly

```asm
0x18001fe54  push    rbx
0x18001fe56  push    rbp
0x18001fe57  push    rsi
0x18001fe58  push    rdi
0x18001fe59  push    r12
0x18001fe5b  push    r13
0x18001fe5d  push    r14
0x18001fe5f  push    r15
0x18001fe61  sub     rsp, 28h
0x18001fe65  mov     r14d, r9d
0x18001fe68  mov     rdi, r8
0x18001fe6b  mov     rbx, rdx
0x18001fe6e  mov     rbp, rcx
0x18001fe71  add     rcx, 8; SRWLock
0x18001fe75  call    cs:__imp_AcquireSRWLockExclusive
0x18001fe7b  mov     r15, [rbp+10h]
0x18001fe7f  mov     qword ptr [rbp+10h], 0
0x18001fe87  mov     r12, [rbp+18h]
0x18001fe8b  mov     r13d, [rbp+20h]
0x18001fe8f  mov     [rbp+10h], rbx
0x18001fe93  mov     [rbp+18h], rdi
0x18001fe97  mov     [rbp+20h], r14d
0x18001fe9b  mov     eax, [rsp+68h+arg_20]
0x18001fea2  mov     [rbp+24h], eax
0x18001fea5  lea     rcx, [rbp+8]; SRWLock
0x18001fea9  call    cs:__imp_ReleaseSRWLockExclusive
0x18001feaf  test    r12, r12
0x18001feb2  jnz     short loc_18001FEE4
0x18001feb4  mov     rcx, r12; pv
0x18001feb7  call    cs:__imp_CoTaskMemFree
0x18001febd  nop
0x18001febe  test    r15, r15
0x18001fec1  jz      short loc_18001FED3
0x18001fec3  mov     rax, [r15]
0x18001fec6  mov     rcx, r15
0x18001fec9  mov     rax, [rax+10h]
0x18001fecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fed2  nop
0x18001fed3  add     rsp, 28h
0x18001fed7  pop     r15
0x18001fed9  pop     r14
0x18001fedb  pop     r13
0x18001fedd  pop     r12
0x18001fedf  pop     rdi
0x18001fee0  pop     rsi
0x18001fee1  pop     rbp
0x18001fee2  pop     rbx
0x18001fee3  retn
0x18001fee4  cmp     r13d, 1
0x18001fee8  jnz     short loc_18001FEB4
0x18001feea  xor     r9d, r9d; dwItem2
0x18001feed  mov     r8, r12; dwItem1
0x18001fef0  lea     edx, [r13+4]; uFlags
0x18001fef4  mov     ecx, 2000h; wEventId
0x18001fef9  call    cs:__imp_SHChangeNotify
0x18001feff  jmp     short loc_18001FEB4
```
