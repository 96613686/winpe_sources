# ATL::CComAggObject<CWLIDFDProv>::~CComAggObject<CWLIDFDProv>(void)

- ea: `0x180005408`
- end: `0x180005443`
- name: `??1?$CComAggObject@VCWLIDFDProv@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005870`

## callees

- `0x18000579c`
- `0x180012010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CWLIDFDProv>::~CComAggObject<CWLIDFDProv>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CWLIDFDProv>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CWLIDFDProv::~CWLIDFDProv((CWLIDFDProv *)(a1 + 24));
}

```

## disassembly

```asm
0x180005408  push    rbx
0x18000540a  sub     rsp, 20h
0x18000540e  mov     dword ptr [rcx+8], 0C0000001h
0x180005415  lea     rax, ??_7?$CComAggObject@VCWLIDFDProv@@@ATL@@6B@; const ATL::CComAggObject<CWLIDFDProv>::`vftable'
0x18000541c  mov     [rcx], rax
0x18000541f  mov     rbx, rcx
0x180005422  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005429  mov     rax, [rcx]
0x18000542c  mov     rax, [rax+10h]
0x180005430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005435  lea     rcx, [rbx+18h]; this
0x180005439  add     rsp, 20h
0x18000543d  pop     rbx
0x18000543e  jmp     ??1CWLIDFDProv@@UEAA@XZ; CWLIDFDProv::~CWLIDFDProv(void)
```
