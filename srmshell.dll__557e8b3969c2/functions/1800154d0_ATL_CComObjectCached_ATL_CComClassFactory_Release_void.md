# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800154d0`
- end: `0x180015577`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800154d0`
- `0x180020010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001554a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001554a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015541`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015541`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(_QWORD *a1)
{
  _QWORD *v2; // r8
  signed __int32 v3; // ecx
  unsigned __int32 v4; // edi

  v2 = a1 + 1;
  do
    v3 = *(_DWORD *)v2;
  while ( *(_DWORD *)v2 != 0x7FFFFFFF && v3 != _InterlockedCompareExchange((volatile signed __int32 *)v2, v3 - 1, v3) );
  v4 = v3 - 1;
  if ( v3 == 1 )
  {
    if ( a1 )
    {
      *a1 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
      *(_DWORD *)v2 = -1073741823;
      *a1 = &ATL::CComClassFactory::`vftable';
      if ( *((_BYTE *)v2 + 48) != (_BYTE)v4 )
      {
        *((_BYTE *)v2 + 48) = v4;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 1));
      }
      operator delete(a1);
    }
  }
  else if ( v3 == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, _QWORD *, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      v2,
      0x7FFFFFFF);
  }
  return v4;
}

```

## disassembly

```asm
0x1800154d0  mov     [rsp+arg_10], rbx
0x1800154d5  push    rdi
0x1800154d6  sub     rsp, 20h
0x1800154da  mov     rbx, rcx
0x1800154dd  lea     r8, [rcx+8]
0x1800154e1  mov     r9d, 7FFFFFFFh
0x1800154e7  jmp     short loc_1800154F5
0x1800154e9  lea     edx, [rcx-1]
0x1800154ec  mov     eax, ecx
0x1800154ee  lock cmpxchg [r8], edx
0x1800154f3  jz      short loc_1800154FD
0x1800154f5  mov     ecx, [r8]
0x1800154f8  cmp     ecx, r9d
0x1800154fb  jnz     short loc_1800154E9
0x1800154fd  lea     edi, [rcx-1]
0x180015500  test    edi, edi
0x180015502  jnz     short loc_180015552
0x180015504  mov     [rsp+28h+arg_0], rbx
0x180015509  test    rbx, rbx
0x18001550c  jz      short loc_18001556A
0x18001550e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180015515  mov     [rbx], rax
0x180015518  mov     dword ptr [r8], 0C0000001h
0x18001551f  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180015526  mov     [rbx], rax
0x180015529  mov     [rsp+28h+arg_0], r8
0x18001552e  lea     rcx, [r8+8]; lpCriticalSection
0x180015532  mov     [rsp+28h+arg_8], rcx
0x180015537  cmp     [rcx+28h], dil
0x18001553b  jz      short loc_180015547
0x18001553d  mov     [rcx+28h], dil
0x180015541  call    cs:__imp_DeleteCriticalSection
0x180015547  mov     rcx, rbx
0x18001554a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015550  jmp     short loc_18001556A
0x180015552  cmp     edi, 1
0x180015555  jnz     short loc_18001556A
0x180015557  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001555e  mov     rdx, [rcx]
0x180015561  mov     rax, [rdx+10h]
0x180015565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001556a  mov     eax, edi
0x18001556c  mov     rbx, [rsp+28h+arg_10]
0x180015571  add     rsp, 20h
0x180015575  pop     rdi
0x180015576  retn
```
