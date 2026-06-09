# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x140002810`
- end: `0x140002837`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_140009AC0);
}

```

## disassembly

```asm
0x140002810  sub     rsp, 28h
0x140002814  mov     rcx, rdx
0x140002817  mov     rax, [rdx]
0x14000281a  lea     r8, qword_140009AC0
0x140002821  lea     rdx, aAppid; "APPID"
0x140002828  mov     rax, [rax+18h]
0x14000282c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002831  nop
0x140002832  add     rsp, 28h
0x140002836  retn
```
