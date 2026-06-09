# ATL::CComObject<CWdsTransportConfigurationManager>::Release(void)

- ea: `0x18000bcc0`
- end: `0x18000bd21`
- name: `?Release@?$CComObject@VCWdsTransportConfigurationManager@@@ATL@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005ea4`
- `0x18000bcc0`
- `0x180018348`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportConfigurationManager>::Release(__int64 a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = CWdsTransportServerComObjectRoot::InternalRelease((CWdsTransportServerComObjectRoot *)(a1 + 8));
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 136LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000bcc0  mov     [rsp+arg_8], rbx
0x18000bcc5  push    rdi
0x18000bcc6  sub     rsp, 20h
0x18000bcca  mov     rbx, rcx
0x18000bccd  add     rcx, 8; this
0x18000bcd1  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x18000bcd6  mov     edi, eax
0x18000bcd8  test    eax, eax
0x18000bcda  jnz     short loc_18000BD13
0x18000bcdc  lea     rcx, [rsp+28h+arg_0]; this
0x18000bce1  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x18000bce6  test    rbx, rbx
0x18000bce9  jz      short loc_18000BD00
0x18000bceb  mov     rdx, [rbx]
0x18000bcee  mov     rcx, rbx
0x18000bcf1  mov     rax, [rdx+88h]
0x18000bcf8  lea     edx, [rdi+1]
0x18000bcfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd00  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bd07  mov     rax, [rcx]
0x18000bd0a  mov     rax, [rax+10h]
0x18000bd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd13  mov     rbx, [rsp+28h+arg_8]
0x18000bd18  mov     eax, edi
0x18000bd1a  add     rsp, 20h
0x18000bd1e  pop     rdi
0x18000bd1f  retn
```
