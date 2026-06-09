# I_CreateAuthKey(VCARD_DATA const *,std::vector<uchar,wil::secure_allocator<uchar>> *)

- ea: `0x18001f42c`
- end: `0x18001f54f`
- name: `?I_CreateAuthKey@@YAKPEBUVCARD_DATA@@PEAV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180016954`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18001cda0`
- `0x18001dcf0`
- `0x18001f42c`
- `0x180028494`
- `0x1800348a0`

## string_xrefs

- `0x18001f460`: `I_CreateAuthKey`

## pseudocode

```c
__int64 __fastcall I_CreateAuthKey(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  unsigned int RandomData; // [rsp+30h] [rbp-40h] BYREF
  int v10; // [rsp+34h] [rbp-3Ch] BYREF
  _QWORD *v11; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v12[3]; // [rsp+40h] [rbp-30h] BYREF
  char v13[16]; // [rsp+58h] [rbp-18h] BYREF

  RandomData = 0;
  v10 = 0;
  strcpy(v13, "I_CreateAuthKey");
  v12[0] = v13;
  v12[1] = &v10;
  v12[2] = &RandomData;
  lambda_8328029f07df0a5869519fd290e68627_::operator()(v12);
  v10 = 1;
  v11 = v12;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  RandomData = I_GenerateRandomData(a1, 20, a2);
  if ( RandomData )
  {
    WppTraceIndent(v6, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        RandomData,
        (__int64)"Unable to generate auth key");
    }
    v7 = RandomData;
  }
  else
  {
    v7 = 0;
  }
  WppTraceUnwinder__lambda_8328029f07df0a5869519fd290e68627____::_WppTraceUnwinder__lambda_8328029f07df0a5869519fd290e68627____(&v11);
  return v7;
}

```

## disassembly

```asm
0x18001f42c  mov     [rsp-8+arg_10], rbx
0x18001f431  mov     [rsp-8+arg_18], rdi
0x18001f436  push    rbp
0x18001f437  mov     rbp, rsp
0x18001f43a  sub     rsp, 70h
0x18001f43e  mov     rax, cs:__security_cookie
0x18001f445  xor     rax, rsp
0x18001f448  mov     [rbp+var_8], rax
0x18001f44c  mov     rbx, rdx
0x18001f44f  mov     rdi, rcx
0x18001f452  mov     [rbp+var_40], 0
0x18001f459  mov     [rbp+var_3C], 0
0x18001f460  movups  xmm0, xmmword ptr cs:aICreateauthkey; "I_CreateAuthKey"
0x18001f467  movdqu  [rbp+var_18], xmm0
0x18001f46c  lea     rax, [rbp+var_18]
0x18001f470  mov     [rbp+var_30], rax
0x18001f474  lea     rax, [rbp+var_3C]
0x18001f478  mov     [rbp+var_28], rax
0x18001f47c  lea     rax, [rbp+var_40]
0x18001f480  mov     [rbp+var_20], rax
0x18001f484  lea     rcx, [rbp+var_30]
0x18001f488  call    _lambda_8328029f07df0a5869519fd290e68627___operator__
0x18001f48d  mov     [rbp+var_3C], 1
0x18001f494  lea     rax, [rbp+var_30]
0x18001f498  mov     [rbp+var_38], rax
0x18001f49c  test    rdi, rdi
0x18001f49f  jnz     short loc_18001F4A6
0x18001f4a1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f4a6  test    rbx, rbx
0x18001f4a9  jnz     short loc_18001F4B0
0x18001f4ab  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001f4b0  mov     r8, rbx
0x18001f4b3  mov     edx, 14h
0x18001f4b8  mov     rcx, rdi
0x18001f4bb  call    ?I_GenerateRandomData@@YAKPEBUVCARD_DATA@@KPEAV?$vector@EU?$secure_allocator@E@wil@@@std@@@Z; I_GenerateRandomData(VCARD_DATA const *,ulong,std::vector<uchar,wil::secure_allocator<uchar>> *)
0x18001f4c0  mov     [rbp+var_40], eax
0x18001f4c3  test    eax, eax
0x18001f4c5  jz      short loc_18001F524
0x18001f4c7  mov     edx, 2
0x18001f4cc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001f4d1  lea     rax, WPP_GLOBAL_Control
0x18001f4d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4df  cmp     rcx, rax
0x18001f4e2  jz      short loc_18001F51F
0x18001f4e4  test    byte ptr [rcx+1Ch], 1
0x18001f4e8  jz      short loc_18001F51F
0x18001f4ea  cmp     byte ptr [rcx+19h], 2
0x18001f4ee  jb      short loc_18001F51F
0x18001f4f0  mov     edx, 3Bh ; ';'
0x18001f4f5  lea     rax, aUnableToGenera_7; "Unable to generate auth key"
0x18001f4fc  mov     [rsp+70h+var_48], rax
0x18001f501  mov     eax, [rbp+var_40]
0x18001f504  mov     [rsp+70h+var_50], eax
0x18001f508  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001f50f  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x18001f516  mov     rcx, [rcx+10h]
0x18001f51a  call    WPP_SF_sDs
0x18001f51f  mov     ebx, [rbp+var_40]
0x18001f522  jmp     short loc_18001F526
0x18001f524  xor     ebx, ebx
0x18001f526  lea     rcx, [rbp+var_38]
0x18001f52a  call    WppTraceUnwinder__lambda_8328029f07df0a5869519fd290e68627_______WppTraceUnwinder__lambda_8328029f07df0a5869519fd290e68627____
0x18001f52f  mov     eax, ebx
0x18001f531  mov     rcx, [rbp+var_8]
0x18001f535  xor     rcx, rsp; StackCookie
0x18001f538  call    __security_check_cookie
0x18001f53d  lea     r11, [rsp+70h+var_s0]
0x18001f542  mov     rbx, [r11+20h]
0x18001f546  mov     rdi, [r11+28h]
0x18001f54a  mov     rsp, r11
0x18001f54d  pop     rbp
0x18001f54e  retn
```
