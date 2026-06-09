# CWMDSPComBase::NDQueryInterface(_GUID const &,void * *)

- ea: `0x18000f950`
- end: `0x18000f9a0`
- name: `?NDQueryInterface@CWMDSPComBase@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `80`
- prototype: `__int64 __fastcall(CWMDSPComBase *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f950`
- `0x180086010`

## pseudocode

```c
__int64 __fastcall CWMDSPComBase::NDQueryInterface(CWMDSPComBase *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rax

  if ( !a3 )
    return 2147500035LL;
  v3 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v3 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( v3 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
    *a3 = this;
    (*(void (__fastcall **)(CWMDSPComBase *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x18000f950  sub     rsp, 28h
0x18000f954  test    r8, r8
0x18000f957  jz      short loc_18000F999
0x18000f959  mov     rax, [rdx]
0x18000f95c  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000f963  jnz     short loc_18000F970
0x18000f965  mov     rax, [rdx+8]
0x18000f969  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000f970  test    rax, rax
0x18000f973  jnz     short loc_18000F98B
0x18000f975  mov     [r8], rcx
0x18000f978  mov     rax, [rcx]
0x18000f97b  mov     rax, [rax+8]
0x18000f97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f984  xor     eax, eax
0x18000f986  add     rsp, 28h
0x18000f98a  retn
0x18000f98b  mov     qword ptr [r8], 0
0x18000f992  mov     eax, 80004002h
0x18000f997  jmp     short loc_18000F986
0x18000f999  mov     eax, 80004003h
0x18000f99e  jmp     short loc_18000F986
```
