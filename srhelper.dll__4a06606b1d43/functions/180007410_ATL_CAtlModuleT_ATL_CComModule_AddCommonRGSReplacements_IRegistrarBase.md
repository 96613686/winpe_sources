# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180007410`
- end: `0x18000742d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_1800196D0);
}

```

## disassembly

```asm
0x180007410  mov     rax, [rdx]
0x180007413  lea     r8, qword_1800196D0
0x18000741a  mov     rcx, rdx
0x18000741d  lea     rdx, aAppid; "APPID"
0x180007424  mov     rax, [rax+18h]
0x180007428  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
