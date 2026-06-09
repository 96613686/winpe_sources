# ATL::CComObject<CWdsTransportServicePolicy>::Release(void)

- ea: `0x18000d920`
- end: `0x18000d981`
- name: `?Release@?$CComObject@VCWdsTransportServicePolicy@@@ATL@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005ea4`
- `0x18000d920`
- `0x180018348`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportServicePolicy>::Release(__int64 a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = CWdsTransportServerComObjectRoot::InternalRelease((CWdsTransportServerComObjectRoot *)(a1 + 8));
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 232LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d920  mov     [rsp+arg_8], rbx
0x18000d925  push    rdi
0x18000d926  sub     rsp, 20h
0x18000d92a  mov     rbx, rcx
0x18000d92d  add     rcx, 8; this
0x18000d931  call    ?InternalRelease@CWdsTransportServerComObjectRoot@@QEAAKXZ; CWdsTransportServerComObjectRoot::InternalRelease(void)
0x18000d936  mov     edi, eax
0x18000d938  test    eax, eax
0x18000d93a  jnz     short loc_18000D973
0x18000d93c  lea     rcx, [rsp+28h+arg_0]; this
0x18000d941  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x18000d946  test    rbx, rbx
0x18000d949  jz      short loc_18000D960
0x18000d94b  mov     rdx, [rbx]
0x18000d94e  mov     rcx, rbx
0x18000d951  mov     rax, [rdx+0E8h]
0x18000d958  lea     edx, [rdi+1]
0x18000d95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d960  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d967  mov     rax, [rcx]
0x18000d96a  mov     rax, [rax+10h]
0x18000d96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d973  mov     rbx, [rsp+28h+arg_8]
0x18000d978  mov     eax, edi
0x18000d97a  add     rsp, 20h
0x18000d97e  pop     rdi
0x18000d97f  retn
```
