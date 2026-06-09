# ATL::CAtlList<CAutoRefPtr<CWLIDItem>,ATL::CElementTraits<CAutoRefPtr<CWLIDItem>>>::RemoveAll(void)

- ea: `0x18000b31c`
- end: `0x18000b382`
- name: `?RemoveAll@?$CAtlList@V?$CAutoRefPtr@VCWLIDItem@@@@V?$CElementTraits@V?$CAutoRefPtr@VCWLIDItem@@@@@ATL@@@ATL@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180009dc0`
- `0x180009f14`
- `0x18000a8a4`
- `0x18000bbf8`

## callees

- `0x180003fac`
- `0x18000a87c`
- `0x18000a8a4`
- `0x18000b31c`

## pseudocode

```c
void __fastcall ATL::CAtlList<CAutoRefPtr<CWLIDItem>,ATL::CElementTraits<CAutoRefPtr<CWLIDItem>>>::RemoveAll(
        __int64 a1)
{
  ATL::CAtlPlex *v2; // rcx

  while ( *(_QWORD *)(a1 + 16) )
  {
    if ( !*(_QWORD *)a1 )
      ATL::AtlThrowImpl(-2147467259);
    *(_QWORD *)a1 = **(_QWORD **)a1;
    ATL::CAtlList<CAutoRefPtr<CWLIDItem>,ATL::CElementTraits<CAutoRefPtr<CWLIDItem>>>::FreeNode(a1);
  }
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v2 = *(ATL::CAtlPlex **)(a1 + 24);
  if ( v2 )
  {
    ATL::CAtlPlex::FreeDataChain(v2);
    *(_QWORD *)(a1 + 24) = 0;
  }
}

```

## disassembly

```asm
0x18000b31c  push    rbx
0x18000b31e  sub     rsp, 20h
0x18000b322  mov     rbx, rcx
0x18000b325  cmp     qword ptr [rbx+10h], 0
0x18000b32a  jbe     short loc_18000B34F
0x18000b32c  mov     rdx, [rbx]
0x18000b32f  test    rdx, rdx
0x18000b332  jz      short loc_18000B344
0x18000b334  mov     rax, [rdx]
0x18000b337  mov     [rbx], rax
0x18000b33a  mov     rcx, rbx
0x18000b33d  call    ?FreeNode@?$CAtlList@V?$CAutoRefPtr@VCWLIDItem@@@@V?$CElementTraits@V?$CAutoRefPtr@VCWLIDItem@@@@@ATL@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<CAutoRefPtr<CWLIDItem>,ATL::CElementTraits<CAutoRefPtr<CWLIDItem>>>::FreeNode(ATL::CAtlList<CAutoRefPtr<CWLIDItem>,ATL::CElementTraits<CAutoRefPtr<CWLIDItem>>>::CNode *)
0x18000b342  jmp     short loc_18000B325
0x18000b344  mov     ecx, 80004005h; int
0x18000b349  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b34f  mov     qword ptr [rbx], 0
0x18000b356  mov     qword ptr [rbx+8], 0
0x18000b35e  mov     qword ptr [rbx+20h], 0
0x18000b366  mov     rcx, [rbx+18h]; this
0x18000b36a  test    rcx, rcx
0x18000b36d  jz      short loc_18000B37C
0x18000b36f  call    ?FreeDataChain@CAtlPlex@ATL@@QEAAXXZ; ATL::CAtlPlex::FreeDataChain(void)
0x18000b374  mov     qword ptr [rbx+18h], 0
0x18000b37c  add     rsp, 20h
0x18000b380  pop     rbx
0x18000b381  retn
```
