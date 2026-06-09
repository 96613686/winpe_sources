# CNetworkAddress::FindLocalInterface(tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)

- ea: `0x180022f20`
- end: `0x180023343`
- name: `?FindLocalInterface@CNetworkAddress@@SAKPEAUtagWDS_IP_ADDRESS6@@0@Z`
- size: `1059`
- prototype: `static unsigned int(struct tagWDS_IP_ADDRESS6 *, struct tagWDS_IP_ADDRESS6 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003590`

## callees

- `0x18001a9a8`
- `0x180022f20`
- `0x180025850`
- `0x180025914`
- `0x1800259d8`
- `0x180026670`
- `0x180026694`
- `0x180026d3a`
- `0x180026d46`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x1800231ff`
- `WS2_32!WSAIoctl` at `0x180023284`
- `WS2_32!WSAIoctl` at `0x1800231ff`
- `WS2_32!WSAIoctl` at `0x180023284`
- `WS2_32!WSASocketW` at `0x180023123`
- `WS2_32!WSASocketW` at `0x180023123`
- `WS2_32!WSAAddressToStringW` at `0x18002300d`
- `WS2_32!WSAAddressToStringW` at `0x180023077`
- `WS2_32!WSAAddressToStringW` at `0x18002300d`
- `WS2_32!WSAAddressToStringW` at `0x180023077`
- `WS2_32!FreeAddrInfoW` at `0x180023312`
- `WS2_32!FreeAddrInfoW` at `0x180023312`
- `WS2_32!GetAddrInfoW` at `0x1800230ed`
- `WS2_32!GetAddrInfoW` at `0x1800230ed`
- `WS2_32!__imp_closesocket` at `0x180023303`
- `WS2_32!__imp_closesocket` at `0x180023303`
- `WS2_32!__imp_WSAGetLastError` at `0x18002301a`
- `WS2_32!__imp_WSAGetLastError` at `0x180023081`
- `WS2_32!__imp_WSAGetLastError` at `0x180023135`
- `WS2_32!__imp_WSAGetLastError` at `0x180023205`
- `WS2_32!__imp_WSAGetLastError` at `0x180023212`
- `WS2_32!__imp_WSAGetLastError` at `0x180023292`
- `WS2_32!__imp_WSAGetLastError` at `0x18002301a`
- `WS2_32!__imp_WSAGetLastError` at `0x180023081`
- `WS2_32!__imp_WSAGetLastError` at `0x180023135`
- `WS2_32!__imp_WSAGetLastError` at `0x180023205`
- `WS2_32!__imp_WSAGetLastError` at `0x180023212`
- `WS2_32!__imp_WSAGetLastError` at `0x180023292`

## string_xrefs

- `0x1800230ac`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x180023156`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x18002321e`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`
- `0x18002329e`: `onecore\base\eco\wds\wdslib\common\src\netaddr.cpp`

## pseudocode

```c
__int64 __fastcall CNetworkAddress::FindLocalInterface(struct tagWDS_IP_ADDRESS6 *a1, struct tagWDS_IP_ADDRESS6 *a2)
{
  SOCKET v4; // r14
  int v5; // ecx
  __int64 v6; // rdx
  int v7; // eax
  __int128 v8; // xmm0
  void *v9; // rdi
  struct sockaddr *p_saAddress; // r15
  DWORD v11; // r12d
  DWORD v12; // eax
  unsigned int Error; // ebx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // kr00_8
  const char *v16; // rdx
  const char *v17; // rdx
  unsigned int v18; // eax
  const char *v19; // rdx
  unsigned __int64 v20; // r15
  DWORD v21; // r12d
  int v22; // edi
  const char *v23; // rdx
  const char *v24; // r8
  unsigned int v25; // r9d
  signed int v26; // eax
  unsigned int v27; // eax
  const char *v28; // rdx
  _DWORD *v29; // rdi
  unsigned int v30; // eax
  const char *v31; // rdx
  DWORD dwAddressStringLength; // [rsp+50h] [rbp-79h] BYREF
  DWORD cbBytesReturned[3]; // [rsp+54h] [rbp-75h] BYREF
  void *v35; // [rsp+60h] [rbp-69h]
  int v36; // [rsp+68h] [rbp-61h]
  int v37; // [rsp+6Ch] [rbp-5Dh]
  __int128 Src; // [rsp+70h] [rbp-59h] BYREF
  int v39; // [rsp+80h] [rbp-49h]
  ADDRINFOW pHints; // [rsp+90h] [rbp-39h] BYREF
  struct sockaddr saAddress; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v42; // [rsp+D0h] [rbp+7h] BYREF
  _QWORD v43[2]; // [rsp+D8h] [rbp+Fh] BYREF
  int v44; // [rsp+E8h] [rbp+1Fh]

  v4 = 0;
  v35 = 0;
  memset_0(&pHints, 0, sizeof(pHints));
  v5 = *((_DWORD *)a1 + 4);
  v6 = 2;
  memset(cbBytesReturned, 0, sizeof(cbBytesReturned));
  v7 = 23;
  v8 = *(_OWORD *)a1;
  v37 = v5;
  v39 = v5;
  if ( v5 == 4 )
    v7 = 2;
  Src = v8;
  v36 = v7;
  v9 = 0;
  dwAddressStringLength = 0;
  *(_QWORD *)&saAddress.sa_family = 0;
  *(_QWORD *)&saAddress.sa_data[6] = 0;
  v42 = 0;
  v43[0] = 0;
  v43[1] = 0;
  v44 = 0;
  if ( v5 == 4 )
  {
    p_saAddress = &saAddress;
    *(_DWORD *)&saAddress.sa_data[2] = Src;
    v11 = 16;
    saAddress.sa_family = 2;
  }
  else
  {
    if ( v5 != 16 )
    {
      Error = 87;
      goto LABEL_18;
    }
    LOWORD(v42) = 23;
    memmove_0(v43, &Src, 0x10u);
    p_saAddress = (struct sockaddr *)&v42;
    v11 = 28;
  }
  WSAAddressToStringW(p_saAddress, v11, 0, 0, &dwAddressStringLength);
  v12 = dwAddressStringLength;
  if ( !dwAddressStringLength )
  {
    Error = WSAGetLastError();
    if ( Error != 10022 )
    {
LABEL_18:
      if ( Error && v9 )
        operator delete(v9);
      goto LABEL_21;
    }
    v12 = 1025;
    dwAddressStringLength = 1025;
  }
  v15 = v12;
  v14 = 2LL * v12;
  if ( !is_mul_ok(v15, 2u) )
    v14 = -1;
  v9 = operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 )
  {
    Error = 8;
LABEL_21:
    v9 = 0;
    goto LABEL_22;
  }
  if ( WSAAddressToStringW(p_saAddress, v11, 0, (LPWSTR)v9, &dwAddressStringLength) )
  {
    Error = WSAGetLastError();
    goto LABEL_18;
  }
  v35 = v9;
  Error = 0;
LABEL_22:
  if ( !ElValidateWin32(Error, (const char *)v6, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0x6CFu) )
  {
    pHints.ai_socktype = 2;
    pHints.ai_protocol = 17;
    pHints.ai_flags = 4;
    Error = GetAddrInfoW((PCWSTR)v9, 0, &pHints, (PADDRINFOW *)&cbBytesReturned[1]);
    if ( !ElValidateWin32(Error, v16, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0x6D9u) )
    {
      v4 = WSASocketW(v36, 2, 0, 0, 0, 0);
      if ( v4 == -1 )
      {
        v18 = WSAGetLastError();
        Error = ElValidateWin32(v18, v19, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0x6E2u);
      }
      else
      {
        v20 = *(_QWORD *)(*(_QWORD *)&cbBytesReturned[1] + 16LL);
        v21 = -1;
        if ( v20 <= 0xFFFFFFFF )
          v21 = *(_QWORD *)(*(_QWORD *)&cbBytesReturned[1] + 16LL);
        v22 = v20 > 0xFFFFFFFF ? 0x80070216 : 0;
        ElValidateHrLite(v22, v17, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0x6EAu);
        if ( v20 <= 0xFFFFFFFF )
          v26 = v20 > 0xFFFFFFFF ? 0x80070216 : 0;
        else
          v26 = ElValidateHr(v22, v23, v24, v25);
        if ( v26 >= 0 )
        {
          WSAIoctl(v4, 0xC8000014, *(LPVOID *)(*(_QWORD *)&cbBytesReturned[1] + 32LL), v21, 0, 0, cbBytesReturned, 0, 0);
          if ( WSAGetLastError() == 10014 )
          {
            v29 = operator new[](cbBytesReturned[0], (const struct std::nothrow_t *)&std::nothrow);
            if ( v29 )
            {
              if ( WSAIoctl(
                     v4,
                     0xC8000014,
                     *(LPVOID *)(*(_QWORD *)&cbBytesReturned[1] + 32LL),
                     v21,
                     v29,
                     cbBytesReturned[0],
                     cbBytesReturned,
                     0,
                     0) == -1 )
              {
                v30 = WSAGetLastError();
                Error = ElValidateWin32(v30, v31, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0x719u);
              }
              else if ( v37 == 4 )
              {
                *((_DWORD *)a2 + 4) = 4;
                *(_DWORD *)a2 = v29[1];
              }
              else
              {
                *((_DWORD *)a2 + 4) = 16;
                memmove_0(a2, v29 + 2, 0x10u);
              }
              operator delete(v29);
            }
            else
            {
              Error = 8;
            }
          }
          else
          {
            v27 = WSAGetLastError();
            Error = ElValidateWin32(v27, v28, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\netaddr.cpp", 0x6FCu);
          }
        }
        else if ( v20 > 0xFFFFFFFF && (v20 > 0xFFFFFFFF ? 0x70000 : 0) == 0x70000 )
        {
          Error = (unsigned __int16)v22;
        }
        else
        {
          Error = v20 > 0xFFFFFFFF ? 0x80070216 : 0;
        }
      }
    }
  }
  if ( v35 )
    operator delete(v35);
  if ( v4 != -1 )
    closesocket(v4);
  if ( *(_QWORD *)&cbBytesReturned[1] )
    FreeAddrInfoW(*(PADDRINFOW *)&cbBytesReturned[1]);
  return Error;
}

```

## disassembly

```asm
0x180022f20  mov     [rsp-8+arg_10], rbx
0x180022f25  mov     [rsp-8+arg_18], rdi
0x180022f2a  push    rbp
0x180022f2b  push    r12
0x180022f2d  push    r13
0x180022f2f  push    r14
0x180022f31  push    r15
0x180022f33  lea     rbp, [rsp-37h]
0x180022f38  sub     rsp, 100h
0x180022f3f  mov     rax, cs:__security_cookie
0x180022f46  xor     rax, rsp
0x180022f49  mov     [rbp+57h+var_30], rax
0x180022f4d  mov     rbx, rcx
0x180022f50  mov     r13, rdx
0x180022f53  xor     ecx, ecx
0x180022f55  xor     r14d, r14d
0x180022f58  mov     [rbp+57h+var_C0], rcx
0x180022f5c  xor     edx, edx; Val
0x180022f5e  lea     rcx, [rbp+57h+pHints]; void *
0x180022f62  lea     r8d, [r14+30h]; Size
0x180022f66  call    memset_0
0x180022f6b  mov     ecx, [rbx+10h]
0x180022f6e  lea     r8d, [r14+17h]
0x180022f72  and     [rbp+57h+ppResult], r14
0x180022f76  lea     edx, [r14+2]
0x180022f7a  and     [rbp+57h+cbBytesReturned], r14d
0x180022f7e  mov     eax, r8d
0x180022f81  movups  xmm0, xmmword ptr [rbx]
0x180022f84  cmp     ecx, 4
0x180022f87  mov     [rbp+57h+var_B4], ecx
0x180022f8a  mov     [rbp+57h+var_A0], ecx
0x180022f8d  cmovz   eax, edx
0x180022f90  movaps  [rbp+57h+Src], xmm0
0x180022f94  mov     [rbp+57h+var_B8], eax
0x180022f97  xor     edi, edi
0x180022f99  mov     eax, ecx
0x180022f9b  xor     ecx, ecx
0x180022f9d  and     [rbp+57h+dwAddressStringLength], ecx
0x180022fa0  mov     qword ptr [rbp+57h+saAddress.sa_family], rcx
0x180022fa4  mov     qword ptr [rbp+57h+saAddress.sa_data+6], rcx
0x180022fa8  mov     [rbp+57h+var_50], rcx
0x180022fac  mov     [rbp+57h+var_48], rcx
0x180022fb0  mov     [rbp+57h+var_40], rcx
0x180022fb4  mov     [rbp+57h+var_38], ecx
0x180022fb7  cmp     eax, 4
0x180022fba  jnz     short loc_180022FD0
0x180022fbc  mov     eax, dword ptr [rbp+57h+Src]
0x180022fbf  lea     r15, [rbp+57h+saAddress]
0x180022fc3  mov     dword ptr [rbp+57h+saAddress.sa_data+2], eax
0x180022fc6  lea     r12d, [r14+10h]
0x180022fca  mov     [rbp+57h+saAddress.sa_family], dx
0x180022fce  jmp     short loc_180022FF8
0x180022fd0  cmp     eax, 10h
0x180022fd3  jnz     loc_180023093
0x180022fd9  mov     word ptr [rbp+57h+var_50], r8w
0x180022fde  lea     rdx, [rbp+57h+Src]; Src
0x180022fe2  mov     r8d, eax; Size
0x180022fe5  lea     rcx, [rbp+57h+var_48]; void *
0x180022fe9  call    memmove_0
0x180022fee  lea     r15, [rbp+57h+var_50]
0x180022ff2  mov     r12d, 1Ch
0x180022ff8  lea     rax, [rbp+57h+dwAddressStringLength]
0x180022ffc  xor     r9d, r9d; lpszAddressString
0x180022fff  xor     r8d, r8d; lpProtocolInfo
0x180023002  mov     [rsp+120h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x180023007  mov     edx, r12d; dwAddressLength
0x18002300a  mov     rcx, r15; lpsaAddress
0x18002300d  call    cs:__imp_WSAAddressToStringW
0x180023013  mov     eax, [rbp+57h+dwAddressStringLength]
0x180023016  test    eax, eax
0x180023018  jnz     short loc_180023031
0x18002301a  call    cs:__imp_WSAGetLastError
0x180023020  mov     ebx, eax
0x180023022  cmp     eax, 2726h
0x180023027  jnz     short loc_180023098
0x180023029  mov     eax, 401h
0x18002302e  mov     [rbp+57h+dwAddressStringLength], eax
0x180023031  mov     ecx, eax
0x180023033  mov     eax, 2
0x180023038  mul     rcx
0x18002303b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180023042  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023049  cmovo   rax, rcx
0x18002304d  mov     rcx, rax; unsigned __int64
0x180023050  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023055  mov     rdi, rax
0x180023058  test    rax, rax
0x18002305b  jnz     short loc_180023062
0x18002305d  lea     ebx, [rax+8]
0x180023060  jmp     short loc_1800230A9
0x180023062  lea     rax, [rbp+57h+dwAddressStringLength]
0x180023066  mov     r9, rdi; lpszAddressString
0x180023069  xor     r8d, r8d; lpProtocolInfo
0x18002306c  mov     [rsp+120h+lpdwAddressStringLength], rax; lpdwAddressStringLength
0x180023071  mov     edx, r12d; dwAddressLength
0x180023074  mov     rcx, r15; lpsaAddress
0x180023077  call    cs:__imp_WSAAddressToStringW
0x18002307d  test    eax, eax
0x18002307f  jz      short loc_18002308B
0x180023081  call    cs:__imp_WSAGetLastError
0x180023087  mov     ebx, eax
0x180023089  jmp     short loc_180023098
0x18002308b  mov     [rbp+57h+var_C0], rdi
0x18002308f  xor     ebx, ebx
0x180023091  jmp     short loc_1800230AC
0x180023093  mov     ebx, 57h ; 'W'
0x180023098  test    ebx, ebx
0x18002309a  jz      short loc_1800230A9
0x18002309c  test    rdi, rdi
0x18002309f  jz      short loc_1800230A9
0x1800230a1  mov     rcx, rdi; void *
0x1800230a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800230a9  mov     rdi, r14
0x1800230ac  lea     r15, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800230b3  mov     r9d, 6CFh; unsigned int
0x1800230b9  mov     r8, r15; char *
0x1800230bc  mov     ecx, ebx; unsigned int
0x1800230be  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800230c3  test    eax, eax
0x1800230c5  jnz     loc_1800232E9
0x1800230cb  lea     r9, [rbp+57h+ppResult]; ppResult
0x1800230cf  mov     [rbp+57h+pHints.ai_socktype], 2
0x1800230d6  lea     r8, [rbp+57h+pHints]; pHints
0x1800230da  mov     [rbp+57h+pHints.ai_protocol], 11h
0x1800230e1  xor     edx, edx; pServiceName
0x1800230e3  mov     [rbp+57h+pHints.ai_flags], 4
0x1800230ea  mov     rcx, rdi; pNodeName
0x1800230ed  call    cs:__imp_GetAddrInfoW
0x1800230f3  mov     r9d, 6D9h; unsigned int
0x1800230f9  mov     r8, r15; char *
0x1800230fc  mov     ecx, eax; unsigned int
0x1800230fe  mov     ebx, eax
0x180023100  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180023105  test    eax, eax
0x180023107  jnz     loc_1800232E9
0x18002310d  and     [rsp+120h+cbOutBuffer], r14d
0x180023112  lea     edx, [rax+2]; type
0x180023115  mov     ecx, [rbp+57h+var_B8]; af
0x180023118  xor     r9d, r9d; lpProtocolInfo
0x18002311b  and     dword ptr [rsp+120h+lpdwAddressStringLength], r14d
0x180023120  xor     r8d, r8d; protocol
0x180023123  call    cs:__imp_WSASocketW
0x180023129  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002312d  mov     r14, rax
0x180023130  cmp     rax, rdi
0x180023133  jnz     short loc_180023152
0x180023135  call    cs:__imp_WSAGetLastError
0x18002313b  mov     r9d, 6E2h; unsigned int
0x180023141  mov     r8, r15; char *
0x180023144  mov     ecx, eax; unsigned int
0x180023146  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18002314b  mov     ebx, eax
0x18002314d  jmp     loc_1800232ED
0x180023152  mov     rax, [rbp+57h+ppResult]
0x180023156  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x18002315d  mov     r9d, 6EAh; unsigned int
0x180023163  mov     r15, [rax+10h]
0x180023167  mov     eax, 0FFFFFFFFh
0x18002316c  cmp     r15, rax
0x18002316f  mov     r12d, eax
0x180023172  cmovbe  r12d, r15d
0x180023176  cmp     rax, r15
0x180023179  sbb     edi, edi
0x18002317b  and     edi, 80070216h
0x180023181  mov     ecx, edi; int
0x180023183  call    ?ElValidateHrLite@@YAJJPEBD0K@Z; ElValidateHrLite(long,char const *,char const *,ulong)
0x180023188  mov     ecx, 0FFFFFFFFh
0x18002318d  cmp     r15, rcx
0x180023190  jbe     short loc_1800231A0
0x180023192  mov     ecx, edi; int
0x180023194  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180023199  mov     ecx, 0FFFFFFFFh
0x18002319e  jmp     short loc_1800231A2
0x1800231a0  mov     eax, edi
0x1800231a2  test    eax, eax
0x1800231a4  jns     short loc_1800231C8
0x1800231a6  cmp     r15, rcx
0x1800231a9  jbe     short loc_1800231C1
0x1800231ab  mov     eax, edi
0x1800231ad  and     eax, 1FFF0000h
0x1800231b2  cmp     eax, 70000h
0x1800231b7  jnz     short loc_1800231C1
0x1800231b9  movzx   ebx, di
0x1800231bc  jmp     loc_1800232E9
0x1800231c1  mov     ebx, edi
0x1800231c3  jmp     loc_1800232E9
0x1800231c8  and     [rsp+120h+var_E0], 0
0x1800231ce  lea     rax, [rbp+57h+cbBytesReturned]
0x1800231d2  and     [rsp+120h+var_E8], 0
0x1800231d8  mov     r15d, 0C8000014h
0x1800231de  mov     r8, [rbp+57h+ppResult]
0x1800231e2  mov     r9d, r12d; cbInBuffer
0x1800231e5  mov     [rsp+120h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800231ea  mov     edx, r15d; dwIoControlCode
0x1800231ed  and     [rsp+120h+cbOutBuffer], 0
0x1800231f2  mov     rcx, r14; s
0x1800231f5  and     [rsp+120h+lpdwAddressStringLength], 0
0x1800231fb  mov     r8, [r8+20h]; lpvInBuffer
0x1800231ff  call    cs:__imp_WSAIoctl
0x180023205  call    cs:__imp_WSAGetLastError
0x18002320b  cmp     eax, 271Eh
0x180023210  jz      short loc_180023233
0x180023212  call    cs:__imp_WSAGetLastError
0x180023218  mov     r9d, 6FCh; unsigned int
0x18002321e  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180023225  mov     ecx, eax; unsigned int
0x180023227  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18002322c  mov     ebx, eax
0x18002322e  jmp     loc_1800232E9
0x180023233  mov     ecx, [rbp+57h+cbBytesReturned]; unsigned __int64
0x180023236  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002323d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023242  mov     rdi, rax
0x180023245  test    rax, rax
0x180023248  jnz     short loc_180023252
0x18002324a  lea     ebx, [rax+8]
0x18002324d  jmp     loc_1800232E9
0x180023252  and     [rsp+120h+var_E0], 0
0x180023258  lea     rax, [rbp+57h+cbBytesReturned]
0x18002325c  and     [rsp+120h+var_E8], 0
0x180023262  mov     r9d, r12d; cbInBuffer
0x180023265  mov     r8, [rbp+57h+ppResult]
0x180023269  mov     edx, r15d; dwIoControlCode
0x18002326c  mov     [rsp+120h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180023271  mov     rcx, r14; s
0x180023274  mov     eax, [rbp+57h+cbBytesReturned]
0x180023277  mov     [rsp+120h+cbOutBuffer], eax; cbOutBuffer
0x18002327b  mov     r8, [r8+20h]; lpvInBuffer
0x18002327f  mov     [rsp+120h+lpdwAddressStringLength], rdi; lpvOutBuffer
0x180023284  call    cs:__imp_WSAIoctl
0x18002328a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002328e  cmp     eax, ecx
0x180023290  jnz     short loc_1800232B0
0x180023292  call    cs:__imp_WSAGetLastError
0x180023298  mov     r9d, 719h; unsigned int
0x18002329e  lea     r8, aOnecoreBaseEco_6; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x1800232a5  mov     ecx, eax; unsigned int
0x1800232a7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800232ac  mov     ebx, eax
0x1800232ae  jmp     short loc_1800232E1
0x1800232b0  cmp     [rbp+57h+var_B4], 4
0x1800232b4  jnz     short loc_1800232C7
0x1800232b6  mov     dword ptr [r13+10h], 4
0x1800232be  mov     eax, [rdi+4]
0x1800232c1  mov     [r13+0], eax
0x1800232c5  jmp     short loc_1800232E1
0x1800232c7  lea     rdx, [rdi+8]; Src
0x1800232cb  mov     dword ptr [r13+10h], 10h
0x1800232d3  mov     r8d, 10h; Size
0x1800232d9  mov     rcx, r13; void *
0x1800232dc  call    memmove_0
0x1800232e1  mov     rcx, rdi; void *
0x1800232e4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800232e9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800232ed  mov     rcx, [rbp+57h+var_C0]; void *
0x1800232f1  test    rcx, rcx
0x1800232f4  jz      short loc_1800232FB
0x1800232f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800232fb  cmp     r14, rdi
0x1800232fe  jz      short loc_180023309
0x180023300  mov     rcx, r14; s
0x180023303  call    cs:__imp_closesocket
0x180023309  mov     rcx, [rbp+57h+ppResult]; pAddrInfo
0x18002330d  test    rcx, rcx
0x180023310  jz      short loc_180023318
0x180023312  call    cs:__imp_FreeAddrInfoW
0x180023318  mov     eax, ebx
0x18002331a  mov     rcx, [rbp+57h+var_30]
0x18002331e  xor     rcx, rsp; StackCookie
0x180023321  call    __security_check_cookie
0x180023326  lea     r11, [rsp+120h+var_20]
0x18002332e  mov     rbx, [r11+40h]
0x180023332  mov     rdi, [r11+48h]
0x180023336  mov     rsp, r11
0x180023339  pop     r15
0x18002333b  pop     r14
0x18002333d  pop     r13
0x18002333f  pop     r12
0x180023341  pop     rbp
0x180023342  retn
```
