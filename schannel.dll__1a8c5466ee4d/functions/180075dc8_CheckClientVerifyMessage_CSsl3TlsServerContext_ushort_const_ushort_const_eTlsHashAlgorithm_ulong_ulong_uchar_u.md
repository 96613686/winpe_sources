# CheckClientVerifyMessage(CSsl3TlsServerContext *,ushort const *,ushort const *,_eTlsHashAlgorithm,ulong,ulong,uchar *,ulong)

- ea: `0x180075dc8`
- end: `0x1800760ea`
- name: `?CheckClientVerifyMessage@@YAJPEAVCSsl3TlsServerContext@@PEBG1W4_eTlsHashAlgorithm@@KKPEAEK@Z`
- size: `802`
- prototype: `__int64 __fastcall(struct CSsl3TlsServerContext *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, ULONG, unsigned __int8 *pbEncoded, DWORD cbEncoded)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007bf6c`

## callees

- `0x1800214f0`
- `0x180021eb0`
- `0x1800597b0`
- `0x18005a160`
- `0x180075dc8`
- `0x1800760f0`
- `0x1800761a4`
- `0x180088a3c`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800760ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800760ac`
- `ntdll!RtlReleaseResource` at `0x180075ebe`
- `ntdll!RtlReleaseResource` at `0x180075f47`
- `ntdll!RtlReleaseResource` at `0x180075ebe`
- `ntdll!RtlReleaseResource` at `0x180075f47`
- `ntdll!RtlAcquireResourceShared` at `0x180075e55`
- `ntdll!RtlAcquireResourceShared` at `0x180075e55`
- `ncrypt!SslComputeClientAuthHash` at `0x180075f33`
- `ncrypt!SslComputeClientAuthHash` at `0x180075f33`
- `bcrypt!BCryptGetProperty` at `0x180075fe6`
- `bcrypt!BCryptGetProperty` at `0x180075fe6`
- `bcrypt!BCryptDestroyKey` at `0x1800760bb`
- `bcrypt!BCryptDestroyKey` at `0x1800760bb`
- `bcrypt!BCryptVerifySignature` at `0x180076085`
- `bcrypt!BCryptVerifySignature` at `0x180076085`

## pseudocode

```c
__int64 __fastcall CheckClientVerifyMessage(
        struct CSsl3TlsServerContext *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        ULONG a6,
        unsigned __int8 *pbEncoded,
        DWORD cbEncoded)
{
  UCHAR *v8; // r15
  const unsigned __int16 **v13; // r12
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int Property; // ebx
  __int64 v18; // r8
  __int64 v19; // rdx
  struct CSsl3TlsServerContext *v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rcx
  unsigned int v23; // eax
  unsigned __int8 *v24; // rsi
  const char *v25; // r14
  int v26; // ecx
  SIZE_T v27; // rcx
  unsigned __int8 *v28; // rax
  unsigned int v29; // eax
  __int64 v30; // r9
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // r9
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-89h] BYREF
  ULONG cbSignature; // [rsp+44h] [rbp-85h] BYREF
  ULONG cbHash; // [rsp+48h] [rbp-81h] BYREF
  __int64 v38; // [rsp+50h] [rbp-79h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+58h] [rbp-71h] BYREF
  ULONG pcbResult[2]; // [rsp+60h] [rbp-69h] BYREF
  const unsigned __int16 *v41; // [rsp+68h] [rbp-61h] BYREF
  __int128 v42; // [rsp+70h] [rbp-59h] BYREF
  UCHAR pbHash[64]; // [rsp+80h] [rbp-49h] BYREF

  v8 = pbEncoded;
  v38 = 0;
  hObject = 0;
  cbHash = 64;
  v13 = 0;
  memset_0(pbHash, 0, sizeof(pbHash));
  v14 = *(_QWORD *)a1;
  v41 = 0;
  v42 = 0;
  (*(void (__fastcall **)(struct CSsl3TlsServerContext *, __int64 *))(v14 + 248))(a1, &v38);
  RtlAcquireResourceShared((PRTL_RESOURCE)(*(_QWORD *)(v38 + 40) + 80LL), 1u);
  *(_QWORD *)pcbResult = *(_QWORD *)(v38 + 32);
  if ( !wcsncmp_0(a2, L"RSA", 3u) )
  {
    if ( a6 == 8 )
    {
      v13 = (const unsigned __int16 **)&v42;
      DWORD2(v42) = a5;
      *(_QWORD *)&v42 = a3;
    }
    else
    {
      if ( a6 != 2 )
      {
        Property = 1359;
        goto LABEL_31;
      }
      v13 = &v41;
      v41 = a3;
    }
  }
  v15 = (*(__int64 (__fastcall **)(struct CSsl3TlsServerContext *, _QWORD))(*(_QWORD *)a1 + 576LL))(a1, a4);
  if ( !v15 )
  {
    RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(v38 + 40) + 80LL));
    Property = 1359;
    v18 = 1359;
    v19 = 1303;
LABEL_6:
    v20 = a1;
LABEL_7:
    LOBYTE(v16) = 80;
    CSslContext::SetErrorAndFatalAlert(v20, v19, v18, v16);
    goto LABEL_31;
  }
  v21 = (__int64 *)*((_QWORD *)a1 + 1);
  if ( v21 )
    v22 = *v21;
  else
    v22 = 0;
  Property = SslComputeClientAuthHash(v22, *(_QWORD *)pcbResult, v15, a2, pbHash, 64, &cbHash, 0);
  RtlReleaseResource((PRTL_RESOURCE)(*(_QWORD *)(v38 + 40) + 80LL));
  v20 = a1;
  if ( Property )
  {
    v18 = Property;
    v19 = 1303;
    goto LABEL_7;
  }
  v23 = ConvertPubKeyToBcryptHdl(a1, a2, &hObject);
  Property = v23;
  if ( v23 )
  {
    v18 = v23;
    v19 = 1304;
    goto LABEL_6;
  }
  v24 = 0;
  if ( !wcsncmp_0(a2, L"RSA", 3u) )
  {
    v31 = cbEncoded;
  }
  else
  {
    *(_DWORD *)pbOutput = 0;
    pcbResult[0] = 0;
    v25 = (const char *)(wcsncmp_0(a2, L"DSA", 3u) != 0 ? 47LL : 40LL);
    Property = BCryptGetProperty(hObject, L"KeyLength", pbOutput, 4u, pcbResult, 0);
    if ( Property )
      goto LABEL_31;
    v26 = ((pbOutput[0] & 7) != 0) + (*(_DWORD *)pbOutput >> 3);
    if ( !v26 )
      goto LABEL_31;
    v27 = (unsigned int)(2 * v26);
    cbSignature = v27;
    v28 = (unsigned __int8 *)SPExternalAlloc(v27);
    v24 = v28;
    if ( !v28 )
    {
      Property = 14;
      goto LABEL_31;
    }
    v29 = DecodeSigAndReverse(pbEncoded, cbEncoded, v28, &cbSignature, v25);
    Property = v29;
    if ( v29 )
    {
      LOBYTE(v30) = 50;
      CSslContext::SetErrorAndFatalAlert(a1, 1305, v29, v30);
LABEL_30:
      LocalFree(v24);
      goto LABEL_31;
    }
    v31 = cbSignature;
    v8 = v24;
  }
  v32 = BCryptVerifySignature(hObject, v13, pbHash, cbHash, v8, v31, a6);
  Property = v32;
  if ( v32 )
  {
    LOBYTE(v33) = 51;
    CSslContext::SetErrorAndFatalAlert(a1, 1306, v32, v33);
  }
  if ( v24 )
    goto LABEL_30;
LABEL_31:
  if ( hObject )
    BCryptDestroyKey(hObject);
  return Property;
}

```

## disassembly

```asm
0x180075dc8  mov     [rsp-8+arg_10], rbx
0x180075dcd  push    rbp
0x180075dce  push    rsi
0x180075dcf  push    rdi
0x180075dd0  push    r12
0x180075dd2  push    r13
0x180075dd4  push    r14
0x180075dd6  push    r15
0x180075dd8  lea     rbp, [rsp-7]
0x180075ddd  sub     rsp, 0D0h
0x180075de4  mov     rax, cs:__security_cookie
0x180075deb  xor     rax, rsp
0x180075dee  mov     [rbp+37h+var_40], rax
0x180075df2  mov     r15, [rbp+37h+pbEncoded]
0x180075df6  xor     r13d, r13d
0x180075df9  mov     rbx, r8
0x180075dfc  mov     [rbp+37h+var_B0], r13
0x180075e00  mov     r14, rdx
0x180075e03  mov     [rbp+37h+hObject], r13
0x180075e07  mov     rdi, rcx
0x180075e0a  xor     edx, edx; Val
0x180075e0c  lea     eax, [r13+40h]
0x180075e10  mov     esi, r9d
0x180075e13  mov     r8d, eax; Size
0x180075e16  mov     [rsp+100h+cbHash], eax
0x180075e1a  lea     rcx, [rbp+37h+pbHash]; void *
0x180075e1e  mov     r12d, r13d
0x180075e21  call    memset_0
0x180075e26  mov     rax, [rdi]
0x180075e29  lea     rdx, [rbp+37h+var_B0]
0x180075e2d  xorps   xmm0, xmm0
0x180075e30  mov     [rbp+37h+var_98], r13
0x180075e34  mov     rcx, rdi
0x180075e37  movups  [rbp+37h+var_90], xmm0
0x180075e3b  mov     rax, [rax+0F8h]
0x180075e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075e47  mov     rax, [rbp+37h+var_B0]
0x180075e4b  mov     dl, 1; Wait
0x180075e4d  mov     rcx, [rax+28h]
0x180075e51  add     rcx, 50h ; 'P'; Resource
0x180075e55  call    cs:__imp_RtlAcquireResourceShared
0x180075e5b  mov     rax, [rbp+37h+var_B0]
0x180075e5f  lea     r8d, [r13+3]; MaxCount
0x180075e63  lea     rdx, aRsa; "RSA"
0x180075e6a  mov     rcx, r14; String1
0x180075e6d  mov     rax, [rax+20h]
0x180075e71  mov     qword ptr [rbp+37h+var_A0], rax
0x180075e75  call    wcsncmp_0
0x180075e7a  mov     r13d, [rbp+37h+arg_28]
0x180075e7e  test    eax, eax
0x180075e80  jnz     short loc_180075E96
0x180075e82  cmp     r13d, 8
0x180075e86  jnz     short loc_180075EDF
0x180075e88  mov     eax, [rbp+37h+arg_20]
0x180075e8b  lea     r12, [rbp+37h+var_90]
0x180075e8f  mov     dword ptr [rbp+37h+var_90+8], eax
0x180075e92  mov     qword ptr [rbp+37h+var_90], rbx
0x180075e96  mov     rax, [rdi]
0x180075e99  mov     edx, esi
0x180075e9b  mov     rcx, rdi
0x180075e9e  mov     rax, [rax+240h]
0x180075ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075eaa  mov     r8, rax
0x180075ead  test    rax, rax
0x180075eb0  jnz     short loc_180075EF9
0x180075eb2  mov     rax, [rbp+37h+var_B0]
0x180075eb6  mov     rcx, [rax+28h]
0x180075eba  add     rcx, 50h ; 'P'; Resource
0x180075ebe  call    cs:__imp_RtlReleaseResource
0x180075ec4  mov     ebx, 54Fh
0x180075ec9  mov     r8d, ebx
0x180075ecc  lea     edx, [rbx-38h]
0x180075ecf  mov     rcx, rdi
0x180075ed2  mov     r9b, 50h ; 'P'
0x180075ed5  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x180075eda  jmp     loc_1800760B2
0x180075edf  cmp     r13d, 2
0x180075ee3  jnz     short loc_180075EEF
0x180075ee5  lea     r12, [rbp+37h+var_98]
0x180075ee9  mov     [rbp+37h+var_98], rbx
0x180075eed  jmp     short loc_180075E96
0x180075eef  mov     ebx, 54Fh
0x180075ef4  jmp     loc_1800760B2
0x180075ef9  mov     rax, [rdi+8]
0x180075efd  test    rax, rax
0x180075f00  jz      short loc_180075F07
0x180075f02  mov     rcx, [rax]
0x180075f05  jmp     short loc_180075F09
0x180075f07  xor     ecx, ecx
0x180075f09  mov     rdx, qword ptr [rbp+37h+var_A0]
0x180075f0d  lea     rax, [rsp+100h+cbHash]
0x180075f12  mov     [rsp+100h+var_C8], 0
0x180075f1a  mov     r9, r14
0x180075f1d  mov     qword ptr [rsp+100h+var_D0], rax
0x180075f22  lea     rax, [rbp+37h+pbHash]
0x180075f26  mov     [rsp+100h+dwFlags], 40h ; '@'
0x180075f2e  mov     [rsp+100h+pcbResult], rax
0x180075f33  call    cs:__imp_SslComputeClientAuthHash
0x180075f39  mov     rcx, [rbp+37h+var_B0]
0x180075f3d  mov     ebx, eax
0x180075f3f  mov     rcx, [rcx+28h]
0x180075f43  add     rcx, 50h ; 'P'; Resource
0x180075f47  call    cs:__imp_RtlReleaseResource
0x180075f4d  mov     rcx, rdi; struct CSslContext *
0x180075f50  test    ebx, ebx
0x180075f52  jz      short loc_180075F61
0x180075f54  mov     r8d, ebx
0x180075f57  mov     edx, 517h
0x180075f5c  jmp     loc_180075ED2
0x180075f61  lea     r8, [rbp+37h+hObject]; void **
0x180075f65  mov     rdx, r14; unsigned __int16 *
0x180075f68  call    ?ConvertPubKeyToBcryptHdl@@YAJPEAVCSslContext@@PEBGPEAPEAX@Z; ConvertPubKeyToBcryptHdl(CSslContext *,ushort const *,void * *)
0x180075f6d  mov     ebx, eax
0x180075f6f  test    eax, eax
0x180075f71  jz      short loc_180075F80
0x180075f73  mov     r8d, eax
0x180075f76  mov     edx, 518h
0x180075f7b  jmp     loc_180075ECF
0x180075f80  xor     esi, esi
0x180075f82  lea     rdx, aRsa; "RSA"
0x180075f89  mov     rcx, r14; String1
0x180075f8c  lea     ebx, [rsi+3]
0x180075f8f  mov     r8d, ebx; MaxCount
0x180075f92  call    wcsncmp_0
0x180075f97  test    eax, eax
0x180075f99  jz      loc_180076064
0x180075f9f  mov     r8d, ebx; MaxCount
0x180075fa2  mov     dword ptr [rsp+100h+pbOutput], esi
0x180075fa6  lea     rdx, aDsa; "DSA"
0x180075fad  mov     [rbp+37h+var_A0], esi
0x180075fb0  mov     rcx, r14; String1
0x180075fb3  call    wcsncmp_0
0x180075fb8  mov     rcx, [rbp+37h+hObject]; hObject
0x180075fbc  lea     r9d, [rsi+4]; cbOutput
0x180075fc0  neg     eax
0x180075fc2  mov     [rsp+100h+dwFlags], esi; dwFlags
0x180075fc6  lea     rax, [rbp+37h+var_A0]
0x180075fca  sbb     r14, r14
0x180075fcd  mov     [rsp+100h+pcbResult], rax; pcbResult
0x180075fd2  and     r14d, 7
0x180075fd6  lea     r8, [rsp+100h+pbOutput]; pbOutput
0x180075fdb  lea     rdx, aKeylength; "KeyLength"
0x180075fe2  add     r14, 28h ; '('
0x180075fe6  call    cs:__imp_BCryptGetProperty
0x180075fec  mov     ebx, eax
0x180075fee  test    eax, eax
0x180075ff0  jnz     loc_1800760B2
0x180075ff6  mov     ecx, dword ptr [rsp+100h+pbOutput]
0x180075ffa  mov     eax, esi
0x180075ffc  test    cl, 7
0x180075fff  setnz   al
0x180076002  shr     ecx, 3
0x180076005  add     ecx, eax
0x180076007  jz      loc_1800760B2
0x18007600d  add     ecx, ecx; uBytes
0x18007600f  mov     [rsp+100h+cbSignature], ecx
0x180076013  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x180076018  mov     rsi, rax
0x18007601b  test    rax, rax
0x18007601e  jnz     short loc_180076028
0x180076020  lea     ebx, [rax+0Eh]
0x180076023  jmp     loc_1800760B2
0x180076028  mov     edx, [rbp+37h+cbEncoded]; cbEncoded
0x18007602b  lea     r9, [rsp+100h+cbSignature]; unsigned int *
0x180076030  mov     r8, rsi; unsigned __int8 *
0x180076033  mov     [rsp+100h+pcbResult], r14; char *
0x180076038  mov     rcx, r15; pbEncoded
0x18007603b  call    ?DecodeSigAndReverse@@YAJPEAEK0PEAKPEBD@Z; DecodeSigAndReverse(uchar *,ulong,uchar *,ulong *,char const *)
0x180076040  mov     ebx, eax
0x180076042  test    eax, eax
0x180076044  jz      short loc_18007605B
0x180076046  mov     r9b, 32h ; '2'
0x180076049  mov     r8d, eax
0x18007604c  mov     edx, 519h
0x180076051  mov     rcx, rdi
0x180076054  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x180076059  jmp     short loc_1800760A9
0x18007605b  mov     eax, [rsp+100h+cbSignature]
0x18007605f  mov     r15, rsi
0x180076062  jmp     short loc_180076067
0x180076064  mov     eax, [rbp+37h+cbEncoded]
0x180076067  mov     r9d, [rsp+100h+cbHash]; cbHash
0x18007606c  lea     r8, [rbp+37h+pbHash]; pbHash
0x180076070  mov     rcx, [rbp+37h+hObject]; hKey
0x180076074  mov     rdx, r12; pPaddingInfo
0x180076077  mov     [rsp+100h+var_D0], r13d; dwFlags
0x18007607c  mov     [rsp+100h+dwFlags], eax; cbSignature
0x180076080  mov     [rsp+100h+pcbResult], r15; pbSignature
0x180076085  call    cs:__imp_BCryptVerifySignature
0x18007608b  mov     ebx, eax
0x18007608d  test    eax, eax
0x18007608f  jz      short loc_1800760A4
0x180076091  mov     r9b, 33h ; '3'
0x180076094  mov     r8d, eax
0x180076097  mov     edx, 51Ah
0x18007609c  mov     rcx, rdi
0x18007609f  call    ?SetErrorAndFatalAlert@CSslContext@@QEAAXW4eSslErrorState@@KE@Z; CSslContext::SetErrorAndFatalAlert(eSslErrorState,ulong,uchar)
0x1800760a4  test    rsi, rsi
0x1800760a7  jz      short loc_1800760B2
0x1800760a9  mov     rcx, rsi; hMem
0x1800760ac  call    cs:__imp_LocalFree
0x1800760b2  mov     rcx, [rbp+37h+hObject]; hKey
0x1800760b6  test    rcx, rcx
0x1800760b9  jz      short loc_1800760C1
0x1800760bb  call    cs:__imp_BCryptDestroyKey
0x1800760c1  mov     eax, ebx
0x1800760c3  mov     rcx, [rbp+37h+var_40]
0x1800760c7  xor     rcx, rsp; StackCookie
0x1800760ca  call    __security_check_cookie
0x1800760cf  mov     rbx, [rsp+100h+arg_10]
0x1800760d7  add     rsp, 0D0h
0x1800760de  pop     r15
0x1800760e0  pop     r14
0x1800760e2  pop     r13
0x1800760e4  pop     r12
0x1800760e6  pop     rdi
0x1800760e7  pop     rsi
0x1800760e8  pop     rbp
0x1800760e9  retn
```
