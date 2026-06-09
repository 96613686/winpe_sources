# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x18000f3b0`
- end: `0x18000f3cd`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const WCHAR *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &psz1);
}

```

## disassembly

```asm
0x18000f3b0  mov     rax, [rdx]
0x18000f3b3  lea     r8, psz1
0x18000f3ba  mov     rcx, rdx
0x18000f3bd  lea     rdx, aAppid; "APPID"
0x18000f3c4  mov     rax, [rax+18h]
0x18000f3c8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
