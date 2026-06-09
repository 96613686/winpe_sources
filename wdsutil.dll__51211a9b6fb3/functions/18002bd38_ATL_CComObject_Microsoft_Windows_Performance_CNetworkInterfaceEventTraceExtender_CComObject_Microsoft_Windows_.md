# ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(void)

- ea: `0x18002bd38`
- end: `0x18002bda2`
- name: `??1?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002bdb0`

## callees

- `0x18002bd38`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable';
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
0x18002bd38  push    rbx
0x18002bd3a  sub     rsp, 30h
0x18002bd3e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002bd47  mov     rbx, rcx
0x18002bd4a  lea     rax, ??_7?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable'
0x18002bd51  mov     [rcx], rax
0x18002bd54  mov     dword ptr [rcx+18h], 0C0000001h
0x18002bd5b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002bd62  mov     rax, [rcx]
0x18002bd65  mov     rax, [rax+10h]
0x18002bd69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd6e  nop
0x18002bd6f  mov     rcx, [rbx+10h]
0x18002bd73  test    rcx, rcx
0x18002bd76  jz      short loc_18002BD85
0x18002bd78  mov     rax, [rcx]
0x18002bd7b  mov     rax, [rax+10h]
0x18002bd7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd84  nop
0x18002bd85  mov     rcx, [rbx+8]
0x18002bd89  test    rcx, rcx
0x18002bd8c  jz      short loc_18002BD9B
0x18002bd8e  mov     rax, [rcx]
0x18002bd91  mov     rax, [rax+10h]
0x18002bd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd9a  nop
0x18002bd9b  add     rsp, 30h
0x18002bd9f  pop     rbx
0x18002bda0  retn
```
