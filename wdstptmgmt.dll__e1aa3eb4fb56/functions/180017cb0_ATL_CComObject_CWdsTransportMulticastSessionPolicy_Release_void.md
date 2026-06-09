# ATL::CComObject<CWdsTransportMulticastSessionPolicy>::Release(void)

- ea: `0x180017cb0`
- end: `0x180017d11`
- name: `?Release@?$CComObject@VCWdsTransportMulticastSessionPolicy@@@ATL@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005ea4`
- `0x180017cb0`
- `0x180018348`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportMulticastSessionPolicy>::Release(__int64 a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = CWdsTransportServerComObjectRoot::InternalRelease((CWdsTransportServerComObjectRoot *)(a1 + 8));
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 152LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180017cb0  mov     [rsp+arg_8], rbx
0x180017cb5  push    rdi
0x180017cb6  sub     rsp, 20h
0x180017cba  mov     rbx, rcx
0x180017cbd  add     rcx, 8; this
0x180017cc1  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x180017cc6  mov     edi, eax
0x180017cc8  test    eax, eax
0x180017cca  jnz     short loc_180017D03
0x180017ccc  lea     rcx, [rsp+28h+arg_0]; this
0x180017cd1  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180017cd6  test    rbx, rbx
0x180017cd9  jz      short loc_180017CF0
0x180017cdb  mov     rdx, [rbx]
0x180017cde  mov     rcx, rbx
0x180017ce1  mov     rax, [rdx+98h]
0x180017ce8  lea     edx, [rdi+1]
0x180017ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cf0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180017cf7  mov     rax, [rcx]
0x180017cfa  mov     rax, [rax+10h]
0x180017cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d03  mov     rbx, [rsp+28h+arg_8]
0x180017d08  mov     eax, edi
0x180017d0a  add     rsp, 20h
0x180017d0e  pop     rdi
0x180017d0f  retn
```
