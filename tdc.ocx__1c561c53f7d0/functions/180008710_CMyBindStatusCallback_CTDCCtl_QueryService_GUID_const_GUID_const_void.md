# CMyBindStatusCallback<CTDCCtl>::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x180008710`
- end: `0x180008747`
- name: `?QueryService@?$CMyBindStatusCallback@VCTDCCtl@@@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180008710`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CMyBindStatusCallback<CTDCCtl>::QueryService(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  if ( *(_QWORD *)&IID_IHttpNegotiate.Data1 == *a2 && *(_QWORD *)IID_IHttpNegotiate.Data4 == a2[1] )
    return (**(__int64 (__fastcall ***)(__int64, __int64, __int64))(a1 - 16))(a1 - 16, a3, a4);
  else
    return 2147500033LL;
}

```

## disassembly

```asm
0x180008710  mov     rax, qword ptr cs:IID_IHttpNegotiate.Data1
0x180008717  mov     r10, r8
0x18000871a  cmp     rax, [rdx]
0x18000871d  jnz     short loc_180008741
0x18000871f  mov     rax, qword ptr cs:IID_IHttpNegotiate.Data4
0x180008726  cmp     rax, [rdx+8]
0x18000872a  jnz     short loc_180008741
0x18000872c  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180008730  mov     r8, r9
0x180008733  mov     rdx, r10
0x180008736  mov     rax, [rcx]
0x180008739  mov     rax, [rax]
0x18000873c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180008741  mov     eax, 80004001h
0x180008746  retn
```
