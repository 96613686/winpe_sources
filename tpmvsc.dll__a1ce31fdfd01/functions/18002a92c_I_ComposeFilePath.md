# I_ComposeFilePath

- ea: `0x18002a92c`
- end: `0x18002aa5c`
- name: `I_ComposeFilePath`
- size: `304`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002aa64`
- `0x18002adec`
- `0x18002af40`
- `0x18002b4a4`
- `0x18002bd24`

## callees

- `0x180001ec0`
- `0x180015384`
- `0x180015a0c`
- `0x180027500`
- `0x180029fa0`
- `0x18002a1a4`
- `0x18002a414`
- `0x18002a92c`
- `0x1800348a0`

## string_xrefs

- `0x18002a95b`: `I_ComposeFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall I_ComposeFilePath(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  int v20; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v21; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v22[2]; // [rsp+30h] [rbp-30h] BYREF
  char v23[24]; // [rsp+40h] [rbp-20h] BYREF

  v20 = 0;
  strcpy(v23, "I_ComposeFilePath");
  v22[0] = v23;
  v22[1] = &v20;
  lambda_31d7ff9d33cc853ad1e480fb92e61e5c_::operator()(v22);
  v20 = 1;
  v21 = v22;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  std::wstring::operator=(a4, a1 + 24);
  if ( !*(_QWORD *)(a4 + 16)
    || (v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4), *(_WORD *)(v12 + 2 * v13 - 2) != 92) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10);
  }
  v14 = std::_WChar_traits<unsigned short>::length(a2);
  std::wstring::_Append<unsigned short>(a4, a2, v14);
  v16 = *(_QWORD *)(a4 + 16);
  if ( !v16
    || (v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4), *(_WORD *)(v17 + 2 * v16 - 2) != 92) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v15, v16);
  }
  v18 = std::_WChar_traits<unsigned short>::length(a3);
  std::wstring::_Append<unsigned short>(a4, a3, v18);
  return WppTraceUnwinder__lambda_31d7ff9d33cc853ad1e480fb92e61e5c____::_WppTraceUnwinder__lambda_31d7ff9d33cc853ad1e480fb92e61e5c____(&v21);
}

```

## disassembly

```asm
0x18002a92c  push    rbp
0x18002a92e  push    rbx
0x18002a92f  push    rsi
0x18002a930  push    rdi
0x18002a931  push    r14
0x18002a933  mov     rbp, rsp
0x18002a936  sub     rsp, 60h
0x18002a93a  mov     rax, cs:__security_cookie
0x18002a941  xor     rax, rsp
0x18002a944  mov     [rbp+var_8], rax
0x18002a948  mov     rbx, r9
0x18002a94b  mov     rdi, r8
0x18002a94e  mov     rsi, rdx
0x18002a951  mov     r14, rcx
0x18002a954  mov     [rbp+var_40], 0
0x18002a95b  movups  xmm0, xmmword ptr cs:aIComposefilepa; "I_ComposeFilePath"
0x18002a962  movups  xmmword ptr [rbp+var_20], xmm0
0x18002a966  movzx   eax, word ptr cs:aIComposefilepa+10h; "h"
0x18002a96d  mov     word ptr [rbp+var_20+10h], ax
0x18002a971  lea     rax, [rbp+var_20]
0x18002a975  mov     [rbp+var_30], rax
0x18002a979  lea     rax, [rbp+var_40]
0x18002a97d  mov     [rbp+var_28], rax
0x18002a981  lea     rcx, [rbp+var_30]
0x18002a985  call    _lambda_31d7ff9d33cc853ad1e480fb92e61e5c___operator__
0x18002a98a  mov     [rbp+var_40], 1
0x18002a991  lea     rax, [rbp+var_30]
0x18002a995  mov     [rbp+var_38], rax
0x18002a999  test    r14, r14
0x18002a99c  jnz     short loc_18002A9A3
0x18002a99e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a9a3  test    rsi, rsi
0x18002a9a6  jnz     short loc_18002A9AD
0x18002a9a8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a9ad  test    rdi, rdi
0x18002a9b0  jnz     short loc_18002A9B7
0x18002a9b2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a9b7  test    rbx, rbx
0x18002a9ba  jnz     short loc_18002A9C1
0x18002a9bc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a9c1  lea     rdx, [r14+18h]
0x18002a9c5  mov     rcx, rbx
0x18002a9c8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002a9cd  mov     r8, [rbx+10h]
0x18002a9d1  mov     r14d, 5Ch ; '\'
0x18002a9d7  test    r8, r8
0x18002a9da  jz      short loc_18002A9EC
0x18002a9dc  mov     rcx, rbx
0x18002a9df  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a9e4  cmp     r14w, [rax+r8*2-2]
0x18002a9ea  jz      short loc_18002A9F1
0x18002a9ec  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a9f1  mov     rcx, rsi
0x18002a9f4  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002a9f9  mov     r8, rax
0x18002a9fc  mov     rdx, rsi
0x18002a9ff  mov     rcx, rbx
0x18002aa02  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002aa07  mov     rdx, [rbx+10h]
0x18002aa0b  test    rdx, rdx
0x18002aa0e  jz      short loc_18002AA20
0x18002aa10  mov     rcx, rbx
0x18002aa13  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002aa18  cmp     r14w, [rax+rdx*2-2]
0x18002aa1e  jz      short loc_18002AA25
0x18002aa20  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002aa25  mov     rcx, rdi
0x18002aa28  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002aa2d  mov     r8, rax
0x18002aa30  mov     rdx, rdi
0x18002aa33  mov     rcx, rbx
0x18002aa36  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002aa3b  nop
0x18002aa3c  lea     rcx, [rbp+var_38]
0x18002aa40  call    WppTraceUnwinder__lambda_31d7ff9d33cc853ad1e480fb92e61e5c_______WppTraceUnwinder__lambda_31d7ff9d33cc853ad1e480fb92e61e5c____
0x18002aa45  mov     rcx, [rbp+var_8]
0x18002aa49  xor     rcx, rsp; StackCookie
0x18002aa4c  call    __security_check_cookie
0x18002aa51  add     rsp, 60h
0x18002aa55  pop     r14
0x18002aa57  pop     rdi
0x18002aa58  pop     rsi
0x18002aa59  pop     rbx
0x18002aa5a  pop     rbp
0x18002aa5b  retn
```
