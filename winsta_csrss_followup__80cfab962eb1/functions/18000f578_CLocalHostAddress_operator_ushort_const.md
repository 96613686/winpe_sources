# CLocalHostAddress::operator==(ushort const *)

- ea: `0x18000f578`
- end: `0x18000f798`
- name: `??8CLocalHostAddress@@QEAAHPEBG@Z`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004330`

## callees

- `0x18000f578`
- `0x18000f7a0`
- `0x18000f9c4`
- `0x180031b10`
- `0x18003274c`
- `0x1800328e8`
- `0x180032be6`
- `0x180032c20`

## import_xrefs

- `WS2_32!GetAddrInfoW` at `0x18000f676`
- `WS2_32!GetAddrInfoW` at `0x18000f676`
- `WS2_32!FreeAddrInfoW` at `0x18000f6ae`
- `WS2_32!FreeAddrInfoW` at `0x18000f6ae`
- `WS2_32!__imp_WSAStartup` at `0x18000f5d9`
- `WS2_32!__imp_WSAStartup` at `0x18000f5d9`
- `WS2_32!__imp_WSACleanup` at `0x18000f631`
- `WS2_32!__imp_WSACleanup` at `0x18000f631`

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
  if ( CLocalHostAddress::Initialize(v4) || !AdapterAddresses && !qword_18005A5D0 )
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
0x18000f578  push    rbp
0x18000f57a  push    rbx
0x18000f57b  push    rsi
0x18000f57c  push    rdi
0x18000f57d  push    r14
0x18000f57f  push    r15
0x18000f581  lea     rbp, [rsp-128h]
0x18000f589  sub     rsp, 228h
0x18000f590  mov     rax, cs:__security_cookie
0x18000f597  xor     rax, rsp
0x18000f59a  mov     [rbp+150h+var_40], rax
0x18000f5a1  xorps   xmm0, xmm0
0x18000f5a4  lea     rcx, [rsp+250h+WSAData]; void *
0x18000f5a9  mov     r15, rdx
0x18000f5ac  xor     edi, edi
0x18000f5ae  xor     edx, edx; Val
0x18000f5b0  mov     [rsp+250h+ppResult], rdi
0x18000f5b5  mov     r8d, 198h; Size
0x18000f5bb  movups  xmmword ptr [rsp+250h+pHints.ai_flags], xmm0
0x18000f5c0  movups  xmmword ptr [rsp+250h+pHints.ai_addrlen], xmm0
0x18000f5c5  movups  xmmword ptr [rsp+250h+pHints.ai_addr], xmm0
0x18000f5ca  call    memset_0
0x18000f5cf  mov     ecx, 202h; wVersionRequested
0x18000f5d4  lea     rdx, [rsp+250h+WSAData]; lpWSAData
0x18000f5d9  call    cs:__imp_WSAStartup
0x18000f5e0  nop     dword ptr [rax+rax+00h]
0x18000f5e5  mov     esi, eax
0x18000f5e7  test    eax, eax
0x18000f5e9  jnz     loc_18000F745
0x18000f5ef  lea     r14d, [rdi+1]
0x18000f5f3  call    ?Initialize@CLocalHostAddress@@AEAAKXZ; CLocalHostAddress::Initialize(void)
0x18000f5f8  test    eax, eax
0x18000f5fa  jz      short loc_18000F63F
0x18000f5fc  mov     rcx, [rsp+250h+ppResult]; pAddrInfo
0x18000f601  test    rcx, rcx
0x18000f604  jnz     loc_18000F6AE
0x18000f60a  test    r14d, r14d
0x18000f60d  jnz     short loc_18000F631
0x18000f60f  mov     eax, edi
0x18000f611  mov     rcx, [rbp+150h+var_40]
0x18000f618  xor     rcx, rsp; StackCookie
0x18000f61b  call    __security_check_cookie
0x18000f620  add     rsp, 228h
0x18000f627  pop     r15
0x18000f629  pop     r14
0x18000f62b  pop     rdi
0x18000f62c  pop     rsi
0x18000f62d  pop     rbx
0x18000f62e  pop     rbp
0x18000f62f  retn
0x18000f631  call    cs:__imp_WSACleanup
0x18000f638  nop     dword ptr [rax+rax+00h]
0x18000f63d  jmp     short loc_18000F60F
0x18000f63f  cmp     cs:AdapterAddresses, rdi
0x18000f646  jz      short loc_18000F6BF
0x18000f648  xorps   xmm0, xmm0
0x18000f64b  lea     r9, [rsp+250h+ppResult]; ppResult
0x18000f650  movups  xmmword ptr [rsp+250h+pHints.ai_flags], xmm0
0x18000f655  lea     r8, [rsp+250h+pHints]; pHints
0x18000f65a  mov     [rsp+250h+pHints.ai_protocol], 6
0x18000f662  xor     edx, edx; pServiceName
0x18000f664  mov     [rsp+250h+pHints.ai_socktype], r14d
0x18000f669  mov     rcx, r15; pNodeName
0x18000f66c  movups  xmmword ptr [rsp+250h+pHints.ai_addrlen], xmm0
0x18000f671  movups  xmmword ptr [rsp+250h+pHints.ai_addr], xmm0
0x18000f676  call    cs:__imp_GetAddrInfoW
0x18000f67d  nop     dword ptr [rax+rax+00h]
0x18000f682  mov     esi, eax
0x18000f684  test    eax, eax
0x18000f686  jnz     short loc_18000F6D1
0x18000f688  mov     rbx, [rsp+250h+ppResult]
0x18000f68d  test    rbx, rbx
0x18000f690  jz      loc_18000F5FC
0x18000f696  test    edi, edi
0x18000f698  jnz     loc_18000F5FC
0x18000f69e  mov     rdx, rbx; struct addrinfoW *
0x18000f6a1  call    ?IsLocalAdapterAddress@CLocalHostAddress@@AEBAHPEBUaddrinfoW@@@Z; CLocalHostAddress::IsLocalAdapterAddress(addrinfoW const *)
0x18000f6a6  mov     rbx, [rbx+28h]
0x18000f6aa  mov     edi, eax
0x18000f6ac  jmp     short loc_18000F68D
0x18000f6ae  call    cs:__imp_FreeAddrInfoW
0x18000f6b5  nop     dword ptr [rax+rax+00h]
0x18000f6ba  jmp     loc_18000F60A
0x18000f6bf  cmp     cs:qword_18005A5D0, rdi
0x18000f6c6  jz      loc_18000F5FC
0x18000f6cc  jmp     loc_18000F648
0x18000f6d1  mov     rax, cs:WPP_GLOBAL_Control
0x18000f6d8  lea     rbx, WPP_GLOBAL_Control
0x18000f6df  cmp     rax, rbx
0x18000f6e2  jz      loc_18000F5FC
0x18000f6e8  test    [rax+1Ch], r14b
0x18000f6ec  jz      short loc_18000F71C
0x18000f6ee  cmp     byte ptr [rax+19h], 3
0x18000f6f2  jb      short loc_18000F71C
0x18000f6f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f6f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f700  mov     r9d, eax
0x18000f703  mov     [rsp+250h+var_228], esi
0x18000f707  mov     [rsp+250h+var_230], r15
0x18000f70c  mov     rcx, [rcx+10h]
0x18000f710  call    WPP_SF_DSD
0x18000f715  mov     rax, cs:WPP_GLOBAL_Control
0x18000f71c  cmp     rax, rbx
0x18000f71f  jz      loc_18000F5FC
0x18000f725  test    [rax+1Ch], r14b
0x18000f729  jz      loc_18000F5FC
0x18000f72f  cmp     byte ptr [rax+19h], 2
0x18000f733  jb      loc_18000F5FC
0x18000f739  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f73e  mov     edx, 0Ch
0x18000f743  jmp     short loc_18000F77C
0x18000f745  xor     r14d, r14d
0x18000f748  mov     rax, cs:WPP_GLOBAL_Control
0x18000f74f  lea     rbx, WPP_GLOBAL_Control
0x18000f756  cmp     rax, rbx
0x18000f759  jz      loc_18000F5FC
0x18000f75f  test    byte ptr [rax+1Ch], 1
0x18000f763  jz      loc_18000F5FC
0x18000f769  cmp     byte ptr [rax+19h], 2
0x18000f76d  jb      loc_18000F5FC
0x18000f773  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000f778  lea     edx, [r14+0Ah]
0x18000f77c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f783  mov     r9d, eax
0x18000f786  mov     dword ptr [rsp+250h+var_230], esi
0x18000f78a  mov     rcx, [rcx+10h]
0x18000f78e  call    WPP_SF_DD
0x18000f793  jmp     loc_18000F5FC
```
