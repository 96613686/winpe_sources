# ITsBus::CreateInstance(ITsBus::ETSBusType)

- ea: `0x180041c54`
- end: `0x180041fcf`
- name: `?CreateInstance@ITsBus@@SA?AV?$shared_ptr@VITsBus@@@utl@@W4ETSBusType@1@@Z`
- size: `891`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f088`
- `0x180031890`
- `0x180034da0`

## callees

- `0x18000b8f8`
- `0x18000bd04`
- `0x18000d5f0`
- `0x18000f75c`
- `0x180017e48`
- `0x180030e48`
- `0x180041c30`
- `0x180041c54`
- `0x180042284`
- `0x1800460a8`
- `0x180047ebe`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041d1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041d1b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041e05`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041e05`

## string_xrefs

- `0x180041ce7`: `CreateUMBusBus`

## pseudocode

```c
_QWORD *__fastcall ITsBus::CreateInstance(_QWORD *a1, unsigned int a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LSTATUS ValueW; // eax
  signed int v6; // ebx
  __int64 v7; // rax
  unsigned int v8; // eax
  unsigned int v9; // eax
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // eax
  _QWORD *v15; // rax
  _QWORD *v16; // rbx
  _DWORD *v17; // rax
  utl::_RefCountBase *v18; // rcx
  _DWORD *v19; // rax
  utl::_RefCountBase *v20; // rcx
  _DWORD *v22; // [rsp+40h] [rbp-20h] BYREF
  _QWORD *p_pvData; // [rsp+48h] [rbp-18h]
  _QWORD *pvData; // [rsp+90h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+40h] BYREF

  *a1 = 0;
  a1[1] = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableSWDForRedirections>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnableSWDForRedirections>::GetImpl'::`2'::impl) )
    goto LABEL_14;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      10,
      WPP_ca718917dae2357c6cf8e20d0a589916_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  LODWORD(pvData) = 0;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server",
             L"CreateUMBusBus",
             0x10u,
             0,
             &pvData,
             &pcbData);
  v6 = ValueW;
  if ( ValueW > 0 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
  if ( v6 >= 0 )
  {
    if ( (_DWORD)pvData )
    {
      v7 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_19:
        v10 = operator new(0x1E0u);
        v11 = v10;
        if ( v10 )
        {
          CTsBusBase::CTsBusBase(v10, a2);
          *v11 = &CTsBusUMBus::`vftable';
          v11[57] = 0;
          v11[58] = 0;
          *((_BYTE *)v11 + 472) = 0;
          if ( CoInitializeEx(0, 0) >= 0 )
            *((_BYTE *)v11 + 472) = 1;
        }
        else
        {
          v11 = 0;
        }
        pvData = v11;
        p_pvData = &pvData;
        v19 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        v22 = v19;
        if ( v19 )
        {
          v19[2] = 1;
          v19[3] = 1;
          *(_QWORD *)v19 = &utl::_RefCountVtable<utl::_RefCountNormal<CTsDeviceUMBus *,utl::default_delete<CTsDeviceUMBus>,utl::allocator<int>>,0>::`vftable';
          *((_QWORD *)v19 + 2) = pvData;
          v20 = (utl::_RefCountBase *)a1[1];
          *a1 = pvData;
          a1[1] = v19;
          if ( v20 )
            utl::_RefCountBase::_DecStrong(v20);
        }
        goto LABEL_42;
      }
      if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 4u )
      {
LABEL_15:
        if ( (unsigned int *)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 1) != 0 && *(_BYTE *)(v7 + 25) >= 4u )
        {
          v9 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_D(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            14,
            WPP_ca718917dae2357c6cf8e20d0a589916_Traceguids,
            v9);
        }
        goto LABEL_19;
      }
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        12,
        WPP_ca718917dae2357c6cf8e20d0a589916_Traceguids,
        v8);
LABEL_14:
      v7 = *(_QWORD *)&WPP_GLOBAL_Control;
      goto LABEL_15;
    }
    goto LABEL_26;
  }
  v12 = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) == 0
      || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 4u )
    {
LABEL_27:
      if ( (unsigned int *)v12 != &WPP_GLOBAL_Control && (*(_BYTE *)(v12 + 28) & 1) != 0 && *(_BYTE *)(v12 + 25) >= 4u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          13,
          WPP_ca718917dae2357c6cf8e20d0a589916_Traceguids,
          v14);
      }
      goto LABEL_31;
    }
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DSD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      11,
      (unsigned int)WPP_ca718917dae2357c6cf8e20d0a589916_Traceguids,
      v13,
      (__int64)L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server",
      v6);
LABEL_26:
    v12 = *(_QWORD *)&WPP_GLOBAL_Control;
    goto LABEL_27;
  }
LABEL_31:
  v15 = operator new(0x360u);
  v16 = v15;
  if ( v15 )
  {
    CTsBusBase::CTsBusBase(v15, a2);
    v16[57] = 0;
    *v16 = &CTsBusSWD::`vftable';
    memset_0(v16 + 58, 0, 0x190u);
  }
  else
  {
    v16 = 0;
  }
  pvData = v16;
  p_pvData = &pvData;
  v17 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v22 = v17;
  if ( v17 )
  {
    v17[2] = 1;
    v17[3] = 1;
    *(_QWORD *)v17 = &utl::_RefCountVtable<utl::_RefCountNormal<CTsDeviceUMBus *,utl::default_delete<CTsDeviceUMBus>,utl::allocator<int>>,0>::`vftable';
    *((_QWORD *)v17 + 2) = pvData;
    v18 = (utl::_RefCountBase *)a1[1];
    *a1 = pvData;
    a1[1] = v17;
    if ( v18 )
      utl::_RefCountBase::_DecStrong(v18);
  }
LABEL_42:
  utl::_SharedBase<ITsBusDevice *>::_SharedReset<CTsDeviceUMBus *,utl::default_delete<CTsDeviceUMBus>,utl::allocator<int>>::~_SharedReset<CTsDeviceUMBus *,utl::default_delete<CTsDeviceUMBus>,utl::allocator<int>>(&v22);
  return a1;
}

```

## disassembly

```asm
0x180041c54  mov     [rsp-28h+arg_8], rbx
0x180041c59  push    rbp
0x180041c5a  push    rsi
0x180041c5b  push    rdi
0x180041c5c  push    r13
0x180041c5e  push    r15
0x180041c60  mov     rbp, rsp
0x180041c63  sub     rsp, 60h
0x180041c67  mov     esi, edx
0x180041c69  mov     qword ptr [rcx], 0
0x180041c70  mov     rdi, rcx
0x180041c73  mov     qword ptr [rcx+8], 0
0x180041c7b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnableSWDForRedirections@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnableSWDForRedirections@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableSWDForRedirections> `wil::Feature<__WilFeatureTraits_Feature_EnableSWDForRedirections>::GetImpl(void)'::`2'::impl
0x180041c82  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableSWDForRedirections@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableSWDForRedirections>::__private_IsEnabled(void)
0x180041c87  lea     r13, WPP_GLOBAL_Control
0x180041c8e  mov     r15d, 1
0x180041c94  test    al, al
0x180041c96  jz      loc_180041D7E
0x180041c9c  mov     rax, cs:WPP_GLOBAL_Control
0x180041ca3  cmp     rax, r13
0x180041ca6  jz      short loc_180041CD7
0x180041ca8  test    [rax+1Ch], r15b
0x180041cac  jz      short loc_180041CD7
0x180041cae  cmp     byte ptr [rax+19h], 4
0x180041cb2  jb      short loc_180041CD7
0x180041cb4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180041cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180041cc0  lea     edx, [r15+9]
0x180041cc4  mov     r9d, eax
0x180041cc7  lea     r8, WPP_ca718917dae2357c6cf8e20d0a589916_Traceguids
0x180041cce  mov     rcx, [rcx+10h]
0x180041cd2  call    WPP_SF_D
0x180041cd7  lea     rax, [rbp+arg_10]
0x180041cdb  mov     dword ptr [rbp+arg_0], 0
0x180041ce2  mov     [rsp+60h+pcbData], rax; pcbData
0x180041ce7  lea     r8, aCreateumbusbus; "CreateUMBusBus"
0x180041cee  lea     rax, [rbp+arg_0]
0x180041cf2  mov     [rbp+arg_10], 4
0x180041cf9  mov     [rsp+60h+pvData], rax; pvData
0x180041cfe  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180041d05  mov     r9d, 10h; dwFlags
0x180041d0b  mov     [rsp+60h+pdwType], 0; pdwType
0x180041d14  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180041d1b  call    cs:__imp_RegGetValueW
0x180041d21  mov     ebx, eax
0x180041d23  test    eax, eax
0x180041d25  jle     short loc_180041D30
0x180041d27  movzx   ebx, ax
0x180041d2a  or      ebx, 80070000h
0x180041d30  test    ebx, ebx
0x180041d32  js      loc_180041E1F
0x180041d38  cmp     dword ptr [rbp+arg_0], 0
0x180041d3c  jz      loc_180041E6B
0x180041d42  mov     rax, cs:WPP_GLOBAL_Control
0x180041d49  cmp     rax, r13
0x180041d4c  jz      short loc_180041DBA
0x180041d4e  test    [rax+1Ch], r15b
0x180041d52  jz      short loc_180041D85
0x180041d54  cmp     byte ptr [rax+19h], 4
0x180041d58  jb      short loc_180041D85
0x180041d5a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180041d5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180041d66  lea     r8, WPP_ca718917dae2357c6cf8e20d0a589916_Traceguids
0x180041d6d  mov     edx, 0Ch
0x180041d72  mov     r9d, eax
0x180041d75  mov     rcx, [rcx+10h]
0x180041d79  call    WPP_SF_D
0x180041d7e  mov     rax, cs:WPP_GLOBAL_Control
0x180041d85  cmp     rax, r13
0x180041d88  jz      short loc_180041DBA
0x180041d8a  test    [rax+1Ch], r15b
0x180041d8e  jz      short loc_180041DBA
0x180041d90  cmp     byte ptr [rax+19h], 4
0x180041d94  jb      short loc_180041DBA
0x180041d96  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180041d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041da2  lea     r8, WPP_ca718917dae2357c6cf8e20d0a589916_Traceguids
0x180041da9  mov     edx, 0Eh
0x180041dae  mov     r9d, eax
0x180041db1  mov     rcx, [rcx+10h]
0x180041db5  call    WPP_SF_D
0x180041dba  mov     ecx, 1E0h; Size
0x180041dbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041dc4  mov     rbx, rax
0x180041dc7  test    rax, rax
0x180041dca  jz      loc_180041F54
0x180041dd0  mov     edx, esi
0x180041dd2  mov     rcx, rax
0x180041dd5  call    ??0CTsBusBase@@QEAA@W4ETSBusType@ITsBus@@@Z; CTsBusBase::CTsBusBase(ITsBus::ETSBusType)
0x180041dda  lea     rax, ??_7CTsBusUMBus@@6B@; const CTsBusUMBus::`vftable'
0x180041de1  xor     edx, edx; dwCoInit
0x180041de3  mov     [rbx], rax
0x180041de6  xor     ecx, ecx; pvReserved
0x180041de8  mov     qword ptr [rbx+1C8h], 0
0x180041df3  mov     qword ptr [rbx+1D0h], 0
0x180041dfe  mov     byte ptr [rbx+1D8h], 0
0x180041e05  call    cs:__imp_CoInitializeEx
0x180041e0b  test    eax, eax
0x180041e0d  js      loc_180041F56
0x180041e13  mov     [rbx+1D8h], r15b
0x180041e1a  jmp     loc_180041F56
0x180041e1f  mov     rax, cs:WPP_GLOBAL_Control
0x180041e26  cmp     rax, r13
0x180041e29  jz      short loc_180041EA7
0x180041e2b  test    [rax+1Ch], r15b
0x180041e2f  jz      short loc_180041E72
0x180041e31  cmp     byte ptr [rax+19h], 4
0x180041e35  jb      short loc_180041E72
0x180041e37  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180041e3c  lea     rcx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180041e43  mov     dword ptr [rsp+60h+pvData], ebx
0x180041e47  mov     [rsp+60h+pdwType], rcx
0x180041e4c  lea     r8, WPP_ca718917dae2357c6cf8e20d0a589916_Traceguids
0x180041e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e5a  mov     edx, 0Bh
0x180041e5f  mov     r9d, eax
0x180041e62  mov     rcx, [rcx+10h]
0x180041e66  call    WPP_SF_DSD
0x180041e6b  mov     rax, cs:WPP_GLOBAL_Control
0x180041e72  cmp     rax, r13
0x180041e75  jz      short loc_180041EA7
0x180041e77  test    [rax+1Ch], r15b
0x180041e7b  jz      short loc_180041EA7
0x180041e7d  cmp     byte ptr [rax+19h], 4
0x180041e81  jb      short loc_180041EA7
0x180041e83  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180041e88  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e8f  lea     r8, WPP_ca718917dae2357c6cf8e20d0a589916_Traceguids
0x180041e96  mov     edx, 0Dh
0x180041e9b  mov     r9d, eax
0x180041e9e  mov     rcx, [rcx+10h]
0x180041ea2  call    WPP_SF_D
0x180041ea7  mov     ecx, 360h; Size
0x180041eac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180041eb1  mov     rbx, rax
0x180041eb4  test    rax, rax
0x180041eb7  jz      short loc_180041EEE
0x180041eb9  mov     edx, esi
0x180041ebb  mov     rcx, rax
0x180041ebe  call    ??0CTsBusBase@@QEAA@W4ETSBusType@ITsBus@@@Z; CTsBusBase::CTsBusBase(ITsBus::ETSBusType)
0x180041ec3  lea     rax, ??_7CTsBusSWD@@6B@; const CTsBusSWD::`vftable'
0x180041eca  mov     qword ptr [rbx+1C8h], 0
0x180041ed5  lea     rcx, [rbx+1D0h]; void *
0x180041edc  mov     [rbx], rax
0x180041edf  xor     edx, edx; Val
0x180041ee1  mov     r8d, 190h; Size
0x180041ee7  call    memset_0
0x180041eec  jmp     short loc_180041EF0
0x180041eee  xor     ebx, ebx
0x180041ef0  lea     rax, [rbp+arg_0]
0x180041ef4  mov     [rbp+arg_0], rbx
0x180041ef8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180041eff  mov     [rbp+var_18], rax
0x180041f03  mov     ecx, 18h; unsigned __int64
0x180041f08  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180041f0d  mov     [rbp+var_20], rax
0x180041f11  test    rax, rax
0x180041f14  jz      short loc_180041F49
0x180041f16  mov     [rax+8], r15d
0x180041f1a  lea     rcx, ??_7?$_RefCountVtable@V?$_RefCountNormal@PEAVCTsDeviceUMBus@@U?$default_delete@VCTsDeviceUMBus@@@utl@@V?$allocator@H@3@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountNormal<CTsDeviceUMBus *,utl::default_delete<CTsDeviceUMBus>,utl::allocator<int>>,0>::`vftable'
0x180041f21  mov     [rax+0Ch], r15d
0x180041f25  mov     [rax], rcx
0x180041f28  mov     rcx, [rbp+arg_0]
0x180041f2c  mov     [rax+10h], rcx
0x180041f30  mov     rcx, [rdi+8]; this
0x180041f34  mov     rdx, [rbp+arg_0]
0x180041f38  mov     [rdi], rdx
0x180041f3b  mov     [rdi+8], rax
0x180041f3f  test    rcx, rcx
0x180041f42  jz      short loc_180041F49
0x180041f44  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180041f49  lea     rcx, [rbp+var_20]
0x180041f4d  call    ??1?$_SharedReset@PEAVCTsDeviceUMBus@@U?$default_delete@VCTsDeviceUMBus@@@utl@@V?$allocator@H@3@@?$_SharedBase@PEAVITsBusDevice@@@utl@@QEAA@XZ; utl::_SharedBase<ITsBusDevice *>::_SharedReset<CTsDeviceUMBus *,utl::default_delete<CTsDeviceUMBus>,utl::allocator<int>>::~_SharedReset<CTsDeviceUMBus *,utl::default_delete<CTsDeviceUMBus>,utl::allocator<int>>(void)
0x180041f52  jmp     short loc_180041FB8
0x180041f54  xor     ebx, ebx
0x180041f56  lea     rax, [rbp+arg_0]
0x180041f5a  mov     [rbp+arg_0], rbx
0x180041f5e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180041f65  mov     [rbp+var_18], rax
0x180041f69  mov     ecx, 18h; unsigned __int64
0x180041f6e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180041f73  mov     [rbp+var_20], rax
0x180041f77  test    rax, rax
0x180041f7a  jz      short loc_180041FAF
0x180041f7c  mov     [rax+8], r15d
0x180041f80  lea     rcx, ??_7?$_RefCountVtable@V?$_RefCountNormal@PEAVCTsDeviceUMBus@@U?$default_delete@VCTsDeviceUMBus@@@utl@@V?$allocator@H@3@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountNormal<CTsDeviceUMBus *,utl::default_delete<CTsDeviceUMBus>,utl::allocator<int>>,0>::`vftable'
0x180041f87  mov     [rax+0Ch], r15d
0x180041f8b  mov     [rax], rcx
0x180041f8e  mov     rcx, [rbp+arg_0]
0x180041f92  mov     [rax+10h], rcx
0x180041f96  mov     rcx, [rdi+8]; this
0x180041f9a  mov     rdx, [rbp+arg_0]
0x180041f9e  mov     [rdi], rdx
0x180041fa1  mov     [rdi+8], rax
0x180041fa5  test    rcx, rcx
0x180041fa8  jz      short loc_180041FAF
0x180041faa  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180041faf  lea     rcx, [rbp+var_20]
0x180041fb3  call    ??1?$_SharedReset@PEAVCTsDeviceUMBus@@U?$default_delete@VCTsDeviceUMBus@@@utl@@V?$allocator@H@3@@?$_SharedBase@PEAVITsBusDevice@@@utl@@QEAA@XZ; utl::_SharedBase<ITsBusDevice *>::_SharedReset<CTsDeviceUMBus *,utl::default_delete<CTsDeviceUMBus>,utl::allocator<int>>::~_SharedReset<CTsDeviceUMBus *,utl::default_delete<CTsDeviceUMBus>,utl::allocator<int>>(void)
0x180041fb8  mov     rbx, [rsp+60h+arg_8]
0x180041fc0  mov     rax, rdi
0x180041fc3  add     rsp, 60h
0x180041fc7  pop     r15
0x180041fc9  pop     r13
0x180041fcb  pop     rdi
0x180041fcc  pop     rsi
0x180041fcd  pop     rbp
0x180041fce  retn
```
