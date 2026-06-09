# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180009820`
- end: `0x1800098ac`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `140`
- prototype: `__int64 __fastcall(char *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012d4`
- `0x180009820`
- `0x180016010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009877`
- `KERNEL32!DeleteCriticalSection` at `0x180009877`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *Block)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)Block + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, i - 1, i);
        i = *((_DWORD *)Block + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( Block )
    {
      *((_DWORD *)Block + 2) = -1073741823;
      *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
      if ( Block[56] != (_BYTE)v3 )
      {
        Block[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
      }
      operator delete(Block);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x180009820  mov     [rsp+arg_0], rbx
0x180009825  push    rdi
0x180009826  sub     rsp, 20h
0x18000982a  mov     rbx, rcx
0x18000982d  mov     r8d, 7FFFFFFFh
0x180009833  mov     ecx, [rcx+8]
0x180009836  jmp     short loc_180009847
0x180009838  lea     edx, [rcx-1]
0x18000983b  mov     eax, ecx
0x18000983d  lock cmpxchg [rbx+8], edx
0x180009842  jz      short loc_18000984C
0x180009844  mov     ecx, [rbx+8]
0x180009847  cmp     ecx, r8d
0x18000984a  jnz     short loc_180009838
0x18000984c  lea     edi, [rcx-1]
0x18000984f  test    edi, edi
0x180009851  jnz     short loc_180009887
0x180009853  test    rbx, rbx
0x180009856  jz      short loc_18000989F
0x180009858  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000985f  mov     dword ptr [rbx+8], 0C0000001h
0x180009866  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000986a  mov     [rbx], rax
0x18000986d  cmp     [rcx+28h], dil
0x180009871  jz      short loc_18000987D
0x180009873  mov     [rcx+28h], dil
0x180009877  call    cs:__imp_DeleteCriticalSection
0x18000987d  mov     rcx, rbx; Block
0x180009880  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009885  jmp     short loc_18000989F
0x180009887  cmp     edi, 1
0x18000988a  jnz     short loc_18000989F
0x18000988c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009893  mov     rdx, [rcx]
0x180009896  mov     rax, [rdx+10h]
0x18000989a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000989f  mov     rbx, [rsp+28h+arg_0]
0x1800098a4  mov     eax, edi
0x1800098a6  add     rsp, 20h
0x1800098aa  pop     rdi
0x1800098ab  retn
```
