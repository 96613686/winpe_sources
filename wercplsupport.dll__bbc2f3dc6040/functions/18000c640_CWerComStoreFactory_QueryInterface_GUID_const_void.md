# CWerComStoreFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c640`
- end: `0x18000c6b5`
- name: `?QueryInterface@CWerComStoreFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `117`
- prototype: `__int64 __fastcall(CWerComStoreFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c6c0`

## callees

- `0x18000c640`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComStoreFactory::QueryInterface(
        CWerComStoreFactory *this,
        const struct _GUID *a2,
        CWerComStoreFactory **a3)
{
  CWerComStoreFactory *v3; // rax

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    v3 = this;
LABEL_7:
    *a3 = v3;
    (*(void (__fastcall **)(CWerComStoreFactory *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWerStoreFactory.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IWerStoreFactory.Data4 )
  {
    v3 = (CWerComStoreFactory *)(((unsigned __int64)this + 24) & -(__int64)(this != 0));
    goto LABEL_7;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000c640  sub     rsp, 28h
0x18000c644  mov     rax, [rdx]
0x18000c647  mov     r9, rcx
0x18000c64a  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c651  jnz     short loc_18000C665
0x18000c653  mov     rax, [rdx+8]
0x18000c657  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c65e  jnz     short loc_18000C665
0x18000c660  mov     rax, rcx
0x18000c663  jmp     short loc_18000C68E
0x18000c665  mov     rax, [rdx]
0x18000c668  cmp     rax, qword ptr cs:IID_IWerStoreFactory.Data1
0x18000c66f  jnz     short loc_18000C6A4
0x18000c671  mov     rax, [rdx+8]
0x18000c675  cmp     rax, qword ptr cs:IID_IWerStoreFactory.Data4
0x18000c67c  jnz     short loc_18000C6A4
0x18000c67e  add     rcx, 18h
0x18000c682  mov     rax, r9
0x18000c685  neg     rax
0x18000c688  sbb     rax, rax
0x18000c68b  and     rax, rcx
0x18000c68e  mov     [r8], rax
0x18000c691  mov     rcx, r9
0x18000c694  mov     rax, [r9]
0x18000c697  mov     rax, [rax+8]
0x18000c69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6a0  xor     eax, eax
0x18000c6a2  jmp     short loc_18000C6B0
0x18000c6a4  mov     qword ptr [r8], 0
0x18000c6ab  mov     eax, 80004002h
0x18000c6b0  add     rsp, 28h
0x18000c6b4  retn
```
