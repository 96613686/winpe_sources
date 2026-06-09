# ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vector deleting destructor'(uint)

- ea: `0x18000a720`
- end: `0x18000a776`
- name: `??_E?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000a720`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a75b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a75b`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000a720  mov     [rsp+arg_0], rbx
0x18000a725  push    rdi
0x18000a726  sub     rsp, 20h
0x18000a72a  mov     dword ptr [rcx+8], 0C0000001h
0x18000a731  lea     rax, ??_7?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable'
0x18000a738  mov     [rcx], rax
0x18000a73b  mov     rdi, rcx
0x18000a73e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a745  mov     ebx, edx
0x18000a747  mov     rax, [rcx]
0x18000a74a  mov     rax, [rax+10h]
0x18000a74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a753  test    bl, 1
0x18000a756  jz      short loc_18000A767
0x18000a758  mov     rcx, rdi
0x18000a75b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a762  nop     dword ptr [rax+rax+00h]
0x18000a767  mov     rbx, [rsp+28h+arg_0]
0x18000a76c  mov     rax, rdi
0x18000a76f  add     rsp, 20h
0x18000a773  pop     rdi
0x18000a774  retn
```
