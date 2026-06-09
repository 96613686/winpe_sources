# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180005754`
- end: `0x1800057c7`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000358c`
- `0x1800057d0`

## callees

- `0x1800012f4`
- `0x180005754`
- `0x180007e8c`
- `0x18000b8c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800057c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800057c0`

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
        JUMPOUT(0x1800057C6LL);
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
0x180005754  mov     [rsp+arg_0], rbx
0x180005759  push    rdi
0x18000575a  sub     rsp, 20h
0x18000575e  mov     eax, [rcx+10h]
0x180005761  mov     rdi, rcx
0x180005764  test    eax, eax
0x180005766  jle     short loc_18000579C
0x180005768  xor     ebx, ebx
0x18000576a  test    ebx, ebx
0x18000576c  js      short loc_1800057B1
0x18000576e  cmp     ebx, eax
0x180005770  jge     short loc_1800057B1
0x180005772  mov     rcx, [rdi]
0x180005775  movsxd  rax, ebx
0x180005778  mov     rcx, [rcx+rax*8]; Block
0x18000577c  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005781  mov     edx, ebx
0x180005783  mov     rcx, rdi
0x180005786  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000578b  mov     rcx, [rax]; Block
0x18000578e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005793  mov     eax, [rdi+10h]
0x180005796  inc     ebx
0x180005798  cmp     ebx, eax
0x18000579a  jl      short loc_18000576A
0x18000579c  mov     rcx, rdi
0x18000579f  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x1800057a4  mov     rbx, [rsp+28h+arg_0]
0x1800057a9  xor     eax, eax
0x1800057ab  add     rsp, 20h
0x1800057af  pop     rdi
0x1800057b0  retn
0x1800057b1  xor     r9d, r9d; lpArguments
0x1800057b4  xor     r8d, r8d; nNumberOfArguments
0x1800057b7  mov     ecx, 0C000008Ch; dwExceptionCode
0x1800057bc  lea     edx, [r9+1]; dwExceptionFlags
0x1800057c0  call    cs:__imp_RaiseException
```
