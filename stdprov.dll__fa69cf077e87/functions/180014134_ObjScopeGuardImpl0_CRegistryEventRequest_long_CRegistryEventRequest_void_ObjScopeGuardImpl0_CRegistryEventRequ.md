# ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>::~ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>(void)

- ea: `0x180014134`
- end: `0x180014153`
- name: `??1?$ObjScopeGuardImpl0@VCRegistryEventRequest@@P81@EAAJXZ@@QEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006740`
- `0x180015ec6`
- `0x180015efc`
- `0x180016d1d`
- `0x180016d49`

## callees

- `0x180014134`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>::~ObjScopeGuardImpl0<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>(
        __int64 a1)
{
  __int64 result; // rax

  result = a1;
  if ( !*(_BYTE *)a1 )
    return (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)(a1 + 8));
  return result;
}

```

## disassembly

```asm
0x180014134  sub     rsp, 28h
0x180014138  mov     rax, rcx
0x18001413b  cmp     byte ptr [rcx], 0
0x18001413e  jnz     short loc_18001414E
0x180014140  mov     rcx, [rcx+8]
0x180014144  mov     rax, [rax+10h]
0x180014148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001414d  nop
0x18001414e  add     rsp, 28h
0x180014152  retn
```
