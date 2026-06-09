# SsGetFQDN

- ea: `0x18002f444`
- end: `0x18002f825`
- name: `SsGetFQDN`
- size: `993`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x180009470`
- `0x180009a20`
- `0x18002f0fc`
- `0x18002f8b8`

## callees

- `0x18001deb0`
- `0x18001def0`
- `0x18001e80c`
- `0x180020de8`
- `0x180021288`
- `0x1800214a4`
- `0x1800215e8`
- `0x18002f444`
- `0x18002fc98`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002f4cb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002f4cb`
- `WS2_32!GetAddrInfoW` at `0x18002f6c3`
- `WS2_32!GetAddrInfoW` at `0x18002f6c3`
- `WS2_32!FreeAddrInfoW` at `0x18002f80c`
- `WS2_32!FreeAddrInfoW` at `0x18002f80c`
- `WS2_32!__imp_WSAStartup` at `0x18002f5ec`
- `WS2_32!__imp_WSAStartup` at `0x18002f5ec`
- `WS2_32!__imp_WSACleanup` at `0x18002f812`
- `WS2_32!__imp_WSACleanup` at `0x18002f812`

## pseudocode

```c
__int64 __fastcall SsGetFQDN(const wchar_t *Src, void *a2, _DWORD *a3, char a4)
{
  wchar_t *v8; // rax
  __int64 v9; // rdi
  int v11; // edi
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // rax
  unsigned int v14; // r15d
  unsigned int AddrInfoW; // ebx
  __int64 v16; // r8
  PWSTR ai_canonname; // rdx
  size_t v18; // rdi
  PADDRINFOW ppResult; // [rsp+30h] [rbp-D0h] BYREF
  ADDRINFOW pHints; // [rsp+38h] [rbp-C8h] BYREF
  WSAData WSAData; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pNodeName[264]; // [rsp+210h] [rbp+110h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  ppResult = 0;
  memset(&pHints, 0, sizeof(pHints));
  if ( !Src || !a2 || !a3 || *a3 < 2u )
    return 87;
  v8 = wcschr(Src, 0x2Eu);
  v9 = -1;
  if ( !v8 )
  {
    v13 = -1;
    do
      ++v13;
    while ( Src[v13] );
    v12 = 260;
    if ( v13 < 0x104 )
      v12 = v13;
LABEL_26:
    v14 = WSAStartup(0x202u, &WSAData);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids, v14);
      }
      return v14;
    }
    else
    {
      memset(&pHints.ai_addrlen, 0, 32);
      *(__m128i *)&pHints.ai_flags = _mm_load_si128((const __m128i *)&_xmm);
      memcpy_0(pNodeName, Src, 2 * v12);
      if ( 2 * v12 >= 0x20A )
LABEL_63:
        _report_rangecheckfailure();
      for ( pNodeName[v12] = 0; --v12 && pNodeName[v12] == 32; pNodeName[v12] = 0 )
      {
        if ( 2 * v12 >= 0x20A )
          goto LABEL_63;
      }
      AddrInfoW = GetAddrInfoW(pNodeName, 0, &pHints, &ppResult);
      if ( AddrInfoW )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids, AddrInfoW);
        }
      }
      else
      {
        ai_canonname = ppResult->ai_canonname;
        if ( ai_canonname )
        {
          do
            ++v9;
          while ( ai_canonname[v9] );
          v18 = 2 * v9 + 2;
          if ( v18 <= (unsigned int)*a3 )
          {
            memcpy_0(a2, ai_canonname, v18);
            *a3 = v18 - 2;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids, a2);
            }
            AddrInfoW = 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), ai_canonname, v16, v18);
            }
            AddrInfoW = 122;
            *a3 = v18 - 2;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids, Src);
          }
          *a3 = 0;
          AddrInfoW = 1359;
        }
        FreeAddrInfoW(ppResult);
      }
      WSACleanup();
      return AddrInfoW;
    }
  }
  if ( !a4 )
  {
    v12 = (unsigned __int64)(unsigned int)((_DWORD)v8 - (_DWORD)Src) >> 1;
    if ( v12 >= 0x104 )
      v12 = 260;
    goto LABEL_26;
  }
  if ( StringCbCopyNW((STRSAFE_LPWSTR)a2, (unsigned int)*a3, Src, 0x208u) == -2147024809 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids, Src);
    }
    return 87;
  }
  do
    ++v9;
  while ( *((_WORD *)a2 + v9) );
  v11 = 2 * v9;
  *a3 = v11;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids,
      (_DWORD)a2,
      v11);
  }
  return 0;
}

```

## disassembly

```asm
0x18002f444  mov     [rsp-8+arg_18], rbx
0x18002f449  push    rbp
0x18002f44a  push    rsi
0x18002f44b  push    rdi
0x18002f44c  push    r12
0x18002f44e  push    r13
0x18002f450  push    r14
0x18002f452  push    r15
0x18002f454  lea     rbp, [rsp-330h]
0x18002f45c  sub     rsp, 430h
0x18002f463  mov     rax, cs:__security_cookie
0x18002f46a  xor     rax, rsp
0x18002f46d  mov     [rbp+360h+var_40], rax
0x18002f474  mov     rsi, r8
0x18002f477  mov     r12, rdx
0x18002f47a  mov     r14, rcx
0x18002f47d  xor     edx, edx; Val
0x18002f47f  mov     r8d, 198h; Size
0x18002f485  lea     rcx, [rsp+460h+WSAData]; void *
0x18002f48a  mov     bl, r9b
0x18002f48d  call    memset_0
0x18002f492  xorps   xmm0, xmm0
0x18002f495  xor     r13d, r13d
0x18002f498  mov     [rsp+460h+ppResult], r13
0x18002f49d  movups  xmmword ptr [rsp+460h+pHints.ai_flags], xmm0
0x18002f4a2  movups  xmmword ptr [rsp+460h+pHints.ai_addrlen], xmm0
0x18002f4a7  movups  xmmword ptr [rsp+460h+pHints.ai_addr], xmm0
0x18002f4ac  test    r14, r14
0x18002f4af  jz      loc_18002F535
0x18002f4b5  test    r12, r12
0x18002f4b8  jz      short loc_18002F535
0x18002f4ba  test    rsi, rsi
0x18002f4bd  jz      short loc_18002F535
0x18002f4bf  cmp     dword ptr [rsi], 2
0x18002f4c2  jb      short loc_18002F535
0x18002f4c4  lea     edx, [r13+2Eh]; Ch
0x18002f4c8  mov     rcx, r14; Str
0x18002f4cb  call    cs:__imp_wcschr
0x18002f4d1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002f4d5  test    rax, rax
0x18002f4d8  jz      loc_18002F5C7
0x18002f4de  test    bl, bl
0x18002f4e0  jz      loc_18002F5B1
0x18002f4e6  mov     edx, [rsi]; cbDest
0x18002f4e8  mov     r9d, 208h; cbToCopy
0x18002f4ee  mov     r8, r14; pszSrc
0x18002f4f1  mov     rcx, r12; pszDest
0x18002f4f4  call    StringCbCopyNW
0x18002f4f9  cmp     eax, 80070057h
0x18002f4fe  jnz     short loc_18002F564
0x18002f500  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f507  lea     rax, WPP_GLOBAL_Control
0x18002f50e  cmp     rcx, rax
0x18002f511  jz      short loc_18002F535
0x18002f513  test    byte ptr [rcx+1Ch], 8
0x18002f517  jz      short loc_18002F535
0x18002f519  cmp     byte ptr [rcx+19h], 1
0x18002f51d  jb      short loc_18002F535
0x18002f51f  mov     rcx, [rcx+10h]
0x18002f523  lea     edx, [rdi+0Bh]
0x18002f526  mov     r9, r14
0x18002f529  lea     r8, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids
0x18002f530  call    WPP_SF_S
0x18002f535  mov     eax, 57h ; 'W'
0x18002f53a  mov     rcx, [rbp+360h+var_40]
0x18002f541  xor     rcx, rsp; StackCookie
0x18002f544  call    __security_check_cookie
0x18002f549  mov     rbx, [rsp+460h+arg_18]
0x18002f551  add     rsp, 430h
0x18002f558  pop     r15
0x18002f55a  pop     r14
0x18002f55c  pop     r13
0x18002f55e  pop     r12
0x18002f560  pop     rdi
0x18002f561  pop     rsi
0x18002f562  pop     rbp
0x18002f563  retn
0x18002f564  inc     rdi
0x18002f567  cmp     [r12+rdi*2], r13w
0x18002f56c  jnz     short loc_18002F564
0x18002f56e  add     edi, edi
0x18002f570  mov     [rsi], edi
0x18002f572  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f579  lea     rax, WPP_GLOBAL_Control
0x18002f580  cmp     rcx, rax
0x18002f583  jz      short loc_18002F5AD
0x18002f585  test    byte ptr [rcx+1Ch], 8
0x18002f589  jz      short loc_18002F5AD
0x18002f58b  cmp     byte ptr [rcx+19h], 2
0x18002f58f  jb      short loc_18002F5AD
0x18002f591  mov     rcx, [rcx+10h]
0x18002f595  lea     r8, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids
0x18002f59c  mov     edx, 0Bh
0x18002f5a1  mov     [rsp+460h+var_440], edi
0x18002f5a5  mov     r9, r12
0x18002f5a8  call    WPP_SF_Sd
0x18002f5ad  xor     eax, eax
0x18002f5af  jmp     short loc_18002F53A
0x18002f5b1  sub     eax, r14d
0x18002f5b4  mov     ecx, 104h
0x18002f5b9  mov     ebx, eax
0x18002f5bb  shr     rbx, 1
0x18002f5be  cmp     rbx, rcx
0x18002f5c1  cmovnb  rbx, rcx
0x18002f5c5  jmp     short loc_18002F5E2
0x18002f5c7  mov     rax, rdi
0x18002f5ca  inc     rax
0x18002f5cd  cmp     [r14+rax*2], r13w
0x18002f5d2  jnz     short loc_18002F5CA
0x18002f5d4  mov     ecx, 104h
0x18002f5d9  cmp     rax, rcx
0x18002f5dc  mov     ebx, ecx
0x18002f5de  cmovb   rbx, rax
0x18002f5e2  mov     ecx, 202h; wVersionRequested
0x18002f5e7  lea     rdx, [rsp+460h+WSAData]; lpWSAData
0x18002f5ec  call    cs:__imp_WSAStartup
0x18002f5f2  mov     r15d, eax
0x18002f5f5  test    eax, eax
0x18002f5f7  jz      short loc_18002F638
0x18002f5f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f600  lea     rax, WPP_GLOBAL_Control
0x18002f607  cmp     rcx, rax
0x18002f60a  jz      short loc_18002F630
0x18002f60c  test    byte ptr [rcx+1Ch], 8
0x18002f610  jz      short loc_18002F630
0x18002f612  cmp     byte ptr [rcx+19h], 1
0x18002f616  jb      short loc_18002F630
0x18002f618  mov     rcx, [rcx+10h]
0x18002f61c  lea     r8, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids
0x18002f623  mov     edx, 0Ch
0x18002f628  mov     r9d, r15d
0x18002f62b  call    WPP_SF_d
0x18002f630  mov     eax, r15d
0x18002f633  jmp     loc_18002F53A
0x18002f638  xorps   xmm0, xmm0
0x18002f63b  lea     r15, [rbx+rbx]
0x18002f63f  movdqu  xmmword ptr [rsp+460h+pHints.ai_addrlen], xmm0
0x18002f645  lea     rcx, [rbp+360h+pNodeName]; void *
0x18002f64c  mov     r8, r15; Size
0x18002f64f  movdqa  xmm0, cs:__xmm@00000006000000010000000000000002
0x18002f657  xorps   xmm1, xmm1
0x18002f65a  mov     rdx, r14; Src
0x18002f65d  movdqu  xmmword ptr [rsp+460h+pHints.ai_flags], xmm0
0x18002f663  movdqu  xmmword ptr [rsp+460h+pHints.ai_addr], xmm1
0x18002f669  call    memcpy_0
0x18002f66e  mov     edx, 20Ah
0x18002f673  cmp     r15, rdx
0x18002f676  jnb     loc_18002F81F
0x18002f67c  mov     [rbp+r15+360h+pNodeName], r13w
0x18002f685  dec     rbx
0x18002f688  test    rbx, rbx
0x18002f68b  jz      short loc_18002F6B0
0x18002f68d  lea     rcx, [rbx+rbx]
0x18002f691  cmp     [rbp+rcx+360h+pNodeName], 20h ; ' '
0x18002f69a  jnz     short loc_18002F6B0
0x18002f69c  cmp     rcx, rdx
0x18002f69f  jnb     loc_18002F81F
0x18002f6a5  mov     [rbp+rcx+360h+pNodeName], r13w
0x18002f6ae  jmp     short loc_18002F685
0x18002f6b0  lea     r9, [rsp+460h+ppResult]; ppResult
0x18002f6b5  xor     edx, edx; pServiceName
0x18002f6b7  lea     r8, [rsp+460h+pHints]; pHints
0x18002f6bc  lea     rcx, [rbp+360h+pNodeName]; pNodeName
0x18002f6c3  call    cs:__imp_GetAddrInfoW
0x18002f6c9  mov     ebx, eax
0x18002f6cb  test    eax, eax
0x18002f6cd  jz      short loc_18002F717
0x18002f6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6d6  lea     rax, WPP_GLOBAL_Control
0x18002f6dd  cmp     rcx, rax
0x18002f6e0  jz      loc_18002F812
0x18002f6e6  test    byte ptr [rcx+1Ch], 8
0x18002f6ea  jz      loc_18002F812
0x18002f6f0  cmp     byte ptr [rcx+19h], 1
0x18002f6f4  jb      loc_18002F812
0x18002f6fa  mov     rcx, [rcx+10h]
0x18002f6fe  lea     r8, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids
0x18002f705  mov     edx, 0Dh
0x18002f70a  mov     r9d, ebx
0x18002f70d  call    WPP_SF_d
0x18002f712  jmp     loc_18002F812
0x18002f717  mov     rax, [rsp+460h+ppResult]
0x18002f71c  mov     rdx, [rax+18h]; Src
0x18002f720  test    rdx, rdx
0x18002f723  jz      loc_18002F7C8
0x18002f729  inc     rdi
0x18002f72c  cmp     [rdx+rdi*2], r13w
0x18002f731  jnz     short loc_18002F729
0x18002f733  mov     eax, [rsi]
0x18002f735  lea     rdi, ds:2[rdi*2]
0x18002f73d  cmp     rdi, rax
0x18002f740  jbe     short loc_18002F77C
0x18002f742  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f749  lea     rax, WPP_GLOBAL_Control
0x18002f750  cmp     rcx, rax
0x18002f753  jz      short loc_18002F76D
0x18002f755  test    byte ptr [rcx+1Ch], 8
0x18002f759  jz      short loc_18002F76D
0x18002f75b  cmp     byte ptr [rcx+19h], 2
0x18002f75f  jb      short loc_18002F76D
0x18002f761  mov     rcx, [rcx+10h]
0x18002f765  mov     r9, rdi
0x18002f768  call    WPP_SF_P
0x18002f76d  lea     eax, [rdi-2]
0x18002f770  mov     ebx, 7Ah ; 'z'
0x18002f775  mov     [rsi], eax
0x18002f777  jmp     loc_18002F807
0x18002f77c  mov     r8, rdi; Size
0x18002f77f  mov     rcx, r12; void *
0x18002f782  call    memcpy_0
0x18002f787  lea     eax, [rdi-2]
0x18002f78a  mov     [rsi], eax
0x18002f78c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f793  lea     rax, WPP_GLOBAL_Control
0x18002f79a  cmp     rcx, rax
0x18002f79d  jz      short loc_18002F7C3
0x18002f79f  test    byte ptr [rcx+1Ch], 8
0x18002f7a3  jz      short loc_18002F7C3
0x18002f7a5  cmp     byte ptr [rcx+19h], 2
0x18002f7a9  jb      short loc_18002F7C3
0x18002f7ab  mov     rcx, [rcx+10h]
0x18002f7af  lea     r8, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids
0x18002f7b6  mov     edx, 0Fh
0x18002f7bb  mov     r9, r12
0x18002f7be  call    WPP_SF_S
0x18002f7c3  mov     ebx, r13d
0x18002f7c6  jmp     short loc_18002F807
0x18002f7c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7cf  lea     rax, WPP_GLOBAL_Control
0x18002f7d6  cmp     rcx, rax
0x18002f7d9  jz      short loc_18002F7FF
0x18002f7db  test    byte ptr [rcx+1Ch], 8
0x18002f7df  jz      short loc_18002F7FF
0x18002f7e1  cmp     byte ptr [rcx+19h], 1
0x18002f7e5  jb      short loc_18002F7FF
0x18002f7e7  mov     rcx, [rcx+10h]
0x18002f7eb  lea     r8, WPP_a7be28bc95893d00f30d82b6dc948cd5_Traceguids
0x18002f7f2  mov     edx, 10h
0x18002f7f7  mov     r9, r14
0x18002f7fa  call    WPP_SF_S
0x18002f7ff  mov     [rsi], r13d
0x18002f802  mov     ebx, 54Fh
0x18002f807  mov     rcx, [rsp+460h+ppResult]; pAddrInfo
0x18002f80c  call    cs:__imp_FreeAddrInfoW
0x18002f812  call    cs:__imp_WSACleanup
0x18002f818  mov     eax, ebx
0x18002f81a  jmp     loc_18002F53A
0x18002f81f  call    __report_rangecheckfailure
```
