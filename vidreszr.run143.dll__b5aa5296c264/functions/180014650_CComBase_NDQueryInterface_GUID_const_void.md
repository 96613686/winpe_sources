# CComBase::NDQueryInterface(_GUID const &,void * *)

- ea: `0x180014650`
- end: `0x18001469d`
- name: `?NDQueryInterface@CComBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `77`
- prototype: `__int64 __fastcall(CComBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180014650`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall CComBase::NDQueryInterface(CComBase *this, const struct _GUID *a2, void **a3)
{
  if ( !a3 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    *a3 = this;
    (*(void (__fastcall **)(CComBase *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  else
  {
    *a3 = 0;
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x180014650  sub     rsp, 28h
0x180014654  test    r8, r8
0x180014657  jnz     short loc_180014660
0x180014659  mov     eax, 80004003h
0x18001465e  jmp     short loc_180014698
0x180014660  mov     rax, [rdx]
0x180014663  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18001466a  jnz     short loc_18001468C
0x18001466c  mov     rax, [rdx+8]
0x180014670  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180014677  jnz     short loc_18001468C
0x180014679  mov     [r8], rcx
0x18001467c  mov     rax, [rcx]
0x18001467f  mov     rax, [rax+8]
0x180014683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014688  xor     eax, eax
0x18001468a  jmp     short loc_180014698
0x18001468c  mov     qword ptr [r8], 0
0x180014693  mov     eax, 80004002h
0x180014698  add     rsp, 28h
0x18001469c  retn
```
