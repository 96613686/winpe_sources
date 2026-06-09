# CWLIDCCHelperWithSsp::GetAuthDataFromAuthIdEx2(uchar *,ulong,_UNICODE_STRING *,_GUID *,_UNICODE_STRING *)

- ea: `0x18000fe40`
- end: `0x1800102ca`
- name: `?GetAuthDataFromAuthIdEx2@CWLIDCCHelperWithSsp@@SAJPEAEKPEAU_UNICODE_STRING@@PEAU_GUID@@1@Z`
- size: `1162`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *@<rcx>, unsigned int@<edx>, struct _UNICODE_STRING *@<r8>, struct _GUID *@<r9>, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025bbc`

## callees

- `0x180004824`
- `0x180004910`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18000fe40`
- `0x1800102d0`
- `0x180015d2c`
- `0x1800392b0`
- `0x18003af00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800102a7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800102a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800101e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800101f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800101e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800101f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ffef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010080`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800100f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ffef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010080`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800100f4`
- `SspiCli!SspiCopyAuthIdentity` at `0x18000ff3d`
- `SspiCli!SspiCopyAuthIdentity` at `0x18000ff3d`
- `SspiCli!SspiFreeAuthIdentity` at `0x18001023f`
- `SspiCli!SspiFreeAuthIdentity` at `0x180010256`
- `SspiCli!SspiFreeAuthIdentity` at `0x18001023f`
- `SspiCli!SspiFreeAuthIdentity` at `0x180010256`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x18000ff13`
- `SspiCli!SspiUnmarshalAuthIdentity` at `0x18000ff13`

## string_xrefs

- `0x18001002e`: `hr = SafeCopyMemory(pszAuthData, cbAuthDataWithNullTerminator, reinterpret_cast<PBYTE>(CredUICred) + CredUICred->AuthInfo.ByteArrayOffset, cbAuthData)`
- `0x180010185`: `hr = SafeCopyMemory(pszUserName, cbUserNameWithNullTerminator, pDeserializedCred->UserOffset + reinterpret_cast<PBYTE>(pDeserializedCred), UserName->Length)`
- `0x1800101b1`: `hr = SafeCopyMemory(pszAuthData, cbAuthDataWithNullTerminator, AuthData->CredData.ByteArrayOffset + (PBYTE)PackedCredentials, cbAuthData)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWLIDCCHelperWithSsp::GetAuthDataFromAuthIdEx2(
        unsigned __int8 *a1,
        unsigned int a2,
        struct _UNICODE_STRING *a3,
        struct _GUID *a4,
        struct _UNICODE_STRING *a5)
{
  struct _UNICODE_STRING *v5; // r13
  WCHAR *v8; // r14
  char *v9; // r12
  struct _GUID *v10; // rsi
  const struct _GUID *v11; // rcx
  char *v12; // r15
  unsigned int v13; // ecx
  unsigned int v14; // eax
  rsize_t v15; // rbx
  unsigned int v16; // r13d
  WCHAR *v17; // rax
  WCHAR *v18; // rdi
  const char *v19; // rax
  unsigned int v20; // r8d
  WCHAR *v21; // rax
  unsigned int v22; // r12d
  char *v23; // rcx
  unsigned int v24; // eax
  struct _UNICODE_STRING *v25; // r14
  unsigned int v26; // ebx
  const unsigned __int16 *v28; // [rsp+28h] [rbp-71h]
  __int64 v29; // [rsp+28h] [rbp-71h]
  int v30; // [rsp+38h] [rbp-61h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+40h] [rbp-59h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy; // [rsp+48h] [rbp-51h] BYREF
  struct _UNICODE_STRING v33; // [rsp+50h] [rbp-49h] BYREF
  void **v34; // [rsp+60h] [rbp-39h] BYREF
  HMODULE hLibModule; // [rsp+68h] [rbp-31h]
  int *v36[4]; // [rsp+70h] [rbp-29h] BYREF
  _QWORD v37[11]; // [rsp+90h] [rbp-9h] BYREF

  v5 = a3;
  v30 = 0;
  *(_QWORD *)&v33.Length = 2228256;
  ppAuthIdentity = 0;
  AuthDataCopy = 0;
  v34 = &SspiFunctions::`vftable';
  hLibModule = 0;
  v37[0] = "CWLIDCCHelperWithSsp::GetAuthDataFromAuthIdEx2";
  v37[1] = &v30;
  v37[2] = 0;
  v37[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\wlidcchelperwithssp.cpp",
    "CWLIDCCHelperWithSsp::GetAuthDataFromAuthIdEx2",
    (const char *)0x33,
    0,
    v28);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v36,
    "CWLIDCCHelperWithSsp::GetAuthDataFromAuthIdEx2",
    &v30,
    0xCu,
    &qword_180063E30);
  v33.Buffer = (PWSTR)L"MicrosoftAccount";
  v30 = CWLIDCCHelper::ValidateAuthIdEx2(a1, a2, &v33);
  if ( v30 < 0 || SspiUnmarshalAuthIdentity(a2, (char *)a1, &ppAuthIdentity) < 0 )
    goto LABEL_43;
  if ( (*((_BYTE *)ppAuthIdentity + 36) & 0x40) == 0 )
  {
    v30 = -805305717;
    LODWORD(v29) = -805305717;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\wlidcchelperwithssp.cpp",
      0x63u,
      L"Unencrypted auth identity found. 0x%0x",
      v29);
    goto LABEL_43;
  }
  v8 = 0;
  if ( SspiCopyAuthIdentity(ppAuthIdentity, &AuthDataCopy) < 0
    || (int)SspiFunctions::SspiDecryptAuthIdentityEx((SspiFunctions *)&v34, 1u, AuthDataCopy) < 0 )
  {
    goto LABEL_41;
  }
  v9 = (char *)AuthDataCopy + *((unsigned int *)AuthDataCopy + 7);
  v10 = (struct _GUID *)(v9 + 4);
  if ( (unsigned int)InlineIsEqualGUID((const struct _GUID *)(v9 + 4), &stru_180063EE0) )
  {
    if ( *((_WORD *)v9 + 12) >= 0x10u )
    {
      v12 = &v9[*((unsigned int *)v9 + 5)];
      v13 = *((unsigned __int16 *)v12 + 1);
      if ( (unsigned __int16)v13 <= *((_WORD *)v9 + 12) && *(_WORD *)v12 <= (unsigned __int16)v13 )
      {
        v14 = *((_DWORD *)v12 + 1);
        LODWORD(v15) = *((unsigned __int16 *)v12 + 4);
        if ( (unsigned int)v15 + v14 >= v14
          && (unsigned int)v15 + v14 <= v13
          && (v15 & 1) == 0
          && (unsigned int)v15 <= 0x7FFD )
        {
          v16 = v15 + 2;
          v17 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(v15 + 2));
          v18 = v17;
          if ( v17 )
          {
            if ( !memcpy_s_3(v17, v16, &v12[*((unsigned int *)v12 + 1)], (unsigned int)v15) )
            {
              v30 = 0;
              v18[(unsigned __int64)(unsigned int)v15 >> 1] = 0;
              goto LABEL_27;
            }
            v19 = "hr = SafeCopyMemory(pszAuthData, cbAuthDataWithNullTerminator, reinterpret_cast<PBYTE>(CredUICred) + C"
                  "redUICred->AuthInfo.ByteArrayOffset, cbAuthData)";
            v20 = 144;
            goto LABEL_37;
          }
          goto LABEL_23;
        }
      }
    }
    goto LABEL_41;
  }
  if ( !(unsigned int)InlineIsEqualGUID(v11, &SEC_WINNT_AUTH_DATA_TYPE_PASSWORD) )
    goto LABEL_41;
  if ( *((_DWORD *)v9 + 5) )
  {
    v15 = *((unsigned __int16 *)v9 + 12);
    if ( (v15 & 1) == 0 && (unsigned int)v15 <= 0x7FFD )
    {
      v16 = v15 + 2;
      v21 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)(v15 + 2));
      v18 = v21;
      if ( v21 )
      {
        if ( !memcpy_s_3(v21, v16, &v9[*((unsigned int *)v9 + 5)], v15) )
        {
          v30 = 0;
          v18[v15 >> 1] = 0;
LABEL_27:
          if ( (*((_BYTE *)ppAuthIdentity + 16) & 1) != 0 )
          {
            v30 = -2147024809;
          }
          else
          {
            v22 = *((unsigned __int16 *)ppAuthIdentity + 8) + 2;
            v8 = (WCHAR *)LocalAlloc(0x40u, v22);
            if ( v8 )
            {
              v23 = (char *)ppAuthIdentity;
              v24 = *((unsigned __int16 *)ppAuthIdentity + 8);
              a3->Length = v24;
              a3->MaximumLength = v22;
              if ( !memcpy_s_3(v8, v22, &v23[*((unsigned int *)v23 + 3)], v24) )
              {
                v30 = 0;
                v8[((unsigned __int64)v22 >> 1) - 1] = 0;
                a3->Buffer = v8;
                v25 = a5;
                a5->MaximumLength = v16;
                a5->Length = v15;
                a5->Buffer = v18;
                *a4 = *v10;
                v30 = 0;
                v5 = a3;
                goto LABEL_44;
              }
              v30 = -2147418113;
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\wlidcchelperwithssp.cpp",
                "CWLIDCCHelperWithSsp::GetAuthDataFromAuthIdEx2",
                0xCDu,
                -2147418113,
                "hr = SafeCopyMemory(pszUserName, cbUserNameWithNullTerminator, pDeserializedCred->UserOffset + reinterpr"
                "et_cast<PBYTE>(pDeserializedCred), UserName->Length)");
            }
            else
            {
              v30 = -2147024882;
            }
          }
          if ( !v18 )
            goto LABEL_39;
          goto LABEL_38;
        }
        v19 = "hr = SafeCopyMemory(pszAuthData, cbAuthDataWithNullTerminator, AuthData->CredData.ByteArrayOffset + (PBYTE"
              ")PackedCredentials, cbAuthData)";
        v20 = 176;
LABEL_37:
        v30 = -2147418113;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\wlidcchelperwithssp.cpp",
          "CWLIDCCHelperWithSsp::GetAuthDataFromAuthIdEx2",
          v20,
          -2147418113,
          v19);
LABEL_38:
        LocalFree(v18);
LABEL_39:
        if ( v8 )
          LocalFree(v8);
        goto LABEL_24;
      }
LABEL_23:
      v30 = -2147024882;
LABEL_24:
      v5 = a3;
      goto LABEL_43;
    }
LABEL_41:
    v30 = -2147024809;
  }
LABEL_43:
  v25 = a5;
LABEL_44:
  if ( AuthDataCopy )
  {
    SspiFreeAuthIdentity(AuthDataCopy);
    AuthDataCopy = 0;
  }
  if ( ppAuthIdentity )
  {
    SspiFreeAuthIdentity(ppAuthIdentity);
    ppAuthIdentity = 0;
  }
  if ( v30 < 0 )
  {
    *v25 = 0;
    *v5 = 0;
  }
  v26 = v30;
  ErrorVerifier::CheckAgainstList((const char *)v36[3], *v36[2], (unsigned __int64)v36[1], v36[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v37);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  return v26;
}

```

## disassembly

```asm
0x18000fe40  mov     rax, rsp
0x18000fe43  mov     [rax+8], rbx
0x18000fe47  mov     [rax+20h], r9
0x18000fe4b  mov     [rax+18h], r8
0x18000fe4f  push    rbp
0x18000fe50  push    rsi
0x18000fe51  push    rdi
0x18000fe52  push    r12
0x18000fe54  push    r13
0x18000fe56  push    r14
0x18000fe58  push    r15
0x18000fe5a  lea     rbp, [rax-57h]
0x18000fe5e  sub     rsp, 0B0h
0x18000fe65  mov     r13, r8
0x18000fe68  mov     ebx, edx
0x18000fe6a  mov     rdi, rcx
0x18000fe6d  xor     r15d, r15d
0x18000fe70  mov     [rbp+4Fh+var_B0], r15d
0x18000fe74  mov     qword ptr [rbp+4Fh+var_98.Length], 220020h
0x18000fe7c  mov     [rbp+4Fh+ppAuthIdentity], r15
0x18000fe80  mov     [rbp+4Fh+AuthDataCopy], r15
0x18000fe84  lea     rax, ??_7SspiFunctions@@6B@; const SspiFunctions::`vftable'
0x18000fe8b  mov     [rbp+4Fh+var_88], rax
0x18000fe8f  mov     [rbp+4Fh+hLibModule], r15
0x18000fe93  lea     rsi, aCwlidcchelperw; "CWLIDCCHelperWithSsp::GetAuthDataFromAu"...
0x18000fe9a  mov     [rbp+4Fh+var_58], rsi
0x18000fe9e  lea     rax, [rbp+4Fh+var_B0]
0x18000fea2  mov     [rbp+4Fh+var_50], rax
0x18000fea6  mov     [rbp+4Fh+var_48], r15
0x18000feaa  mov     [rbp+4Fh+var_40], r15
0x18000feae  xor     r9d, r9d; unsigned int
0x18000feb1  lea     r8d, [r15+33h]; char *
0x18000feb5  mov     rdx, rsi; char *
0x18000feb8  lea     rcx, aOnecoreuapDsEx_10; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18000febf  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000fec4  nop
0x18000fec5  lea     rax, qword_180063E30
0x18000fecc  mov     [rsp+20h], rax; int *
0x18000fed1  lea     r9d, [r15+0Ch]; unsigned __int64
0x18000fed5  lea     r8, [rbp+4Fh+var_B0]; int *
0x18000fed9  mov     rdx, rsi; char *
0x18000fedc  lea     rcx, [rbp+4Fh+var_78]; this
0x18000fee0  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18000fee5  nop
0x18000fee6  lea     rax, Src; "MicrosoftAccount"
0x18000feed  mov     [rbp+4Fh+var_98.Buffer], rax
0x18000fef1  lea     r8, [rbp+4Fh+var_98]; struct _UNICODE_STRING *
0x18000fef5  mov     edx, ebx; unsigned int
0x18000fef7  mov     rcx, rdi; unsigned __int8 *
0x18000fefa  call    ?ValidateAuthIdEx2@CWLIDCCHelper@@SAJPEBEKPEAU_UNICODE_STRING@@@Z; CWLIDCCHelper::ValidateAuthIdEx2(uchar const *,ulong,_UNICODE_STRING *)
0x18000feff  mov     [rbp+4Fh+var_B0], eax
0x18000ff02  test    eax, eax
0x18000ff04  js      loc_180010232
0x18000ff0a  lea     r8, [rbp+4Fh+ppAuthIdentity]; ppAuthIdentity
0x18000ff0e  mov     rdx, rdi; AuthIdentityByteArray
0x18000ff11  mov     ecx, ebx; AuthIdentityLength
0x18000ff13  call    cs:__imp_SspiUnmarshalAuthIdentity
0x18000ff19  test    eax, eax
0x18000ff1b  js      loc_180010232
0x18000ff21  mov     rcx, [rbp+4Fh+ppAuthIdentity]; AuthData
0x18000ff25  mov     eax, [rcx+24h]
0x18000ff28  lea     edi, [r15+40h]
0x18000ff2c  and     eax, edi
0x18000ff2e  test    al, al
0x18000ff30  jz      loc_180010209
0x18000ff36  mov     r14d, r15d
0x18000ff39  lea     rdx, [rbp+4Fh+AuthDataCopy]; AuthDataCopy
0x18000ff3d  call    cs:__imp_SspiCopyAuthIdentity
0x18000ff43  test    eax, eax
0x18000ff45  js      loc_180010200
0x18000ff4b  mov     r8, [rbp+4Fh+AuthDataCopy]; void *
0x18000ff4f  lea     edx, [rdi-3Fh]; unsigned int
0x18000ff52  lea     rcx, [rbp+4Fh+var_88]; this
0x18000ff56  call    ?SspiDecryptAuthIdentityEx@SspiFunctions@@UEAAJKPEAX@Z; SspiFunctions::SspiDecryptAuthIdentityEx(ulong,void *)
0x18000ff5b  test    eax, eax
0x18000ff5d  js      loc_180010200
0x18000ff63  mov     rcx, [rbp+4Fh+AuthDataCopy]
0x18000ff67  mov     r12d, [rcx+1Ch]
0x18000ff6b  add     r12, rcx
0x18000ff6e  lea     rsi, [r12+4]
0x18000ff73  lea     rdx, stru_180063EE0; struct _GUID *
0x18000ff7a  mov     rcx, rsi; struct _GUID *
0x18000ff7d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000ff82  test    eax, eax
0x18000ff84  jz      loc_180010040
0x18000ff8a  cmp     word ptr [rsi+14h], 10h
0x18000ff8f  jb      loc_180010200
0x18000ff95  mov     r15d, [rsi+10h]
0x18000ff99  add     r15, r12
0x18000ff9c  movzx   ecx, word ptr [r15+2]
0x18000ffa1  cmp     cx, [rsi+14h]
0x18000ffa5  ja      loc_180010200
0x18000ffab  cmp     [r15], cx
0x18000ffaf  ja      loc_180010200
0x18000ffb5  mov     eax, [r15+4]
0x18000ffb9  movzx   ebx, word ptr [r15+8]
0x18000ffbe  lea     edx, [rbx+rax]
0x18000ffc1  cmp     edx, eax
0x18000ffc3  jb      loc_180010200
0x18000ffc9  cmp     edx, ecx
0x18000ffcb  ja      loc_180010200
0x18000ffd1  test    bl, 1
0x18000ffd4  jnz     loc_180010200
0x18000ffda  cmp     ebx, 7FFDh
0x18000ffe0  ja      loc_180010200
0x18000ffe6  lea     r13d, [rbx+2]
0x18000ffea  mov     edx, r13d; uBytes
0x18000ffed  mov     ecx, edi; uFlags
0x18000ffef  call    cs:__imp_LocalAlloc
0x18000fff5  mov     rdi, rax
0x18000fff8  test    rax, rax
0x18000fffb  jz      loc_18001008E
0x180010001  mov     r12d, ebx
0x180010004  mov     r8d, [r15+4]
0x180010008  add     r8, r15; Source
0x18001000b  mov     r9d, ebx; SourceSize
0x18001000e  mov     edx, r13d; DestinationSize
0x180010011  mov     rcx, rax; Destination
0x180010014  call    memcpy_s_3
0x180010019  test    eax, eax
0x18001001b  jnz     short loc_18001002E
0x18001001d  mov     [rbp+4Fh+var_B0], r14d
0x180010021  shr     r12, 1
0x180010024  mov     [rdi+r12*2], ax
0x180010029  jmp     loc_1800100CA
0x18001002e  lea     rax, aHrSafecopymemo_0; "hr = SafeCopyMemory(pszAuthData, cbAuth"...
0x180010035  mov     r8d, 90h
0x18001003b  jmp     loc_1800101BE
0x180010040  lea     rdx, SEC_WINNT_AUTH_DATA_TYPE_PASSWORD; struct _GUID *
0x180010047  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001004c  test    eax, eax
0x18001004e  jz      loc_180010200
0x180010054  cmp     [rsi+10h], r15d
0x180010058  jz      loc_180010232
0x18001005e  movzx   ebx, word ptr [rsi+14h]
0x180010062  test    bl, 1
0x180010065  jnz     loc_180010200
0x18001006b  cmp     ebx, 7FFDh
0x180010071  ja      loc_180010200
0x180010077  lea     r13d, [rbx+2]
0x18001007b  mov     edx, r13d; uBytes
0x18001007e  mov     ecx, edi; uFlags
0x180010080  call    cs:__imp_LocalAlloc
0x180010086  mov     rdi, rax
0x180010089  test    rax, rax
0x18001008c  jnz     short loc_18001009E
0x18001008e  mov     [rbp+4Fh+var_B0], 8007000Eh
0x180010095  mov     r13, [rbp+4Fh+arg_10]
0x180010099  jmp     loc_180010232
0x18001009e  mov     r15, rbx
0x1800100a1  mov     r8d, [rsi+10h]
0x1800100a5  add     r8, r12; Source
0x1800100a8  mov     r9, rbx; SourceSize
0x1800100ab  mov     edx, r13d; DestinationSize
0x1800100ae  mov     rcx, rdi; Destination
0x1800100b1  call    memcpy_s_3
0x1800100b6  test    eax, eax
0x1800100b8  jnz     loc_1800101B1
0x1800100be  mov     [rbp+4Fh+var_B0], r14d
0x1800100c2  shr     r15, 1
0x1800100c5  mov     [rdi+r15*2], ax
0x1800100ca  mov     rax, [rbp+4Fh+ppAuthIdentity]
0x1800100ce  test    byte ptr [rax+10h], 1
0x1800100d2  jz      short loc_1800100E0
0x1800100d4  mov     [rbp+4Fh+var_B0], 80070057h
0x1800100db  jmp     loc_1800101AA
0x1800100e0  movzx   r12d, word ptr [rax+10h]
0x1800100e5  add     r12d, 2
0x1800100e9  mov     r15d, r12d
0x1800100ec  mov     edx, r12d; uBytes
0x1800100ef  mov     ecx, 40h ; '@'; uFlags
0x1800100f4  call    cs:__imp_LocalAlloc
0x1800100fa  mov     r14, rax
0x1800100fd  test    rax, rax
0x180010100  jnz     short loc_18001010E
0x180010102  mov     [rbp+4Fh+var_B0], 8007000Eh
0x180010109  jmp     loc_1800101AA
0x18001010e  mov     rcx, [rbp+4Fh+ppAuthIdentity]
0x180010112  movzx   eax, word ptr [rcx+10h]
0x180010116  mov     rdx, [rbp+4Fh+arg_10]
0x18001011a  mov     [rdx], ax
0x18001011d  mov     [rdx+2], r12w
0x180010122  mov     r9d, eax; SourceSize
0x180010125  mov     r8d, [rcx+0Ch]
0x180010129  add     r8, rcx; Source
0x18001012c  mov     rdx, r15; DestinationSize
0x18001012f  mov     rcx, r14; Destination
0x180010132  call    memcpy_s_3
0x180010137  test    eax, eax
0x180010139  jnz     short loc_18001017B
0x18001013b  mov     [rbp+4Fh+var_B0], eax
0x18001013e  shr     r15, 1
0x180010141  mov     [r14+r15*2-2], ax
0x180010147  mov     rax, [rbp+4Fh+arg_10]
0x18001014b  mov     [rax+8], r14
0x18001014f  mov     r14, [rbp+4Fh+arg_20]
0x180010153  mov     [r14+2], r13w
0x180010158  mov     [r14], bx
0x18001015c  mov     [r14+8], rdi
0x180010160  movups  xmm0, xmmword ptr [rsi]
0x180010163  mov     rax, [rbp+4Fh+arg_18]
0x180010167  movdqu  xmmword ptr [rax], xmm0
0x18001016b  mov     [rbp+4Fh+var_B0], 0
0x180010172  mov     r13, [rbp+4Fh+arg_10]
0x180010176  jmp     loc_180010236
0x18001017b  mov     r9d, 8000FFFFh; int
0x180010181  mov     [rbp+4Fh+var_B0], r9d
0x180010185  lea     rax, aHrSafecopymemo_1; "hr = SafeCopyMemory(pszUserName, cbUser"...
0x18001018c  mov     [rsp+20h], rax; char *
0x180010191  mov     r8d, 0CDh; unsigned int
0x180010197  lea     rdx, aCwlidcchelperw; "CWLIDCCHelperWithSsp::GetAuthDataFromAu"...
0x18001019e  lea     rcx, aOnecoreuapDsEx_10; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800101a5  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800101aa  test    rdi, rdi
0x1800101ad  jnz     short loc_1800101E0
0x1800101af  jmp     short loc_1800101E9
0x1800101b1  lea     rax, aHrSafecopymemo_4; "hr = SafeCopyMemory(pszAuthData, cbAuth"...
0x1800101b8  mov     r8d, 0B0h; unsigned int
0x1800101be  mov     r9d, 8000FFFFh; int
0x1800101c4  mov     [rsp+20h], rax; char *
0x1800101c9  mov     [rbp+4Fh+var_B0], r9d
0x1800101cd  lea     rdx, aCwlidcchelperw; "CWLIDCCHelperWithSsp::GetAuthDataFromAu"...
0x1800101d4  lea     rcx, aOnecoreuapDsEx_10; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800101db  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800101e0  mov     rcx, rdi; hMem
0x1800101e3  call    cs:__imp_LocalFree
0x1800101e9  test    r14, r14
0x1800101ec  jz      loc_180010095
0x1800101f2  mov     rcx, r14; hMem
0x1800101f5  call    cs:__imp_LocalFree
0x1800101fb  jmp     loc_180010095
0x180010200  mov     [rbp+4Fh+var_B0], 80070057h
0x180010207  jmp     short loc_180010232
0x180010209  mov     eax, 0D000028Bh
0x18001020e  mov     [rbp+4Fh+var_B0], eax
0x180010211  mov     [rsp+20h], eax
0x180010215  lea     r9, aUnencryptedAut; "Unencrypted auth identity found. 0x%0x"
0x18001021c  mov     r8d, 63h ; 'c'; unsigned int
0x180010222  lea     rdx, aOnecoreuapDsEx_10; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180010229  lea     ecx, [r8-61h]; unsigned __int8
0x18001022d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180010232  mov     r14, [rbp+4Fh+arg_20]
0x180010236  mov     rcx, [rbp+4Fh+AuthDataCopy]; AuthData
0x18001023a  test    rcx, rcx
0x18001023d  jz      short loc_18001024D
0x18001023f  call    cs:__imp_SspiFreeAuthIdentity
0x180010245  mov     [rbp+4Fh+AuthDataCopy], 0
0x18001024d  mov     rcx, [rbp+4Fh+ppAuthIdentity]; AuthData
0x180010251  test    rcx, rcx
0x180010254  jz      short loc_180010264
0x180010256  call    cs:__imp_SspiFreeAuthIdentity
0x18001025c  mov     [rbp+4Fh+ppAuthIdentity], 0
0x180010264  cmp     [rbp+4Fh+var_B0], 0
0x180010268  jge     short loc_180010279
0x18001026a  xorps   xmm0, xmm0
0x18001026d  movups  xmmword ptr [r14], xmm0
0x180010271  xorps   xmm1, xmm1
0x180010274  movups  xmmword ptr [r13+0], xmm1
0x180010279  mov     ebx, [rbp+4Fh+var_B0]
0x18001027c  mov     r9, [rbp+4Fh+var_78]; int *
0x180010280  mov     r8, [rbp+4Fh+var_70]; unsigned __int64
0x180010284  mov     rdx, [rbp+4Fh+var_68]
0x180010288  mov     edx, [rdx]; int
0x18001028a  mov     rcx, [rbp+4Fh+var_60]; char *
0x18001028e  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180010293  nop
0x180010294  lea     rcx, [rbp+4Fh+var_58]
0x180010298  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001029d  nop
0x18001029e  mov     rcx, [rbp+4Fh+hLibModule]; hLibModule
0x1800102a2  test    rcx, rcx
0x1800102a5  jz      short loc_1800102AD
0x1800102a7  call    cs:__imp_FreeLibrary
0x1800102ad  mov     eax, ebx
0x1800102af  mov     rbx, [rsp+0E0h+arg_0]
0x1800102b7  add     rsp, 0B0h
0x1800102be  pop     r15
0x1800102c0  pop     r14
0x1800102c2  pop     r13
0x1800102c4  pop     r12
0x1800102c6  pop     rdi
0x1800102c7  pop     rsi
0x1800102c8  pop     rbp
0x1800102c9  retn
```
