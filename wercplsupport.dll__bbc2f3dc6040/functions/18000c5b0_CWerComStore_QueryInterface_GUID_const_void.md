# CWerComStore::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c5b0`
- end: `0x18000c625`
- name: `?QueryInterface@CWerComStore@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `117`
- prototype: `__int64 __fastcall(CWerComStore *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c630`

## callees

- `0x18000c5b0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComStore::QueryInterface(CWerComStore *this, const struct _GUID *a2, CWerComStore **a3)
{
  CWerComStore *v3; // rax

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    v3 = this;
LABEL_7:
    *a3 = v3;
    (*(void (__fastcall **)(CWerComStore *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWerStore.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IWerStore.Data4 )
  {
    v3 = (CWerComStore *)(((unsigned __int64)this + 24) & -(__int64)(this != 0));
    goto LABEL_7;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000c5b0  sub     rsp, 28h
0x18000c5b4  mov     rax, [rdx]
0x18000c5b7  mov     r9, rcx
0x18000c5ba  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c5c1  jnz     short loc_18000C5D5
0x18000c5c3  mov     rax, [rdx+8]
0x18000c5c7  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c5ce  jnz     short loc_18000C5D5
0x18000c5d0  mov     rax, rcx
0x18000c5d3  jmp     short loc_18000C5FE
0x18000c5d5  mov     rax, [rdx]
0x18000c5d8  cmp     rax, qword ptr cs:IID_IWerStore.Data1
0x18000c5df  jnz     short loc_18000C614
0x18000c5e1  mov     rax, [rdx+8]
0x18000c5e5  cmp     rax, qword ptr cs:IID_IWerStore.Data4
0x18000c5ec  jnz     short loc_18000C614
0x18000c5ee  add     rcx, 18h
0x18000c5f2  mov     rax, r9
0x18000c5f5  neg     rax
0x18000c5f8  sbb     rax, rax
0x18000c5fb  and     rax, rcx
0x18000c5fe  mov     [r8], rax
0x18000c601  mov     rcx, r9
0x18000c604  mov     rax, [r9]
0x18000c607  mov     rax, [rax+8]
0x18000c60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c610  xor     eax, eax
0x18000c612  jmp     short loc_18000C620
0x18000c614  mov     qword ptr [r8], 0
0x18000c61b  mov     eax, 80004002h
0x18000c620  add     rsp, 28h
0x18000c624  retn
```
