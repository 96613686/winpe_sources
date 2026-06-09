# ATL::CAtlModuleT<CATLwinetHCModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180010ac0`
- end: `0x180010add`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCATLwinetHCModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CATLwinetHCModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{832701D5-B081-4790-93A7-5BCC7EE0755E}");
}

```

## disassembly

```asm
0x180010ac0  mov     rax, [rdx]
0x180010ac3  lea     r8, a832701d5B08147; "{832701D5-B081-4790-93A7-5BCC7EE0755E}"
0x180010aca  mov     rcx, rdx
0x180010acd  lea     rdx, aAppid_0; "APPID"
0x180010ad4  mov     rax, [rax+18h]
0x180010ad8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
