# ATL::CComObject<CPXWizardRegistration>::Release(void)

- ea: `0x180005c80`
- end: `0x180005cdd`
- name: `?Release@?$CComObject@VCPXWizardRegistration@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002af0`
- `0x180005c80`
- `0x180005e04`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPXWizardRegistration>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 96LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180005c80  mov     [rsp+arg_8], rbx
0x180005c85  push    rdi
0x180005c86  sub     rsp, 20h
0x180005c8a  mov     rbx, rcx
0x180005c8d  add     rcx, 8; volatile int *
0x180005c91  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180005c96  mov     edi, eax
0x180005c98  test    eax, eax
0x180005c9a  jnz     short loc_180005CD0
0x180005c9c  lea     rcx, [rsp+28h+arg_0]; this
0x180005ca1  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180005ca6  test    rbx, rbx
0x180005ca9  jz      short loc_180005CBD
0x180005cab  mov     rdx, [rbx]
0x180005cae  mov     rcx, rbx
0x180005cb1  mov     rax, [rdx+60h]
0x180005cb5  lea     edx, [rdi+1]
0x180005cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cbd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005cc4  mov     rax, [rcx]
0x180005cc7  mov     rax, [rax+10h]
0x180005ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cd0  mov     rbx, [rsp+28h+arg_8]
0x180005cd5  mov     eax, edi
0x180005cd7  add     rsp, 20h
0x180005cdb  pop     rdi
0x180005cdc  retn
```
