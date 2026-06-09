# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180018c2c`
- end: `0x180018d0c`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x18001486c`
- `0x180018c2c`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v6; // rax
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v7; // rbx
  Microsoft::Windows::Performance::CImageIdEventTraceExtender *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = (Microsoft::Windows::Performance::CImageIdEventTraceExtender *)operator new(0x1A8u);
    v7 = v6;
    if ( v6 )
    {
      Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(v6);
      *(_QWORD *)v7 = &ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable';
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
    v5 = (**(__int64 (__fastcall ***)(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(Microsoft::Windows::Performance::CImageIdEventTraceExtender *, __int64))(*(_QWORD *)v7 + 136LL))(
        v7,
        1);
  }
  return v5;
}

```

## disassembly

```asm
0x180018c2c  mov     rax, rsp
0x180018c2f  mov     [rax+18h], r8
0x180018c33  mov     [rax+10h], rdx
0x180018c37  mov     [rax+8], rcx
0x180018c3b  push    rbx
0x180018c3c  push    rsi
0x180018c3d  push    rdi
0x180018c3e  sub     rsp, 30h
0x180018c42  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180018c4a  mov     rdi, r8
0x180018c4d  test    r8, r8
0x180018c50  jnz     short loc_180018C5C
0x180018c52  mov     eax, 80004003h
0x180018c57  jmp     loc_180018D03
0x180018c5c  mov     qword ptr [r8], 0
0x180018c63  mov     esi, 8007000Eh
0x180018c68  mov     [rsp+48h+arg_8], esi
0x180018c6c  mov     [rsp+48h+arg_0], 0
0x180018c75  mov     ecx, 1A8h; Size
0x180018c7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018c7f  mov     rbx, rax
0x180018c82  mov     [rsp+48h+arg_18], rax
0x180018c87  test    rbx, rbx
0x180018c8a  jz      short loc_180018CB2
0x180018c8c  mov     rcx, rax; this
0x180018c8f  call    ??0CImageIdEventTraceExtender@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CImageIdEventTraceExtender::CImageIdEventTraceExtender(void)
0x180018c94  lea     rax, ??_7?$CComObject@VCImageIdEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CImageIdEventTraceExtender>::`vftable'
0x180018c9b  mov     [rbx], rax
0x180018c9e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180018ca5  mov     rax, [rcx]
0x180018ca8  mov     rax, [rax+8]
0x180018cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018cb1  nop
0x180018cb2  mov     [rsp+48h+arg_0], rbx
0x180018cb7  jmp     short loc_180018CC7
0x180018cb9  mov     rdi, [rsp+48h+arg_10]
0x180018cbe  mov     esi, [rsp+48h+arg_8]
0x180018cc2  mov     rbx, [rsp+48h+arg_0]
0x180018cc7  test    rbx, rbx
0x180018cca  jz      short loc_180018D01
0x180018ccc  mov     rax, [rbx]
0x180018ccf  mov     r8, rdi
0x180018cd2  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x180018cd9  mov     rcx, rbx
0x180018cdc  mov     rax, [rax]
0x180018cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ce4  mov     esi, eax
0x180018ce6  test    eax, eax
0x180018ce8  jz      short loc_180018D01
0x180018cea  mov     rdx, [rbx]
0x180018ced  mov     rax, [rdx+88h]
0x180018cf4  mov     edx, 1
0x180018cf9  mov     rcx, rbx
0x180018cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d01  mov     eax, esi
0x180018d03  add     rsp, 30h
0x180018d07  pop     rdi
0x180018d08  pop     rsi
0x180018d09  pop     rbx
0x180018d0a  retn
```
