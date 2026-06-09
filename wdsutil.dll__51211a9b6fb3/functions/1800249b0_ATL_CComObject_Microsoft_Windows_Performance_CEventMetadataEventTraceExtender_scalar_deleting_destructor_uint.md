# ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x1800249b0`
- end: `0x180024a0e`
- name: `??_G?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `94`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800241bc`
- `0x1800249b0`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800249f3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800249f3`

## pseudocode

```c
Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800249b0  mov     [rsp+arg_0], rbx
0x1800249b5  push    rdi
0x1800249b6  sub     rsp, 20h
0x1800249ba  mov     dword ptr [rcx+18h], 0C0000001h
0x1800249c1  lea     rax, ??_7?$CComObject@VCEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventMetadataEventTraceExtender>::`vftable'
0x1800249c8  mov     [rcx], rax
0x1800249cb  mov     rdi, rcx
0x1800249ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800249d5  mov     ebx, edx
0x1800249d7  mov     rax, [rcx]
0x1800249da  mov     rax, [rax+10h]
0x1800249de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249e3  mov     rcx, rdi; this
0x1800249e6  call    ??1CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::~CEventMetadataEventTraceExtender(void)
0x1800249eb  test    bl, 1
0x1800249ee  jz      short loc_1800249FF
0x1800249f0  mov     rcx, rdi
0x1800249f3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800249fa  nop     dword ptr [rax+rax+00h]
0x1800249ff  mov     rbx, [rsp+28h+arg_0]
0x180024a04  mov     rax, rdi
0x180024a07  add     rsp, 20h
0x180024a0b  pop     rdi
0x180024a0c  retn
```
