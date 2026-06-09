# ATL::CAtlModuleT<sandbox::IsolationHost>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x140012620`
- end: `0x14001263d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VIsolationHost@sandbox@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140016010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<sandbox::IsolationHost>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           byte_140019300);
}

```

## disassembly

```asm
0x140012620  mov     rax, [rdx]
0x140012623  lea     r8, byte_140019300
0x14001262a  mov     rcx, rdx
0x14001262d  lea     rdx, aAppid; "APPID"
0x140012634  mov     rax, [rax+18h]
0x140012638  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
