# ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(void)

- ea: `0x18000a24c`
- end: `0x18000a2b6`
- name: `??1?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a780`

## callees

- `0x18000a24c`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable';
  *(_DWORD *)(a1 + 24) = -1073741823;
  result = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v3 = *(_QWORD *)(a1 + 16);
  if ( v3 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return result;
}

```

## disassembly

```asm
0x18000a24c  push    rbx
0x18000a24e  sub     rsp, 30h
0x18000a252  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000a25b  mov     rbx, rcx
0x18000a25e  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x18000a265  mov     [rcx], rax
0x18000a268  mov     dword ptr [rcx+18h], 0C0000001h
0x18000a26f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a276  mov     rax, [rcx]
0x18000a279  mov     rax, [rax+10h]
0x18000a27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a282  nop
0x18000a283  mov     rcx, [rbx+10h]
0x18000a287  test    rcx, rcx
0x18000a28a  jz      short loc_18000A299
0x18000a28c  mov     rax, [rcx]
0x18000a28f  mov     rax, [rax+10h]
0x18000a293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a298  nop
0x18000a299  mov     rcx, [rbx+8]
0x18000a29d  test    rcx, rcx
0x18000a2a0  jz      short loc_18000A2AF
0x18000a2a2  mov     rax, [rcx]
0x18000a2a5  mov     rax, [rax+10h]
0x18000a2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2ae  nop
0x18000a2af  add     rsp, 30h
0x18000a2b3  pop     rbx
0x18000a2b4  retn
```
