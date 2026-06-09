# NegotiateTLS(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_SecHandle &,_SecBuffer *,bool)

- ea: `0x180058a5c`
- end: `0x1800591f5`
- name: `?NegotiateTLS@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SecHandle@@PEAU_SecBuffer@@_N@Z`
- size: `1945`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054b50`
- `0x18005a214`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x18003dd2c`
- `0x18003f491`
- `0x180045abc`
- `0x18005876c`
- `0x18005879c`
- `0x180058844`
- `0x180058898`
- `0x180058a5c`
- `0x180063ef0`

## import_xrefs

- `WS2_32!__imp_recv` at `0x180058d6e`
- `WS2_32!__imp_recv` at `0x180058d6e`
- `WS2_32!__imp_send` at `0x180058fb6`
- `WS2_32!__imp_send` at `0x180058fb6`
- `WS2_32!__imp_WSAGetLastError` at `0x180058fcf`
- `WS2_32!__imp_WSAGetLastError` at `0x180059154`
- `WS2_32!__imp_WSAGetLastError` at `0x180058fcf`
- `WS2_32!__imp_WSAGetLastError` at `0x180059154`
- `SspiCli!InitializeSecurityContextW` at `0x180058ebe`
- `SspiCli!InitializeSecurityContextW` at `0x180058ebe`
- `SspiCli!FreeCredentialsHandle` at `0x180058bcb`
- `SspiCli!FreeCredentialsHandle` at `0x180058c75`
- `SspiCli!FreeCredentialsHandle` at `0x180058ce7`
- `SspiCli!FreeCredentialsHandle` at `0x180058f46`
- `SspiCli!FreeCredentialsHandle` at `0x180059041`
- `SspiCli!FreeCredentialsHandle` at `0x1800590e8`
- `SspiCli!FreeCredentialsHandle` at `0x1800591a9`
- `SspiCli!FreeCredentialsHandle` at `0x180058bcb`
- `SspiCli!FreeCredentialsHandle` at `0x180058c75`
- `SspiCli!FreeCredentialsHandle` at `0x180058ce7`
- `SspiCli!FreeCredentialsHandle` at `0x180058f46`
- `SspiCli!FreeCredentialsHandle` at `0x180059041`
- `SspiCli!FreeCredentialsHandle` at `0x1800590e8`
- `SspiCli!FreeCredentialsHandle` at `0x1800591a9`
- `SspiCli!AcquireCredentialsHandleW` at `0x180058b80`
- `SspiCli!AcquireCredentialsHandleW` at `0x180058b80`

## string_xrefs

- `0x180058b77`: `Microsoft Unified Security Protocol Provider`
- `0x180058c10`: `NegotiateTLS: This is the initial attempt to create the connection\n`
- `0x180058b9d`: `onecore\ds\security\services\w32time\nts\ntstls.cpp`
- `0x180058c47`: `onecore\ds\security\services\w32time\nts\ntstls.cpp`
- `0x180058f00`: `NegotiateTLS: InitializeSecurityContextW returned unexpected hr: 0x%08X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NegotiateTLS(SOCKET *a1, __int64 a2, struct _SecHandle *a3, unsigned int *a4, char a5)
{
  int v9; // eax
  SECURITY_STATUS v10; // eax
  unsigned int v11; // ebx
  const char *v12; // r9
  __int64 result; // rax
  unsigned int v14; // edi
  char v15; // al
  int v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  int v19; // eax
  unsigned int v20; // r8d
  SECURITY_STATUS v21; // eax
  int Error; // eax
  unsigned int v23; // ebx
  unsigned int v24; // eax
  int v25; // eax
  unsigned int v26; // ebx
  int pAuthData; // [rsp+20h] [rbp-101B8h]
  PCredHandle v28; // [rsp+60h] [rbp-10178h] BYREF
  char v29; // [rsp+68h] [rbp-10170h]
  int v30; // [rsp+70h] [rbp-10168h]
  unsigned int v31; // [rsp+74h] [rbp-10164h]
  struct _SecBuffer *v32; // [rsp+78h] [rbp-10160h] BYREF
  char v33; // [rsp+80h] [rbp-10158h]
  unsigned int pfContextAttr; // [rsp+88h] [rbp-10150h] BYREF
  struct _SecBufferDesc pOutput; // [rsp+90h] [rbp-10148h] BYREF
  struct _SecBufferDesc pInput; // [rsp+A0h] [rbp-10138h] BYREF
  _DWORD v37[2]; // [rsp+B0h] [rbp-10128h] BYREF
  char *v38; // [rsp+B8h] [rbp-10120h]
  size_t Size; // [rsp+C0h] [rbp-10118h]
  __int64 v40; // [rsp+C8h] [rbp-10110h]
  struct _SecHandle *p_phCredential; // [rsp+D8h] [rbp-10100h] BYREF
  char **v42; // [rsp+E0h] [rbp-100F8h] BYREF
  char *buf[2]; // [rsp+E8h] [rbp-100F0h] BYREF
  __int128 v44; // [rsp+F8h] [rbp-100E0h]
  __int128 v45; // [rsp+108h] [rbp-100D0h] BYREF
  __int128 v46; // [rsp+118h] [rbp-100C0h]
  __int64 v47; // [rsp+128h] [rbp-100B0h]
  int v48[13]; // [rsp+130h] [rbp-100A8h] BYREF
  int v49; // [rsp+164h] [rbp-10074h]
  int v50; // [rsp+168h] [rbp-10070h]
  __int128 *v51; // [rsp+170h] [rbp-10068h]
  struct _SecHandle phCredential; // [rsp+180h] [rbp-10058h] BYREF
  char v53[65536]; // [rsp+190h] [rbp-10048h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+101D8h] [rbp+0h]

  try
  {
    v30 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    memset_0(v48, 0, 0x48u);
    phCredential = 0;
    p_phCredential = &phCredential;
    wil::scope_exit__lambda_fa9b29b6ef06adeb7346e0e4080241e5___(&v28, &p_phCredential);
    LODWORD(v46) = 4095;
    v48[0] = 5;
    v9 = v49;
    if ( a5 )
      v9 = 8;
    v49 = v9;
    v50 = 1;
    v51 = &v45;
    v10 = AcquireCredentialsHandleW(
            0,
            (LPWSTR)L"Microsoft Unified Security Protocol Provider",
            2u,
            0,
            v48,
            0,
            0,
            &phCredential,
            0);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntstls.cpp",
        (const char *)(unsigned int)v10,
        pAuthData);
      if ( v29 )
      {
        v29 = 0;
        if ( v28->dwLower || v28->dwUpper )
        {
          FreeCredentialsHandle(v28);
          v28->dwLower = 0;
          v28->dwUpper = 0;
        }
      }
      return v11;
    }
    v14 = 0;
    v31 = 0;
    v15 = FileLogAllowEntry(200);
    if ( a4 )
    {
      if ( v15 )
        FileLogAdd(L"NegotiateTLS: handling a post-Handshake authentication message\n");
      if ( *a4 > 0x10000 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(200) )
          FileLogAdd(L"NegotiateTLS: buffer too small for extraData of size %d\n", *a4);
        if ( v29 )
        {
          v29 = 0;
          if ( v28->dwLower || v28->dwUpper )
          {
            FreeCredentialsHandle(v28);
            v28->dwLower = 0;
            v28->dwUpper = 0;
          }
        }
        return 2147942487LL;
      }
      v14 = *a4;
      v31 = v14;
      memcpy_0(v53, *((const void **)a4 + 1), v14);
    }
    else
    {
      if ( v15 )
        FileLogAdd(L"NegotiateTLS: This is the initial attempt to create the connection\n");
      v16 = InitialTls(a1, a2, (__int64)a3);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9A,
          (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntstls.cpp",
          (const char *)(unsigned int)v16,
          pAuthData);
        if ( v29 )
        {
          v29 = 0;
          if ( v28->dwLower || v28->dwUpper )
          {
            FreeCredentialsHandle(v28);
            v28->dwLower = 0;
            v28->dwUpper = 0;
          }
        }
        return v17;
      }
    }
    v18 = 590610;
    v30 = 590610;
    while ( 1 )
    {
      if ( v18 != 590610 && v18 != -2146893032 )
        goto LABEL_74;
      if ( !v14 || v18 == -2146893032 )
        break;
LABEL_37:
      v38 = v53;
      v37[0] = v14;
      v37[1] = 2;
      v40 = 0;
      Size = 0;
      pInput.cBuffers = 2;
      pInput.pBuffers = (PSecBuffer)v37;
      pInput.ulVersion = 0;
      *(_OWORD *)buf = 0;
      v44 = 0;
      HIDWORD(buf[0]) = 2;
      DWORD1(v44) = 17;
      v42 = buf;
      wil::scope_exit__lambda_e809bc703c2f031fb314c3909cbf4963___(&v32, &v42, 2, v12);
      pOutput.cBuffers = v20;
      pOutput.pBuffers = (PSecBuffer)buf;
      pOutput.ulVersion = 0;
      pfContextAttr = 0;
      v21 = InitializeSecurityContextW(&phCredential, a3, 0, 0xC11Cu, 0, 0, &pInput, 0, a3, &pOutput, &pfContextAttr, 0);
      v18 = v21;
      v30 = v21;
      if ( v21 == -2146893032 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(200) )
          FileLogAdd(L"NegotiateTLS: We need to loop and grab more data from socket, hr: 0x%08X\n", v18);
      }
      else
      {
        if ( v21 != 590610 && v21 != 590694 && v21 )
        {
          if ( (unsigned __int8)FileLogAllowEntry(0) )
            FileLogAdd(L"NegotiateTLS: InitializeSecurityContextW returned unexpected hr: 0x%08X\n", v18);
          if ( v33 )
          {
            v33 = 0;
            FreeOutBuffers(v32);
          }
          if ( v29 )
          {
            v29 = 0;
            if ( v28->dwLower || v28->dwUpper )
            {
              FreeCredentialsHandle(v28);
              v28->dwLower = 0;
              v28->dwUpper = 0;
            }
          }
          return v18;
        }
        if ( (unsigned __int8)FileLogAllowEntry(200) )
          FileLogAdd(L"NegotiateTLS: Succesful hr of: 0x%08X\n", v18);
        if ( LODWORD(buf[0]) && ((send(*a1, buf[1], (int)buf[0], 0) + 1) & 0xFFFFFFFE) == 0 )
        {
          Error = WSAGetLastError();
          v23 = Error;
          if ( Error > 0 )
            v23 = (unsigned __int16)Error | 0x80070000;
          v30 = v23;
          if ( (unsigned __int8)FileLogAllowEntry(0) )
            FileLogAdd(L"NegotiateTLS: Sending on socket failed with: 0x%08X\n", v23);
          if ( v33 )
          {
            v33 = 0;
            FreeOutBuffers(v32);
          }
          if ( v29 )
          {
            v29 = 0;
            if ( v28->dwLower || v28->dwUpper )
            {
              FreeCredentialsHandle(v28);
              v28->dwLower = 0;
              v28->dwUpper = 0;
            }
          }
          return v23;
        }
        if ( !v18 )
        {
          if ( HIDWORD(Size) == 5 )
          {
            v24 = Size;
            if ( (_DWORD)Size && a4 )
            {
              *a4 = Size;
              memcpy_0(*((void **)a4 + 1), &v53[v14 - v24], v24);
            }
          }
          else if ( a4 )
          {
            *a4 = 0;
          }
          if ( v33 )
          {
            v33 = 0;
            FreeOutBuffers(v32);
          }
LABEL_74:
          if ( v29 )
          {
            v29 = 0;
            if ( v28->dwLower || v28->dwUpper )
            {
              FreeCredentialsHandle(v28);
              v28->dwLower = 0;
              v28->dwUpper = 0;
            }
          }
          return 0;
        }
        v14 = 0;
        v31 = 0;
      }
      if ( v33 )
      {
        v33 = 0;
        FreeOutBuffers(v32);
      }
    }
    v19 = recv(*a1, &v53[v14], 0x10000 - v14, 0);
    if ( (unsigned int)(v19 - 1) <= 0xFFFFFFFD )
    {
      v14 += v19;
      v31 = v14;
      goto LABEL_37;
    }
    v25 = WSAGetLastError();
    v26 = v25;
    if ( v25 > 0 )
      v26 = (unsigned __int16)v25 | 0x80070000;
    v30 = v26;
    if ( (unsigned __int8)FileLogAllowEntry(0) )
      FileLogAdd(L"NegotiateTLS: Receiving on socket failed with: 0x%08X\n", v26);
    if ( v29 )
    {
      v29 = 0;
      if ( v28->dwLower || v28->dwUpper )
      {
        FreeCredentialsHandle(v28);
        v28->dwLower = 0;
        v28->dwUpper = 0;
      }
    }
    result = v26;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x121,
                           (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntstls.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x180058a5c  push    rbx
0x180058a5e  push    rsi
0x180058a5f  push    rdi
0x180058a60  push    r12
0x180058a62  push    r13
0x180058a64  push    r14
0x180058a66  push    r15
0x180058a68  mov     eax, 101A0h
0x180058a6d  call    _alloca_probe
0x180058a72  sub     rsp, rax
0x180058a75  mov     rax, cs:__security_cookie
0x180058a7c  xor     rax, rsp
0x180058a7f  mov     [rsp+101D8h+var_48], rax
0x180058a87  mov     rsi, r9
0x180058a8a  mov     r12, r8
0x180058a8d  mov     r14, rdx
0x180058a90  mov     r15, rcx
0x180058a93  xor     r13d, r13d
0x180058a96  mov     [rsp+101D8h+var_10168], r13d
0x180058a9b  xorps   xmm0, xmm0
0x180058a9e  xor     eax, eax
0x180058aa0  movups  [rsp+101D8h+var_100D0], xmm0
0x180058aa8  movups  [rsp+101D8h+var_100C0], xmm0
0x180058ab0  mov     [rsp+101D8h+var_100B0], rax
0x180058ab8  xor     edx, edx; Val
0x180058aba  lea     r8d, [r13+48h]; Size
0x180058abe  lea     rcx, [rsp+101D8h+var_100A8]; void *
0x180058ac6  call    memset_0
0x180058acb  xorps   xmm0, xmm0
0x180058ace  movups  xmmword ptr [rsp+101D8h+var_10058.dwLower], xmm0
0x180058ad6  lea     rax, [rsp+101D8h+var_10058]
0x180058ade  mov     [rsp+101D8h+var_10100], rax
0x180058ae6  lea     rdx, [rsp+101D8h+var_10100]
0x180058aee  lea     rcx, [rsp+101D8h+var_10178]
0x180058af3  call    wil__scope_exit__lambda_fa9b29b6ef06adeb7346e0e4080241e5___
0x180058af8  nop
0x180058af9  mov     dword ptr [rsp+101D8h+var_100C0], 0FFFh
0x180058b04  mov     [rsp+101D8h+var_100A8], 5
0x180058b0f  mov     eax, [rsp+101D8h+var_10074]
0x180058b16  lea     ecx, [r13+8]
0x180058b1a  cmp     [rsp+101D8h+arg_20], r13b
0x180058b22  cmovnz  eax, ecx
0x180058b25  mov     [rsp+101D8h+var_10074], eax
0x180058b2c  mov     [rsp+101D8h+var_10070], 1
0x180058b37  lea     rax, [rsp+101D8h+var_100D0]
0x180058b3f  mov     [rsp+101D8h+var_10068], rax
0x180058b47  mov     [rsp+101D8h+ptsExpiry], r13; ptsExpiry
0x180058b4c  lea     rax, [rsp+101D8h+var_10058]
0x180058b54  mov     [rsp+101D8h+phCredential], rax; phCredential
0x180058b59  mov     [rsp+101D8h+pvGetKeyArgument], r13; pvGetKeyArgument
0x180058b5e  mov     [rsp+101D8h+pGetKeyFn], r13; pGetKeyFn
0x180058b63  lea     rax, [rsp+101D8h+var_100A8]
0x180058b6b  mov     [rsp+101D8h+pAuthData], rax; int
0x180058b70  xor     r9d, r9d; pvLogonId
0x180058b73  lea     r8d, [r13+2]; fCredentialUse
0x180058b77  lea     rdx, pszPackage; "Microsoft Unified Security Protocol Pro"...
0x180058b7e  xor     ecx, ecx; pszPrincipal
0x180058b80  call    cs:__imp_AcquireCredentialsHandleW
0x180058b87  nop     dword ptr [rax+rax+00h]
0x180058b8c  mov     ebx, eax
0x180058b8e  test    eax, eax
0x180058b90  jns     short loc_180058BEF
0x180058b92  mov     rcx, [rsp+101D8h]; this
0x180058b9a  mov     r9d, eax; char *
0x180058b9d  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\services\\w32tim"...
0x180058ba4  mov     edx, 8Fh; void *
0x180058ba9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058bae  nop
0x180058baf  cmp     [rsp+101D8h+var_10170], r13b
0x180058bb4  jz      short loc_180058BE8
0x180058bb6  mov     [rsp+101D8h+var_10170], r13b
0x180058bbb  mov     rcx, [rsp+101D8h+var_10178]; phCredential
0x180058bc0  cmp     [rcx], r13
0x180058bc3  jnz     short loc_180058BCB
0x180058bc5  cmp     [rcx+8], r13
0x180058bc9  jz      short loc_180058BE8
0x180058bcb  call    cs:__imp_FreeCredentialsHandle
0x180058bd2  nop     dword ptr [rax+rax+00h]
0x180058bd7  mov     rax, [rsp+101D8h+var_10178]
0x180058bdc  mov     [rax], r13
0x180058bdf  mov     rax, [rsp+101D8h+var_10178]
0x180058be4  mov     [rax+8], r13
0x180058be8  mov     eax, ebx
0x180058bea  jmp     loc_1800591D1
0x180058bef  mov     edi, r13d
0x180058bf2  mov     [rsp+101D8h+var_10164], r13d
0x180058bf7  mov     ebx, 0C8h
0x180058bfc  mov     ecx, ebx
0x180058bfe  call    FileLogAllowEntry
0x180058c03  test    rsi, rsi
0x180058c06  jnz     loc_180058C99
0x180058c0c  test    al, al
0x180058c0e  jz      short loc_180058C1C
0x180058c10  lea     rcx, aNegotiatetlsTh; "NegotiateTLS: This is the initial attem"...
0x180058c17  call    FileLogAdd
0x180058c1c  lea     r9, [rsp+101D8h+var_10058]
0x180058c24  mov     r8, r12
0x180058c27  mov     rdx, r14
0x180058c2a  mov     rcx, r15
0x180058c2d  call    ?InitialTls@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SecHandle@@2@Z; InitialTls(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,std::wstring const &,_SecHandle &,_SecHandle &)
0x180058c32  mov     ebx, eax
0x180058c34  test    eax, eax
0x180058c36  jns     loc_180058D28
0x180058c3c  mov     rcx, [rsp+101D8h]; this
0x180058c44  mov     r9d, eax; char *
0x180058c47  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\services\\w32tim"...
0x180058c4e  mov     edx, 9Ah; void *
0x180058c53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058c58  nop
0x180058c59  cmp     [rsp+101D8h+var_10170], r13b
0x180058c5e  jz      short loc_180058C92
0x180058c60  mov     [rsp+101D8h+var_10170], r13b
0x180058c65  mov     rcx, [rsp+101D8h+var_10178]; phCredential
0x180058c6a  cmp     [rcx], r13
0x180058c6d  jnz     short loc_180058C75
0x180058c6f  cmp     [rcx+8], r13
0x180058c73  jz      short loc_180058C92
0x180058c75  call    cs:__imp_FreeCredentialsHandle
0x180058c7c  nop     dword ptr [rax+rax+00h]
0x180058c81  mov     rax, [rsp+101D8h+var_10178]
0x180058c86  mov     [rax], r13
0x180058c89  mov     rax, [rsp+101D8h+var_10178]
0x180058c8e  mov     [rax+8], r13
0x180058c92  mov     eax, ebx
0x180058c94  jmp     loc_1800591D1
0x180058c99  test    al, al
0x180058c9b  jz      short loc_180058CA9
0x180058c9d  lea     rcx, aNegotiatetlsHa; "NegotiateTLS: handling a post-Handshake"...
0x180058ca4  call    FileLogAdd
0x180058ca9  cmp     dword ptr [rsi], 10000h
0x180058caf  jbe     short loc_180058D0E
0x180058cb1  mov     ecx, ebx
0x180058cb3  call    FileLogAllowEntry
0x180058cb8  test    al, al
0x180058cba  jz      short loc_180058CCB
0x180058cbc  mov     edx, [rsi]
0x180058cbe  lea     rcx, aNegotiatetlsBu; "NegotiateTLS: buffer too small for extr"...
0x180058cc5  call    FileLogAdd
0x180058cca  nop
0x180058ccb  cmp     [rsp+101D8h+var_10170], r13b
0x180058cd0  jz      short loc_180058D04
0x180058cd2  mov     [rsp+101D8h+var_10170], r13b
0x180058cd7  mov     rcx, [rsp+101D8h+var_10178]; phCredential
0x180058cdc  cmp     [rcx], r13
0x180058cdf  jnz     short loc_180058CE7
0x180058ce1  cmp     [rcx+8], r13
0x180058ce5  jz      short loc_180058D04
0x180058ce7  call    cs:__imp_FreeCredentialsHandle
0x180058cee  nop     dword ptr [rax+rax+00h]
0x180058cf3  mov     rax, [rsp+101D8h+var_10178]
0x180058cf8  mov     [rax], r13
0x180058cfb  mov     rax, [rsp+101D8h+var_10178]
0x180058d00  mov     [rax+8], r13
0x180058d04  mov     eax, 80070057h
0x180058d09  jmp     loc_1800591D1
0x180058d0e  mov     edi, [rsi]
0x180058d10  mov     [rsp+101D8h+var_10164], edi
0x180058d14  mov     r8d, edi; Size
0x180058d17  mov     rdx, [rsi+8]; Src
0x180058d1b  lea     rcx, [rsp+101D8h+var_10048]; void *
0x180058d23  call    memcpy_0
0x180058d28  mov     r14d, 90312h
0x180058d2e  mov     ebx, r14d
0x180058d31  mov     [rsp+101D8h+var_10168], ebx
0x180058d35  cmp     ebx, r14d
0x180058d38  jz      short loc_180058D46
0x180058d3a  cmp     ebx, 80090318h
0x180058d40  jnz     loc_1800590CC
0x180058d46  test    edi, edi
0x180058d48  jz      short loc_180058D52
0x180058d4a  cmp     ebx, 80090318h
0x180058d50  jnz     short loc_180058D8C
0x180058d52  mov     r8d, 10000h
0x180058d58  sub     r8d, edi; len
0x180058d5b  mov     eax, edi
0x180058d5d  lea     rdx, [rsp+101D8h+var_10048]
0x180058d65  add     rdx, rax; buf
0x180058d68  xor     r9d, r9d; flags
0x180058d6b  mov     rcx, [r15]; s
0x180058d6e  call    cs:__imp_recv
0x180058d75  nop     dword ptr [rax+rax+00h]
0x180058d7a  lea     ecx, [rax-1]
0x180058d7d  cmp     ecx, 0FFFFFFFDh
0x180058d80  ja      loc_180059154
0x180058d86  add     edi, eax
0x180058d88  mov     [rsp+101D8h+var_10164], edi
0x180058d8c  lea     rax, [rsp+101D8h+var_10048]
0x180058d94  mov     [rsp+101D8h+var_10120], rax
0x180058d9c  mov     [rsp+101D8h+var_10128], edi
0x180058da3  mov     r8d, 2
0x180058da9  mov     [rsp+101D8h+var_10124], r8d
0x180058db1  mov     [rsp+101D8h+var_10110], r13
0x180058db9  mov     dword ptr [rsp+101D8h+Size], r13d
0x180058dc1  mov     dword ptr [rsp+101D8h+Size+4], r13d
0x180058dc9  xorps   xmm0, xmm0
0x180058dcc  movups  xmmword ptr [rsp+101D8h+pInput.ulVersion], xmm0
0x180058dd4  mov     [rsp+101D8h+pInput.cBuffers], r8d
0x180058ddc  lea     rax, [rsp+101D8h+var_10128]
0x180058de4  mov     [rsp+101D8h+pInput.pBuffers], rax
0x180058dec  mov     [rsp+101D8h+pInput.ulVersion], r13d
0x180058df4  movups  xmmword ptr [rsp+101D8h+buf], xmm0
0x180058dfc  movups  [rsp+101D8h+var_100E0], xmm0
0x180058e04  mov     dword ptr [rsp+101D8h+buf+4], r8d
0x180058e0c  mov     dword ptr [rsp+101D8h+var_100E0+4], 11h
0x180058e17  lea     rax, [rsp+101D8h+buf]
0x180058e1f  mov     [rsp+101D8h+var_100F8], rax
0x180058e27  lea     rdx, [rsp+101D8h+var_100F8]
0x180058e2f  lea     rcx, [rsp+101D8h+var_10160]
0x180058e34  call    wil__scope_exit__lambda_e809bc703c2f031fb314c3909cbf4963___
0x180058e39  nop
0x180058e3a  movups  xmmword ptr [rsp+101D8h+var_10148.ulVersion], xmm0
0x180058e42  mov     [rsp+101D8h+var_10148.cBuffers], r8d
0x180058e4a  lea     rax, [rsp+101D8h+buf]
0x180058e52  mov     [rsp+101D8h+var_10148.pBuffers], rax
0x180058e5a  mov     [rsp+101D8h+var_10148.ulVersion], r13d
0x180058e62  mov     [rsp+101D8h+var_10150], r13d
0x180058e6a  mov     [rsp+101D8h+var_10180], r13; ptsExpiry
0x180058e6f  lea     rax, [rsp+101D8h+var_10150]
0x180058e77  mov     [rsp+101D8h+pfContextAttr], rax; pfContextAttr
0x180058e7c  lea     rax, [rsp+101D8h+var_10148]
0x180058e84  mov     [rsp+101D8h+pOutput], rax; pOutput
0x180058e89  mov     [rsp+101D8h+ptsExpiry], r12; phNewContext
0x180058e8e  mov     dword ptr [rsp+101D8h+phCredential], r13d; Reserved2
0x180058e93  lea     rax, [rsp+101D8h+pInput]
0x180058e9b  mov     [rsp+101D8h+pvGetKeyArgument], rax; pInput
0x180058ea0  mov     dword ptr [rsp+101D8h+pGetKeyFn], r13d; TargetDataRep
0x180058ea5  mov     dword ptr [rsp+101D8h+pAuthData], r13d; Reserved1
0x180058eaa  mov     r9d, 0C11Ch; fContextReq
0x180058eb0  xor     r8d, r8d; pszTargetName
0x180058eb3  mov     rdx, r12; phContext
0x180058eb6  lea     rcx, [rsp+101D8h+var_10058]; phCredential
0x180058ebe  call    cs:__imp_InitializeSecurityContextW
0x180058ec5  nop     dword ptr [rax+rax+00h]
0x180058eca  mov     ebx, eax
0x180058ecc  mov     [rsp+101D8h+var_10168], eax
0x180058ed0  cmp     eax, 80090318h
0x180058ed5  jz      loc_180059116
0x180058edb  cmp     eax, r14d
0x180058ede  jz      loc_180058F7B
0x180058ee4  cmp     eax, 90366h
0x180058ee9  jz      short loc_180058F6A
0x180058eeb  test    eax, eax
0x180058eed  jz      loc_180058F7B
0x180058ef3  xor     ecx, ecx
0x180058ef5  call    FileLogAllowEntry
0x180058efa  test    al, al
0x180058efc  jz      short loc_180058F0D
0x180058efe  mov     edx, ebx
0x180058f00  lea     rcx, aNegotiatetlsIn; "NegotiateTLS: InitializeSecurityContext"...
0x180058f07  call    FileLogAdd
0x180058f0c  nop
0x180058f0d  cmp     [rsp+101D8h+var_10158], r13b
0x180058f15  jz      short loc_180058F2A
0x180058f17  mov     [rsp+101D8h+var_10158], r13b
0x180058f1f  mov     rcx, [rsp+101D8h+var_10160]; struct _SecBuffer *
0x180058f24  call    ?FreeOutBuffers@@YAXQEAU_SecBuffer@@@Z; FreeOutBuffers(_SecBuffer * const)
0x180058f29  nop
0x180058f2a  cmp     [rsp+101D8h+var_10170], r13b
0x180058f2f  jz      short loc_180058F63
0x180058f31  mov     [rsp+101D8h+var_10170], r13b
0x180058f36  mov     rcx, [rsp+101D8h+var_10178]; phCredential
0x180058f3b  cmp     [rcx], r13
0x180058f3e  jnz     short loc_180058F46
0x180058f40  cmp     [rcx+8], r13
0x180058f44  jz      short loc_180058F63
0x180058f46  call    cs:__imp_FreeCredentialsHandle
0x180058f4d  nop     dword ptr [rax+rax+00h]
0x180058f52  mov     rax, [rsp+101D8h+var_10178]
0x180058f57  mov     [rax], r13
0x180058f5a  mov     rax, [rsp+101D8h+var_10178]
0x180058f5f  mov     [rax+8], r13
0x180058f63  mov     eax, ebx
0x180058f65  jmp     loc_1800591D1
0x180058f6a  cmp     ebx, r14d
0x180058f6d  jz      short loc_180058F7B
0x180058f6f  cmp     ebx, 90366h
0x180058f75  jnz     loc_180059065
0x180058f7b  mov     ecx, 0C8h
0x180058f80  call    FileLogAllowEntry
0x180058f85  test    al, al
0x180058f87  jz      short loc_180058F97
0x180058f89  mov     edx, ebx
0x180058f8b  lea     rcx, aNegotiatetlsSu; "NegotiateTLS: Succesful hr of: 0x%08X\n"
0x180058f92  call    FileLogAdd
0x180058f97  mov     r8d, dword ptr [rsp+101D8h+buf]; len
0x180058f9f  test    r8d, r8d
0x180058fa2  jz      loc_180059065
0x180058fa8  xor     r9d, r9d; flags
0x180058fab  mov     rdx, [rsp+101D8h+buf+8]; buf
0x180058fb3  mov     rcx, [r15]; s
0x180058fb6  call    cs:__imp_send
0x180058fbd  nop     dword ptr [rax+rax+00h]
0x180058fc2  inc     eax
0x180058fc4  test    eax, 0FFFFFFFEh
0x180058fc9  jnz     loc_180059065
0x180058fcf  call    cs:__imp_WSAGetLastError
0x180058fd6  nop     dword ptr [rax+rax+00h]
0x180058fdb  mov     ebx, eax
0x180058fdd  test    eax, eax
0x180058fdf  jle     short loc_180058FEA
  ... truncated ...
```
