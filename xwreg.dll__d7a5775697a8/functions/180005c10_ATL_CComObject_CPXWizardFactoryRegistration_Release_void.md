# ATL::CComObject<CPXWizardFactoryRegistration>::Release(void)

- ea: `0x180005c10`
- end: `0x180005c6d`
- name: `?Release@?$CComObject@VCPXWizardFactoryRegistration@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002af0`
- `0x180005c10`
- `0x180005e04`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPXWizardFactoryRegistration>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 88LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180005c10  mov     [rsp+arg_8], rbx
0x180005c15  push    rdi
0x180005c16  sub     rsp, 20h
0x180005c1a  mov     rbx, rcx
0x180005c1d  add     rcx, 8; volatile int *
0x180005c21  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180005c26  mov     edi, eax
0x180005c28  test    eax, eax
0x180005c2a  jnz     short loc_180005C60
0x180005c2c  lea     rcx, [rsp+28h+arg_0]; this
0x180005c31  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180005c36  test    rbx, rbx
0x180005c39  jz      short loc_180005C4D
0x180005c3b  mov     rdx, [rbx]
0x180005c3e  mov     rcx, rbx
0x180005c41  mov     rax, [rdx+58h]
0x180005c45  lea     edx, [rdi+1]
0x180005c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005c54  mov     rax, [rcx]
0x180005c57  mov     rax, [rax+10h]
0x180005c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c60  mov     rbx, [rsp+28h+arg_8]
0x180005c65  mov     eax, edi
0x180005c67  add     rsp, 20h
0x180005c6b  pop     rdi
0x180005c6c  retn
```
