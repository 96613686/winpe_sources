# CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Bind(tagWDS_ENDPOINT *)

- ea: `0x1800186f0`
- end: `0x18001897b`
- name: `?Bind@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKPEAUtagWDS_ENDPOINT@@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180018b08`

## callees

- `0x180003944`
- `0x1800183b0`
- `0x1800184d0`
- `0x1800186f0`
- `0x180018984`
- `0x180019498`
- `0x18001c12a`
- `0x18001c150`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180018935`
- `KERNEL32!LeaveCriticalSection` at `0x180018935`
- `KERNEL32!EnterCriticalSection` at `0x180018736`
- `KERNEL32!EnterCriticalSection` at `0x180018736`
- `WS2_32!__imp_bind` at `0x180018788`
- `WS2_32!__imp_bind` at `0x180018788`
- `WS2_32!__imp_WSAGetLastError` at `0x180018798`
- `WS2_32!__imp_WSAGetLastError` at `0x180018798`
- `WdsServerCommonLib!?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z` at `0x180018872`
- `WdsServerCommonLib!?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z` at `0x1800188cb`
- `WdsServerCommonLib!?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z` at `0x180018872`
- `WdsServerCommonLib!?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z` at `0x1800188cb`
- `WdsServerCommonLib!?Initialize@CCompPort@@QEAAKPEAXK@Z` at `0x18001889f`
- `WdsServerCommonLib!?Initialize@CCompPort@@QEAAKPEAXK@Z` at `0x18001889f`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::Bind(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rdx
  unsigned int Error; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rsi
  __int64 v16; // rdx
  int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rdx
  unsigned int i; // esi
  __int64 v23; // rdx
  int namelen[4]; // [rsp+30h] [rbp-C8h] BYREF
  struct sockaddr name; // [rsp+40h] [rbp-B8h] BYREF

  memset_0(&name, 0, 0x80u);
  namelen[0] = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v6 = (unsigned int)CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::EndpointToSockaddr(v5, v4, a2, &name, namelen);
  if ( (unsigned int)ElValidateWin32(v6, v7, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1500) )
    goto LABEL_23;
  if ( bind(*(_QWORD *)(a1 + 56), &name, namelen[0]) )
  {
    Error = WSAGetLastError();
    LODWORD(v6) = ElValidateWin32(Error, v10, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1510);
    goto LABEL_23;
  }
  if ( !*(_DWORD *)(a1 + 128) )
    goto LABEL_12;
  v11 = a1 + 152;
  if ( *(_DWORD *)(a1 + 256) )
  {
    v12 = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::AddMulticastSourceMembership(a1, v11, a1 + 260, a1 + 132);
    v14 = 1525;
  }
  else
  {
    v12 = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::AddMulticastMembership(a1, v11, a1 + 132);
    v14 = 1533;
  }
  LODWORD(v6) = v12;
  if ( (unsigned int)ElValidateWin32(v12, v13, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", v14) )
    goto LABEL_23;
  v15 = 0;
  if ( !*(_DWORD *)(a1 + 172) )
  {
LABEL_12:
    v17 = *(_DWORD *)(a1 + 88);
    if ( v17 )
    {
      if ( v17 != 1 )
      {
        if ( v17 != 2 )
        {
          LODWORD(v6) = 87;
          goto LABEL_23;
        }
LABEL_18:
        LODWORD(v6) = 0;
        if ( *(_DWORD *)(a1 + 88) != 2 )
        {
          for ( i = 0; i < *(_DWORD *)(a1 + 72); ++i )
          {
            LODWORD(v6) = CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostReadRequest(a1);
            if ( (unsigned int)ElValidateWin32((unsigned int)v6, v23, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1638) )
              break;
          }
        }
        ElValidateWin32((unsigned int)v6, v8, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1599);
        goto LABEL_23;
      }
      LODWORD(v6) = CCompPort::Initialize((CCompPort *)(a1 + 288), 0, *(_DWORD *)(a1 + 104));
      if ( (unsigned int)ElValidateWin32((unsigned int)v6, v21, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1582) )
        goto LABEL_23;
      v18 = CCompPort::Attach((CCompPort *)(a1 + 288), *(void **)(a1 + 56), (struct ICpRecvRequest *)a1);
      v20 = 1586;
    }
    else
    {
      v18 = CCompPort::Attach(*(CCompPort **)(a1 + 96), *(void **)(a1 + 56), (struct ICpRecvRequest *)a1);
      v20 = 1574;
    }
    LODWORD(v6) = v18;
    if ( (unsigned int)ElValidateWin32(v18, v19, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", v20) )
      goto LABEL_23;
    goto LABEL_18;
  }
  while ( 1 )
  {
    v6 = (unsigned int)CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::AddMulticastMembership(
                         a1,
                         a1 + 4 * (v15 + 4 * (v15 + 11)),
                         a1 + 132);
    if ( (unsigned int)ElValidateWin32(v6, v16, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1561) )
      break;
    v15 = (unsigned int)(v15 + 1);
    if ( (unsigned int)v15 >= *(_DWORD *)(a1 + 172) )
      goto LABEL_12;
  }
LABEL_23:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800186f0  mov     [rsp+arg_10], rbx
0x1800186f5  push    rbp
0x1800186f6  push    rsi
0x1800186f7  push    rdi
0x1800186f8  push    r12
0x1800186fa  push    r14
0x1800186fc  sub     rsp, 0D0h
0x180018703  mov     rax, cs:__security_cookie
0x18001870a  xor     rax, rsp
0x18001870d  mov     [rsp+0F8h+var_38], rax
0x180018715  mov     rbx, rdx
0x180018718  mov     rdi, rcx
0x18001871b  xor     edx, edx; Val
0x18001871d  lea     rcx, [rsp+0F8h+name]; void *
0x180018722  mov     r8d, 80h; Size
0x180018728  call    memset_0
0x18001872d  and     [rsp+0F8h+namelen], 0
0x180018732  lea     rcx, [rdi+8]; lpCriticalSection
0x180018736  call    cs:__imp_EnterCriticalSection
0x18001873d  nop     dword ptr [rax+rax+00h]
0x180018742  lea     rax, [rsp+0F8h+namelen]
0x180018747  mov     r8, rbx
0x18001874a  lea     r9, [rsp+0F8h+name]
0x18001874f  mov     [rsp+0F8h+var_D8], rax
0x180018754  call    ?EndpointToSockaddr@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKHPEAUtagWDS_ENDPOINT@@PEAUsockaddr_storage@@PEAH@Z; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::EndpointToSockaddr(int,tagWDS_ENDPOINT *,sockaddr_storage *,int *)
0x180018759  lea     r12, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x180018760  mov     r9d, 5DCh
0x180018766  mov     r8, r12
0x180018769  mov     ecx, eax
0x18001876b  mov     ebx, eax
0x18001876d  call    ElValidateWin32
0x180018772  test    eax, eax
0x180018774  jnz     loc_180018931
0x18001877a  mov     r8d, [rsp+0F8h+namelen]; namelen
0x18001877f  lea     rdx, [rsp+0F8h+name]; name
0x180018784  mov     rcx, [rdi+38h]; s
0x180018788  call    cs:__imp_bind
0x18001878f  nop     dword ptr [rax+rax+00h]
0x180018794  test    eax, eax
0x180018796  jz      short loc_1800187BB
0x180018798  call    cs:__imp_WSAGetLastError
0x18001879f  nop     dword ptr [rax+rax+00h]
0x1800187a4  mov     r9d, 5E6h
0x1800187aa  mov     r8, r12
0x1800187ad  mov     ecx, eax
0x1800187af  call    ElValidateWin32
0x1800187b4  mov     ebx, eax
0x1800187b6  jmp     loc_180018931
0x1800187bb  cmp     dword ptr [rdi+80h], 0
0x1800187c2  jz      loc_180018860
0x1800187c8  cmp     dword ptr [rdi+100h], 0
0x1800187cf  lea     rbp, [rdi+84h]
0x1800187d6  lea     rdx, [rdi+98h]
0x1800187dd  mov     rcx, rdi
0x1800187e0  jz      short loc_1800187F9
0x1800187e2  lea     r8, [rdi+104h]
0x1800187e9  mov     r9, rbp
0x1800187ec  call    ?AddMulticastSourceMembership@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKPEAUtagWDS_IP_ADDRESS6@@00@Z; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::AddMulticastSourceMembership(tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)
0x1800187f1  mov     r9d, 5F5h
0x1800187f7  jmp     short loc_180018807
0x1800187f9  mov     r8, rbp
0x1800187fc  call    ?AddMulticastMembership@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKPEAUtagWDS_IP_ADDRESS6@@0@Z; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::AddMulticastMembership(tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)
0x180018801  mov     r9d, 5FDh
0x180018807  mov     r8, r12
0x18001880a  mov     ecx, eax
0x18001880c  mov     ebx, eax
0x18001880e  call    ElValidateWin32
0x180018813  test    eax, eax
0x180018815  jnz     loc_180018931
0x18001881b  xor     esi, esi
0x18001881d  cmp     [rdi+0ACh], esi
0x180018823  jbe     short loc_180018860
0x180018825  lea     rcx, [rsi+0Bh]
0x180018829  mov     r8, rbp
0x18001882c  lea     rcx, [rsi+rcx*4]
0x180018830  lea     rdx, [rdi+rcx*4]
0x180018834  mov     rcx, rdi
0x180018837  call    ?AddMulticastMembership@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@QEAAKPEAUtagWDS_IP_ADDRESS6@@0@Z; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::AddMulticastMembership(tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)
0x18001883c  mov     r9d, 619h
0x180018842  mov     r8, r12
0x180018845  mov     ecx, eax
0x180018847  mov     ebx, eax
0x180018849  call    ElValidateWin32
0x18001884e  test    eax, eax
0x180018850  jnz     loc_180018931
0x180018856  inc     esi
0x180018858  cmp     esi, [rdi+0ACh]
0x18001885e  jb      short loc_180018825
0x180018860  mov     eax, [rdi+58h]
0x180018863  test    eax, eax
0x180018865  jnz     short loc_180018886
0x180018867  mov     rdx, [rdi+38h]
0x18001886b  mov     r8, rdi
0x18001886e  mov     rcx, [rdi+60h]
0x180018872  call    cs:__imp_?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z; CCompPort::Attach(void *,ICpRecvRequest *)
0x180018879  nop     dword ptr [rax+rax+00h]
0x18001887e  mov     r9d, 626h
0x180018884  jmp     short loc_1800188DD
0x180018886  cmp     eax, 1
0x180018889  jnz     loc_18001896B
0x18001888f  mov     r8d, [rdi+68h]
0x180018893  lea     rsi, [rdi+120h]
0x18001889a  mov     rcx, rsi
0x18001889d  xor     edx, edx
0x18001889f  call    cs:__imp_?Initialize@CCompPort@@QEAAKPEAXK@Z; CCompPort::Initialize(void *,ulong)
0x1800188a6  nop     dword ptr [rax+rax+00h]
0x1800188ab  mov     r9d, 62Eh
0x1800188b1  mov     r8, r12
0x1800188b4  mov     ecx, eax
0x1800188b6  mov     ebx, eax
0x1800188b8  call    ElValidateWin32
0x1800188bd  test    eax, eax
0x1800188bf  jnz     short loc_180018931
0x1800188c1  mov     rdx, [rdi+38h]
0x1800188c5  mov     r8, rdi
0x1800188c8  mov     rcx, rsi
0x1800188cb  call    cs:__imp_?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z; CCompPort::Attach(void *,ICpRecvRequest *)
0x1800188d2  nop     dword ptr [rax+rax+00h]
0x1800188d7  mov     r9d, 632h
0x1800188dd  mov     r8, r12
0x1800188e0  mov     ecx, eax
0x1800188e2  mov     ebx, eax
0x1800188e4  call    ElValidateWin32
0x1800188e9  test    eax, eax
0x1800188eb  jnz     short loc_180018931
0x1800188ed  xor     ebx, ebx
0x1800188ef  cmp     dword ptr [rdi+58h], 2
0x1800188f3  jz      short loc_180018921
0x1800188f5  xor     esi, esi
0x1800188f7  cmp     [rdi+48h], ebx
0x1800188fa  jbe     short loc_180018921
0x1800188fc  mov     rcx, rdi
0x1800188ff  call    ?PostReadRequest@?$CUdpSocket@VCUdpEndpoint@@U?$IoOperation@VCUdpEndpoint@@@@@@AEAAKXZ; CUdpSocket<CUdpEndpoint,IoOperation<CUdpEndpoint>>::PostReadRequest(void)
0x180018904  mov     r9d, 666h
0x18001890a  mov     r8, r12
0x18001890d  mov     ecx, eax
0x18001890f  mov     ebx, eax
0x180018911  call    ElValidateWin32
0x180018916  test    eax, eax
0x180018918  jnz     short loc_180018921
0x18001891a  inc     esi
0x18001891c  cmp     esi, [rdi+48h]
0x18001891f  jb      short loc_1800188FC
0x180018921  mov     r9d, 63Fh
0x180018927  mov     r8, r12
0x18001892a  mov     ecx, ebx
0x18001892c  call    ElValidateWin32
0x180018931  lea     rcx, [rdi+8]; lpCriticalSection
0x180018935  call    cs:__imp_LeaveCriticalSection
0x18001893c  nop     dword ptr [rax+rax+00h]
0x180018941  mov     eax, ebx
0x180018943  mov     rcx, [rsp+0F8h+var_38]
0x18001894b  xor     rcx, rsp; StackCookie
0x18001894e  call    __security_check_cookie
0x180018953  mov     rbx, [rsp+0F8h+arg_10]
0x18001895b  add     rsp, 0D0h
0x180018962  pop     r14
0x180018964  pop     r12
0x180018966  pop     rdi
0x180018967  pop     rsi
0x180018968  pop     rbp
0x180018969  retn
0x18001896b  cmp     eax, 2
0x18001896e  jz      loc_1800188ED
0x180018974  mov     ebx, 57h ; 'W'
0x180018979  jmp     short loc_180018931
```
