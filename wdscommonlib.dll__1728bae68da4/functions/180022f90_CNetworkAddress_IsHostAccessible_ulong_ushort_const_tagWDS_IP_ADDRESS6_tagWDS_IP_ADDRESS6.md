# CNetworkAddress::IsHostAccessible(ulong,ushort const *,tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)

- ea: `0x180022f90`
- end: `0x1800230d9`
- name: `?IsHostAccessible@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@1@Z`
- size: `329`
- prototype: `static unsigned int(unsigned int, const unsigned __int16 *, struct tagWDS_IP_ADDRESS6 *, struct tagWDS_IP_ADDRESS6 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180021900`
- `0x180021ce0`
- `0x180022f90`
- `0x180023d18`
- `0x180030390`

## import_xrefs

- `WS2_32!FreeAddrInfoW` at `0x180023088`
- `WS2_32!FreeAddrInfoW` at `0x180023088`
- `WS2_32!GetAddrInfoW` at `0x180022ff8`
- `WS2_32!GetAddrInfoW` at `0x180023019`
- `WS2_32!GetAddrInfoW` at `0x180022ff8`
- `WS2_32!GetAddrInfoW` at `0x180023019`
- `WS2_32!__imp_WSAGetLastError` at `0x180023029`
- `WS2_32!__imp_WSAGetLastError` at `0x180023029`

## pseudocode

```c
__int64 __fastcall CNetworkAddress::IsHostAccessible(
        int a1,
        const unsigned __int16 *a2,
        struct tagWDS_IP_ADDRESS6 *a3,
        struct tagWDS_IP_ADDRESS6 *a4)
{
  unsigned int Error; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int LocalInterface; // ebx
  PADDRINFOW i; // rdi
  int v13; // eax
  int v14; // eax
  PADDRINFOW ppResult; // [rsp+20h] [rbp-39h] BYREF
  ADDRINFOW pHints; // [rsp+28h] [rbp-31h] BYREF
  __int128 v17; // [rsp+58h] [rbp-1h] BYREF
  int v18; // [rsp+68h] [rbp+Fh]
  __int128 v19; // [rsp+70h] [rbp+17h] BYREF
  int v20; // [rsp+80h] [rbp+27h]

  ppResult = 0;
  memset(&pHints.ai_socktype, 0, 40);
  pHints.ai_family = a1;
  pHints.ai_flags = 4;
  v18 = 0;
  v20 = 0;
  v17 = 0;
  v19 = 0;
  if ( GetAddrInfoW(a2, 0, &pHints, &ppResult) && (pHints.ai_flags = 0, GetAddrInfoW(a2, 0, &pHints, &ppResult)) )
  {
    Error = WSAGetLastError();
    LocalInterface = ElValidateWin32_12(Error, v8, v9, 0x4BDu);
  }
  else
  {
    for ( i = ppResult; ; i = i->ai_next )
    {
      do
      {
        if ( !i )
        {
          LocalInterface = 10051;
          goto LABEL_10;
        }
      }
      while ( CNetworkAddress::ExtractAddress(i, 0, (struct tagWDS_IP_ADDRESS6 *)&v17) );
      LocalInterface = CNetworkAddress::FindLocalInterface(
                         (struct tagWDS_IP_ADDRESS6 *)&v17,
                         (struct tagWDS_IP_ADDRESS6 *)&v19);
      if ( !LocalInterface )
        break;
    }
    if ( a3 )
    {
      v13 = v18;
      *(_OWORD *)a3 = v17;
      *((_DWORD *)a3 + 4) = v13;
    }
    if ( a4 )
    {
      v14 = v20;
      *(_OWORD *)a4 = v19;
      *((_DWORD *)a4 + 4) = v14;
    }
  }
LABEL_10:
  if ( ppResult )
    FreeAddrInfoW(ppResult);
  return LocalInterface;
}

```

## disassembly

```asm
0x180022f90  push    rbp
0x180022f92  push    rbx
0x180022f93  push    rsi
0x180022f94  push    rdi
0x180022f95  push    r14
0x180022f97  lea     rbp, [rsp-37h]
0x180022f9c  sub     rsp, 90h
0x180022fa3  mov     rax, cs:__security_cookie
0x180022faa  xor     rax, rsp
0x180022fad  mov     [rbp+57h+var_28], rax
0x180022fb1  and     [rbp+57h+ppResult], 0
0x180022fb6  xorps   xmm0, xmm0
0x180022fb9  movups  xmmword ptr [rbp+57h+pHints.ai_flags], xmm0
0x180022fbd  mov     rbx, rdx
0x180022fc0  mov     [rbp+57h+pHints.ai_family], ecx
0x180022fc3  xor     eax, eax
0x180022fc5  mov     [rbp+57h+pHints.ai_flags], 4
0x180022fcc  mov     rsi, r9
0x180022fcf  mov     [rbp+57h+var_48], eax
0x180022fd2  mov     r14, r8
0x180022fd5  mov     [rbp+57h+var_30], eax
0x180022fd8  xorps   xmm1, xmm1
0x180022fdb  lea     r9, [rbp+57h+ppResult]; ppResult
0x180022fdf  mov     rcx, rbx; pNodeName
0x180022fe2  lea     r8, [rbp+57h+pHints]; pHints
0x180022fe6  xor     edx, edx; pServiceName
0x180022fe8  movups  xmmword ptr [rbp+57h+pHints.ai_addrlen], xmm0
0x180022fec  movups  xmmword ptr [rbp+57h+pHints.ai_addr], xmm0
0x180022ff0  movups  [rbp+57h+var_58], xmm0
0x180022ff4  movups  [rbp+57h+var_40], xmm1
0x180022ff8  call    cs:__imp_GetAddrInfoW
0x180022fff  nop     dword ptr [rax+rax+00h]
0x180023004  test    eax, eax
0x180023006  jz      short loc_180023046
0x180023008  and     [rbp+57h+pHints.ai_flags], 0
0x18002300c  lea     r9, [rbp+57h+ppResult]; ppResult
0x180023010  lea     r8, [rbp+57h+pHints]; pHints
0x180023014  xor     edx, edx; pServiceName
0x180023016  mov     rcx, rbx; pNodeName
0x180023019  call    cs:__imp_GetAddrInfoW
0x180023020  nop     dword ptr [rax+rax+00h]
0x180023025  test    eax, eax
0x180023027  jz      short loc_180023046
0x180023029  call    cs:__imp_WSAGetLastError
0x180023030  nop     dword ptr [rax+rax+00h]
0x180023035  mov     ecx, eax
0x180023037  mov     r9d, 4BDh
0x18002303d  call    ElValidateWin32_12
0x180023042  mov     ebx, eax
0x180023044  jmp     short loc_18002307F
0x180023046  mov     rdi, [rbp+57h+ppResult]
0x18002304a  jmp     short loc_180023075
0x18002304c  lea     r8, [rbp+57h+var_58]; struct tagWDS_IP_ADDRESS6 *
0x180023050  xor     edx, edx; int
0x180023052  mov     rcx, rdi; struct addrinfoW *
0x180023055  call    ?ExtractAddress@CNetworkAddress@@CAKPEAUaddrinfoW@@HPEAUtagWDS_IP_ADDRESS6@@@Z; CNetworkAddress::ExtractAddress(addrinfoW *,int,tagWDS_IP_ADDRESS6 *)
0x18002305a  test    eax, eax
0x18002305c  jnz     short loc_180023075
0x18002305e  lea     rdx, [rbp+57h+var_40]; struct tagWDS_IP_ADDRESS6 *
0x180023062  lea     rcx, [rbp+57h+var_58]; struct tagWDS_IP_ADDRESS6 *
0x180023066  call    ?FindLocalInterface@CNetworkAddress@@SAKPEAUtagWDS_IP_ADDRESS6@@0@Z; CNetworkAddress::FindLocalInterface(tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)
0x18002306b  mov     ebx, eax
0x18002306d  test    eax, eax
0x18002306f  jz      short loc_1800230B1
0x180023071  mov     rdi, [rdi+28h]
0x180023075  test    rdi, rdi
0x180023078  jnz     short loc_18002304C
0x18002307a  mov     ebx, 2743h
0x18002307f  mov     rcx, [rbp+57h+ppResult]; pAddrInfo
0x180023083  test    rcx, rcx
0x180023086  jz      short loc_180023094
0x180023088  call    cs:__imp_FreeAddrInfoW
0x18002308f  nop     dword ptr [rax+rax+00h]
0x180023094  mov     eax, ebx
0x180023096  mov     rcx, [rbp+57h+var_28]
0x18002309a  xor     rcx, rsp; StackCookie
0x18002309d  call    __security_check_cookie
0x1800230a2  add     rsp, 90h
0x1800230a9  pop     r14
0x1800230ab  pop     rdi
0x1800230ac  pop     rsi
0x1800230ad  pop     rbx
0x1800230ae  pop     rbp
0x1800230af  retn
0x1800230b1  test    r14, r14
0x1800230b4  jz      short loc_1800230C5
0x1800230b6  movups  xmm0, [rbp+57h+var_58]
0x1800230ba  mov     eax, [rbp+57h+var_48]
0x1800230bd  movups  xmmword ptr [r14], xmm0
0x1800230c1  mov     [r14+10h], eax
0x1800230c5  test    rsi, rsi
0x1800230c8  jz      short loc_18002307F
0x1800230ca  movups  xmm0, [rbp+57h+var_40]
0x1800230ce  mov     eax, [rbp+57h+var_30]
0x1800230d1  movups  xmmword ptr [rsi], xmm0
0x1800230d4  mov     [rsi+10h], eax
0x1800230d7  jmp     short loc_18002307F
```
