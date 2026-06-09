# ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::CreateInstance(ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>> * *)

- ea: `0x18000688c`
- end: `0x18000698e`
- name: `?CreateInstance@?$CComObject@V?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@@ATL@@SAJPEAPEAV12@@Z`
- size: `258`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006688`

## callees

- `0x180001264`
- `0x18000688c`
- `0x18000968c`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::CreateInstance(
        _QWORD *a1)
{
  _QWORD *v1; // r14
  unsigned int v3; // esi
  _BYTE *v4; // rax
  _BYTE *v5; // rdi
  int v6; // ecx
  int v7; // eax
  _BYTE *v8; // [rsp+20h] [rbp-28h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  try
  {
    v4 = operator new(0x50u);
    v5 = v4;
    if ( v4 )
    {
      *((_DWORD *)v4 + 2) = 0;
      *((_OWORD *)v4 + 1) = 0;
      *((_OWORD *)v4 + 2) = 0;
      *((_QWORD *)v4 + 6) = 0;
      v4[56] = 0;
      *((_DWORD *)v4 + 18) = 0;
      *(_QWORD *)v4 = &ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    else
    {
      v5 = 0;
    }
    v8 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v8;
  }
  if ( v5 )
  {
    v6 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v5 + 16));
    if ( v6 >= 0 )
      v5[56] = 1;
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    if ( v3 )
    {
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v5 + 56LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x18000688c  mov     [rsp+arg_0], rcx
0x180006891  push    rsi
0x180006892  push    rdi
0x180006893  push    r14
0x180006895  sub     rsp, 30h
0x180006899  mov     r14, rcx
0x18000689c  test    rcx, rcx
0x18000689f  jnz     short loc_1800068AB
0x1800068a1  mov     eax, 80004003h
0x1800068a6  jmp     loc_180006985
0x1800068ab  mov     qword ptr [rcx], 0
0x1800068b2  mov     esi, 8007000Eh
0x1800068b7  mov     [rsp+48h+arg_8], esi
0x1800068bb  mov     [rsp+48h+var_28], 0
0x1800068c4  mov     ecx, 50h ; 'P'; Size
0x1800068c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800068ce  mov     rdi, rax
0x1800068d1  mov     [rsp+48h+arg_10], rax
0x1800068d6  test    rax, rax
0x1800068d9  jz      short loc_180006929
0x1800068db  add     rax, 8
0x1800068df  mov     [rsp+48h+arg_18], rax
0x1800068e4  mov     dword ptr [rax], 0
0x1800068ea  add     rax, 8
0x1800068ee  mov     [rsp+48h+var_20], rax
0x1800068f3  xorps   xmm0, xmm0
0x1800068f6  xor     ecx, ecx
0x1800068f8  movups  xmmword ptr [rax], xmm0
0x1800068fb  movups  xmmword ptr [rax+10h], xmm0
0x1800068ff  mov     [rax+20h], rcx
0x180006903  mov     [rax+28h], cl
0x180006906  mov     [rdi+48h], ecx
0x180006909  lea     rax, ??_7?$CComObject@V?$CSrmSink@VCFciPropertiesShellExt@@$1?_GUID_26942db0_dabf_41d8_bbdd_b129a9f70424@@3U__s_GUID@@B@@@ATL@@6B@; const ATL::CComObject<CSrmSink<CFciPropertiesShellExt,&__s_GUID const _GUID_26942db0_dabf_41d8_bbdd_b129a9f70424>>::`vftable'
0x180006910  mov     [rdi], rax
0x180006913  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000691a  mov     rax, [rcx]
0x18000691d  mov     rax, [rax+8]
0x180006921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006926  nop
0x180006927  jmp     short loc_18000692B
0x180006929  xor     edi, edi
0x18000692b  mov     [rsp+48h+var_28], rdi
0x180006930  jmp     short loc_180006940
0x180006932  mov     r14, [rsp+48h+arg_0]
0x180006937  mov     esi, [rsp+48h+arg_8]
0x18000693b  mov     rdi, [rsp+48h+var_28]
0x180006940  test    rdi, rdi
0x180006943  jz      short loc_180006980
0x180006945  lea     rcx, [rdi+10h]; this
0x180006949  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000694e  mov     ecx, eax
0x180006950  test    eax, eax
0x180006952  js      short loc_180006958
0x180006954  mov     byte ptr [rdi+38h], 1
0x180006958  xor     eax, eax
0x18000695a  test    ecx, ecx
0x18000695c  cmovs   eax, ecx
0x18000695f  xor     esi, esi
0x180006961  test    eax, eax
0x180006963  cmovs   esi, eax
0x180006966  test    esi, esi
0x180006968  jz      short loc_180006980
0x18000696a  mov     rax, [rdi]
0x18000696d  mov     edx, 1
0x180006972  mov     rcx, rdi
0x180006975  mov     rax, [rax+38h]
0x180006979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000697e  xor     edi, edi
0x180006980  mov     [r14], rdi
0x180006983  mov     eax, esi
0x180006985  add     rsp, 30h
0x180006989  pop     r14
0x18000698b  pop     rdi
0x18000698c  pop     rsi
0x18000698d  retn
```
