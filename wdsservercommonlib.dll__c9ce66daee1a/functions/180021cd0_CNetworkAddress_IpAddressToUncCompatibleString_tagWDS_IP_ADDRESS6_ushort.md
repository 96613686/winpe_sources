# CNetworkAddress::IpAddressToUncCompatibleString(tagWDS_IP_ADDRESS6,ushort * *)

- ea: `0x180021cd0`
- end: `0x180021edf`
- name: `?IpAddressToUncCompatibleString@CNetworkAddress@@SAKUtagWDS_IP_ADDRESS6@@PEAPEAG@Z`
- size: `527`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000179c`
- `0x18000cd48`
- `0x180021cd0`
- `0x180022b9c`
- `0x18002e468`
- `0x18002f3a2`
- `0x18002f3e0`

## import_xrefs

- `WS2_32!WSAAddressToStringW` at `0x180021d70`
- `WS2_32!WSAAddressToStringW` at `0x180021e01`
- `WS2_32!WSAAddressToStringW` at `0x180021d70`
- `WS2_32!WSAAddressToStringW` at `0x180021e01`
- `WS2_32!__imp_WSAGetLastError` at `0x180021d83`
- `WS2_32!__imp_WSAGetLastError` at `0x180021e11`
- `WS2_32!__imp_WSAGetLastError` at `0x180021d83`
- `WS2_32!__imp_WSAGetLastError` at `0x180021e11`

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
0x180021cd0  mov     [rsp-38h+arg_10], rbx
0x180021cd5  push    rbp
0x180021cd6  push    rsi
0x180021cd7  push    rdi
0x180021cd8  push    r12
0x180021cda  push    r13
0x180021cdc  push    r14
0x180021cde  push    r15
0x180021ce0  mov     rbp, rsp
0x180021ce3  sub     rsp, 70h
0x180021ce7  mov     rax, cs:__security_cookie
0x180021cee  xor     rax, rsp
0x180021cf1  mov     [rbp+var_8], rax
0x180021cf5  mov     esi, [rcx+10h]
0x180021cf8  xor     eax, eax
0x180021cfa  xor     r13d, r13d
0x180021cfd  mov     [rbp+var_18], rax
0x180021d01  mov     [rbp+var_10], eax
0x180021d04  xorps   xmm0, xmm0
0x180021d07  mov     [rbp+dwAddressStringLength], r13d
0x180021d0b  xorps   xmm1, xmm1
0x180021d0e  lea     ebx, [rax+2]
0x180021d11  mov     r12, rdx
0x180021d14  movups  xmmword ptr [rbp+saAddress.sa_family], xmm0
0x180021d18  movups  [rbp+var_28], xmm1
0x180021d1c  cmp     esi, 4
0x180021d1f  jnz     short loc_180021D34
0x180021d21  mov     eax, [rcx]
0x180021d23  lea     r14, [rbp+saAddress]
0x180021d27  mov     dword ptr [rbp+saAddress.sa_data+2], eax
0x180021d2a  lea     r15d, [r13+10h]
0x180021d2e  mov     [rbp+saAddress.sa_family], bx
0x180021d32  jmp     short loc_180021D5B
0x180021d34  cmp     esi, 10h
0x180021d37  jnz     loc_180021EB3
0x180021d3d  lea     eax, [rsi+7]
0x180021d40  mov     rdx, rcx; Src
0x180021d43  lea     rcx, [rbp+var_28+8]; void *
0x180021d47  mov     word ptr [rbp+var_28], ax
0x180021d4b  mov     r8, rsi; Size
0x180021d4e  call    memcpy_0
0x180021d53  lea     r14, [rbp+var_28]
0x180021d57  lea     r15d, [rsi+0Ch]
0x180021d5b  lea     rax, [rbp+dwAddressStringLength]
0x180021d5f  xor     r9d, r9d; lpszAddressString
0x180021d62  xor     r8d, r8d; lpProtocolInfo
0x180021d65  mov     [rsp+70h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x180021d6a  mov     edx, r15d; dwAddressLength
0x180021d6d  mov     rcx, r14; lpsaAddress
0x180021d70  call    cs:__imp_WSAAddressToStringW
0x180021d77  nop     dword ptr [rax+rax+00h]
0x180021d7c  mov     eax, [rbp+dwAddressStringLength]
0x180021d7f  test    eax, eax
0x180021d81  jnz     short loc_180021DA9
0x180021d83  call    cs:__imp_WSAGetLastError
0x180021d8a  nop     dword ptr [rax+rax+00h]
0x180021d8f  mov     ebx, eax
0x180021d91  cmp     eax, 2726h
0x180021d96  jnz     loc_180021EB8
0x180021d9c  mov     eax, 401h
0x180021da1  mov     ebx, 2
0x180021da6  mov     [rbp+dwAddressStringLength], eax
0x180021da9  cmp     esi, 10h
0x180021dac  jnz     short loc_180021DB4
0x180021dae  add     eax, 11h
0x180021db1  mov     [rbp+dwAddressStringLength], eax
0x180021db4  mov     ecx, eax
0x180021db6  mov     rax, rbx
0x180021db9  mul     rcx
0x180021dbc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180021dc3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021dca  cmovo   rax, rcx
0x180021dce  mov     rcx, rax; unsigned __int64
0x180021dd1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180021dd6  mov     rdi, rax
0x180021dd9  test    rax, rax
0x180021ddc  jnz     short loc_180021DE6
0x180021dde  lea     ebx, [rax+8]
0x180021de1  jmp     loc_180021EB8
0x180021de6  mov     eax, [rbp+dwAddressStringLength]
0x180021de9  mov     r9, rdi; lpszAddressString
0x180021dec  mov     [rbp+var_3C], eax
0x180021def  xor     r8d, r8d; lpProtocolInfo
0x180021df2  lea     rax, [rbp+var_3C]
0x180021df6  mov     edx, r15d; dwAddressLength
0x180021df9  mov     rcx, r14; lpsaAddress
0x180021dfc  mov     [rsp+70h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x180021e01  call    cs:__imp_WSAAddressToStringW
0x180021e08  nop     dword ptr [rax+rax+00h]
0x180021e0d  test    eax, eax
0x180021e0f  jz      short loc_180021E21
0x180021e11  call    cs:__imp_WSAGetLastError
0x180021e18  nop     dword ptr [rax+rax+00h]
0x180021e1d  mov     ebx, eax
0x180021e1f  jmp     short loc_180021EA0
0x180021e21  cmp     esi, 10h
0x180021e24  jnz     loc_180021EAA
0x180021e2a  movzx   eax, word ptr [rdi]
0x180021e2d  mov     rcx, rdi
0x180021e30  jmp     short loc_180021E43
0x180021e32  cmp     ax, 3Ah ; ':'
0x180021e36  jnz     short loc_180021E3D
0x180021e38  mov     word ptr [rcx], 2Dh ; '-'
0x180021e3d  add     rcx, rbx
0x180021e40  movzx   eax, word ptr [rcx]
0x180021e43  test    ax, ax
0x180021e46  jnz     short loc_180021E32
0x180021e48  movzx   eax, word ptr [rdi]
0x180021e4b  mov     rcx, rdi
0x180021e4e  jmp     short loc_180021E61
0x180021e50  cmp     ax, 25h ; '%'
0x180021e54  jnz     short loc_180021E5B
0x180021e56  mov     word ptr [rcx], 73h ; 's'
0x180021e5b  add     rcx, rbx
0x180021e5e  movzx   eax, word ptr [rcx]
0x180021e61  test    ax, ax
0x180021e64  jnz     short loc_180021E50
0x180021e66  mov     edx, [rbp+dwAddressStringLength]; unsigned __int64
0x180021e69  lea     r8, aIpv6LiteralNet; ".ipv6-literal.net"
0x180021e70  mov     rcx, rdi; unsigned __int16 *
0x180021e73  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021e78  mov     r9d, 407h
0x180021e7e  mov     ecx, eax
0x180021e80  mov     ebx, eax
0x180021e82  call    ElValidateHr_7
0x180021e87  test    eax, eax
0x180021e89  jns     short loc_180021EAA
0x180021e8b  test    ebx, ebx
0x180021e8d  jns     short loc_180021EA0
0x180021e8f  mov     eax, ebx
0x180021e91  and     eax, 1FFF0000h
0x180021e96  cmp     eax, 70000h
0x180021e9b  jnz     short loc_180021EA0
0x180021e9d  movzx   ebx, bx
0x180021ea0  mov     rcx, rdi; lpMem
0x180021ea3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021ea8  jmp     short loc_180021EB8
0x180021eaa  mov     [r12], rdi
0x180021eae  mov     ebx, r13d
0x180021eb1  jmp     short loc_180021EB8
0x180021eb3  mov     ebx, 57h ; 'W'
0x180021eb8  mov     eax, ebx
0x180021eba  mov     rcx, [rbp+var_8]
0x180021ebe  xor     rcx, rsp; StackCookie
0x180021ec1  call    __security_check_cookie
0x180021ec6  mov     rbx, [rsp+70h+arg_10]
0x180021ece  add     rsp, 70h
0x180021ed2  pop     r15
0x180021ed4  pop     r14
0x180021ed6  pop     r13
0x180021ed8  pop     r12
0x180021eda  pop     rdi
0x180021edb  pop     rsi
0x180021edc  pop     rbp
0x180021edd  retn
```
