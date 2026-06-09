# ATL::CComAggObject<CPXWizardFactoryRegistration>::Release(void)

- ea: `0x180005b80`
- end: `0x180005bdd`
- name: `?Release@?$CComAggObject@VCPXWizardFactoryRegistration@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002af0`
- `0x180005b80`
- `0x180005e04`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPXWizardFactoryRegistration>::Release(volatile int *a1)
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
0x180005b80  mov     [rsp+arg_8], rbx
0x180005b85  push    rdi
0x180005b86  sub     rsp, 20h
0x180005b8a  mov     rbx, rcx
0x180005b8d  add     rcx, 8; volatile int *
0x180005b91  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180005b96  mov     edi, eax
0x180005b98  test    eax, eax
0x180005b9a  jnz     short loc_180005BD0
0x180005b9c  lea     rcx, [rsp+28h+arg_0]; this
0x180005ba1  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180005ba6  test    rbx, rbx
0x180005ba9  jz      short loc_180005BBD
0x180005bab  mov     rdx, [rbx]
0x180005bae  mov     rcx, rbx
0x180005bb1  mov     rax, [rdx+18h]
0x180005bb5  lea     edx, [rdi+1]
0x180005bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bbd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005bc4  mov     rax, [rcx]
0x180005bc7  mov     rax, [rax+10h]
0x180005bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bd0  mov     rbx, [rsp+28h+arg_8]
0x180005bd5  mov     eax, edi
0x180005bd7  add     rsp, 20h
0x180005bdb  pop     rdi
0x180005bdc  retn
```
