# ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::Release(void)

- ea: `0x1800127a0`
- end: `0x180012801`
- name: `?Release@?$CComObject@VCWdsTransportNamespaceScheduledCastManualStart@@@ATL@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012810`
- `0x180012830`

## callees

- `0x180005ea4`
- `0x180006654`
- `0x1800127a0`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportNamespaceScheduledCastManualStart>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 256LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x1800127a0  mov     [rsp+arg_8], rbx
0x1800127a5  push    rdi
0x1800127a6  sub     rsp, 20h
0x1800127aa  mov     rbx, rcx
0x1800127ad  add     rcx, 8; volatile int *
0x1800127b1  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800127b6  mov     edi, eax
0x1800127b8  test    eax, eax
0x1800127ba  jnz     short loc_1800127F3
0x1800127bc  lea     rcx, [rsp+28h+arg_0]; this
0x1800127c1  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x1800127c6  test    rbx, rbx
0x1800127c9  jz      short loc_1800127E0
0x1800127cb  mov     rdx, [rbx]
0x1800127ce  mov     rcx, rbx
0x1800127d1  mov     rax, [rdx+100h]
0x1800127d8  lea     edx, [rdi+1]
0x1800127db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127e0  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800127e7  mov     rax, [rcx]
0x1800127ea  mov     rax, [rax+10h]
0x1800127ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127f3  mov     rbx, [rsp+28h+arg_8]
0x1800127f8  mov     eax, edi
0x1800127fa  add     rsp, 20h
0x1800127fe  pop     rdi
0x1800127ff  retn
```
