# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800269b4`
- end: `0x180026a29`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180024d10`
- `0x180024d54`
- `0x180026a30`

## callees

- `0x1800269b4`
- `0x18002838c`
- `0x18002b150`

## import_xrefs

- `msvcrt!free` at `0x1800269dc`
- `msvcrt!free` at `0x1800269ef`
- `msvcrt!free` at `0x1800269dc`
- `msvcrt!free` at `0x1800269ef`
- `KERNEL32!RaiseException` at `0x180026a22`
- `KERNEL32!RaiseException` at `0x180026a22`

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
        JUMPOUT(0x180026A28LL);
      }
      free(*(void **)(*(_QWORD *)this + 8LL * i));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)i);
      free(*ValueAt);
      v1 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x1800269b4  mov     [rsp+arg_0], rbx
0x1800269b9  push    rdi
0x1800269ba  sub     rsp, 20h
0x1800269be  mov     eax, [rcx+10h]
0x1800269c1  mov     rdi, rcx
0x1800269c4  test    eax, eax
0x1800269c6  jle     short loc_1800269FE
0x1800269c8  xor     ebx, ebx
0x1800269ca  test    ebx, ebx
0x1800269cc  js      short loc_180026A13
0x1800269ce  cmp     ebx, eax
0x1800269d0  jge     short loc_180026A13
0x1800269d2  mov     rcx, [rdi]
0x1800269d5  movsxd  rax, ebx
0x1800269d8  mov     rcx, [rcx+rax*8]; Block
0x1800269dc  call    cs:__imp_free
0x1800269e2  mov     edx, ebx
0x1800269e4  mov     rcx, rdi
0x1800269e7  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1800269ec  mov     rcx, [rax]; Block
0x1800269ef  call    cs:__imp_free
0x1800269f5  mov     eax, [rdi+10h]
0x1800269f8  inc     ebx
0x1800269fa  cmp     ebx, eax
0x1800269fc  jl      short loc_1800269CA
0x1800269fe  mov     rcx, rdi
0x180026a01  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180026a06  mov     rbx, [rsp+28h+arg_0]
0x180026a0b  xor     eax, eax
0x180026a0d  add     rsp, 20h
0x180026a11  pop     rdi
0x180026a12  retn
0x180026a13  xor     r9d, r9d; lpArguments
0x180026a16  xor     r8d, r8d; nNumberOfArguments
0x180026a19  mov     ecx, 0C000008Ch; dwExceptionCode
0x180026a1e  lea     edx, [r9+1]; dwExceptionFlags
0x180026a22  call    cs:__imp_RaiseException
```
