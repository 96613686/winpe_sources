# GetResourcesFromMsg

- ea: `0x180027dac`
- end: `0x180028015`
- name: `GetResourcesFromMsg`
- size: `617`
- prototype: `__int64 __fastcall(HCRYPTMSG hCryptMsg)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800268a0`
- `0x180040d58`

## callees

- `0x180027dac`
- `0x18002ae70`
- `0x18002c090`
- `0x18002c1b4`
- `0x18002c394`
- `0x18002d060`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027e3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027ea5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027e3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027ea5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027ee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027fc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027ee0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027f9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027fc1`
- `CRYPT32!CryptMsgGetParam` at `0x180027df9`
- `CRYPT32!CryptMsgGetParam` at `0x180027e7a`
- `CRYPT32!CryptMsgGetParam` at `0x180027df9`
- `CRYPT32!CryptMsgGetParam` at `0x180027e7a`

## string_xrefs

- `0x180027e88`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x180027ebb`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x180027f87`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`
- `0x180027fcd`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall GetResourcesFromMsg(HCRYPTMSG hCryptMsg, _QWORD *a2)
{
  DWORD LastError; // eax
  unsigned int v5; // r8d
  unsigned int v6; // ebx
  __int64 v7; // rsi
  _BYTE *v8; // rax
  _QWORD *v9; // rbx
  _BYTE *i; // rcx
  void *v11; // r15
  const char *v12; // r9
  char *v13; // r8
  __int64 v14; // r14
  __int64 j; // rsi
  __int64 v16; // r10
  char *v17; // rax
  __int64 v18; // r9
  int v19; // edx
  int v20; // ecx
  int v21; // eax
  unsigned int v22; // edi
  __int64 v23; // r9
  __int64 v24; // rdx
  unsigned int pcbData; // [rsp+20h] [rbp-10h]
  int pcbDataa; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  DWORD v29; // [rsp+60h] [rbp+30h] BYREF
  char *v30; // [rsp+70h] [rbp+40h] BYREF

  v29 = 0;
  v30 = 0;
  if ( !hCryptMsg )
  {
LABEL_34:
    SIPolicyFreeResources(&v30);
    return 0;
  }
  if ( !CryptMsgGetParam(hCryptMsg, 9u, 0, 0, &v29) )
  {
    LastError = GetLastError();
    if ( LastError != -2146889713 && LastError )
    {
      v6 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x8D1, v5, (const char *)LastError, pcbData);
LABEL_32:
      SIPolicyFreeResources(&v30);
      return v6;
    }
    goto LABEL_34;
  }
  v7 = v29;
  v8 = LocalAlloc(0, v29);
  v9 = v8;
  if ( !v8 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D5,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
      (const char *)0x8007000ELL,
      pcbData);
    goto LABEL_32;
  }
  for ( i = &v8[v7]; v8 != i; ++v8 )
    *v8 = 0;
  v11 = v9;
  if ( !CryptMsgGetParam(hCryptMsg, 9u, 0, v9, &v29) )
  {
    v6 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x8DB,
           (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
           v12);
LABEL_13:
    SIPolicyFreeResources(&v30);
    LocalFree(v11);
    return v6;
  }
  v30 = (char *)LocalAlloc(0x40u, 0x48u);
  v13 = v30;
  if ( !v30 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E0,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
      (const char *)0x8007000ELL,
      pcbDataa);
    goto LABEL_13;
  }
  v14 = 0;
LABEL_15:
  if ( (unsigned int)v14 >= *(_DWORD *)v9 )
  {
    *a2 = v13;
    v30 = 0;
    SIPolicyFreeResources(&v30);
    LocalFree(v9);
    return 0;
  }
  for ( j = 0; ; j = (unsigned int)(j + 1) )
  {
    if ( (unsigned int)j >= 5 )
    {
      v14 = (unsigned int)(v14 + 1);
      goto LABEL_15;
    }
    v16 = v9[1] + 24 * v14;
    v17 = (&off_180052770)[3 * j];
    v18 = *(_QWORD *)v16 - (_QWORD)v17;
    do
    {
      v19 = (unsigned __int8)v17[v18];
      v20 = (unsigned __int8)*v17 - v19;
      if ( v20 )
        break;
      ++v17;
    }
    while ( v19 );
    if ( v20 )
      continue;
    if ( *(_DWORD *)(v16 + 8) != 1 )
      break;
    v21 = ((__int64 (__fastcall *)(__int64, char *))*(&funcs_180027F4D + 3 * j))(
            v9[1] + 24 * v14,
            &v13[LODWORD((&off_180052770)[3 * j + 1])]);
    v22 = v21;
    if ( v21 < 0 )
    {
      v23 = (unsigned int)v21;
      v24 = 2288;
      goto LABEL_29;
    }
    v13 = v30;
  }
  v22 = -2147418113;
  v24 = 2283;
  v23 = 2147549183LL;
LABEL_29:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v24,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
    (const char *)v23,
    pcbDataa);
  SIPolicyFreeResources(&v30);
  LocalFree(v9);
  return v22;
}

```

## disassembly

```asm
0x180027dac  mov     [rsp-28h+arg_8], rbx
0x180027db1  mov     [rsp-28h+arg_18], rsi
0x180027db6  push    rbp
0x180027db7  push    rdi
0x180027db8  push    r12
0x180027dba  push    r14
0x180027dbc  push    r15
0x180027dbe  mov     rbp, rsp
0x180027dc1  sub     rsp, 30h
0x180027dc5  mov     [rbp+arg_0], 0
0x180027dcc  mov     r12, rdx
0x180027dcf  mov     [rbp+arg_10], 0
0x180027dd7  mov     rdi, rcx
0x180027dda  test    rcx, rcx
0x180027ddd  jz      loc_180027FF3
0x180027de3  xor     r9d, r9d; pvData
0x180027de6  lea     rax, [rbp+arg_0]
0x180027dea  xor     r8d, r8d; dwIndex
0x180027ded  mov     qword ptr [rsp+30h+pcbData], rax; int
0x180027df2  lea     r14d, [r9+9]
0x180027df6  mov     edx, r14d; dwParamType
0x180027df9  call    cs:__imp_CryptMsgGetParam
0x180027dff  test    eax, eax
0x180027e01  jnz     short loc_180027E34
0x180027e03  call    cs:__imp_GetLastError
0x180027e09  cmp     eax, 8009100Fh
0x180027e0e  jz      loc_180027FF3
0x180027e14  test    eax, eax
0x180027e16  jz      loc_180027FF3
0x180027e1c  mov     rcx, [rbp+28h]; this
0x180027e20  mov     r9d, eax; char *
0x180027e23  mov     edx, 8D1h; void *
0x180027e28  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180027e2d  mov     ebx, eax
0x180027e2f  jmp     loc_180027FE6
0x180027e34  mov     esi, [rbp+arg_0]
0x180027e37  xor     ecx, ecx; uFlags
0x180027e39  mov     edx, esi; uBytes
0x180027e3b  call    cs:__imp_LocalAlloc
0x180027e41  mov     rbx, rax
0x180027e44  test    rax, rax
0x180027e47  jz      loc_180027FC9
0x180027e4d  lea     rcx, [rsi+rax]
0x180027e51  cmp     rax, rcx
0x180027e54  jz      short loc_180027E62
0x180027e56  xor     edx, edx
0x180027e58  mov     [rax], dl
0x180027e5a  inc     rax
0x180027e5d  cmp     rax, rcx
0x180027e60  jnz     short loc_180027E56
0x180027e62  lea     rax, [rbp+arg_0]
0x180027e66  mov     r9, rbx; pvData
0x180027e69  xor     r8d, r8d; dwIndex
0x180027e6c  mov     qword ptr [rsp+30h+pcbData], rax; int
0x180027e71  mov     edx, r14d; dwParamType
0x180027e74  mov     rcx, rdi; hCryptMsg
0x180027e77  mov     r15, rbx
0x180027e7a  call    cs:__imp_CryptMsgGetParam
0x180027e80  test    eax, eax
0x180027e82  jnz     short loc_180027E9D
0x180027e84  mov     rcx, [rbp+28h]; this
0x180027e88  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180027e8f  mov     edx, 8DBh; void *
0x180027e94  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027e99  mov     ebx, eax
0x180027e9b  jmp     short loc_180027ED4
0x180027e9d  mov     edx, 48h ; 'H'; uBytes
0x180027ea2  lea     ecx, [rdx-8]; uFlags
0x180027ea5  call    cs:__imp_LocalAlloc
0x180027eab  mov     [rbp+arg_10], rax
0x180027eaf  mov     r8, rax
0x180027eb2  test    rax, rax
0x180027eb5  jnz     short loc_180027EEB
0x180027eb7  mov     rcx, [rbp+28h]; this
0x180027ebb  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180027ec2  mov     ebx, 8007000Eh
0x180027ec7  mov     edx, 8E0h; void *
0x180027ecc  mov     r9d, ebx; char *
0x180027ecf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ed4  lea     rcx, [rbp+arg_10]
0x180027ed8  call    SIPolicyFreeResources
0x180027edd  mov     rcx, r15; hMem
0x180027ee0  call    cs:__imp_LocalFree
0x180027ee6  jmp     loc_180027FEF
0x180027eeb  xor     r14d, r14d
0x180027eee  lea     rdi, off_180052770; "1.3.6.1.4.1.311.2.7.1"
0x180027ef5  cmp     r14d, [r15]
0x180027ef8  jnb     loc_180027FA9
0x180027efe  xor     esi, esi
0x180027f00  cmp     esi, 5
0x180027f03  jnb     short loc_180027F67
0x180027f05  mov     rax, [r15+8]
0x180027f09  lea     rcx, [r14+r14*2]
0x180027f0d  lea     r11, [rsi+rsi*2]
0x180027f11  lea     r10, [rax+rcx*8]
0x180027f15  mov     rax, [rdi+r11*8]
0x180027f19  mov     r9, [r10]
0x180027f1c  sub     r9, rax
0x180027f1f  movzx   ecx, byte ptr [rax]
0x180027f22  movzx   edx, byte ptr [rax+r9]
0x180027f27  sub     ecx, edx
0x180027f29  jnz     short loc_180027F32
0x180027f2b  inc     rax
0x180027f2e  test    edx, edx
0x180027f30  jnz     short loc_180027F1F
0x180027f32  test    ecx, ecx
0x180027f34  jnz     short loc_180027F63
0x180027f36  cmp     dword ptr [r10+8], 1
0x180027f3b  jnz     short loc_180027F76
0x180027f3d  mov     edx, [rdi+r11*8+8]
0x180027f42  mov     rcx, r10
0x180027f45  mov     rax, ds:(funcs_180027F4D - 180052770h)[rdi+r11*8]
0x180027f4a  add     rdx, r8
0x180027f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f52  mov     edi, eax
0x180027f54  test    eax, eax
0x180027f56  js      short loc_180027F6C
0x180027f58  mov     r8, [rbp+arg_10]
0x180027f5c  lea     rdi, off_180052770; "1.3.6.1.4.1.311.2.7.1"
0x180027f63  inc     esi
0x180027f65  jmp     short loc_180027F00
0x180027f67  inc     r14d
0x180027f6a  jmp     short loc_180027EF5
0x180027f6c  mov     r9d, eax
0x180027f6f  mov     edx, 8F0h
0x180027f74  jmp     short loc_180027F83
0x180027f76  mov     edi, 8000FFFFh
0x180027f7b  mov     edx, 8EBh; void *
0x180027f80  mov     r9d, edi; char *
0x180027f83  mov     rcx, [rbp+28h]; this
0x180027f87  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180027f8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027f93  lea     rcx, [rbp+arg_10]
0x180027f97  call    SIPolicyFreeResources
0x180027f9c  mov     rcx, rbx; hMem
0x180027f9f  call    cs:__imp_LocalFree
0x180027fa5  mov     eax, edi
0x180027fa7  jmp     short loc_180027FFE
0x180027fa9  lea     rcx, [rbp+arg_10]
0x180027fad  mov     [r12], r8
0x180027fb1  mov     [rbp+arg_10], 0
0x180027fb9  call    SIPolicyFreeResources
0x180027fbe  mov     rcx, rbx; hMem
0x180027fc1  call    cs:__imp_LocalFree
0x180027fc7  jmp     short loc_180027FFC
0x180027fc9  mov     rcx, [rbp+28h]; this
0x180027fcd  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180027fd4  mov     ebx, 8007000Eh
0x180027fd9  mov     edx, 8D5h; void *
0x180027fde  mov     r9d, ebx; char *
0x180027fe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027fe6  lea     rcx, [rbp+arg_10]
0x180027fea  call    SIPolicyFreeResources
0x180027fef  mov     eax, ebx
0x180027ff1  jmp     short loc_180027FFE
0x180027ff3  lea     rcx, [rbp+arg_10]
0x180027ff7  call    SIPolicyFreeResources
0x180027ffc  xor     eax, eax
0x180027ffe  mov     rbx, [rsp+30h+arg_8]
0x180028003  mov     rsi, [rsp+30h+arg_18]
0x180028008  add     rsp, 30h
0x18002800c  pop     r15
0x18002800e  pop     r14
0x180028010  pop     r12
0x180028012  pop     rdi
0x180028013  pop     rbp
0x180028014  retn
```
