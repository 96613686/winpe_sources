# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180002670`
- end: `0x180002697`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &dword_180009ABC);
}

```

## disassembly

```asm
0x180002670  sub     rsp, 28h
0x180002674  mov     rcx, rdx
0x180002677  mov     rax, [rdx]
0x18000267a  lea     r8, dword_180009ABC
0x180002681  lea     rdx, aAppid; "APPID"
0x180002688  mov     rax, [rax+18h]
0x18000268c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002691  nop
0x180002692  add     rsp, 28h
0x180002696  retn
```
