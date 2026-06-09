# ATL::CComObject<CWdsTransportDiagnosticsPolicy>::Release(void)

- ea: `0x18000fa40`
- end: `0x18000fa9e`
- name: `?Release@?$CComObject@VCWdsTransportDiagnosticsPolicy@@@ATL@@UEAAKXZ`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005ea4`
- `0x18000fa40`
- `0x180018348`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportDiagnosticsPolicy>::Release(__int64 a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = CWdsTransportServerComObjectRoot::InternalRelease((CWdsTransportServerComObjectRoot *)(a1 + 8));
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 120LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000fa40  mov     [rsp+arg_8], rbx
0x18000fa45  push    rdi
0x18000fa46  sub     rsp, 20h
0x18000fa4a  mov     rbx, rcx
0x18000fa4d  add     rcx, 8; this
0x18000fa51  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x18000fa56  mov     edi, eax
0x18000fa58  test    eax, eax
0x18000fa5a  jnz     short loc_18000FA90
0x18000fa5c  lea     rcx, [rsp+28h+arg_0]; this
0x18000fa61  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x18000fa66  test    rbx, rbx
0x18000fa69  jz      short loc_18000FA7D
0x18000fa6b  mov     rdx, [rbx]
0x18000fa6e  mov     rcx, rbx
0x18000fa71  mov     rax, [rdx+78h]
0x18000fa75  lea     edx, [rdi+1]
0x18000fa78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa7d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000fa84  mov     rax, [rcx]
0x18000fa87  mov     rax, [rax+10h]
0x18000fa8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa90  mov     rbx, [rsp+28h+arg_8]
0x18000fa95  mov     eax, edi
0x18000fa97  add     rsp, 20h
0x18000fa9b  pop     rdi
0x18000fa9c  retn
```
