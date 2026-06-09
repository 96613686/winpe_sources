# ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::Release(void)

- ea: `0x180008750`
- end: `0x1800087c3`
- name: `?Release@?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180008750`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::Release(
        _DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[12];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[12] = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 56LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180008750  mov     [rsp+arg_0], rbx
0x180008755  push    rdi
0x180008756  sub     rsp, 20h
0x18000875a  mov     ebx, [rcx+30h]
0x18000875d  mov     rdi, rcx
0x180008760  cmp     ebx, 7FFFFFFFh
0x180008766  jnz     short loc_18000876F
0x180008768  mov     ebx, 7FFFFFFEh
0x18000876d  jmp     short loc_1800087B6
0x18000876f  sub     ebx, 1
0x180008772  mov     [rcx+30h], ebx
0x180008775  jnz     short loc_1800087B6
0x180008777  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000877e  mov     rax, [rcx]
0x180008781  mov     rax, [rax+8]
0x180008785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000878a  test    rdi, rdi
0x18000878d  jz      short loc_1800087A3
0x18000878f  mov     rax, [rdi]
0x180008792  mov     edx, 1
0x180008797  mov     rcx, rdi
0x18000879a  mov     rax, [rax+38h]
0x18000879e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087a3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800087aa  mov     rdx, [rcx]
0x1800087ad  mov     rax, [rdx+10h]
0x1800087b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087b6  mov     eax, ebx
0x1800087b8  mov     rbx, [rsp+28h+arg_0]
0x1800087bd  add     rsp, 20h
0x1800087c1  pop     rdi
0x1800087c2  retn
```
