# ATL::CComAggObject<CElevateWlanUi>::Release(void)

- ea: `0x180005190`
- end: `0x180005211`
- name: `?Release@?$CComAggObject@VCElevateWlanUi@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005190`
- `0x18001d010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CElevateWlanUi>::Release(volatile signed __int32 *a1)
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
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x180005190  mov     [rsp+arg_0], rbx
0x180005195  push    rdi
0x180005196  sub     rsp, 20h
0x18000519a  mov     r8d, [rcx+8]
0x18000519e  mov     rbx, rcx
0x1800051a1  mov     ecx, 7FFFFFFFh
0x1800051a6  jmp     short loc_1800051BA
0x1800051a8  lea     edx, [r8-1]
0x1800051ac  mov     eax, r8d
0x1800051af  lock cmpxchg [rbx+8], edx
0x1800051b4  jz      short loc_1800051BF
0x1800051b6  mov     r8d, [rbx+8]
0x1800051ba  cmp     r8d, ecx
0x1800051bd  jnz     short loc_1800051A8
0x1800051bf  lea     edi, [r8-1]
0x1800051c3  test    edi, edi
0x1800051c5  jnz     short loc_180005204
0x1800051c7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800051ce  mov     rax, [rcx]
0x1800051d1  mov     rax, [rax+8]
0x1800051d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051da  test    rbx, rbx
0x1800051dd  jz      short loc_1800051F1
0x1800051df  mov     rax, [rbx]
0x1800051e2  lea     edx, [rdi+1]
0x1800051e5  mov     rcx, rbx
0x1800051e8  mov     rax, [rax+18h]
0x1800051ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800051f8  mov     rdx, [rcx]
0x1800051fb  mov     rax, [rdx+10h]
0x1800051ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005204  mov     rbx, [rsp+28h+arg_0]
0x180005209  mov     eax, edi
0x18000520b  add     rsp, 20h
0x18000520f  pop     rdi
0x180005210  retn
```
