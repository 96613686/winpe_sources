# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000adfc`
- end: `0x18000aed2`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f0ac`

## callees

- `0x180001374`
- `0x18000adfc`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rdi
  unsigned int v5; // esi
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  _DWORD *v8; // [rsp+50h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v5 = -2147024882;
    v6 = operator new(0x10u);
    v7 = v6;
    if ( v6 )
    {
      v6[2] = 0;
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable';
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
    v5 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v7)(
           v7,
           &GUID_ad66cb4b_7487_4f77_84cf_cc94f549eb5e,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 32LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18000adfc  mov     rax, rsp
0x18000adff  mov     [rax+18h], r8
0x18000ae03  mov     [rax+10h], rdx
0x18000ae07  mov     [rax+8], rcx
0x18000ae0b  push    rbx
0x18000ae0c  push    rsi
0x18000ae0d  push    rdi
0x18000ae0e  sub     rsp, 30h
0x18000ae12  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18000ae1a  mov     rdi, r8
0x18000ae1d  test    r8, r8
0x18000ae20  jnz     short loc_18000AE2C
0x18000ae22  mov     eax, 80004003h
0x18000ae27  jmp     loc_18000AEC9
0x18000ae2c  mov     qword ptr [r8], 0
0x18000ae33  mov     esi, 8007000Eh
0x18000ae38  mov     [rsp+48h+arg_8], esi
0x18000ae3c  mov     [rsp+48h+arg_0], 0
0x18000ae45  mov     ecx, 10h; Size
0x18000ae4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ae4f  mov     rbx, rax
0x18000ae52  test    rbx, rbx
0x18000ae55  jz      short loc_18000AE7B
0x18000ae57  mov     dword ptr [rax+8], 0
0x18000ae5e  lea     rax, ??_7?$CComObject@VCEventTraceReloggerFactory@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CEventTraceReloggerFactory>::`vftable'
0x18000ae65  mov     [rbx], rax
0x18000ae68  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ae6f  mov     rax, [rcx]
0x18000ae72  mov     rax, [rax+8]
0x18000ae76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae7b  mov     [rsp+48h+arg_0], rbx
0x18000ae80  jmp     short loc_18000AE90
0x18000ae82  mov     rdi, [rsp+48h+arg_10]
0x18000ae87  mov     esi, [rsp+48h+arg_8]
0x18000ae8b  mov     rbx, [rsp+48h+arg_0]
0x18000ae90  test    rbx, rbx
0x18000ae93  jz      short loc_18000AEC7
0x18000ae95  mov     rax, [rbx]
0x18000ae98  mov     r8, rdi
0x18000ae9b  lea     rdx, _GUID_ad66cb4b_7487_4f77_84cf_cc94f549eb5e
0x18000aea2  mov     rcx, rbx
0x18000aea5  mov     rax, [rax]
0x18000aea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aead  mov     esi, eax
0x18000aeaf  test    eax, eax
0x18000aeb1  jz      short loc_18000AEC7
0x18000aeb3  mov     rdx, [rbx]
0x18000aeb6  mov     rax, [rdx+20h]
0x18000aeba  mov     edx, 1
0x18000aebf  mov     rcx, rbx
0x18000aec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec7  mov     eax, esi
0x18000aec9  add     rsp, 30h
0x18000aecd  pop     rdi
0x18000aece  pop     rsi
0x18000aecf  pop     rbx
0x18000aed0  retn
```
