# SpWow64MapVersion3Certificate(void *,ulong,_SecBuffer *,LSA_SCHANNEL_CRED *)

- ea: `0x18005cf90`
- end: `0x18005d3ee`
- name: `?SpWow64MapVersion3Certificate@@YAJPEAXKPEAU_SecBuffer@@PEAULSA_SCHANNEL_CRED@@@Z`
- size: `1118`
- prototype: `int(void *, unsigned int, struct _SecBuffer *, struct LSA_SCHANNEL_CRED *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002b800`

## callees

- `0x180011f40`
- `0x180012d10`
- `0x180021eb0`
- `0x18002acc0`
- `0x180057c8c`
- `0x1800597b0`
- `0x18005a160`
- `0x18005cf90`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d15e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d22e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d15e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d22e`
- `CRYPT32!CertOpenStore` at `0x18005d14c`
- `CRYPT32!CertOpenStore` at `0x18005d2a7`
- `CRYPT32!CertOpenStore` at `0x18005d14c`
- `CRYPT32!CertOpenStore` at `0x18005d2a7`
- `CRYPT32!CertCloseStore` at `0x18005d3b1`
- `CRYPT32!CertCloseStore` at `0x18005d3b1`
- `CRYPT32!CertAddSerializedElementToStore` at `0x18005d20f`
- `CRYPT32!CertAddSerializedElementToStore` at `0x18005d20f`

## pseudocode

```c
__int64 __fastcall SpWow64MapVersion3Certificate(void *a1, int a2, struct _SecBuffer *a3, struct LSA_SCHANNEL_CRED *a4)
{
  void *v4; // r13
  int v8; // ebx
  __int64 v9; // rdx
  unsigned int v10; // r14d
  int v11; // eax
  int v12; // r12d
  unsigned int *pvBuffer; // rbx
  unsigned int cbBuffer; // esi
  void *v15; // rax
  void *v16; // r10
  __int64 i; // rax
  __int64 v18; // r13
  unsigned int v19; // esi
  unsigned int *v20; // r12
  __int64 ppvContext; // r9
  DWORD v22; // r8d
  __int64 v23; // rcx
  HCERTSTORE v24; // rax
  int v25; // r15d
  int v26; // eax
  int v27; // eax
  unsigned int v28; // ebx
  void *v29; // rax
  unsigned int v30; // ecx
  HCERTSTORE v32; // [rsp+40h] [rbp-49h]
  int v33; // [rsp+48h] [rbp-41h]
  int v34; // [rsp+4Ch] [rbp-3Dh]
  __int128 pvPara; // [rsp+58h] [rbp-31h] BYREF
  __int128 v37; // [rsp+68h] [rbp-21h] BYREF
  __int128 v38; // [rsp+78h] [rbp-11h]
  unsigned int v39[4]; // [rsp+88h] [rbp-1h]
  __int64 v40; // [rsp+98h] [rbp+Fh]

  v4 = 0;
  v40 = 0;
  pvPara = 0;
  v37 = 0;
  v38 = 0;
  *(_OWORD *)v39 = 0;
  if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
  if ( a2 == 3 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, void *))(LsaTable + 80))(0, 48, &v37, a1);
    if ( v8 < 0 )
      goto LABEL_66;
    v40 = 0;
  }
  else
  {
    v9 = 56;
    if ( a2 != 4 )
      v9 = 44;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, void *))(LsaTable + 80))(0, v9, &v37, a1);
    if ( v8 < 0 )
      goto LABEL_66;
  }
  memset_0((char *)a4 + 4, 0, 0x6Cu);
  *(_DWORD *)a4 = a2;
  if ( (unsigned int)(a2 - 3) <= 1 )
  {
    v10 = DWORD1(v37);
    v11 = DWORD2(v37);
    v12 = HIDWORD(v37);
  }
  else
  {
    v10 = DWORD2(v37);
    v11 = HIDWORD(v37);
    v12 = v38;
  }
  v34 = v12;
  if ( v10 > 0x64 )
    goto LABEL_14;
  pvBuffer = (unsigned int *)a3->pvBuffer;
  if ( pvBuffer )
  {
    cbBuffer = a3->cbBuffer;
  }
  else
  {
    if ( v10 && v11 || v12 )
    {
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids);
      v8 = 590610;
      goto LABEL_66;
    }
    cbBuffer = 0;
  }
  if ( !v10 || !v11 )
    goto LABEL_43;
  *((_DWORD *)a4 + 1) = v10;
  v15 = SPExternalAlloc(56 * v10);
  *((_QWORD *)a4 + 1) = v15;
  if ( !v15 )
    goto LABEL_14;
  v32 = CertOpenStore((LPCSTR)2, 0, 0, 4u, 0);
  v16 = v32;
  if ( v32 )
  {
    for ( i = 0; ; i = (unsigned int)(v33 + 1) )
    {
      v33 = i;
      if ( (unsigned int)i >= v10 )
        break;
      if ( cbBuffer < 4 )
        goto LABEL_41;
      v18 = *pvBuffer;
      v19 = cbBuffer - 4;
      if ( v19 < (unsigned int)v18
        || (v20 = pvBuffer + 1, pvBuffer == (unsigned int *)-4LL)
        || (unsigned int)v18 < 0x10
        || (ppvContext = *((_QWORD *)a4 + 1) + 56 * i,
            *(_QWORD *)(ppvContext + 16) = *v20,
            *(_BYTE *)(ppvContext + 24) = pvBuffer[2] != 0,
            *(_QWORD *)(ppvContext + 32) = pvBuffer[3],
            v22 = pvBuffer[4],
            (int)v18 - 16 < v22) )
      {
LABEL_41:
        v8 = -2146893052;
        goto LABEL_30;
      }
      if ( !CertAddSerializedElementToStore(
              v16,
              (const BYTE *)pvBuffer + 20,
              v22,
              4u,
              0,
              2u,
              0,
              (const void **)ppvContext) )
      {
        GetLastError();
        v8 = -2146893043;
        goto LABEL_30;
      }
      pvBuffer = (unsigned int *)((char *)v20 + v18);
      v16 = v32;
      cbBuffer = v19 - v18;
    }
    v12 = v34;
    v4 = v32;
LABEL_43:
    if ( v12 )
    {
      if ( cbBuffer < 4
        || (v23 = *pvBuffer, cbBuffer - 4 < (unsigned int)v23)
        || pvBuffer == (unsigned int *)-4LL
        || (unsigned int)v23 < 4
        || (LODWORD(pvPara) = pvBuffer[1],
            *((_QWORD *)&pvPara + 1) = pvBuffer + 2,
            v23 - 4 < (unsigned __int64)(unsigned int)pvPara) )
      {
        v8 = -2146893052;
        goto LABEL_66;
      }
      v24 = CertOpenStore((LPCSTR)6, 1u, 0, 0, &pvPara);
      *((_QWORD *)a4 + 2) = v24;
      if ( !v24 )
      {
        v8 = -2146893043;
        goto LABEL_66;
      }
    }
    v25 = a2 - 4;
    if ( v25 )
    {
      if ( v25 != 1 )
      {
LABEL_65:
        v8 = 0;
        goto LABEL_66;
      }
      v8 = CopyTlsParameters(0, v39[1], v39[2], 1u, (struct _TLS_PARAMETERS **)a4 + 13, (unsigned int *)a4 + 24);
      if ( v8 )
        goto LABEL_66;
      *((_DWORD *)a4 + 21) = HIDWORD(v38);
      *((_DWORD *)a4 + 22) = v39[0];
      v26 = DWORD1(v37);
LABEL_64:
      *((_DWORD *)a4 + 23) = v26;
      goto LABEL_65;
    }
    v27 = DWORD2(v38);
    if ( !DWORD2(v38) || !HIDWORD(v38) )
    {
LABEL_61:
      v30 = v39[0];
      if ( v39[0] == -1 )
        v30 = 0;
      *((_DWORD *)a4 + 19) = v39[1];
      *((_DWORD *)a4 + 20) = v39[2];
      *((_DWORD *)a4 + 21) = v39[3];
      *((_DWORD *)a4 + 22) = v40;
      v26 = HIDWORD(v40);
      *((_DWORD *)a4 + 18) = v30 & 0x3FFFFFFF;
      goto LABEL_64;
    }
    if ( DWORD2(v38) <= 0x100 )
    {
      v28 = 4 * DWORD2(v38);
      *((_DWORD *)a4 + 14) = DWORD2(v38);
      v29 = SPExternalAlloc((unsigned int)(4 * v27));
      *((_QWORD *)a4 + 8) = v29;
      if ( v29 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void *, _QWORD))(LsaTable + 80))(0, v28, v29, HIDWORD(v38));
        if ( v8 < 0 )
          goto LABEL_66;
        goto LABEL_61;
      }
    }
LABEL_14:
    v8 = -2146893056;
    goto LABEL_66;
  }
  GetLastError();
  v8 = -2146893056;
LABEL_30:
  v4 = v32;
LABEL_66:
  CleanupAppModeInfo(0, a3);
  if ( v4 )
    CertCloseStore(v4, 0);
  if ( v8 < 0 )
    FreeSchannelCred(a4, 1u);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18005cf90  mov     [rsp-8+arg_8], rbx
0x18005cf95  push    rbp
0x18005cf96  push    rsi
0x18005cf97  push    rdi
0x18005cf98  push    r12
0x18005cf9a  push    r13
0x18005cf9c  push    r14
0x18005cf9e  push    r15
0x18005cfa0  lea     rbp, [rsp-27h]
0x18005cfa5  sub     rsp, 0B0h
0x18005cfac  mov     rax, cs:__security_cookie
0x18005cfb3  xor     rax, rsp
0x18005cfb6  mov     [rbp+57h+var_40], rax
0x18005cfba  xorps   xmm1, xmm1
0x18005cfbd  mov     [rbp+57h+var_90], r8
0x18005cfc1  xor     r13d, r13d
0x18005cfc4  xorps   xmm0, xmm0
0x18005cfc7  xor     eax, eax
0x18005cfc9  mov     rdi, r9
0x18005cfcc  mov     [rbp+57h+var_48], rax
0x18005cfd0  mov     r15d, edx
0x18005cfd3  mov     rbx, rcx
0x18005cfd6  movups  [rbp+57h+var_88], xmm0
0x18005cfda  movups  [rbp+57h+var_78], xmm1
0x18005cfde  movups  [rbp+57h+var_68], xmm1
0x18005cfe2  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x18005cfe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cfed  lea     rsi, WPP_GLOBAL_Control
0x18005cff4  cmp     rcx, rsi
0x18005cff7  jz      short loc_18005D012
0x18005cff9  test    byte ptr [rcx+1Ch], 20h
0x18005cffd  jz      short loc_18005D012
0x18005cfff  mov     rcx, [rcx+10h]
0x18005d003  lea     edx, [rax+14h]
0x18005d006  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18005d00d  call    WPP_SF_
0x18005d012  lea     r8, [rbp+57h+var_78]
0x18005d016  mov     r9, rbx
0x18005d019  cmp     r15d, 3
0x18005d01d  jnz     short loc_18005D045
0x18005d01f  mov     rax, cs:LsaTable
0x18005d026  lea     edx, [r15+2Dh]
0x18005d02a  xor     ecx, ecx
0x18005d02c  mov     rax, [rax+50h]
0x18005d030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d035  mov     ebx, eax
0x18005d037  test    eax, eax
0x18005d039  js      loc_18005D39C
0x18005d03f  mov     [rbp+57h+var_48], r13
0x18005d043  jmp     short loc_18005D070
0x18005d045  mov     edx, 38h ; '8'
0x18005d04a  cmp     r15d, 4
0x18005d04e  lea     eax, [rdx-0Ch]
0x18005d051  cmovnz  edx, eax
0x18005d054  mov     rax, cs:LsaTable
0x18005d05b  xor     ecx, ecx
0x18005d05d  mov     rax, [rax+50h]
0x18005d061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d066  mov     ebx, eax
0x18005d068  test    eax, eax
0x18005d06a  js      loc_18005D39C
0x18005d070  xor     edx, edx; Val
0x18005d072  lea     rcx, [rdi+4]; void *
0x18005d076  lea     r8d, [rdx+6Ch]; Size
0x18005d07a  call    memset_0
0x18005d07f  lea     eax, [r15-3]
0x18005d083  mov     [rdi], r15d
0x18005d086  cmp     eax, 1
0x18005d089  jbe     short loc_18005D098
0x18005d08b  mov     r14d, dword ptr [rbp+57h+var_78+8]
0x18005d08f  mov     eax, dword ptr [rbp+57h+var_78+0Ch]
0x18005d092  mov     r12d, dword ptr [rbp+57h+var_68]
0x18005d096  jmp     short loc_18005D0A3
0x18005d098  mov     r14d, dword ptr [rbp+57h+var_78+4]
0x18005d09c  mov     eax, dword ptr [rbp+57h+var_78+8]
0x18005d09f  mov     r12d, dword ptr [rbp+57h+var_78+0Ch]
0x18005d0a3  mov     [rbp+57h+var_94], r12d
0x18005d0a7  cmp     r14d, 64h ; 'd'
0x18005d0ab  jbe     short loc_18005D0B7
0x18005d0ad  mov     ebx, 80090300h
0x18005d0b2  jmp     loc_18005D39C
0x18005d0b7  mov     rcx, [rbp+57h+var_90]
0x18005d0bb  mov     rbx, [rcx+8]
0x18005d0bf  test    rbx, rbx
0x18005d0c2  jnz     short loc_18005D108
0x18005d0c4  test    r14d, r14d
0x18005d0c7  jz      short loc_18005D0CD
0x18005d0c9  test    eax, eax
0x18005d0cb  jnz     short loc_18005D0D2
0x18005d0cd  test    r12d, r12d
0x18005d0d0  jz      short loc_18005D103
0x18005d0d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d0d9  cmp     rcx, rsi
0x18005d0dc  jz      short loc_18005D0F9
0x18005d0de  test    byte ptr [rcx+1Ch], 4
0x18005d0e2  jz      short loc_18005D0F9
0x18005d0e4  mov     rcx, [rcx+10h]
0x18005d0e8  lea     r8, WPP_76bc67c2eec53f46259ed5dc696c8d2c_Traceguids
0x18005d0ef  mov     edx, 17h
0x18005d0f4  call    WPP_SF_
0x18005d0f9  mov     ebx, 90312h
0x18005d0fe  jmp     loc_18005D39C
0x18005d103  test    rbx, rbx
0x18005d106  jz      short loc_18005D10C
0x18005d108  mov     esi, [rcx]
0x18005d10a  jmp     short loc_18005D10E
0x18005d10c  xor     esi, esi
0x18005d10e  test    r14d, r14d
0x18005d111  jz      loc_18005D250
0x18005d117  test    eax, eax
0x18005d119  jz      loc_18005D250
0x18005d11f  imul    ecx, r14d, 38h ; '8'; uBytes
0x18005d123  mov     [rdi+4], r14d
0x18005d127  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18005d12c  mov     [rdi+8], rax
0x18005d130  test    rax, rax
0x18005d133  jz      loc_18005D0AD
0x18005d139  xor     edx, edx; dwEncodingType
0x18005d13b  mov     [rsp+0E0h+pvPara], r13; pvPara
0x18005d140  mov     r9d, 4; dwFlags
0x18005d146  xor     r8d, r8d; hCryptProv
0x18005d149  lea     ecx, [rdx+2]; lpszStoreProvider
0x18005d14c  call    cs:__imp_CertOpenStore
0x18005d152  mov     [rbp+57h+var_A0], rax
0x18005d156  mov     r10, rax
0x18005d159  test    rax, rax
0x18005d15c  jnz     short loc_18005D172
0x18005d15e  call    cs:__imp_GetLastError
0x18005d164  mov     ebx, 80090300h
0x18005d169  mov     r13, [rbp+57h+var_A0]
0x18005d16d  jmp     loc_18005D39C
0x18005d172  xor     eax, eax
0x18005d174  mov     [rbp+57h+var_98], eax
0x18005d177  cmp     eax, r14d
0x18005d17a  jnb     loc_18005D248
0x18005d180  cmp     esi, 4
0x18005d183  jb      loc_18005D23E
0x18005d189  mov     r13d, [rbx]
0x18005d18c  add     esi, 0FFFFFFFCh
0x18005d18f  cmp     esi, r13d
0x18005d192  jb      loc_18005D23E
0x18005d198  lea     r12, [rbx+4]
0x18005d19c  test    r12, r12
0x18005d19f  jz      loc_18005D23E
0x18005d1a5  cmp     r13d, 10h
0x18005d1a9  jb      loc_18005D23E
0x18005d1af  imul    r9, rax, 38h ; '8'
0x18005d1b3  mov     eax, [r12]
0x18005d1b7  add     r9, [rdi+8]
0x18005d1bb  mov     [r9+10h], rax
0x18005d1bf  cmp     dword ptr [r12+4], 0
0x18005d1c5  setnz   al
0x18005d1c8  mov     [r9+18h], al
0x18005d1cc  mov     eax, [r12+8]
0x18005d1d1  mov     [r9+20h], rax
0x18005d1d5  lea     eax, [r13-10h]
0x18005d1d9  mov     r8d, [r12+0Ch]; cbElement
0x18005d1de  cmp     eax, r8d
0x18005d1e1  jb      short loc_18005D23E
0x18005d1e3  mov     [rsp+0E0h+ppvContext], r9; ppvContext
0x18005d1e8  lea     rdx, [r12+10h]; pbElement
0x18005d1ed  mov     [rsp+0E0h+pdwContextType], 0; pdwContextType
0x18005d1f6  mov     r9d, 4; dwAddDisposition
0x18005d1fc  mov     [rsp+0E0h+dwContextTypeFlags], 2; dwContextTypeFlags
0x18005d204  mov     rcx, r10; hCertStore
0x18005d207  mov     dword ptr [rsp+0E0h+pvPara], 0; dwFlags
0x18005d20f  call    cs:__imp_CertAddSerializedElementToStore
0x18005d215  test    eax, eax
0x18005d217  jz      short loc_18005D22E
0x18005d219  mov     eax, [rbp+57h+var_98]
0x18005d21c  lea     rbx, [r12+r13]
0x18005d220  mov     r10, [rbp+57h+var_A0]
0x18005d224  sub     esi, r13d
0x18005d227  inc     eax
0x18005d229  jmp     loc_18005D174
0x18005d22e  call    cs:__imp_GetLastError
0x18005d234  mov     ebx, 8009030Dh
0x18005d239  jmp     loc_18005D169
0x18005d23e  mov     ebx, 80090304h
0x18005d243  jmp     loc_18005D169
0x18005d248  mov     r12d, [rbp+57h+var_94]
0x18005d24c  mov     r13, [rbp+57h+var_A0]
0x18005d250  test    r12d, r12d
0x18005d253  jz      short loc_18005D2C0
0x18005d255  cmp     esi, 4
0x18005d258  jnb     short loc_18005D264
0x18005d25a  mov     ebx, 80090304h
0x18005d25f  jmp     loc_18005D39C
0x18005d264  mov     ecx, [rbx]
0x18005d266  lea     eax, [rsi-4]
0x18005d269  cmp     eax, ecx
0x18005d26b  jb      short loc_18005D25A
0x18005d26d  lea     rax, [rbx+4]
0x18005d271  test    rax, rax
0x18005d274  jz      short loc_18005D25A
0x18005d276  cmp     ecx, 4
0x18005d279  jb      short loc_18005D25A
0x18005d27b  mov     edx, [rax]
0x18005d27d  sub     rcx, 4
0x18005d281  add     rax, 4
0x18005d285  mov     dword ptr [rbp+57h+var_88], edx
0x18005d288  mov     qword ptr [rbp+57h+var_88+8], rax
0x18005d28c  cmp     rcx, rdx
0x18005d28f  jb      short loc_18005D25A
0x18005d291  xor     r9d, r9d; dwFlags
0x18005d294  lea     rax, [rbp+57h+var_88]
0x18005d298  xor     r8d, r8d; hCryptProv
0x18005d29b  mov     [rsp+0E0h+pvPara], rax; pvPara
0x18005d2a0  lea     edx, [r9+1]; dwEncodingType
0x18005d2a4  lea     ecx, [rdx+5]; lpszStoreProvider
0x18005d2a7  call    cs:__imp_CertOpenStore
0x18005d2ad  mov     [rdi+10h], rax
0x18005d2b1  test    rax, rax
0x18005d2b4  jnz     short loc_18005D2C0
0x18005d2b6  mov     ebx, 8009030Dh
0x18005d2bb  jmp     loc_18005D39C
0x18005d2c0  sub     r15d, 4
0x18005d2c4  jz      short loc_18005D311
0x18005d2c6  cmp     r15d, 1
0x18005d2ca  jnz     loc_18005D39A
0x18005d2d0  mov     r8d, [rbp+57h+var_58+8]; unsigned int
0x18005d2d4  lea     rax, [rdi+60h]
0x18005d2d8  mov     edx, [rbp+57h+var_58+4]; unsigned int
0x18005d2db  lea     rcx, [rdi+68h]
0x18005d2df  mov     qword ptr [rsp+0E0h+dwContextTypeFlags], rax; unsigned int *
0x18005d2e4  mov     r9b, r15b; unsigned __int8
0x18005d2e7  mov     [rsp+0E0h+pvPara], rcx; struct _TLS_PARAMETERS **
0x18005d2ec  xor     ecx, ecx; struct _TLS_PARAMETERS *
0x18005d2ee  call    ?CopyTlsParameters@@YAJPEAU_TLS_PARAMETERS@@KKEPEAPEAU1@PEAK@Z; CopyTlsParameters(_TLS_PARAMETERS *,ulong,ulong,uchar,_TLS_PARAMETERS * *,ulong *)
0x18005d2f3  mov     ebx, eax
0x18005d2f5  test    eax, eax
0x18005d2f7  jnz     loc_18005D39C
0x18005d2fd  mov     eax, dword ptr [rbp+57h+var_68+0Ch]
0x18005d300  mov     [rdi+54h], eax
0x18005d303  mov     eax, [rbp+57h+var_58]
0x18005d306  mov     [rdi+58h], eax
0x18005d309  mov     eax, dword ptr [rbp+57h+var_78+4]
0x18005d30c  jmp     loc_18005D397
0x18005d311  mov     eax, dword ptr [rbp+57h+var_68+8]
0x18005d314  test    eax, eax
0x18005d316  jz      short loc_18005D368
0x18005d318  cmp     dword ptr [rbp+57h+var_68+0Ch], 0
0x18005d31c  jz      short loc_18005D368
0x18005d31e  cmp     eax, 100h
0x18005d323  ja      loc_18005D0AD
0x18005d329  lea     ebx, ds:0[rax*4]
0x18005d330  mov     [rdi+38h], eax
0x18005d333  mov     ecx, ebx; uBytes
0x18005d335  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x18005d33a  mov     [rdi+40h], rax
0x18005d33e  mov     r8, rax
0x18005d341  test    rax, rax
0x18005d344  jz      loc_18005D0AD
0x18005d34a  mov     rax, cs:LsaTable
0x18005d351  mov     edx, ebx
0x18005d353  mov     r9d, dword ptr [rbp+57h+var_68+0Ch]
0x18005d357  xor     ecx, ecx
0x18005d359  mov     rax, [rax+50h]
0x18005d35d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d362  mov     ebx, eax
0x18005d364  test    eax, eax
0x18005d366  js      short loc_18005D39C
0x18005d368  mov     ecx, [rbp+57h+var_58]
0x18005d36b  xor     eax, eax
0x18005d36d  cmp     ecx, 0FFFFFFFFh
0x18005d370  cmovz   ecx, eax
0x18005d373  mov     eax, [rbp+57h+var_58+4]
0x18005d376  mov     [rdi+4Ch], eax
0x18005d379  and     ecx, 3FFFFFFFh
0x18005d37f  mov     eax, [rbp+57h+var_58+8]
0x18005d382  mov     [rdi+50h], eax
0x18005d385  mov     eax, [rbp+57h+var_58+0Ch]
0x18005d388  mov     [rdi+54h], eax
0x18005d38b  mov     eax, dword ptr [rbp+57h+var_48]
0x18005d38e  mov     [rdi+58h], eax
0x18005d391  mov     eax, dword ptr [rbp+57h+var_48+4]
0x18005d394  mov     [rdi+48h], ecx
0x18005d397  mov     [rdi+5Ch], eax
0x18005d39a  xor     ebx, ebx
0x18005d39c  mov     rdx, [rbp+57h+var_90]
0x18005d3a0  xor     ecx, ecx
0x18005d3a2  call    ?CleanupAppModeInfo@@YAXW4_UserDataCleanupAction@@PEAU_SecBuffer@@@Z; CleanupAppModeInfo(_UserDataCleanupAction,_SecBuffer *)
0x18005d3a7  test    r13, r13
0x18005d3aa  jz      short loc_18005D3B7
0x18005d3ac  xor     edx, edx; dwFlags
0x18005d3ae  mov     rcx, r13; hCertStore
0x18005d3b1  call    cs:__imp_CertCloseStore
0x18005d3b7  test    ebx, ebx
0x18005d3b9  jns     short loc_18005D3C5
0x18005d3bb  mov     dl, 1; unsigned __int8
0x18005d3bd  mov     rcx, rdi; struct LSA_SCHANNEL_CRED *
0x18005d3c0  call    ?FreeSchannelCred@@YAXPEAULSA_SCHANNEL_CRED@@E@Z; FreeSchannelCred(LSA_SCHANNEL_CRED *,uchar)
0x18005d3c5  mov     eax, ebx
0x18005d3c7  mov     rcx, [rbp+57h+var_40]
0x18005d3cb  xor     rcx, rsp; StackCookie
0x18005d3ce  call    __security_check_cookie
0x18005d3d3  mov     rbx, [rsp+0E0h+arg_8]
0x18005d3db  add     rsp, 0B0h
0x18005d3e2  pop     r15
0x18005d3e4  pop     r14
  ... truncated ...
```
