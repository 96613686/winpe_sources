# WriteCommaDelimitedStringToVariantBuffer(Buffer &,tag_EcRpcMetadataProperty &)

- ea: `0x18000aea4`
- end: `0x18000b2aa`
- name: `?WriteCommaDelimitedStringToVariantBuffer@@YAXAEAVBuffer@@AEAUtag_EcRpcMetadataProperty@@@Z`
- size: `1030`
- prototype: `void __fastcall(struct Buffer *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a820`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800026c0`
- `0x1800027ac`
- `0x180009ee0`
- `0x18000a100`
- `0x18000aaa0`
- `0x18000aea4`
- `0x18000ba60`
- `0x18000d010`

## string_xrefs

- `0x18000b220`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`
- `0x18000b285`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
void __fastcall WriteCommaDelimitedStringToVariantBuffer(struct Buffer *a1, void **a2)
{
  unsigned int v4; // r14d
  int Token; // eax
  int *v6; // r15
  unsigned int v7; // r13d
  char *v8; // rsi
  int *v9; // rbx
  int v10; // edi
  __int64 v11; // rdi
  void **v12; // rdx
  _QWORD *v13; // rax
  _QWORD *v14; // r15
  _QWORD *v15; // rdx
  unsigned int i; // r13d
  __int64 v17; // rbx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  void *v19[2]; // [rsp+28h] [rbp-D8h] BYREF
  int *v20; // [rsp+38h] [rbp-C8h]
  _BYTE pExceptionObject[56]; // [rsp+40h] [rbp-C0h] BYREF
  void *v22[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v23; // [rsp+88h] [rbp-78h]
  unsigned __int64 v24; // [rsp+90h] [rbp-70h]
  void *v25[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v27; // [rsp+B8h] [rbp-48h]
  void *v28; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v29; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v30; // [rsp+D8h] [rbp-28h]
  __int64 v31; // [rsp+E0h] [rbp-20h]
  char v32; // [rsp+E8h] [rbp-18h]
  void *v33[3]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v34; // [rsp+108h] [rbp+8h]
  void *v35; // [rsp+110h] [rbp+10h] BYREF
  __int64 v36; // [rsp+120h] [rbp+20h]
  unsigned __int64 v37; // [rsp+128h] [rbp+28h]
  __int64 v38; // [rsp+130h] [rbp+30h]
  char v39; // [rsp+138h] [rbp+38h]

  v4 = 0;
  v24 = 7;
  v23 = 0;
  LOWORD(v22[0]) = 0;
  v34 = 7;
  v33[2] = 0;
  LOWORD(v33[0]) = 0;
  std::wstring::assign(v33, a2[1]);
  v37 = 7;
  v36 = 0;
  LOWORD(v35) = 0;
  std::wstring::assign(&v35, L",");
  v38 = 0;
  v39 = 0;
  do
  {
    Token = StringTokenizer::NextToken(v33, v22);
    if ( Token != 1 )
      break;
    ++v4;
    Token = StringTokenizer::NextToken(v33, v22);
  }
  while ( !Token );
  if ( Token != 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 13);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0xDu,
      "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp",
      996);
    throw (wmi::GenericException *)pExceptionObject;
  }
  if ( v37 >= 8 )
    operator delete(v35);
  v37 = 7;
  v36 = 0;
  LOWORD(v35) = 0;
  if ( v34 >= 8 )
    operator delete(v33[0]);
  (*(void (__fastcall **)(struct Buffer *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 16);
  (*(void (__fastcall **)(struct Buffer *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 8 * v4);
  *(_OWORD *)v19 = 0;
  v6 = 0;
  v20 = 0;
  v27 = 7;
  v26 = 0;
  LOWORD(v25[0]) = 0;
  std::wstring::assign(v25, a2[1]);
  v30 = 7;
  v29 = 0;
  LOWORD(v28) = 0;
  std::wstring::assign(&v28, L",");
  v31 = 0;
  v32 = 0;
  v7 = 0;
  v8 = 0;
  if ( v4 )
  {
    v9 = (int *)v19[1];
    do
    {
      StringTokenizer::NextToken(v25, v22);
      if ( v23 > 0x200 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 13);
        }
        wmi::GenericException::GenericException(
          (wmi::GenericException *)pExceptionObject,
          0xDu,
          "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp",
          1012);
        throw (wmi::GenericException *)pExceptionObject;
      }
      v10 = (*(__int64 (__fastcall **)(struct Buffer *))(*(_QWORD *)a1 + 24LL))(a1);
      v18 = v10;
      if ( &v18 >= v9 || v8 > (char *)&v18 )
      {
        if ( v9 == v6 )
        {
          std::vector<unsigned long>::_Reserve(v19);
          v6 = v20;
          v9 = (int *)v19[1];
          v8 = (char *)v19[0];
        }
        *v9 = v10;
      }
      else
      {
        v11 = ((char *)&v18 - v8) >> 2;
        if ( v9 == v6 )
        {
          std::vector<unsigned long>::_Reserve(v19);
          v6 = v20;
          v9 = (int *)v19[1];
          v8 = (char *)v19[0];
        }
        *v9 = *(_DWORD *)&v8[4 * v11];
      }
      v19[1] = ++v9;
      v12 = v22;
      if ( v24 >= 8 )
        v12 = (void **)v22[0];
      (*(void (__fastcall **)(struct Buffer *, void **, _QWORD))(*(_QWORD *)a1 + 8LL))(
        a1,
        v12,
        (unsigned int)(2 * v23 + 2));
      StringTokenizer::NextToken(v25, v22);
      ++v7;
    }
    while ( v7 < v4 );
  }
  v13 = (_QWORD *)(*(__int64 (__fastcall **)(struct Buffer *))(*(_QWORD *)a1 + 48LL))(a1);
  v14 = v13;
  v15 = v13 + 2;
  if ( !v4 )
    v15 = 0;
  *v13 = v15;
  for ( i = 0; i < v4; ++i )
  {
    v17 = *(unsigned int *)&v8[4 * i];
    *(_QWORD *)(*v14 + 8LL * i) = (*(__int64 (__fastcall **)(struct Buffer *))(*(_QWORD *)a1 + 48LL))(a1) + v17;
  }
  *((_DWORD *)v14 + 3) = 132;
  *((_DWORD *)v14 + 2) = v4;
  if ( v30 >= 8 )
    operator delete(v28);
  v30 = 7;
  v29 = 0;
  LOWORD(v28) = 0;
  if ( v27 >= 8 )
    operator delete(v25[0]);
  v27 = 7;
  v26 = 0;
  LOWORD(v25[0]) = 0;
  if ( v8 )
    operator delete(v8);
  if ( v24 >= 8 )
    operator delete(v22[0]);
}

```

## disassembly

```asm
0x18000aea4  mov     [rsp-8+arg_10], rbx
0x18000aea9  push    rbp
0x18000aeaa  push    rsi
0x18000aeab  push    rdi
0x18000aeac  push    r12
0x18000aeae  push    r13
0x18000aeb0  push    r14
0x18000aeb2  push    r15
0x18000aeb4  lea     rbp, [rsp-50h]
0x18000aeb9  sub     rsp, 150h
0x18000aec0  mov     rax, cs:__security_cookie
0x18000aec7  xor     rax, rsp
0x18000aeca  mov     [rbp+80h+var_40], rax
0x18000aece  mov     rbx, rdx
0x18000aed1  mov     r12, rcx
0x18000aed4  xor     edi, edi
0x18000aed6  mov     r14d, edi
0x18000aed9  lea     esi, [rdi+7]
0x18000aedc  mov     [rbp+80h+var_F0], rsi
0x18000aee0  mov     [rbp+80h+var_F8], rdi
0x18000aee4  mov     word ptr [rsp+180h+var_108], di
0x18000aee9  mov     [rbp+80h+var_78], rsi
0x18000aeed  mov     [rbp+80h+var_80], rdi
0x18000aef1  mov     word ptr [rbp+80h+var_90], di
0x18000aef5  mov     rdx, [rdx+8]; Src
0x18000aef9  lea     rcx, [rbp+80h+var_90]; void *
0x18000aefd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000af02  nop
0x18000af03  mov     [rbp+80h+var_58], rsi
0x18000af07  mov     [rbp+80h+var_60], rdi
0x18000af0b  mov     word ptr [rbp+80h+var_70], di
0x18000af0f  lea     rdx, asc_180010C2C; ","
0x18000af16  lea     rcx, [rbp+80h+var_70]; void *
0x18000af1a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000af1f  mov     [rbp+80h+var_50], rdi
0x18000af23  mov     [rbp+80h+var_48], dil
0x18000af27  jmp     short loc_18000AF3E
0x18000af29  inc     r14d
0x18000af2c  lea     rdx, [rsp+180h+var_108]
0x18000af31  lea     rcx, [rbp+80h+var_90]
0x18000af35  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringTokenizer::NextToken(std::wstring &)
0x18000af3a  test    eax, eax
0x18000af3c  jnz     short loc_18000AF51
0x18000af3e  lea     rdx, [rsp+180h+var_108]
0x18000af43  lea     rcx, [rbp+80h+var_90]
0x18000af47  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringTokenizer::NextToken(std::wstring &)
0x18000af4c  cmp     eax, 1
0x18000af4f  jz      short loc_18000AF29
0x18000af51  cmp     eax, 2
0x18000af54  jnz     loc_18000B1E0
0x18000af5a  cmp     [rbp+80h+var_58], 8
0x18000af5f  jb      short loc_18000AF6A
0x18000af61  mov     rcx, [rbp+80h+var_70]; void *
0x18000af65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000af6a  mov     [rbp+80h+var_58], rsi
0x18000af6e  mov     [rbp+80h+var_60], rdi
0x18000af72  mov     word ptr [rbp+80h+var_70], di
0x18000af76  cmp     [rbp+80h+var_78], 8
0x18000af7b  jb      short loc_18000AF86
0x18000af7d  mov     rcx, [rbp+80h+var_90]; void *
0x18000af81  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000af86  mov     rax, [r12]
0x18000af8a  mov     edx, 10h
0x18000af8f  mov     rcx, r12
0x18000af92  mov     rax, [rax+28h]
0x18000af96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af9b  mov     rax, [r12]
0x18000af9f  lea     edx, ds:0[r14*8]
0x18000afa7  mov     rcx, r12
0x18000afaa  mov     rax, [rax+28h]
0x18000afae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afb3  xorps   xmm0, xmm0
0x18000afb6  movdqu  xmmword ptr [rsp+180h+var_158], xmm0
0x18000afbc  mov     r15, rdi
0x18000afbf  mov     [rsp+180h+var_148], rdi
0x18000afc4  mov     [rbp+80h+var_C8], rsi
0x18000afc8  mov     [rbp+80h+var_D0], rdi
0x18000afcc  mov     word ptr [rbp+80h+var_E0], di
0x18000afd0  mov     rdx, [rbx+8]; Src
0x18000afd4  lea     rcx, [rbp+80h+var_E0]; void *
0x18000afd8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000afdd  nop
0x18000afde  mov     [rbp+80h+var_A8], rsi
0x18000afe2  mov     [rbp+80h+var_B0], rdi
0x18000afe6  mov     word ptr [rbp+80h+var_C0], di
0x18000afea  lea     rdx, asc_180010C2C; ","
0x18000aff1  lea     rcx, [rbp+80h+var_C0]; void *
0x18000aff5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000affa  mov     [rbp+80h+var_A0], rdi
0x18000affe  mov     [rbp+80h+var_98], dil
0x18000b002  mov     r13d, edi
0x18000b005  mov     rsi, [rsp+180h+var_158]
0x18000b00a  test    r14d, r14d
0x18000b00d  jz      loc_18000B100
0x18000b013  mov     rbx, [rsp+180h+var_158+8]
0x18000b018  lea     rdx, [rsp+180h+var_108]
0x18000b01d  lea     rcx, [rbp+80h+var_E0]
0x18000b021  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringTokenizer::NextToken(std::wstring &)
0x18000b026  cmp     [rbp+80h+var_F8], 200h
0x18000b02e  ja      loc_18000B245
0x18000b034  mov     rax, [r12]
0x18000b038  mov     rcx, r12
0x18000b03b  mov     rax, [rax+18h]
0x18000b03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b044  mov     edi, eax
0x18000b046  mov     [rsp+180h+var_160], eax
0x18000b04a  lea     rax, [rsp+180h+var_160]
0x18000b04f  cmp     rax, rbx
0x18000b052  jnb     short loc_18000B08F
0x18000b054  lea     rax, [rsp+180h+var_160]
0x18000b059  cmp     rsi, rax
0x18000b05c  ja      short loc_18000B08F
0x18000b05e  lea     rdi, [rsp+180h+var_160]
0x18000b063  sub     rdi, rsi
0x18000b066  sar     rdi, 2
0x18000b06a  cmp     rbx, r15
0x18000b06d  jnz     short loc_18000B088
0x18000b06f  lea     rcx, [rsp+180h+var_158]
0x18000b074  call    ?_Reserve@?$vector@KV?$allocator@K@std@@@std@@IEAAX_K@Z; std::vector<ulong>::_Reserve(unsigned __int64)
0x18000b079  mov     r15, [rsp+180h+var_148]
0x18000b07e  mov     rbx, [rsp+180h+var_158+8]
0x18000b083  mov     rsi, [rsp+180h+var_158]
0x18000b088  mov     eax, [rsi+rdi*4]
0x18000b08b  mov     [rbx], eax
0x18000b08d  jmp     short loc_18000B0AF
0x18000b08f  cmp     rbx, r15
0x18000b092  jnz     short loc_18000B0AD
0x18000b094  lea     rcx, [rsp+180h+var_158]
0x18000b099  call    ?_Reserve@?$vector@KV?$allocator@K@std@@@std@@IEAAX_K@Z; std::vector<ulong>::_Reserve(unsigned __int64)
0x18000b09e  mov     r15, [rsp+180h+var_148]
0x18000b0a3  mov     rbx, [rsp+180h+var_158+8]
0x18000b0a8  mov     rsi, [rsp+180h+var_158]
0x18000b0ad  mov     [rbx], edi
0x18000b0af  add     rbx, 4
0x18000b0b3  mov     [rsp+180h+var_158+8], rbx
0x18000b0b8  mov     rax, [r12]
0x18000b0bc  mov     r8d, dword ptr [rbp+80h+var_F8]
0x18000b0c0  lea     rdx, [rsp+180h+var_108]
0x18000b0c5  cmp     [rbp+80h+var_F0], 8
0x18000b0ca  cmovnb  rdx, [rsp+180h+var_108]
0x18000b0d0  lea     r8d, ds:2[r8*2]
0x18000b0d8  mov     rcx, r12
0x18000b0db  mov     rax, [rax+8]
0x18000b0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0e4  lea     rdx, [rsp+180h+var_108]
0x18000b0e9  lea     rcx, [rbp+80h+var_E0]
0x18000b0ed  call    ?NextToken@StringTokenizer@@QEAA?AW4StringTokenType@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringTokenizer::NextToken(std::wstring &)
0x18000b0f2  inc     r13d
0x18000b0f5  cmp     r13d, r14d
0x18000b0f8  jb      loc_18000B018
0x18000b0fe  xor     edi, edi
0x18000b100  mov     rax, [r12]
0x18000b104  mov     rcx, r12
0x18000b107  mov     rax, [rax+30h]
0x18000b10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b110  mov     r15, rax
0x18000b113  lea     rdx, [rax+10h]
0x18000b117  test    r14d, r14d
0x18000b11a  cmovz   rdx, rdi
0x18000b11e  mov     [rax], rdx
0x18000b121  mov     r13d, edi
0x18000b124  jz      short loc_18000B151
0x18000b126  mov     edi, r13d
0x18000b129  mov     ebx, [rsi+rdi*4]
0x18000b12c  mov     rax, [r12]
0x18000b130  mov     rcx, r12
0x18000b133  mov     rax, [rax+30h]
0x18000b137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b13c  lea     rcx, [rax+rbx]
0x18000b140  mov     rax, [r15]
0x18000b143  mov     [rax+rdi*8], rcx
0x18000b147  inc     r13d
0x18000b14a  cmp     r13d, r14d
0x18000b14d  jb      short loc_18000B126
0x18000b14f  xor     edi, edi
0x18000b151  mov     dword ptr [r15+0Ch], 84h
0x18000b159  mov     [r15+8], r14d
0x18000b15d  cmp     [rbp+80h+var_A8], 8
0x18000b162  jb      short loc_18000B16D
0x18000b164  mov     rcx, [rbp+80h+var_C0]; void *
0x18000b168  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b16d  mov     ebx, 7
0x18000b172  mov     [rbp+80h+var_A8], rbx
0x18000b176  mov     [rbp+80h+var_B0], rdi
0x18000b17a  mov     word ptr [rbp+80h+var_C0], di
0x18000b17e  cmp     [rbp+80h+var_C8], 8
0x18000b183  jb      short loc_18000B18E
0x18000b185  mov     rcx, [rbp+80h+var_E0]; void *
0x18000b189  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b18e  mov     [rbp+80h+var_C8], rbx
0x18000b192  mov     [rbp+80h+var_D0], rdi
0x18000b196  mov     word ptr [rbp+80h+var_E0], di
0x18000b19a  test    rsi, rsi
0x18000b19d  jz      short loc_18000B1A8
0x18000b19f  mov     rcx, rsi; void *
0x18000b1a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b1a7  nop
0x18000b1a8  cmp     [rbp+80h+var_F0], 8
0x18000b1ad  jb      short loc_18000B1B9
0x18000b1af  mov     rcx, [rsp+180h+var_108]; void *
0x18000b1b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b1b9  mov     rcx, [rbp+80h+var_40]
0x18000b1bd  xor     rcx, rsp; StackCookie
0x18000b1c0  call    __security_check_cookie
0x18000b1c5  mov     rbx, [rsp+180h+arg_10]
0x18000b1cd  add     rsp, 150h
0x18000b1d4  pop     r15
0x18000b1d6  pop     r14
0x18000b1d8  pop     r13
0x18000b1da  pop     r12
0x18000b1dc  pop     rdi
0x18000b1dd  pop     rsi
0x18000b1de  pop     rbp
0x18000b1df  retn
0x18000b1e0  lea     rax, WPP_GLOBAL_Control
0x18000b1e7  mov     ebx, 0Dh
0x18000b1ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1f3  cmp     rcx, rax
0x18000b1f6  jz      short loc_18000B21A
0x18000b1f8  test    byte ptr [rcx+1Ch], 80h
0x18000b1fc  jz      short loc_18000B21A
0x18000b1fe  cmp     byte ptr [rcx+19h], 2
0x18000b202  jb      short loc_18000B21A
0x18000b204  lea     edx, [rbx+0Ah]
0x18000b207  mov     r9d, ebx
0x18000b20a  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18000b211  mov     rcx, [rcx+10h]
0x18000b215  call    WPP_SF_D
0x18000b21a  mov     r9d, 3E4h; int
0x18000b220  lea     r8, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\collect"...
0x18000b227  mov     edx, ebx; unsigned int
0x18000b229  lea     rcx, [rsp+180h+pExceptionObject]; this
0x18000b22e  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000b233  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b23a  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x18000b23f  call    _CxxThrowException_0
0x18000b245  lea     rax, WPP_GLOBAL_Control
0x18000b24c  mov     ebx, 0Dh
0x18000b251  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b258  cmp     rcx, rax
0x18000b25b  jz      short loc_18000B27F
0x18000b25d  test    byte ptr [rcx+1Ch], 80h
0x18000b261  jz      short loc_18000B27F
0x18000b263  cmp     byte ptr [rcx+19h], 2
0x18000b267  jb      short loc_18000B27F
0x18000b269  lea     edx, [rbx+0Bh]
0x18000b26c  mov     r9d, ebx
0x18000b26f  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18000b276  mov     rcx, [rcx+10h]
0x18000b27a  call    WPP_SF_D
0x18000b27f  mov     r9d, 3F4h; int
0x18000b285  lea     r8, aAdminWmiEvents_0; "admin\\wmi\\events\\forwarding\\collect"...
0x18000b28c  mov     edx, ebx; unsigned int
0x18000b28e  lea     rcx, [rsp+180h+pExceptionObject]; this
0x18000b293  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000b298  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b29f  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x18000b2a4  call    _CxxThrowException_0
```
