# ATL::CComCreator<ATL::CComAggObject<CXmlContentFilter>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180011574`
- end: `0x1800116a8`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCXmlContentFilter@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `308`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011560`

## callees

- `0x180002148`
- `0x1800060c0`
- `0x18000fb0c`
- `0x180011574`
- `0x180011aec`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CXmlContentFilter>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  _DWORD *v7; // rbx
  int v8; // edi
  _DWORD *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0x238u);
    v7[2] = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<CXmlContentFilter>::`vftable';
    CXmlContentFilter::CXmlContentFilter((CXmlContentFilter *)(v7 + 6));
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CXmlContentFilter>::`vftable'{for `IFilter'};
    *((_QWORD *)v7 + 4) = &ATL::CComContainedObject<CXmlContentFilter>::`vftable'{for `IPersistFile'};
    *((_QWORD *)v7 + 5) = &ATL::CComContainedObject<CXmlContentFilter>::`vftable'{for `IPersistStream'};
    *((_QWORD *)v7 + 6) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 14));
    if ( v8 < 0
      || (*((_BYTE *)v7 + 96) = 1, v8 = CXmlContentFilter::FinalConstruct((CXmlContentFilter *)(v7 + 6)), v8 < 0)
      || (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0 )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180011574  mov     [rsp+arg_0], rbx
0x180011579  mov     [rsp+arg_10], r8
0x18001157e  mov     [rsp+arg_8], rdx
0x180011583  push    rsi
0x180011584  push    rdi
0x180011585  push    r12
0x180011587  push    r14
0x180011589  push    r15
0x18001158b  sub     rsp, 30h
0x18001158f  mov     rsi, r8
0x180011592  mov     r14, rdx
0x180011595  mov     r12, rcx
0x180011598  test    r8, r8
0x18001159b  jnz     short loc_1800115A7
0x18001159d  mov     eax, 80004003h
0x1800115a2  jmp     loc_180011696
0x1800115a7  mov     qword ptr [r8], 0
0x1800115ae  mov     edi, 8007000Eh
0x1800115b3  mov     [rsp+58h+arg_18], edi
0x1800115b7  mov     [rsp+58h+var_38], 0
0x1800115c0  mov     ecx, 238h; Size
0x1800115c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800115ca  mov     rbx, rax
0x1800115cd  mov     [rsp+58h+var_30], rax
0x1800115d2  mov     dword ptr [rax+8], 0
0x1800115d9  lea     rax, ??_7?$CComAggObject@VCXmlContentFilter@@@ATL@@6B@; const ATL::CComAggObject<CXmlContentFilter>::`vftable'
0x1800115e0  mov     [rbx], rax
0x1800115e3  lea     rcx, [rbx+18h]; this
0x1800115e7  call    ??0CXmlContentFilter@@QEAA@XZ; CXmlContentFilter::CXmlContentFilter(void)
0x1800115ec  lea     rax, ??_7?$CComContainedObject@VCXmlContentFilter@@@ATL@@6BIFilter@@@; const ATL::CComContainedObject<CXmlContentFilter>::`vftable'{for `IFilter'}
0x1800115f3  mov     [rbx+18h], rax
0x1800115f7  lea     rax, ??_7?$CComContainedObject@VCXmlContentFilter@@@ATL@@6BIPersistFile@@@; const ATL::CComContainedObject<CXmlContentFilter>::`vftable'{for `IPersistFile'}
0x1800115fe  mov     [rbx+20h], rax
0x180011602  lea     rax, ??_7?$CComContainedObject@VCXmlContentFilter@@@ATL@@6BIPersistStream@@@; const ATL::CComContainedObject<CXmlContentFilter>::`vftable'{for `IPersistStream'}
0x180011609  mov     [rbx+28h], rax
0x18001160d  mov     [rbx+30h], r12
0x180011611  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011618  mov     rax, [rcx]
0x18001161b  mov     rax, [rax+8]
0x18001161f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011624  nop
0x180011625  mov     [rsp+58h+var_38], rbx
0x18001162a  jmp     short loc_18001163F
0x18001162c  mov     rsi, [rsp+58h+arg_10]
0x180011631  mov     r14, [rsp+58h+arg_8]
0x180011636  mov     edi, [rsp+58h+arg_18]
0x18001163a  mov     rbx, [rsp+58h+var_38]
0x18001163f  test    rbx, rbx
0x180011642  jz      short loc_180011694
0x180011644  lea     rcx, [rbx+38h]; this
0x180011648  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18001164d  mov     edi, eax
0x18001164f  test    eax, eax
0x180011651  js      short loc_180011680
0x180011653  mov     byte ptr [rbx+60h], 1
0x180011657  lea     rcx, [rbx+18h]; this
0x18001165b  call    ?FinalConstruct@CXmlContentFilter@@QEAAJXZ; CXmlContentFilter::FinalConstruct(void)
0x180011660  mov     edi, eax
0x180011662  test    eax, eax
0x180011664  js      short loc_180011680
0x180011666  mov     rax, [rbx]
0x180011669  mov     r8, rsi
0x18001166c  mov     rdx, r14
0x18001166f  mov     rcx, rbx
0x180011672  mov     rax, [rax]
0x180011675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001167a  mov     edi, eax
0x18001167c  test    eax, eax
0x18001167e  jz      short loc_180011694
0x180011680  mov     rax, [rbx]
0x180011683  mov     edx, 1
0x180011688  mov     rcx, rbx
0x18001168b  mov     rax, [rax+18h]
0x18001168f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011694  mov     eax, edi
0x180011696  mov     rbx, [rsp+58h+arg_0]
0x18001169b  add     rsp, 30h
0x18001169f  pop     r15
0x1800116a1  pop     r14
0x1800116a3  pop     r12
0x1800116a5  pop     rdi
0x1800116a6  pop     rsi
0x1800116a7  retn
```
