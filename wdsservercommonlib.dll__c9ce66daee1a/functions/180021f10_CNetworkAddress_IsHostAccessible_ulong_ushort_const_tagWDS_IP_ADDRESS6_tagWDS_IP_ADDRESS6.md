# CNetworkAddress::IsHostAccessible(ulong,ushort const *,tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)

- ea: `0x180021f10`
- end: `0x180022059`
- name: `?IsHostAccessible@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@1@Z`
- size: `329`
- prototype: `static unsigned int(unsigned int, const unsigned __int16 *, struct tagWDS_IP_ADDRESS6 *, struct tagWDS_IP_ADDRESS6 *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800208e0`
- `0x180020ca0`
- `0x180021f10`
- `0x180022c98`
- `0x18002f3e0`

## import_xrefs

- `WS2_32!GetAddrInfoW` at `0x180021f78`
- `WS2_32!GetAddrInfoW` at `0x180021f99`
- `WS2_32!GetAddrInfoW` at `0x180021f78`
- `WS2_32!GetAddrInfoW` at `0x180021f99`
- `WS2_32!FreeAddrInfoW` at `0x180022008`
- `WS2_32!FreeAddrInfoW` at `0x180022008`
- `WS2_32!__imp_WSAGetLastError` at `0x180021fa9`
- `WS2_32!__imp_WSAGetLastError` at `0x180021fa9`

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
0x180021f10  push    rbp
0x180021f12  push    rbx
0x180021f13  push    rsi
0x180021f14  push    rdi
0x180021f15  push    r14
0x180021f17  lea     rbp, [rsp-37h]
0x180021f1c  sub     rsp, 90h
0x180021f23  mov     rax, cs:__security_cookie
0x180021f2a  xor     rax, rsp
0x180021f2d  mov     [rbp+57h+var_28], rax
0x180021f31  and     [rbp+57h+ppResult], 0
0x180021f36  xorps   xmm0, xmm0
0x180021f39  movups  xmmword ptr [rbp+57h+pHints.ai_flags], xmm0
0x180021f3d  mov     rbx, rdx
0x180021f40  mov     [rbp+57h+pHints.ai_family], ecx
0x180021f43  xor     eax, eax
0x180021f45  mov     [rbp+57h+pHints.ai_flags], 4
0x180021f4c  mov     rsi, r9
0x180021f4f  mov     [rbp+57h+var_48], eax
0x180021f52  mov     r14, r8
0x180021f55  mov     [rbp+57h+var_30], eax
0x180021f58  xorps   xmm1, xmm1
0x180021f5b  lea     r9, [rbp+57h+ppResult]; ppResult
0x180021f5f  mov     rcx, rbx; pNodeName
0x180021f62  lea     r8, [rbp+57h+pHints]; pHints
0x180021f66  xor     edx, edx; pServiceName
0x180021f68  movups  xmmword ptr [rbp+57h+pHints.ai_addrlen], xmm0
0x180021f6c  movups  xmmword ptr [rbp+57h+pHints.ai_addr], xmm0
0x180021f70  movups  [rbp+57h+var_58], xmm0
0x180021f74  movups  [rbp+57h+var_40], xmm1
0x180021f78  call    cs:__imp_GetAddrInfoW
0x180021f7f  nop     dword ptr [rax+rax+00h]
0x180021f84  test    eax, eax
0x180021f86  jz      short loc_180021FC6
0x180021f88  and     [rbp+57h+pHints.ai_flags], 0
0x180021f8c  lea     r9, [rbp+57h+ppResult]; ppResult
0x180021f90  lea     r8, [rbp+57h+pHints]; pHints
0x180021f94  xor     edx, edx; pServiceName
0x180021f96  mov     rcx, rbx; pNodeName
0x180021f99  call    cs:__imp_GetAddrInfoW
0x180021fa0  nop     dword ptr [rax+rax+00h]
0x180021fa5  test    eax, eax
0x180021fa7  jz      short loc_180021FC6
0x180021fa9  call    cs:__imp_WSAGetLastError
0x180021fb0  nop     dword ptr [rax+rax+00h]
0x180021fb5  mov     ecx, eax
0x180021fb7  mov     r9d, 4BDh
0x180021fbd  call    ElValidateWin32_12
0x180021fc2  mov     ebx, eax
0x180021fc4  jmp     short loc_180021FFF
0x180021fc6  mov     rdi, [rbp+57h+ppResult]
0x180021fca  jmp     short loc_180021FF5
0x180021fcc  lea     r8, [rbp+57h+var_58]; struct tagWDS_IP_ADDRESS6 *
0x180021fd0  xor     edx, edx; int
0x180021fd2  mov     rcx, rdi; struct addrinfoW *
0x180021fd5  call    ?ExtractAddress@CNetworkAddress@@CAKPEAUaddrinfoW@@HPEAUtagWDS_IP_ADDRESS6@@@Z; CNetworkAddress::ExtractAddress(addrinfoW *,int,tagWDS_IP_ADDRESS6 *)
0x180021fda  test    eax, eax
0x180021fdc  jnz     short loc_180021FF5
0x180021fde  lea     rdx, [rbp+57h+var_40]; struct tagWDS_IP_ADDRESS6 *
0x180021fe2  lea     rcx, [rbp+57h+var_58]; struct tagWDS_IP_ADDRESS6 *
0x180021fe6  call    ?FindLocalInterface@CNetworkAddress@@SAKPEAUtagWDS_IP_ADDRESS6@@0@Z; CNetworkAddress::FindLocalInterface(tagWDS_IP_ADDRESS6 *,tagWDS_IP_ADDRESS6 *)
0x180021feb  mov     ebx, eax
0x180021fed  test    eax, eax
0x180021fef  jz      short loc_180022031
0x180021ff1  mov     rdi, [rdi+28h]
0x180021ff5  test    rdi, rdi
0x180021ff8  jnz     short loc_180021FCC
0x180021ffa  mov     ebx, 2743h
0x180021fff  mov     rcx, [rbp+57h+ppResult]; pAddrInfo
0x180022003  test    rcx, rcx
0x180022006  jz      short loc_180022014
0x180022008  call    cs:__imp_FreeAddrInfoW
0x18002200f  nop     dword ptr [rax+rax+00h]
0x180022014  mov     eax, ebx
0x180022016  mov     rcx, [rbp+57h+var_28]
0x18002201a  xor     rcx, rsp; StackCookie
0x18002201d  call    __security_check_cookie
0x180022022  add     rsp, 90h
0x180022029  pop     r14
0x18002202b  pop     rdi
0x18002202c  pop     rsi
0x18002202d  pop     rbx
0x18002202e  pop     rbp
0x18002202f  retn
0x180022031  test    r14, r14
0x180022034  jz      short loc_180022045
0x180022036  movups  xmm0, [rbp+57h+var_58]
0x18002203a  mov     eax, [rbp+57h+var_48]
0x18002203d  movups  xmmword ptr [r14], xmm0
0x180022041  mov     [r14+10h], eax
0x180022045  test    rsi, rsi
0x180022048  jz      short loc_180021FFF
0x18002204a  movups  xmm0, [rbp+57h+var_40]
0x18002204e  mov     eax, [rbp+57h+var_30]
0x180022051  movups  xmmword ptr [rsi], xmm0
0x180022054  mov     [rsi+10h], eax
0x180022057  jmp     short loc_180021FFF
```
