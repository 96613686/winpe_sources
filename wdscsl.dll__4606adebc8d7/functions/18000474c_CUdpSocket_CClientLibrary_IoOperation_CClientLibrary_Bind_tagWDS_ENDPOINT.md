# CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Bind(tagWDS_ENDPOINT *)

- ea: `0x18000474c`
- end: `0x1800049d7`
- name: `?Bind@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKPEAUtagWDS_ENDPOINT@@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180006dac`

## callees

- `0x180004340`
- `0x180004460`
- `0x18000474c`
- `0x180005338`
- `0x180008174`
- `0x18000bd5c`
- `0x18000d6d2`
- `0x18000d700`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180004792`
- `KERNEL32!EnterCriticalSection` at `0x180004792`
- `KERNEL32!LeaveCriticalSection` at `0x180004991`
- `KERNEL32!LeaveCriticalSection` at `0x180004991`
- `WS2_32!__imp_bind` at `0x1800047e4`
- `WS2_32!__imp_bind` at `0x1800047e4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800047f4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800047f4`
- `WdsCommonLib!?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z` at `0x1800048ce`
- `WdsCommonLib!?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z` at `0x180004927`
- `WdsCommonLib!?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z` at `0x1800048ce`
- `WdsCommonLib!?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z` at `0x180004927`
- `WdsCommonLib!?Initialize@CCompPort@@QEAAKPEAXK@Z` at `0x1800048fb`
- `WdsCommonLib!?Initialize@CCompPort@@QEAAKPEAXK@Z` at `0x1800048fb`

## pseudocode

```c
__int64 __fastcall CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::Bind(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 Request; // rbx
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
  sockaddr name; // [rsp+40h] [rbp-B8h] BYREF

  memset_0(&name, 0, 0x80u);
  namelen[0] = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  Request = (unsigned int)CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::EndpointToSockaddr(
                            v5,
                            v4,
                            a2,
                            &name,
                            namelen);
  if ( (unsigned int)ElValidateWin32(Request, v7, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1500) )
    goto LABEL_23;
  if ( bind(*(_QWORD *)(a1 + 56), &name, namelen[0]) )
  {
    Error = WSAGetLastError();
    LODWORD(Request) = ElValidateWin32(Error, v10, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1510);
    goto LABEL_23;
  }
  if ( !*(_DWORD *)(a1 + 128) )
    goto LABEL_12;
  v11 = a1 + 152;
  if ( *(_DWORD *)(a1 + 256) )
  {
    v12 = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::AddMulticastSourceMembership(
            a1,
            v11,
            a1 + 260,
            a1 + 132);
    v14 = 1525;
  }
  else
  {
    v12 = CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::AddMulticastMembership(a1, v11, a1 + 132);
    v14 = 1533;
  }
  LODWORD(Request) = v12;
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
          LODWORD(Request) = 87;
          goto LABEL_23;
        }
LABEL_18:
        LODWORD(Request) = 0;
        if ( *(_DWORD *)(a1 + 88) != 2 )
        {
          for ( i = 0; i < *(_DWORD *)(a1 + 72); ++i )
          {
            Request = (unsigned int)CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostReadRequest(a1);
            if ( (unsigned int)ElValidateWin32(Request, v23, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1638) )
              break;
          }
        }
        ElValidateWin32((unsigned int)Request, v8, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1599);
        goto LABEL_23;
      }
      LODWORD(Request) = CCompPort::Initialize((CCompPort *)(a1 + 288), 0, *(_DWORD *)(a1 + 104));
      if ( (unsigned int)ElValidateWin32((unsigned int)Request, v21, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1582) )
        goto LABEL_23;
      v18 = CCompPort::Attach((CCompPort *)(a1 + 288), *(void **)(a1 + 56), (struct ICpRecvRequest *)a1);
      v20 = 1586;
    }
    else
    {
      v18 = CCompPort::Attach(*(CCompPort **)(a1 + 96), *(void **)(a1 + 56), (struct ICpRecvRequest *)a1);
      v20 = 1574;
    }
    LODWORD(Request) = v18;
    if ( (unsigned int)ElValidateWin32(v18, v19, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", v20) )
      goto LABEL_23;
    goto LABEL_18;
  }
  while ( 1 )
  {
    Request = (unsigned int)CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::AddMulticastMembership(
                              a1,
                              a1 + 4 * (v15 + 4 * (v15 + 11)),
                              a1 + 132);
    if ( (unsigned int)ElValidateWin32(Request, v16, "base\\Eco\\WDS\\wdslib\\net\\UdpSocket.h", 1561) )
      break;
    v15 = (unsigned int)(v15 + 1);
    if ( (unsigned int)v15 >= *(_DWORD *)(a1 + 172) )
      goto LABEL_12;
  }
LABEL_23:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return (unsigned int)Request;
}

```

## disassembly

```asm
0x18000474c  mov     [rsp+arg_10], rbx
0x180004751  push    rbp
0x180004752  push    rsi
0x180004753  push    rdi
0x180004754  push    r12
0x180004756  push    r14
0x180004758  sub     rsp, 0D0h
0x18000475f  mov     rax, cs:__security_cookie
0x180004766  xor     rax, rsp
0x180004769  mov     [rsp+0F8h+var_38], rax
0x180004771  mov     rbx, rdx
0x180004774  mov     rdi, rcx
0x180004777  xor     edx, edx; Val
0x180004779  lea     rcx, [rsp+0F8h+name]; void *
0x18000477e  mov     r8d, 80h; Size
0x180004784  call    memset_0
0x180004789  and     [rsp+0F8h+namelen], 0
0x18000478e  lea     rcx, [rdi+8]; lpCriticalSection
0x180004792  call    cs:__imp_EnterCriticalSection
0x180004799  nop     dword ptr [rax+rax+00h]
0x18000479e  lea     rax, [rsp+0F8h+namelen]
0x1800047a3  mov     r8, rbx
0x1800047a6  lea     r9, [rsp+0F8h+name]
0x1800047ab  mov     [rsp+0F8h+var_D8], rax
0x1800047b0  call    ?EndpointToSockaddr@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKHPEAUtagWDS_ENDPOINT@@PEAUsockaddr_storage@@PEAH@Z; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::EndpointToSockaddr(int,tagWDS_ENDPOINT *,sockaddr_storage *,int *)
0x1800047b5  lea     r12, aBaseEcoWdsWdsl; "base\\Eco\\WDS\\wdslib\\net\\UdpSocket."...
0x1800047bc  mov     r9d, 5DCh
0x1800047c2  mov     r8, r12
0x1800047c5  mov     ecx, eax
0x1800047c7  mov     ebx, eax
0x1800047c9  call    ElValidateWin32
0x1800047ce  test    eax, eax
0x1800047d0  jnz     loc_18000498D
0x1800047d6  mov     r8d, [rsp+0F8h+namelen]; namelen
0x1800047db  lea     rdx, [rsp+0F8h+name]; name
0x1800047e0  mov     rcx, [rdi+38h]; s
0x1800047e4  call    cs:__imp_bind
0x1800047eb  nop     dword ptr [rax+rax+00h]
0x1800047f0  test    eax, eax
0x1800047f2  jz      short loc_180004817
0x1800047f4  call    cs:__imp_WSAGetLastError
0x1800047fb  nop     dword ptr [rax+rax+00h]
0x180004800  mov     r9d, 5E6h
0x180004806  mov     r8, r12
0x180004809  mov     ecx, eax
0x18000480b  call    ElValidateWin32
0x180004810  mov     ebx, eax
0x180004812  jmp     loc_18000498D
0x180004817  cmp     dword ptr [rdi+80h], 0
0x18000481e  jz      loc_1800048BC
0x180004824  cmp     dword ptr [rdi+100h], 0
0x18000482b  lea     rbp, [rdi+84h]
0x180004832  lea     rdx, [rdi+98h]
0x180004839  mov     rcx, rdi
0x18000483c  jz      short loc_180004855
0x18000483e  lea     r8, [rdi+104h]
0x180004845  mov     r9, rbp
0x180004848  call    ?AddMulticastSourceMembership@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKPEAUtagWDS_IP_ADDRESS6@@00@Z; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::AddMulticastSourceMembership(tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)
0x18000484d  mov     r9d, 5F5h
0x180004853  jmp     short loc_180004863
0x180004855  mov     r8, rbp
0x180004858  call    ?AddMulticastMembership@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKPEAUtagWDS_IP_ADDRESS6@@0@Z; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::AddMulticastMembership(tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)
0x18000485d  mov     r9d, 5FDh
0x180004863  mov     r8, r12
0x180004866  mov     ecx, eax
0x180004868  mov     ebx, eax
0x18000486a  call    ElValidateWin32
0x18000486f  test    eax, eax
0x180004871  jnz     loc_18000498D
0x180004877  xor     esi, esi
0x180004879  cmp     [rdi+0ACh], esi
0x18000487f  jbe     short loc_1800048BC
0x180004881  lea     rcx, [rsi+0Bh]
0x180004885  mov     r8, rbp
0x180004888  lea     rcx, [rsi+rcx*4]
0x18000488c  lea     rdx, [rdi+rcx*4]
0x180004890  mov     rcx, rdi
0x180004893  call    ?AddMulticastMembership@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@QEAAKPEAUtagWDS_IP_ADDRESS6@@0@Z; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::AddMulticastMembership(tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)
0x180004898  mov     r9d, 619h
0x18000489e  mov     r8, r12
0x1800048a1  mov     ecx, eax
0x1800048a3  mov     ebx, eax
0x1800048a5  call    ElValidateWin32
0x1800048aa  test    eax, eax
0x1800048ac  jnz     loc_18000498D
0x1800048b2  inc     esi
0x1800048b4  cmp     esi, [rdi+0ACh]
0x1800048ba  jb      short loc_180004881
0x1800048bc  mov     eax, [rdi+58h]
0x1800048bf  test    eax, eax
0x1800048c1  jnz     short loc_1800048E2
0x1800048c3  mov     rdx, [rdi+38h]
0x1800048c7  mov     r8, rdi
0x1800048ca  mov     rcx, [rdi+60h]
0x1800048ce  call    cs:__imp_?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z; CCompPort::Attach(void *,ICpRecvRequest *)
0x1800048d5  nop     dword ptr [rax+rax+00h]
0x1800048da  mov     r9d, 626h
0x1800048e0  jmp     short loc_180004939
0x1800048e2  cmp     eax, 1
0x1800048e5  jnz     loc_1800049C7
0x1800048eb  mov     r8d, [rdi+68h]
0x1800048ef  lea     rsi, [rdi+120h]
0x1800048f6  mov     rcx, rsi
0x1800048f9  xor     edx, edx
0x1800048fb  call    cs:__imp_?Initialize@CCompPort@@QEAAKPEAXK@Z; CCompPort::Initialize(void *,ulong)
0x180004902  nop     dword ptr [rax+rax+00h]
0x180004907  mov     r9d, 62Eh
0x18000490d  mov     r8, r12
0x180004910  mov     ecx, eax
0x180004912  mov     ebx, eax
0x180004914  call    ElValidateWin32
0x180004919  test    eax, eax
0x18000491b  jnz     short loc_18000498D
0x18000491d  mov     rdx, [rdi+38h]
0x180004921  mov     r8, rdi
0x180004924  mov     rcx, rsi
0x180004927  call    cs:__imp_?Attach@CCompPort@@QEAAKPEAXPEAVICpRecvRequest@@@Z; CCompPort::Attach(void *,ICpRecvRequest *)
0x18000492e  nop     dword ptr [rax+rax+00h]
0x180004933  mov     r9d, 632h
0x180004939  mov     r8, r12
0x18000493c  mov     ecx, eax
0x18000493e  mov     ebx, eax
0x180004940  call    ElValidateWin32
0x180004945  test    eax, eax
0x180004947  jnz     short loc_18000498D
0x180004949  xor     ebx, ebx
0x18000494b  cmp     dword ptr [rdi+58h], 2
0x18000494f  jz      short loc_18000497D
0x180004951  xor     esi, esi
0x180004953  cmp     [rdi+48h], ebx
0x180004956  jbe     short loc_18000497D
0x180004958  mov     rcx, rdi
0x18000495b  call    ?PostReadRequest@?$CUdpSocket@VCClientLibrary@@U?$IoOperation@VCClientLibrary@@@@@@AEAAKXZ; CUdpSocket<CClientLibrary,IoOperation<CClientLibrary>>::PostReadRequest(void)
0x180004960  mov     r9d, 666h
0x180004966  mov     r8, r12
0x180004969  mov     ecx, eax
0x18000496b  mov     ebx, eax
0x18000496d  call    ElValidateWin32
0x180004972  test    eax, eax
0x180004974  jnz     short loc_18000497D
0x180004976  inc     esi
0x180004978  cmp     esi, [rdi+48h]
0x18000497b  jb      short loc_180004958
0x18000497d  mov     r9d, 63Fh
0x180004983  mov     r8, r12
0x180004986  mov     ecx, ebx
0x180004988  call    ElValidateWin32
0x18000498d  lea     rcx, [rdi+8]; lpCriticalSection
0x180004991  call    cs:__imp_LeaveCriticalSection
0x180004998  nop     dword ptr [rax+rax+00h]
0x18000499d  mov     eax, ebx
0x18000499f  mov     rcx, [rsp+0F8h+var_38]
0x1800049a7  xor     rcx, rsp; StackCookie
0x1800049aa  call    __security_check_cookie
0x1800049af  mov     rbx, [rsp+0F8h+arg_10]
0x1800049b7  add     rsp, 0D0h
0x1800049be  pop     r14
0x1800049c0  pop     r12
0x1800049c2  pop     rdi
0x1800049c3  pop     rsi
0x1800049c4  pop     rbp
0x1800049c5  retn
0x1800049c7  cmp     eax, 2
0x1800049ca  jz      loc_180004949
0x1800049d0  mov     ebx, 57h ; 'W'
0x1800049d5  jmp     short loc_18000498D
```
