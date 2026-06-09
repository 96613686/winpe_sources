# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180002fb0`
- end: `0x180002fcd`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const WCHAR *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &String);
}

```

## disassembly

```asm
0x180002fb0  mov     rax, [rdx]
0x180002fb3  lea     r8, String
0x180002fba  mov     rcx, rdx
0x180002fbd  lea     rdx, aAppid; "APPID"
0x180002fc4  mov     rax, [rax+18h]
0x180002fc8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
