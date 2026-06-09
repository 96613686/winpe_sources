# CNetworkAddress::IpAddressToUncCompatibleString(tagWDS_IP_ADDRESS6,ushort * *)

- ea: `0x180022d50`
- end: `0x180022f66`
- name: `?IpAddressToUncCompatibleString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z`
- size: `534`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000214c`
- `0x1800024a6`
- `0x18000d888`
- `0x180022d50`
- `0x180023c1c`
- `0x180030390`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180022f23`
- `msvcrt!??3@YAXPEAX@Z` at `0x180022f23`
- `WS2_32!WSAAddressToStringW` at `0x180022df0`
- `WS2_32!WSAAddressToStringW` at `0x180022e81`
- `WS2_32!WSAAddressToStringW` at `0x180022df0`
- `WS2_32!WSAAddressToStringW` at `0x180022e81`
- `WS2_32!__imp_WSAGetLastError` at `0x180022e03`
- `WS2_32!__imp_WSAGetLastError` at `0x180022e91`
- `WS2_32!__imp_WSAGetLastError` at `0x180022e03`
- `WS2_32!__imp_WSAGetLastError` at `0x180022e91`

## pseudocode

```c
__int64 __fastcall CNetworkAddress::IpAddressToUncCompatibleString(_DWORD *a1, unsigned __int16 **a2)
{
  size_t v2; // rsi
  struct sockaddr *p_saAddress; // r14
  DWORD v5; // r15d
  DWORD v6; // eax
  int Error; // ebx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // kr00_8
  WCHAR *v10; // rax
  unsigned __int16 *v11; // rdi
  unsigned __int16 v12; // ax
  unsigned __int16 *v13; // rcx
  unsigned __int16 v14; // ax
  unsigned __int16 *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  DWORD dwAddressStringLength; // [rsp+30h] [rbp-40h] BYREF
  DWORD lpdwAddressStringLength; // [rsp+34h] [rbp-3Ch] BYREF
  struct sockaddr saAddress; // [rsp+38h] [rbp-38h] BYREF
  __int128 v22; // [rsp+48h] [rbp-28h] BYREF
  __int64 v23; // [rsp+58h] [rbp-18h]
  int v24; // [rsp+60h] [rbp-10h]

  v2 = (unsigned int)a1[4];
  v23 = 0;
  v24 = 0;
  dwAddressStringLength = 0;
  saAddress = 0;
  v22 = 0;
  if ( (_DWORD)v2 == 4 )
  {
    p_saAddress = &saAddress;
    *(_DWORD *)&saAddress.sa_data[2] = *a1;
    v5 = 16;
    saAddress.sa_family = 2;
  }
  else
  {
    if ( (_DWORD)v2 != 16 )
      return 87;
    LOWORD(v22) = 23;
    memcpy_0((char *)&v22 + 8, a1, v2);
    p_saAddress = (struct sockaddr *)&v22;
    v5 = 28;
  }
  WSAAddressToStringW(p_saAddress, v5, 0, 0, &dwAddressStringLength);
  v6 = dwAddressStringLength;
  if ( !dwAddressStringLength )
  {
    Error = WSAGetLastError();
    if ( Error != 10022 )
      return (unsigned int)Error;
    v6 = 1025;
    dwAddressStringLength = 1025;
  }
  if ( (_DWORD)v2 == 16 )
  {
    v6 += 17;
    dwAddressStringLength = v6;
  }
  v9 = v6;
  v8 = 2LL * v6;
  if ( !is_mul_ok(v9, 2u) )
    v8 = -1;
  v10 = (WCHAR *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    lpdwAddressStringLength = dwAddressStringLength;
    if ( WSAAddressToStringW(p_saAddress, v5, 0, v10, &lpdwAddressStringLength) )
    {
      Error = WSAGetLastError();
    }
    else
    {
      if ( (_DWORD)v2 != 16 )
        goto LABEL_32;
      v12 = *v11;
      v13 = v11;
      while ( v12 )
      {
        if ( v12 == 58 )
          *v13 = 45;
        v12 = *++v13;
      }
      v14 = *v11;
      v15 = v11;
      while ( v14 )
      {
        if ( v14 == 37 )
          *v15 = 115;
        v14 = *++v15;
      }
      Error = StringCchCatW(v11, dwAddressStringLength, L".ipv6-literal.net");
      if ( (int)ElValidateHr_7(Error, v16, v17, 0x407u) >= 0 )
      {
LABEL_32:
        *a2 = v11;
        return 0;
      }
      if ( Error < 0 && (Error & 0x1FFF0000) == 0x70000 )
        Error = (unsigned __int16)Error;
    }
    operator delete(v11);
  }
  else
  {
    return 8;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180022d50  mov     [rsp-38h+arg_10], rbx
0x180022d55  push    rbp
0x180022d56  push    rsi
0x180022d57  push    rdi
0x180022d58  push    r12
0x180022d5a  push    r13
0x180022d5c  push    r14
0x180022d5e  push    r15
0x180022d60  mov     rbp, rsp
0x180022d63  sub     rsp, 70h
0x180022d67  mov     rax, cs:__security_cookie
0x180022d6e  xor     rax, rsp
0x180022d71  mov     [rbp+var_8], rax
0x180022d75  mov     esi, [rcx+10h]
0x180022d78  xor     eax, eax
0x180022d7a  xor     r13d, r13d
0x180022d7d  mov     [rbp+var_18], rax
0x180022d81  mov     [rbp+var_10], eax
0x180022d84  xorps   xmm0, xmm0
0x180022d87  mov     [rbp+dwAddressStringLength], r13d
0x180022d8b  xorps   xmm1, xmm1
0x180022d8e  lea     ebx, [rax+2]
0x180022d91  mov     r12, rdx
0x180022d94  movups  xmmword ptr [rbp+saAddress.sa_family], xmm0
0x180022d98  movups  [rbp+var_28], xmm1
0x180022d9c  cmp     esi, 4
0x180022d9f  jnz     short loc_180022DB4
0x180022da1  mov     eax, [rcx]
0x180022da3  lea     r14, [rbp+saAddress]
0x180022da7  mov     dword ptr [rbp+saAddress.sa_data+2], eax
0x180022daa  lea     r15d, [r13+10h]
0x180022dae  mov     [rbp+saAddress.sa_family], bx
0x180022db2  jmp     short loc_180022DDB
0x180022db4  cmp     esi, 10h
0x180022db7  jnz     loc_180022F3A
0x180022dbd  lea     eax, [rsi+7]
0x180022dc0  mov     rdx, rcx; Src
0x180022dc3  lea     rcx, [rbp+var_28+8]; void *
0x180022dc7  mov     word ptr [rbp+var_28], ax
0x180022dcb  mov     r8, rsi; Size
0x180022dce  call    memcpy_0
0x180022dd3  lea     r14, [rbp+var_28]
0x180022dd7  lea     r15d, [rsi+0Ch]
0x180022ddb  lea     rax, [rbp+dwAddressStringLength]
0x180022ddf  xor     r9d, r9d; lpszAddressString
0x180022de2  xor     r8d, r8d; lpProtocolInfo
0x180022de5  mov     [rsp+70h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x180022dea  mov     edx, r15d; dwAddressLength
0x180022ded  mov     rcx, r14; lpsaAddress
0x180022df0  call    cs:__imp_WSAAddressToStringW
0x180022df7  nop     dword ptr [rax+rax+00h]
0x180022dfc  mov     eax, [rbp+dwAddressStringLength]
0x180022dff  test    eax, eax
0x180022e01  jnz     short loc_180022E29
0x180022e03  call    cs:__imp_WSAGetLastError
0x180022e0a  nop     dword ptr [rax+rax+00h]
0x180022e0f  mov     ebx, eax
0x180022e11  cmp     eax, 2726h
0x180022e16  jnz     loc_180022F3F
0x180022e1c  mov     eax, 401h
0x180022e21  mov     ebx, 2
0x180022e26  mov     [rbp+dwAddressStringLength], eax
0x180022e29  cmp     esi, 10h
0x180022e2c  jnz     short loc_180022E34
0x180022e2e  add     eax, 11h
0x180022e31  mov     [rbp+dwAddressStringLength], eax
0x180022e34  mov     ecx, eax
0x180022e36  mov     rax, rbx
0x180022e39  mul     rcx
0x180022e3c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180022e43  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022e4a  cmovo   rax, rcx
0x180022e4e  mov     rcx, rax; unsigned __int64
0x180022e51  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180022e56  mov     rdi, rax
0x180022e59  test    rax, rax
0x180022e5c  jnz     short loc_180022E66
0x180022e5e  lea     ebx, [rax+8]
0x180022e61  jmp     loc_180022F3F
0x180022e66  mov     eax, [rbp+dwAddressStringLength]
0x180022e69  mov     r9, rdi; lpszAddressString
0x180022e6c  mov     [rbp+var_3C], eax
0x180022e6f  xor     r8d, r8d; lpProtocolInfo
0x180022e72  lea     rax, [rbp+var_3C]
0x180022e76  mov     edx, r15d; dwAddressLength
0x180022e79  mov     rcx, r14; lpsaAddress
0x180022e7c  mov     [rsp+70h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x180022e81  call    cs:__imp_WSAAddressToStringW
0x180022e88  nop     dword ptr [rax+rax+00h]
0x180022e8d  test    eax, eax
0x180022e8f  jz      short loc_180022EA1
0x180022e91  call    cs:__imp_WSAGetLastError
0x180022e98  nop     dword ptr [rax+rax+00h]
0x180022e9d  mov     ebx, eax
0x180022e9f  jmp     short loc_180022F20
0x180022ea1  cmp     esi, 10h
0x180022ea4  jnz     loc_180022F31
0x180022eaa  movzx   eax, word ptr [rdi]
0x180022ead  mov     rcx, rdi
0x180022eb0  jmp     short loc_180022EC3
0x180022eb2  cmp     ax, 3Ah ; ':'
0x180022eb6  jnz     short loc_180022EBD
0x180022eb8  mov     word ptr [rcx], 2Dh ; '-'
0x180022ebd  add     rcx, rbx
0x180022ec0  movzx   eax, word ptr [rcx]
0x180022ec3  test    ax, ax
0x180022ec6  jnz     short loc_180022EB2
0x180022ec8  movzx   eax, word ptr [rdi]
0x180022ecb  mov     rcx, rdi
0x180022ece  jmp     short loc_180022EE1
0x180022ed0  cmp     ax, 25h ; '%'
0x180022ed4  jnz     short loc_180022EDB
0x180022ed6  mov     word ptr [rcx], 73h ; 's'
0x180022edb  add     rcx, rbx
0x180022ede  movzx   eax, word ptr [rcx]
0x180022ee1  test    ax, ax
0x180022ee4  jnz     short loc_180022ED0
0x180022ee6  mov     edx, [rbp+dwAddressStringLength]; unsigned __int64
0x180022ee9  lea     r8, aIpv6LiteralNet; ".ipv6-literal.net"
0x180022ef0  mov     rcx, rdi; unsigned __int16 *
0x180022ef3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022ef8  mov     r9d, 407h
0x180022efe  mov     ecx, eax
0x180022f00  mov     ebx, eax
0x180022f02  call    ElValidateHr_7
0x180022f07  test    eax, eax
0x180022f09  jns     short loc_180022F31
0x180022f0b  test    ebx, ebx
0x180022f0d  jns     short loc_180022F20
0x180022f0f  mov     eax, ebx
0x180022f11  and     eax, 1FFF0000h
0x180022f16  cmp     eax, 70000h
0x180022f1b  jnz     short loc_180022F20
0x180022f1d  movzx   ebx, bx
0x180022f20  mov     rcx, rdi
0x180022f23  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180022f2a  nop     dword ptr [rax+rax+00h]
0x180022f2f  jmp     short loc_180022F3F
0x180022f31  mov     [r12], rdi
0x180022f35  mov     ebx, r13d
0x180022f38  jmp     short loc_180022F3F
0x180022f3a  mov     ebx, 57h ; 'W'
0x180022f3f  mov     eax, ebx
0x180022f41  mov     rcx, [rbp+var_8]
0x180022f45  xor     rcx, rsp; StackCookie
0x180022f48  call    __security_check_cookie
0x180022f4d  mov     rbx, [rsp+70h+arg_10]
0x180022f55  add     rsp, 70h
0x180022f59  pop     r15
0x180022f5b  pop     r14
0x180022f5d  pop     r13
0x180022f5f  pop     r12
0x180022f61  pop     rdi
0x180022f62  pop     rsi
0x180022f63  pop     rbp
0x180022f64  retn
```
