# ATL::CComObject<CSrDrvWuHelper>::Release(void)

- ea: `0x180009790`
- end: `0x180009811`
- name: `?Release@?$CComObject@VCSrDrvWuHelper@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009790`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSrDrvWuHelper>::Release(volatile signed __int32 *a1)
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
0x180009790  mov     [rsp+arg_0], rbx
0x180009795  push    rdi
0x180009796  sub     rsp, 20h
0x18000979a  mov     r8d, [rcx+8]
0x18000979e  mov     rbx, rcx
0x1800097a1  mov     ecx, 7FFFFFFFh
0x1800097a6  jmp     short loc_1800097BA
0x1800097a8  lea     edx, [r8-1]
0x1800097ac  mov     eax, r8d
0x1800097af  lock cmpxchg [rbx+8], edx
0x1800097b4  jz      short loc_1800097BF
0x1800097b6  mov     r8d, [rbx+8]
0x1800097ba  cmp     r8d, ecx
0x1800097bd  jnz     short loc_1800097A8
0x1800097bf  lea     edi, [r8-1]
0x1800097c3  test    edi, edi
0x1800097c5  jnz     short loc_180009804
0x1800097c7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800097ce  mov     rax, [rcx]
0x1800097d1  mov     rax, [rax+8]
0x1800097d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097da  test    rbx, rbx
0x1800097dd  jz      short loc_1800097F1
0x1800097df  mov     rax, [rbx]
0x1800097e2  lea     edx, [rdi+1]
0x1800097e5  mov     rcx, rbx
0x1800097e8  mov     rax, [rax+38h]
0x1800097ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097f1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800097f8  mov     rdx, [rcx]
0x1800097fb  mov     rax, [rdx+10h]
0x1800097ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009804  mov     rbx, [rsp+28h+arg_0]
0x180009809  mov     eax, edi
0x18000980b  add     rsp, 20h
0x18000980f  pop     rdi
0x180009810  retn
```
