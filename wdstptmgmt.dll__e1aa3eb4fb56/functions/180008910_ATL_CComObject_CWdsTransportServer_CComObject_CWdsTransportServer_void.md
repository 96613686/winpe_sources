# ATL::CComObject<CWdsTransportServer>::CComObject<CWdsTransportServer>(void *)

- ea: `0x180008910`
- end: `0x18000899e`
- name: `??0?$CComObject@VCWdsTransportServer@@@ATL@@QEAA@PEAX@Z`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008a30`

## callees

- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180008949`
- `KERNEL32!InitializeCriticalSection` at `0x180008949`
- `WdsCommonLib!??0CWinsockInitializer@@QEAA@XZ` at `0x180008939`
- `WdsCommonLib!??0CWinsockInitializer@@QEAA@XZ` at `0x180008939`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportServer>::CComObject<CWdsTransportServer>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  CWinsockInitializer::CWinsockInitializer((CWinsockInitializer *)(a1 + 64));
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)a1 = &ATL::CComObject<CWdsTransportServer>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return a1;
}

```

## disassembly

```asm
0x180008910  mov     [rsp+arg_0], rcx
0x180008915  push    rbx
0x180008916  sub     rsp, 20h
0x18000891a  mov     rbx, rcx
0x18000891d  and     dword ptr [rcx+8], 0
0x180008921  xorps   xmm0, xmm0
0x180008924  xor     eax, eax
0x180008926  movups  xmmword ptr [rcx+10h], xmm0
0x18000892a  movups  xmmword ptr [rcx+20h], xmm0
0x18000892e  mov     [rcx+30h], rax
0x180008932  mov     [rcx+38h], al
0x180008935  add     rcx, 40h ; '@'
0x180008939  call    cs:__imp_??0CWinsockInitializer@@QEAA@XZ; CWinsockInitializer::CWinsockInitializer(void)
0x180008940  nop     dword ptr [rax+rax+00h]
0x180008945  lea     rcx, [rbx+48h]; lpCriticalSection
0x180008949  call    cs:__imp_InitializeCriticalSection
0x180008950  nop     dword ptr [rax+rax+00h]
0x180008955  and     qword ptr [rbx+70h], 0
0x18000895a  and     qword ptr [rbx+78h], 0
0x18000895f  and     qword ptr [rbx+80h], 0
0x180008967  and     qword ptr [rbx+88h], 0
0x18000896f  and     qword ptr [rbx+90h], 0
0x180008977  lea     rax, ??_7?$CComObject@VCWdsTransportServer@@@ATL@@6B@; const ATL::CComObject<CWdsTransportServer>::`vftable'
0x18000897e  mov     [rbx], rax
0x180008981  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008988  mov     rax, [rcx]
0x18000898b  mov     rax, [rax+8]
0x18000898f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008994  mov     rax, rbx
0x180008997  add     rsp, 20h
0x18000899b  pop     rbx
0x18000899c  retn
```
