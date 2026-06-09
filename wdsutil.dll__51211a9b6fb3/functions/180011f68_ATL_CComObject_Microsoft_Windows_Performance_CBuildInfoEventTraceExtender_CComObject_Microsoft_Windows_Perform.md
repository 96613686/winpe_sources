# ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>(void)

- ea: `0x180011f68`
- end: `0x180011fd2`
- name: `??1?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012060`

## callees

- `0x180011f68`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable';
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
0x180011f68  push    rbx
0x180011f6a  sub     rsp, 30h
0x180011f6e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180011f77  mov     rbx, rcx
0x180011f7a  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x180011f81  mov     [rcx], rax
0x180011f84  mov     dword ptr [rcx+18h], 0C0000001h
0x180011f8b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011f92  mov     rax, [rcx]
0x180011f95  mov     rax, [rax+10h]
0x180011f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f9e  nop
0x180011f9f  mov     rcx, [rbx+10h]
0x180011fa3  test    rcx, rcx
0x180011fa6  jz      short loc_180011FB5
0x180011fa8  mov     rax, [rcx]
0x180011fab  mov     rax, [rax+10h]
0x180011faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fb4  nop
0x180011fb5  mov     rcx, [rbx+8]
0x180011fb9  test    rcx, rcx
0x180011fbc  jz      short loc_180011FCB
0x180011fbe  mov     rax, [rcx]
0x180011fc1  mov     rax, [rax+10h]
0x180011fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fca  nop
0x180011fcb  add     rsp, 30h
0x180011fcf  pop     rbx
0x180011fd0  retn
```
