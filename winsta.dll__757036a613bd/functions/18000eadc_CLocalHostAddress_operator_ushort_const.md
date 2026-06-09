# CLocalHostAddress::operator==(ushort const *)

- ea: `0x18000eadc`
- end: `0x18000ece0`
- name: `??8CLocalHostAddress@@QEAAHPEBG@Z`
- size: `516`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005db0`

## callees

- `0x18000eadc`
- `0x18000ece8`
- `0x18000eee4`
- `0x18002ee14`
- `0x18002f99c`
- `0x18002fb28`
- `0x18002fe06`
- `0x18002fe40`

## import_xrefs

- `WS2_32!GetAddrInfoW` at `0x18000ebcd`
- `WS2_32!GetAddrInfoW` at `0x18000ebcd`
- `WS2_32!FreeAddrInfoW` at `0x18000ebff`
- `WS2_32!FreeAddrInfoW` at `0x18000ebff`
- `WS2_32!__imp_WSAStartup` at `0x18000eb3d`
- `WS2_32!__imp_WSAStartup` at `0x18000eb3d`
- `WS2_32!__imp_WSACleanup` at `0x18000eb8e`
- `WS2_32!__imp_WSACleanup` at `0x18000eb8e`

## pseudocode

```c
__int64 __fastcall CLocalHostAddress::operator==(__int64 a1, const WCHAR *a2)
{
  unsigned int v3; // edi
  CLocalHostAddress *v4; // rcx
  int AddrInfoW; // esi
  int v6; // r14d
  CLocalHostAddress *v8; // rcx
  PADDRINFOW v9; // rbx
  unsigned int IsLocalAdapterAddress; // eax
  _BYTE *v11; // rax
  unsigned int v12; // eax
  int v13; // edx
  int v14; // r8d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v16; // r8
  __int64 v17; // rdx
  PADDRINFOW ppResult; // [rsp+30h] [rbp-D0h] BYREF
  ADDRINFOW pHints; // [rsp+38h] [rbp-C8h] BYREF
  WSAData WSAData; // [rsp+70h] [rbp-90h] BYREF

  v3 = 0;
  ppResult = 0;
  memset(&pHints, 0, sizeof(pHints));
  memset_0(&WSAData, 0, sizeof(WSAData));
  AddrInfoW = WSAStartup(0x202u, &WSAData);
  if ( AddrInfoW )
  {
    v6 = 0;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_3;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 10;
LABEL_28:
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, v16, CurrentThreadActivityIdPrefix, AddrInfoW);
    goto LABEL_3;
  }
  v6 = 1;
  if ( CLocalHostAddress::Initialize(v4) || !AdapterAddresses && !qword_1800575D0 )
    goto LABEL_3;
  *(_QWORD *)&pHints.ai_flags = 0;
  pHints.ai_protocol = 6;
  pHints.ai_socktype = 1;
  memset(&pHints.ai_addrlen, 0, 32);
  AddrInfoW = GetAddrInfoW(a2, 0, &pHints, &ppResult);
  if ( !AddrInfoW )
  {
    v9 = ppResult;
    while ( v9 && !v3 )
    {
      IsLocalAdapterAddress = CLocalHostAddress::IsLocalAdapterAddress(v8, v9);
      v9 = v9->ai_next;
      v3 = IsLocalAdapterAddress;
    }
    goto LABEL_3;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, v12, (__int64)a2, AddrInfoW);
      v11 = WPP_GLOBAL_Control;
    }
    if ( v11 != (_BYTE *)&WPP_GLOBAL_Control && (v11[28] & 1) != 0 && v11[25] >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 12;
      goto LABEL_28;
    }
  }
LABEL_3:
  if ( ppResult )
    FreeAddrInfoW(ppResult);
  if ( v6 )
    WSACleanup();
  return v3;
}

```

## disassembly

```asm
0x18000eadc  push    rbp
0x18000eade  push    rbx
0x18000eadf  push    rsi
0x18000eae0  push    rdi
0x18000eae1  push    r14
0x18000eae3  push    r15
0x18000eae5  lea     rbp, [rsp-128h]
0x18000eaed  sub     rsp, 228h
0x18000eaf4  mov     rax, cs:__security_cookie
0x18000eafb  xor     rax, rsp
0x18000eafe  mov     [rbp+150h+var_40], rax
0x18000eb05  xorps   xmm0, xmm0
0x18000eb08  lea     rcx, [rsp+250h+WSAData]; void *
0x18000eb0d  mov     r15, rdx
0x18000eb10  xor     edi, edi
0x18000eb12  xor     edx, edx; Val
0x18000eb14  mov     [rsp+250h+ppResult], rdi
0x18000eb19  mov     r8d, 198h; Size
0x18000eb1f  movups  xmmword ptr [rsp+250h+pHints.ai_flags], xmm0
0x18000eb24  movups  xmmword ptr [rsp+250h+pHints.ai_addrlen], xmm0
0x18000eb29  movups  xmmword ptr [rsp+250h+pHints.ai_addr], xmm0
0x18000eb2e  call    memset_0
0x18000eb33  mov     ecx, 202h; wVersionRequested
0x18000eb38  lea     rdx, [rsp+250h+WSAData]; lpWSAData
0x18000eb3d  call    cs:__imp_WSAStartup
0x18000eb43  mov     esi, eax
0x18000eb45  test    eax, eax
0x18000eb47  jnz     loc_18000EC8D
0x18000eb4d  lea     r14d, [rdi+1]
0x18000eb51  call    ?Initialize@CLocalHostAddress@@AEAAKXZ; CLocalHostAddress::Initialize(void)
0x18000eb56  test    eax, eax
0x18000eb58  jz      short loc_18000EB96
0x18000eb5a  mov     rcx, [rsp+250h+ppResult]; pAddrInfo
0x18000eb5f  test    rcx, rcx
0x18000eb62  jnz     loc_18000EBFF
0x18000eb68  test    r14d, r14d
0x18000eb6b  jnz     short loc_18000EB8E
0x18000eb6d  mov     eax, edi
0x18000eb6f  mov     rcx, [rbp+150h+var_40]
0x18000eb76  xor     rcx, rsp; StackCookie
0x18000eb79  call    __security_check_cookie
0x18000eb7e  add     rsp, 228h
0x18000eb85  pop     r15
0x18000eb87  pop     r14
0x18000eb89  pop     rdi
0x18000eb8a  pop     rsi
0x18000eb8b  pop     rbx
0x18000eb8c  pop     rbp
0x18000eb8d  retn
0x18000eb8e  call    cs:__imp_WSACleanup
0x18000eb94  jmp     short loc_18000EB6D
0x18000eb96  cmp     cs:AdapterAddresses, rdi
0x18000eb9d  jz      short loc_18000EC0A
0x18000eb9f  xorps   xmm0, xmm0
0x18000eba2  lea     r9, [rsp+250h+ppResult]; ppResult
0x18000eba7  movups  xmmword ptr [rsp+250h+pHints.ai_flags], xmm0
0x18000ebac  lea     r8, [rsp+250h+pHints]; pHints
0x18000ebb1  mov     [rsp+250h+pHints.ai_protocol], 6
0x18000ebb9  xor     edx, edx; pServiceName
0x18000ebbb  mov     [rsp+250h+pHints.ai_socktype], r14d
0x18000ebc0  mov     rcx, r15; pNodeName
0x18000ebc3  movups  xmmword ptr [rsp+250h+pHints.ai_addrlen], xmm0
0x18000ebc8  movups  xmmword ptr [rsp+250h+pHints.ai_addr], xmm0
0x18000ebcd  call    cs:__imp_GetAddrInfoW
0x18000ebd3  mov     esi, eax
0x18000ebd5  test    eax, eax
0x18000ebd7  jnz     short loc_18000EC19
0x18000ebd9  mov     rbx, [rsp+250h+ppResult]
0x18000ebde  test    rbx, rbx
0x18000ebe1  jz      loc_18000EB5A
0x18000ebe7  test    edi, edi
0x18000ebe9  jnz     loc_18000EB5A
0x18000ebef  mov     rdx, rbx; struct addrinfoW *
0x18000ebf2  call    ?IsLocalAdapterAddress@CLocalHostAddress@@AEBAHPEBUaddrinfoW@@@Z; CLocalHostAddress::IsLocalAdapterAddress(addrinfoW const *)
0x18000ebf7  mov     rbx, [rbx+28h]
0x18000ebfb  mov     edi, eax
0x18000ebfd  jmp     short loc_18000EBDE
0x18000ebff  call    cs:__imp_FreeAddrInfoW
0x18000ec05  jmp     loc_18000EB68
0x18000ec0a  cmp     cs:qword_1800575D0, rdi
0x18000ec11  jz      loc_18000EB5A
0x18000ec17  jmp     short loc_18000EB9F
0x18000ec19  mov     rax, cs:WPP_GLOBAL_Control
0x18000ec20  lea     rbx, WPP_GLOBAL_Control
0x18000ec27  cmp     rax, rbx
0x18000ec2a  jz      loc_18000EB5A
0x18000ec30  test    [rax+1Ch], r14b
0x18000ec34  jz      short loc_18000EC64
0x18000ec36  cmp     byte ptr [rax+19h], 3
0x18000ec3a  jb      short loc_18000EC64
0x18000ec3c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000ec41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec48  mov     r9d, eax
0x18000ec4b  mov     [rsp+250h+var_228], esi
0x18000ec4f  mov     [rsp+250h+var_230], r15
0x18000ec54  mov     rcx, [rcx+10h]
0x18000ec58  call    WPP_SF_DSD
0x18000ec5d  mov     rax, cs:WPP_GLOBAL_Control
0x18000ec64  cmp     rax, rbx
0x18000ec67  jz      loc_18000EB5A
0x18000ec6d  test    [rax+1Ch], r14b
0x18000ec71  jz      loc_18000EB5A
0x18000ec77  cmp     byte ptr [rax+19h], 2
0x18000ec7b  jb      loc_18000EB5A
0x18000ec81  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000ec86  mov     edx, 0Ch
0x18000ec8b  jmp     short loc_18000ECC4
0x18000ec8d  xor     r14d, r14d
0x18000ec90  mov     rax, cs:WPP_GLOBAL_Control
0x18000ec97  lea     rbx, WPP_GLOBAL_Control
0x18000ec9e  cmp     rax, rbx
0x18000eca1  jz      loc_18000EB5A
0x18000eca7  test    byte ptr [rax+1Ch], 1
0x18000ecab  jz      loc_18000EB5A
0x18000ecb1  cmp     byte ptr [rax+19h], 2
0x18000ecb5  jb      loc_18000EB5A
0x18000ecbb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000ecc0  lea     edx, [r14+0Ah]
0x18000ecc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eccb  mov     r9d, eax
0x18000ecce  mov     dword ptr [rsp+250h+var_230], esi
0x18000ecd2  mov     rcx, [rcx+10h]
0x18000ecd6  call    WPP_SF_DD
0x18000ecdb  jmp     loc_18000EB5A
```
