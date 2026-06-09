# ATL::CComObject<CContainer>::Release(void)

- ea: `0x1400050d0`
- end: `0x140005151`
- name: `?Release@?$CComObject@VCContainer@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400050d0`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CContainer>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x1400050d0  mov     [rsp+arg_0], rbx
0x1400050d5  push    rdi
0x1400050d6  sub     rsp, 20h
0x1400050da  mov     r8d, [rcx+8]
0x1400050de  mov     rbx, rcx
0x1400050e1  mov     ecx, 7FFFFFFFh
0x1400050e6  jmp     short loc_1400050FA
0x1400050e8  lea     edx, [r8-1]
0x1400050ec  mov     eax, r8d
0x1400050ef  lock cmpxchg [rbx+8], edx
0x1400050f4  jz      short loc_1400050FF
0x1400050f6  mov     r8d, [rbx+8]
0x1400050fa  cmp     r8d, ecx
0x1400050fd  jnz     short loc_1400050E8
0x1400050ff  lea     edi, [r8-1]
0x140005103  test    edi, edi
0x140005105  jnz     short loc_140005144
0x140005107  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000510e  mov     rax, [rcx]
0x140005111  mov     rax, [rax+8]
0x140005115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000511a  test    rbx, rbx
0x14000511d  jz      short loc_140005131
0x14000511f  mov     rax, [rbx]
0x140005122  lea     edx, [rdi+1]
0x140005125  mov     rcx, rbx
0x140005128  mov     rax, [rax+30h]
0x14000512c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005131  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140005138  mov     rdx, [rcx]
0x14000513b  mov     rax, [rdx+10h]
0x14000513f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005144  mov     rbx, [rsp+28h+arg_0]
0x140005149  mov     eax, edi
0x14000514b  add     rsp, 20h
0x14000514f  pop     rdi
0x140005150  retn
```
