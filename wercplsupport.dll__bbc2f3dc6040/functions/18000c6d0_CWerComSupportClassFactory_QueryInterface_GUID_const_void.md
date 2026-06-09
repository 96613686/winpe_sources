# CWerComSupportClassFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x18000c6d0`
- end: `0x18000c745`
- name: `?QueryInterface@CWerComSupportClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `117`
- prototype: `__int64 __fastcall(CWerComSupportClassFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c750`

## callees

- `0x18000c6d0`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall CWerComSupportClassFactory::QueryInterface(
        CWerComSupportClassFactory *this,
        const struct _GUID *a2,
        CWerComSupportClassFactory **a3)
{
  CWerComSupportClassFactory *v3; // rax

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    v3 = this;
LABEL_7:
    *a3 = v3;
    (*(void (__fastcall **)(CWerComSupportClassFactory *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IClassFactory.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IClassFactory.Data4 )
  {
    v3 = (CWerComSupportClassFactory *)(((unsigned __int64)this + 24) & -(__int64)(this != 0));
    goto LABEL_7;
  }
  *a3 = 0;
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000c6d0  sub     rsp, 28h
0x18000c6d4  mov     rax, [rdx]
0x18000c6d7  mov     r9, rcx
0x18000c6da  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000c6e1  jnz     short loc_18000C6F5
0x18000c6e3  mov     rax, [rdx+8]
0x18000c6e7  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000c6ee  jnz     short loc_18000C6F5
0x18000c6f0  mov     rax, rcx
0x18000c6f3  jmp     short loc_18000C71E
0x18000c6f5  mov     rax, [rdx]
0x18000c6f8  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x18000c6ff  jnz     short loc_18000C734
0x18000c701  mov     rax, [rdx+8]
0x18000c705  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x18000c70c  jnz     short loc_18000C734
0x18000c70e  add     rcx, 18h
0x18000c712  mov     rax, r9
0x18000c715  neg     rax
0x18000c718  sbb     rax, rax
0x18000c71b  and     rax, rcx
0x18000c71e  mov     [r8], rax
0x18000c721  mov     rcx, r9
0x18000c724  mov     rax, [r9]
0x18000c727  mov     rax, [rax+8]
0x18000c72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c730  xor     eax, eax
0x18000c732  jmp     short loc_18000C740
0x18000c734  mov     qword ptr [r8], 0
0x18000c73b  mov     eax, 80004002h
0x18000c740  add     rsp, 28h
0x18000c744  retn
```
