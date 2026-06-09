# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180021090`
- end: `0x1800211c5`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `309`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x180021090`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>>::CreateInstance(
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
    v6 = operator new(0xB0u);
    v7 = v6;
    if ( v6 )
    {
      v6[6] = 0;
      *((_QWORD *)v6 + 1) = 0;
      *((_QWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 4) = 0;
      *((_QWORD *)v6 + 5) = 0;
      *((_QWORD *)v6 + 6) = 0;
      *((_QWORD *)v6 + 7) = 0;
      *((_QWORD *)v6 + 8) = 0;
      *((_QWORD *)v6 + 9) = 0;
      *((_QWORD *)v6 + 13) = 7;
      *((_QWORD *)v6 + 12) = 0;
      *((_WORD *)v6 + 40) = 0;
      *((_QWORD *)v6 + 17) = 7;
      *((_QWORD *)v6 + 16) = 0;
      *((_WORD *)v6 + 56) = 0;
      *((_BYTE *)v6 + 144) = 0;
      *((_BYTE *)v6 + 152) = 0;
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v7 = 0;
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
0x180021090  mov     rax, rsp
0x180021093  mov     [rax+18h], r8
0x180021097  mov     [rax+10h], rdx
0x18002109b  mov     [rax+8], rcx
0x18002109f  push    rsi
0x1800210a0  push    rdi
0x1800210a1  push    r14
0x1800210a3  sub     rsp, 30h
0x1800210a7  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800210af  mov     [rax+20h], rbx
0x1800210b3  mov     rsi, r8
0x1800210b6  xor     edi, edi
0x1800210b8  test    r8, r8
0x1800210bb  jnz     short loc_1800210C7
0x1800210bd  mov     eax, 80004003h
0x1800210c2  jmp     loc_1800211B6
0x1800210c7  mov     [r8], rdi
0x1800210ca  mov     r14d, 8007000Eh
0x1800210d0  mov     [rsp+48h+arg_8], r14d
0x1800210d5  mov     [rsp+48h+arg_0], rdi
0x1800210da  mov     ecx, 0B0h; Size
0x1800210df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800210e4  mov     rbx, rax
0x1800210e7  test    rax, rax
0x1800210ea  jz      short loc_18002115F
0x1800210ec  mov     [rax+18h], edi
0x1800210ef  mov     [rax+8], rdi
0x1800210f3  mov     [rax+10h], rdi
0x1800210f7  mov     [rax+20h], rdi
0x1800210fb  mov     [rax+28h], rdi
0x1800210ff  mov     [rax+30h], rdi
0x180021103  mov     [rax+38h], rdi
0x180021107  mov     [rax+40h], rdi
0x18002110b  mov     [rax+48h], rdi
0x18002110f  mov     eax, 7
0x180021114  mov     [rbx+68h], rax
0x180021118  mov     [rbx+60h], rdi
0x18002111c  mov     [rbx+50h], di
0x180021120  mov     [rbx+88h], rax
0x180021127  mov     [rbx+80h], rdi
0x18002112e  mov     [rbx+70h], di
0x180021132  mov     [rbx+90h], dil
0x180021139  mov     [rbx+98h], dil
0x180021140  lea     rax, ??_7?$CComObject@VCVolumeMappingEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CVolumeMappingEventTraceExtender>::`vftable'
0x180021147  mov     [rbx], rax
0x18002114a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180021151  mov     rax, [rcx]
0x180021154  mov     rax, [rax+8]
0x180021158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002115d  jmp     short loc_180021162
0x18002115f  mov     rbx, rdi
0x180021162  mov     [rsp+48h+arg_0], rbx
0x180021167  jmp     short loc_180021178
0x180021169  mov     rsi, [rsp+48h+arg_10]
0x18002116e  mov     r14d, [rsp+48h+arg_8]
0x180021173  mov     rbx, [rsp+48h+arg_0]
0x180021178  test    rbx, rbx
0x18002117b  jz      short loc_1800211B3
0x18002117d  mov     rax, [rbx]
0x180021180  mov     r8, rsi
0x180021183  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18002118a  mov     rcx, rbx
0x18002118d  mov     rax, [rax]
0x180021190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021195  mov     r14d, eax
0x180021198  test    eax, eax
0x18002119a  jz      short loc_1800211B3
0x18002119c  mov     rdx, [rbx]
0x18002119f  mov     rax, [rdx+88h]
0x1800211a6  mov     edx, 1
0x1800211ab  mov     rcx, rbx
0x1800211ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211b3  mov     eax, r14d
0x1800211b6  mov     rbx, [rsp+48h+arg_18]
0x1800211bb  add     rsp, 30h
0x1800211bf  pop     r14
0x1800211c1  pop     rdi
0x1800211c2  pop     rsi
0x1800211c3  retn
```
