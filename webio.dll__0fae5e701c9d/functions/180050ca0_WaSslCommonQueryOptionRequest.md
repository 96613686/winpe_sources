# WaSslCommonQueryOptionRequest

- ea: `0x180050ca0`
- end: `0x180051511`
- name: `WaSslCommonQueryOptionRequest`
- size: `2161`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180050c30`

## callees

- `0x180050ca0`
- `0x18008d63c`
- `0x18008d914`
- `0x18008d97c`
- `0x18008dac8`
- `0x180091678`
- `0x1800971ec`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050d1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050dd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050e24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050f10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050f53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051073`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800510f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005116a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800511a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800511f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051232`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051271`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800512ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051330`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005136d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800513d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050d1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050dd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050e24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050f10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050f53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051073`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800510f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005116a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800511a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800511f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051232`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051271`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800512ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051330`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005136d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800513d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050d81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050d81`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180050f85`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180050f85`
- `CRYPT32!CertDuplicateCertificateChain` at `0x180050e02`
- `CRYPT32!CertDuplicateCertificateChain` at `0x180050e02`

## pseudocode

```c
__int64 __fastcall WaSslCommonQueryOptionRequest(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int64 a5,
        unsigned __int64 *a6)
{
  unsigned __int64 *v6; // rdi
  __int64 v7; // rsi
  unsigned int *v9; // rdx
  unsigned __int64 v10; // rax
  unsigned int TokenBindingMessage; // ebx
  bool v13; // zf
  const CERT_CHAIN_CONTEXT *v14; // rcx
  __int128 *v15; // rax
  __int64 v16; // rcx
  __int128 v17; // xmm0
  const CERT_CONTEXT *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  unsigned int v21; // eax
  unsigned int TokenBindingPublicKey; // eax
  unsigned __int64 v23; // r9
  unsigned int v24; // [rsp+80h] [rbp+18h] BYREF

  v6 = a6;
  v24 = 0;
  v7 = a4;
  *a6 = 0;
  if ( a3 == 13 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
    v9 = (unsigned int *)(a2 + 328);
    *v6 = 0;
    if ( a2 == -328 || !*(_QWORD *)(a2 + 336) )
    {
      TokenBindingMessage = 1168;
      if ( (xmmword_1800AD710 & 8) != 0 )
      {
        v19 = 28;
        v20 = 1168;
LABEL_48:
        WPP_SF_d(515, v19, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids, v20);
      }
    }
    else
    {
      v10 = *v9 + 16LL;
      *v6 = v10;
      if ( a5 < v10 )
      {
        TokenBindingMessage = 234;
      }
      else
      {
        TokenBindingMessage = 0;
        *(_OWORD *)v7 = *(_OWORD *)v9;
        memcpy_0((void *)(v7 + 16), *(const void **)(a2 + 336), *v9);
        *(_QWORD *)(v7 + 8) = v7 + 16;
      }
    }
  }
  else
  {
    if ( a3 != 15 )
    {
      TokenBindingMessage = 0;
      switch ( a3 )
      {
        case 3u:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 4;
          *v6 = 4;
          if ( v13 )
            *(_DWORD *)v7 = *(_DWORD *)(a2 + 204);
          else
            TokenBindingMessage = 234;
          goto LABEL_8;
        case 6u:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 4;
          *v6 = 4;
          if ( v13 )
            *(_DWORD *)v7 = *(_DWORD *)(a2 + 1056);
          else
            TokenBindingMessage = 234;
          goto LABEL_8;
        case 8u:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 4;
          *v6 = 4;
          if ( v13 )
            *(_DWORD *)v7 = *(_DWORD *)(a2 + 232);
          else
            TokenBindingMessage = 234;
          goto LABEL_8;
        case 9u:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 8;
          *v6 = 8;
          if ( v13 )
          {
            v18 = *(const CERT_CONTEXT **)(a2 + 216);
            if ( !v18 )
              goto LABEL_39;
            CertDuplicateCertificateContext(v18);
            *(_QWORD *)v7 = *(_QWORD *)(a2 + 216);
          }
          else
          {
            TokenBindingMessage = 234;
          }
          goto LABEL_8;
        case 0xCu:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          if ( !*(_QWORD *)(a2 + 312) )
          {
            *v6 = 0;
            TokenBindingMessage = 1168;
            goto LABEL_8;
          }
          v21 = WaCopyIssuerList(a2 + 312, v7, a5, v6);
          TokenBindingMessage = v21;
          if ( !v21 || v21 == 997 || v21 == 234 || (xmmword_1800AD710 & 8) == 0 )
            goto LABEL_8;
          v19 = 27;
          v20 = v21;
          goto LABEL_48;
        case 0xEu:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 28;
          *v6 = 28;
          if ( v13 )
          {
            *(_OWORD *)v7 = *(_OWORD *)(a2 + 344);
            *(_OWORD *)(v7 + 12) = *(_OWORD *)(a2 + 356);
          }
          else
          {
            TokenBindingMessage = 234;
          }
          goto LABEL_8;
        case 0x11u:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 4;
          *v6 = 4;
          if ( v13 )
          {
            if ( !*(_BYTE *)(a2 + 1064) )
              goto LABEL_40;
            *(_DWORD *)v7 = *(_DWORD *)(a2 + 1060);
          }
          else
          {
            TokenBindingMessage = 234;
          }
          goto LABEL_8;
        case 0x13u:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 4;
          *v6 = 4;
          if ( v13 )
          {
            if ( *(_BYTE *)(a2 + 1243) && *(_BYTE *)(a2 + 1242) )
            {
              *(_DWORD *)v7 = 1;
            }
            else
            {
              *(_DWORD *)v7 = 0;
              TokenBindingMessage = 1168;
            }
          }
          else
          {
            TokenBindingMessage = 234;
          }
          goto LABEL_8;
        case 0x16u:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 8;
          *v6 = 8;
          if ( v13 )
          {
            v14 = *(const CERT_CHAIN_CONTEXT **)(a2 + 224);
            if ( v14 )
            {
              CertDuplicateCertificateChain(v14);
              *(_QWORD *)v7 = *(_QWORD *)(a2 + 224);
            }
            else
            {
LABEL_39:
              *(_QWORD *)v7 = 0;
LABEL_40:
              TokenBindingMessage = 1168;
            }
          }
          else
          {
            TokenBindingMessage = 234;
          }
          goto LABEL_8;
        case 0x1Bu:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 1;
          *v6 = 1;
          if ( v13 )
            *(_BYTE *)v7 = *(_DWORD *)(a2 + 116) != -1;
          else
            TokenBindingMessage = 234;
          goto LABEL_8;
        case 0x1Du:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v24 = a5;
          TokenBindingPublicKey = WapSslGetTokenBindingPublicKey(a2, v7, &v24);
          TokenBindingMessage = TokenBindingPublicKey;
          if ( !TokenBindingPublicKey || TokenBindingPublicKey == 234 )
            *v6 = v24;
          goto LABEL_8;
        case 0x1Eu:
          if ( a5 != 8 )
          {
            TokenBindingMessage = 87;
            goto LABEL_21;
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          TokenBindingMessage = WapSslGetTokenBindingMessage(a2, v7, &v24);
          if ( !TokenBindingMessage )
            *v6 = v24;
          goto LABEL_8;
        case 0x20u:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 8;
          *v6 = 8;
          if ( v13 )
            WapGetTlsHandshakeMismatchInfo(a2, v7);
          else
            TokenBindingMessage = 234;
          goto LABEL_8;
        case 0x39u:
          v13 = a5 == 272;
          *v6 = 272;
          if ( !v13 )
            return 234;
          *(_OWORD *)(a4 + 56) = *(_OWORD *)(a2 + 1136);
          *(_OWORD *)(a4 + 72) = *(_OWORD *)(a2 + 1152);
          *(_OWORD *)(a4 + 88) = *(_OWORD *)(a2 + 1168);
          TokenBindingMessage = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, unsigned __int64 *))(*(_QWORD *)(a2 + 16) + 72LL))(
                                  a1,
                                  a3,
                                  a4,
                                  272,
                                  v6);
          goto LABEL_9;
        case 0x3Au:
          v13 = a5 == 152;
          *v6 = 152;
          if ( !v13 )
            return 234;
          *(_OWORD *)(a4 + 24) = *(_OWORD *)(a2 + 1184);
          *(_OWORD *)(a4 + 40) = *(_OWORD *)(a2 + 1200);
          *(_QWORD *)(a4 + 56) = *(_QWORD *)(a2 + 1216);
          TokenBindingMessage = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, unsigned __int64 *))(*(_QWORD *)(a2 + 16) + 72LL))(
                                  a1,
                                  a3,
                                  a4,
                                  152,
                                  v6);
          goto LABEL_9;
        case 0x42u:
          EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
          v13 = a5 == 4;
          *v6 = 4;
          if ( v13 )
            *(_DWORD *)v7 = *(_DWORD *)(a2 + 200);
          else
            TokenBindingMessage = 234;
          goto LABEL_8;
        case 0x4Fu:
          v23 = a5;
          *v6 = 24;
          if ( v23 < 0x18 )
            return 234;
          TokenBindingMessage = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(a2 + 16) + 72LL))(
                                  a1,
                                  a3,
                                  v7);
          if ( TokenBindingMessage )
            goto LABEL_19;
          if ( !*(_DWORD *)v7 )
          {
            *(_OWORD *)v7 = *(_OWORD *)(a2 + 240);
            *(_QWORD *)(v7 + 16) = *(_QWORD *)(a2 + 256);
          }
          break;
        default:
          TokenBindingMessage = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned __int64, unsigned __int64 *))(*(_QWORD *)(a2 + 16) + 72LL))(
                                  a1,
                                  a3,
                                  a4,
                                  a5,
                                  v6);
          goto LABEL_9;
      }
      return TokenBindingMessage;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
    v13 = a5 == 680;
    *v6 = 680;
    if ( v13 )
    {
      v15 = (__int128 *)(a2 + 372);
      v16 = 5;
      do
      {
        v7 += 128;
        v17 = *v15;
        v15 += 8;
        *(_OWORD *)(v7 - 128) = v17;
        *(_OWORD *)(v7 - 112) = *(v15 - 7);
        *(_OWORD *)(v7 - 96) = *(v15 - 6);
        *(_OWORD *)(v7 - 80) = *(v15 - 5);
        *(_OWORD *)(v7 - 64) = *(v15 - 4);
        *(_OWORD *)(v7 - 48) = *(v15 - 3);
        *(_OWORD *)(v7 - 32) = *(v15 - 2);
        *(_OWORD *)(v7 - 16) = *(v15 - 1);
        --v16;
      }
      while ( v16 );
      TokenBindingMessage = 0;
      *(_OWORD *)v7 = *v15;
      *(_OWORD *)(v7 + 16) = v15[1];
      *(_QWORD *)(v7 + 32) = *((_QWORD *)v15 + 4);
    }
    else
    {
      TokenBindingMessage = 234;
    }
  }
LABEL_8:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 1256));
LABEL_9:
  if ( TokenBindingMessage )
  {
LABEL_19:
    if ( TokenBindingMessage != 234 && TokenBindingMessage != 997 )
    {
LABEL_21:
      if ( (xmmword_1800AD710 & 8) != 0 )
        WPP_SF_d(515, 18, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids, TokenBindingMessage);
    }
  }
  return TokenBindingMessage;
}

```

## disassembly

```asm
0x180050ca0  push    rbx
0x180050ca2  push    rbp
0x180050ca3  push    rsi
0x180050ca4  push    rdi
0x180050ca5  push    r14
0x180050ca7  push    r15
0x180050ca9  sub     rsp, 38h
0x180050cad  mov     rdi, [rsp+68h+arg_28]
0x180050cb5  xor     r15d, r15d
0x180050cb8  mov     [rsp+68h+arg_10], r15d
0x180050cc0  mov     rsi, r9
0x180050cc3  mov     r10d, r8d
0x180050cc6  mov     rbp, rdx
0x180050cc9  mov     r11, rcx
0x180050ccc  mov     [rdi], r15
0x180050ccf  cmp     r8d, 0Dh
0x180050cd3  jz      short loc_180050D13
0x180050cd5  cmp     r8d, 0Fh
0x180050cd9  jz      loc_180050E1D
0x180050cdf  lea     eax, [r8-3]; switch 77 cases
0x180050ce3  cmp     eax, 4Ch
0x180050ce6  jbe     loc_180050DA5
0x180050cec  mov     rax, [rbp+10h]; jumptable 0000000180050DC3 default case, cases 4,5,7,10,11,13,15,16,18,20,21,23-26,28,31,33-56,59-65,67-78
0x180050cf0  mov     r8, rsi
0x180050cf3  mov     r9, [rsp+68h+arg_20]
0x180050cfb  mov     edx, r10d
0x180050cfe  mov     rcx, r11
0x180050d01  mov     [rsp+68h+var_48], rdi
0x180050d06  mov     rax, [rax+48h]
0x180050d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d0f  mov     ebx, eax
0x180050d11  jmp     short loc_180050D8D
0x180050d13  lea     rcx, [rdx+4E8h]; lpCriticalSection
0x180050d1a  call    cs:__imp_EnterCriticalSection
0x180050d21  nop     dword ptr [rax+rax+00h]
0x180050d26  lea     rdx, [rbp+148h]
0x180050d2d  mov     [rdi], r15
0x180050d30  test    rdx, rdx
0x180050d33  jz      loc_180051133
0x180050d39  cmp     [rdx+8], r15
0x180050d3d  jz      loc_180051133
0x180050d43  mov     eax, [rdx]
0x180050d45  add     rax, 10h
0x180050d49  mov     [rdi], rax
0x180050d4c  cmp     [rsp+68h+arg_20], rax
0x180050d54  jb      loc_1800510A6
0x180050d5a  movups  xmm0, xmmword ptr [rdx]
0x180050d5d  lea     rdi, [rsi+10h]
0x180050d61  mov     ebx, r15d
0x180050d64  mov     rcx, rdi; void *
0x180050d67  movups  xmmword ptr [rsi], xmm0
0x180050d6a  mov     r8d, [rdx]; Size
0x180050d6d  mov     rdx, [rdx+8]; Src
0x180050d71  call    memcpy_0
0x180050d76  mov     [rsi+8], rdi
0x180050d7a  lea     rcx, [rbp+4E8h]; lpCriticalSection
0x180050d81  call    cs:__imp_LeaveCriticalSection
0x180050d88  nop     dword ptr [rax+rax+00h]
0x180050d8d  test    ebx, ebx
0x180050d8f  jnz     loc_180050EC6
0x180050d95  mov     eax, ebx
0x180050d97  add     rsp, 38h
0x180050d9b  pop     r15
0x180050d9d  pop     r14
0x180050d9f  pop     rdi
0x180050da0  pop     rsi
0x180050da1  pop     rbp
0x180050da2  pop     rbx
0x180050da3  retn
0x180050da5  lea     rdx, __ImageBase
0x180050dac  cdqe
0x180050dae  mov     ebx, r15d
0x180050db1  movzx   eax, ds:(byte_1800514C4 - 180000000h)[rdx+rax]
0x180050db9  mov     ecx, ds:(jpt_180050DC3 - 180000000h)[rdx+rax*4]
0x180050dc0  add     rcx, rdx
0x180050dc3  jmp     rcx; switch jump
0x180050dc9  lea     rcx, [rbp+4E8h]; jumptable 0000000180050DC3 case 22
0x180050dd0  call    cs:__imp_EnterCriticalSection
0x180050dd7  nop     dword ptr [rax+rax+00h]
0x180050ddc  cmp     [rsp+68h+arg_20], 8
0x180050de5  mov     qword ptr [rdi], 8
0x180050dec  jnz     loc_1800511E5
0x180050df2  mov     rcx, [rbp+0E0h]; pChainContext
0x180050df9  test    rcx, rcx
0x180050dfc  jz      loc_1800510D8
0x180050e02  call    cs:__imp_CertDuplicateCertificateChain
0x180050e09  nop     dword ptr [rax+rax+00h]
0x180050e0e  mov     rax, [rbp+0E0h]
0x180050e15  mov     [rsi], rax
0x180050e18  jmp     loc_180050D7A
0x180050e1d  lea     rcx, [rdx+4E8h]; lpCriticalSection
0x180050e24  call    cs:__imp_EnterCriticalSection
0x180050e2b  nop     dword ptr [rax+rax+00h]
0x180050e30  cmp     [rsp+68h+arg_20], 2A8h
0x180050e3c  mov     qword ptr [rdi], 2A8h
0x180050e43  jnz     loc_180051471
0x180050e49  lea     rax, [rbp+174h]
0x180050e50  mov     ecx, 5
0x180050e55  lea     rsi, [rsi+80h]
0x180050e5c  movups  xmm0, xmmword ptr [rax]
0x180050e5f  lea     rax, [rax+80h]
0x180050e66  movups  xmmword ptr [rsi-80h], xmm0
0x180050e6a  movups  xmm1, xmmword ptr [rax-70h]
0x180050e6e  movups  xmmword ptr [rsi-70h], xmm1
0x180050e72  movups  xmm0, xmmword ptr [rax-60h]
0x180050e76  movups  xmmword ptr [rsi-60h], xmm0
0x180050e7a  movups  xmm1, xmmword ptr [rax-50h]
0x180050e7e  movups  xmmword ptr [rsi-50h], xmm1
0x180050e82  movups  xmm0, xmmword ptr [rax-40h]
0x180050e86  movups  xmmword ptr [rsi-40h], xmm0
0x180050e8a  movups  xmm1, xmmword ptr [rax-30h]
0x180050e8e  movups  xmmword ptr [rsi-30h], xmm1
0x180050e92  movups  xmm0, xmmword ptr [rax-20h]
0x180050e96  movups  xmmword ptr [rsi-20h], xmm0
0x180050e9a  movups  xmm1, xmmword ptr [rax-10h]
0x180050e9e  movups  xmmword ptr [rsi-10h], xmm1
0x180050ea2  sub     rcx, 1
0x180050ea6  jnz     short loc_180050E55
0x180050ea8  movups  xmm0, xmmword ptr [rax]
0x180050eab  mov     ebx, r15d
0x180050eae  movups  xmmword ptr [rsi], xmm0
0x180050eb1  movups  xmm1, xmmword ptr [rax+10h]
0x180050eb5  movups  xmmword ptr [rsi+10h], xmm1
0x180050eb9  mov     rax, [rax+20h]
0x180050ebd  mov     [rsi+20h], rax
0x180050ec1  jmp     loc_180050D7A
0x180050ec6  cmp     ebx, 0EAh
0x180050ecc  jz      loc_180050D95
0x180050ed2  cmp     ebx, 3E5h
0x180050ed8  jz      loc_180050D95
0x180050ede  test    byte ptr cs:xmmword_1800AD710, 8
0x180050ee5  jz      loc_180050D95
0x180050eeb  mov     edx, 12h
0x180050ef0  lea     r8, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids
0x180050ef7  mov     ecx, 203h
0x180050efc  mov     r9d, ebx
0x180050eff  call    WPP_SF_d
0x180050f04  jmp     loc_180050D95
0x180050f09  lea     rcx, [rbp+4E8h]; jumptable 0000000180050DC3 case 14
0x180050f10  call    cs:__imp_EnterCriticalSection
0x180050f17  nop     dword ptr [rax+rax+00h]
0x180050f1c  cmp     [rsp+68h+arg_20], 1Ch
0x180050f25  mov     qword ptr [rdi], 1Ch
0x180050f2c  jnz     loc_18005131F
0x180050f32  movups  xmm0, xmmword ptr [rbp+158h]
0x180050f39  movups  xmmword ptr [rsi], xmm0
0x180050f3c  movups  xmm1, xmmword ptr [rbp+164h]
0x180050f43  movups  xmmword ptr [rsi+0Ch], xmm1
0x180050f47  jmp     loc_180050D7A
0x180050f4c  lea     rcx, [rbp+4E8h]; jumptable 0000000180050DC3 case 9
0x180050f53  call    cs:__imp_EnterCriticalSection
0x180050f5a  nop     dword ptr [rax+rax+00h]
0x180050f5f  cmp     [rsp+68h+arg_20], 8
0x180050f68  mov     qword ptr [rdi], 8
0x180050f6f  jnz     loc_1800511DB
0x180050f75  mov     rcx, [rbp+0D8h]; pCertContext
0x180050f7c  test    rcx, rcx
0x180050f7f  jz      loc_1800510D8
0x180050f85  call    cs:__imp_CertDuplicateCertificateContext
0x180050f8c  nop     dword ptr [rax+rax+00h]
0x180050f91  mov     rax, [rbp+0D8h]
0x180050f98  mov     [rsi], rax
0x180050f9b  jmp     loc_180050D7A
0x180050fa0  cmp     [rsp+68h+arg_20], 110h; jumptable 0000000180050DC3 case 57
0x180050fac  mov     qword ptr [rdi], 110h
0x180050fb3  jnz     loc_1800510C3
0x180050fb9  movups  xmm0, xmmword ptr [rbp+470h]
0x180050fc0  mov     r8, rsi
0x180050fc3  mov     [rsp+68h+var_48], rdi
0x180050fc8  mov     edx, r10d
0x180050fcb  mov     rcx, r11
0x180050fce  movups  xmmword ptr [r9+38h], xmm0
0x180050fd3  movups  xmm1, xmmword ptr [rbp+480h]
0x180050fda  movups  xmmword ptr [r9+48h], xmm1
0x180050fdf  movups  xmm0, xmmword ptr [rbp+490h]
0x180050fe6  movups  xmmword ptr [r9+58h], xmm0
0x180050feb  mov     rax, [rbp+10h]
0x180050fef  mov     r9d, 110h
0x180050ff5  mov     rax, [rax+48h]
0x180050ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ffe  mov     ebx, eax
0x180051000  jmp     loc_180050D8D
0x180051005  cmp     [rsp+68h+arg_20], 98h; jumptable 0000000180050DC3 case 58
0x180051011  mov     qword ptr [rdi], 98h
0x180051018  jnz     loc_1800510C3
0x18005101e  movups  xmm0, xmmword ptr [rbp+4A0h]
0x180051025  mov     r8, rsi
0x180051028  mov     [rsp+68h+var_48], rdi
0x18005102d  mov     edx, r10d
0x180051030  mov     rcx, r11
0x180051033  movups  xmmword ptr [r9+18h], xmm0
0x180051038  movups  xmm1, xmmword ptr [rbp+4B0h]
0x18005103f  movups  xmmword ptr [r9+28h], xmm1
0x180051044  movsd   xmm0, qword ptr [rbp+4C0h]
0x18005104c  movsd   qword ptr [r9+38h], xmm0
0x180051052  mov     r9d, 98h
0x180051058  mov     rax, [rbp+10h]
0x18005105c  mov     rax, [rax+48h]
0x180051060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051065  mov     ebx, eax
0x180051067  jmp     loc_180050D8D
0x18005106c  lea     rcx, [rbp+4E8h]; jumptable 0000000180050DC3 case 19
0x180051073  call    cs:__imp_EnterCriticalSection
0x18005107a  nop     dword ptr [rax+rax+00h]
0x18005107f  cmp     [rsp+68h+arg_20], 4
0x180051088  mov     qword ptr [rdi], 4
0x18005108f  jnz     short loc_1800510E5
0x180051091  cmp     [rbp+4DBh], bl
0x180051097  jnz     short loc_1800510B0
0x180051099  mov     [rsi], r15d
0x18005109c  mov     ebx, 490h
0x1800510a1  jmp     loc_180050D7A
0x1800510a6  mov     ebx, 0EAh
0x1800510ab  jmp     loc_180050D7A
0x1800510b0  cmp     [rbp+4DAh], bl
0x1800510b6  jz      short loc_180051099
0x1800510b8  mov     dword ptr [rsi], 1
0x1800510be  jmp     loc_180050D7A
0x1800510c3  mov     ebx, 0EAh
0x1800510c8  mov     eax, ebx
0x1800510ca  add     rsp, 38h
0x1800510ce  pop     r15
0x1800510d0  pop     r14
0x1800510d2  pop     rdi
0x1800510d3  pop     rsi
0x1800510d4  pop     rbp
0x1800510d5  pop     rbx
0x1800510d6  retn
0x1800510d8  mov     [rsi], r15
0x1800510db  mov     ebx, 490h
0x1800510e0  jmp     loc_180050D7A
0x1800510e5  mov     ebx, 0EAh
0x1800510ea  jmp     loc_180050D7A
0x1800510ef  lea     rcx, [rbp+4E8h]; jumptable 0000000180050DC3 case 17
0x1800510f6  call    cs:__imp_EnterCriticalSection
0x1800510fd  nop     dword ptr [rax+rax+00h]
0x180051102  cmp     [rsp+68h+arg_20], 4
0x18005110b  mov     qword ptr [rdi], 4
0x180051112  jnz     short loc_180051129
0x180051114  cmp     [rbp+428h], bl
0x18005111a  jz      short loc_1800510DB
0x18005111c  mov     eax, [rbp+424h]
0x180051122  mov     [rsi], eax
0x180051124  jmp     loc_180050D7A
0x180051129  mov     ebx, 0EAh
0x18005112e  jmp     loc_180050D7A
0x180051133  test    byte ptr cs:xmmword_1800AD710, 8
0x18005113a  mov     ebx, 490h
0x18005113f  jz      loc_180050D7A
0x180051145  mov     edx, 1Ch
0x18005114a  mov     r9d, ebx
0x18005114d  lea     r8, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids
0x180051154  mov     ecx, 203h
0x180051159  call    WPP_SF_d
0x18005115e  jmp     loc_180050D7A
0x180051163  lea     rcx, [rbp+4E8h]; jumptable 0000000180050DC3 case 3
0x18005116a  call    cs:__imp_EnterCriticalSection
0x180051171  nop     dword ptr [rax+rax+00h]
0x180051176  cmp     [rsp+68h+arg_20], 4
0x18005117f  mov     qword ptr [rdi], 4
0x180051186  jz      short loc_180051192
0x180051188  mov     ebx, 0EAh
0x18005118d  jmp     loc_180050D7A
0x180051192  mov     eax, [rbp+0CCh]
0x180051198  mov     [rsi], eax
0x18005119a  jmp     loc_180050D7A
0x18005119f  lea     rcx, [rbp+4E8h]; jumptable 0000000180050DC3 case 8
0x1800511a6  call    cs:__imp_EnterCriticalSection
0x1800511ad  nop     dword ptr [rax+rax+00h]
0x1800511b2  cmp     [rsp+68h+arg_20], 4
0x1800511bb  mov     qword ptr [rdi], 4
0x1800511c2  jz      short loc_1800511CE
0x1800511c4  mov     ebx, 0EAh
0x1800511c9  jmp     loc_180050D7A
0x1800511ce  mov     eax, [rbp+0E8h]
0x1800511d4  mov     [rsi], eax
0x1800511d6  jmp     loc_180050D7A
0x1800511db  mov     ebx, 0EAh
0x1800511e0  jmp     loc_180050D7A
0x1800511e5  mov     ebx, 0EAh
0x1800511ea  jmp     loc_180050D7A
0x1800511ef  lea     rcx, [rbp+4E8h]; jumptable 0000000180050DC3 case 6
0x1800511f6  call    cs:__imp_EnterCriticalSection
0x1800511fd  nop     dword ptr [rax+rax+00h]
0x180051202  cmp     [rsp+68h+arg_20], 4
0x18005120b  mov     qword ptr [rdi], 4
0x180051212  jz      short loc_18005121E
0x180051214  mov     ebx, 0EAh
0x180051219  jmp     loc_180050D7A
0x18005121e  mov     eax, [rbp+420h]
0x180051224  mov     [rsi], eax
0x180051226  jmp     loc_180050D7A
0x18005122b  lea     rcx, [rbp+4E8h]; jumptable 0000000180050DC3 case 32
0x180051232  call    cs:__imp_EnterCriticalSection
0x180051239  nop     dword ptr [rax+rax+00h]
0x18005123e  cmp     [rsp+68h+arg_20], 8
0x180051247  mov     qword ptr [rdi], 8
0x18005124e  jz      short loc_18005125A
0x180051250  mov     ebx, 0EAh
0x180051255  jmp     loc_180050D7A
  ... truncated ...
```
