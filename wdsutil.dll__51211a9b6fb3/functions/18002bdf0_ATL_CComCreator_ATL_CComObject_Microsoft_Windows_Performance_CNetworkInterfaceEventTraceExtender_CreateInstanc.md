# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18002bdf0`
- end: `0x18002bee0`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `240`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x18002bdf0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>>::CreateInstance(
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
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable';
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
0x18002bdf0  mov     rax, rsp
0x18002bdf3  mov     [rax+18h], r8
0x18002bdf7  mov     [rax+10h], rdx
0x18002bdfb  mov     [rax+8], rcx
0x18002bdff  push    rbx
0x18002be00  push    rsi
0x18002be01  push    r14
0x18002be03  sub     rsp, 30h
0x18002be07  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18002be0f  mov     rsi, r8
0x18002be12  test    r8, r8
0x18002be15  jnz     short loc_18002BE21
0x18002be17  mov     eax, 80004003h
0x18002be1c  jmp     loc_18002BED6
0x18002be21  mov     qword ptr [r8], 0
0x18002be28  mov     r14d, 8007000Eh
0x18002be2e  mov     [rsp+48h+arg_8], r14d
0x18002be33  mov     [rsp+48h+arg_0], 0
0x18002be3c  mov     ecx, 20h ; ' '; Size
0x18002be41  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002be46  mov     rbx, rax
0x18002be49  test    rbx, rbx
0x18002be4c  jz      short loc_18002BE82
0x18002be4e  mov     dword ptr [rax+18h], 0
0x18002be55  mov     qword ptr [rax+8], 0
0x18002be5d  mov     qword ptr [rax+10h], 0
0x18002be65  lea     rax, ??_7?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vftable'
0x18002be6c  mov     [rbx], rax
0x18002be6f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002be76  mov     rax, [rcx]
0x18002be79  mov     rax, [rax+8]
0x18002be7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be82  mov     [rsp+48h+arg_0], rbx
0x18002be87  jmp     short loc_18002BE98
0x18002be89  mov     rsi, [rsp+48h+arg_10]
0x18002be8e  mov     r14d, [rsp+48h+arg_8]
0x18002be93  mov     rbx, [rsp+48h+arg_0]
0x18002be98  test    rbx, rbx
0x18002be9b  jz      short loc_18002BED3
0x18002be9d  mov     rax, [rbx]
0x18002bea0  mov     r8, rsi
0x18002bea3  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002beaa  mov     rcx, rbx
0x18002bead  mov     rax, [rax]
0x18002beb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002beb5  mov     r14d, eax
0x18002beb8  test    eax, eax
0x18002beba  jz      short loc_18002BED3
0x18002bebc  mov     rdx, [rbx]
0x18002bebf  mov     rax, [rdx+88h]
0x18002bec6  mov     edx, 1
0x18002becb  mov     rcx, rbx
0x18002bece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bed3  mov     eax, r14d
0x18002bed6  add     rsp, 30h
0x18002beda  pop     r14
0x18002bedc  pop     rsi
0x18002bedd  pop     rbx
0x18002bede  retn
```
