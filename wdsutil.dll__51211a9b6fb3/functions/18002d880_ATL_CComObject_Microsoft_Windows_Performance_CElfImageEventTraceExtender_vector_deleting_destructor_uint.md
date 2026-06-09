# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18002d880`
- end: `0x18002d8de`
- name: `??_E?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `94`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CElfImageEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002d644`
- `0x18002d880`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002d8c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002d8c3`

## pseudocode

```c
Microsoft::Windows::Performance::CElfImageEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vector deleting destructor'(
        Microsoft::Windows::Performance::CElfImageEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18002d880  mov     [rsp+arg_0], rbx
0x18002d885  push    rdi
0x18002d886  sub     rsp, 20h
0x18002d88a  mov     dword ptr [rcx+18h], 0C0000001h
0x18002d891  lea     rax, ??_7?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::`vftable'
0x18002d898  mov     [rcx], rax
0x18002d89b  mov     rdi, rcx
0x18002d89e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002d8a5  mov     ebx, edx
0x18002d8a7  mov     rax, [rcx]
0x18002d8aa  mov     rax, [rax+10h]
0x18002d8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8b3  mov     rcx, rdi; this
0x18002d8b6  call    ??1CElfImageEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CElfImageEventTraceExtender::~CElfImageEventTraceExtender(void)
0x18002d8bb  test    bl, 1
0x18002d8be  jz      short loc_18002D8CF
0x18002d8c0  mov     rcx, rdi
0x18002d8c3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002d8ca  nop     dword ptr [rax+rax+00h]
0x18002d8cf  mov     rbx, [rsp+28h+arg_0]
0x18002d8d4  mov     rax, rdi
0x18002d8d7  add     rsp, 20h
0x18002d8db  pop     rdi
0x18002d8dc  retn
```
