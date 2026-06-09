# MSACredentialManagerImplementation::SaveAuthStateInternal(IClientApiExecutionContext *,ushort const *,ushort const *,ushort const *,ulong,uchar *)

- ea: `0x180034bb0`
- end: `0x180034e99`
- name: `?SaveAuthStateInternal@MSACredentialManagerImplementation@@EEAAJPEAVIClientApiExecutionContext@@PEBG11KPEAE@Z`
- size: `745`
- prototype: `__int64 __fastcall(MSACredentialManagerImplementation *__hidden this, struct IClientApiExecutionContext *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update`

## callees

- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18001ac3c`
- `0x180030b58`
- `0x180034bb0`
- `0x180058010`

## import_xrefs

- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x180034d8c`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x180034d8c`

## string_xrefs

- `0x180034e49`: `IsNullOrEmpty(daToken) == false`
- `0x180034e3a`: `IsNullOrEmpty(daTokenCreationTime) == false`
- `0x180034e24`: `IsNullOrEmpty(daTokenExpiryTime) == false`
- `0x180034d23`: `hr = pNtServiceFunctions->WLIDCCreateContextEx( L"", c_identityProviderApplicationId, CREATECONTEXT_SET_APP_IDENTITY, &serviceHandle)`
- `0x180034dcf`: `hr = pNtServiceFunctions->WLIDCUpdateToken( serviceHandle, &tokenParam)`
- `0x180034e12`: `hr = pNtServiceFunctions->WLIDCPersistCredential( serviceHandle, PPCRL_CREDTYPE_PASSWORD, 0)`

## pseudocode

```c
__int64 __fastcall MSACredentialManagerImplementation::SaveAuthStateInternal(
        MSACredentialManagerImplementation *this,
        struct IClientApiExecutionContext *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        unsigned __int8 *a7)
{
  __int64 v7; // rax
  __int64 v11; // rbx
  const unsigned __int16 *v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  int v16; // r9d
  const char *v17; // rax
  unsigned int v18; // r8d
  __int64 v19; // rax
  __int64 (__fastcall *v20)(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64, _QWORD *); // rax
  int v21; // eax
  const char *v22; // rcx
  unsigned int v23; // r8d
  int v24; // eax
  __int64 v25; // rax
  unsigned int v26; // ebx
  char *v28; // [rsp+20h] [rbp-91h]
  _QWORD v29[3]; // [rsp+30h] [rbp-81h] BYREF
  _QWORD v30[5]; // [rsp+48h] [rbp-69h] BYREF
  _BYTE v31[16]; // [rsp+70h] [rbp-41h] BYREF
  const wchar_t *v32; // [rsp+80h] [rbp-31h]
  const unsigned __int16 *v33; // [rsp+88h] [rbp-29h]
  unsigned int v34; // [rsp+90h] [rbp-21h]
  unsigned __int8 *v35; // [rsp+98h] [rbp-19h]
  int v36; // [rsp+A0h] [rbp-11h]
  const unsigned __int16 *v37; // [rsp+A8h] [rbp-9h]
  const unsigned __int16 *v38; // [rsp+B0h] [rbp-1h]
  int v39; // [rsp+108h] [rbp+57h] BYREF
  int v40; // [rsp+110h] [rbp+5Fh] BYREF

  v7 = *(_QWORD *)a2;
  v39 = 0;
  v11 = (*(__int64 (__fastcall **)(struct IClientApiExecutionContext *))(v7 + 16))(a2);
  v30[2] = 17;
  v30[1] = &v39;
  v30[0] = "MSACredentialManagerImplementation::SaveAuthStateInternal";
  v30[3] = qword_18006B510;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
    "MSACredentialManagerImplementation::SaveAuthStateInternal",
    (const char *)0x1CD,
    0,
    (const unsigned __int16 *)v28);
  if ( !a3 || !*a3 )
  {
    v17 = "IsNullOrEmpty(daToken) == false";
    v18 = 463;
    goto LABEL_26;
  }
  if ( !a4 || !*a4 )
  {
    v17 = "IsNullOrEmpty(daTokenCreationTime) == false";
    v18 = 464;
    goto LABEL_26;
  }
  v12 = a5;
  if ( !a5 || !*a5 )
  {
    v17 = "IsNullOrEmpty(daTokenExpiryTime) == false";
    v18 = 465;
LABEL_26:
    v16 = -2147024809;
    goto LABEL_27;
  }
  v13 = *(_QWORD *)a2;
  v40 = 0;
  v14 = (*(__int64 (__fastcall **)(struct IClientApiExecutionContext *))(v13 + 32))(a2);
  v15 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v14 + 8LL))(v14, &v40, 0);
  if ( v15 >= 0 )
  {
    if ( !v40 )
    {
      v16 = -2147023579;
      v17 = "hr = HRESULT_FROM_WIN32(ERROR_NO_SUCH_USER)";
      v18 = 472;
LABEL_27:
      v39 = v16;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
        "MSACredentialManagerImplementation::SaveAuthStateInternal",
        v18,
        v16,
        v17);
      goto LABEL_28;
    }
    v19 = *(_QWORD *)v11;
    v29[0] = 0;
    v29[2] = v11;
    v20 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64, _QWORD *))(v19 + 48);
    v29[1] = 0;
    v21 = v20(v11, &qword_180063440, L"{2a2059e7-a58a-445c-befe-6a173ffe7ffd}", 0x800000, v29);
    v39 = v21;
    if ( v21 >= 0 )
    {
      memset_0(v31, 0, 0x48u);
      v33 = a3;
      v32 = L"http://Passport.NET/tb";
      v34 = a6;
      v35 = a7;
      if ( a7 && *a7 || (v24 = MsaDevice_UseXTokenBasedSessionKey(), v36 = 0, v24 != 1) )
        v36 = 1;
      v25 = *(_QWORD *)v11;
      v37 = a4;
      v38 = v12;
      v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *, _QWORD))(v25 + 208))(v11, v29[0], v31, 0);
      v39 = v21;
      if ( v21 >= 0 )
      {
        v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)v11 + 200LL))(
                v11,
                v29[0],
                L"ps:password",
                0,
                0);
        v39 = v21;
        if ( v21 >= 0 )
          goto LABEL_14;
        v22 = "hr = pNtServiceFunctions->WLIDCPersistCredential( serviceHandle, PPCRL_CREDTYPE_PASSWORD, 0)";
        v23 = 520;
      }
      else
      {
        v22 = "hr = pNtServiceFunctions->WLIDCUpdateToken( serviceHandle, &tokenParam)";
        v23 = 513;
      }
    }
    else
    {
      v22 = "hr = pNtServiceFunctions->WLIDCCreateContextEx( L\"\", c_identityProviderApplicationId, CREATECONTEXT_SET_AP"
            "P_IDENTITY, &serviceHandle)";
      v23 = 486;
    }
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
      "MSACredentialManagerImplementation::SaveAuthStateInternal",
      v23,
      v21,
      v22);
LABEL_14:
    Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>(v29);
    goto LABEL_28;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
    "MSACredentialManagerImplementation::SaveAuthStateInternal",
    0x1D5u,
    v15,
    "pExecutionContext->GetSystemStoreLiteFunctions()->IsConnected(&isConnected, nullptr)");
LABEL_28:
  v26 = v39;
  CTraceFuncW<long>::~CTraceFuncW<long>(v30);
  return v26;
}

```

## disassembly

```asm
0x180034bb0  mov     [rsp-8+arg_0], rbx
0x180034bb5  push    rbp
0x180034bb6  push    rsi
0x180034bb7  push    rdi
0x180034bb8  push    r12
0x180034bba  push    r13
0x180034bbc  push    r14
0x180034bbe  push    r15
0x180034bc0  lea     rbp, [rsp-0Fh]
0x180034bc5  sub     rsp, 0C0h
0x180034bcc  mov     rax, [rdx]
0x180034bcf  xor     r12d, r12d
0x180034bd2  mov     rcx, rdx
0x180034bd5  mov     [rbp+3Fh+arg_8], r12d
0x180034bd9  mov     rsi, r9
0x180034bdc  mov     r14, r8
0x180034bdf  mov     r15, rdx
0x180034be2  mov     rax, [rax+10h]
0x180034be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034beb  mov     rbx, rax
0x180034bee  mov     [rbp+3Fh+var_98], 11h
0x180034bf6  lea     rax, [rbp+3Fh+arg_8]
0x180034bfa  xor     r9d, r9d; unsigned int
0x180034bfd  mov     [rbp+3Fh+var_A0], rax
0x180034c01  lea     r13, aMsacredentialm_1; "MSACredentialManagerImplementation::Sav"...
0x180034c08  lea     rax, qword_18006B510
0x180034c0f  mov     [rbp+3Fh+var_A8], r13
0x180034c13  lea     rdi, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180034c1a  mov     [rbp+3Fh+var_90], rax
0x180034c1e  mov     r8d, 1CDh; char *
0x180034c24  mov     rdx, r13; char *
0x180034c27  mov     rcx, rdi; this
0x180034c2a  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180034c2f  test    r14, r14
0x180034c32  jz      loc_180034E49
0x180034c38  cmp     [r14], r12w
0x180034c3c  jz      loc_180034E49
0x180034c42  test    rsi, rsi
0x180034c45  jz      loc_180034E3A
0x180034c4b  cmp     [rsi], r12w
0x180034c4f  jz      loc_180034E3A
0x180034c55  mov     rdi, [rbp+3Fh+arg_20]
0x180034c59  test    rdi, rdi
0x180034c5c  jz      loc_180034E24
0x180034c62  cmp     [rdi], r12w
0x180034c66  jz      loc_180034E24
0x180034c6c  mov     rax, [r15]
0x180034c6f  mov     rcx, r15
0x180034c72  mov     [rbp+3Fh+arg_10], r12d
0x180034c76  mov     rax, [rax+20h]
0x180034c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c7f  mov     r9, rax
0x180034c82  lea     rdx, [rbp+3Fh+arg_10]
0x180034c86  xor     r8d, r8d
0x180034c89  mov     rcx, [rax]
0x180034c8c  mov     rax, [rcx+8]
0x180034c90  mov     rcx, r9
0x180034c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c98  test    eax, eax
0x180034c9a  jns     short loc_180034CBD
0x180034c9c  lea     r8, aPexecutioncont; "pExecutionContext->GetSystemStoreLiteFu"...
0x180034ca3  mov     r9d, eax
0x180034ca6  mov     [rsp+0F0h+var_D0], r8
0x180034cab  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180034cb2  mov     r8d, 1D5h
0x180034cb8  jmp     loc_180034E68
0x180034cbd  cmp     [rbp+3Fh+arg_10], r12d
0x180034cc1  jnz     short loc_180034CE2
0x180034cc3  mov     r9d, 80070525h
0x180034cc9  lea     rax, aHrHresultFromW_0; "hr = HRESULT_FROM_WIN32(ERROR_NO_SUCH_U"...
0x180034cd0  mov     r8d, 1D8h
0x180034cd6  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180034cdd  jmp     loc_180034E5F
0x180034ce2  mov     rax, [rbx]
0x180034ce5  lea     rcx, [rsp+0F0h+var_C0]
0x180034cea  mov     [rsp+0F0h+var_D0], rcx
0x180034cef  lea     r8, a2a2059e7A58a44; "{2a2059e7-a58a-445c-befe-6a173ffe7ffd}"
0x180034cf6  mov     r9d, 800000h
0x180034cfc  mov     [rsp+0F0h+var_C0], r12
0x180034d01  lea     rdx, qword_180063440
0x180034d08  mov     [rbp+3Fh+var_B0], rbx
0x180034d0c  mov     rax, [rax+30h]
0x180034d10  mov     rcx, rbx
0x180034d13  mov     [rbp+3Fh+var_B8], r12
0x180034d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d1c  mov     [rbp+3Fh+arg_8], eax
0x180034d1f  test    eax, eax
0x180034d21  jns     short loc_180034D56
0x180034d23  lea     rcx, aHrPntservicefu_1; "hr = pNtServiceFunctions->WLIDCCreateCo"...
0x180034d2a  mov     r8d, 1E6h; unsigned int
0x180034d30  mov     [rsp+0F0h+var_D0], rcx; char *
0x180034d35  mov     r9d, eax; int
0x180034d38  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180034d3f  mov     rdx, r13; char *
0x180034d42  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180034d47  lea     rcx, [rsp+0F0h+var_C0]
0x180034d4c  call    ??1?$Auto@PEAXVWLIDHandleFunctor@@VILiveIdNtService@@@@QEAA@XZ; Auto<void *,WLIDHandleFunctor,ILiveIdNtService>::~Auto<void *,WLIDHandleFunctor,ILiveIdNtService>(void)
0x180034d51  jmp     loc_180034E70
0x180034d56  xor     edx, edx; Val
0x180034d58  lea     rcx, [rbp+3Fh+var_80]; void *
0x180034d5c  lea     r8d, [rdx+48h]; Size
0x180034d60  call    memset_0
0x180034d65  lea     rax, aHttpPassportNe_0; "http://Passport.NET/tb"
0x180034d6c  mov     [rbp+3Fh+var_68], r14
0x180034d70  mov     [rbp+3Fh+var_70], rax
0x180034d74  mov     eax, [rbp+3Fh+arg_28]
0x180034d77  mov     [rbp+3Fh+var_60], eax
0x180034d7a  mov     rax, [rbp+3Fh+arg_30]
0x180034d7e  mov     [rbp+3Fh+var_58], rax
0x180034d82  test    rax, rax
0x180034d85  jz      short loc_180034D8C
0x180034d87  cmp     [rax], r12b
0x180034d8a  jnz     short loc_180034D9B
0x180034d8c  call    cs:__imp_MsaDevice_UseXTokenBasedSessionKey
0x180034d92  mov     [rbp+3Fh+var_50], r12d
0x180034d96  cmp     eax, 1
0x180034d99  jz      short loc_180034DA2
0x180034d9b  mov     [rbp+3Fh+var_50], 1
0x180034da2  mov     rax, [rbx]
0x180034da5  lea     r8, [rbp+3Fh+var_80]
0x180034da9  mov     rdx, [rsp+0F0h+var_C0]
0x180034dae  xor     r9d, r9d
0x180034db1  mov     rcx, rbx
0x180034db4  mov     [rbp+3Fh+var_48], rsi
0x180034db8  mov     [rbp+3Fh+var_40], rdi
0x180034dbc  mov     rax, [rax+0D0h]
0x180034dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034dc8  mov     [rbp+3Fh+arg_8], eax
0x180034dcb  test    eax, eax
0x180034dcd  jns     short loc_180034DE1
0x180034dcf  lea     rcx, aHrPntservicefu_0; "hr = pNtServiceFunctions->WLIDCUpdateTo"...
0x180034dd6  mov     r8d, 201h
0x180034ddc  jmp     loc_180034D30
0x180034de1  mov     rax, [rbx]
0x180034de4  lea     r8, aPsPassword; "ps:password"
0x180034deb  mov     rdx, [rsp+0F0h+var_C0]
0x180034df0  xor     r9d, r9d
0x180034df3  mov     rcx, rbx
0x180034df6  mov     [rsp+0F0h+var_D0], r12
0x180034dfb  mov     rax, [rax+0C8h]
0x180034e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e07  mov     [rbp+3Fh+arg_8], eax
0x180034e0a  test    eax, eax
0x180034e0c  jns     loc_180034D47
0x180034e12  lea     rcx, aHrPntservicefu_2; "hr = pNtServiceFunctions->WLIDCPersistC"...
0x180034e19  mov     r8d, 208h
0x180034e1f  jmp     loc_180034D30
0x180034e24  lea     rax, aIsnulloremptyD_2; "IsNullOrEmpty(daTokenExpiryTime) == fal"...
0x180034e2b  mov     r8d, 1D1h
0x180034e31  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180034e38  jmp     short loc_180034E59
0x180034e3a  lea     rax, aIsnulloremptyD_1; "IsNullOrEmpty(daTokenCreationTime) == f"...
0x180034e41  mov     r8d, 1D0h
0x180034e47  jmp     short loc_180034E56
0x180034e49  lea     rax, aIsnulloremptyD_3; "IsNullOrEmpty(daToken) == false"
0x180034e50  mov     r8d, 1CFh; unsigned int
0x180034e56  mov     rcx, rdi; char *
0x180034e59  mov     r9d, 80070057h; int
0x180034e5f  mov     [rsp+0F0h+var_D0], rax; char *
0x180034e64  mov     [rbp+3Fh+arg_8], r9d
0x180034e68  mov     rdx, r13; char *
0x180034e6b  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180034e70  mov     ebx, [rbp+3Fh+arg_8]
0x180034e73  lea     rcx, [rbp+3Fh+var_A8]
0x180034e77  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180034e7c  mov     eax, ebx
0x180034e7e  mov     rbx, [rsp+0F0h+arg_0]
0x180034e86  add     rsp, 0C0h
0x180034e8d  pop     r15
0x180034e8f  pop     r14
0x180034e91  pop     r13
0x180034e93  pop     r12
0x180034e95  pop     rdi
0x180034e96  pop     rsi
0x180034e97  pop     rbp
0x180034e98  retn
```
