# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000bff0`
- end: `0x18000c083`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `147`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012c0`
- `0x18000bff0`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000c047`
- `KERNEL32!DeleteCriticalSection` at `0x18000c047`

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
0x18000bff0  mov     [rsp+arg_0], rbx
0x18000bff5  push    rdi
0x18000bff6  sub     rsp, 20h
0x18000bffa  mov     rbx, rcx
0x18000bffd  mov     r8d, 7FFFFFFFh
0x18000c003  mov     ecx, [rcx+8]
0x18000c006  jmp     short loc_18000C017
0x18000c008  lea     edx, [rcx-1]
0x18000c00b  mov     eax, ecx
0x18000c00d  lock cmpxchg [rbx+8], edx
0x18000c012  jz      short loc_18000C01C
0x18000c014  mov     ecx, [rbx+8]
0x18000c017  cmp     ecx, r8d
0x18000c01a  jnz     short loc_18000C008
0x18000c01c  lea     edi, [rcx-1]
0x18000c01f  test    edi, edi
0x18000c021  jnz     short loc_18000C05D
0x18000c023  test    rbx, rbx
0x18000c026  jz      short loc_18000C075
0x18000c028  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000c02f  mov     dword ptr [rbx+8], 0C0000001h
0x18000c036  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000c03a  mov     [rbx], rax
0x18000c03d  cmp     [rcx+28h], dil
0x18000c041  jz      short loc_18000C053
0x18000c043  mov     [rcx+28h], dil
0x18000c047  call    cs:__imp_DeleteCriticalSection
0x18000c04e  nop     dword ptr [rax+rax+00h]
0x18000c053  mov     rcx, rbx; Block
0x18000c056  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c05b  jmp     short loc_18000C075
0x18000c05d  cmp     edi, 1
0x18000c060  jnz     short loc_18000C075
0x18000c062  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c069  mov     rdx, [rcx]
0x18000c06c  mov     rax, [rdx+10h]
0x18000c070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c075  mov     rbx, [rsp+28h+arg_0]
0x18000c07a  mov     eax, edi
0x18000c07c  add     rsp, 20h
0x18000c080  pop     rdi
0x18000c081  retn
```
