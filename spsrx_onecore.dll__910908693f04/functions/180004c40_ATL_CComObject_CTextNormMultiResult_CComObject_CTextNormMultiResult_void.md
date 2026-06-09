# ATL::CComObject<CTextNormMultiResult>::CComObject<CTextNormMultiResult>(void *)

- ea: `0x180004c40`
- end: `0x180004cb4`
- name: `??0?$CComObject@VCTextNormMultiResult@@@ATL@@QEAA@PEAX@Z`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004dd0`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CTextNormMultiResult>::CComObject<CTextNormMultiResult>(__int64 a1)
{
  ATL::CAtlModule *v2; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  *(_DWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  v2 = ATL::_pAtlModule;
  *(_DWORD *)(a1 + 168) = 10;
  *(_QWORD *)a1 = &ATL::CComObject<CTextNormMultiResult>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x180004c40  push    rbx
0x180004c42  sub     rsp, 20h
0x180004c46  mov     rbx, rcx
0x180004c49  xor     eax, eax
0x180004c4b  xor     ecx, ecx
0x180004c4d  xorps   xmm0, xmm0
0x180004c50  mov     [rbx+8], ecx
0x180004c53  movups  xmmword ptr [rbx+10h], xmm0
0x180004c57  movups  xmmword ptr [rbx+20h], xmm0
0x180004c5b  mov     [rbx+30h], rax
0x180004c5f  lea     rax, ??_7?$CComObject@VCTextNormMultiResult@@@ATL@@6B@; const ATL::CComObject<CTextNormMultiResult>::`vftable'
0x180004c66  mov     [rbx+38h], cl
0x180004c69  mov     [rbx+90h], ecx
0x180004c6f  mov     [rbx+98h], rcx
0x180004c76  mov     [rbx+88h], rcx
0x180004c7d  mov     [rbx+80h], rcx
0x180004c84  mov     [rbx+0A0h], rcx
0x180004c8b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004c92  mov     dword ptr [rbx+0A8h], 0Ah
0x180004c9c  mov     [rbx], rax
0x180004c9f  mov     rax, [rcx]
0x180004ca2  mov     rax, [rax+8]
0x180004ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cab  mov     rax, rbx
0x180004cae  add     rsp, 20h
0x180004cb2  pop     rbx
0x180004cb3  retn
```
