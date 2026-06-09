# ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180015dd0`
- end: `0x180015e2e`
- name: `??_G?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `94`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CImageIdEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180015590`
- `0x180015dd0`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180015e13`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015e13`

## pseudocode

```c
Microsoft::Windows::Performance::CImageIdEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CImageIdEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180015dd0  mov     [rsp+arg_0], rbx
0x180015dd5  push    rdi
0x180015dd6  sub     rsp, 20h
0x180015dda  mov     dword ptr [rcx+18h], 0C0000001h
0x180015de1  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x180015de8  mov     [rcx], rax
0x180015deb  mov     rdi, rcx
0x180015dee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180015df5  mov     ebx, edx
0x180015df7  mov     rax, [rcx]
0x180015dfa  mov     rax, [rax+10h]
0x180015dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e03  mov     rcx, rdi; this
0x180015e06  call    ??1CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::~CImageIdEventTraceExtender(void)
0x180015e0b  test    bl, 1
0x180015e0e  jz      short loc_180015E1F
0x180015e10  mov     rcx, rdi
0x180015e13  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015e1a  nop     dword ptr [rax+rax+00h]
0x180015e1f  mov     rbx, [rsp+28h+arg_0]
0x180015e24  mov     rax, rdi
0x180015e27  add     rsp, 20h
0x180015e2b  pop     rdi
0x180015e2c  retn
```
