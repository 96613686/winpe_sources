# WcmConnectionMappingPolicyKey::ReadFromRegistry(ATL::CRegKey &)

- ea: `0x180007754`
- end: `0x180007a69`
- name: `?ReadFromRegistry@WcmConnectionMappingPolicyKey@@QEAAJAEAVCRegKey@ATL@@@Z`
- size: `789`
- prototype: `int(WcmConnectionMappingPolicyKey *__hidden this, struct ATL::CRegKey *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180006750`
- `0x1800176c0`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180007754`
- `0x180007a70`
- `0x180008a90`
- `0x18001728c`
- `0x1800185e8`
- `0x180018734`
- `0x1800188bc`
- `0x180018f18`
- `0x18001ae30`

## string_xrefs

- `0x1800077a4`: `WcmConnectionMappingPolicyKey::ReadFromRegistry`
- `0x180007a27`: `WcmConnectionMappingPolicyKey::ReadFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall WcmConnectionMappingPolicyKey::ReadFromRegistry(
        WcmConnectionMappingPolicyKey *this,
        struct ATL::CRegKey *a2)
{
  signed int v4; // ebx
  WcmPolicyManager *v5; // rcx
  bool v6; // sf
  int StringValue; // edi
  int v8; // edi
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 PackageFamilyNameFromSid; // rax
  int v12; // edi
  _BYTE v14[32]; // [rsp+38h] [rbp-80h] BYREF
  unsigned int v15; // [rsp+58h] [rbp-60h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_c091792df07e35dda6dca04425677804_Traceguids,
      "WcmConnectionMappingPolicyKey::ReadFromRegistry");
  }
  v15 = 0;
  v4 = ATL::CRegKey::QueryDWORDValue(a2, L"Version", &v15);
  if ( !v4 )
  {
    v5 = WPP_GLOBAL_Control;
    goto LABEL_13;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"Version");
    v5 = WPP_GLOBAL_Control;
  }
  v6 = v4 < 0;
  if ( v4 > 0 )
  {
    v4 = (unsigned __int16)v4 | 0x80070000;
LABEL_13:
    v6 = v4 < 0;
  }
  if ( v6 )
  {
    if ( v4 != -2147024894 )
      goto LABEL_45;
    v4 = 0;
    v15 = 1;
  }
  else if ( v15 != 1 )
  {
    v4 = -2147418113;
    goto LABEL_45;
  }
  StringValue = QueryStringValue(a2, L"PolicyContext");
  if ( StringValue )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"PolicyContext");
      v5 = WPP_GLOBAL_Control;
    }
    if ( StringValue > 0 )
      v4 = (unsigned __int16)StringValue | 0x80070000;
    else
      v4 = StringValue;
  }
  else
  {
    std::wstring::wstring(v16);
    v8 = QueryStringValue(a2, L"ClientIdentifier");
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ClientIdentifier");
      }
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      else
        v4 = v8;
      std::wstring::_Tidy_deallocate(v16);
      v5 = WPP_GLOBAL_Control;
    }
    else
    {
      PackageFamilyNameFromSid = GetPackageFamilyNameFromSid((__int64)v14, (__int64)v16, v9, v10);
      std::wstring::operator=((char *)this + 48, PackageFamilyNameFromSid);
      std::wstring::_Tidy_deallocate(v14);
      v12 = QueryStringValue(a2, L"Host");
      if ( v12 )
      {
        if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"Host");
        }
        if ( v12 > 0 )
          v4 = (unsigned __int16)v12 | 0x80070000;
        else
          v4 = v12;
      }
      std::wstring::_Tidy_deallocate(v16);
      v5 = WPP_GLOBAL_Control;
    }
  }
LABEL_45:
  if ( v5 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 5u && (*((_BYTE *)v5 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v5 + 2),
      22,
      (unsigned int)WPP_c091792df07e35dda6dca04425677804_Traceguids,
      (unsigned int)"WcmConnectionMappingPolicyKey::ReadFromRegistry",
      v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007754  mov     [rsp+arg_10], rbx
0x180007759  push    rsi
0x18000775a  push    rdi
0x18000775b  push    r12
0x18000775d  push    r13
0x18000775f  push    r15
0x180007761  sub     rsp, 90h
0x180007768  mov     rax, cs:__security_cookie
0x18000776f  xor     rax, rsp
0x180007772  mov     [rsp+0B8h+var_38], rax
0x18000777a  mov     r15, rdx
0x18000777d  mov     r13, rcx
0x180007780  lea     rsi, WPP_GLOBAL_Control
0x180007787  mov     rcx, cs:WPP_GLOBAL_Control
0x18000778e  cmp     rcx, rsi
0x180007791  jz      short loc_1800077BB
0x180007793  cmp     byte ptr [rcx+19h], 5
0x180007797  jb      short loc_1800077BB
0x180007799  test    byte ptr [rcx+1Ch], 1
0x18000779d  jz      short loc_1800077BB
0x18000779f  mov     edx, 12h
0x1800077a4  lea     r9, aWcmconnectionm_2; "WcmConnectionMappingPolicyKey::ReadFrom"...
0x1800077ab  lea     r8, WPP_c091792df07e35dda6dca04425677804_Traceguids
0x1800077b2  mov     rcx, [rcx+10h]
0x1800077b6  call    WPP_SF_s
0x1800077bb  mov     [rsp+0B8h+var_60], 0
0x1800077c3  lea     r8, [rsp+0B8h+var_60]; unsigned int *
0x1800077c8  lea     rdi, ?c_szVersionRegValue@@3QBGB; "Version"
0x1800077cf  mov     rdx, rdi; unsigned __int16 *
0x1800077d2  mov     rcx, r15; this
0x1800077d5  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x1800077da  mov     ebx, eax
0x1800077dc  test    eax, eax
0x1800077de  jz      short loc_18000782B
0x1800077e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077e7  cmp     rcx, rsi
0x1800077ea  jz      short loc_18000781C
0x1800077ec  cmp     byte ptr [rcx+19h], 1
0x1800077f0  jb      short loc_18000781C
0x1800077f2  test    byte ptr [rcx+1Ch], 1
0x1800077f6  jz      short loc_18000781C
0x1800077f8  mov     edx, 17h
0x1800077fd  mov     [rsp+0B8h+var_98], rdi; __int64
0x180007802  mov     r9d, eax
0x180007805  lea     r8, WPP_c091792df07e35dda6dca04425677804_Traceguids
0x18000780c  mov     rcx, [rcx+10h]; LoggerHandle
0x180007810  call    WPP_SF_DS
0x180007815  mov     rcx, cs:WPP_GLOBAL_Control
0x18000781c  test    ebx, ebx
0x18000781e  jle     short loc_180007834
0x180007820  movzx   ebx, bx
0x180007823  or      ebx, 80070000h
0x180007829  jmp     short loc_180007832
0x18000782b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007832  test    ebx, ebx
0x180007834  jns     short loc_18000784F
0x180007836  cmp     ebx, 80070002h
0x18000783c  jnz     short loc_18000784A
0x18000783e  xor     ebx, ebx
0x180007840  mov     [rsp+0B8h+var_60], 1
0x180007848  jmp     short loc_180007860
0x18000784a  jmp     loc_180007A0D
0x18000784f  cmp     [rsp+0B8h+var_60], 1
0x180007854  jz      short loc_180007860
0x180007856  mov     ebx, 8000FFFFh
0x18000785b  jmp     loc_180007A0D
0x180007860  lea     r8, [r13+10h]
0x180007864  lea     r12, ?c_szPolicyContextRegValue@@3QBGB; "PolicyContext"
0x18000786b  mov     rdx, r12; unsigned __int16 *
0x18000786e  mov     rcx, r15; this
0x180007871  call    ?QueryStringValue@@YAKAEAVCRegKey@ATL@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; QueryStringValue(ATL::CRegKey &,ushort const *,std::wstring &)
0x180007876  mov     edi, eax
0x180007878  test    eax, eax
0x18000787a  jz      short loc_1800078CE
0x18000787c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007883  cmp     rcx, rsi
0x180007886  jz      short loc_1800078B8
0x180007888  cmp     byte ptr [rcx+19h], 1
0x18000788c  jb      short loc_1800078B8
0x18000788e  test    byte ptr [rcx+1Ch], 1
0x180007892  jz      short loc_1800078B8
0x180007894  mov     edx, 13h
0x180007899  mov     [rsp+0B8h+var_98], r12; __int64
0x18000789e  mov     r9d, eax
0x1800078a1  lea     r8, WPP_c091792df07e35dda6dca04425677804_Traceguids
0x1800078a8  mov     rcx, [rcx+10h]; LoggerHandle
0x1800078ac  call    WPP_SF_DS
0x1800078b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078b8  test    edi, edi
0x1800078ba  jg      short loc_1800078C0
0x1800078bc  mov     ebx, edi
0x1800078be  jmp     short loc_1800078C9
0x1800078c0  movzx   ebx, di
0x1800078c3  or      ebx, 80070000h
0x1800078c9  jmp     loc_180007A0D
0x1800078ce  lea     rcx, [rsp+0B8h+var_58]
0x1800078d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800078d8  nop
0x1800078d9  lea     r8, [rsp+0B8h+var_58]
0x1800078de  lea     r12, ?c_szClientIdentifierRegValue@@3QBGB; "ClientIdentifier"
0x1800078e5  mov     rdx, r12; unsigned __int16 *
0x1800078e8  mov     rcx, r15; this
0x1800078eb  call    ?QueryStringValue@@YAKAEAVCRegKey@ATL@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; QueryStringValue(ATL::CRegKey &,ushort const *,std::wstring &)
0x1800078f0  mov     edi, eax
0x1800078f2  test    eax, eax
0x1800078f4  jz      short loc_180007953
0x1800078f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078fd  cmp     rcx, rsi
0x180007900  jz      short loc_18000792B
0x180007902  cmp     byte ptr [rcx+19h], 1
0x180007906  jb      short loc_18000792B
0x180007908  test    byte ptr [rcx+1Ch], 1
0x18000790c  jz      short loc_18000792B
0x18000790e  mov     edx, 14h
0x180007913  mov     [rsp+0B8h+var_98], r12; __int64
0x180007918  mov     r9d, eax
0x18000791b  lea     r8, WPP_c091792df07e35dda6dca04425677804_Traceguids
0x180007922  mov     rcx, [rcx+10h]; LoggerHandle
0x180007926  call    WPP_SF_DS
0x18000792b  test    edi, edi
0x18000792d  jg      short loc_180007933
0x18000792f  mov     ebx, edi
0x180007931  jmp     short loc_18000793C
0x180007933  movzx   ebx, di
0x180007936  or      ebx, 80070000h
0x18000793c  lea     rcx, [rsp+0B8h+var_58]
0x180007941  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180007946  nop
0x180007947  mov     rcx, cs:WPP_GLOBAL_Control
0x18000794e  jmp     loc_180007A0D
0x180007953  lea     rdx, [rsp+0B8h+var_58]
0x180007958  lea     rcx, [rsp+0B8h+var_80]
0x18000795d  call    GetPackageFamilyNameFromSid
0x180007962  lea     rcx, [r13+30h]
0x180007966  mov     rdx, rax
0x180007969  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000796e  lea     rcx, [rsp+0B8h+var_80]
0x180007973  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180007978  lea     r8, [r13+50h]
0x18000797c  lea     r12, ?c_szHostRegValue@@3QBGB; "Host"
0x180007983  mov     rdx, r12; unsigned __int16 *
0x180007986  mov     rcx, r15; this
0x180007989  call    ?QueryStringValue@@YAKAEAVCRegKey@ATL@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; QueryStringValue(ATL::CRegKey &,ushort const *,std::wstring &)
0x18000798e  mov     edi, eax
0x180007990  test    eax, eax
0x180007992  jz      short loc_1800079EE
0x180007994  mov     rcx, cs:WPP_GLOBAL_Control
0x18000799b  cmp     rcx, rsi
0x18000799e  jz      short loc_1800079C9
0x1800079a0  cmp     byte ptr [rcx+19h], 1
0x1800079a4  jb      short loc_1800079C9
0x1800079a6  test    byte ptr [rcx+1Ch], 1
0x1800079aa  jz      short loc_1800079C9
0x1800079ac  mov     edx, 15h
0x1800079b1  mov     [rsp+0B8h+var_98], r12; __int64
0x1800079b6  mov     r9d, eax
0x1800079b9  lea     r8, WPP_c091792df07e35dda6dca04425677804_Traceguids
0x1800079c0  mov     rcx, [rcx+10h]; LoggerHandle
0x1800079c4  call    WPP_SF_DS
0x1800079c9  test    edi, edi
0x1800079cb  jg      short loc_1800079D1
0x1800079cd  mov     ebx, edi
0x1800079cf  jmp     short loc_1800079DA
0x1800079d1  movzx   ebx, di
0x1800079d4  or      ebx, 80070000h
0x1800079da  lea     rcx, [rsp+0B8h+var_58]
0x1800079df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800079e4  nop
0x1800079e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079ec  jmp     short loc_180007A0D
0x1800079ee  lea     rcx, [rsp+0B8h+var_58]
0x1800079f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800079f8  nop
0x1800079f9  jmp     short loc_180007A06
0x1800079fb  lea     rsi, WPP_GLOBAL_Control
0x180007a02  mov     ebx, [rsp+0B8h+var_88]
0x180007a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a0d  cmp     rcx, rsi
0x180007a10  jz      short loc_180007A3E
0x180007a12  cmp     byte ptr [rcx+19h], 5
0x180007a16  jb      short loc_180007A3E
0x180007a18  test    byte ptr [rcx+1Ch], 1
0x180007a1c  jz      short loc_180007A3E
0x180007a1e  mov     edx, 16h
0x180007a23  mov     dword ptr [rsp+0B8h+var_98], ebx
0x180007a27  lea     r9, aWcmconnectionm_2; "WcmConnectionMappingPolicyKey::ReadFrom"...
0x180007a2e  lea     r8, WPP_c091792df07e35dda6dca04425677804_Traceguids
0x180007a35  mov     rcx, [rcx+10h]
0x180007a39  call    WPP_SF_sL
0x180007a3e  mov     eax, ebx
0x180007a40  mov     rcx, [rsp+0B8h+var_38]
0x180007a48  xor     rcx, rsp; StackCookie
0x180007a4b  call    __security_check_cookie
0x180007a50  mov     rbx, [rsp+0B8h+arg_10]
0x180007a58  add     rsp, 90h
0x180007a5f  pop     r15
0x180007a61  pop     r13
0x180007a63  pop     r12
0x180007a65  pop     rdi
0x180007a66  pop     rsi
0x180007a67  retn
```
