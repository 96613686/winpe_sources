# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180012420`
- end: `0x1800124ac`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `140`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001194`
- `0x180012420`
- `0x180015010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180012477`
- `KERNEL32!DeleteCriticalSection` at `0x180012477`

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
0x180012420  mov     [rsp+arg_0], rbx
0x180012425  push    rdi
0x180012426  sub     rsp, 20h
0x18001242a  mov     rbx, rcx
0x18001242d  mov     r8d, 7FFFFFFFh
0x180012433  mov     ecx, [rcx+8]
0x180012436  jmp     short loc_180012447
0x180012438  lea     edx, [rcx-1]
0x18001243b  mov     eax, ecx
0x18001243d  lock cmpxchg [rbx+8], edx
0x180012442  jz      short loc_18001244C
0x180012444  mov     ecx, [rbx+8]
0x180012447  cmp     ecx, r8d
0x18001244a  jnz     short loc_180012438
0x18001244c  lea     edi, [rcx-1]
0x18001244f  test    edi, edi
0x180012451  jnz     short loc_180012487
0x180012453  test    rbx, rbx
0x180012456  jz      short loc_18001249F
0x180012458  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18001245f  mov     dword ptr [rbx+8], 0C0000001h
0x180012466  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001246a  mov     [rbx], rax
0x18001246d  cmp     [rcx+28h], dil
0x180012471  jz      short loc_18001247D
0x180012473  mov     [rcx+28h], dil
0x180012477  call    cs:__imp_DeleteCriticalSection
0x18001247d  mov     rcx, rbx; Block
0x180012480  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012485  jmp     short loc_18001249F
0x180012487  cmp     edi, 1
0x18001248a  jnz     short loc_18001249F
0x18001248c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012493  mov     rdx, [rcx]
0x180012496  mov     rax, [rdx+10h]
0x18001249a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001249f  mov     rbx, [rsp+28h+arg_0]
0x1800124a4  mov     eax, edi
0x1800124a6  add     rsp, 20h
0x1800124aa  pop     rdi
0x1800124ab  retn
```
