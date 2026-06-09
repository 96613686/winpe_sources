# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180003280`
- end: `0x1800032a7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &dword_18001682C);
}

```

## disassembly

```asm
0x180003280  sub     rsp, 28h
0x180003284  mov     rcx, rdx
0x180003287  mov     rax, [rdx]
0x18000328a  lea     r8, dword_18001682C
0x180003291  lea     rdx, aAppid; "APPID"
0x180003298  mov     rax, [rax+18h]
0x18000329c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a1  nop
0x1800032a2  add     rsp, 28h
0x1800032a6  retn
```
