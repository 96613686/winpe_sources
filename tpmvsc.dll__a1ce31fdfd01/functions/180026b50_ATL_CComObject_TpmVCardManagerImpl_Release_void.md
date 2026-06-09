# ATL::CComObject<TpmVCardManagerImpl>::Release(void)

- ea: `0x180026b50`
- end: `0x180026bba`
- name: `?Release@?$CComObject@VTpmVCardManagerImpl@@@ATL@@UEAAKXZ`
- size: `106`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800257fc`
- `0x180026b50`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<TpmVCardManagerImpl>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180026b50  mov     [rsp+arg_8], rbx
0x180026b55  push    rdi
0x180026b56  sub     rsp, 20h
0x180026b5a  mov     edi, [rcx+8]
0x180026b5d  mov     rbx, rcx
0x180026b60  cmp     edi, 7FFFFFFFh
0x180026b66  jnz     short loc_180026B6F
0x180026b68  mov     edi, 7FFFFFFEh
0x180026b6d  jmp     short loc_180026BAD
0x180026b6f  sub     edi, 1
0x180026b72  mov     [rcx+8], edi
0x180026b75  jnz     short loc_180026BAD
0x180026b77  lea     rcx, [rsp+28h+arg_0]; this
0x180026b7c  call    ??0ModuleLockHelper@ATL@@QEAA@XZ; ATL::ModuleLockHelper::ModuleLockHelper(void)
0x180026b81  test    rbx, rbx
0x180026b84  jz      short loc_180026B9A
0x180026b86  mov     rax, [rbx]
0x180026b89  mov     edx, 1
0x180026b8e  mov     rcx, rbx
0x180026b91  mov     rax, [rax+28h]
0x180026b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b9a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180026ba1  mov     rdx, [rcx]
0x180026ba4  mov     rax, [rdx+10h]
0x180026ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bad  mov     rbx, [rsp+28h+arg_8]
0x180026bb2  mov     eax, edi
0x180026bb4  add     rsp, 20h
0x180026bb8  pop     rdi
0x180026bb9  retn
```
