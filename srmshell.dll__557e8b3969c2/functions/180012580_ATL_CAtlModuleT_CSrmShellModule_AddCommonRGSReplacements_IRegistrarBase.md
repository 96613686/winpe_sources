# ATL::CAtlModuleT<CSrmShellModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180012580`
- end: `0x1800125a7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCSrmShellModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CSrmShellModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_180023088);
}

```

## disassembly

```asm
0x180012580  sub     rsp, 28h
0x180012584  mov     rcx, rdx
0x180012587  mov     rax, [rdx]
0x18001258a  lea     r8, qword_180023088
0x180012591  lea     rdx, aAppid; "APPID"
0x180012598  mov     rax, [rax+18h]
0x18001259c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125a1  nop
0x1800125a2  add     rsp, 28h
0x1800125a6  retn
```
