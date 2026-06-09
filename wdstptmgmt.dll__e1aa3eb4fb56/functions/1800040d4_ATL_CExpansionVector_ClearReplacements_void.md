# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800040d4`
- end: `0x180004158`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002bec`
- `0x180004160`

## callees

- `0x1800040d4`
- `0x18000445c`
- `0x18000552c`
- `0x180005c28`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180004100`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004119`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004100`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004119`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, unsigned int a2)
{
  int v2; // eax
  int v3; // ebx
  __int64 v5; // rsi
  void **ValueAt; // rax

  v2 = *((_DWORD *)this + 4);
  v3 = 0;
  if ( v2 > 0 )
  {
    v5 = 0;
    do
    {
      if ( v3 < 0 || v3 >= v2 )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x180004157LL);
      }
      operator delete[](*(void **)(v5 + *(_QWORD *)this));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)v3);
      operator delete[](*ValueAt);
      v2 = *((_DWORD *)this + 4);
      ++v3;
      v5 += 8;
    }
    while ( v3 < v2 );
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x1800040d4  mov     [rsp+arg_0], rbx
0x1800040d9  mov     [rsp+arg_8], rsi
0x1800040de  push    rdi
0x1800040df  sub     rsp, 20h
0x1800040e3  mov     eax, [rcx+10h]
0x1800040e6  xor     ebx, ebx
0x1800040e8  mov     rdi, rcx
0x1800040eb  test    eax, eax
0x1800040ed  jle     short loc_180004132
0x1800040ef  xor     esi, esi
0x1800040f1  test    ebx, ebx
0x1800040f3  js      short loc_18000414D
0x1800040f5  cmp     ebx, eax
0x1800040f7  jge     short loc_18000414D
0x1800040f9  mov     rcx, [rdi]
0x1800040fc  mov     rcx, [rsi+rcx]
0x180004100  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004107  nop     dword ptr [rax+rax+00h]
0x18000410c  mov     edx, ebx
0x18000410e  mov     rcx, rdi
0x180004111  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180004116  mov     rcx, [rax]
0x180004119  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004120  nop     dword ptr [rax+rax+00h]
0x180004125  mov     eax, [rdi+10h]
0x180004128  inc     ebx
0x18000412a  add     rsi, 8
0x18000412e  cmp     ebx, eax
0x180004130  jl      short loc_1800040F1
0x180004132  mov     rcx, rdi
0x180004135  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x18000413a  mov     rbx, [rsp+28h+arg_0]
0x18000413f  xor     eax, eax
0x180004141  mov     rsi, [rsp+28h+arg_8]
0x180004146  add     rsp, 20h
0x18000414a  pop     rdi
0x18000414b  retn
0x18000414d  mov     ecx, 0C000008Ch; unsigned int
0x180004152  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
