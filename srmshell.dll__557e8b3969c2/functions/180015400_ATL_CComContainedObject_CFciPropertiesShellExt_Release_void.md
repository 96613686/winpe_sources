# ATL::CComContainedObject<CFciPropertiesShellExt>::Release(void)

- ea: `0x180015400`
- end: `0x18001541a`
- name: `?Release@?$CComContainedObject@VCFciPropertiesShellExt@@@ATL@@UEAAKXZ`
- size: `26`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015420`

## callees

- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComContainedObject<CFciPropertiesShellExt>::Release(__int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180015400  sub     rsp, 28h
0x180015404  mov     rcx, [rcx+10h]
0x180015408  mov     rax, [rcx]
0x18001540b  mov     rax, [rax+10h]
0x18001540f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015414  nop
0x180015415  add     rsp, 28h
0x180015419  retn
```
