# ParseKERecords(void *,ulong,NtsForNtpInfoInternal &)

- ea: `0x180059d30`
- end: `0x18005a022`
- name: `?ParseKERecords@@YAJPEAXKAEAUNtsForNtpInfoInternal@@@Z`
- size: `754`
- prototype: `int(void *, unsigned int, struct NtsForNtpInfoInternal *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005a028`

## callees

- `0x180016454`
- `0x180018138`
- `0x18001d9a0`
- `0x180045abc`
- `0x180052b80`
- `0x180056920`
- `0x1800591fc`
- `0x180059308`
- `0x180059c3c`
- `0x180059d30`
- `0x18005b0d0`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x180059d81`
- `WS2_32!__imp_ntohs` at `0x180059d99`
- `WS2_32!__imp_ntohs` at `0x180059db1`
- `WS2_32!__imp_ntohs` at `0x180059f00`
- `WS2_32!__imp_ntohs` at `0x180059f29`
- `WS2_32!__imp_ntohs` at `0x180059f64`
- `WS2_32!__imp_ntohs` at `0x180059d81`
- `WS2_32!__imp_ntohs` at `0x180059d99`
- `WS2_32!__imp_ntohs` at `0x180059db1`
- `WS2_32!__imp_ntohs` at `0x180059f00`
- `WS2_32!__imp_ntohs` at `0x180059f29`
- `WS2_32!__imp_ntohs` at `0x180059f64`

## string_xrefs

- `0x180059e38`: `onecore\ds\security\services\w32time\nts\ntske.cpp`
- `0x180059fb2`: `ParseKERecords: Received multiple NtsProtocolNego records\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ParseKERecords(void *a1, unsigned int a2, struct NtsForNtpInfoInternal *a3)
{
  unsigned int v3; // r8d
  bool v4; // r14
  unsigned __int8 v5; // r13
  unsigned __int8 v6; // r12
  u_short *NextRecord; // rax
  u_short *v8; // rsi
  unsigned int v9; // ebx
  BOOL v10; // r15d
  unsigned int v11; // edi
  unsigned int i; // ebx
  _BYTE *v13; // r8
  u_short v14; // bx
  u_short v15; // ax
  u_short v16; // ax
  unsigned __int8 v17; // bl
  int v19; // [rsp+20h] [rbp-38h]
  unsigned int v20; // [rsp+30h] [rbp-28h] BYREF
  __int64 v21; // [rsp+38h] [rbp-20h] BYREF
  _BYTE *v22; // [rsp+40h] [rbp-18h]
  _BYTE *v23; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  void *v25; // [rsp+A0h] [rbp+48h]

  v25 = a1;
  v3 = a2;
  v20 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  while ( 1 )
  {
    NextRecord = (u_short *)GetNextRecord(a1, &v20, v3);
    v8 = NextRecord;
    if ( !NextRecord )
      break;
    v9 = ntohs(*NextRecord) & 0x7FFF;
    v10 = (ntohs(*v8) & 0x8000u) != 0;
    v11 = ntohs(v8[1]);
    if ( (unsigned __int8)FileLogAllowEntry(200) )
      FileLogAdd(L"ParseKERecords: Received record of type: %d critical: %d length: %d\n", v9, v10, v11);
    switch ( v9 )
    {
      case 0u:
        v17 = 1;
        goto LABEL_38;
      case 1u:
        if ( v4 )
        {
          if ( (unsigned __int8)FileLogAllowEntry(200) )
            FileLogAdd(L"ParseKERecords: Received multiple NtsProtocolNego records\n");
          return 2147549183LL;
        }
        if ( v11 == 2 )
          v4 = ntohs(v8[2]) == 0;
        break;
      case 4u:
        if ( v5 )
        {
          if ( (unsigned __int8)FileLogAllowEntry(200) )
            FileLogAdd(L"ParseKERecords: Received multiple AEADAlgoNego records\n");
          return 2147549183LL;
        }
        if ( v11 == 2 )
        {
          v14 = v8[2];
          if ( (unsigned __int8)FileLogAllowEntry(200) )
          {
            v15 = ntohs(v14);
            FileLogAdd(L"ParseKERecords: Received aead algorithm: %d\n", v15);
          }
          v16 = ntohs(v14);
          if ( (int)AeadCryptoWrapper::MakeAeadCryptoWrapper(v16, (__int64)a3 + 208) >= 0 )
          {
            v5 = 1;
            *((_DWORD *)a3 + 43) = *(_DWORD *)(*((_QWORD *)a3 + 26) + 68LL);
          }
        }
        break;
      case 5u:
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v21);
        for ( i = 0; i < v11; ++i )
        {
          v13 = (char *)v8 + i + 4;
          if ( v22 == v23 )
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Emplace_reallocate<unsigned char const &>(
              &v21,
              v22,
              v13);
          else
            *v22++ = *v13;
        }
        if ( *((_QWORD *)a3 + 28) == *((_QWORD *)a3 + 29) )
        {
          std::vector<std::vector<unsigned char,wil::secure_allocator<unsigned char>>,wil::secure_allocator<std::vector<unsigned char,wil::secure_allocator<unsigned char>>>>::_Emplace_reallocate<std::vector<unsigned char,wil::secure_allocator<unsigned char>> const &>(
            (char *)a3 + 216,
            *((_QWORD *)a3 + 28),
            &v21);
        }
        else
        {
          std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
            *((_QWORD *)a3 + 28),
            &v21);
          *((_QWORD *)a3 + 28) += 24LL;
        }
        v6 = 1;
        std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v21);
        break;
      default:
        if ( (unsigned __int8)FileLogAllowEntry(200) )
          FileLogAdd(L"ParseKERecords: Received unknown record of type: %d critical: %d length: %d\n", v9, v10, v11);
        if ( v10 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x177,
            (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntske.cpp",
            (const char *)0x8000FFFFLL,
            v19);
          return 2147549183LL;
        }
        break;
    }
    v3 = a2;
    a1 = v25;
  }
  v17 = 0;
LABEL_38:
  if ( v4 && v5 && v6 && v17 )
    return 0;
  if ( (unsigned __int8)FileLogAllowEntry(200) )
    FileLogAdd(
      L"ParseKERecords: Invalid response received. ntsNextVersionFound: %d, aeadAlgoFound %d, ntpCookieFound %d, eomFound %d\n",
      v4,
      v5,
      v6,
      v17);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180059d30  mov     [rsp-40h+arg_10], r8
0x180059d35  mov     [rsp-40h+arg_8], edx
0x180059d39  mov     [rsp-40h+arg_0], rcx
0x180059d3e  push    rbp
0x180059d3f  push    rbx
0x180059d40  push    rsi
0x180059d41  push    rdi
0x180059d42  push    r12
0x180059d44  push    r13
0x180059d46  push    r14
0x180059d48  push    r15
0x180059d4a  mov     rbp, rsp
0x180059d4d  sub     rsp, 58h
0x180059d51  mov     r8d, edx; unsigned int
0x180059d54  mov     [rbp+var_28], 0
0x180059d5b  xor     r14b, r14b
0x180059d5e  xor     r13b, r13b
0x180059d61  xor     r12b, r12b
0x180059d64  xor     bl, bl
0x180059d66  mov     [rbp+arg_18], bl
0x180059d69  lea     rdx, [rbp+var_28]; unsigned int *
0x180059d6d  call    ?GetNextRecord@@YAPEAUNtsKeRecord@@PEAXPEAKK@Z; GetNextRecord(void *,ulong *,ulong)
0x180059d72  mov     rsi, rax
0x180059d75  test    rax, rax
0x180059d78  jz      loc_180059FC4
0x180059d7e  movzx   ecx, word ptr [rax]; netshort
0x180059d81  call    cs:__imp_ntohs
0x180059d88  nop     dword ptr [rax+rax+00h]
0x180059d8d  movzx   ebx, ax
0x180059d90  and     ebx, 7FFFh
0x180059d96  movzx   ecx, word ptr [rsi]; netshort
0x180059d99  call    cs:__imp_ntohs
0x180059da0  nop     dword ptr [rax+rax+00h]
0x180059da5  shr     ax, 0Fh
0x180059da9  movzx   r15d, al
0x180059dad  movzx   ecx, word ptr [rsi+2]; netshort
0x180059db1  call    cs:__imp_ntohs
0x180059db8  nop     dword ptr [rax+rax+00h]
0x180059dbd  movzx   edi, ax
0x180059dc0  mov     ecx, 0C8h
0x180059dc5  call    FileLogAllowEntry
0x180059dca  test    al, al
0x180059dcc  jz      short loc_180059DE2
0x180059dce  mov     r9d, edi
0x180059dd1  mov     r8d, r15d
0x180059dd4  mov     edx, ebx
0x180059dd6  lea     rcx, aParsekerecords_2; "ParseKERecords: Received record of type"...
0x180059ddd  call    FileLogAdd
0x180059de2  mov     eax, ebx
0x180059de4  test    ebx, ebx
0x180059de6  jz      loc_180059FC0
0x180059dec  sub     eax, 1
0x180059def  jz      loc_180059F56
0x180059df5  sub     eax, 3
0x180059df8  jz      loc_180059ED9
0x180059dfe  cmp     eax, 1
0x180059e01  jz      short loc_180059E4E
0x180059e03  mov     ecx, 0C8h
0x180059e08  call    FileLogAllowEntry
0x180059e0d  test    al, al
0x180059e0f  jz      short loc_180059E25
0x180059e11  mov     r9d, edi
0x180059e14  mov     r8d, r15d
0x180059e17  mov     edx, ebx
0x180059e19  lea     rcx, aParsekerecords_0; "ParseKERecords: Received unknown record"...
0x180059e20  call    FileLogAdd
0x180059e25  test    r15b, r15b
0x180059e28  jz      loc_180059F80
0x180059e2e  mov     rcx, [rbp+40h]; this
0x180059e32  mov     r9d, 8000FFFFh; char *
0x180059e38  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\w32tim"...
0x180059e3f  mov     edx, 177h; void *
0x180059e44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059e49  jmp     loc_18005A00B
0x180059e4e  lea     rcx, [rbp+var_20]
0x180059e52  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x180059e57  nop
0x180059e58  xor     ebx, ebx
0x180059e5a  lea     r15d, [rbx+1]
0x180059e5e  test    edi, edi
0x180059e60  jz      short loc_180059E91
0x180059e62  mov     r8d, ebx
0x180059e65  add     r8, 4
0x180059e69  add     r8, rsi
0x180059e6c  mov     rdx, [rbp+var_18]
0x180059e70  cmp     rdx, [rbp+var_10]
0x180059e74  jz      short loc_180059E81
0x180059e76  mov     al, [r8]
0x180059e79  mov     [rdx], al
0x180059e7b  add     [rbp+var_18], r15
0x180059e7f  jmp     short loc_180059E8A
0x180059e81  lea     rcx, [rbp+var_20]
0x180059e85  call    ??$_Emplace_reallocate@AEBE@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar,wil::secure_allocator<uchar>>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x180059e8a  add     ebx, r15d
0x180059e8d  cmp     ebx, edi
0x180059e8f  jb      short loc_180059E62
0x180059e91  mov     rbx, [rbp+arg_10]
0x180059e95  add     rbx, 0D8h
0x180059e9c  mov     rax, [rbx+8]
0x180059ea0  cmp     rax, [rbx+10h]
0x180059ea4  jz      short loc_180059EB9
0x180059ea6  lea     rdx, [rbp+var_20]
0x180059eaa  mov     rcx, rax
0x180059ead  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@AEBV01@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x180059eb2  add     qword ptr [rbx+8], 18h
0x180059eb7  jmp     short loc_180059EC8
0x180059eb9  lea     r8, [rbp+var_20]
0x180059ebd  mov     rdx, rax
0x180059ec0  mov     rcx, rbx
0x180059ec3  call    ??$_Emplace_reallocate@AEBV?$vector@EU?$secure_allocator@E@wil@@@std@@@?$vector@V?$vector@EU?$secure_allocator@E@wil@@@std@@U?$secure_allocator@V?$vector@EU?$secure_allocator@E@wil@@@std@@@wil@@@std@@AEAAPEAV?$vector@EU?$secure_allocator@E@wil@@@1@QEAV21@AEBV21@@Z; std::vector<std::vector<uchar,wil::secure_allocator<uchar>>,wil::secure_allocator<std::vector<uchar,wil::secure_allocator<uchar>>>>::_Emplace_reallocate<std::vector<uchar,wil::secure_allocator<uchar>> const &>(std::vector<uchar,wil::secure_allocator<uchar>> * const,std::vector<uchar,wil::secure_allocator<uchar>> const &)
0x180059ec8  mov     r12b, r15b
0x180059ecb  lea     rcx, [rbp+var_20]
0x180059ecf  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180059ed4  jmp     loc_180059F80
0x180059ed9  test    r13b, r13b
0x180059edc  jnz     loc_180059F8D
0x180059ee2  cmp     edi, 2
0x180059ee5  jnz     loc_180059F80
0x180059eeb  movzx   ebx, word ptr [rsi+4]
0x180059eef  mov     ecx, 0C8h
0x180059ef4  call    FileLogAllowEntry
0x180059ef9  test    al, al
0x180059efb  jz      short loc_180059F1B
0x180059efd  movzx   ecx, bx; netshort
0x180059f00  call    cs:__imp_ntohs
0x180059f07  nop     dword ptr [rax+rax+00h]
0x180059f0c  movzx   edx, ax
0x180059f0f  lea     rcx, aParsekerecords_4; "ParseKERecords: Received aead algorithm"...
0x180059f16  call    FileLogAdd
0x180059f1b  mov     r15, [rbp+arg_10]
0x180059f1f  lea     rdi, [r15+0D0h]
0x180059f26  movzx   ecx, bx; netshort
0x180059f29  call    cs:__imp_ntohs
0x180059f30  nop     dword ptr [rax+rax+00h]
0x180059f35  movzx   ecx, ax
0x180059f38  mov     rdx, rdi
0x180059f3b  call    ?MakeAeadCryptoWrapper@AeadCryptoWrapper@@SAJW4AeadAlgorithms@@AEAV?$unique_ptr@VAeadCryptoWrapper@@U?$default_delete@VAeadCryptoWrapper@@@std@@@std@@@Z; AeadCryptoWrapper::MakeAeadCryptoWrapper(AeadAlgorithms,std::unique_ptr<AeadCryptoWrapper> &)
0x180059f40  test    eax, eax
0x180059f42  js      short loc_180059F80
0x180059f44  mov     r13b, 1
0x180059f47  mov     rax, [rdi]
0x180059f4a  mov     ecx, [rax+44h]
0x180059f4d  mov     [r15+0ACh], ecx
0x180059f54  jmp     short loc_180059F80
0x180059f56  test    r14b, r14b
0x180059f59  jnz     short loc_180059FA4
0x180059f5b  cmp     edi, 2
0x180059f5e  jnz     short loc_180059F80
0x180059f60  movzx   ecx, word ptr [rsi+4]; netshort
0x180059f64  call    cs:__imp_ntohs
0x180059f6b  nop     dword ptr [rax+rax+00h]
0x180059f70  movzx   r14d, r14b
0x180059f74  xor     ecx, ecx
0x180059f76  cmp     cx, ax
0x180059f79  lea     eax, [rdi-1]
0x180059f7c  cmovz   r14d, eax
0x180059f80  mov     r8d, [rbp+arg_8]
0x180059f84  mov     rcx, [rbp+arg_0]
0x180059f88  jmp     loc_180059D69
0x180059f8d  mov     ecx, 0C8h
0x180059f92  call    FileLogAllowEntry
0x180059f97  test    al, al
0x180059f99  jz      short loc_18005A00B
0x180059f9b  lea     rcx, aParsekerecords_3; "ParseKERecords: Received multiple AEADA"...
0x180059fa2  jmp     short loc_180059FB9
0x180059fa4  mov     ecx, 0C8h
0x180059fa9  call    FileLogAllowEntry
0x180059fae  test    al, al
0x180059fb0  jz      short loc_18005A00B
0x180059fb2  lea     rcx, aParsekerecords_1; "ParseKERecords: Received multiple NtsPr"...
0x180059fb9  call    FileLogAdd
0x180059fbe  jmp     short loc_18005A00B
0x180059fc0  mov     bl, 1
0x180059fc2  jmp     short loc_180059FC7
0x180059fc4  mov     bl, [rbp+arg_18]
0x180059fc7  test    r14b, r14b
0x180059fca  jz      short loc_180059FDE
0x180059fcc  test    r13b, r13b
0x180059fcf  jz      short loc_180059FDE
0x180059fd1  test    r12b, r12b
0x180059fd4  jz      short loc_180059FDE
0x180059fd6  test    bl, bl
0x180059fd8  jz      short loc_180059FDE
0x180059fda  xor     eax, eax
0x180059fdc  jmp     short loc_18005A010
0x180059fde  mov     ecx, 0C8h
0x180059fe3  call    FileLogAllowEntry
0x180059fe8  test    al, al
0x180059fea  jz      short loc_18005A00B
0x180059fec  movzx   eax, bl
0x180059fef  movzx   r9d, r12b
0x180059ff3  movzx   r8d, r13b
0x180059ff7  movzx   edx, r14b
0x180059ffb  mov     [rsp+58h+var_38], eax
0x180059fff  lea     rcx, aParsekerecords; "ParseKERecords: Invalid response receiv"...
0x18005a006  call    FileLogAdd
0x18005a00b  mov     eax, 8000FFFFh
0x18005a010  add     rsp, 58h
0x18005a014  pop     r15
0x18005a016  pop     r14
0x18005a018  pop     r13
0x18005a01a  pop     r12
0x18005a01c  pop     rdi
0x18005a01d  pop     rsi
0x18005a01e  pop     rbx
0x18005a01f  pop     rbp
0x18005a020  retn
```
