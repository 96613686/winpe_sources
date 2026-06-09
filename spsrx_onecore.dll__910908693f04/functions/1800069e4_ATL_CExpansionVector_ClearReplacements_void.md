# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800069e4`
- end: `0x180006a7c`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `152`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800058b4`
- `0x180006a90`

## callees

- `0x180001c50`
- `0x1800069e4`
- `0x180006e4c`
- `0x180007f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006a75`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006a75`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // ebx
  void *v4; // rdx
  void *v5; // rdx

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x180006A7BLL);
      }
      v4 = *(void **)(*(_QWORD *)this + 8LL * i);
      if ( v4 )
        CWinHeap::Free((CWinHeap *)&g_heap, v4);
      v5 = *(void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                       this,
                       (unsigned int)i);
      if ( v5 )
        CWinHeap::Free((CWinHeap *)&g_heap, v5);
      v1 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x1800069e4  mov     [rsp+arg_8], rbx
0x1800069e9  mov     [rsp+arg_10], rsi
0x1800069ee  push    rdi
0x1800069ef  sub     rsp, 20h
0x1800069f3  mov     eax, [rcx+10h]
0x1800069f6  mov     rdi, rcx
0x1800069f9  test    eax, eax
0x1800069fb  jle     short loc_180006A4C
0x1800069fd  xor     ebx, ebx
0x1800069ff  test    ebx, ebx
0x180006a01  js      short loc_180006A66
0x180006a03  cmp     ebx, eax
0x180006a05  jge     short loc_180006A66
0x180006a07  mov     rax, [rdi]
0x180006a0a  movsxd  rcx, ebx
0x180006a0d  lea     rsi, [rax+rcx*8]
0x180006a11  mov     rdx, [rsi]; void *
0x180006a14  test    rdx, rdx
0x180006a17  jz      short loc_180006A25
0x180006a19  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180006a20  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180006a25  mov     edx, ebx
0x180006a27  mov     rcx, rdi
0x180006a2a  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180006a2f  mov     rdx, [rax]; void *
0x180006a32  test    rdx, rdx
0x180006a35  jz      short loc_180006A43
0x180006a37  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180006a3e  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180006a43  mov     eax, [rdi+10h]
0x180006a46  inc     ebx
0x180006a48  cmp     ebx, eax
0x180006a4a  jl      short loc_1800069FF
0x180006a4c  mov     rcx, rdi
0x180006a4f  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180006a54  mov     rbx, [rsp+28h+arg_8]
0x180006a59  xor     eax, eax
0x180006a5b  mov     rsi, [rsp+28h+arg_10]
0x180006a60  add     rsp, 20h
0x180006a64  pop     rdi
0x180006a65  retn
0x180006a66  xor     r9d, r9d; lpArguments
0x180006a69  xor     r8d, r8d; nNumberOfArguments
0x180006a6c  mov     ecx, 0C000008Ch; dwExceptionCode
0x180006a71  lea     edx, [r9+1]; dwExceptionFlags
0x180006a75  call    cs:__imp_RaiseException
```
