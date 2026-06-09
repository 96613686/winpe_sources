# ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(void)

- ea: `0x140005160`
- end: `0x1400051d7`
- name: `?Release@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `119`
- prototype: `__int64 __fastcall(char *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001110`
- `0x140005160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400051b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400051b7`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(char *Block)
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
  if ( i == 1 && Block )
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
  return v3;
}

```

## disassembly

```asm
0x140005160  mov     [rsp+arg_0], rbx
0x140005165  push    rdi
0x140005166  sub     rsp, 20h
0x14000516a  mov     rbx, rcx
0x14000516d  mov     r8d, 7FFFFFFFh
0x140005173  mov     ecx, [rcx+8]
0x140005176  jmp     short loc_140005187
0x140005178  lea     edx, [rcx-1]
0x14000517b  mov     eax, ecx
0x14000517d  lock cmpxchg [rbx+8], edx
0x140005182  jz      short loc_14000518C
0x140005184  mov     ecx, [rbx+8]
0x140005187  cmp     ecx, r8d
0x14000518a  jnz     short loc_140005178
0x14000518c  lea     edi, [rcx-1]
0x14000518f  test    edi, edi
0x140005191  jnz     short loc_1400051CA
0x140005193  test    rbx, rbx
0x140005196  jz      short loc_1400051CA
0x140005198  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x14000519f  mov     dword ptr [rbx+8], 0C0000001h
0x1400051a6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1400051aa  mov     [rbx], rax
0x1400051ad  cmp     [rcx+28h], dil
0x1400051b1  jz      short loc_1400051BD
0x1400051b3  mov     [rcx+28h], dil
0x1400051b7  call    cs:__imp_DeleteCriticalSection
0x1400051bd  mov     edx, 48h ; 'H'
0x1400051c2  mov     rcx, rbx; Block
0x1400051c5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400051ca  mov     rbx, [rsp+28h+arg_0]
0x1400051cf  mov     eax, edi
0x1400051d1  add     rsp, 20h
0x1400051d5  pop     rdi
0x1400051d6  retn
```
