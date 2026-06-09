# ATL::CComObject<CWLIDFDProv>::Release(void)

- ea: `0x180008370`
- end: `0x1800083cd`
- name: `?Release@?$CComObject@VCWLIDFDProv@@@ATL@@UEAAKXZ`
- size: `93`
- prototype: `__int64 __fastcall(volatile int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005218`
- `0x180008370`
- `0x18000867c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWLIDFDProv>::Release(volatile int *a1)
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
0x180008370  mov     [rsp+arg_8], rbx
0x180008375  push    rdi
0x180008376  sub     rsp, 20h
0x18000837a  mov     rbx, rcx
0x18000837d  add     rcx, 8; volatile int *
0x180008381  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x180008386  mov     edi, eax
0x180008388  test    eax, eax
0x18000838a  jnz     short loc_1800083C0
0x18000838c  lea     rcx, [rsp+28h+arg_0]; this
0x180008391  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180008396  test    rbx, rbx
0x180008399  jz      short loc_1800083AD
0x18000839b  mov     rdx, [rbx]
0x18000839e  mov     rcx, rbx
0x1800083a1  mov     rax, [rdx+58h]
0x1800083a5  lea     edx, [rdi+1]
0x1800083a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083ad  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800083b4  mov     rax, [rcx]
0x1800083b7  mov     rax, [rax+10h]
0x1800083bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083c0  mov     rbx, [rsp+28h+arg_8]
0x1800083c5  mov     eax, edi
0x1800083c7  add     rsp, 20h
0x1800083cb  pop     rdi
0x1800083cc  retn
```
