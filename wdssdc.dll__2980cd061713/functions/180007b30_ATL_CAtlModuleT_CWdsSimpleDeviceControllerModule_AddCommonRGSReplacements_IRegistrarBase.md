# ATL::CAtlModuleT<CWdsSimpleDeviceControllerModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180007b30`
- end: `0x180007b4d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCWdsSimpleDeviceControllerModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CWdsSimpleDeviceControllerModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"70F829DE-656F-4EA9-B6BD-7D092099429C");
}

```

## disassembly

```asm
0x180007b30  mov     rax, [rdx]
0x180007b33  lea     r8, a70f829de656f4e; "70F829DE-656F-4EA9-B6BD-7D092099429C"
0x180007b3a  mov     rcx, rdx
0x180007b3d  lea     rdx, aAppid; "APPID"
0x180007b44  mov     rax, [rax+18h]
0x180007b48  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
