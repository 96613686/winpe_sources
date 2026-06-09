# ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(void)

- ea: `0x18000a1dc`
- end: `0x18000a246`
- name: `??1?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a6e0`

## callees

- `0x18000a1dc`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable';
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
0x18000a1dc  push    rbx
0x18000a1de  sub     rsp, 30h
0x18000a1e2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000a1eb  mov     rbx, rcx
0x18000a1ee  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x18000a1f5  mov     [rcx], rax
0x18000a1f8  mov     dword ptr [rcx+18h], 0C0000001h
0x18000a1ff  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a206  mov     rax, [rcx]
0x18000a209  mov     rax, [rax+10h]
0x18000a20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a212  nop
0x18000a213  mov     rcx, [rbx+10h]
0x18000a217  test    rcx, rcx
0x18000a21a  jz      short loc_18000A229
0x18000a21c  mov     rax, [rcx]
0x18000a21f  mov     rax, [rax+10h]
0x18000a223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a228  nop
0x18000a229  mov     rcx, [rbx+8]
0x18000a22d  test    rcx, rcx
0x18000a230  jz      short loc_18000A23F
0x18000a232  mov     rax, [rcx]
0x18000a235  mov     rax, [rax+10h]
0x18000a239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a23e  nop
0x18000a23f  add     rsp, 30h
0x18000a243  pop     rbx
0x18000a244  retn
```
