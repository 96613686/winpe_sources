# ATL::CAtlModuleT<CPrincipalProviderLibModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180003790`
- end: `0x1800037b7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCPrincipalProviderLibModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CPrincipalProviderLibModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           byte_180017D50);
}

```

## disassembly

```asm
0x180003790  sub     rsp, 28h
0x180003794  mov     rcx, rdx
0x180003797  mov     rax, [rdx]
0x18000379a  lea     r8, byte_180017D50
0x1800037a1  lea     rdx, aAppid; "APPID"
0x1800037a8  mov     rax, [rax+18h]
0x1800037ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b1  nop
0x1800037b2  add     rsp, 28h
0x1800037b6  retn
```
