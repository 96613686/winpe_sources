# ATL::CAtlModuleT<CSecurityCenterUIModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180004340`
- end: `0x180004367`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCSecurityCenterUIModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CSecurityCenterUIModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, _BYTE *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           byte_18000F684);
}

```

## disassembly

```asm
0x180004340  sub     rsp, 28h
0x180004344  mov     rcx, rdx
0x180004347  mov     rax, [rdx]
0x18000434a  lea     r8, byte_18000F684
0x180004351  lea     rdx, aAppid; "APPID"
0x180004358  mov     rax, [rax+18h]
0x18000435c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004361  nop
0x180004362  add     rsp, 28h
0x180004366  retn
```
