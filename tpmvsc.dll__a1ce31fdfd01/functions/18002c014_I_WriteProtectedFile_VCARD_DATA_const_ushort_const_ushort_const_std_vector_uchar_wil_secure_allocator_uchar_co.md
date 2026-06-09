# I_WriteProtectedFile(VCARD_DATA const *,ushort const *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> const &)

- ea: `0x18002c014`
- end: `0x18002c1b8`
- name: `?I_WriteProtectedFile@@YAKPEBUVCARD_DATA@@PEBG1AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010cdc`
- `0x180010e90`
- `0x1800110c0`
- `0x180013434`
- `0x1800135d4`
- `0x180014954`

## callees

- `0x180001ec0`
- `0x18000653c`
- `0x18000bc48`
- `0x18000bf8c`
- `0x18000c198`
- `0x18002a1dc`
- `0x18002a4e0`
- `0x18002b1d0`
- `0x18002bd24`
- `0x18002c014`
- `0x1800348a0`

## string_xrefs

- `0x18002c158`: `Unable to write file`
- `0x18002c04f`: `I_WriteProtectedFile`

## pseudocode

```c
__int64 __fastcall I_WriteProtectedFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  int v12; // edx
  const char *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  unsigned int v17; // [rsp+30h] [rbp-29h] BYREF
  int v18; // [rsp+34h] [rbp-25h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp-21h] BYREF
  _QWORD v20[3]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v21[24]; // [rsp+58h] [rbp-1h] BYREF
  char v22[24]; // [rsp+70h] [rbp+17h] BYREF

  v17 = 0;
  v18 = 0;
  strcpy(v22, "I_WriteProtectedFile");
  v20[0] = v22;
  v20[1] = &v18;
  v20[2] = &v17;
  lambda_56c9486e220eeefce980ce0cb946db83_::operator()(v20);
  v18 = 1;
  v19 = v20;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v21);
  v17 = I_ProtectData(a4, v21);
  if ( v17 )
  {
    WppTraceIndent(v10, 2);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_18;
    }
    v12 = 45;
    v13 = "Unable to protect file";
    goto LABEL_17;
  }
  v17 = I_WriteFile(a1, a2, a3, (__int64)v21);
  if ( !v17 )
  {
    v15 = 0;
    goto LABEL_20;
  }
  WppTraceIndent(v14, 2);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 46;
    v13 = "Unable to write file";
LABEL_17:
    WPP_SF_sDs(
      v11[2],
      v12,
      (unsigned int)&WPP_07138201f8c239aeb1d90374442b236d_Traceguids,
      (_DWORD)WPP_pszIndent,
      v17,
      (__int64)v13);
  }
LABEL_18:
  v15 = v17;
LABEL_20:
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(v21);
  WppTraceUnwinder__lambda_56c9486e220eeefce980ce0cb946db83____::_WppTraceUnwinder__lambda_56c9486e220eeefce980ce0cb946db83____(&v19);
  return v15;
}

```

## disassembly

```asm
0x18002c014  push    rbp
0x18002c016  push    rbx
0x18002c017  push    rsi
0x18002c018  push    rdi
0x18002c019  push    r14
0x18002c01b  lea     rbp, [rsp-37h]
0x18002c020  sub     rsp, 90h
0x18002c027  mov     rax, cs:__security_cookie
0x18002c02e  xor     rax, rsp
0x18002c031  mov     [rbp+57h+var_28], rax
0x18002c035  mov     r14, r9
0x18002c038  mov     rdi, r8
0x18002c03b  mov     rbx, rdx
0x18002c03e  mov     rsi, rcx
0x18002c041  mov     [rbp+57h+var_80], 0
0x18002c048  mov     [rbp+57h+var_7C], 0
0x18002c04f  movups  xmm0, xmmword ptr cs:aIWriteprotecte; "I_WriteProtectedFile"
0x18002c056  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18002c05a  movsd   xmm1, qword ptr cs:aIWriteprotecte+0Dh; "tedFile"
0x18002c062  movsd   qword ptr [rbp+57h+var_40+0Dh], xmm1
0x18002c067  lea     rax, [rbp+57h+var_40]
0x18002c06b  mov     [rbp+57h+var_70], rax
0x18002c06f  lea     rax, [rbp+57h+var_7C]
0x18002c073  mov     [rbp+57h+var_68], rax
0x18002c077  lea     rax, [rbp+57h+var_80]
0x18002c07b  mov     [rbp+57h+var_60], rax
0x18002c07f  lea     rcx, [rbp+57h+var_70]
0x18002c083  call    _lambda_56c9486e220eeefce980ce0cb946db83___operator__
0x18002c088  mov     [rbp+57h+var_7C], 1
0x18002c08f  lea     rax, [rbp+57h+var_70]
0x18002c093  mov     [rbp+57h+var_78], rax
0x18002c097  test    rsi, rsi
0x18002c09a  jnz     short loc_18002C0A1
0x18002c09c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c0a1  test    rbx, rbx
0x18002c0a4  jnz     short loc_18002C0AB
0x18002c0a6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c0ab  test    rdi, rdi
0x18002c0ae  jnz     short loc_18002C0B5
0x18002c0b0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002c0b5  lea     rcx, [rbp+57h+var_58]
0x18002c0b9  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18002c0be  nop
0x18002c0bf  lea     rdx, [rbp+57h+var_58]
0x18002c0c3  mov     rcx, r14
0x18002c0c6  call    ?I_ProtectData@@YAKAEBV?$vector@EU?$secure_allocator@E@wil@@@std@@PEAV12@@Z; I_ProtectData(std::vector<uchar,wil::secure_allocator<uchar>> const &,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x18002c0cb  mov     [rbp+57h+var_80], eax
0x18002c0ce  test    eax, eax
0x18002c0d0  jz      short loc_18002C111
0x18002c0d2  mov     edx, 2
0x18002c0d7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c0dc  lea     rax, WPP_GLOBAL_Control
0x18002c0e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0ea  cmp     rcx, rax
0x18002c0ed  jz      loc_18002C182
0x18002c0f3  test    byte ptr [rcx+1Ch], 1
0x18002c0f7  jz      loc_18002C182
0x18002c0fd  cmp     byte ptr [rcx+19h], 2
0x18002c101  jb      short loc_18002C182
0x18002c103  mov     edx, 2Dh ; '-'
0x18002c108  lea     rax, aUnableToProtec; "Unable to protect file"
0x18002c10f  jmp     short loc_18002C15F
0x18002c111  lea     r9, [rbp+57h+var_58]
0x18002c115  mov     r8, rdi
0x18002c118  mov     rdx, rbx
0x18002c11b  mov     rcx, rsi
0x18002c11e  call    ?I_WriteFile@@YAKPEBUVCARD_DATA@@PEBG1AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_WriteFile(VCARD_DATA const *,ushort const *,ushort const *,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x18002c123  mov     [rbp+57h+var_80], eax
0x18002c126  test    eax, eax
0x18002c128  jz      short loc_18002C187
0x18002c12a  mov     edx, 2
0x18002c12f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002c134  lea     rax, WPP_GLOBAL_Control
0x18002c13b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c142  cmp     rcx, rax
0x18002c145  jz      short loc_18002C182
0x18002c147  test    byte ptr [rcx+1Ch], 1
0x18002c14b  jz      short loc_18002C182
0x18002c14d  cmp     byte ptr [rcx+19h], 2
0x18002c151  jb      short loc_18002C182
0x18002c153  mov     edx, 2Eh ; '.'
0x18002c158  lea     rax, aUnableToWriteF; "Unable to write file"
0x18002c15f  mov     [rsp+0B0h+var_88], rax
0x18002c164  mov     eax, [rbp+57h+var_80]
0x18002c167  mov     [rsp+0B0h+var_90], eax
0x18002c16b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002c172  lea     r8, WPP_07138201f8c239aeb1d90374442b236d_Traceguids
0x18002c179  mov     rcx, [rcx+10h]
0x18002c17d  call    WPP_SF_sDs
0x18002c182  mov     ebx, [rbp+57h+var_80]
0x18002c185  jmp     short loc_18002C189
0x18002c187  xor     ebx, ebx
0x18002c189  lea     rcx, [rbp+57h+var_58]
0x18002c18d  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18002c192  nop
0x18002c193  lea     rcx, [rbp+57h+var_78]
0x18002c197  call    WppTraceUnwinder__lambda_56c9486e220eeefce980ce0cb946db83_______WppTraceUnwinder__lambda_56c9486e220eeefce980ce0cb946db83____
0x18002c19c  mov     eax, ebx
0x18002c19e  mov     rcx, [rbp+57h+var_28]
0x18002c1a2  xor     rcx, rsp; StackCookie
0x18002c1a5  call    __security_check_cookie
0x18002c1aa  add     rsp, 90h
0x18002c1b1  pop     r14
0x18002c1b3  pop     rdi
0x18002c1b4  pop     rsi
0x18002c1b5  pop     rbx
0x18002c1b6  pop     rbp
0x18002c1b7  retn
```
