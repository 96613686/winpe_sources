# ATL::CComAggObject<TpmVCardManagerImpl>::Release(void)

- ea: `0x180026ac0`
- end: `0x180026b2a`
- name: `?Release@?$CComAggObject@VTpmVCardManagerImpl@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800257fc`
- `0x180026ac0`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<TpmVCardManagerImpl>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      ATL::ModuleLockHelper::ModuleLockHelper((ATL::ModuleLockHelper *)&v5);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 24LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180026ac0  mov     [rsp+arg_8], rbx
0x180026ac5  push    rdi
0x180026ac6  sub     rsp, 20h
0x180026aca  mov     edi, [rcx+8]
0x180026acd  mov     rbx, rcx
0x180026ad0  cmp     edi, 7FFFFFFFh
0x180026ad6  jnz     short loc_180026ADF
0x180026ad8  mov     edi, 7FFFFFFEh
0x180026add  jmp     short loc_180026B1D
0x180026adf  sub     edi, 1
0x180026ae2  mov     [rcx+8], edi
0x180026ae5  jnz     short loc_180026B1D
0x180026ae7  lea     rcx, [rsp+28h+arg_0]; this
0x180026aec  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180026af1  test    rbx, rbx
0x180026af4  jz      short loc_180026B0A
0x180026af6  mov     rax, [rbx]
0x180026af9  mov     edx, 1
0x180026afe  mov     rcx, rbx
0x180026b01  mov     rax, [rax+18h]
0x180026b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b0a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180026b11  mov     rdx, [rcx]
0x180026b14  mov     rax, [rdx+10h]
0x180026b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b1d  mov     rbx, [rsp+28h+arg_8]
0x180026b22  mov     eax, edi
0x180026b24  add     rsp, 20h
0x180026b28  pop     rdi
0x180026b29  retn
```
