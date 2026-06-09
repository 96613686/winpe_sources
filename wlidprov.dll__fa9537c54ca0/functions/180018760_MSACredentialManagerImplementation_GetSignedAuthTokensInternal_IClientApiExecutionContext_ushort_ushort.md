# MSACredentialManagerImplementation::GetSignedAuthTokensInternal(IClientApiExecutionContext *,ushort * *,ushort * *)

- ea: `0x180018760`
- end: `0x1800189eb`
- name: `?GetSignedAuthTokensInternal@MSACredentialManagerImplementation@@EEAAJPEAVIClientApiExecutionContext@@PEAPEAG1@Z`
- size: `651`
- prototype: `__int64 __fastcall(MSACredentialManagerImplementation *__hidden this, struct IClientApiExecutionContext *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x180018760`
- `0x1800189f4`
- `0x180018a0c`
- `0x180030640`
- `0x180032b3c`
- `0x180058010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800189bb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800189bb`

## string_xrefs

- `0x18001877c`: `MSACredentialManagerImplementation::GetSignedAuthTokensInternal`
- `0x180018850`: `MSACredentialManagerImplementation::GetSignedAuthTokensInternal`
- `0x180018834`: `pSignedUserDAToken != nullptr`
- `0x18001886d`: `pSignedDeviceDAToken != nullptr`
- `0x18001889d`: `hr = pNtServiceFunctions->WLIDCGetSignedTokens(&pSignedTokens)`
- `0x180018902`: `hr = CopyToAutoString(autoUserToken, autoComUserToken, &sizeInBytes)`
- `0x180018944`: `hr = CopyToAutoString(autoDeviceToken, autoComDeviceToken, &sizeInBytes)`

## pseudocode

```c
__int64 __fastcall MSACredentialManagerImplementation::GetSignedAuthTokensInternal(
        MSACredentialManagerImplementation *this,
        struct IClientApiExecutionContext *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  __int64 v7; // rax
  unsigned __int16 *v8; // rbx
  unsigned __int16 *v9; // rdi
  unsigned __int16 *v10; // r15
  unsigned __int16 *v11; // r14
  const char *v12; // rax
  unsigned int v13; // r8d
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int v17; // ebx
  char *v19; // [rsp+20h] [rbp-79h]
  void **v20; // [rsp+38h] [rbp-61h] BYREF
  unsigned __int16 *v21; // [rsp+40h] [rbp-59h] BYREF
  __int64 v22; // [rsp+48h] [rbp-51h]
  void ***v23; // [rsp+50h] [rbp-49h]
  unsigned __int16 *v24; // [rsp+58h] [rbp-41h] BYREF
  __int64 v25; // [rsp+60h] [rbp-39h]
  void ***v26; // [rsp+68h] [rbp-31h]
  unsigned __int16 *v27; // [rsp+70h] [rbp-29h] BYREF
  __int64 v28; // [rsp+78h] [rbp-21h]
  __int64 v29; // [rsp+80h] [rbp-19h]
  unsigned __int16 *v30; // [rsp+88h] [rbp-11h] BYREF
  __int64 v31; // [rsp+90h] [rbp-9h]
  __int64 v32; // [rsp+98h] [rbp-1h]
  _QWORD v33[10]; // [rsp+A0h] [rbp+7h] BYREF
  int v34; // [rsp+108h] [rbp+6Fh] BYREF
  void *Block; // [rsp+110h] [rbp+77h] BYREF

  v33[2] = 11;
  v33[0] = "MSACredentialManagerImplementation::GetSignedAuthTokensInternal";
  v20 = &CoTaskMemoryManager::`vftable';
  v33[1] = &v34;
  v33[3] = qword_18006B450;
  v34 = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
    "MSACredentialManagerImplementation::GetSignedAuthTokensInternal",
    (const char *)0x2EE,
    0,
    (const unsigned __int16 *)v19);
  v7 = (*(__int64 (__fastcall **)(struct IClientApiExecutionContext *))(*(_QWORD *)a2 + 16LL))(a2);
  Block = 0;
  v30 = 0;
  v26 = &v20;
  v23 = &v20;
  v8 = 0;
  v32 = 0;
  v9 = 0;
  v31 = 0;
  v10 = 0;
  v27 = 0;
  v11 = 0;
  v29 = 0;
  v28 = 0;
  v24 = 0;
  v25 = 0;
  v21 = 0;
  v22 = 0;
  if ( !a3 )
  {
    v12 = "pSignedUserDAToken != nullptr";
    v13 = 763;
LABEL_3:
    v34 = -2147467261;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
      "MSACredentialManagerImplementation::GetSignedAuthTokensInternal",
      v13,
      -2147467261,
      v12);
    goto LABEL_23;
  }
  if ( !a4 )
  {
    v12 = "pSignedDeviceDAToken != nullptr";
    v13 = 764;
    goto LABEL_3;
  }
  *a3 = 0;
  *a4 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v7 + 160LL))(v7, &Block);
  v34 = v14;
  if ( v14 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
      "MSACredentialManagerImplementation::GetSignedAuthTokensInternal",
      0x301u,
      v14,
      "hr = pNtServiceFunctions->WLIDCGetSignedTokens(&pSignedTokens)");
    goto LABEL_23;
  }
  if ( Block )
  {
    v9 = *(unsigned __int16 **)Block;
    Auto<unsigned char *,LocalMIDLSecurePointerFunctor<unsigned char *>,DummyContext>::Clear(&v30);
    v30 = v9;
    v8 = (unsigned __int16 *)*((_QWORD *)Block + 1);
    Auto<unsigned char *,LocalMIDLSecurePointerFunctor<unsigned char *>,DummyContext>::Clear(&v27);
    v27 = v8;
  }
  if ( v9 )
  {
    v15 = CopyToAutoString<ZeroMemoryFunctor<unsigned short *>,IMemoryManager>(v9);
    v34 = v15;
    if ( v15 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
        "MSACredentialManagerImplementation::GetSignedAuthTokensInternal",
        0x30Du,
        v15,
        "hr = CopyToAutoString(autoUserToken, autoComUserToken, &sizeInBytes)");
      goto LABEL_23;
    }
    v10 = v24;
    v31 = 0;
  }
  if ( v8 )
  {
    v16 = CopyToAutoString<ZeroMemoryFunctor<unsigned short *>,IMemoryManager>(v8);
    v34 = v16;
    if ( v16 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
        "MSACredentialManagerImplementation::GetSignedAuthTokensInternal",
        0x312u,
        v16,
        "hr = CopyToAutoString(autoDeviceToken, autoComDeviceToken, &sizeInBytes)");
      goto LABEL_23;
    }
    v11 = v21;
    v28 = 0;
  }
  if ( v9 )
  {
    v24 = 0;
    v25 = 0;
    *a3 = v10;
  }
  if ( v8 )
  {
    v21 = 0;
    v22 = 0;
    *a4 = v11;
  }
LABEL_23:
  v17 = v34;
  Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v21);
  Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>::~Auto<unsigned char *,ZeroMemoryFunctor<unsigned char *>,IMemoryManager>(&v24);
  Auto<unsigned short *,LocalMIDLSecurePointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLSecurePointerFunctor<unsigned short *>,DummyContext>(&v27);
  Auto<unsigned short *,LocalMIDLSecurePointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLSecurePointerFunctor<unsigned short *>,DummyContext>(&v30);
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>(v33);
  return v17;
}

```

## disassembly

```asm
0x180018760  mov     [rsp-8+arg_0], rbx
0x180018765  push    rbp
0x180018766  push    rsi
0x180018767  push    rdi
0x180018768  push    r12
0x18001876a  push    r13
0x18001876c  push    r14
0x18001876e  push    r15
0x180018770  lea     rbp, [rsp-27h]
0x180018775  sub     rsp, 0C0h
0x18001877c  lea     rcx, aMsacredentialm_4; "MSACredentialManagerImplementation::Get"...
0x180018783  mov     [rbp+57h+var_40], 0Bh
0x18001878b  lea     rax, ??_7CoTaskMemoryManager@@6B@; const CoTaskMemoryManager::`vftable'
0x180018792  mov     [rbp+57h+var_50], rcx
0x180018796  mov     [rbp+57h+var_B8], rax
0x18001879a  mov     rbx, rdx
0x18001879d  lea     rax, [rbp+57h+arg_8]
0x1800187a1  mov     rsi, r9
0x1800187a4  mov     [rbp+57h+var_48], rax
0x1800187a8  mov     r12, r8
0x1800187ab  lea     rax, qword_18006B450
0x1800187b2  mov     rdx, rcx; char *
0x1800187b5  xor     r13d, r13d
0x1800187b8  mov     [rbp+57h+var_38], rax
0x1800187bc  xor     r9d, r9d; unsigned int
0x1800187bf  mov     [rbp+57h+arg_8], r13d
0x1800187c3  mov     r8d, 2EEh; char *
0x1800187c9  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800187d0  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800187d5  mov     rax, [rbx]
0x1800187d8  mov     rcx, rbx
0x1800187db  mov     rax, [rax+10h]
0x1800187df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187e4  mov     [rbp+57h+Block], r13
0x1800187e8  mov     rcx, rax
0x1800187eb  mov     [rbp+57h+var_68], r13
0x1800187ef  lea     rax, [rbp+57h+var_B8]
0x1800187f3  mov     [rbp+57h+var_88], rax
0x1800187f7  lea     rax, [rbp+57h+var_B8]
0x1800187fb  mov     [rbp+57h+var_A0], rax
0x1800187ff  mov     ebx, r13d
0x180018802  mov     [rbp+57h+var_58], r13
0x180018806  mov     edi, r13d
0x180018809  mov     [rbp+57h+var_60], r13
0x18001880d  mov     r15d, r13d
0x180018810  mov     [rbp+57h+var_80], rbx
0x180018814  mov     r14d, r13d
0x180018817  mov     [rbp+57h+var_70], r13
0x18001881b  mov     [rbp+57h+var_78], r13
0x18001881f  mov     [rbp+57h+var_98], r13
0x180018823  mov     [rbp+57h+var_90], r13
0x180018827  mov     [rbp+57h+var_B0], r13
0x18001882b  mov     [rbp+57h+var_A8], r13
0x18001882f  test    r12, r12
0x180018832  jnz     short loc_180018868
0x180018834  lea     rax, aPsigneduserdat; "pSignedUserDAToken != nullptr"
0x18001883b  mov     r8d, 2FBh; unsigned int
0x180018841  mov     r9d, 80004003h; int
0x180018847  mov     [rsp+0F0h+var_D0], rax; char *
0x18001884c  mov     [rbp+57h+arg_8], r9d
0x180018850  lea     rdx, aMsacredentialm_4; "MSACredentialManagerImplementation::Get"...
0x180018857  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18001885e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180018863  jmp     loc_18001898B
0x180018868  test    rsi, rsi
0x18001886b  jnz     short loc_18001887C
0x18001886d  lea     rax, aPsigneddeviced; "pSignedDeviceDAToken != nullptr"
0x180018874  mov     r8d, 2FCh
0x18001887a  jmp     short loc_180018841
0x18001887c  mov     [r12], r13
0x180018880  lea     rdx, [rbp+57h+Block]
0x180018884  mov     [rsi], r13
0x180018887  mov     rax, [rcx]
0x18001888a  mov     rax, [rax+0A0h]
0x180018891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018896  mov     [rbp+57h+arg_8], eax
0x180018899  test    eax, eax
0x18001889b  jns     short loc_1800188B4
0x18001889d  lea     rcx, aHrPntservicefu; "hr = pNtServiceFunctions->WLIDCGetSigne"...
0x1800188a4  mov     r9d, eax
0x1800188a7  mov     [rsp+0F0h+var_D0], rcx
0x1800188ac  mov     r8d, 301h
0x1800188b2  jmp     short loc_180018850
0x1800188b4  mov     rax, [rbp+57h+Block]
0x1800188b8  test    rax, rax
0x1800188bb  jz      short loc_1800188E2
0x1800188bd  mov     rdi, [rax]
0x1800188c0  lea     rcx, [rbp+57h+var_68]
0x1800188c4  call    ?Clear@?$Auto@PEAEV?$LocalMIDLSecurePointerFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalMIDLSecurePointerFunctor<uchar *>,DummyContext>::Clear(void)
0x1800188c9  mov     rax, [rbp+57h+Block]
0x1800188cd  lea     rcx, [rbp+57h+var_80]
0x1800188d1  mov     [rbp+57h+var_68], rdi
0x1800188d5  mov     rbx, [rax+8]
0x1800188d9  call    ?Clear@?$Auto@PEAEV?$LocalMIDLSecurePointerFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalMIDLSecurePointerFunctor<uchar *>,DummyContext>::Clear(void)
0x1800188de  mov     [rbp+57h+var_80], rbx
0x1800188e2  mov     [rbp+57h+var_C0], r13
0x1800188e6  test    rdi, rdi
0x1800188e9  jz      short loc_180018928
0x1800188eb  lea     r8, [rbp+57h+var_C0]
0x1800188ef  mov     rcx, rdi; unsigned __int16 *
0x1800188f2  lea     rdx, [rbp+57h+var_98]
0x1800188f6  call    ??$CopyToAutoString@V?$ZeroMemoryFunctor@PEAG@@VIMemoryManager@@@@YAJPEBGAEAV?$Auto@PEAGV?$ZeroMemoryFunctor@PEAG@@VIMemoryManager@@@@PEA_K@Z; CopyToAutoString<ZeroMemoryFunctor<ushort *>,IMemoryManager>(ushort const *,Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager> &,unsigned __int64 *)
0x1800188fb  mov     [rbp+57h+arg_8], eax
0x1800188fe  test    eax, eax
0x180018900  jns     short loc_18001891C
0x180018902  lea     rcx, aHrCopytoautost_2; "hr = CopyToAutoString(autoUserToken, au"...
0x180018909  mov     r9d, eax
0x18001890c  mov     [rsp+0F0h+var_D0], rcx
0x180018911  mov     r8d, 30Dh
0x180018917  jmp     loc_180018850
0x18001891c  mov     rax, [rbp+57h+var_C0]
0x180018920  mov     r15, [rbp+57h+var_98]
0x180018924  mov     [rbp+57h+var_60], rax
0x180018928  test    rbx, rbx
0x18001892b  jz      short loc_18001896A
0x18001892d  lea     r8, [rbp+57h+var_C0]
0x180018931  mov     rcx, rbx; unsigned __int16 *
0x180018934  lea     rdx, [rbp+57h+var_B0]
0x180018938  call    ??$CopyToAutoString@V?$ZeroMemoryFunctor@PEAG@@VIMemoryManager@@@@YAJPEBGAEAV?$Auto@PEAGV?$ZeroMemoryFunctor@PEAG@@VIMemoryManager@@@@PEA_K@Z; CopyToAutoString<ZeroMemoryFunctor<ushort *>,IMemoryManager>(ushort const *,Auto<ushort *,ZeroMemoryFunctor<ushort *>,IMemoryManager> &,unsigned __int64 *)
0x18001893d  mov     [rbp+57h+arg_8], eax
0x180018940  test    eax, eax
0x180018942  jns     short loc_18001895E
0x180018944  lea     rcx, aHrCopytoautost; "hr = CopyToAutoString(autoDeviceToken, "...
0x18001894b  mov     r9d, eax
0x18001894e  mov     [rsp+0F0h+var_D0], rcx
0x180018953  mov     r8d, 312h
0x180018959  jmp     loc_180018850
0x18001895e  mov     rax, [rbp+57h+var_C0]
0x180018962  mov     r14, [rbp+57h+var_B0]
0x180018966  mov     [rbp+57h+var_78], rax
0x18001896a  test    rdi, rdi
0x18001896d  jz      short loc_18001897B
0x18001896f  mov     [rbp+57h+var_98], r13
0x180018973  mov     [rbp+57h+var_90], r13
0x180018977  mov     [r12], r15
0x18001897b  test    rbx, rbx
0x18001897e  jz      short loc_18001898B
0x180018980  mov     [rbp+57h+var_B0], r13
0x180018984  mov     [rbp+57h+var_A8], r13
0x180018988  mov     [rsi], r14
0x18001898b  mov     ebx, [rbp+57h+arg_8]
0x18001898e  lea     rcx, [rbp+57h+var_B0]
0x180018992  call    ??1?$Auto@PEAEV?$ZeroMemoryFunctor@PEAE@@VIMemoryManager@@@@QEAA@XZ; Auto<uchar *,ZeroMemoryFunctor<uchar *>,IMemoryManager>::~Auto<uchar *,ZeroMemoryFunctor<uchar *>,IMemoryManager>(void)
0x180018997  lea     rcx, [rbp+57h+var_98]
0x18001899b  call    ??1?$Auto@PEAEV?$ZeroMemoryFunctor@PEAE@@VIMemoryManager@@@@QEAA@XZ; Auto<uchar *,ZeroMemoryFunctor<uchar *>,IMemoryManager>::~Auto<uchar *,ZeroMemoryFunctor<uchar *>,IMemoryManager>(void)
0x1800189a0  lea     rcx, [rbp+57h+var_80]
0x1800189a4  call    ??1?$Auto@PEAGV?$LocalMIDLSecurePointerFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,LocalMIDLSecurePointerFunctor<ushort *>,DummyContext>::~Auto<ushort *,LocalMIDLSecurePointerFunctor<ushort *>,DummyContext>(void)
0x1800189a9  lea     rcx, [rbp+57h+var_68]
0x1800189ad  call    ??1?$Auto@PEAGV?$LocalMIDLSecurePointerFunctor@PEAG@@VDummyContext@@@@QEAA@XZ; Auto<ushort *,LocalMIDLSecurePointerFunctor<ushort *>,DummyContext>::~Auto<ushort *,LocalMIDLSecurePointerFunctor<ushort *>,DummyContext>(void)
0x1800189b2  mov     rcx, [rbp+57h+Block]; Block
0x1800189b6  test    rcx, rcx
0x1800189b9  jz      short loc_1800189C5
0x1800189bb  call    cs:__imp_free
0x1800189c1  mov     [rbp+57h+Block], r13
0x1800189c5  lea     rcx, [rbp+57h+var_50]
0x1800189c9  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800189ce  mov     eax, ebx
0x1800189d0  mov     rbx, [rsp+0F0h+arg_0]
0x1800189d8  add     rsp, 0C0h
0x1800189df  pop     r15
0x1800189e1  pop     r14
0x1800189e3  pop     r13
0x1800189e5  pop     r12
0x1800189e7  pop     rdi
0x1800189e8  pop     rsi
0x1800189e9  pop     rbp
0x1800189ea  retn
```
