# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180005d60`
- end: `0x180005d87`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_180012480);
}

```

## disassembly

```asm
0x180005d60  sub     rsp, 28h
0x180005d64  mov     rcx, rdx
0x180005d67  mov     rax, [rdx]
0x180005d6a  lea     r8, qword_180012480
0x180005d71  lea     rdx, aAppid; "APPID"
0x180005d78  mov     rax, [rax+18h]
0x180005d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d81  nop
0x180005d82  add     rsp, 28h
0x180005d86  retn
```
