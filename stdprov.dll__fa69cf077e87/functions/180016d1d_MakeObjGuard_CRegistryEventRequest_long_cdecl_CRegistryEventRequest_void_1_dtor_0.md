# _MakeObjGuard_CRegistryEventRequest_long_(__cdecl_CRegistryEventRequest::_)(void)__::_1_::dtor$0

- ea: `0x180016d1d`
- end: `0x180016d43`
- name: `_MakeObjGuard_CRegistryEventRequest_long_(__cdecl_CRegistryEventRequest::_)(void)__::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180014134`
- `0x180016d1d`

## pseudocode

```c
__int64 __fastcall MakeObjGuard_CRegistryEventRequest_long____cdecl_CRegistryEventRequest::___void___::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)a2 & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)a2 &= ~1u;
    return ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>::~ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>(*(_QWORD *)(a2 + 32));
  }
  return result;
}

```

## disassembly

```asm
0x180016d1d  push    rbp
0x180016d1f  sub     rsp, 20h
0x180016d23  mov     rbp, rdx
0x180016d26  mov     eax, [rbp+0]
0x180016d29  and     eax, 1
0x180016d2c  test    eax, eax
0x180016d2e  jz      short loc_180016D3D
0x180016d30  and     dword ptr [rbp+0], 0FFFFFFFEh
0x180016d34  mov     rcx, [rbp+20h]
0x180016d38  call    ??1?$ObjScopeGuardImpl0@VCRegistryEventRequest@@P81@EAAJXZ@@QEAA@XZ; ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>::~ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>(void)
0x180016d3d  add     rsp, 20h
0x180016d41  pop     rbp
0x180016d42  retn
```
