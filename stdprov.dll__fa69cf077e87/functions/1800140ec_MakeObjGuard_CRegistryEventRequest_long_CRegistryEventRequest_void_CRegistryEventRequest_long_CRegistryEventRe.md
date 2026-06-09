# MakeObjGuard<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>(CRegistryEventRequest &,long (CRegistryEventRequest::*)(void))

- ea: `0x1800140ec`
- end: `0x18001412b`
- name: `??$MakeObjGuard@VCRegistryEventRequest@@P81@EAAJXZ@@YA?AV?$ObjScopeGuardImpl0@VCRegistryEventRequest@@P81@EAAJXZ@@AEAVCRegistryEventRequest@@P81@EAAJXZ@Z`
- size: `63`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180006740`

## pseudocode

```c
__int64 __fastcall MakeObjGuard<CRegistryEventRequest,long (CRegistryEventRequest::*)(void)>(__int64 a1, __int64 a2)
{
  *(_BYTE *)a1 = 0;
  *(_QWORD *)(a1 + 8) = a2;
  *(_QWORD *)(a1 + 16) = CRegistryEventRequest::Release;
  return a1;
}

```

## disassembly

```asm
0x1800140ec  mov     [rsp+arg_0], rcx
0x1800140f1  sub     rsp, 18h
0x1800140f5  mov     [rsp+18h+var_18], 0
0x1800140fc  mov     byte ptr [rcx], 0
0x1800140ff  mov     [rcx+8], rdx
0x180014103  lea     rax, ?Release@CRegistryEventRequest@@QEAAJXZ; CRegistryEventRequest::Release(void)
0x18001410a  mov     [rcx+10h], rax
0x18001410e  mov     eax, 2
0x180014113  mov     [rsp+18h+var_18], eax
0x180014116  and     eax, 0FFFFFFFDh
0x180014119  mov     [rsp+18h+var_18], eax
0x18001411c  or      eax, 1
0x18001411f  mov     [rsp+18h+var_18], eax
0x180014122  mov     rax, rcx
0x180014125  add     rsp, 18h
0x180014129  retn
```
