# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180003d18`
- end: `0x180003d8d`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002d94`
- `0x180003da0`

## callees

- `0x180003d18`
- `0x18000492c`
- `0x180005db0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180003d40`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003d53`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003d40`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003d53`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003d86`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180003d86`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // ebx
  void **ValueAt; // rax

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x180003D8CLL);
      }
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)i);
      operator delete[](*ValueAt);
      v1 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x180003d18  mov     [rsp+arg_0], rbx
0x180003d1d  push    rdi
0x180003d1e  sub     rsp, 20h
0x180003d22  mov     eax, [rcx+10h]
0x180003d25  mov     rdi, rcx
0x180003d28  test    eax, eax
0x180003d2a  jle     short loc_180003D62
0x180003d2c  xor     ebx, ebx
0x180003d2e  test    ebx, ebx
0x180003d30  js      short loc_180003D77
0x180003d32  cmp     ebx, eax
0x180003d34  jge     short loc_180003D77
0x180003d36  mov     rcx, [rdi]
0x180003d39  movsxd  rax, ebx
0x180003d3c  mov     rcx, [rcx+rax*8]
0x180003d40  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003d46  mov     edx, ebx
0x180003d48  mov     rcx, rdi
0x180003d4b  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180003d50  mov     rcx, [rax]
0x180003d53  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003d59  mov     eax, [rdi+10h]
0x180003d5c  inc     ebx
0x180003d5e  cmp     ebx, eax
0x180003d60  jl      short loc_180003D2E
0x180003d62  mov     rcx, rdi
0x180003d65  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180003d6a  mov     rbx, [rsp+28h+arg_0]
0x180003d6f  xor     eax, eax
0x180003d71  add     rsp, 20h
0x180003d75  pop     rdi
0x180003d76  retn
0x180003d77  xor     r9d, r9d; lpArguments
0x180003d7a  xor     r8d, r8d; nNumberOfArguments
0x180003d7d  mov     ecx, 0C000008Ch; dwExceptionCode
0x180003d82  lea     edx, [r9+1]; dwExceptionFlags
0x180003d86  call    cs:__imp_RaiseException
```
