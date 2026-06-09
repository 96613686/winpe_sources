# ATL::CComObject<CWdsTransportSetupManager>::Release(void)

- ea: `0x18000a9d0`
- end: `0x18000aa2e`
- name: `?Release@?$CComObject@VCWdsTransportSetupManager@@@ATL@@UEAAKXZ`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005ea4`
- `0x18000a9d0`
- `0x180018348`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportSetupManager>::Release(__int64 a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = CWdsTransportServerComObjectRoot::InternalRelease((CWdsTransportServerComObjectRoot *)(a1 + 8));
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000a9d0  mov     [rsp+arg_8], rbx
0x18000a9d5  push    rdi
0x18000a9d6  sub     rsp, 20h
0x18000a9da  mov     rbx, rcx
0x18000a9dd  add     rcx, 8; this
0x18000a9e1  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x18000a9e6  mov     edi, eax
0x18000a9e8  test    eax, eax
0x18000a9ea  jnz     short loc_18000AA20
0x18000a9ec  lea     rcx, [rsp+28h+arg_0]; this
0x18000a9f1  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x18000a9f6  test    rbx, rbx
0x18000a9f9  jz      short loc_18000AA0D
0x18000a9fb  mov     rdx, [rbx]
0x18000a9fe  mov     rcx, rbx
0x18000aa01  mov     rax, [rdx+70h]
0x18000aa05  lea     edx, [rdi+1]
0x18000aa08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa0d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000aa14  mov     rax, [rcx]
0x18000aa17  mov     rax, [rax+10h]
0x18000aa1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa20  mov     rbx, [rsp+28h+arg_8]
0x18000aa25  mov     eax, edi
0x18000aa27  add     rsp, 20h
0x18000aa2b  pop     rdi
0x18000aa2c  retn
```
