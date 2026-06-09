# ATL::CComObject<CWdsTransportSession>::CComObject<CWdsTransportSession>(void *)

- ea: `0x180015400`
- end: `0x18001549e`
- name: `??0?$CComObject@VCWdsTransportSession@@@ATL@@QEAA@PEAX@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015530`

## callees

- `0x180020010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18001542b`
- `KERNEL32!InitializeCriticalSection` at `0x18001542b`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportSession>::CComObject<CWdsTransportSession>(__int64 a1)
{
  struct ATL::CAtlModule *v2; // rcx

  *(_DWORD *)(a1 + 8) = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_BYTE *)(a1 + 56) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  v2 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<CWdsTransportSession>::`vftable';
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_DWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x180015400  mov     [rsp+arg_0], rbx
0x180015405  push    rdi
0x180015406  sub     rsp, 20h
0x18001540a  xorps   xmm0, xmm0
0x18001540d  xor     edi, edi
0x18001540f  mov     [rcx+8], edi
0x180015412  xor     eax, eax
0x180015414  movups  xmmword ptr [rcx+10h], xmm0
0x180015418  mov     rbx, rcx
0x18001541b  movups  xmmword ptr [rcx+20h], xmm0
0x18001541f  mov     [rcx+30h], rax
0x180015423  mov     [rcx+38h], dil
0x180015427  add     rcx, 40h ; '@'; lpCriticalSection
0x18001542b  call    cs:__imp_InitializeCriticalSection
0x180015432  nop     dword ptr [rax+rax+00h]
0x180015437  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001543e  lea     rax, ??_7?$CComObject@VCWdsTransportSession@@@ATL@@6B@; const ATL::CComObject<CWdsTransportSession>::`vftable'
0x180015445  mov     [rbx], rax
0x180015448  mov     [rbx+68h], rdi
0x18001544c  mov     [rbx+70h], rdi
0x180015450  mov     [rbx+78h], edi
0x180015453  mov     [rbx+80h], rdi
0x18001545a  mov     [rbx+88h], rdi
0x180015461  mov     [rbx+90h], rdi
0x180015468  mov     [rbx+98h], rdi
0x18001546f  mov     [rbx+0A0h], rdi
0x180015476  mov     [rbx+0A8h], edi
0x18001547c  mov     [rbx+0B0h], rdi
0x180015483  mov     rax, [rcx]
0x180015486  mov     rax, [rax+8]
0x18001548a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001548f  mov     rax, rbx
0x180015492  mov     rbx, [rsp+28h+arg_0]
0x180015497  add     rsp, 20h
0x18001549b  pop     rdi
0x18001549c  retn
```
