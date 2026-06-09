# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800052d0`
- end: `0x18000535d`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800052d0`
- `0x18001d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005330`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005330`
- `KERNEL32!DeleteCriticalSection` at `0x180005327`
- `KERNEL32!DeleteCriticalSection` at `0x180005327`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *a1)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( a1 )
    {
      *((_DWORD *)a1 + 2) = -1073741823;
      *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
      if ( a1[56] != (_BYTE)v3 )
      {
        a1[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      }
      operator delete(a1);
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
0x1800052d0  mov     [rsp+arg_0], rbx
0x1800052d5  push    rdi
0x1800052d6  sub     rsp, 20h
0x1800052da  mov     rbx, rcx
0x1800052dd  mov     r8d, 7FFFFFFFh
0x1800052e3  mov     ecx, [rcx+8]
0x1800052e6  jmp     short loc_1800052F7
0x1800052e8  lea     edx, [rcx-1]
0x1800052eb  mov     eax, ecx
0x1800052ed  lock cmpxchg [rbx+8], edx
0x1800052f2  jz      short loc_1800052FC
0x1800052f4  mov     ecx, [rbx+8]
0x1800052f7  cmp     ecx, r8d
0x1800052fa  jnz     short loc_1800052E8
0x1800052fc  lea     edi, [rcx-1]
0x1800052ff  test    edi, edi
0x180005301  jnz     short loc_180005338
0x180005303  test    rbx, rbx
0x180005306  jz      short loc_180005350
0x180005308  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000530f  mov     dword ptr [rbx+8], 0C0000001h
0x180005316  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000531a  mov     [rbx], rax
0x18000531d  cmp     [rcx+28h], dil
0x180005321  jz      short loc_18000532D
0x180005323  mov     [rcx+28h], dil
0x180005327  call    cs:__imp_DeleteCriticalSection
0x18000532d  mov     rcx, rbx
0x180005330  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005336  jmp     short loc_180005350
0x180005338  cmp     edi, 1
0x18000533b  jnz     short loc_180005350
0x18000533d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005344  mov     rdx, [rcx]
0x180005347  mov     rax, [rdx+10h]
0x18000534b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005350  mov     rbx, [rsp+28h+arg_0]
0x180005355  mov     eax, edi
0x180005357  add     rsp, 20h
0x18000535b  pop     rdi
0x18000535c  retn
```
