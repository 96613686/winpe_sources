# I_PinMapDeleteBlob(VCARD_DATA const *,_CARD_ROLE)

- ea: `0x180012074`
- end: `0x1800121d3`
- name: `?I_PinMapDeleteBlob@@YAKPEBUVCARD_DATA@@W4_CARD_ROLE@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(const struct VCARD_DATA *, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006c74`
- `0x180006dc0`
- `0x180007628`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18000d368`
- `0x18000d85c`
- `0x18000e8e0`
- `0x180011db4`
- `0x180012074`
- `0x180015384`
- `0x180015638`
- `0x18002af40`
- `0x1800348a0`

## string_xrefs

- `0x18001216c`: `Unable to delete blob file`
- `0x1800120ac`: `I_PinMapDeleteBlob`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall I_PinMapDeleteBlob(const struct VCARD_DATA *a1, unsigned int a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  const unsigned __int16 *v6; // rax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  unsigned int v10; // [rsp+30h] [rbp-19h] BYREF
  int v11; // [rsp+34h] [rbp-15h] BYREF
  _QWORD *v12; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v13[3]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v14[32]; // [rsp+58h] [rbp+Fh] BYREF
  char v15[24]; // [rsp+78h] [rbp+2Fh] BYREF

  v10 = 0;
  v11 = 0;
  strcpy(v15, "I_PinMapDeleteBlob");
  v13[0] = v15;
  v13[1] = &v11;
  v13[2] = &v10;
  lambda_818ae95457b0f55b0ae3795f97c03ac4_::operator()(v13);
  v11 = 1;
  v12 = v13;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( a2 - 1 > 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v14);
  I_PinMapCardRoleToBlobFileName(a2, v14);
  v6 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v10 = I_DeleteFile(a1, L"blobs\\", v6);
  if ( v10 )
  {
    WppTraceIndent(v7, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        151,
        (unsigned int)WPP_3886136cb8093a1468cf8d1588af7ee2_Traceguids,
        (_DWORD)WPP_pszIndent,
        v10,
        (__int64)"Unable to delete blob file");
    }
    v8 = v10;
  }
  else
  {
    v8 = 0;
  }
  std::wstring::_Tidy_deallocate((__int64)v14);
  WppTraceUnwinder__lambda_818ae95457b0f55b0ae3795f97c03ac4____::_WppTraceUnwinder__lambda_818ae95457b0f55b0ae3795f97c03ac4____(&v12);
  return v8;
}

```

## disassembly

```asm
0x180012074  mov     [rsp-8+arg_8], rbx
0x180012079  mov     [rsp-8+arg_10], rdi
0x18001207e  push    rbp
0x18001207f  lea     rbp, [rsp-57h]
0x180012084  sub     rsp, 0A0h
0x18001208b  mov     rax, cs:__security_cookie
0x180012092  xor     rax, rsp
0x180012095  mov     [rbp+57h+var_10], rax
0x180012099  mov     ebx, edx
0x18001209b  mov     rdi, rcx
0x18001209e  mov     [rbp+57h+var_70], 0
0x1800120a5  mov     [rbp+57h+var_6C], 0
0x1800120ac  movups  xmm0, xmmword ptr cs:aIPinmapdeleteb; "I_PinMapDeleteBlob"
0x1800120b3  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x1800120b7  mov     eax, dword ptr cs:aIPinmapdeleteb+0Fh; "lob"
0x1800120bd  mov     dword ptr [rbp+57h+var_28+0Fh], eax
0x1800120c0  lea     rax, [rbp+57h+var_28]
0x1800120c4  mov     [rbp+57h+var_60], rax
0x1800120c8  lea     rax, [rbp+57h+var_6C]
0x1800120cc  mov     [rbp+57h+var_58], rax
0x1800120d0  lea     rax, [rbp+57h+var_70]
0x1800120d4  mov     [rbp+57h+var_50], rax
0x1800120d8  lea     rcx, [rbp+57h+var_60]
0x1800120dc  call    _lambda_818ae95457b0f55b0ae3795f97c03ac4___operator__
0x1800120e1  mov     [rbp+57h+var_6C], 1
0x1800120e8  lea     rax, [rbp+57h+var_60]
0x1800120ec  mov     [rbp+57h+var_68], rax
0x1800120f0  test    rdi, rdi
0x1800120f3  jnz     short loc_1800120FA
0x1800120f5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800120fa  lea     eax, [rbx-1]
0x1800120fd  cmp     eax, 1
0x180012100  jbe     short loc_180012107
0x180012102  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012107  lea     rcx, [rbp+57h+var_48]
0x18001210b  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180012110  nop
0x180012111  lea     rdx, [rbp+57h+var_48]
0x180012115  mov     ecx, ebx
0x180012117  call    I_PinMapCardRoleToBlobFileName
0x18001211c  lea     rcx, [rbp+57h+var_48]
0x180012120  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012125  mov     r8, rax; unsigned __int16 *
0x180012128  lea     rdx, aBlobs; "blobs\\"
0x18001212f  mov     rcx, rdi; struct VCARD_DATA *
0x180012132  call    ?I_DeleteFile@@YAKPEBUVCARD_DATA@@PEBG1@Z; I_DeleteFile(VCARD_DATA const *,ushort const *,ushort const *)
0x180012137  mov     [rbp+57h+var_70], eax
0x18001213a  test    eax, eax
0x18001213c  jz      short loc_18001219B
0x18001213e  mov     edx, 2
0x180012143  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012148  lea     rax, WPP_GLOBAL_Control
0x18001214f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012156  cmp     rcx, rax
0x180012159  jz      short loc_180012196
0x18001215b  test    byte ptr [rcx+1Ch], 1
0x18001215f  jz      short loc_180012196
0x180012161  cmp     byte ptr [rcx+19h], 2
0x180012165  jb      short loc_180012196
0x180012167  mov     edx, 97h
0x18001216c  lea     rax, aUnableToDelete_2; "Unable to delete blob file"
0x180012173  mov     [rsp+0A0h+var_78], rax
0x180012178  mov     eax, [rbp+57h+var_70]
0x18001217b  mov     [rsp+0A0h+var_80], eax
0x18001217f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180012186  lea     r8, WPP_3886136cb8093a1468cf8d1588af7ee2_Traceguids
0x18001218d  mov     rcx, [rcx+10h]
0x180012191  call    WPP_SF_sDs
0x180012196  mov     ebx, [rbp+57h+var_70]
0x180012199  jmp     short loc_18001219D
0x18001219b  xor     ebx, ebx
0x18001219d  lea     rcx, [rbp+57h+var_48]
0x1800121a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800121a6  nop
0x1800121a7  lea     rcx, [rbp+57h+var_68]
0x1800121ab  call    WppTraceUnwinder__lambda_818ae95457b0f55b0ae3795f97c03ac4_______WppTraceUnwinder__lambda_818ae95457b0f55b0ae3795f97c03ac4____
0x1800121b0  mov     eax, ebx
0x1800121b2  mov     rcx, [rbp+57h+var_10]
0x1800121b6  xor     rcx, rsp; StackCookie
0x1800121b9  call    __security_check_cookie
0x1800121be  lea     r11, [rsp+0A0h+var_s0]
0x1800121c6  mov     rbx, [r11+18h]
0x1800121ca  mov     rdi, [r11+20h]
0x1800121ce  mov     rsp, r11
0x1800121d1  pop     rbp
0x1800121d2  retn
```
