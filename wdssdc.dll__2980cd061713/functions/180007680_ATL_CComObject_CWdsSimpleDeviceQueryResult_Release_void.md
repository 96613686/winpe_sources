# ATL::CComObject<CWdsSimpleDeviceQueryResult>::Release(void)

- ea: `0x180007680`
- end: `0x180007702`
- name: `?Release@?$CComObject@VCWdsSimpleDeviceQueryResult@@@ATL@@UEAAKXZ`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180007680`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsSimpleDeviceQueryResult>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180007680  mov     [rsp+arg_0], rbx
0x180007685  push    rdi
0x180007686  sub     rsp, 20h
0x18000768a  mov     r8d, [rcx+8]
0x18000768e  mov     rbx, rcx
0x180007691  mov     ecx, 7FFFFFFFh
0x180007696  jmp     short loc_1800076AA
0x180007698  lea     edx, [r8-1]
0x18000769c  mov     eax, r8d
0x18000769f  lock cmpxchg [rbx+8], edx
0x1800076a4  jz      short loc_1800076AF
0x1800076a6  mov     r8d, [rbx+8]
0x1800076aa  cmp     r8d, ecx
0x1800076ad  jnz     short loc_180007698
0x1800076af  lea     edi, [r8-1]
0x1800076b3  test    edi, edi
0x1800076b5  jnz     short loc_1800076F4
0x1800076b7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800076be  mov     rax, [rcx]
0x1800076c1  mov     rax, [rax+8]
0x1800076c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ca  test    rbx, rbx
0x1800076cd  jz      short loc_1800076E1
0x1800076cf  mov     rax, [rbx]
0x1800076d2  lea     edx, [rdi+1]
0x1800076d5  mov     rcx, rbx
0x1800076d8  mov     rax, [rax+38h]
0x1800076dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076e1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800076e8  mov     rdx, [rcx]
0x1800076eb  mov     rax, [rdx+10h]
0x1800076ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076f4  mov     rbx, [rsp+28h+arg_0]
0x1800076f9  mov     eax, edi
0x1800076fb  add     rsp, 20h
0x1800076ff  pop     rdi
0x180007700  retn
```
