# ReceiveKEResponse(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,_SecHandle &,_SecPkgContext_StreamSizes const &,NtsForNtpInfoInternal &)

- ea: `0x18005a214`
- end: `0x18005a59b`
- name: `?ReceiveKEResponse@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEAU_SecHandle@@AEBU_SecPkgContext_StreamSizes@@AEAUNtsForNtpInfoInternal@@@Z`
- size: `903`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005997c`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003b8fc`
- `0x18003d270`
- `0x18003d2d8`
- `0x18003dd2c`
- `0x18003f3ec`
- `0x18003f49d`
- `0x180041348`
- `0x180045abc`
- `0x180058a5c`
- `0x180059620`
- `0x18005a028`
- `0x18005a214`

## import_xrefs

- `WS2_32!__imp_recv` at `0x18005a2b5`
- `WS2_32!__imp_recv` at `0x18005a2b5`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a50d`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a50d`
- `SspiCli!DecryptMessage` at `0x18005a31e`
- `SspiCli!DecryptMessage` at `0x18005a31e`

## string_xrefs

- `0x18005a4a5`: `onecore\ds\security\services\w32time\nts\ntske.cpp`
- `0x18005a4de`: `onecore\ds\security\services\w32time\nts\ntske.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ReceiveKEResponse(SOCKET *a1, struct _SecHandle *a2, _DWORD *a3, struct NtsForNtpInfoInternal *a4)
{
  SOCKET *v5; // rsi
  unsigned int v6; // ebx
  unsigned int v7; // edi
  char v8; // r15
  unsigned int v9; // r13d
  int v10; // ecx
  unsigned int v11; // esi
  int v12; // r14d
  int v13; // eax
  unsigned int v14; // edi
  int v15; // esi
  int Error; // eax
  int v18; // [rsp+20h] [rbp-B9h]
  void **v19; // [rsp+30h] [rbp-A9h] BYREF
  char v20; // [rsp+38h] [rbp-A1h]
  SOCKET *v21; // [rsp+40h] [rbp-99h]
  void *v22; // [rsp+48h] [rbp-91h] BYREF
  void *Src[2]; // [rsp+50h] [rbp-89h] BYREF
  struct _SecBufferDesc pMessage; // [rsp+60h] [rbp-79h] BYREF
  struct NtsForNtpInfoInternal *v25; // [rsp+78h] [rbp-61h]
  _BYTE v26[32]; // [rsp+80h] [rbp-59h] BYREF
  void *v27[2]; // [rsp+A0h] [rbp-39h] BYREF
  int v28; // [rsp+B4h] [rbp-25h]
  int v29; // [rsp+C4h] [rbp-15h]
  int v30; // [rsp+D4h] [rbp-5h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v25 = a4;
  v5 = a1;
  v21 = a1;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = *a3 + a3[1] + a3[2];
  v22 = operator new[](v9);
  Src[0] = &v22;
  wil::scope_exit__lambda_5b0cea69da2f2023c814ebef0d37cd7f___(&v19, Src);
  while ( !v8 )
  {
    if ( !v7 || v6 == -2146893032 )
    {
      v10 = recv(*v5, (char *)v22 + v7, v9 - v7, 0);
      if ( (unsigned int)(v10 - 1) > 0xFFFFFFFD )
      {
        Error = WSAGetLastError();
        v6 = Error;
        if ( Error > 0 )
          v6 = (unsigned __int16)Error | 0x80070000;
        if ( (unsigned __int8)FileLogAllowEntry(0) )
          FileLogAdd(L"ReceiveKEResponse: Sending on socket failed with hr: 0x%08X\n", v6);
        goto LABEL_43;
      }
      v7 += v10;
    }
    memset_0(v27, 0, 0x40u);
    v27[0] = (void *)(v7 | 0x100000000LL);
    v27[1] = v22;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    pMessage.ulVersion = 0;
    pMessage.cBuffers = 4;
    pMessage.pBuffers = (PSecBuffer)v27;
    v6 = DecryptMessage(a2, &pMessage, 0, 0);
    if ( v6 == -2146893032 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(200) )
        FileLogAdd(L"ReceiveKEResponse: We need to get more data to fill our buffer\n");
    }
    else
    {
      if ( v6 && v6 != 590625 && v6 != 590615 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(0) )
          FileLogAdd(L"ReceiveKEResponse: DecryptMessage returned unexpected hr: 0x%08X\n", v6);
LABEL_43:
        if ( v20 )
        {
          v20 = 0;
          operator delete(*v19);
        }
        return v6;
      }
      *(_OWORD *)Src = 0;
      v11 = 0;
      v12 = 0;
      while ( v11 < pMessage.cBuffers )
      {
        if ( HIDWORD(v27[2 * v11]) == 1 )
        {
          if ( !v6 )
          {
            v13 = ParseServerResponse(v27[2 * v11 + 1], (unsigned int)v27[2 * v11], a2, v25);
            v14 = v13;
            if ( v13 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1E3,
                (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntske.cpp",
                (const char *)(unsigned int)v13,
                v18);
              if ( v20 )
              {
                v20 = 0;
                operator delete(*v19);
              }
              return v14;
            }
            v8 = 1;
          }
        }
        else if ( HIDWORD(v27[2 * v11]) == 5 )
        {
          if ( v6 == 590625 && !v12 )
          {
            *(_OWORD *)Src = *(_OWORD *)&v27[2 * v11];
            v12 = _mm_cvtsi128_si32(*(__m128i *)Src);
          }
        }
        else if ( (unsigned __int8)FileLogAllowEntry(200) )
        {
          FileLogAdd(L"ReceiveKEResponse: DecryptMessage received unused SECBUFFER type: %d\n", HIDWORD(v27[2 * v11]));
        }
        ++v11;
      }
      v7 = 0;
      v5 = v21;
      if ( v6 != 590625 || !v12 )
        continue;
      std::wstring::wstring(v26, &qword_180071478);
      v15 = NegotiateTLS(v5, (__int64)v26, a2, (unsigned int *)Src, 0);
      std::wstring::~wstring((__int64)v26);
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1FA,
          (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntske.cpp",
          (const char *)(unsigned int)v15,
          v18);
        if ( v20 )
        {
          v20 = 0;
          operator delete(*v19);
        }
        return (unsigned int)v15;
      }
      v5 = v21;
      if ( LODWORD(Src[0]) )
      {
        v7 = (unsigned int)Src[0];
        memmove_0(v22, Src[1], LODWORD(Src[0]));
      }
    }
  }
  if ( v20 )
  {
    v20 = 0;
    operator delete(*v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18005a214  push    rbp
0x18005a216  push    rbx
0x18005a217  push    rsi
0x18005a218  push    rdi
0x18005a219  push    r12
0x18005a21b  push    r13
0x18005a21d  push    r14
0x18005a21f  push    r15
0x18005a221  lea     rbp, [rsp-1Fh]
0x18005a226  sub     rsp, 0F8h
0x18005a22d  mov     rax, cs:__security_cookie
0x18005a234  xor     rax, rsp
0x18005a237  mov     [rbp+57h+var_50], rax
0x18005a23b  mov     [rbp+57h+var_B8], r9
0x18005a23f  mov     r12, rdx
0x18005a242  mov     rsi, rcx
0x18005a245  mov     [rsp+130h+var_F0], rcx
0x18005a24a  xor     r14d, r14d
0x18005a24d  mov     ebx, r14d
0x18005a250  mov     edi, r14d
0x18005a253  mov     r15b, r14b
0x18005a256  mov     r13d, [r8+8]
0x18005a25a  add     r13d, [r8+4]
0x18005a25e  add     r13d, [r8]
0x18005a261  mov     ecx, r13d; unsigned __int64
0x18005a264  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005a269  mov     [rsp+130h+var_E8], rax
0x18005a26e  lea     rax, [rsp+130h+var_E8]
0x18005a273  mov     [rsp+130h+Src], rax
0x18005a278  lea     rdx, [rsp+130h+Src]
0x18005a27d  lea     rcx, [rsp+130h+var_100]
0x18005a282  call    wil__scope_exit__lambda_5b0cea69da2f2023c814ebef0d37cd7f___
0x18005a287  nop
0x18005a288  jmp     short loc_18005A28D
0x18005a28a  xor     r14d, r14d
0x18005a28d  test    r15b, r15b
0x18005a290  jnz     loc_18005A55F
0x18005a296  test    edi, edi
0x18005a298  jz      short loc_18005A2A2
0x18005a29a  cmp     ebx, 80090318h
0x18005a2a0  jnz     short loc_18005A2D0
0x18005a2a2  mov     r8d, r13d
0x18005a2a5  sub     r8d, edi; len
0x18005a2a8  mov     edx, edi
0x18005a2aa  add     rdx, [rsp+130h+var_E8]; buf
0x18005a2af  xor     r9d, r9d; flags
0x18005a2b2  mov     rcx, [rsi]; s
0x18005a2b5  call    cs:__imp_recv
0x18005a2bc  nop     dword ptr [rax+rax+00h]
0x18005a2c1  mov     ecx, eax
0x18005a2c3  dec     eax
0x18005a2c5  cmp     eax, 0FFFFFFFDh
0x18005a2c8  ja      loc_18005A50D
0x18005a2ce  add     edi, ecx
0x18005a2d0  xor     edx, edx; Val
0x18005a2d2  lea     r8d, [rdx+40h]; Size
0x18005a2d6  lea     rcx, [rbp+57h+var_90]; void *
0x18005a2da  call    memset_0
0x18005a2df  mov     dword ptr [rbp+57h+var_90+4], 1
0x18005a2e6  mov     dword ptr [rbp+57h+var_90], edi
0x18005a2e9  mov     rax, [rsp+130h+var_E8]
0x18005a2ee  mov     [rbp+57h+var_90+8], rax
0x18005a2f2  mov     [rbp+57h+var_7C], r14d
0x18005a2f6  mov     [rbp+57h+var_6C], r14d
0x18005a2fa  mov     [rbp+57h+var_5C], r14d
0x18005a2fe  mov     [rbp+57h+pMessage.ulVersion], r14d
0x18005a302  mov     [rbp+57h+pMessage.cBuffers], 4
0x18005a309  lea     rax, [rbp+57h+var_90]
0x18005a30d  mov     [rbp+57h+pMessage.pBuffers], rax
0x18005a311  xor     r9d, r9d; pfQOP
0x18005a314  xor     r8d, r8d; MessageSeqNo
0x18005a317  lea     rdx, [rbp+57h+pMessage]; pMessage
0x18005a31b  mov     rcx, r12; phContext
0x18005a31e  call    cs:__imp_DecryptMessage
0x18005a325  nop     dword ptr [rax+rax+00h]
0x18005a32a  mov     ebx, eax
0x18005a32c  cmp     eax, 80090318h
0x18005a331  jnz     short loc_18005A356
0x18005a333  mov     ecx, 0C8h
0x18005a338  call    FileLogAllowEntry
0x18005a33d  test    al, al
0x18005a33f  jz      loc_18005A28D
0x18005a345  lea     rcx, aReceivekerespo_0; "ReceiveKEResponse: We need to get more "...
0x18005a34c  call    FileLogAdd
0x18005a351  jmp     loc_18005A28D
0x18005a356  test    ebx, ebx
0x18005a358  jz      short loc_18005A36E
0x18005a35a  cmp     ebx, 90321h
0x18005a360  jz      short loc_18005A36E
0x18005a362  cmp     ebx, 90317h
0x18005a368  jnz     loc_18005A483
0x18005a36e  xorps   xmm0, xmm0
0x18005a371  movups  xmmword ptr [rsp+130h+Src], xmm0
0x18005a376  mov     esi, r14d
0x18005a379  mov     r14d, dword ptr [rsp+130h+Src]
0x18005a37e  cmp     esi, [rbp+57h+pMessage.cBuffers]
0x18005a381  jnb     short loc_18005A3FE
0x18005a383  mov     edi, esi
0x18005a385  add     rdi, rdi
0x18005a388  mov     ecx, dword ptr [rbp+rdi*8+57h+var_90+4]
0x18005a38c  sub     ecx, 1
0x18005a38f  jz      short loc_18005A3D4
0x18005a391  cmp     ecx, 4
0x18005a394  jz      short loc_18005A3B6
0x18005a396  mov     ecx, 0C8h
0x18005a39b  call    FileLogAllowEntry
0x18005a3a0  test    al, al
0x18005a3a2  jz      short loc_18005A3FA
0x18005a3a4  mov     edx, dword ptr [rbp+rdi*8+57h+var_90+4]
0x18005a3a8  lea     rcx, aReceivekerespo_2; "ReceiveKEResponse: DecryptMessage recei"...
0x18005a3af  call    FileLogAdd
0x18005a3b4  jmp     short loc_18005A3FA
0x18005a3b6  cmp     ebx, 90321h
0x18005a3bc  jnz     short loc_18005A3FA
0x18005a3be  test    r14d, r14d
0x18005a3c1  jnz     short loc_18005A3FA
0x18005a3c3  movups  xmm0, xmmword ptr [rbp+rdi*8+57h+var_90]
0x18005a3c8  movups  xmmword ptr [rsp+130h+Src], xmm0
0x18005a3cd  movd    r14d, xmm0
0x18005a3d2  jmp     short loc_18005A3FA
0x18005a3d4  test    ebx, ebx
0x18005a3d6  jnz     short loc_18005A3FA
0x18005a3d8  mov     r9, [rbp+57h+var_B8]; struct NtsForNtpInfoInternal *
0x18005a3dc  mov     r8, r12; phContext
0x18005a3df  mov     edx, dword ptr [rbp+rdi*8+57h+var_90]; unsigned int
0x18005a3e3  mov     rcx, [rbp+rdi*8+57h+var_90+8]; void *
0x18005a3e8  call    ?ParseServerResponse@@YAJPEAXKAEAU_SecHandle@@AEAUNtsForNtpInfoInternal@@@Z; ParseServerResponse(void *,ulong,_SecHandle &,NtsForNtpInfoInternal &)
0x18005a3ed  mov     edi, eax
0x18005a3ef  test    eax, eax
0x18005a3f1  js      loc_18005A49E
0x18005a3f7  mov     r15b, 1
0x18005a3fa  inc     esi
0x18005a3fc  jmp     short loc_18005A37E
0x18005a3fe  xor     edi, edi
0x18005a400  cmp     ebx, 90321h
0x18005a406  mov     rsi, [rsp+130h+var_F0]
0x18005a40b  jnz     loc_18005A28A
0x18005a411  test    r14d, r14d
0x18005a414  mov     r14d, edi
0x18005a417  jz      loc_18005A28D
0x18005a41d  lea     rdx, qword_180071478
0x18005a424  lea     rcx, [rbp+57h+var_B0]
0x18005a428  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005a42d  nop
0x18005a42e  xor     r14d, r14d
0x18005a431  mov     byte ptr [rsp+130h+var_110], r14b; int
0x18005a436  lea     r9, [rsp+130h+Src]
0x18005a43b  mov     r8, r12
0x18005a43e  lea     rdx, [rbp+57h+var_B0]
0x18005a442  mov     rcx, rsi
0x18005a445  call    ?NegotiateTLS@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SecHandle@@PEAU_SecBuffer@@_N@Z; NegotiateTLS(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,std::wstring const &,_SecHandle &,_SecBuffer *,bool)
0x18005a44a  mov     esi, eax
0x18005a44c  lea     rcx, [rbp+57h+var_B0]
0x18005a450  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005a455  test    esi, esi
0x18005a457  js      short loc_18005A4D7
0x18005a459  mov     eax, dword ptr [rsp+130h+Src]
0x18005a45d  test    eax, eax
0x18005a45f  mov     rsi, [rsp+130h+var_F0]
0x18005a464  jz      loc_18005A28D
0x18005a46a  mov     edi, eax
0x18005a46c  mov     r8d, eax; Size
0x18005a46f  mov     rdx, [rsp+130h+Src+8]; Src
0x18005a474  mov     rcx, [rsp+130h+var_E8]; void *
0x18005a479  call    memmove_0
0x18005a47e  jmp     loc_18005A28D
0x18005a483  xor     ecx, ecx
0x18005a485  call    FileLogAllowEntry
0x18005a48a  test    al, al
0x18005a48c  jz      loc_18005A542
0x18005a492  lea     rcx, aReceivekerespo; "ReceiveKEResponse: DecryptMessage retur"...
0x18005a499  jmp     loc_18005A53A
0x18005a49e  mov     rcx, [rbp+5Fh]; this
0x18005a4a2  mov     r9d, edi; char *
0x18005a4a5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\w32tim"...
0x18005a4ac  mov     edx, 1E3h; void *
0x18005a4b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a4b6  nop
0x18005a4b7  cmp     [rsp+130h+var_F8], 0
0x18005a4bc  jz      short loc_18005A4D0
0x18005a4be  mov     [rsp+130h+var_F8], 0
0x18005a4c3  mov     rcx, [rsp+130h+var_100]
0x18005a4c8  mov     rcx, [rcx]; void *
0x18005a4cb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a4d0  mov     eax, edi
0x18005a4d2  jmp     loc_18005A57A
0x18005a4d7  mov     rcx, [rbp+5Fh]; this
0x18005a4db  mov     r9d, esi; char *
0x18005a4de  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\w32tim"...
0x18005a4e5  mov     edx, 1FAh; void *
0x18005a4ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a4ef  nop
0x18005a4f0  cmp     [rsp+130h+var_F8], r14b
0x18005a4f5  jz      short loc_18005A509
0x18005a4f7  mov     [rsp+130h+var_F8], r14b
0x18005a4fc  mov     rcx, [rsp+130h+var_100]
0x18005a501  mov     rcx, [rcx]; void *
0x18005a504  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a509  mov     eax, esi
0x18005a50b  jmp     short loc_18005A57A
0x18005a50d  call    cs:__imp_WSAGetLastError
0x18005a514  nop     dword ptr [rax+rax+00h]
0x18005a519  mov     ebx, eax
0x18005a51b  test    eax, eax
0x18005a51d  jle     short loc_18005A528
0x18005a51f  movzx   ebx, ax
0x18005a522  or      ebx, 80070000h
0x18005a528  xor     ecx, ecx
0x18005a52a  call    FileLogAllowEntry
0x18005a52f  test    al, al
0x18005a531  jz      short loc_18005A542
0x18005a533  lea     rcx, aReceivekerespo_1; "ReceiveKEResponse: Sending on socket fa"...
0x18005a53a  mov     edx, ebx
0x18005a53c  call    FileLogAdd
0x18005a541  nop
0x18005a542  cmp     [rsp+130h+var_F8], r14b
0x18005a547  jz      short loc_18005A55B
0x18005a549  mov     [rsp+130h+var_F8], r14b
0x18005a54e  mov     rcx, [rsp+130h+var_100]
0x18005a553  mov     rcx, [rcx]; void *
0x18005a556  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a55b  mov     eax, ebx
0x18005a55d  jmp     short loc_18005A57A
0x18005a55f  cmp     [rsp+130h+var_F8], r14b
0x18005a564  jz      short loc_18005A578
0x18005a566  mov     [rsp+130h+var_F8], r14b
0x18005a56b  mov     rcx, [rsp+130h+var_100]
0x18005a570  mov     rcx, [rcx]; void *
0x18005a573  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a578  xor     eax, eax
0x18005a57a  mov     rcx, [rbp+57h+var_50]
0x18005a57e  xor     rcx, rsp; StackCookie
0x18005a581  call    __security_check_cookie
0x18005a586  add     rsp, 0F8h
0x18005a58d  pop     r15
0x18005a58f  pop     r14
0x18005a591  pop     r13
0x18005a593  pop     r12
0x18005a595  pop     rdi
0x18005a596  pop     rsi
0x18005a597  pop     rbx
0x18005a598  pop     rbp
0x18005a599  retn
```
