# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180029e24`
- end: `0x180029f04`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x18002990c`
- `0x180029e24`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = (Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *)operator new(0x90u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v8 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v5 = -2147024882;
    v7 = v8;
  }
  if ( v7 )
  {
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *, __int64))(*(_QWORD *)v7 + 136LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x180029e24  mov     rax, rsp
0x180029e27  mov     [rax+18h], r8
0x180029e2b  mov     [rax+10h], rdx
0x180029e2f  mov     [rax+8], rcx
0x180029e33  push    rbx
0x180029e34  push    rsi
0x180029e35  push    rdi
0x180029e36  sub     rsp, 30h
0x180029e3a  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180029e42  mov     rdi, r8
0x180029e45  test    r8, r8
0x180029e48  jnz     short loc_180029E54
0x180029e4a  mov     eax, 80004003h
0x180029e4f  jmp     loc_180029EFB
0x180029e54  mov     qword ptr [r8], 0
0x180029e5b  mov     esi, 8007000Eh
0x180029e60  mov     [rsp+48h+arg_8], esi
0x180029e64  mov     [rsp+48h+arg_0], 0
0x180029e6d  mov     ecx, 90h; Size
0x180029e72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029e77  mov     rbx, rax
0x180029e7a  mov     [rsp+48h+arg_18], rax
0x180029e7f  test    rbx, rbx
0x180029e82  jz      short loc_180029EAA
0x180029e84  mov     rcx, rax; this
0x180029e87  call    ??0CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::CPerfTrackMetadataEventTraceExtender(void)
0x180029e8c  lea     rax, ??_7?$CComObject@VCPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender>::`vftable'
0x180029e93  mov     [rbx], rax
0x180029e96  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180029e9d  mov     rax, [rcx]
0x180029ea0  mov     rax, [rax+8]
0x180029ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ea9  nop
0x180029eaa  mov     [rsp+48h+arg_0], rbx
0x180029eaf  jmp     short loc_180029EBF
0x180029eb1  mov     rdi, [rsp+48h+arg_10]
0x180029eb6  mov     esi, [rsp+48h+arg_8]
0x180029eba  mov     rbx, [rsp+48h+arg_0]
0x180029ebf  test    rbx, rbx
0x180029ec2  jz      short loc_180029EF9
0x180029ec4  mov     rax, [rbx]
0x180029ec7  mov     r8, rdi
0x180029eca  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180029ed1  mov     rcx, rbx
0x180029ed4  mov     rax, [rax]
0x180029ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029edc  mov     esi, eax
0x180029ede  test    eax, eax
0x180029ee0  jz      short loc_180029EF9
0x180029ee2  mov     rdx, [rbx]
0x180029ee5  mov     rax, [rdx+88h]
0x180029eec  mov     edx, 1
0x180029ef1  mov     rcx, rbx
0x180029ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ef9  mov     eax, esi
0x180029efb  add     rsp, 30h
0x180029eff  pop     rdi
0x180029f00  pop     rsi
0x180029f01  pop     rbx
0x180029f02  retn
```
