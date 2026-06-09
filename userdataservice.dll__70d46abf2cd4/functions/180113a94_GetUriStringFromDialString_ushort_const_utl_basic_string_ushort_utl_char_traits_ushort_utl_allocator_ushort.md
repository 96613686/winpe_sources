# GetUriStringFromDialString(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x180113a94`
- end: `0x180113c3e`
- name: `?GetUriStringFromDialString@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010d2d0`
- `0x18010f830`

## callees

- `0x180035c40`
- `0x180113a94`
- `0x180113c44`
- `0x180113c94`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `PhoneUtil!GetTelUriFromDialString` at `0x180113b53`
- `PhoneUtil!GetTelUriFromDialString` at `0x180113b53`
- `PhoneUtil!MaskPhoneNumber` at `0x180113b97`
- `PhoneUtil!MaskPhoneNumber` at `0x180113b97`
- `PhoneUtil!MaskPhoneUri` at `0x180113bc2`
- `PhoneUtil!MaskPhoneUri` at `0x180113bc2`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x180113b16`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x180113b16`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x180113ad5`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x180113ad5`

## pseudocode

```c
__int64 __fastcall GetUriStringFromDialString(const unsigned __int16 *a1, __int64 a2)
{
  int DefaultOutgoingLine; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // rdx
  int v9; // eax
  __int64 v10; // r8
  __int128 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[128]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v13[96]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v14[64]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v15[128]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v16[128]; // [rsp+280h] [rbp+180h] BYREF

  v11 = 0;
  DefaultOutgoingLine = PhoneGetDefaultOutgoingLine(&v11);
  if ( DefaultOutgoingLine < 0 )
  {
    v6 = 54;
LABEL_3:
    v7 = 1;
LABEL_4:
    Log_HREvent_66((unsigned int)DefaultOutgoingLine, v7, v5, v6);
    return (unsigned int)DefaultOutgoingLine;
  }
  memset_0(v12, 0, 0x13Cu);
  DefaultOutgoingLine = PhoneGetProviderLineServiceInfo(&v11, v12);
  if ( DefaultOutgoingLine < 0 )
  {
    v6 = 57;
    goto LABEL_3;
  }
  memset_0(v14, 0, sizeof(v14));
  DefaultOutgoingLine = GetTelUriFromDialString(a1, v13, v14, 0x40u);
  if ( DefaultOutgoingLine < 0 )
  {
    v6 = 61;
    goto LABEL_3;
  }
  memset_0(v16, 0, sizeof(v16));
  memset_0(v15, 0, sizeof(v15));
  v9 = MaskPhoneNumber(a1, v16, 64);
  if ( v9 < 0 )
    Log_HREvent_66((unsigned int)v9, 0, v10, 65);
  MaskPhoneUri(v14, v15, 64);
  if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(
      MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context,
      UtilsTelUriConvert,
      v16,
      v15);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a2,
                           v14) )
  {
    v7 = 0;
    DefaultOutgoingLine = -2147024882;
    v6 = 69;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x180113a94  mov     [rsp-8+arg_10], rbx
0x180113a99  mov     [rsp-8+arg_18], rsi
0x180113a9e  push    rbp
0x180113a9f  push    rdi
0x180113aa0  push    r15
0x180113aa2  lea     rbp, [rsp-210h]
0x180113aaa  sub     rsp, 310h
0x180113ab1  mov     rax, cs:__security_cookie
0x180113ab8  xor     rax, rsp
0x180113abb  mov     [rbp+220h+var_20], rax
0x180113ac2  mov     rdi, rcx
0x180113ac5  xorps   xmm0, xmm0
0x180113ac8  lea     rcx, [rsp+320h+var_2F0]
0x180113acd  mov     rsi, rdx
0x180113ad0  movups  [rsp+320h+var_2F0], xmm0
0x180113ad5  call    cs:__imp_PhoneGetDefaultOutgoingLine
0x180113adb  mov     ebx, eax
0x180113add  test    eax, eax
0x180113adf  jns     short loc_180113AFA
0x180113ae1  mov     r9d, 36h ; '6'
0x180113ae7  mov     edx, 1
0x180113aec  mov     ecx, ebx
0x180113aee  call    Log_HREvent_66
0x180113af3  mov     eax, ebx
0x180113af5  jmp     loc_180113C17
0x180113afa  xor     edx, edx; Val
0x180113afc  lea     rcx, [rsp+320h+var_2E0]; void *
0x180113b01  mov     r8d, 13Ch; Size
0x180113b07  call    memset_0
0x180113b0c  lea     rdx, [rsp+320h+var_2E0]
0x180113b11  lea     rcx, [rsp+320h+var_2F0]
0x180113b16  call    cs:__imp_PhoneGetProviderLineServiceInfo
0x180113b1c  mov     ebx, eax
0x180113b1e  test    eax, eax
0x180113b20  jns     short loc_180113B2A
0x180113b22  mov     r9d, 39h ; '9'
0x180113b28  jmp     short loc_180113AE7
0x180113b2a  mov     r15d, 80h
0x180113b30  lea     rcx, [rbp+220h+var_1A0]; void *
0x180113b37  mov     r8d, r15d; Size
0x180113b3a  xor     edx, edx; Val
0x180113b3c  call    memset_0
0x180113b41  lea     r9d, [r15-40h]
0x180113b45  mov     rcx, rdi
0x180113b48  lea     r8, [rbp+220h+var_1A0]
0x180113b4f  lea     rdx, [rbp+220h+var_260]
0x180113b53  call    cs:__imp_?GetTelUriFromDialString@@YAJPEBG0PEAGI@Z; GetTelUriFromDialString(ushort const *,ushort const *,ushort *,uint)
0x180113b59  mov     ebx, eax
0x180113b5b  test    eax, eax
0x180113b5d  jns     short loc_180113B65
0x180113b5f  lea     r9d, [r15-43h]
0x180113b63  jmp     short loc_180113AE7
0x180113b65  mov     r8, r15; Size
0x180113b68  lea     rcx, [rbp+220h+var_A0]; void *
0x180113b6f  xor     edx, edx; Val
0x180113b71  call    memset_0
0x180113b76  mov     r8, r15; Size
0x180113b79  lea     rcx, [rbp+220h+var_120]; void *
0x180113b80  xor     edx, edx; Val
0x180113b82  call    memset_0
0x180113b87  mov     r8d, 40h ; '@'
0x180113b8d  lea     rdx, [rbp+220h+var_A0]
0x180113b94  mov     rcx, rdi
0x180113b97  call    cs:__imp_MaskPhoneNumber
0x180113b9d  test    eax, eax
0x180113b9f  jns     short loc_180113BAE
0x180113ba1  xor     edx, edx
0x180113ba3  mov     ecx, eax
0x180113ba5  lea     r9d, [rdx+41h]
0x180113ba9  call    Log_HREvent_66
0x180113bae  mov     r8d, 40h ; '@'
0x180113bb4  lea     rdx, [rbp+220h+var_120]
0x180113bbb  lea     rcx, [rbp+220h+var_1A0]
0x180113bc2  call    cs:__imp_MaskPhoneUri
0x180113bc8  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x180113bcf  jz      short loc_180113BF2
0x180113bd1  lea     r9, [rbp+220h+var_120]
0x180113bd8  lea     r8, [rbp+220h+var_A0]
0x180113bdf  lea     rdx, UtilsTelUriConvert
0x180113be6  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_RCSSERVICEADAPTER_Context
0x180113bed  call    McTemplateU0zz_EventWriteTransfer
0x180113bf2  lea     rdx, [rbp+220h+var_1A0]
0x180113bf9  mov     rcx, rsi
0x180113bfc  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180113c01  test    al, al
0x180113c03  jnz     short loc_180113C15
0x180113c05  xor     edx, edx
0x180113c07  mov     ebx, 8007000Eh
0x180113c0c  lea     r9d, [rdx+45h]
0x180113c10  jmp     loc_180113AEC
0x180113c15  xor     eax, eax
0x180113c17  mov     rcx, [rbp+220h+var_20]
0x180113c1e  xor     rcx, rsp; StackCookie
0x180113c21  call    __security_check_cookie
0x180113c26  lea     r11, [rsp+320h+var_10]
0x180113c2e  mov     rbx, [r11+30h]
0x180113c32  mov     rsi, [r11+38h]
0x180113c36  mov     rsp, r11
0x180113c39  pop     r15
0x180113c3b  pop     rdi
0x180113c3c  pop     rbp
0x180113c3d  retn
```
