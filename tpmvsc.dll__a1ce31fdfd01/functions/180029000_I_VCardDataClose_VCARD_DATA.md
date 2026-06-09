# I_VCardDataClose(VCARD_DATA *)

- ea: `0x180029000`
- end: `0x180029130`
- name: `?I_VCardDataClose@@YAXPEAUVCARD_DATA@@@Z`
- size: `304`
- prototype: `void __fastcall(struct VCARD_DATA *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016740`
- `0x18002c4c0`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c124`
- `0x18000f3a4`
- `0x180015384`
- `0x180015ca8`
- `0x180027250`
- `0x1800276f4`
- `0x180027f5c`
- `0x180029000`
- `0x1800348a0`

## string_xrefs

- `0x180029025`: `I_VCardDataClose`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall I_VCardDataClose(struct VCARD_DATA *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rcx
  int v5; // r9d
  __int64 v6; // rcx
  void *v7; // rdx
  int v8; // [rsp+30h] [rbp-40h] BYREF
  _QWORD *v9; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v10[2]; // [rsp+40h] [rbp-30h] BYREF
  char v11[24]; // [rsp+50h] [rbp-20h] BYREF

  v8 = 0;
  strcpy(v11, "I_VCardDataClose");
  v10[0] = v11;
  v10[1] = &v8;
  lambda_1cb83f5109481786d7f6be5192320fb2_::operator()(v10);
  v8 = 1;
  v9 = v10;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3, v2);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 30, 0, 0) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0, v2);
    WppTraceIndent(v4, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          (unsigned int)WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids,
          v5,
          73);
    }
    __fastfail(0x649u);
  }
  *((_DWORD *)a1 + 4) = 0;
  *((_QWORD *)a1 + 5) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr() = 0;
  std::unique_ptr<KEY_MAPS_MEM>::reset((char *)a1 + 64, 0);
  v7 = (void *)*((_QWORD *)a1 + 10);
  *((_QWORD *)a1 + 10) = 0;
  if ( v7 )
    std::default_delete<PIN_MAPS_MEM>::operator()(v6, v7);
  I_CloseProviders(a1);
  WppTraceUnwinder__lambda_1cb83f5109481786d7f6be5192320fb2____::_WppTraceUnwinder__lambda_1cb83f5109481786d7f6be5192320fb2____(&v9);
}

```

## disassembly

```asm
0x180029000  mov     [rsp-8+arg_8], rbx
0x180029005  push    rbp
0x180029006  mov     rbp, rsp
0x180029009  sub     rsp, 70h
0x18002900d  mov     rax, cs:__security_cookie
0x180029014  xor     rax, rsp
0x180029017  mov     [rbp+var_8], rax
0x18002901b  mov     rbx, rcx
0x18002901e  mov     [rbp+var_40], 0
0x180029025  movups  xmm0, xmmword ptr cs:aIVcarddataclos; "I_VCardDataClose"
0x18002902c  movups  xmmword ptr [rbp+var_20], xmm0
0x180029030  mov     al, byte ptr cs:aIVcarddataclos+10h; ""
0x180029036  mov     [rbp+var_20+10h], al
0x180029039  lea     rax, [rbp+var_20]
0x18002903d  mov     [rbp+var_30], rax
0x180029041  lea     rax, [rbp+var_40]
0x180029045  mov     [rbp+var_28], rax
0x180029049  lea     rcx, [rbp+var_30]
0x18002904d  call    _lambda_1cb83f5109481786d7f6be5192320fb2___operator__
0x180029052  mov     [rbp+var_40], 1
0x180029059  lea     rax, [rbp+var_30]
0x18002905d  mov     [rbp+var_38], rax
0x180029061  test    rbx, rbx
0x180029064  jnz     short loc_18002906B
0x180029066  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002906b  xor     ecx, ecx
0x18002906d  xor     eax, eax
0x18002906f  lock cmpxchg [rbx+78h], ecx
0x180029074  jz      short loc_1800290C8
0x180029076  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002907b  mov     edx, 2
0x180029080  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180029085  lea     rax, WPP_GLOBAL_Control
0x18002908c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029093  cmp     rcx, rax
0x180029096  jz      short loc_1800290C1
0x180029098  test    byte ptr [rcx+1Ch], 1
0x18002909c  jz      short loc_1800290C1
0x18002909e  cmp     byte ptr [rcx+19h], 1
0x1800290a2  jb      short loc_1800290C1
0x1800290a4  mov     edx, 2Ch ; ','
0x1800290a9  mov     [rsp+70h+var_50], 649h
0x1800290b1  lea     r8, WPP_0b864d11e5aa35941b658d08f6a7e9ca_Traceguids
0x1800290b8  mov     rcx, [rcx+10h]
0x1800290bc  call    WPP_SF_sD
0x1800290c1  mov     ecx, 649h
0x1800290c6  int     29h; Win8: RtlFailFast(ecx)
0x1800290c8  mov     dword ptr [rbx+10h], 0
0x1800290cf  lea     rcx, [rbx+18h]
0x1800290d3  mov     qword ptr [rcx+10h], 0
0x1800290db  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800290e0  xor     edx, edx
0x1800290e2  mov     [rax], dx
0x1800290e5  lea     rcx, [rbx+40h]
0x1800290e9  call    ?reset@?$unique_ptr@UKEY_MAPS_MEM@@U?$default_delete@UKEY_MAPS_MEM@@@std@@@std@@QEAAXPEAUKEY_MAPS_MEM@@@Z; std::unique_ptr<KEY_MAPS_MEM>::reset(KEY_MAPS_MEM *)
0x1800290ee  mov     rdx, [rbx+50h]
0x1800290f2  mov     qword ptr [rbx+50h], 0
0x1800290fa  test    rdx, rdx
0x1800290fd  jz      short loc_180029104
0x1800290ff  call    ??R?$default_delete@UPIN_MAPS_MEM@@@std@@QEBAXPEAUPIN_MAPS_MEM@@@Z; std::default_delete<PIN_MAPS_MEM>::operator()(PIN_MAPS_MEM *)
0x180029104  mov     rcx, rbx; struct VCARD_DATA *
0x180029107  call    ?I_CloseProviders@@YAXPEAUVCARD_DATA@@@Z; I_CloseProviders(VCARD_DATA *)
0x18002910c  nop
0x18002910d  lea     rcx, [rbp+var_38]
0x180029111  call    WppTraceUnwinder__lambda_1cb83f5109481786d7f6be5192320fb2_______WppTraceUnwinder__lambda_1cb83f5109481786d7f6be5192320fb2____
0x180029116  mov     rcx, [rbp+var_8]
0x18002911a  xor     rcx, rsp; StackCookie
0x18002911d  call    __security_check_cookie
0x180029122  mov     rbx, [rsp+70h+arg_8]
0x18002912a  add     rsp, 70h
0x18002912e  pop     rbp
0x18002912f  retn
```
