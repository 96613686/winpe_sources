# LiteCryptUtilities::HmacHashHelper(unsigned __int64,unsigned __int64,uint,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x180059568`
- end: `0x1800598f3`
- name: `?HmacHashHelper@LiteCryptUtilities@@YAJ_K0IPEAEK1KPEAPEAEPEAK@Z`
- size: `907`
- prototype: `__int64 __usercall@<rax>(HCRYPTPROV hProv@<rcx>, HCRYPTKEY hKey@<rdx>, unsigned __int64@<r8>, unsigned int@<r9d>, DWORD dwDataLen, BYTE *, DWORD, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180058be8`

## callees

- `0x18000cc9c`
- `0x18000e870`
- `0x180021a64`
- `0x180021a90`
- `0x180051250`
- `0x1800512f8`
- `0x180053890`
- `0x180058b80`
- `0x180059568`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800596d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800597ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800596d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800597ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059831`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800597dc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800597dc`
- `CRYPTSP!CryptGetHashParam` at `0x1800597a2`
- `CRYPTSP!CryptGetHashParam` at `0x180059827`
- `CRYPTSP!CryptGetHashParam` at `0x1800597a2`
- `CRYPTSP!CryptGetHashParam` at `0x180059827`
- `CRYPTSP!CryptSetHashParam` at `0x1800596cf`
- `CRYPTSP!CryptSetHashParam` at `0x1800596cf`
- `CRYPTSP!CryptCreateHash` at `0x180059679`
- `CRYPTSP!CryptCreateHash` at `0x180059679`
- `CRYPTSP!CryptHashData` at `0x18005970c`
- `CRYPTSP!CryptHashData` at `0x180059758`
- `CRYPTSP!CryptHashData` at `0x18005970c`
- `CRYPTSP!CryptHashData` at `0x180059758`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LiteCryptUtilities::HmacHashHelper(
        HCRYPTPROV hProv,
        HCRYPTKEY hKey,
        __int64 a3,
        const BYTE *a4,
        DWORD dwDataLen,
        BYTE *a6,
        DWORD a7,
        BYTE **a8,
        unsigned __int8 **a9)
{
  DWORD v12; // ebx
  BYTE **v13; // rdi
  unsigned __int8 **v14; // rsi
  signed int LastError; // eax
  signed int v16; // r9d
  unsigned int v17; // r8d
  const char *v18; // rax
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  BYTE *v23; // rbx
  signed int v24; // eax
  unsigned int v25; // ebx
  HCRYPTHASH *phHash; // [rsp+20h] [rbp-A9h]
  DWORD pdwDataLen; // [rsp+30h] [rbp-99h] BYREF
  HCRYPTHASH hHash[3]; // [rsp+38h] [rbp-91h] BYREF
  BYTE *v30; // [rsp+50h] [rbp-79h] BYREF
  __int64 v31; // [rsp+58h] [rbp-71h]
  __int64 v32; // [rsp+60h] [rbp-69h]
  int *v33[4]; // [rsp+68h] [rbp-61h] BYREF
  _QWORD v34[4]; // [rsp+88h] [rbp-41h] BYREF
  BYTE pbData[16]; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-11h]
  __int64 v37; // [rsp+C8h] [rbp-1h]
  int v38; // [rsp+120h] [rbp+57h] BYREF
  DWORD v39; // [rsp+128h] [rbp+5Fh] BYREF

  v38 = 0;
  v39 = 0;
  pdwDataLen = 4;
  v30 = 0;
  v32 = 0;
  v31 = 0;
  memset(hHash, 0, sizeof(hHash));
  *(_OWORD *)pbData = 0;
  v36 = 0;
  v37 = 0;
  *(_DWORD *)pbData = 32772;
  v34[0] = "LiteCryptUtilities::HmacHashHelper";
  v34[1] = &v38;
  v34[2] = 0;
  v34[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
    "LiteCryptUtilities::HmacHashHelper",
    (const char *)0x4E,
    0,
    (const unsigned __int16 *)phHash);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v33, "LiteCryptUtilities::HmacHashHelper", &v38, 0xBu, &qword_180083C40);
  if ( !a4 || (v12 = dwDataLen) == 0 || (v13 = a8) == 0 || (v14 = a9) == 0 )
  {
    v16 = -2147024809;
    v18 = "hr = E_INVALIDARG";
    v17 = 90;
    goto LABEL_42;
  }
  *a8 = 0;
  *(_DWORD *)v14 = 0;
  if ( !CryptCreateHash(hProv, 0x8009u, hKey, 0, hHash) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    v38 = v16;
    if ( v16 < 0 )
    {
      v17 = 96;
LABEL_10:
      v18 = "hr = HRESULT_FROM_WIN32(GetLastError())";
LABEL_43:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\utilitieslite\\litecryptutilities.cpp",
        "LiteCryptUtilities::HmacHashHelper",
        v17,
        v16,
        v18);
      goto LABEL_44;
    }
  }
  if ( !CryptSetHashParam(hHash[0], 5u, pbData, 0) )
  {
    v19 = GetLastError();
    v16 = v19;
    if ( v19 > 0 )
      v16 = (unsigned __int16)v19 | 0x80070000;
    v38 = v16;
    if ( v16 < 0 )
    {
      v17 = 97;
      goto LABEL_10;
    }
  }
  if ( !CryptHashData(hHash[0], a4, v12, 0) )
  {
    v20 = GetLastError();
    v16 = v20;
    if ( v20 > 0 )
      v16 = (unsigned __int16)v20 | 0x80070000;
    v38 = v16;
    if ( v16 < 0 )
    {
      v17 = 98;
      goto LABEL_10;
    }
  }
  if ( a6 && a7 && !CryptHashData(hHash[0], a6, a7, 0) )
  {
    v21 = GetLastError();
    v16 = v21;
    if ( v21 > 0 )
      v16 = (unsigned __int16)v21 | 0x80070000;
    v38 = v16;
    if ( v16 < 0 )
    {
      v17 = 102;
      goto LABEL_10;
    }
  }
  if ( !CryptGetHashParam(hHash[0], 4u, (BYTE *)&v39, &pdwDataLen, 0) )
  {
    v22 = GetLastError();
    v16 = v22;
    if ( v22 > 0 )
      v16 = (unsigned __int16)v22 | 0x80070000;
    v38 = v16;
    if ( v16 < 0 )
    {
      v17 = 105;
      goto LABEL_10;
    }
  }
  v23 = (BYTE *)LocalAlloc(0x40u, v39);
  Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(&v30);
  v30 = v23;
  if ( !v23 )
  {
    v16 = -2147024882;
    v18 = "hr = E_OUTOFMEMORY";
    v17 = 110;
LABEL_42:
    v38 = v16;
    goto LABEL_43;
  }
  if ( !CryptGetHashParam(hHash[0], 2u, v23, &v39, 0) )
  {
    v24 = GetLastError();
    v16 = v24;
    if ( v24 > 0 )
      v16 = (unsigned __int16)v24 | 0x80070000;
    v38 = v16;
    if ( v16 < 0 )
    {
      v17 = 113;
      goto LABEL_10;
    }
  }
  v30 = 0;
  v31 = 0;
  *v13 = v23;
  *(_DWORD *)v14 = v39;
LABEL_44:
  v25 = v38;
  ErrorVerifier::CheckAgainstList((const char *)v33[3], *v33[2], (unsigned __int64)v33[1], v33[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v34);
  Auto<unsigned __int64,CryptHashFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,CryptHashFunctor<unsigned __int64>,DummyContext>(hHash);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  return v25;
}

```

## disassembly

```asm
0x180059568  mov     [rsp-8+arg_0], rbx
0x18005956d  mov     [rsp-8+arg_10], r8d
0x180059572  push    rbp
0x180059573  push    rsi
0x180059574  push    rdi
0x180059575  push    r12
0x180059577  push    r13
0x180059579  push    r14
0x18005957b  push    r15
0x18005957d  lea     rbp, [rsp-7]
0x180059582  sub     rsp, 0D0h
0x180059589  mov     r12, r9
0x18005958c  mov     r14, rdx
0x18005958f  mov     r15, rcx
0x180059592  xor     r13d, r13d
0x180059595  mov     [rbp+37h+arg_10], r13d
0x180059599  mov     [rbp+37h+arg_18], r13d
0x18005959d  mov     [rsp+100h+pdwDataLen], 4
0x1800595a5  mov     [rbp+37h+var_B0], r13
0x1800595a9  mov     [rbp+37h+var_A0], r13
0x1800595ad  mov     [rbp+37h+var_A8], r13
0x1800595b1  mov     [rsp+100h+hHash], r13
0x1800595b6  mov     [rsp+100h+var_B8], r13
0x1800595bb  mov     [rsp+100h+var_C0], r13
0x1800595c0  xorps   xmm0, xmm0
0x1800595c3  xor     eax, eax
0x1800595c5  movups  xmmword ptr [rbp+37h+pbData], xmm0
0x1800595c9  movups  [rbp+37h+var_48], xmm0
0x1800595cd  mov     [rbp+37h+var_38], rax
0x1800595d1  mov     dword ptr [rbp+37h+pbData], 8004h
0x1800595d8  lea     rsi, aLitecryptutili_0; "LiteCryptUtilities::HmacHashHelper"
0x1800595df  mov     [rbp+37h+var_78], rsi
0x1800595e3  lea     rax, [rbp+37h+arg_10]
0x1800595e7  mov     [rbp+37h+var_70], rax
0x1800595eb  mov     [rbp+37h+var_68], r13
0x1800595ef  mov     [rbp+37h+var_60], r13
0x1800595f3  xor     r9d, r9d; unsigned int
0x1800595f6  lea     r8d, [r13+4Eh]; char *
0x1800595fa  mov     rdx, rsi; char *
0x1800595fd  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180059604  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180059609  nop
0x18005960a  lea     rax, qword_180083C40
0x180059611  mov     [rsp+100h+phHash], rax; int *
0x180059616  lea     r9d, [r13+0Bh]; unsigned __int64
0x18005961a  lea     r8, [rbp+37h+arg_10]; int *
0x18005961e  mov     rdx, rsi; char *
0x180059621  lea     rcx, [rbp+37h+var_98]; this
0x180059625  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18005962a  test    r12, r12
0x18005962d  jz      loc_180059872
0x180059633  mov     ebx, [rbp+37h+dwDataLen]
0x180059636  test    ebx, ebx
0x180059638  jz      loc_180059872
0x18005963e  mov     rdi, [rbp+37h+arg_38]
0x180059642  test    rdi, rdi
0x180059645  jz      loc_180059872
0x18005964b  mov     rsi, [rbp+37h+arg_40]
0x180059652  test    rsi, rsi
0x180059655  jz      loc_18005986B
0x18005965b  mov     [rdi], r13
0x18005965e  mov     [rsi], r13d
0x180059661  lea     rax, [rsp+100h+hHash]
0x180059666  mov     [rsp+100h+phHash], rax; phHash
0x18005966b  xor     r9d, r9d; dwFlags
0x18005966e  mov     r8, r14; hKey
0x180059671  mov     edx, 8009h; Algid
0x180059676  mov     rcx, r15; hProv
0x180059679  call    cs:__imp_CryptCreateHash
0x18005967f  mov     r14d, 80070000h
0x180059685  test    eax, eax
0x180059687  jnz     short loc_1800596BF
0x180059689  call    cs:__imp_GetLastError
0x18005968f  mov     r9d, eax
0x180059692  test    eax, eax
0x180059694  jle     short loc_18005969D
0x180059696  movzx   r9d, ax
0x18005969a  or      r9d, r14d
0x18005969d  mov     [rbp+37h+arg_10], r9d
0x1800596a1  test    r9d, r9d
0x1800596a4  jns     short loc_1800596BF
0x1800596a6  mov     r8d, 60h ; '`'
0x1800596ac  lea     rax, aHrHresultFromW; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800596b3  lea     rdx, aLitecryptutili_0; "LiteCryptUtilities::HmacHashHelper"
0x1800596ba  jmp     loc_18005988C
0x1800596bf  xor     r9d, r9d; dwFlags
0x1800596c2  lea     r8, [rbp+37h+pbData]; pbData
0x1800596c6  lea     edx, [r9+5]; dwParam
0x1800596ca  mov     rcx, [rsp+100h+hHash]; hHash
0x1800596cf  call    cs:__imp_CryptSetHashParam
0x1800596d5  test    eax, eax
0x1800596d7  jnz     short loc_1800596FE
0x1800596d9  call    cs:__imp_GetLastError
0x1800596df  mov     r9d, eax
0x1800596e2  test    eax, eax
0x1800596e4  jle     short loc_1800596ED
0x1800596e6  movzx   r9d, ax
0x1800596ea  or      r9d, r14d
0x1800596ed  mov     [rbp+37h+arg_10], r9d
0x1800596f1  test    r9d, r9d
0x1800596f4  jns     short loc_1800596FE
0x1800596f6  mov     r8d, 61h ; 'a'
0x1800596fc  jmp     short loc_1800596AC
0x1800596fe  xor     r9d, r9d; dwFlags
0x180059701  mov     r8d, ebx; dwDataLen
0x180059704  mov     rdx, r12; pbData
0x180059707  mov     rcx, [rsp+100h+hHash]; hHash
0x18005970c  call    cs:__imp_CryptHashData
0x180059712  test    eax, eax
0x180059714  jnz     short loc_18005973E
0x180059716  call    cs:__imp_GetLastError
0x18005971c  mov     r9d, eax
0x18005971f  test    eax, eax
0x180059721  jle     short loc_18005972A
0x180059723  movzx   r9d, ax
0x180059727  or      r9d, r14d
0x18005972a  mov     [rbp+37h+arg_10], r9d
0x18005972e  test    r9d, r9d
0x180059731  jns     short loc_18005973E
0x180059733  mov     r8d, 62h ; 'b'
0x180059739  jmp     loc_1800596AC
0x18005973e  mov     rdx, [rbp+37h+arg_28]; pbData
0x180059742  test    rdx, rdx
0x180059745  jz      short loc_18005978A
0x180059747  mov     r8d, [rbp+37h+arg_30]; dwDataLen
0x18005974b  test    r8d, r8d
0x18005974e  jz      short loc_18005978A
0x180059750  xor     r9d, r9d; dwFlags
0x180059753  mov     rcx, [rsp+100h+hHash]; hHash
0x180059758  call    cs:__imp_CryptHashData
0x18005975e  test    eax, eax
0x180059760  jnz     short loc_18005978A
0x180059762  call    cs:__imp_GetLastError
0x180059768  mov     r9d, eax
0x18005976b  test    eax, eax
0x18005976d  jle     short loc_180059776
0x18005976f  movzx   r9d, ax
0x180059773  or      r9d, r14d
0x180059776  mov     [rbp+37h+arg_10], r9d
0x18005977a  test    r9d, r9d
0x18005977d  jns     short loc_18005978A
0x18005977f  mov     r8d, 66h ; 'f'
0x180059785  jmp     loc_1800596AC
0x18005978a  mov     dword ptr [rsp+100h+phHash], r13d; dwFlags
0x18005978f  lea     r9, [rsp+100h+pdwDataLen]; pdwDataLen
0x180059794  lea     r8, [rbp+37h+arg_18]; pbData
0x180059798  mov     edx, 4; dwParam
0x18005979d  mov     rcx, [rsp+100h+hHash]; hHash
0x1800597a2  call    cs:__imp_CryptGetHashParam
0x1800597a8  test    eax, eax
0x1800597aa  jnz     short loc_1800597D4
0x1800597ac  call    cs:__imp_GetLastError
0x1800597b2  mov     r9d, eax
0x1800597b5  test    eax, eax
0x1800597b7  jle     short loc_1800597C0
0x1800597b9  movzx   r9d, ax
0x1800597bd  or      r9d, r14d
0x1800597c0  mov     [rbp+37h+arg_10], r9d
0x1800597c4  test    r9d, r9d
0x1800597c7  jns     short loc_1800597D4
0x1800597c9  mov     r8d, 69h ; 'i'
0x1800597cf  jmp     loc_1800596AC
0x1800597d4  mov     edx, [rbp+37h+arg_18]; uBytes
0x1800597d7  mov     ecx, 40h ; '@'; uFlags
0x1800597dc  call    cs:__imp_LocalAlloc
0x1800597e2  mov     rbx, rax
0x1800597e5  lea     rcx, [rbp+37h+var_B0]
0x1800597e9  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x1800597ee  mov     [rbp+37h+var_B0], rbx
0x1800597f2  test    rbx, rbx
0x1800597f5  jnz     short loc_180059811
0x1800597f7  mov     r9d, 8007000Eh
0x1800597fd  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x180059804  lea     r8d, [rbx+6Eh]
0x180059808  lea     rdx, aLitecryptutili_0; "LiteCryptUtilities::HmacHashHelper"
0x18005980f  jmp     short loc_180059888
0x180059811  mov     dword ptr [rsp+100h+phHash], r13d; dwFlags
0x180059816  lea     r9, [rbp+37h+arg_18]; pdwDataLen
0x18005981a  mov     r8, rbx; pbData
0x18005981d  mov     edx, 2; dwParam
0x180059822  mov     rcx, [rsp+100h+hHash]; hHash
0x180059827  call    cs:__imp_CryptGetHashParam
0x18005982d  test    eax, eax
0x18005982f  jnz     short loc_180059859
0x180059831  call    cs:__imp_GetLastError
0x180059837  mov     r9d, eax
0x18005983a  test    eax, eax
0x18005983c  jle     short loc_180059845
0x18005983e  movzx   r9d, ax
0x180059842  or      r9d, r14d
0x180059845  mov     [rbp+37h+arg_10], r9d
0x180059849  test    r9d, r9d
0x18005984c  jns     short loc_180059859
0x18005984e  mov     r8d, 71h ; 'q'
0x180059854  jmp     loc_1800596AC
0x180059859  mov     [rbp+37h+var_B0], r13
0x18005985d  mov     [rbp+37h+var_A8], r13
0x180059861  mov     [rdi], rbx
0x180059864  mov     eax, [rbp+37h+arg_18]
0x180059867  mov     [rsi], eax
0x180059869  jmp     short loc_18005989D
0x18005986b  lea     rsi, aLitecryptutili_0; "LiteCryptUtilities::HmacHashHelper"
0x180059872  mov     r9d, 80070057h; int
0x180059878  lea     rax, aHrEInvalidarg; "hr = E_INVALIDARG"
0x18005987f  mov     r8d, 5Ah ; 'Z'; unsigned int
0x180059885  mov     rdx, rsi; char *
0x180059888  mov     [rbp+37h+arg_10], r9d
0x18005988c  mov     [rsp+100h+phHash], rax; char *
0x180059891  lea     rcx, aOnecoreuapDsEx_3; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180059898  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005989d  mov     ebx, [rbp+37h+arg_10]
0x1800598a0  mov     r9, [rbp+37h+var_98]; int *
0x1800598a4  mov     r8, [rbp+37h+var_90]; unsigned __int64
0x1800598a8  mov     rdx, [rbp+37h+var_88]
0x1800598ac  mov     edx, [rdx]; int
0x1800598ae  mov     rcx, [rbp+37h+var_80]; char *
0x1800598b2  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x1800598b7  nop
0x1800598b8  lea     rcx, [rbp+37h+var_78]
0x1800598bc  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800598c1  nop
0x1800598c2  lea     rcx, [rsp+100h+hHash]
0x1800598c7  call    ??1?$Auto@_KV?$CryptHashFunctor@_K@@VDummyContext@@@@QEAA@XZ; Auto<unsigned __int64,CryptHashFunctor<unsigned __int64>,DummyContext>::~Auto<unsigned __int64,CryptHashFunctor<unsigned __int64>,DummyContext>(void)
0x1800598cc  nop
0x1800598cd  lea     rcx, [rbp+37h+var_B0]
0x1800598d1  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x1800598d6  mov     eax, ebx
0x1800598d8  mov     rbx, [rsp+100h+arg_0]
0x1800598e0  add     rsp, 0D0h
0x1800598e7  pop     r15
0x1800598e9  pop     r14
0x1800598eb  pop     r13
0x1800598ed  pop     r12
0x1800598ef  pop     rdi
0x1800598f0  pop     rsi
0x1800598f1  pop     rbp
0x1800598f2  retn
```
