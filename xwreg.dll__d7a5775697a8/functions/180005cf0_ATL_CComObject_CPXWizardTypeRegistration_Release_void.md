# ATL::CComObject<CPXWizardTypeRegistration>::Release(void)

- ea: `0x180005cf0`
- end: `0x180005d4d`
- name: `?Release@?$CComObject@VCPXWizardTypeRegistration@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002af0`
- `0x180005cf0`
- `0x180005e04`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPXWizardTypeRegistration>::Release(volatile int *a1)
{
  unsigned int v2; // edi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 2);
  if ( !v2 )
  {
    ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v4);
    if ( a1 )
      (*(void (__fastcall **)(volatile int *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v2 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v2;
}

```

## disassembly

```asm
0x180005cf0  mov     [rsp+arg_8], rbx
0x180005cf5  push    rdi
0x180005cf6  sub     rsp, 20h
0x180005cfa  mov     rbx, rcx
0x180005cfd  add     rcx, 8; volatile int *
0x180005d01  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180005d06  mov     edi, eax
0x180005d08  test    eax, eax
0x180005d0a  jnz     short loc_180005D40
0x180005d0c  lea     rcx, [rsp+28h+arg_0]; this
0x180005d11  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180005d16  test    rbx, rbx
0x180005d19  jz      short loc_180005D2D
0x180005d1b  mov     rdx, [rbx]
0x180005d1e  mov     rcx, rbx
0x180005d21  mov     rax, [rdx+28h]
0x180005d25  lea     edx, [rdi+1]
0x180005d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d2d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005d34  mov     rax, [rcx]
0x180005d37  mov     rax, [rax+10h]
0x180005d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d40  mov     rbx, [rsp+28h+arg_8]
0x180005d45  mov     eax, edi
0x180005d47  add     rsp, 20h
0x180005d4b  pop     rdi
0x180005d4c  retn
```
