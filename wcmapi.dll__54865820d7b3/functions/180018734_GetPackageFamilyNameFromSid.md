# GetPackageFamilyNameFromSid

- ea: `0x180018734`
- end: `0x1800188b5`
- name: `GetPackageFamilyNameFromSid`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180007754`

## callees

- `0x180007a70`
- `0x180008a90`
- `0x180018040`
- `0x1800180c4`
- `0x1800184c4`
- `0x180018500`
- `0x180018734`
- `0x180018d58`
- `0x180018d84`
- `0x180018e48`
- `0x180018fc4`
- `0x18001902c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180018770`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180018770`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetPackageFamilyNameFromSid(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  const OLECHAR *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // r10
  void *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // r10
  int v27; // r9d
  int v29; // [rsp+20h] [rbp-58h]
  GUID pclsid; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v31[32]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  pclsid = 0;
  v6 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, a2, a3, a4);
  if ( CLSIDFromString(v6, &pclsid) >= 0 )
  {
    v12 = *(void **)(a2 + 16);
    if ( (unsigned __int64)v12 <= 1 )
      wil::details::in1diag3::_FailFast_Hr(retaddr, v12, v8, (const char *)0x8000FFFFLL, v29);
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v12, v8, v9);
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v14 - 1, v13 + 2 * (v14 - 1), v15);
    std::wstring::wstring(v31, v16 + 2);
    v17 = std::_WChar_traits<unsigned short>::length(L"_0000000000000");
    std::wstring::_Append<unsigned short>(v31, v18, v17);
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v19, v20, v21);
      v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31, v23, v24, v22);
      WPP_SF_SS(*(_QWORD *)(v26 + 16), 17, (unsigned int)WPP_c091792df07e35dda6dca04425677804_Traceguids, v27, v25);
    }
    std::wstring::wstring(a1, v31);
    std::wstring::_Tidy_deallocate(v31);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v7, v8, v9);
      WPP_SF_S(*(_QWORD *)(v11 + 16), 16, WPP_c091792df07e35dda6dca04425677804_Traceguids, v10);
    }
    std::wstring::wstring(a1, a2);
  }
  return a1;
}

```

## disassembly

```asm
0x180018734  mov     [rsp+arg_10], rbx
0x180018739  push    rdi
0x18001873a  sub     rsp, 70h
0x18001873e  mov     rax, cs:__security_cookie
0x180018745  xor     rax, rsp
0x180018748  mov     [rsp+78h+var_10], rax
0x18001874d  mov     rdi, rdx
0x180018750  mov     rbx, rcx
0x180018753  mov     qword ptr [rsp+78h+pclsid.Data1], rcx
0x180018758  xorps   xmm0, xmm0
0x18001875b  movups  xmmword ptr [rsp+78h+pclsid.Data1], xmm0
0x180018760  mov     rcx, rdx
0x180018763  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018768  lea     rdx, [rsp+78h+pclsid]; pclsid
0x18001876d  mov     rcx, rax; lpsz
0x180018770  call    cs:__imp_CLSIDFromString
0x180018777  nop     dword ptr [rax+rax+00h]
0x18001877c  test    eax, eax
0x18001877e  jns     short loc_1800187D1
0x180018780  lea     rax, WPP_GLOBAL_Control
0x180018787  mov     r10, cs:WPP_GLOBAL_Control
0x18001878e  cmp     r10, rax
0x180018791  jz      short loc_1800187C1
0x180018793  cmp     byte ptr [r10+19h], 4
0x180018798  jb      short loc_1800187C1
0x18001879a  test    byte ptr [r10+1Ch], 1
0x18001879f  jz      short loc_1800187C1
0x1800187a1  mov     rcx, rdi
0x1800187a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800187a9  mov     edx, 10h
0x1800187ae  mov     r9, rax
0x1800187b1  lea     r8, WPP_c091792df07e35dda6dca04425677804_Traceguids
0x1800187b8  mov     rcx, [r10+10h]
0x1800187bc  call    WPP_SF_S
0x1800187c1  mov     rdx, rdi
0x1800187c4  mov     rcx, rbx
0x1800187c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800187cc  jmp     loc_180018896
0x1800187d1  mov     rdx, [rdi+10h]; void *
0x1800187d5  mov     rcx, [rsp+78h]; this
0x1800187da  cmp     rdx, 1
0x1800187de  ja      short loc_1800187EC
0x1800187e0  mov     r9d, 8000FFFFh; char *
0x1800187e6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800187ec  mov     rcx, rdi
0x1800187ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800187f4  dec     rdx
0x1800187f7  lea     r8, [rax+rdx*2]
0x1800187fb  mov     rcx, rdi
0x1800187fe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018803  lea     rdx, [rax+2]
0x180018807  lea     rcx, [rsp+78h+var_30]
0x18001880c  call    ??$?0V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<ushort> const &)
0x180018811  nop
0x180018812  lea     rcx, ?c_szPFNNullPublisher@@3QBGB; "_0000000000000"
0x180018819  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18001881e  mov     r8, rax
0x180018821  mov     rdx, rcx
0x180018824  lea     rcx, [rsp+78h+var_30]
0x180018829  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001882e  lea     rax, WPP_GLOBAL_Control
0x180018835  mov     r10, cs:WPP_GLOBAL_Control
0x18001883c  cmp     r10, rax
0x18001883f  jz      short loc_18001887E
0x180018841  cmp     byte ptr [r10+19h], 4
0x180018846  jb      short loc_18001887E
0x180018848  test    byte ptr [r10+1Ch], 1
0x18001884d  jz      short loc_18001887E
0x18001884f  mov     rcx, rdi
0x180018852  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018857  mov     r9, rax
0x18001885a  lea     rcx, [rsp+78h+var_30]
0x18001885f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180018864  mov     edx, 11h
0x180018869  mov     qword ptr [rsp+78h+var_58], rax
0x18001886e  lea     r8, WPP_c091792df07e35dda6dca04425677804_Traceguids
0x180018875  mov     rcx, [r10+10h]
0x180018879  call    WPP_SF_SS
0x18001887e  lea     rdx, [rsp+78h+var_30]
0x180018883  mov     rcx, rbx
0x180018886  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001888b  nop
0x18001888c  lea     rcx, [rsp+78h+var_30]
0x180018891  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018896  mov     rax, rbx
0x180018899  mov     rcx, [rsp+78h+var_10]
0x18001889e  xor     rcx, rsp; StackCookie
0x1800188a1  call    __security_check_cookie
0x1800188a6  mov     rbx, [rsp+78h+arg_10]
0x1800188ae  add     rsp, 70h
0x1800188b2  pop     rdi
0x1800188b3  retn
```
