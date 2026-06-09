# ATL::CComAggObject<CWLIDFDProv>::Release(void)

- ea: `0x1800082e0`
- end: `0x18000833d`
- name: `?Release@?$CComAggObject@VCWLIDFDProv@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005218`
- `0x1800082e0`
- `0x18000867c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CWLIDFDProv>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x1800082e0  mov     [rsp+arg_8], rbx
0x1800082e5  push    rdi
0x1800082e6  sub     rsp, 20h
0x1800082ea  mov     rbx, rcx
0x1800082ed  add     rcx, 8; volatile int *
0x1800082f1  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800082f6  mov     edi, eax
0x1800082f8  test    eax, eax
0x1800082fa  jnz     short loc_180008330
0x1800082fc  lea     rcx, [rsp+28h+arg_0]; this
0x180008301  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180008306  test    rbx, rbx
0x180008309  jz      short loc_18000831D
0x18000830b  mov     rdx, [rbx]
0x18000830e  mov     rcx, rbx
0x180008311  mov     rax, [rdx+18h]
0x180008315  lea     edx, [rdi+1]
0x180008318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000831d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008324  mov     rax, [rcx]
0x180008327  mov     rax, [rax+10h]
0x18000832b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008330  mov     rbx, [rsp+28h+arg_8]
0x180008335  mov     eax, edi
0x180008337  add     rsp, 20h
0x18000833b  pop     rdi
0x18000833c  retn
```
