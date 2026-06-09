# ATL::CSid::CSid(void)

- ea: `0x140006bd0`
- end: `0x140006c73`
- name: `??0CSid@ATL@@QEAA@XZ`
- size: `163`
- prototype: `__int64 __fastcall(ATL::CSid *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140006d7c`

## callees

- `0x140008010`

## pseudocode

```c
ATL::CSid *__fastcall ATL::CSid::CSid(ATL::CSid *this)
{
  *((_BYTE *)this + 76) = 0;
  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_DWORD *)this + 20) = 7;
  *((_QWORD *)this + 11) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 12) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 13) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  *((_QWORD *)this + 14) = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  return this;
}

```

## disassembly

```asm
0x140006bd0  push    rbx
0x140006bd2  sub     rsp, 20h
0x140006bd6  mov     byte ptr [rcx+4Ch], 0
0x140006bda  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x140006be1  mov     [rcx], rax
0x140006be4  mov     rbx, rcx
0x140006be7  mov     dword ptr [rcx+50h], 7
0x140006bee  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006bf5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006bfc  mov     rax, [rax+18h]
0x140006c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c05  add     rax, 18h
0x140006c09  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006c10  mov     [rbx+58h], rax
0x140006c14  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006c1b  mov     rax, [rax+18h]
0x140006c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c24  add     rax, 18h
0x140006c28  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006c2f  mov     [rbx+60h], rax
0x140006c33  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006c3a  mov     rax, [rax+18h]
0x140006c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c43  add     rax, 18h
0x140006c47  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006c4e  mov     [rbx+68h], rax
0x140006c52  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140006c59  mov     rax, [rax+18h]
0x140006c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c62  add     rax, 18h
0x140006c66  mov     [rbx+70h], rax
0x140006c6a  mov     rax, rbx
0x140006c6d  add     rsp, 20h
0x140006c71  pop     rbx
0x140006c72  retn
```
