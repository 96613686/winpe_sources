# I_KeyMapDeleteBlob(VCARD_DATA const *,uchar)

- ea: `0x18000f53c`
- end: `0x18000f69a`
- name: `?I_KeyMapDeleteBlob@@YAKPEBUVCARD_DATA@@E@Z`
- size: `350`
- prototype: `__int64 __fastcall(const struct VCARD_DATA *, char)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d9c4`
- `0x18001dd60`
- `0x18001de40`
- `0x18001e0e0`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c198`
- `0x18000d368`
- `0x18000d610`
- `0x18000e000`
- `0x18000f53c`
- `0x18000fd68`
- `0x180015384`
- `0x180015638`
- `0x18002af40`
- `0x1800348a0`

## string_xrefs

- `0x18000f574`: `I_KeyMapDeleteBlob`
- `0x18000f633`: `Unable to delete blob file`

## pseudocode

```c
__int64 __fastcall I_KeyMapDeleteBlob(const struct VCARD_DATA *a1, char a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  const unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  unsigned int v11; // [rsp+30h] [rbp-19h] BYREF
  int v12; // [rsp+34h] [rbp-15h] BYREF
  _QWORD *v13; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v14[3]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v15[32]; // [rsp+58h] [rbp+Fh] BYREF
  char v16[24]; // [rsp+78h] [rbp+2Fh] BYREF

  v11 = 0;
  v12 = 0;
  strcpy(v16, "I_KeyMapDeleteBlob");
  v14[0] = v16;
  v14[1] = &v12;
  v14[2] = &v11;
  lambda_1f451072560405cbfc461f815805003b_::operator()(v14);
  v12 = 1;
  v13 = v14;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( (unsigned __int8)(a2 + 0x80) > 0x20u )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)v15);
  LOBYTE(v6) = a2;
  I_KeyMapKeyIdToBlobFileName(v6, v15);
  v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v11 = I_DeleteFile(a1, L"blobs\\", v7);
  if ( v11 )
  {
    WppTraceIndent(v8, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        (unsigned int)WPP_3886136cb8093a1468cf8d1588af7ee2_Traceguids,
        (_DWORD)WPP_pszIndent,
        v11,
        (__int64)"Unable to delete blob file");
    }
    v9 = v11;
  }
  else
  {
    v9 = 0;
  }
  std::wstring::_Tidy_deallocate((__int64)v15);
  WppTraceUnwinder__lambda_1f451072560405cbfc461f815805003b____::_WppTraceUnwinder__lambda_1f451072560405cbfc461f815805003b____(&v13);
  return v9;
}

```

## disassembly

```asm
0x18000f53c  mov     [rsp-8+arg_10], rbx
0x18000f541  mov     [rsp-8+arg_18], rdi
0x18000f546  push    rbp
0x18000f547  lea     rbp, [rsp-57h]
0x18000f54c  sub     rsp, 0A0h
0x18000f553  mov     rax, cs:__security_cookie
0x18000f55a  xor     rax, rsp
0x18000f55d  mov     [rbp+57h+var_10], rax
0x18000f561  mov     bl, dl
0x18000f563  mov     rdi, rcx
0x18000f566  mov     [rbp+57h+var_70], 0
0x18000f56d  mov     [rbp+57h+var_6C], 0
0x18000f574  movups  xmm0, xmmword ptr cs:aIKeymapdeleteb; "I_KeyMapDeleteBlob"
0x18000f57b  movups  xmmword ptr [rbp+57h+var_28], xmm0
0x18000f57f  mov     eax, dword ptr cs:aIKeymapdeleteb+0Fh; "lob"
0x18000f585  mov     dword ptr [rbp+57h+var_28+0Fh], eax
0x18000f588  lea     rax, [rbp+57h+var_28]
0x18000f58c  mov     [rbp+57h+var_60], rax
0x18000f590  lea     rax, [rbp+57h+var_6C]
0x18000f594  mov     [rbp+57h+var_58], rax
0x18000f598  lea     rax, [rbp+57h+var_70]
0x18000f59c  mov     [rbp+57h+var_50], rax
0x18000f5a0  lea     rcx, [rbp+57h+var_60]
0x18000f5a4  call    _lambda_1f451072560405cbfc461f815805003b___operator__
0x18000f5a9  mov     [rbp+57h+var_6C], 1
0x18000f5b0  lea     rax, [rbp+57h+var_60]
0x18000f5b4  mov     [rbp+57h+var_68], rax
0x18000f5b8  test    rdi, rdi
0x18000f5bb  jnz     short loc_18000F5C2
0x18000f5bd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f5c2  lea     eax, [rbx-80h]
0x18000f5c5  cmp     al, 20h ; ' '
0x18000f5c7  jbe     short loc_18000F5CE
0x18000f5c9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f5ce  lea     rcx, [rbp+57h+var_48]
0x18000f5d2  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18000f5d7  nop
0x18000f5d8  lea     rdx, [rbp+57h+var_48]
0x18000f5dc  mov     cl, bl
0x18000f5de  call    I_KeyMapKeyIdToBlobFileName
0x18000f5e3  lea     rcx, [rbp+57h+var_48]
0x18000f5e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000f5ec  mov     r8, rax; unsigned __int16 *
0x18000f5ef  lea     rdx, aBlobs; "blobs\\"
0x18000f5f6  mov     rcx, rdi; struct VCARD_DATA *
0x18000f5f9  call    ?I_DeleteFile@@YAKPEBUVCARD_DATA@@PEBG1@Z; I_DeleteFile(VCARD_DATA const *,ushort const *,ushort const *)
0x18000f5fe  mov     [rbp+57h+var_70], eax
0x18000f601  test    eax, eax
0x18000f603  jz      short loc_18000F662
0x18000f605  mov     edx, 2
0x18000f60a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f60f  lea     rax, WPP_GLOBAL_Control
0x18000f616  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f61d  cmp     rcx, rax
0x18000f620  jz      short loc_18000F65D
0x18000f622  test    byte ptr [rcx+1Ch], 1
0x18000f626  jz      short loc_18000F65D
0x18000f628  cmp     byte ptr [rcx+19h], 2
0x18000f62c  jb      short loc_18000F65D
0x18000f62e  mov     edx, 49h ; 'I'
0x18000f633  lea     rax, aUnableToDelete_2; "Unable to delete blob file"
0x18000f63a  mov     [rsp+0A0h+var_78], rax
0x18000f63f  mov     eax, [rbp+57h+var_70]
0x18000f642  mov     [rsp+0A0h+var_80], eax
0x18000f646  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000f64d  lea     r8, WPP_3886136cb8093a1468cf8d1588af7ee2_Traceguids
0x18000f654  mov     rcx, [rcx+10h]
0x18000f658  call    WPP_SF_sDs
0x18000f65d  mov     ebx, [rbp+57h+var_70]
0x18000f660  jmp     short loc_18000F664
0x18000f662  xor     ebx, ebx
0x18000f664  lea     rcx, [rbp+57h+var_48]
0x18000f668  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f66d  nop
0x18000f66e  lea     rcx, [rbp+57h+var_68]
0x18000f672  call    WppTraceUnwinder__lambda_1f451072560405cbfc461f815805003b_______WppTraceUnwinder__lambda_1f451072560405cbfc461f815805003b____
0x18000f677  mov     eax, ebx
0x18000f679  mov     rcx, [rbp+57h+var_10]
0x18000f67d  xor     rcx, rsp; StackCookie
0x18000f680  call    __security_check_cookie
0x18000f685  lea     r11, [rsp+0A0h+var_s0]
0x18000f68d  mov     rbx, [r11+20h]
0x18000f691  mov     rdi, [r11+28h]
0x18000f695  mov     rsp, r11
0x18000f698  pop     rbp
0x18000f699  retn
```
