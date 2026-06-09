# WcmConnectionMappingPolicyData::WriteToRegistry(ATL::CRegKey &)

- ea: `0x180006b4c`
- end: `0x180006f29`
- name: `?WriteToRegistry@WcmConnectionMappingPolicyData@@QEAAJAEAVCRegKey@ATL@@@Z`
- size: `989`
- prototype: `int(WcmConnectionMappingPolicyData *__hidden this, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x180008010`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180006b4c`
- `0x1800075e8`
- `0x180007a70`
- `0x180008a90`
- `0x18000a61c`
- `0x18001728c`
- `0x1800172ec`
- `0x1800189d8`
- `0x180018ac0`
- `0x180018d84`
- `0x180018f18`
- `0x18001902c`
- `0x18001a2d0`
- `0x18001a9b0`
- `0x18001e010`

## string_xrefs

- `0x180006ba2`: `WcmConnectionMappingPolicyData::WriteToRegistry`
- `0x180006ed7`: `WcmConnectionMappingPolicyData::WriteToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall WcmConnectionMappingPolicyData::WriteToRegistry(WcmConnectionMappingPolicyData *this, HKEY *a2)
{
  int v4; // r12d
  char *v5; // r13
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const BYTE *v9; // r8
  int v10; // ebx
  WcmPolicyManager *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  const BYTE *v15; // r8
  LSTATUS v16; // edi
  _QWORD *v17; // rdi
  _QWORD *v18; // rsi
  unsigned __int16 *v19; // r9
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r10
  unsigned int v28[2]; // [rsp+20h] [rbp-298h]
  __int128 v29; // [rsp+48h] [rbp-270h] BYREF
  __int64 v30; // [rsp+58h] [rbp-260h]
  _BYTE v31[32]; // [rsp+60h] [rbp-258h] BYREF
  WCHAR SubKey[256]; // [rsp+80h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_12c04c40514534d8737ded40bb3f712d_Traceguids,
      "WcmConnectionMappingPolicyData::WriteToRegistry");
  }
  std::wstring::wstring(v31);
  v4 = 0;
  v5 = (char *)this + 16;
  v9 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 16, v6, v7, v8);
  v10 = ATL::CRegKey::SetStringValue(a2, L"PolicyName", v9);
  if ( v10 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"PolicyName");
      v11 = WPP_GLOBAL_Control;
    }
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
  }
  else
  {
    v10 = ATL::CRegKey::SetDWORDValue(a2, L"UseConnectionsInOrder", *((_DWORD *)this + 17));
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"UseConnectionsInOrder");
        v11 = WPP_GLOBAL_Control;
      }
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v10 = GuidToString((char *)this + 52, v31);
      if ( v10 >= 0 )
      {
        v15 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31, v12, v13, v14);
        v16 = ATL::CRegKey::SetStringValue(a2, L"PolicyTag", v15);
        if ( v16 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25)
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"PolicyTag");
            v11 = WPP_GLOBAL_Control;
          }
          if ( v16 > 0 )
            v10 = (unsigned __int16)v16 | 0x80070000;
          else
            v10 = v16;
        }
        else
        {
          v17 = (_QWORD *)*((_QWORD *)this + 9);
          v18 = (_QWORD *)*((_QWORD *)this + 10);
          while ( v17 != v18 )
          {
            v28[0] = ++v4;
            v10 = StringCchPrintfW(SubKey, 0xFFu, L"%s%03u", L"Selection", *(_QWORD *)v28);
            if ( v10 < 0 )
            {
              v11 = WPP_GLOBAL_Control;
              goto LABEL_51;
            }
            v29 = 0u;
            v30 = 0;
            v10 = ATL::CRegKey::Create((ATL::CRegKey *)&v29, *a2, SubKey, v19);
            if ( v10 )
            {
              if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25)
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5, WPP_GLOBAL_Control, v21, v22);
                WPP_SF_DSS(*(_QWORD *)(v24 + 16), (__int64)SubKey, v23);
              }
              if ( v10 > 0 )
                v10 = (unsigned __int16)v10 | 0x80070000;
LABEL_48:
              ATL::CRegKey::Close((ATL::CRegKey *)&v29);
              v11 = WPP_GLOBAL_Control;
              goto LABEL_51;
            }
            if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5, v20, v21, v22);
              WPP_SF_SS(
                *(_QWORD *)(v26 + 16),
                15,
                (unsigned int)&WPP_12c04c40514534d8737ded40bb3f712d_Traceguids,
                (unsigned int)SubKey,
                v25);
            }
            v10 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v17 + 8LL))(*v17, &v29);
            if ( v10 < 0 )
              goto LABEL_48;
            ATL::CRegKey::Close((ATL::CRegKey *)&v29);
            v17 += 2;
          }
          v11 = WPP_GLOBAL_Control;
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
      }
    }
  }
LABEL_51:
  if ( v11 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) >= 5u && (*((_BYTE *)v11 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v11 + 2),
      16,
      (unsigned int)&WPP_12c04c40514534d8737ded40bb3f712d_Traceguids,
      (unsigned int)"WcmConnectionMappingPolicyData::WriteToRegistry",
      v10);
  std::wstring::_Tidy_deallocate(v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006b4c  mov     [rsp+arg_10], rbx
0x180006b51  mov     [rsp+arg_18], rsi
0x180006b56  push    rdi
0x180006b57  push    r12
0x180006b59  push    r13
0x180006b5b  push    r14
0x180006b5d  push    r15
0x180006b5f  sub     rsp, 290h
0x180006b66  mov     rax, cs:__security_cookie
0x180006b6d  xor     rax, rsp
0x180006b70  mov     [rsp+2B8h+var_38], rax
0x180006b78  mov     r15, rdx
0x180006b7b  mov     rsi, rcx
0x180006b7e  lea     r14, WPP_GLOBAL_Control
0x180006b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b8c  cmp     rcx, r14
0x180006b8f  jz      short loc_180006BB9
0x180006b91  cmp     byte ptr [rcx+19h], 5
0x180006b95  jb      short loc_180006BB9
0x180006b97  test    byte ptr [rcx+1Ch], 1
0x180006b9b  jz      short loc_180006BB9
0x180006b9d  mov     edx, 0Ah
0x180006ba2  lea     r9, aWcmconnectionm; "WcmConnectionMappingPolicyData::WriteTo"...
0x180006ba9  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180006bb0  mov     rcx, [rcx+10h]
0x180006bb4  call    WPP_SF_s
0x180006bb9  lea     rcx, [rsp+2B8h+var_258]
0x180006bbe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180006bc3  nop
0x180006bc4  xor     r12d, r12d
0x180006bc7  lea     r13, [rsi+10h]
0x180006bcb  mov     rcx, r13
0x180006bce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180006bd3  mov     r8, rax; unsigned __int16 *
0x180006bd6  lea     rdi, ?c_szPolicyNameRegValue@@3QBGB; "PolicyName"
0x180006bdd  mov     rdx, rdi; unsigned __int16 *
0x180006be0  mov     rcx, r15; this
0x180006be3  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180006be8  mov     ebx, eax
0x180006bea  test    eax, eax
0x180006bec  jz      short loc_180006C3C
0x180006bee  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bf5  cmp     rcx, r14
0x180006bf8  jz      short loc_180006C2A
0x180006bfa  cmp     byte ptr [rcx+19h], 1
0x180006bfe  jb      short loc_180006C2A
0x180006c00  test    byte ptr [rcx+1Ch], 1
0x180006c04  jz      short loc_180006C2A
0x180006c06  lea     edx, [r12+0Bh]
0x180006c0b  mov     qword ptr [rsp+2B8h+var_298], rdi; __int64
0x180006c10  mov     r9d, eax
0x180006c13  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180006c1a  mov     rcx, [rcx+10h]; LoggerHandle
0x180006c1e  call    WPP_SF_DS
0x180006c23  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c2a  test    ebx, ebx
0x180006c2c  jle     short loc_180006C37
0x180006c2e  movzx   ebx, bx
0x180006c31  or      ebx, 80070000h
0x180006c37  jmp     loc_180006EBD
0x180006c3c  mov     r8d, [rsi+44h]; unsigned int
0x180006c40  lea     rdi, ?c_szUseConnectionsInOrder@@3QBGB; "UseConnectionsInOrder"
0x180006c47  mov     rdx, rdi; unsigned __int16 *
0x180006c4a  mov     rcx, r15; this
0x180006c4d  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180006c52  mov     ebx, eax
0x180006c54  test    eax, eax
0x180006c56  jz      short loc_180006CA6
0x180006c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c5f  cmp     rcx, r14
0x180006c62  jz      short loc_180006C94
0x180006c64  cmp     byte ptr [rcx+19h], 1
0x180006c68  jb      short loc_180006C94
0x180006c6a  test    byte ptr [rcx+1Ch], 1
0x180006c6e  jz      short loc_180006C94
0x180006c70  mov     edx, 0Ch
0x180006c75  mov     qword ptr [rsp+2B8h+var_298], rdi; __int64
0x180006c7a  mov     r9d, eax
0x180006c7d  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180006c84  mov     rcx, [rcx+10h]; LoggerHandle
0x180006c88  call    WPP_SF_DS
0x180006c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c94  test    ebx, ebx
0x180006c96  jle     short loc_180006CA1
0x180006c98  movzx   ebx, bx
0x180006c9b  or      ebx, 80070000h
0x180006ca1  jmp     loc_180006EBD
0x180006ca6  lea     rcx, [rsi+34h]
0x180006caa  lea     rdx, [rsp+2B8h+var_258]
0x180006caf  call    ?GuidToString@@YAJAEAU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GuidToString(_GUID &,std::wstring &)
0x180006cb4  mov     ebx, eax
0x180006cb6  test    eax, eax
0x180006cb8  jns     short loc_180006CC6
0x180006cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cc1  jmp     loc_180006EBD
0x180006cc6  lea     rcx, [rsp+2B8h+var_258]
0x180006ccb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180006cd0  mov     r8, rax; unsigned __int16 *
0x180006cd3  lea     rdx, ?c_szPolicyTagRegValue@@3QBGB; "PolicyTag"
0x180006cda  mov     rcx, r15; this
0x180006cdd  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180006ce2  mov     edi, eax
0x180006ce4  test    eax, eax
0x180006ce6  jz      short loc_180006D41
0x180006ce8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cef  cmp     rcx, r14
0x180006cf2  jz      short loc_180006D2B
0x180006cf4  cmp     byte ptr [rcx+19h], 1
0x180006cf8  jb      short loc_180006D2B
0x180006cfa  test    byte ptr [rcx+1Ch], 1
0x180006cfe  jz      short loc_180006D2B
0x180006d00  mov     edx, 0Dh
0x180006d05  lea     rax, ?c_szPolicyTagRegValue@@3QBGB; "PolicyTag"
0x180006d0c  mov     qword ptr [rsp+2B8h+var_298], rax; __int64
0x180006d11  mov     r9d, edi
0x180006d14  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180006d1b  mov     rcx, [rcx+10h]; LoggerHandle
0x180006d1f  call    WPP_SF_DS
0x180006d24  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d2b  test    edi, edi
0x180006d2d  jg      short loc_180006D33
0x180006d2f  mov     ebx, edi
0x180006d31  jmp     short loc_180006D3C
0x180006d33  movzx   ebx, di
0x180006d36  or      ebx, 80070000h
0x180006d3c  jmp     loc_180006EBD
0x180006d41  mov     rdi, [rsi+48h]
0x180006d45  mov     rsi, [rsi+50h]
0x180006d49  cmp     rdi, rsi
0x180006d4c  jz      loc_180006EA9
0x180006d52  inc     r12d
0x180006d55  mov     [rsp+2B8h+var_298], r12d; unsigned int
0x180006d5a  lea     r9, ?c_szConnectionSelectionRegKeyPrefix@@3QBGB; "Selection"
0x180006d61  lea     r8, aS03u; "%s%03u"
0x180006d68  mov     edx, 0FFh; unsigned __int64
0x180006d6d  lea     rcx, [rsp+2B8h+SubKey]; unsigned __int16 *
0x180006d75  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006d7a  mov     ebx, eax
0x180006d7c  xor     ecx, ecx
0x180006d7e  test    eax, eax
0x180006d80  jns     short loc_180006D8E
0x180006d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d89  jmp     loc_180006EBD
0x180006d8e  xorps   xmm0, xmm0
0x180006d91  movups  [rsp+2B8h+var_270], xmm0
0x180006d96  mov     qword ptr [rsp+2B8h+var_270], rcx
0x180006d9b  mov     qword ptr [rsp+2B8h+var_270+8], rcx
0x180006da0  mov     [rsp+2B8h+var_260], rcx
0x180006da5  lea     r8, [rsp+2B8h+SubKey]; lpSubKey
0x180006dad  mov     rdx, [r15]; hKey
0x180006db0  lea     rcx, [rsp+2B8h+var_270]; this
0x180006db5  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180006dba  mov     ebx, eax
0x180006dbc  test    eax, eax
0x180006dbe  jz      short loc_180006E29
0x180006dc0  mov     rdx, cs:WPP_GLOBAL_Control
0x180006dc7  cmp     rdx, r14
0x180006dca  jz      short loc_180006E05
0x180006dcc  cmp     byte ptr [rdx+19h], 1
0x180006dd0  jb      short loc_180006E05
0x180006dd2  test    byte ptr [rdx+1Ch], 1
0x180006dd6  jz      short loc_180006E05
0x180006dd8  mov     rcx, r13
0x180006ddb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180006de0  mov     [rsp+2B8h+var_290], rax; __int64
0x180006de5  lea     rax, [rsp+2B8h+SubKey]
0x180006ded  mov     qword ptr [rsp+2B8h+var_298], rax; __int64
0x180006df2  mov     r9d, ebx
0x180006df5  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180006dfc  mov     rcx, [rdx+10h]; LoggerHandle
0x180006e00  call    WPP_SF_DSS
0x180006e05  test    ebx, ebx
0x180006e07  jle     short loc_180006E12
0x180006e09  movzx   ebx, bx
0x180006e0c  or      ebx, 80070000h
0x180006e12  lea     rcx, [rsp+2B8h+var_270]; this
0x180006e17  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006e1c  nop
0x180006e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e24  jmp     loc_180006EBD
0x180006e29  mov     r10, cs:WPP_GLOBAL_Control
0x180006e30  cmp     r10, r14
0x180006e33  jz      short loc_180006E6D
0x180006e35  cmp     byte ptr [r10+19h], 4
0x180006e3a  jb      short loc_180006E6D
0x180006e3c  test    byte ptr [r10+1Ch], 1
0x180006e41  jz      short loc_180006E6D
0x180006e43  mov     rcx, r13
0x180006e46  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180006e4b  mov     edx, 0Fh
0x180006e50  mov     qword ptr [rsp+2B8h+var_298], rax
0x180006e55  lea     r9, [rsp+2B8h+SubKey]
0x180006e5d  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180006e64  mov     rcx, [r10+10h]
0x180006e68  call    WPP_SF_SS
0x180006e6d  mov     rcx, [rdi]
0x180006e70  mov     rax, [rcx]
0x180006e73  lea     rdx, [rsp+2B8h+var_270]
0x180006e78  mov     rax, [rax+8]
0x180006e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e81  mov     ebx, eax
0x180006e83  lea     rcx, [rsp+2B8h+var_270]; this
0x180006e88  test    eax, eax
0x180006e8a  jns     short loc_180006E9B
0x180006e8c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006e91  nop
0x180006e92  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e99  jmp     short loc_180006EBD
0x180006e9b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180006ea0  add     rdi, 10h
0x180006ea4  jmp     loc_180006D49
0x180006ea9  jmp     short loc_180006EB6
0x180006eab  lea     r14, WPP_GLOBAL_Control
0x180006eb2  mov     ebx, [rsp+2B8h+var_278]
0x180006eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ebd  cmp     rcx, r14
0x180006ec0  jz      short loc_180006EEF
0x180006ec2  cmp     byte ptr [rcx+19h], 5
0x180006ec6  jb      short loc_180006EEF
0x180006ec8  test    byte ptr [rcx+1Ch], 1
0x180006ecc  jz      short loc_180006EEF
0x180006ece  mov     edx, 10h
0x180006ed3  mov     [rsp+2B8h+var_298], ebx
0x180006ed7  lea     r9, aWcmconnectionm; "WcmConnectionMappingPolicyData::WriteTo"...
0x180006ede  lea     r8, WPP_12c04c40514534d8737ded40bb3f712d_Traceguids
0x180006ee5  mov     rcx, [rcx+10h]
0x180006ee9  call    WPP_SF_sL
0x180006eee  nop
0x180006eef  lea     rcx, [rsp+2B8h+var_258]
0x180006ef4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180006ef9  mov     eax, ebx
0x180006efb  mov     rcx, [rsp+2B8h+var_38]
0x180006f03  xor     rcx, rsp; StackCookie
0x180006f06  call    __security_check_cookie
0x180006f0b  lea     r11, [rsp+2B8h+var_28]
0x180006f13  mov     rbx, [r11+40h]
0x180006f17  mov     rsi, [r11+48h]
0x180006f1b  mov     rsp, r11
0x180006f1e  pop     r15
0x180006f20  pop     r14
0x180006f22  pop     r13
0x180006f24  pop     r12
0x180006f26  pop     rdi
0x180006f27  retn
```
