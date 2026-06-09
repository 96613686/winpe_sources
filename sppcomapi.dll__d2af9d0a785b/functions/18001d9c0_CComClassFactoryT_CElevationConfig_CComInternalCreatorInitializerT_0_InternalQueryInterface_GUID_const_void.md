# CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>::_InternalQueryInterface(_GUID const &,void * *)

- ea: `0x18001d9c0`
- end: `0x18001da27`
- name: `?_InternalQueryInterface@?$CComClassFactoryT@VCElevationConfig@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003520`
- `0x18001d9c0`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>::_InternalQueryInterface(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // ecx

  if ( !a3 )
  {
    v5 = 2147500035LL;
LABEL_7:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    return v6;
  }
  if ( *a2 != *(_QWORD *)&GUID_00000001_0000_0000_c000_000000000046.Data1
    || a2[1] != *(_QWORD *)GUID_00000001_0000_0000_c000_000000000046.Data4 )
  {
    v5 = 2147500034LL;
    *a3 = 0;
    goto LABEL_7;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v6 = 0;
  *a3 = a1;
  return v6;
}

```

## disassembly

```asm
0x18001d9c0  mov     [rsp+arg_0], rbx
0x18001d9c5  push    rdi
0x18001d9c6  sub     rsp, 20h
0x18001d9ca  mov     rbx, r8
0x18001d9cd  mov     rdi, rcx
0x18001d9d0  test    r8, r8
0x18001d9d3  jnz     short loc_18001D9DC
0x18001d9d5  mov     ecx, 80004003h
0x18001d9da  jmp     short loc_18001DA14
0x18001d9dc  mov     rax, [rdx]
0x18001d9df  cmp     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data1
0x18001d9e6  jnz     short loc_18001DA08
0x18001d9e8  mov     rax, [rdx+8]
0x18001d9ec  cmp     rax, qword ptr cs:_GUID_00000001_0000_0000_c000_000000000046.Data4
0x18001d9f3  jnz     short loc_18001DA08
0x18001d9f5  mov     rax, [rcx]
0x18001d9f8  mov     rax, [rax+8]
0x18001d9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da01  xor     ecx, ecx
0x18001da03  mov     [rbx], rdi
0x18001da06  jmp     short loc_18001DA19
0x18001da08  mov     ecx, 80004002h
0x18001da0d  mov     qword ptr [r8], 0
0x18001da14  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001da19  mov     rbx, [rsp+28h+arg_0]
0x18001da1e  mov     eax, ecx
0x18001da20  add     rsp, 20h
0x18001da24  pop     rdi
0x18001da25  retn
```
