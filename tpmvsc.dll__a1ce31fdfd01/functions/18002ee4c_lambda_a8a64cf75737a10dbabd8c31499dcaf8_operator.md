# _lambda_a8a64cf75737a10dbabd8c31499dcaf8_::operator()

- ea: `0x18002ee4c`
- end: `0x18002f08a`
- name: `_lambda_a8a64cf75737a10dbabd8c31499dcaf8_::operator()`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18002c644`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18000d368`
- `0x180015384`
- `0x180015638`
- `0x180016040`
- `0x1800215d0`
- `0x180027eac`
- `0x180029cb8`
- `0x18002ee4c`
- `0x18003031c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ee7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ee7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f06a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ef14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f06a`

## string_xrefs

- `0x18002f016`: `Unable to copy container name string`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_a8a64cf75737a10dbabd8c31499dcaf8_::operator()(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 v3; // rcx
  int AikContainerNameLocking; // edi
  struct VCHANNEL_DATA **v6; // rcx
  unsigned __int64 v7; // rdi
  __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // r9
  __int64 v11; // rcx
  void *v12; // [rsp+30h] [rbp-19h] BYREF
  _QWORD v13[2]; // [rsp+38h] [rbp-11h] BYREF
  __int16 v14; // [rsp+48h] [rbp-1h]
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+50h] [rbp+7h]
  _BYTE v16[16]; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v17; // [rsp+68h] [rbp+1Fh]

  v2 = (struct _RTL_CRITICAL_SECTION *)(**(_QWORD **)a1 + 8LL);
  EnterCriticalSection(v2);
  v15 = v2;
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v16);
  AikContainerNameLocking = I_GetAikContainerNameLocking(**(struct VCHANNEL_DATA ***)a1);
  if ( AikContainerNameLocking )
  {
    WppTraceIndent(v3, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        122,
        (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
        (_DWORD)WPP_pszIndent,
        AikContainerNameLocking,
        (__int64)"Unable to get AIK container name");
    }
    goto LABEL_6;
  }
  v12 = 0;
  v6 = *(struct VCHANNEL_DATA ***)a1;
  v13[0] = &v12;
  v13[1] = v6;
  v14 = 256;
  v7 = 2 * v17 + 2;
  v12 = I_Alloc(*(const struct VCARD_DATA **)*v6, v7);
  if ( !v12 )
  {
    WppTraceIndent(v8, 2u);
    AikContainerNameLocking = 14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        123,
        (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
        (_DWORD)WPP_pszIndent,
        14,
        (__int64)"Unable to allocate container name buffer");
    }
LABEL_14:
    wil::details::ScopeExitFnGuard__lambda_c6892442b8a6d56ce08e6517610ee184___::operator()(v13);
LABEL_6:
    std::wstring::_Tidy_deallocate((__int64)v16);
    if ( v2 )
      LeaveCriticalSection(v2);
    return (unsigned int)AikContainerNameLocking;
  }
  v9 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  AikContainerNameLocking = StringCbCopyW(v10, v7, v9);
  if ( AikContainerNameLocking < 0 )
  {
    WppTraceIndent(v11, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        124,
        (unsigned int)WPP_19641971e2e2383bda07edbd33517adf_Traceguids,
        (_DWORD)WPP_GLOBAL_Control,
        AikContainerNameLocking,
        (__int64)"Unable to copy container name string");
    }
    goto LABEL_14;
  }
  ***(_QWORD ***)(a1 + 16) = v12;
  v12 = 0;
  wil::details::ScopeExitFnGuard__lambda_c6892442b8a6d56ce08e6517610ee184___::operator()(v13);
  std::wstring::_Tidy_deallocate((__int64)v16);
  if ( v2 )
    LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x18002ee4c  push    rbp
0x18002ee4e  push    rbx
0x18002ee4f  push    rsi
0x18002ee50  push    rdi
0x18002ee51  lea     rbp, [rsp-3Fh]
0x18002ee56  sub     rsp, 88h
0x18002ee5d  mov     rax, cs:__security_cookie
0x18002ee64  xor     rax, rsp
0x18002ee67  mov     [rbp+57h+var_28], rax
0x18002ee6b  mov     rsi, rcx
0x18002ee6e  mov     rax, [rcx]
0x18002ee71  mov     rbx, [rax]
0x18002ee74  add     rbx, 8
0x18002ee78  mov     rcx, rbx; lpCriticalSection
0x18002ee7b  call    cs:__imp_EnterCriticalSection
0x18002ee81  mov     [rbp+57h+var_50], rbx
0x18002ee85  lea     rcx, [rbp+57h+var_48]
0x18002ee89  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002ee8e  nop
0x18002ee8f  mov     rdx, [rsi+8]
0x18002ee93  mov     rcx, [rsi]
0x18002ee96  lea     r8, [rbp+57h+var_48]
0x18002ee9a  mov     dl, [rdx]
0x18002ee9c  mov     rcx, [rcx]; struct VCHANNEL_DATA *
0x18002ee9f  call    ?I_GetAikContainerNameLocking@@YAKPEAUVCHANNEL_DATA@@EPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; I_GetAikContainerNameLocking(VCHANNEL_DATA *,uchar,std::wstring *)
0x18002eea4  mov     edi, eax
0x18002eea6  test    eax, eax
0x18002eea8  jz      short loc_18002EF21
0x18002eeaa  mov     edx, 2
0x18002eeaf  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002eeb4  lea     rcx, WPP_GLOBAL_Control
0x18002eebb  mov     r10, cs:WPP_GLOBAL_Control
0x18002eec2  cmp     r10, rcx
0x18002eec5  jz      short loc_18002EF02
0x18002eec7  test    byte ptr [r10+1Ch], 1
0x18002eecc  jz      short loc_18002EF02
0x18002eece  cmp     byte ptr [r10+19h], 2
0x18002eed3  jb      short loc_18002EF02
0x18002eed5  mov     edx, 7Ah ; 'z'
0x18002eeda  lea     rax, aUnableToGetAik_0; "Unable to get AIK container name"
0x18002eee1  mov     [rsp+0A0h+var_78], rax
0x18002eee6  mov     [rsp+0A0h+var_80], edi
0x18002eeea  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002eef1  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x18002eef8  mov     rcx, [r10+10h]
0x18002eefc  call    WPP_SF_sDs
0x18002ef01  nop
0x18002ef02  lea     rcx, [rbp+57h+var_48]
0x18002ef06  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002ef0b  nop
0x18002ef0c  test    rbx, rbx
0x18002ef0f  jz      short loc_18002EF1A
0x18002ef11  mov     rcx, rbx; lpCriticalSection
0x18002ef14  call    cs:__imp_LeaveCriticalSection
0x18002ef1a  mov     eax, edi
0x18002ef1c  jmp     loc_18002F072
0x18002ef21  mov     [rbp+57h+var_70], 0
0x18002ef29  mov     rcx, [rsi]
0x18002ef2c  lea     rax, [rbp+57h+var_70]
0x18002ef30  mov     [rbp+57h+var_68], rax
0x18002ef34  mov     [rbp+57h+var_60], rcx
0x18002ef38  mov     [rbp+57h+var_58], 100h
0x18002ef3e  mov     rax, [rbp+57h+var_38]
0x18002ef42  lea     rdi, ds:2[rax*2]
0x18002ef4a  mov     rcx, [rcx]
0x18002ef4d  mov     rdx, rdi; unsigned __int64
0x18002ef50  mov     rcx, [rcx]; struct VCARD_DATA *
0x18002ef53  call    ?I_Alloc@@YAPEAXPEBUVCARD_DATA@@_K@Z; I_Alloc(VCARD_DATA const *,unsigned __int64)
0x18002ef58  mov     r9, rax
0x18002ef5b  mov     [rbp+57h+var_70], rax
0x18002ef5f  test    rax, rax
0x18002ef62  jnz     short loc_18002EFC9
0x18002ef64  lea     edx, [rax+2]
0x18002ef67  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002ef6c  lea     rcx, WPP_GLOBAL_Control
0x18002ef73  mov     edi, 0Eh
0x18002ef78  mov     rax, cs:WPP_GLOBAL_Control
0x18002ef7f  cmp     rax, rcx
0x18002ef82  jz      short loc_18002EFBB
0x18002ef84  test    byte ptr [rax+1Ch], 1
0x18002ef88  jz      short loc_18002EFBB
0x18002ef8a  cmp     byte ptr [rax+19h], 2
0x18002ef8e  jb      short loc_18002EFBB
0x18002ef90  lea     edx, [rdi+6Dh]
0x18002ef93  lea     rcx, aUnableToAlloca; "Unable to allocate container name buffe"...
0x18002ef9a  mov     [rsp+0A0h+var_78], rcx
0x18002ef9f  mov     [rsp+0A0h+var_80], edi
0x18002efa3  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002efaa  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x18002efb1  mov     rcx, [rax+10h]
0x18002efb5  call    WPP_SF_sDs
0x18002efba  nop
0x18002efbb  lea     rcx, [rbp+57h+var_68]
0x18002efbf  call    wil__details__ScopeExitFnGuard__lambda_c6892442b8a6d56ce08e6517610ee184_____operator__
0x18002efc4  jmp     loc_18002EF02
0x18002efc9  lea     rcx, [rbp+57h+var_48]
0x18002efcd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002efd2  mov     r8, rax; unsigned __int16 *
0x18002efd5  mov     rdx, rdi; unsigned __int64
0x18002efd8  mov     rcx, r9; unsigned __int16 *
0x18002efdb  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002efe0  mov     edi, eax
0x18002efe2  test    eax, eax
0x18002efe4  jns     short loc_18002F038
0x18002efe6  mov     edx, 2
0x18002efeb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002eff0  lea     rcx, WPP_GLOBAL_Control
0x18002eff7  mov     r9, cs:WPP_GLOBAL_Control
0x18002effe  cmp     r9, rcx
0x18002f001  jz      short loc_18002EFBB
0x18002f003  test    byte ptr [r9+1Ch], 1
0x18002f008  jz      short loc_18002EFBB
0x18002f00a  cmp     byte ptr [r9+19h], 2
0x18002f00f  jb      short loc_18002EFBB
0x18002f011  mov     edx, 7Ch ; '|'
0x18002f016  lea     rax, aUnableToCopyCo; "Unable to copy container name string"
0x18002f01d  mov     [rsp+0A0h+var_78], rax
0x18002f022  mov     [rsp+0A0h+var_80], edi
0x18002f026  lea     r8, WPP_19641971e2e2383bda07edbd33517adf_Traceguids
0x18002f02d  mov     rcx, [r9+10h]
0x18002f031  call    WPP_SF_sds
0x18002f036  jmp     short loc_18002EFBB
0x18002f038  mov     rax, [rsi+10h]
0x18002f03c  mov     rcx, [rax]
0x18002f03f  mov     rax, [rbp+57h+var_70]
0x18002f043  mov     [rcx], rax
0x18002f046  mov     [rbp+57h+var_70], 0
0x18002f04e  lea     rcx, [rbp+57h+var_68]
0x18002f052  call    wil__details__ScopeExitFnGuard__lambda_c6892442b8a6d56ce08e6517610ee184_____operator__
0x18002f057  nop
0x18002f058  lea     rcx, [rbp+57h+var_48]
0x18002f05c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f061  nop
0x18002f062  test    rbx, rbx
0x18002f065  jz      short loc_18002F070
0x18002f067  mov     rcx, rbx; lpCriticalSection
0x18002f06a  call    cs:__imp_LeaveCriticalSection
0x18002f070  xor     eax, eax
0x18002f072  mov     rcx, [rbp+57h+var_28]
0x18002f076  xor     rcx, rsp; StackCookie
0x18002f079  call    __security_check_cookie
0x18002f07e  add     rsp, 88h
0x18002f085  pop     rdi
0x18002f086  pop     rsi
0x18002f087  pop     rbx
0x18002f088  pop     rbp
0x18002f089  retn
```
