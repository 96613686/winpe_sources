# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180013010`
- end: `0x1800130a1`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(char *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000213c`
- `0x180013010`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013067`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013067`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180013010  mov     [rsp+arg_0], rbx
0x180013015  push    rdi
0x180013016  sub     rsp, 20h
0x18001301a  mov     rbx, rcx
0x18001301d  mov     r8d, 7FFFFFFFh
0x180013023  mov     ecx, [rcx+8]
0x180013026  jmp     short loc_180013037
0x180013028  lea     edx, [rcx-1]
0x18001302b  mov     eax, ecx
0x18001302d  lock cmpxchg [rbx+8], edx
0x180013032  jz      short loc_18001303C
0x180013034  mov     ecx, [rbx+8]
0x180013037  cmp     ecx, r8d
0x18001303a  jnz     short loc_180013028
0x18001303c  lea     edi, [rcx-1]
0x18001303f  test    edi, edi
0x180013041  jnz     short loc_18001307C
0x180013043  test    rbx, rbx
0x180013046  jz      short loc_180013094
0x180013048  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18001304f  mov     dword ptr [rbx+8], 0C0000001h
0x180013056  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001305a  mov     [rbx], rax
0x18001305d  cmp     [rcx+28h], dil
0x180013061  jz      short loc_18001306D
0x180013063  mov     [rcx+28h], dil
0x180013067  call    cs:__imp_DeleteCriticalSection
0x18001306d  mov     edx, 48h ; 'H'
0x180013072  mov     rcx, rbx; Block
0x180013075  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001307a  jmp     short loc_180013094
0x18001307c  cmp     edi, 1
0x18001307f  jnz     short loc_180013094
0x180013081  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180013088  mov     rdx, [rcx]
0x18001308b  mov     rax, [rdx+10h]
0x18001308f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013094  mov     rbx, [rsp+28h+arg_0]
0x180013099  mov     eax, edi
0x18001309b  add     rsp, 20h
0x18001309f  pop     rdi
0x1800130a0  retn
```
