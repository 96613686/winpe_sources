# I_SetVCardRoot(VCARD_DATA *,ushort const *)

- ea: `0x180028e48`
- end: `0x180028ff8`
- name: `?I_SetVCardRoot@@YAKPEAUVCARD_DATA@@PEBG@Z`
- size: `432`
- prototype: `__int64 __fastcall(struct VCARD_DATA *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180016954`
- `0x1800292e8`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x180015384`
- `0x180015638`
- `0x18001cb44`
- `0x18002707c`
- `0x1800272a4`
- `0x180027500`
- `0x180027830`
- `0x180028e48`
- `0x1800348a0`

## string_xrefs

- `0x180028f44`: `Empty path is provided`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_SetVCardRoot(struct VCARD_DATA *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rax
  unsigned __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int16 v10; // r9
  int v12; // [rsp+30h] [rbp-9h] BYREF
  int v13; // [rsp+34h] [rbp-5h] BYREF
  _QWORD *v14; // [rsp+38h] [rbp-1h] BYREF
  _QWORD v15[3]; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v16[16]; // [rsp+58h] [rbp+1Fh] BYREF
  unsigned __int64 v17; // [rsp+68h] [rbp+2Fh]
  unsigned __int64 v18; // [rsp+70h] [rbp+37h]
  char v19[16]; // [rsp+78h] [rbp+3Fh] BYREF

  v12 = 0;
  v13 = 0;
  strcpy(v19, "I_SetVCardRoot");
  v15[0] = v19;
  v15[1] = &v13;
  v15[2] = &v12;
  lambda_594311838cda77d16bbc3df9641771d7_::operator()(v15);
  v13 = 1;
  v14 = v15;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  std::wstring::wstring(v16, a2);
  if ( v17 )
  {
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
    if ( *(_WORD *)(v6 + 2 * v7 - 2) != 92 )
    {
      if ( v7 >= v18 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v16);
      }
      else
      {
        v17 = v7 + 1;
        v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v16);
        *(_WORD *)(v8 + 2 * v9) = v10;
        *(_WORD *)(v8 + 2 * v9 + 2) = 0;
      }
    }
    std::wstring::operator=((char *)a1 + 24, v16);
    goto LABEL_15;
  }
  WppTraceIndent(v4, 2);
  v5 = 87;
  v12 = 87;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sDs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
      (_DWORD)WPP_pszIndent,
      87,
      (__int64)"Empty path is provided");
LABEL_15:
    v5 = v12;
  }
  std::wstring::_Tidy_deallocate(v16);
  WppTraceUnwinder__lambda_594311838cda77d16bbc3df9641771d7____::_WppTraceUnwinder__lambda_594311838cda77d16bbc3df9641771d7____(&v14);
  return v5;
}

```

## disassembly

```asm
0x180028e48  mov     [rsp-8+arg_10], rbx
0x180028e4d  mov     [rsp-8+arg_18], rdi
0x180028e52  push    rbp
0x180028e53  lea     rbp, [rsp-57h]
0x180028e58  sub     rsp, 90h
0x180028e5f  mov     rax, cs:__security_cookie
0x180028e66  xor     rax, rsp
0x180028e69  mov     [rbp+57h+var_8], rax
0x180028e6d  mov     rbx, rdx
0x180028e70  mov     rdi, rcx
0x180028e73  mov     [rbp+57h+var_60], 0
0x180028e7a  mov     [rbp+57h+var_5C], 0
0x180028e81  movsd   xmm0, qword ptr cs:aISetvcardroot; "I_SetVCardRoot"
0x180028e89  movsd   qword ptr [rbp+57h+var_18], xmm0
0x180028e8e  mov     eax, dword ptr cs:aISetvcardroot+8; "rdRoot"
0x180028e94  mov     dword ptr [rbp+57h+var_18+8], eax
0x180028e97  movzx   eax, word ptr cs:aISetvcardroot+0Ch; "ot"
0x180028e9e  mov     word ptr [rbp+57h+var_18+0Ch], ax
0x180028ea2  mov     al, byte ptr cs:aISetvcardroot+0Eh; ""
0x180028ea8  mov     [rbp+57h+var_18+0Eh], al
0x180028eab  lea     rax, [rbp+57h+var_18]
0x180028eaf  mov     [rbp+57h+var_50], rax
0x180028eb3  lea     rax, [rbp+57h+var_5C]
0x180028eb7  mov     [rbp+57h+var_48], rax
0x180028ebb  lea     rax, [rbp+57h+var_60]
0x180028ebf  mov     [rbp+57h+var_40], rax
0x180028ec3  lea     rcx, [rbp+57h+var_50]
0x180028ec7  call    _lambda_594311838cda77d16bbc3df9641771d7___operator__
0x180028ecc  mov     [rbp+57h+var_5C], 1
0x180028ed3  lea     rax, [rbp+57h+var_50]
0x180028ed7  mov     [rbp+57h+var_58], rax
0x180028edb  test    rdi, rdi
0x180028ede  jnz     short loc_180028EE5
0x180028ee0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180028ee5  test    rbx, rbx
0x180028ee8  jnz     short loc_180028EEF
0x180028eea  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180028eef  mov     rdx, rbx
0x180028ef2  lea     rcx, [rbp+57h+var_38]
0x180028ef6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028efb  nop
0x180028efc  mov     r8, [rbp+57h+var_28]
0x180028f00  test    r8, r8
0x180028f03  jnz     short loc_180028F6D
0x180028f05  lea     edx, [r8+2]
0x180028f09  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180028f0e  mov     ebx, 57h ; 'W'
0x180028f13  mov     [rbp+57h+var_60], ebx
0x180028f16  lea     rax, WPP_GLOBAL_Control
0x180028f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f24  cmp     rcx, rax
0x180028f27  jz      loc_180028FC2
0x180028f2d  test    byte ptr [rcx+1Ch], 1
0x180028f31  jz      loc_180028FC2
0x180028f37  cmp     byte ptr [rcx+19h], 2
0x180028f3b  jb      loc_180028FC2
0x180028f41  lea     edx, [rbx-40h]
0x180028f44  lea     rax, aEmptyPathIsPro; "Empty path is provided"
0x180028f4b  mov     [rsp+90h+var_68], rax
0x180028f50  mov     [rsp+90h+var_70], ebx
0x180028f54  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180028f5b  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x180028f62  mov     rcx, [rcx+10h]
0x180028f66  call    WPP_SF_sDs
0x180028f6b  jmp     short loc_180028FBF
0x180028f6d  lea     rcx, [rbp+57h+var_38]
0x180028f71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180028f76  mov     r9d, 5Ch ; '\'
0x180028f7c  cmp     r9w, [rax+r8*2-2]
0x180028f82  jz      short loc_180028FB2
0x180028f84  lea     rcx, [rbp+57h+var_38]
0x180028f88  cmp     r8, [rbp+57h+var_20]
0x180028f8c  jnb     short loc_180028FAD
0x180028f8e  lea     rax, [r8+1]
0x180028f92  mov     [rbp+57h+var_28], rax
0x180028f96  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180028f9b  mov     rdx, rax
0x180028f9e  mov     [rax+r8*2], r9w
0x180028fa3  xor     eax, eax
0x180028fa5  mov     [rdx+r8*2+2], ax
0x180028fab  jmp     short loc_180028FB2
0x180028fad  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180028fb2  lea     rcx, [rdi+18h]
0x180028fb6  lea     rdx, [rbp+57h+var_38]
0x180028fba  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180028fbf  mov     ebx, [rbp+57h+var_60]
0x180028fc2  lea     rcx, [rbp+57h+var_38]
0x180028fc6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028fcb  nop
0x180028fcc  lea     rcx, [rbp+57h+var_58]
0x180028fd0  call    WppTraceUnwinder__lambda_594311838cda77d16bbc3df9641771d7_______WppTraceUnwinder__lambda_594311838cda77d16bbc3df9641771d7____
0x180028fd5  mov     eax, ebx
0x180028fd7  mov     rcx, [rbp+57h+var_8]
0x180028fdb  xor     rcx, rsp; StackCookie
0x180028fde  call    __security_check_cookie
0x180028fe3  lea     r11, [rsp+90h+var_s0]
0x180028feb  mov     rbx, [r11+20h]
0x180028fef  mov     rdi, [r11+28h]
0x180028ff3  mov     rsp, r11
0x180028ff6  pop     rbp
0x180028ff7  retn
```
