# CElevatedFactoryClient::CreateElevatedObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180001d50`
- end: `0x180001d88`
- name: `?CreateElevatedObject@CElevatedFactoryClient@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `56`
- prototype: `__int64 __fastcall(CElevatedFactoryClient *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001d50`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CElevatedFactoryClient::CreateElevatedObject(
        CElevatedFactoryClient *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  __int64 v7; // rcx

  result = 2147500037LL;
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
    return (*(__int64 (__fastcall **)(__int64, char *, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v7 + 40LL))(
             v7,
             (char *)this + 8,
             a2,
             a3,
             a4);
  return result;
}

```

## disassembly

```asm
0x180001d50  sub     rsp, 38h
0x180001d54  mov     r10, rdx
0x180001d57  mov     eax, 80004005h
0x180001d5c  mov     rdx, rcx
0x180001d5f  mov     rcx, [rcx+18h]
0x180001d63  test    rcx, rcx
0x180001d66  jz      short loc_180001D83
0x180001d68  mov     rax, [rcx]
0x180001d6b  add     rdx, 8
0x180001d6f  mov     [rsp+38h+var_18], r9
0x180001d74  mov     r9, r8
0x180001d77  mov     r8, r10
0x180001d7a  mov     rax, [rax+28h]
0x180001d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d83  add     rsp, 38h
0x180001d87  retn
```
