# ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(void)

- ea: `0x180020a24`
- end: `0x180020a97`
- name: `??1?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020b00`

## callees

- `0x180015844`
- `0x180020a24`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable';
  *(_DWORD *)(a1 + 24) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase((void **)(a1 + 32));
  v2 = *(_QWORD *)(a1 + 16);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *(_QWORD *)(a1 + 8);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x180020a24  push    rbx
0x180020a26  sub     rsp, 30h
0x180020a2a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180020a33  mov     rbx, rcx
0x180020a36  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x180020a3d  mov     [rcx], rax
0x180020a40  mov     dword ptr [rcx+18h], 0C0000001h
0x180020a47  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180020a4e  mov     rax, [rcx]
0x180020a51  mov     rax, [rax+10h]
0x180020a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a5a  lea     rcx, [rbx+20h]; this
0x180020a5e  call    ??1CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void)
0x180020a63  nop
0x180020a64  mov     rcx, [rbx+10h]
0x180020a68  test    rcx, rcx
0x180020a6b  jz      short loc_180020A7A
0x180020a6d  mov     rax, [rcx]
0x180020a70  mov     rax, [rax+10h]
0x180020a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a79  nop
0x180020a7a  mov     rcx, [rbx+8]
0x180020a7e  test    rcx, rcx
0x180020a81  jz      short loc_180020A90
0x180020a83  mov     rax, [rcx]
0x180020a86  mov     rax, [rax+10h]
0x180020a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a8f  nop
0x180020a90  add     rsp, 30h
0x180020a94  pop     rbx
0x180020a95  retn
```
