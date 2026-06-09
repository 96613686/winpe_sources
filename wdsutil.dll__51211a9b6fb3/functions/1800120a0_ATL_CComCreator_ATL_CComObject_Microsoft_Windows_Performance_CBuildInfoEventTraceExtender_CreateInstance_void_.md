# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800120a0`
- end: `0x180012190`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `240`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x1800120a0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>>::CreateInstance(
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
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable';
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
0x1800120a0  mov     rax, rsp
0x1800120a3  mov     [rax+18h], r8
0x1800120a7  mov     [rax+10h], rdx
0x1800120ab  mov     [rax+8], rcx
0x1800120af  push    rbx
0x1800120b0  push    rsi
0x1800120b1  push    r14
0x1800120b3  sub     rsp, 30h
0x1800120b7  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800120bf  mov     rsi, r8
0x1800120c2  test    r8, r8
0x1800120c5  jnz     short loc_1800120D1
0x1800120c7  mov     eax, 80004003h
0x1800120cc  jmp     loc_180012186
0x1800120d1  mov     qword ptr [r8], 0
0x1800120d8  mov     r14d, 8007000Eh
0x1800120de  mov     [rsp+48h+arg_8], r14d
0x1800120e3  mov     [rsp+48h+arg_0], 0
0x1800120ec  mov     ecx, 20h ; ' '; Size
0x1800120f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800120f6  mov     rbx, rax
0x1800120f9  test    rbx, rbx
0x1800120fc  jz      short loc_180012132
0x1800120fe  mov     dword ptr [rax+18h], 0
0x180012105  mov     qword ptr [rax+8], 0
0x18001210d  mov     qword ptr [rax+10h], 0
0x180012115  lea     rax, ??_7?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vftable'
0x18001211c  mov     [rbx], rax
0x18001211f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012126  mov     rax, [rcx]
0x180012129  mov     rax, [rax+8]
0x18001212d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012132  mov     [rsp+48h+arg_0], rbx
0x180012137  jmp     short loc_180012148
0x180012139  mov     rsi, [rsp+48h+arg_10]
0x18001213e  mov     r14d, [rsp+48h+arg_8]
0x180012143  mov     rbx, [rsp+48h+arg_0]
0x180012148  test    rbx, rbx
0x18001214b  jz      short loc_180012183
0x18001214d  mov     rax, [rbx]
0x180012150  mov     r8, rsi
0x180012153  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18001215a  mov     rcx, rbx
0x18001215d  mov     rax, [rax]
0x180012160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012165  mov     r14d, eax
0x180012168  test    eax, eax
0x18001216a  jz      short loc_180012183
0x18001216c  mov     rdx, [rbx]
0x18001216f  mov     rax, [rdx+88h]
0x180012176  mov     edx, 1
0x18001217b  mov     rcx, rbx
0x18001217e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012183  mov     eax, r14d
0x180012186  add     rsp, 30h
0x18001218a  pop     r14
0x18001218c  pop     rsi
0x18001218d  pop     rbx
0x18001218e  retn
```
