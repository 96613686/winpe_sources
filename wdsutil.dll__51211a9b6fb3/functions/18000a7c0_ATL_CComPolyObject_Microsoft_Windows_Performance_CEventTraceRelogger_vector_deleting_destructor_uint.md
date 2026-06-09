# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(uint)

- ea: `0x18000a7c0`
- end: `0x18000a81f`
- name: `??_E?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a508`
- `0x18000a7c0`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a804`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a804`

## pseudocode

```c
_DWORD *__fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger((Microsoft::Windows::Performance::CEventTraceRelogger *)(a1 + 4));
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a7c0  mov     [rsp+arg_0], rbx
0x18000a7c5  push    rdi
0x18000a7c6  sub     rsp, 20h
0x18000a7ca  mov     dword ptr [rcx+8], 0C0000001h
0x18000a7d1  lea     rax, ??_7?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::`vftable'
0x18000a7d8  mov     [rcx], rax
0x18000a7db  mov     rdi, rcx
0x18000a7de  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a7e5  mov     ebx, edx
0x18000a7e7  mov     rax, [rcx]
0x18000a7ea  mov     rax, [rax+10h]
0x18000a7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7f3  lea     rcx, [rdi+10h]; this
0x18000a7f7  call    ??1CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CEventTraceRelogger::~CEventTraceRelogger(void)
0x18000a7fc  test    bl, 1
0x18000a7ff  jz      short loc_18000A810
0x18000a801  mov     rcx, rdi
0x18000a804  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a80b  nop     dword ptr [rax+rax+00h]
0x18000a810  mov     rbx, [rsp+28h+arg_0]
0x18000a815  mov     rax, rdi
0x18000a818  add     rsp, 20h
0x18000a81c  pop     rdi
0x18000a81d  retn
```
