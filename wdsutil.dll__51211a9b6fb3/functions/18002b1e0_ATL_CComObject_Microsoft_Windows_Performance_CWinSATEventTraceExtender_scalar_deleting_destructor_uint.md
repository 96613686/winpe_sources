# ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18002b1e0`
- end: `0x18002b23e`
- name: `??_G?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `94`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002b140`
- `0x18002b1e0`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002b223`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b223`

## pseudocode

```c
Microsoft::Windows::Performance::CWinSATEventTraceExtender *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`scalar deleting destructor'(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        char a2)
{
  *((_DWORD *)this + 6) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CWinSATEventTraceExtender::~CWinSATEventTraceExtender(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18002b1e0  mov     [rsp+arg_0], rbx
0x18002b1e5  push    rdi
0x18002b1e6  sub     rsp, 20h
0x18002b1ea  mov     dword ptr [rcx+18h], 0C0000001h
0x18002b1f1  lea     rax, ??_7?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`vftable'
0x18002b1f8  mov     [rcx], rax
0x18002b1fb  mov     rdi, rcx
0x18002b1fe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002b205  mov     ebx, edx
0x18002b207  mov     rax, [rcx]
0x18002b20a  mov     rax, [rax+10h]
0x18002b20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b213  mov     rcx, rdi; this
0x18002b216  call    ??1CWinSATEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CWinSATEventTraceExtender::~CWinSATEventTraceExtender(void)
0x18002b21b  test    bl, 1
0x18002b21e  jz      short loc_18002B22F
0x18002b220  mov     rcx, rdi
0x18002b223  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b22a  nop     dword ptr [rax+rax+00h]
0x18002b22f  mov     rbx, [rsp+28h+arg_0]
0x18002b234  mov     rax, rdi
0x18002b237  add     rsp, 20h
0x18002b23b  pop     rdi
0x18002b23c  retn
```
