# ATL::CComCreator<ATL::CComObject<CXmlContentFilter>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800116b0`
- end: `0x1800117c2`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCXmlContentFilter@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `274`
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
- `0x1800116b0`
- `0x180011aec`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CXmlContentFilter>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  char *v6; // rbx
  int v7; // edi
  char *v10; // [rsp+78h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v6 = (char *)operator new(0x220u);
    CXmlContentFilter::CXmlContentFilter((CXmlContentFilter *)v6);
    *(_QWORD *)v6 = &ATL::CComObject<CXmlContentFilter>::`vftable'{for `IFilter'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CXmlContentFilter>::`vftable'{for `IPersistFile'};
    *((_QWORD *)v6 + 2) = &ATL::CComObject<CXmlContentFilter>::`vftable'{for `IPersistStream'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v10 = v6;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v6 = v10;
  }
  if ( v6 )
  {
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v6 + 32));
    if ( v7 < 0
      || (v6[72] = 1, v7 = CXmlContentFilter::FinalConstruct((CXmlContentFilter *)v6), v7 < 0)
      || (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, v4, v3)) != 0 )
    {
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 64LL))(v6, 1);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800116b0  mov     [rsp+arg_10], r8
0x1800116b5  mov     [rsp+arg_8], rdx
0x1800116ba  mov     [rsp+arg_0], rcx
0x1800116bf  push    rbx
0x1800116c0  push    rsi
0x1800116c1  push    rdi
0x1800116c2  push    r14
0x1800116c4  push    r15
0x1800116c6  sub     rsp, 30h
0x1800116ca  mov     rsi, r8
0x1800116cd  mov     r14, rdx
0x1800116d0  test    r8, r8
0x1800116d3  jnz     short loc_1800116DF
0x1800116d5  mov     eax, 80004003h
0x1800116da  jmp     loc_1800117B6
0x1800116df  mov     qword ptr [r8], 0
0x1800116e6  mov     edi, 8007000Eh
0x1800116eb  mov     dword ptr [rsp+58h+arg_0], edi
0x1800116ef  mov     [rsp+58h+arg_18], 0
0x1800116f8  mov     ecx, 220h; Size
0x1800116fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011702  mov     rbx, rax
0x180011705  mov     [rsp+58h+var_38], rax
0x18001170a  mov     rcx, rax; this
0x18001170d  call    ??0CXmlContentFilter@@QEAA@XZ; CXmlContentFilter::CXmlContentFilter(void)
0x180011712  lea     rax, ??_7?$CComObject@VCXmlContentFilter@@@ATL@@6BIFilter@@@; const ATL::CComObject<CXmlContentFilter>::`vftable'{for `IFilter'}
0x180011719  mov     [rbx], rax
0x18001171c  lea     rax, ??_7?$CComObject@VCXmlContentFilter@@@ATL@@6BIPersistFile@@@; const ATL::CComObject<CXmlContentFilter>::`vftable'{for `IPersistFile'}
0x180011723  mov     [rbx+8], rax
0x180011727  lea     rax, ??_7?$CComObject@VCXmlContentFilter@@@ATL@@6BIPersistStream@@@; const ATL::CComObject<CXmlContentFilter>::`vftable'{for `IPersistStream'}
0x18001172e  mov     [rbx+10h], rax
0x180011732  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011739  mov     rax, [rcx]
0x18001173c  mov     rax, [rax+8]
0x180011740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011745  nop
0x180011746  mov     [rsp+58h+arg_18], rbx
0x18001174b  jmp     short loc_180011760
0x18001174d  mov     rsi, [rsp+58h+arg_10]
0x180011752  mov     r14, [rsp+58h+arg_8]
0x180011757  mov     edi, dword ptr [rsp+58h+arg_0]
0x18001175b  mov     rbx, [rsp+58h+arg_18]
0x180011760  test    rbx, rbx
0x180011763  jz      short loc_1800117B4
0x180011765  lea     rcx, [rbx+20h]; this
0x180011769  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18001176e  mov     edi, eax
0x180011770  test    eax, eax
0x180011772  js      short loc_1800117A0
0x180011774  mov     byte ptr [rbx+48h], 1
0x180011778  mov     rcx, rbx; this
0x18001177b  call    ?FinalConstruct@CXmlContentFilter@@QEAAJXZ; CXmlContentFilter::FinalConstruct(void)
0x180011780  mov     edi, eax
0x180011782  test    eax, eax
0x180011784  js      short loc_1800117A0
0x180011786  mov     rax, [rbx]
0x180011789  mov     r8, rsi
0x18001178c  mov     rdx, r14
0x18001178f  mov     rcx, rbx
0x180011792  mov     rax, [rax]
0x180011795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001179a  mov     edi, eax
0x18001179c  test    eax, eax
0x18001179e  jz      short loc_1800117B4
0x1800117a0  mov     rax, [rbx]
0x1800117a3  mov     edx, 1
0x1800117a8  mov     rcx, rbx
0x1800117ab  mov     rax, [rax+40h]
0x1800117af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117b4  mov     eax, edi
0x1800117b6  add     rsp, 30h
0x1800117ba  pop     r15
0x1800117bc  pop     r14
0x1800117be  pop     rdi
0x1800117bf  pop     rsi
0x1800117c0  pop     rbx
0x1800117c1  retn
```
