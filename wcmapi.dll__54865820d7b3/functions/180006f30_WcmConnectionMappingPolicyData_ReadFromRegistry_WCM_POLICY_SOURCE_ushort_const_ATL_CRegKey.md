# WcmConnectionMappingPolicyData::ReadFromRegistry(WCM_POLICY_SOURCE,ushort const *,ATL::CRegKey &)

- ea: `0x180006f30`
- end: `0x1800075df`
- name: `?ReadFromRegistry@WcmConnectionMappingPolicyData@@QEAAJW4WCM_POLICY_SOURCE@@PEBGAEAVCRegKey@ATL@@@Z`
- size: `1711`
- prototype: `int __high(enum WCM_POLICY_SOURCE, const unsigned __int16 *, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config`

## callers

- `0x1800176c0`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x1800060e8`
- `0x180006f30`
- `0x1800075e8`
- `0x180007a70`
- `0x180008a90`
- `0x18000953c`
- `0x18001728c`
- `0x180017664`
- `0x180017a60`
- `0x180017dac`
- `0x180018134`
- `0x180018500`
- `0x1800188bc`
- `0x180018e48`
- `0x180018f18`
- `0x180019228`
- `0x18001932c`
- `0x180019604`
- `0x180019660`
- `0x1800196bc`
- `0x180019720`
- `0x18001a1ac`
- `0x18001a3c8`
- `0x18001ae30`
- `0x18001afcc`
- `0x18001e010`

## string_xrefs

- `0x180006f8e`: `WcmConnectionMappingPolicyData::ReadFromRegistry`
- `0x180007594`: `WcmConnectionMappingPolicyData::ReadFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall WcmConnectionMappingPolicyData::ReadFromRegistry(__int64 a1, int a2, __int64 a3, ATL::CRegKey *a4)
{
  ATL::CRegKey *v4; // rsi
  __int64 v8; // rax
  signed int StringValue; // ebx
  WcmPolicyManager *v10; // rcx
  __int64 v11; // rax
  unsigned int i; // r12d
  int v13; // edi
  int v14; // edi
  int v15; // edi
  std::_Ref_count_base *v16; // rdi
  __int64 v17; // rax
  std::_Ref_count_base *v18; // rsi
  std::_Ref_count_base *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // r9
  struct _FILETIME *v26; // [rsp+20h] [rbp-308h]
  std::_Ref_count_base *v27[2]; // [rsp+30h] [rbp-2F8h] BYREF
  ATL::CRegKey *v28; // [rsp+40h] [rbp-2E8h]
  __int64 v29; // [rsp+48h] [rbp-2E0h]
  _BYTE v30[8]; // [rsp+50h] [rbp-2D8h] BYREF
  std::_Ref_count_base *v31; // [rsp+58h] [rbp-2D0h]
  _BYTE v32[8]; // [rsp+60h] [rbp-2C8h] BYREF
  std::_Ref_count_base *v33; // [rsp+68h] [rbp-2C0h]
  _BYTE v34[8]; // [rsp+70h] [rbp-2B8h] BYREF
  std::_Ref_count_base *v35; // [rsp+78h] [rbp-2B0h]
  _BYTE v36[8]; // [rsp+80h] [rbp-2A8h] BYREF
  std::_Ref_count_base *v37; // [rsp+88h] [rbp-2A0h]
  unsigned int v38; // [rsp+90h] [rbp-298h] BYREF
  unsigned int v39; // [rsp+98h] [rbp-290h] BYREF
  __int128 v40; // [rsp+A0h] [rbp-288h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-278h]
  _BYTE v42[32]; // [rsp+C0h] [rbp-268h] BYREF
  WCHAR SubKey[256]; // [rsp+E0h] [rbp-248h] BYREF

  v4 = a4;
  v28 = a4;
  v29 = a1;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_12c04c40514534d8737ded40bb3f712d_Traceguids,
      "WcmConnectionMappingPolicyData::ReadFromRegistry");
  }
  std::wstring::wstring(v42);
  v38 = 0;
  v8 = std::_WChar_traits<unsigned short>::length(a3);
  std::wstring::_Assign<unsigned short>(a1 + 16, a3, v8);
  *(_DWORD *)(a1 + 48) = a2;
  StringValue = ATL::CRegKey::QueryDWORDValue(v4, L"UseConnectionsInOrder", &v38);
  if ( StringValue )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"UseConnectionsInOrder");
      v10 = WPP_GLOBAL_Control;
    }
    if ( StringValue > 0 )
      StringValue = (unsigned __int16)StringValue | 0x80070000;
    goto LABEL_86;
  }
  *(_DWORD *)(a1 + 68) = v38 != 0;
  StringValue = QueryStringValue(v4, L"PolicyTag");
  if ( StringValue )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"PolicyTag");
      v10 = WPP_GLOBAL_Control;
    }
    if ( StringValue > 0 )
      StringValue = (unsigned __int16)StringValue | 0x80070000;
    goto LABEL_86;
  }
  v11 = std::wstring::wstring(&v40, v42);
  StringValue = StringToGuid(v11, a1 + 52);
  if ( StringValue < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    goto LABEL_86;
  }
  for ( i = 0; ; ++i )
  {
    memset_0(SubKey, 0, 0x1FEu);
    v39 = 255;
    v40 = 0u;
    v41 = 0;
    *(_OWORD *)v27 = 0;
    v13 = ATL::CRegKey::EnumKey(v4, i, SubKey, &v39, v26);
    if ( v13 == 259 )
    {
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)&WPP_12c04c40514534d8737ded40bb3f712d_Traceguids,
          a3,
          i);
      }
      goto LABEL_27;
    }
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), a3, i);
      }
      if ( v13 > 0 )
        StringValue = (unsigned __int16)v13 | 0x80070000;
      else
        StringValue = v13;
      goto LABEL_27;
    }
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), a3, i);
    }
    v14 = ATL::CRegKey::Open((ATL::CRegKey *)&v40, *(HKEY *)v4, SubKey, 0x20019u);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)SubKey);
      }
      if ( v14 > 0 )
        StringValue = (unsigned __int16)v14 | 0x80070000;
      else
        StringValue = v14;
      goto LABEL_27;
    }
    v15 = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)&v40, L"SelectionType", &v38);
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"SelectionType");
      }
      if ( v15 > 0 )
        StringValue = (unsigned __int16)v15 | 0x80070000;
      else
        StringValue = v15;
      goto LABEL_27;
    }
    if ( v38 == 1 )
      break;
    switch ( v38 )
    {
      case 2u:
        v21 = std::make_shared<WcmConnectionSelectionByDeviceType,>(v34);
        v18 = *(std::_Ref_count_base **)v21;
        v16 = *(std::_Ref_count_base **)(v21 + 8);
        *(_QWORD *)v21 = 0;
        *(_QWORD *)(v21 + 8) = 0;
        v19 = v35;
        goto LABEL_69;
      case 3u:
        v20 = std::make_shared<WcmConnectionSelectionByConnectionType,>(v32);
        v18 = *(std::_Ref_count_base **)v20;
        v16 = *(std::_Ref_count_base **)(v20 + 8);
        *(_QWORD *)v20 = 0;
        *(_QWORD *)(v20 + 8) = 0;
        v19 = v33;
        goto LABEL_69;
      case 4u:
        v17 = std::make_shared<WcmConnectionSelectionByNetworkType,>(v30);
        v18 = *(std::_Ref_count_base **)v17;
        v16 = *(std::_Ref_count_base **)(v17 + 8);
        *(_QWORD *)v17 = 0;
        *(_QWORD *)(v17 + 8) = 0;
        v19 = v31;
        goto LABEL_69;
    }
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), a3);
    }
    StringValue = -2147467259;
    v16 = v27[1];
LABEL_83:
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    ATL::CRegKey::Close((ATL::CRegKey *)&v40);
  }
  v22 = std::make_shared<WcmConnectionSelectionByName,>(v36);
  v18 = *(std::_Ref_count_base **)v22;
  v16 = *(std::_Ref_count_base **)(v22 + 8);
  *(_QWORD *)v22 = 0;
  *(_QWORD *)(v22 + 8) = 0;
  v19 = v37;
LABEL_69:
  v27[1] = v16;
  v27[0] = v18;
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  if ( !v18 )
  {
LABEL_82:
    v4 = v28;
    goto LABEL_83;
  }
  StringValue = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int128 *))(*(_QWORD *)v18 + 16LL))(v18, &v40);
  if ( StringValue >= 0 )
  {
    v23 = *(_QWORD *)(v29 + 80);
    if ( v23 == *(_QWORD *)(v29 + 88) )
    {
      std::vector<std::shared_ptr<WcmConnectionSelection>>::_Emplace_reallocate<std::shared_ptr<WcmConnectionSelection> const &>(
        v29 + 72,
        *(_QWORD *)(v29 + 80),
        v27);
      v16 = v27[1];
    }
    else
    {
      std::_Construct_in_place<std::shared_ptr<WcmConnectionSelection>,std::shared_ptr<WcmConnectionSelection> const &>(
        v23,
        v27);
      *(_QWORD *)(v24 + 80) += 16LL;
    }
    goto LABEL_82;
  }
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), a3);
  }
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
LABEL_27:
  ATL::CRegKey::Close((ATL::CRegKey *)&v40);
  v10 = WPP_GLOBAL_Control;
LABEL_86:
  if ( v10 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 5u && (*((_BYTE *)v10 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v10 + 2),
      27,
      (unsigned int)&WPP_12c04c40514534d8737ded40bb3f712d_Traceguids,
      (unsigned int)"WcmConnectionMappingPolicyData::ReadFromRegistry",
      StringValue);
  std::wstring::_Tidy_deallocate(v42);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x180006f30  push    rbx
0x180006f32  push    rsi
0x180006f33  push    rdi
0x180006f34  push    r12
0x180006f36  push    r13
0x180006f38  push    r14
0x180006f3a  push    r15
0x180006f3c  sub     rsp, 2F0h
0x180006f43  mov     rax, cs:__security_cookie
0x180006f4a  xor     rax, rsp
0x180006f4d  mov     [rsp+328h+var_48], rax
0x180006f55  mov     rsi, r9
0x180006f58  mov     [rsp+328h+var_2E8], r9
0x180006f5d  mov     r13, r8
0x180006f60  mov     ebx, edx
0x180006f62  mov     rdi, rcx
0x180006f65  mov     [rsp+328h+var_2E0], rcx
0x180006f6a  lea     r14, WPP_GLOBAL_Control
0x180006f71  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f78  cmp     rcx, r14
0x180006f7b  jz      short loc_180006FA5
0x180006f7d  cmp     byte ptr [rcx+19h], 5
0x180006f81  jb      short loc_180006FA5
0x180006f83  test    byte ptr [rcx+1Ch], 1
0x180006f87  jz      short loc_180006FA5
0x180006f89  mov     edx, 11h
0x180006f8e  lea     r9, aWcmconnectionm_7; "WcmConnectionMappingPolicyData::ReadFro"...
0x180006f95  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180006f9c  mov     rcx, [rcx+10h]
0x180006fa0  call    WPP_SF_s
0x180006fa5  lea     rcx, [rsp+328h+var_268]
0x180006fad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180006fb2  nop
0x180006fb3  xor     r15d, r15d
0x180006fb6  mov     [rsp+328h+var_298], r15d
0x180006fbe  mov     rcx, r13
0x180006fc1  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180006fc6  lea     rcx, [rdi+10h]
0x180006fca  mov     r8, rax
0x180006fcd  mov     rdx, r13
0x180006fd0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180006fd5  mov     [rdi+30h], ebx
0x180006fd8  lea     r8, [rsp+328h+var_298]; unsigned int *
0x180006fe0  lea     r12, ?c_szUseConnectionsInOrder@@3QBGB; "UseConnectionsInOrder"
0x180006fe7  mov     rdx, r12; unsigned __int16 *
0x180006fea  mov     rcx, rsi; this
0x180006fed  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x180006ff2  mov     ebx, eax
0x180006ff4  test    eax, eax
0x180006ff6  jz      short loc_180007045
0x180006ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fff  cmp     rcx, r14
0x180007002  jz      short loc_180007033
0x180007004  cmp     byte ptr [rcx+19h], 1
0x180007008  jb      short loc_180007033
0x18000700a  test    byte ptr [rcx+1Ch], 1
0x18000700e  jz      short loc_180007033
0x180007010  lea     edx, [r15+12h]
0x180007014  mov     [rsp+328h+var_308], r12; __int64
0x180007019  mov     r9d, eax
0x18000701c  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180007023  mov     rcx, [rcx+10h]; LoggerHandle
0x180007027  call    WPP_SF_DS
0x18000702c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007033  test    ebx, ebx
0x180007035  jle     short loc_180007040
0x180007037  movzx   ebx, bx
0x18000703a  or      ebx, 80070000h
0x180007040  jmp     loc_18000757A
0x180007045  mov     eax, r15d
0x180007048  cmp     [rsp+328h+var_298], r15d
0x180007050  setnz   al
0x180007053  mov     [rdi+44h], eax
0x180007056  lea     r8, [rsp+328h+var_268]
0x18000705e  lea     r12, ?c_szPolicyTagRegValue@@3QBGB; "PolicyTag"
0x180007065  mov     rdx, r12; unsigned __int16 *
0x180007068  mov     rcx, rsi; this
0x18000706b  call    ?QueryStringValue@@YAKAEAVCRegKey@ATL@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; QueryStringValue(ATL::CRegKey &,ushort const *,std::wstring &)
0x180007070  mov     ebx, eax
0x180007072  test    eax, eax
0x180007074  jz      short loc_1800070C4
0x180007076  mov     rcx, cs:WPP_GLOBAL_Control
0x18000707d  cmp     rcx, r14
0x180007080  jz      short loc_1800070B2
0x180007082  cmp     byte ptr [rcx+19h], 1
0x180007086  jb      short loc_1800070B2
0x180007088  test    byte ptr [rcx+1Ch], 1
0x18000708c  jz      short loc_1800070B2
0x18000708e  mov     edx, 13h
0x180007093  mov     [rsp+328h+var_308], r12; __int64
0x180007098  mov     r9d, eax
0x18000709b  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x1800070a2  mov     rcx, [rcx+10h]; LoggerHandle
0x1800070a6  call    WPP_SF_DS
0x1800070ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070b2  test    ebx, ebx
0x1800070b4  jle     short loc_1800070BF
0x1800070b6  movzx   ebx, bx
0x1800070b9  or      ebx, 80070000h
0x1800070bf  jmp     loc_18000757A
0x1800070c4  lea     rdx, [rsp+328h+var_268]
0x1800070cc  lea     rcx, [rsp+328h+var_288]
0x1800070d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800070d9  lea     rdx, [rdi+34h]
0x1800070dd  mov     rcx, rax
0x1800070e0  call    ?StringToGuid@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_GUID@@@Z; StringToGuid(std::wstring,_GUID &)
0x1800070e5  mov     ebx, eax
0x1800070e7  test    eax, eax
0x1800070e9  jns     short loc_1800070F7
0x1800070eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070f2  jmp     loc_18000757A
0x1800070f7  mov     r12d, r15d
0x1800070fa  xor     edx, edx; Val
0x1800070fc  mov     r8d, 1FEh; Size
0x180007102  lea     rcx, [rsp+328h+SubKey]; void *
0x18000710a  call    memset_0
0x18000710f  mov     [rsp+328h+var_290], 0FFh
0x18000711a  xorps   xmm0, xmm0
0x18000711d  movups  [rsp+328h+var_288], xmm0
0x180007125  mov     qword ptr [rsp+328h+var_288], r15
0x18000712d  mov     qword ptr [rsp+328h+var_288+8], r15
0x180007135  mov     [rsp+328h+var_278], r15
0x18000713d  xorps   xmm1, xmm1
0x180007140  movdqu  xmmword ptr [rsp+328h+var_2F8], xmm1
0x180007146  lea     r9, [rsp+328h+var_290]; unsigned int *
0x18000714e  lea     r8, [rsp+328h+SubKey]; unsigned __int16 *
0x180007156  mov     edx, r12d; unsigned int
0x180007159  mov     rcx, rsi; this
0x18000715c  call    ?EnumKey@CRegKey@ATL@@QEAAJKPEAGPEAKPEAU_FILETIME@@@Z; ATL::CRegKey::EnumKey(ulong,ushort *,ulong *,_FILETIME *)
0x180007161  mov     edi, eax
0x180007163  cmp     eax, 103h
0x180007168  jnz     short loc_1800071B3
0x18000716a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007171  cmp     rcx, r14
0x180007174  jz      short loc_1800071A0
0x180007176  cmp     byte ptr [rcx+19h], 4
0x18000717a  jb      short loc_1800071A0
0x18000717c  test    byte ptr [rcx+1Ch], 1
0x180007180  jz      short loc_1800071A0
0x180007182  mov     edx, 14h
0x180007187  mov     dword ptr [rsp+328h+var_308], r12d
0x18000718c  mov     r9, r13
0x18000718f  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180007196  mov     rcx, [rcx+10h]
0x18000719a  call    WPP_SF_SD
0x18000719f  nop
0x1800071a0  lea     rcx, [rsp+328h+var_288]; this
0x1800071a8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800071ad  nop
0x1800071ae  jmp     loc_180007573
0x1800071b3  test    edi, edi
0x1800071b5  jz      short loc_18000721C
0x1800071b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071be  cmp     rcx, r14
0x1800071c1  jz      short loc_1800071F1
0x1800071c3  cmp     byte ptr [rcx+19h], 1
0x1800071c7  jb      short loc_1800071F1
0x1800071c9  test    byte ptr [rcx+1Ch], 1
0x1800071cd  jz      short loc_1800071F1
0x1800071cf  mov     edx, 15h
0x1800071d4  mov     dword ptr [rsp+328h+var_300], r12d; char
0x1800071d9  mov     [rsp+328h+var_308], r13; __int64
0x1800071de  mov     r9d, edi
0x1800071e1  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x1800071e8  mov     rcx, [rcx+10h]; LoggerHandle
0x1800071ec  call    WPP_SF_DSD
0x1800071f1  test    edi, edi
0x1800071f3  jg      short loc_1800071F9
0x1800071f5  mov     ebx, edi
0x1800071f7  jmp     short loc_180007202
0x1800071f9  movzx   ebx, di
0x1800071fc  or      ebx, 80070000h
0x180007202  lea     rcx, [rsp+328h+var_288]; this
0x18000720a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000720f  nop
0x180007210  mov     rcx, cs:WPP_GLOBAL_Control
0x180007217  jmp     loc_18000757A
0x18000721c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007223  cmp     rcx, r14
0x180007226  jz      short loc_18000724F
0x180007228  cmp     byte ptr [rcx+19h], 4
0x18000722c  jb      short loc_18000724F
0x18000722e  test    byte ptr [rcx+1Ch], 1
0x180007232  jz      short loc_18000724F
0x180007234  mov     dword ptr [rsp+328h+var_300], r12d; char
0x180007239  mov     [rsp+328h+var_308], r13; __int64
0x18000723e  lea     r9, [rsp+328h+SubKey]
0x180007246  mov     rcx, [rcx+10h]; LoggerHandle
0x18000724a  call    WPP_SF_SSD
0x18000724f  mov     r9d, 20019h; unsigned int
0x180007255  lea     r8, [rsp+328h+SubKey]; lpSubKey
0x18000725d  mov     rdx, [rsi]; hKey
0x180007260  lea     rcx, [rsp+328h+var_288]; this
0x180007268  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000726d  mov     edi, eax
0x18000726f  test    eax, eax
0x180007271  jz      short loc_1800072DB
0x180007273  mov     rcx, cs:WPP_GLOBAL_Control
0x18000727a  cmp     rcx, r14
0x18000727d  jz      short loc_1800072B0
0x18000727f  cmp     byte ptr [rcx+19h], 1
0x180007283  jb      short loc_1800072B0
0x180007285  test    byte ptr [rcx+1Ch], 1
0x180007289  jz      short loc_1800072B0
0x18000728b  mov     edx, 17h
0x180007290  lea     rax, [rsp+328h+SubKey]
0x180007298  mov     [rsp+328h+var_308], rax; __int64
0x18000729d  mov     r9d, edi
0x1800072a0  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x1800072a7  mov     rcx, [rcx+10h]; LoggerHandle
0x1800072ab  call    WPP_SF_DS
0x1800072b0  test    edi, edi
0x1800072b2  jg      short loc_1800072B8
0x1800072b4  mov     ebx, edi
0x1800072b6  jmp     short loc_1800072C1
0x1800072b8  movzx   ebx, di
0x1800072bb  or      ebx, 80070000h
0x1800072c1  lea     rcx, [rsp+328h+var_288]; this
0x1800072c9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800072ce  nop
0x1800072cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072d6  jmp     loc_18000757A
0x1800072db  lea     r8, [rsp+328h+var_298]; unsigned int *
0x1800072e3  lea     rdx, ?c_szConnectionSelection_SelectionTypeRegKey@@3QBGB; "SelectionType"
0x1800072ea  lea     rcx, [rsp+328h+var_288]; this
0x1800072f2  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800072f7  mov     edi, eax
0x1800072f9  test    eax, eax
0x1800072fb  jz      short loc_180007364
0x1800072fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180007304  cmp     rcx, r14
0x180007307  jz      short loc_180007339
0x180007309  cmp     byte ptr [rcx+19h], 1
0x18000730d  jb      short loc_180007339
0x18000730f  test    byte ptr [rcx+1Ch], 1
0x180007313  jz      short loc_180007339
0x180007315  mov     edx, 18h
0x18000731a  lea     rax, ?c_szConnectionSelection_SelectionTypeRegKey@@3QBGB; "SelectionType"
0x180007321  mov     [rsp+328h+var_308], rax; __int64
0x180007326  mov     r9d, edi
0x180007329  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180007330  mov     rcx, [rcx+10h]; LoggerHandle
0x180007334  call    WPP_SF_DS
0x180007339  test    edi, edi
0x18000733b  jg      short loc_180007341
0x18000733d  mov     ebx, edi
0x18000733f  jmp     short loc_18000734A
0x180007341  movzx   ebx, di
0x180007344  or      ebx, 80070000h
0x18000734a  lea     rcx, [rsp+328h+var_288]; this
0x180007352  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007357  nop
0x180007358  mov     rcx, cs:WPP_GLOBAL_Control
0x18000735f  jmp     loc_18000757A
0x180007364  mov     r15d, [rsp+328h+var_298]
0x18000736c  mov     ecx, r15d
0x18000736f  sub     ecx, 1
0x180007372  jz      loc_180007444
0x180007378  sub     ecx, 1
0x18000737b  jz      loc_18000741D
0x180007381  sub     ecx, 1
0x180007384  jz      short loc_1800073F6
0x180007386  cmp     ecx, 1
0x180007389  jz      short loc_1800073CF
0x18000738b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007392  cmp     rcx, r14
0x180007395  jz      short loc_1800073C0
0x180007397  cmp     byte ptr [rcx+19h], 1
0x18000739b  jb      short loc_1800073C0
0x18000739d  test    byte ptr [rcx+1Ch], 1
0x1800073a1  jz      short loc_1800073C0
0x1800073a3  mov     edx, 19h
0x1800073a8  mov     [rsp+328h+var_308], r13; __int64
0x1800073ad  mov     r9d, r15d
0x1800073b0  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x1800073b7  mov     rcx, [rcx+10h]; LoggerHandle
0x1800073bb  call    WPP_SF_DS
0x1800073c0  mov     ebx, 80004005h
0x1800073c5  mov     rdi, [rsp+328h+var_2F8+8]
0x1800073ca  jmp     loc_18000753F
0x1800073cf  lea     rcx, [rsp+328h+var_2D8]
0x1800073d4  call    ??$make_shared@VWcmConnectionSelectionByNetworkType@@$$V@std@@YA?AV?$shared_ptr@VWcmConnectionSelectionByNetworkType@@@0@XZ; std::make_shared<WcmConnectionSelectionByNetworkType,>(void)
0x1800073d9  mov     rsi, [rax]
0x1800073dc  mov     rdi, [rax+8]
0x1800073e0  mov     qword ptr [rax], 0
0x1800073e7  mov     qword ptr [rax+8], 0
0x1800073ef  mov     rcx, [rsp+328h+var_2D0]
0x1800073f4  jmp     short loc_18000746F
0x1800073f6  lea     rcx, [rsp+328h+var_2C8]
0x1800073fb  call    ??$make_shared@VWcmConnectionSelectionByConnectionType@@$$V@std@@YA?AV?$shared_ptr@VWcmConnectionSelectionByConnectionType@@@0@XZ; std::make_shared<WcmConnectionSelectionByConnectionType,>(void)
0x180007400  mov     rsi, [rax]
0x180007403  mov     rdi, [rax+8]
0x180007407  mov     qword ptr [rax], 0
0x18000740e  mov     qword ptr [rax+8], 0
0x180007416  mov     rcx, [rsp+328h+var_2C0]
0x18000741b  jmp     short loc_18000746F
0x18000741d  lea     rcx, [rsp+328h+var_2B8]
0x180007422  call    ??$make_shared@VWcmConnectionSelectionByDeviceType@@$$V@std@@YA?AV?$shared_ptr@VWcmConnectionSelectionByDeviceType@@@0@XZ; std::make_shared<WcmConnectionSelectionByDeviceType,>(void)
0x180007427  mov     rsi, [rax]
0x18000742a  mov     rdi, [rax+8]
  ... truncated ...
```
