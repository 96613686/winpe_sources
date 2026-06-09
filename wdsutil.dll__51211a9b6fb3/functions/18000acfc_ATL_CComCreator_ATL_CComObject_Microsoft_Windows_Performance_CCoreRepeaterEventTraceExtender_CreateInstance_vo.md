# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000acfc`
- end: `0x18000adf3`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ee20`

## callees

- `0x180001374`
- `0x18000acfc`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(
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
    v6 = operator new(0x28u);
    v7 = v6;
    if ( v6 )
    {
      v6[6] = 0;
      *((_QWORD *)v6 + 1) = 0;
      *((_QWORD *)v6 + 2) = 0;
      v6[8] = 0;
      *(_QWORD *)v6 = &ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable';
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
0x18000acfc  mov     rax, rsp
0x18000acff  mov     [rax+18h], r8
0x18000ad03  mov     [rax+10h], rdx
0x18000ad07  mov     [rax+8], rcx
0x18000ad0b  push    rbx
0x18000ad0c  push    rsi
0x18000ad0d  push    r14
0x18000ad0f  sub     rsp, 30h
0x18000ad13  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18000ad1b  mov     rsi, r8
0x18000ad1e  test    r8, r8
0x18000ad21  jnz     short loc_18000AD2D
0x18000ad23  mov     eax, 80004003h
0x18000ad28  jmp     loc_18000ADE9
0x18000ad2d  mov     qword ptr [r8], 0
0x18000ad34  mov     r14d, 8007000Eh
0x18000ad3a  mov     [rsp+48h+arg_8], r14d
0x18000ad3f  mov     [rsp+48h+arg_0], 0
0x18000ad48  mov     ecx, 28h ; '('; Size
0x18000ad4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ad52  mov     rbx, rax
0x18000ad55  test    rbx, rbx
0x18000ad58  jz      short loc_18000AD95
0x18000ad5a  mov     dword ptr [rax+18h], 0
0x18000ad61  mov     qword ptr [rax+8], 0
0x18000ad69  mov     qword ptr [rax+10h], 0
0x18000ad71  mov     dword ptr [rax+20h], 0
0x18000ad78  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x18000ad7f  mov     [rbx], rax
0x18000ad82  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ad89  mov     rax, [rcx]
0x18000ad8c  mov     rax, [rax+8]
0x18000ad90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad95  mov     [rsp+48h+arg_0], rbx
0x18000ad9a  jmp     short loc_18000ADAB
0x18000ad9c  mov     rsi, [rsp+48h+arg_10]
0x18000ada1  mov     r14d, [rsp+48h+arg_8]
0x18000ada6  mov     rbx, [rsp+48h+arg_0]
0x18000adab  test    rbx, rbx
0x18000adae  jz      short loc_18000ADE6
0x18000adb0  mov     rax, [rbx]
0x18000adb3  mov     r8, rsi
0x18000adb6  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x18000adbd  mov     rcx, rbx
0x18000adc0  mov     rax, [rax]
0x18000adc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc8  mov     r14d, eax
0x18000adcb  test    eax, eax
0x18000adcd  jz      short loc_18000ADE6
0x18000adcf  mov     rdx, [rbx]
0x18000add2  mov     rax, [rdx+88h]
0x18000add9  mov     edx, 1
0x18000adde  mov     rcx, rbx
0x18000ade1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ade6  mov     eax, r14d
0x18000ade9  add     rsp, 30h
0x18000aded  pop     r14
0x18000adef  pop     rsi
0x18000adf0  pop     rbx
0x18000adf1  retn
```
