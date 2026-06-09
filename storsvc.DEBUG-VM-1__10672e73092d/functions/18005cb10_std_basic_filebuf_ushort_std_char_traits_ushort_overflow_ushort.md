# std::basic_filebuf<ushort,std::char_traits<ushort>>::overflow(ushort)

- ea: `0x18005cb10`
- end: `0x18005cc93`
- name: `?overflow@?$basic_filebuf@GU?$char_traits@G@std@@@std@@MEAAGG@Z`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000d030`
- `0x18005c874`
- `0x18005ca34`
- `0x18005ca78`
- `0x18005cb10`

## import_xrefs

- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x18005cb5e`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x18005cb78`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x18005cb5e`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x18005cb78`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x18005cb6c`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x18005cb6c`
- `msvcp_win!?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ` at `0x18005cb86`
- `msvcp_win!?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ` at `0x18005cb86`
- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x18005cc15`
- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x18005cc15`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x18005cbc0`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x18005cbc0`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18005cc4f`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18005cc4f`

## pseudocode

```c
__int64 __fastcall std::basic_filebuf<unsigned short>::overflow(__int64 a1, __int64 a2)
{
  unsigned __int16 v3; // r14
  unsigned __int16 v4; // di
  unsigned __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rbx
  unsigned __int16 v12; // [rsp+40h] [rbp-40h] BYREF
  char v13[6]; // [rsp+42h] [rbp-3Eh] BYREF
  _BYTE *v14; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v17; // [rsp+78h] [rbp-8h] BYREF

  v3 = -1;
  v4 = a2;
  if ( (unsigned __int8)std::_WChar_traits<unsigned short>::eq_int_type(0xFFFF, a2) )
    return std::_WChar_traits<unsigned short>::not_eof(v4);
  if ( std::basic_streambuf<unsigned short>::pptr(a1) )
  {
    v6 = std::basic_streambuf<unsigned short>::epptr(a1);
    if ( std::basic_streambuf<unsigned short>::pptr(a1) < v6 )
    {
      *(_WORD *)std::basic_streambuf<unsigned short>::_Pninc(a1) = v4;
      return v4;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::basic_filebuf<unsigned short>::_Reset_back(a1);
    v7 = *(_QWORD *)(a1 + 104);
    if ( !v7 )
    {
      v8 = v4;
      goto LABEL_10;
    }
    v12 = v4;
    v15 = 0;
    v14 = 0;
    v9 = std::codecvt<unsigned short,char,_Mbstatet>::out(v7, a1 + 116, &v12, v13, &v15, v16, &v17, &v14);
    if ( v9 && (v10 = v9 - 1) != 0 )
    {
      if ( v10 == 2 )
      {
        v8 = v12;
LABEL_10:
        if ( (unsigned __int16)_o_fputwc(v8, *(_QWORD *)(a1 + 128)) == 0xFFFF )
          return (unsigned __int16)-1;
        return v4;
      }
    }
    else if ( v14 == v16 || (v11 = v14 - v16, v11 == _o_fwrite(v16, 1, v14 - v16, *(_QWORD *)(a1 + 128))) )
    {
      *(_BYTE *)(a1 + 114) = 1;
      if ( v15 != &v12 )
        return v4;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18005cb10  mov     [rsp-18h+arg_10], rbx
0x18005cb15  mov     [rsp-18h+arg_18], rsi
0x18005cb1a  push    rbp
0x18005cb1b  push    rdi
0x18005cb1c  push    r14
0x18005cb1e  mov     rbp, rsp
0x18005cb21  sub     rsp, 80h
0x18005cb28  mov     rax, cs:__security_cookie
0x18005cb2f  xor     rax, rsp
0x18005cb32  mov     [rbp+var_8], rax
0x18005cb36  mov     rsi, rcx
0x18005cb39  mov     r14d, 0FFFFh
0x18005cb3f  mov     ecx, r14d
0x18005cb42  movzx   edi, dx
0x18005cb45  call    ?eq_int_type@?$_WChar_traits@G@std@@SA_NGG@Z; std::_WChar_traits<ushort>::eq_int_type(ushort,ushort)
0x18005cb4a  test    al, al
0x18005cb4c  jz      short loc_18005CB5B
0x18005cb4e  movzx   ecx, di
0x18005cb51  call    ?not_eof@?$_WChar_traits@G@std@@SAGG@Z; std::_WChar_traits<ushort>::not_eof(ushort)
0x18005cb56  jmp     loc_18005CC6F
0x18005cb5b  mov     rcx, rsi
0x18005cb5e  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x18005cb64  test    rax, rax
0x18005cb67  jz      short loc_18005CB97
0x18005cb69  mov     rcx, rsi
0x18005cb6c  call    cs:__imp_?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::epptr(void)
0x18005cb72  mov     rcx, rsi
0x18005cb75  mov     rbx, rax
0x18005cb78  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x18005cb7e  cmp     rax, rbx
0x18005cb81  jnb     short loc_18005CB97
0x18005cb83  mov     rcx, rsi
0x18005cb86  call    cs:__imp_?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ; std::basic_streambuf<ushort>::_Pninc(void)
0x18005cb8c  mov     [rax], di
0x18005cb8f  movzx   eax, di
0x18005cb92  jmp     loc_18005CC6F
0x18005cb97  cmp     qword ptr [rsi+80h], 0
0x18005cb9f  jz      loc_18005CC6B
0x18005cba5  mov     rcx, rsi
0x18005cba8  call    ?_Reset_back@?$basic_filebuf@GU?$char_traits@G@std@@@std@@AEAAXXZ; std::basic_filebuf<ushort>::_Reset_back(void)
0x18005cbad  mov     rcx, [rsi+68h]
0x18005cbb1  test    rcx, rcx
0x18005cbb4  jnz     short loc_18005CBD1
0x18005cbb6  movzx   ecx, di
0x18005cbb9  mov     rdx, [rsi+80h]
0x18005cbc0  call    cs:__imp__o_fputwc
0x18005cbc6  cmp     ax, r14w
0x18005cbca  cmovz   di, r14w
0x18005cbcf  jmp     short loc_18005CB8F
0x18005cbd1  lea     rax, [rbp+var_38]
0x18005cbd5  mov     [rbp+var_40], di
0x18005cbd9  mov     [rsp+80h+var_48], rax
0x18005cbde  lea     rdx, [rsi+74h]
0x18005cbe2  lea     rax, [rbp+var_8]
0x18005cbe6  mov     [rbp+var_30], 0
0x18005cbee  mov     [rsp+80h+var_50], rax
0x18005cbf3  lea     r9, [rbp+var_3E]
0x18005cbf7  lea     rax, [rbp+var_28]
0x18005cbfb  mov     [rbp+var_38], 0
0x18005cc03  mov     [rsp+80h+var_58], rax
0x18005cc08  lea     r8, [rbp+var_40]
0x18005cc0c  lea     rax, [rbp+var_30]
0x18005cc10  mov     [rsp+80h+var_60], rax
0x18005cc15  call    cs:__imp_?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::out(_Mbstatet &,ushort const *,ushort const *,ushort const * &,char *,char *,char * &)
0x18005cc1b  test    eax, eax
0x18005cc1d  jz      short loc_18005CC2F
0x18005cc1f  sub     eax, 1
0x18005cc22  jz      short loc_18005CC2F
0x18005cc24  cmp     eax, 2
0x18005cc27  jnz     short loc_18005CC6B
0x18005cc29  movzx   ecx, [rbp+var_40]
0x18005cc2d  jmp     short loc_18005CBB9
0x18005cc2f  mov     rbx, [rbp+var_38]
0x18005cc33  lea     rax, [rbp+var_28]
0x18005cc37  sub     rbx, rax
0x18005cc3a  jz      short loc_18005CC5A
0x18005cc3c  mov     r9, [rsi+80h]
0x18005cc43  lea     rcx, [rbp+var_28]
0x18005cc47  mov     r8, rbx
0x18005cc4a  mov     edx, 1
0x18005cc4f  call    cs:__imp__o_fwrite
0x18005cc55  cmp     rbx, rax
0x18005cc58  jnz     short loc_18005CC6B
0x18005cc5a  lea     rax, [rbp+var_40]
0x18005cc5e  mov     byte ptr [rsi+72h], 1
0x18005cc62  cmp     [rbp+var_30], rax
0x18005cc66  cmovnz  r14w, di
0x18005cc6b  movzx   eax, r14w
0x18005cc6f  mov     rcx, [rbp+var_8]
0x18005cc73  xor     rcx, rsp; StackCookie
0x18005cc76  call    __security_check_cookie
0x18005cc7b  lea     r11, [rsp+80h+var_s0]
0x18005cc83  mov     rbx, [r11+30h]
0x18005cc87  mov     rsi, [r11+38h]
0x18005cc8b  mov     rsp, r11
0x18005cc8e  pop     r14
0x18005cc90  pop     rdi
0x18005cc91  pop     rbp
0x18005cc92  retn
```
