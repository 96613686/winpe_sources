# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180004f40`
- end: `0x180004fd8`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `152`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800015d4`
- `0x180004f40`
- `0x18000d010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180004f97`
- `KERNEL32!DeleteCriticalSection` at `0x180004f97`

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
0x180004f40  mov     [rsp+arg_0], rbx
0x180004f45  push    rdi
0x180004f46  sub     rsp, 20h
0x180004f4a  mov     rbx, rcx
0x180004f4d  mov     r8d, 7FFFFFFFh
0x180004f53  mov     ecx, [rcx+8]
0x180004f56  jmp     short loc_180004F67
0x180004f58  lea     edx, [rcx-1]
0x180004f5b  mov     eax, ecx
0x180004f5d  lock cmpxchg [rbx+8], edx
0x180004f62  jz      short loc_180004F6C
0x180004f64  mov     ecx, [rbx+8]
0x180004f67  cmp     ecx, r8d
0x180004f6a  jnz     short loc_180004F58
0x180004f6c  lea     edi, [rcx-1]
0x180004f6f  test    edi, edi
0x180004f71  jnz     short loc_180004FB2
0x180004f73  test    rbx, rbx
0x180004f76  jz      short loc_180004FCA
0x180004f78  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004f7f  mov     dword ptr [rbx+8], 0C0000001h
0x180004f86  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004f8a  mov     [rbx], rax
0x180004f8d  cmp     [rcx+28h], dil
0x180004f91  jz      short loc_180004FA3
0x180004f93  mov     [rcx+28h], dil
0x180004f97  call    cs:__imp_DeleteCriticalSection
0x180004f9e  nop     dword ptr [rax+rax+00h]
0x180004fa3  mov     edx, 48h ; 'H'
0x180004fa8  mov     rcx, rbx; Block
0x180004fab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004fb0  jmp     short loc_180004FCA
0x180004fb2  cmp     edi, 1
0x180004fb5  jnz     short loc_180004FCA
0x180004fb7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004fbe  mov     rdx, [rcx]
0x180004fc1  mov     rax, [rdx+10h]
0x180004fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fca  mov     rbx, [rsp+28h+arg_0]
0x180004fcf  mov     eax, edi
0x180004fd1  add     rsp, 20h
0x180004fd5  pop     rdi
0x180004fd6  retn
```
