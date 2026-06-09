# ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180029dc0`
- end: `0x180029e1e`
- name: `??_G?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `94`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180029d18`
- `0x180029dc0`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180029e03`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029e03`

## pseudocode

```c
Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180029dc0  mov     [rsp+arg_0], rbx
0x180029dc5  push    rdi
0x180029dc6  sub     rsp, 20h
0x180029dca  mov     dword ptr [rcx+18h], 0C0000001h
0x180029dd1  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x180029dd8  mov     [rcx], rax
0x180029ddb  mov     rdi, rcx
0x180029dde  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180029de5  mov     ebx, edx
0x180029de7  mov     rax, [rcx]
0x180029dea  mov     rax, [rax+10h]
0x180029dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029df3  mov     rcx, rdi; this
0x180029df6  call    ??1CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::~CPerfTrackMetadataEventTraceExtender(void)
0x180029dfb  test    bl, 1
0x180029dfe  jz      short loc_180029E0F
0x180029e00  mov     rcx, rdi
0x180029e03  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180029e0a  nop     dword ptr [rax+rax+00h]
0x180029e0f  mov     rbx, [rsp+28h+arg_0]
0x180029e14  mov     rax, rdi
0x180029e17  add     rsp, 20h
0x180029e1b  pop     rdi
0x180029e1c  retn
```
