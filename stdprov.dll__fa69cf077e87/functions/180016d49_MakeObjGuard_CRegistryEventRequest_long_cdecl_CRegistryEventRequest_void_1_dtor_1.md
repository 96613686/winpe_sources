# _MakeObjGuard_CRegistryEventRequest_long_(__cdecl_CRegistryEventRequest::_)(void)__::_1_::dtor$1

- ea: `0x180016d49`
- end: `0x180016d6f`
- name: `_MakeObjGuard_CRegistryEventRequest_long_(__cdecl_CRegistryEventRequest::_)(void)__::_1_::dtor$1`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180014134`
- `0x180016d49`

## pseudocode

```c
__int64 __fastcall MakeObjGuard_CRegistryEventRequest_long____cdecl_CRegistryEventRequest::___void___::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)a2 & 2;
  if ( (_DWORD)result )
  {
    *(_DWORD *)a2 &= ~2u;
    return ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>::~ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>(*(_QWORD *)(a2 + 32));
  }
  return result;
}

```

## disassembly

```asm
0x180016d49  push    rbp
0x180016d4b  sub     rsp, 20h
0x180016d4f  mov     rbp, rdx
0x180016d52  mov     eax, [rbp+0]
0x180016d55  and     eax, 2
0x180016d58  test    eax, eax
0x180016d5a  jz      short loc_180016D69
0x180016d5c  and     dword ptr [rbp+0], 0FFFFFFFDh
0x180016d60  mov     rcx, [rbp+20h]
0x180016d64  call    ??1?$ObjScopeGuardImpl0@VCRegistryEventRequest@@P81@EAAJXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>::~ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>(void)
0x180016d69  add     rsp, 20h
0x180016d6d  pop     rbp
0x180016d6e  retn
```
