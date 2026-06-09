# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000aed8`
- end: `0x18000afc8`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `240`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x18000aed8`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  unsigned int v5; // r14d
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
    v6 = operator new(0x20u);
    v7 = v6;
    if ( v6 )
    {
      v6[6] = 0;
      *((_QWORD *)v6 + 1) = 0;
      *((_QWORD *)v6 + 2) = 0;
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable';
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
           &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33,
           v3);
    if ( v5 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 136LL))(v7, 1);
  }
  return v5;
}

```

## disassembly

```asm
0x18000aed8  mov     rax, rsp
0x18000aedb  mov     [rax+18h], r8
0x18000aedf  mov     [rax+10h], rdx
0x18000aee3  mov     [rax+8], rcx
0x18000aee7  push    rbx
0x18000aee8  push    rsi
0x18000aee9  push    r14
0x18000aeeb  sub     rsp, 30h
0x18000aeef  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18000aef7  mov     rsi, r8
0x18000aefa  test    r8, r8
0x18000aefd  jnz     short loc_18000AF09
0x18000aeff  mov     eax, 80004003h
0x18000af04  jmp     loc_18000AFBE
0x18000af09  mov     qword ptr [r8], 0
0x18000af10  mov     r14d, 8007000Eh
0x18000af16  mov     [rsp+48h+arg_8], r14d
0x18000af1b  mov     [rsp+48h+arg_0], 0
0x18000af24  mov     ecx, 20h ; ' '; Size
0x18000af29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000af2e  mov     rbx, rax
0x18000af31  test    rbx, rbx
0x18000af34  jz      short loc_18000AF6A
0x18000af36  mov     dword ptr [rax+18h], 0
0x18000af3d  mov     qword ptr [rax+8], 0
0x18000af45  mov     qword ptr [rax+10h], 0
0x18000af4d  lea     rax, ??_7?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vftable'
0x18000af54  mov     [rbx], rax
0x18000af57  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000af5e  mov     rax, [rcx]
0x18000af61  mov     rax, [rax+8]
0x18000af65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af6a  mov     [rsp+48h+arg_0], rbx
0x18000af6f  jmp     short loc_18000AF80
0x18000af71  mov     rsi, [rsp+48h+arg_10]
0x18000af76  mov     r14d, [rsp+48h+arg_8]
0x18000af7b  mov     rbx, [rsp+48h+arg_0]
0x18000af80  test    rbx, rbx
0x18000af83  jz      short loc_18000AFBB
0x18000af85  mov     rax, [rbx]
0x18000af88  mov     r8, rsi
0x18000af8b  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18000af92  mov     rcx, rbx
0x18000af95  mov     rax, [rax]
0x18000af98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af9d  mov     r14d, eax
0x18000afa0  test    eax, eax
0x18000afa2  jz      short loc_18000AFBB
0x18000afa4  mov     rdx, [rbx]
0x18000afa7  mov     rax, [rdx+88h]
0x18000afae  mov     edx, 1
0x18000afb3  mov     rcx, rbx
0x18000afb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afbb  mov     eax, r14d
0x18000afbe  add     rsp, 30h
0x18000afc2  pop     r14
0x18000afc4  pop     rsi
0x18000afc5  pop     rbx
0x18000afc6  retn
```
