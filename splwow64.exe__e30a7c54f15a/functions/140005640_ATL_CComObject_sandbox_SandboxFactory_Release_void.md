# ATL::CComObject<sandbox::SandboxFactory>::Release(void)

- ea: `0x140005640`
- end: `0x1400056c1`
- name: `?Release@?$CComObject@VSandboxFactory@sandbox@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005640`
- `0x140016010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<sandbox::SandboxFactory>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 32LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x140005640  mov     [rsp+arg_0], rbx
0x140005645  push    rdi
0x140005646  sub     rsp, 20h
0x14000564a  mov     r8d, [rcx+8]
0x14000564e  mov     rbx, rcx
0x140005651  mov     ecx, 7FFFFFFFh
0x140005656  jmp     short loc_14000566A
0x140005658  lea     edx, [r8-1]
0x14000565c  mov     eax, r8d
0x14000565f  lock cmpxchg [rbx+8], edx
0x140005664  jz      short loc_14000566F
0x140005666  mov     r8d, [rbx+8]
0x14000566a  cmp     r8d, ecx
0x14000566d  jnz     short loc_140005658
0x14000566f  lea     edi, [r8-1]
0x140005673  test    edi, edi
0x140005675  jnz     short loc_1400056B4
0x140005677  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000567e  mov     rax, [rcx]
0x140005681  mov     rax, [rax+8]
0x140005685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000568a  test    rbx, rbx
0x14000568d  jz      short loc_1400056A1
0x14000568f  mov     rax, [rbx]
0x140005692  lea     edx, [rdi+1]
0x140005695  mov     rcx, rbx
0x140005698  mov     rax, [rax+20h]
0x14000569c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056a1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400056a8  mov     rdx, [rcx]
0x1400056ab  mov     rax, [rdx+10h]
0x1400056af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056b4  mov     rbx, [rsp+28h+arg_0]
0x1400056b9  mov     eax, edi
0x1400056bb  add     rsp, 20h
0x1400056bf  pop     rdi
0x1400056c0  retn
```
