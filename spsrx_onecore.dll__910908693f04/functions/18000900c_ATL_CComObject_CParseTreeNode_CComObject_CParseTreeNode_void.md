# ATL::CComObject<CParseTreeNode>::CComObject<CParseTreeNode>(void *)

- ea: `0x18000900c`
- end: `0x180009066`
- name: `??0?$CComObject@VCParseTreeNode@@@ATL@@QEAA@PEAX@Z`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ae6c`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CParseTreeNode>::CComObject<CParseTreeNode>(__int64 a1)
{
  ATL::CAtlModule *v2; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  *(_BYTE *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 68) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_DWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  v2 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<CParseTreeNode>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x18000900c  push    rbx
0x18000900e  sub     rsp, 20h
0x180009012  mov     rbx, rcx
0x180009015  xor     eax, eax
0x180009017  xor     ecx, ecx
0x180009019  xorps   xmm0, xmm0
0x18000901c  mov     [rbx+8], ecx
0x18000901f  movups  xmmword ptr [rbx+10h], xmm0
0x180009023  movups  xmmword ptr [rbx+20h], xmm0
0x180009027  mov     [rbx+30h], rax
0x18000902b  lea     rax, ??_7?$CComObject@VCParseTreeNode@@@ATL@@6B@; const ATL::CComObject<CParseTreeNode>::`vftable'
0x180009032  mov     [rbx+38h], cl
0x180009035  mov     [rbx+40h], cl
0x180009038  mov     [rbx+44h], rcx
0x18000903c  mov     [rbx+50h], rcx
0x180009040  mov     [rbx+58h], ecx
0x180009043  mov     [rbx+60h], rcx
0x180009047  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000904e  mov     [rbx], rax
0x180009051  mov     rax, [rcx]
0x180009054  mov     rax, [rax+8]
0x180009058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000905d  mov     rax, rbx
0x180009060  add     rsp, 20h
0x180009064  pop     rbx
0x180009065  retn
```
