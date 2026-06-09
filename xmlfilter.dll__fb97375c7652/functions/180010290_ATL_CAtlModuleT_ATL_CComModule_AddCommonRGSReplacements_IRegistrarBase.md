# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180010290`
- end: `0x1800102b7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           byte_1800194F0);
}

```

## disassembly

```asm
0x180010290  sub     rsp, 28h
0x180010294  mov     rcx, rdx
0x180010297  mov     rax, [rdx]
0x18001029a  lea     r8, byte_1800194F0
0x1800102a1  lea     rdx, aAppid; "APPID"
0x1800102a8  mov     rax, [rax+18h]
0x1800102ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102b1  nop
0x1800102b2  add     rsp, 28h
0x1800102b6  retn
```
