# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18001e2d0`
- end: `0x18001e32e`
- name: `??_G?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `94`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001df44`
- `0x18001e2d0`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001e313`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e313`

## pseudocode

```c
Microsoft::Windows::Performance::CNGenEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18001e2d0  mov     [rsp+arg_0], rbx
0x18001e2d5  push    rdi
0x18001e2d6  sub     rsp, 20h
0x18001e2da  mov     dword ptr [rcx+18h], 0C0000001h
0x18001e2e1  lea     rax, ??_7?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::`vftable'
0x18001e2e8  mov     [rcx], rax
0x18001e2eb  mov     rdi, rcx
0x18001e2ee  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001e2f5  mov     ebx, edx
0x18001e2f7  mov     rax, [rcx]
0x18001e2fa  mov     rax, [rax+10h]
0x18001e2fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e303  mov     rcx, rdi; this
0x18001e306  call    ??1CNGenEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CNGenEventTraceExtender::~CNGenEventTraceExtender(void)
0x18001e30b  test    bl, 1
0x18001e30e  jz      short loc_18001E31F
0x18001e310  mov     rcx, rdi
0x18001e313  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e31a  nop     dword ptr [rax+rax+00h]
0x18001e31f  mov     rbx, [rsp+28h+arg_0]
0x18001e324  mov     rax, rdi
0x18001e327  add     rsp, 20h
0x18001e32b  pop     rdi
0x18001e32c  retn
```
