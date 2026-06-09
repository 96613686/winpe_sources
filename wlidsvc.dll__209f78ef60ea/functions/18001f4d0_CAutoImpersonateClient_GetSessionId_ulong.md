# CAutoImpersonateClient::GetSessionId(ulong &)

- ea: `0x18001f4d0`
- end: `0x18001f962`
- name: `?GetSessionId@CAutoImpersonateClient@@QEAAJAEAK@Z`
- size: `1170`
- prototype: `int(CAutoImpersonateClient *__hidden this, unsigned int *)`
- caller_count: `15`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001f190`
- `0x180029088`
- `0x18003100c`
- `0x18003b550`
- `0x18008cf4c`
- `0x18008f2cc`
- `0x180090afc`
- `0x180092c78`
- `0x18009ef98`
- `0x1800a1f78`
- `0x1800a2c38`
- `0x1800b0604`
- `0x1800b0bf4`
- `0x1800b0d34`
- `0x1800be570`

## callees

- `0x180019690`
- `0x18001a9c0`
- `0x18001b760`
- `0x18001f4d0`
- `0x1800a3b60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f554`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f6f3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f746`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f799`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f7ec`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f83f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f892`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f554`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f6f3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f746`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f799`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f7ec`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f83f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18001f892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f625`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f62f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f62f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f5dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f5dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f5f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f5f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f619`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001f619`

## string_xrefs

- `0x18001f525`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x18001f4f9`: `CAutoImpersonateClient::GetSessionId`

## pseudocode

```c
__int64 __fastcall CAutoImpersonateClient::GetSessionId(CAutoImpersonateClient *this, unsigned int *a2)
{
  char *v4; // rax
  __int64 v5; // r8
  const char *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 *v9; // rdx
  HANDLE CurrentThread; // rax
  BOOL TokenInformation; // ebx
  signed int LastError; // eax
  unsigned int v13; // ebx
  char *v15; // rax
  __int64 v16; // rcx
  char *v17; // rax
  __int64 v18; // rcx
  char *v19; // rax
  __int64 v20; // rcx
  char *v21; // rax
  __int64 v22; // rcx
  char *v23; // rax
  __int64 v24; // rcx
  char *v25; // rax
  __int64 v26; // rcx
  PDWORD ReturnLength; // [rsp+20h] [rbp-99h]
  DWORD v28; // [rsp+30h] [rbp-89h] BYREF
  int v29; // [rsp+38h] [rbp-81h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v31[5]; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v32[16]; // [rsp+70h] [rbp-49h] BYREF
  const char *v33; // [rsp+80h] [rbp-39h]
  int v34; // [rsp+88h] [rbp-31h]
  int v35; // [rsp+8Ch] [rbp-2Dh]
  const char *v36; // [rsp+90h] [rbp-29h]
  __int64 v37; // [rsp+98h] [rbp-21h]
  DWORD *v38; // [rsp+A0h] [rbp-19h]
  __int64 v39; // [rsp+A8h] [rbp-11h]
  const wchar_t *v40; // [rsp+B0h] [rbp-9h]
  __int64 v41; // [rsp+B8h] [rbp-1h]

  TokenHandle = 0;
  v29 = 0;
  v31[0] = "CAutoImpersonateClient::GetSessionId";
  v31[1] = &v29;
  v31[2] = 0;
  v31[3] = 0;
  switch ( dword_1801C3ABC )
  {
    case 4:
      if ( (byte_1801C36C4 & 4) != 0 )
      {
        v4 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v4 )
          v6 = v4 + 1;
        else
          v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v28 = 318;
        if ( v6 )
        {
          v7 = -1;
          do
            ++v7;
          while ( v6[v7] );
          v8 = (unsigned int)(v7 + 1);
        }
        else
        {
          v6 = "NULL";
          v8 = 5;
        }
        v9 = WlidSvc_TraceFunction_Enter;
LABEL_10:
        v33 = v6;
        v34 = v8;
        v38 = &v28;
        v40 = L"NULL";
        v35 = 0;
        v36 = "CAutoImpersonateClient::GetSessionId";
        v37 = 37;
        v39 = 4;
        v41 = 10;
        McGenEventWrite_EventWriteTransfer(v8, v9, v5, 5, v32);
      }
      break;
    case 5:
      if ( byte_1801C36C5 >= 0 )
        break;
      v25 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v25 )
        v6 = v25 + 1;
      else
        v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v28 = 318;
      if ( v6 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v6[v26] );
        v8 = (unsigned int)(v26 + 1);
      }
      else
      {
        v6 = "NULL";
        v8 = 5;
      }
      v9 = WlidModern_TraceFunction_Enter;
      goto LABEL_10;
    case 6:
      if ( (byte_1801C36C7 & 8) == 0 )
        break;
      v23 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v23 )
        v6 = v23 + 1;
      else
        v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v28 = 318;
      if ( v6 )
      {
        v24 = -1;
        do
          ++v24;
        while ( v6[v24] );
        v8 = (unsigned int)(v24 + 1);
      }
      else
      {
        v6 = "NULL";
        v8 = 5;
      }
      v9 = WlidCli_TraceFunction_Enter;
      goto LABEL_10;
    case 7:
      if ( (byte_1801C36C8 & 8) == 0 )
        break;
      v21 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v21 )
        v6 = v21 + 1;
      else
        v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v28 = 318;
      if ( v6 )
      {
        v22 = -1;
        do
          ++v22;
        while ( v6[v22] );
        v8 = (unsigned int)(v22 + 1);
      }
      else
      {
        v6 = "NULL";
        v8 = 5;
      }
      v9 = WlidProv_TraceFunction_Enter;
      goto LABEL_10;
    case 8:
      if ( (byte_1801C36C9 & 0x10) == 0 )
        break;
      v19 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v19 )
        v6 = v19 + 1;
      else
        v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v28 = 318;
      if ( v6 )
      {
        v20 = -1;
        do
          ++v20;
        while ( v6[v20] );
        v8 = (unsigned int)(v20 + 1);
      }
      else
      {
        v6 = "NULL";
        v8 = 5;
      }
      v9 = WlidBho_TraceFunction_Enter;
      goto LABEL_10;
    case 9:
      if ( (byte_1801C36CA & 0x10) == 0 )
        break;
      v17 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v17 )
        v6 = v17 + 1;
      else
        v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      v28 = 318;
      if ( v6 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v6[v18] );
        v8 = (unsigned int)(v18 + 1);
      }
      else
      {
        v6 = "NULL";
        v8 = 5;
      }
      v9 = TokenProvider_TraceFunction_Enter;
      goto LABEL_10;
    default:
      if ( dword_1801C3ABC == 10 && (byte_1801C36CB & 0x10) != 0 )
      {
        v15 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
        if ( v15 )
          v6 = v15 + 1;
        else
          v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
        v28 = 318;
        if ( v6 )
        {
          v16 = -1;
          do
            ++v16;
          while ( v6[v16] );
          v8 = (unsigned int)(v16 + 1);
        }
        else
        {
          v6 = "NULL";
          v8 = 5;
        }
        v9 = Extension_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
  }
  if ( *(_DWORD *)this || *((_DWORD *)this + 1) )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
      || (v28 = 0,
          TokenInformation = GetTokenInformation(TokenHandle, TokenSessionId, a2, 4u, &v28),
          CloseHandle(TokenHandle),
          !TokenInformation) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v29 = LastError;
    }
    LODWORD(ReturnLength) = *a2;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h",
      0x157u,
      L"SessionId=%d",
      ReturnLength);
    v13 = v29;
  }
  else
  {
    v13 = -2147024891;
    v29 = -2147024891;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v31);
  return v13;
}

```

## disassembly

```asm
0x18001f4d0  push    rbp
0x18001f4d2  push    rbx
0x18001f4d3  push    rsi
0x18001f4d4  push    rdi
0x18001f4d5  push    r12
0x18001f4d7  push    r13
0x18001f4d9  push    r14
0x18001f4db  push    r15
0x18001f4dd  lea     rbp, [rsp-1Fh]
0x18001f4e2  sub     rsp, 0D8h
0x18001f4e9  mov     rax, cs:__security_cookie
0x18001f4f0  xor     rax, rsp
0x18001f4f3  mov     [rbp+57h+var_50], rax
0x18001f4f7  xor     esi, esi
0x18001f4f9  lea     r13, aCautoimpersona; "CAutoImpersonateClient::GetSessionId"
0x18001f500  mov     rbx, rcx
0x18001f503  mov     [rbp+57h+TokenHandle], rsi
0x18001f507  mov     ecx, cs:dword_1801C3ABC
0x18001f50d  lea     rax, [rsp+110h+var_D8]
0x18001f512  mov     rdi, rdx
0x18001f515  mov     [rsp+110h+var_D8], esi
0x18001f519  lea     r12d, [rsi+4]
0x18001f51d  mov     [rbp+57h+var_C8], r13
0x18001f521  mov     [rbp+57h+var_C0], rax
0x18001f525  lea     r14, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18001f52c  mov     [rbp+57h+var_B8], rsi
0x18001f530  lea     r15d, [rsi+5]
0x18001f534  mov     [rbp+57h+var_B0], rsi
0x18001f538  sub     ecx, r12d
0x18001f53b  jnz     loc_18001F6AE
0x18001f541  test    cs:byte_1801C36C4, r12b
0x18001f548  jz      loc_18001F5D4
0x18001f54e  lea     edx, [rsi+5Ch]; Ch
0x18001f551  mov     rcx, r14; Str
0x18001f554  call    cs:__imp_strrchr
0x18001f55a  test    rax, rax
0x18001f55d  jz      loc_18001F6A6
0x18001f563  inc     rax
0x18001f566  mov     [rsp+110h+var_E0], 13Eh
0x18001f56e  test    rax, rax
0x18001f571  jz      loc_18001F953
0x18001f577  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f57b  inc     rcx
0x18001f57e  cmp     [rax+rcx], sil
0x18001f582  jnz     short loc_18001F57B
0x18001f584  inc     ecx
0x18001f586  lea     rdx, WlidSvc_TraceFunction_Enter
0x18001f58d  mov     [rbp+57h+var_90], rax
0x18001f591  mov     r9d, r15d
0x18001f594  lea     rax, [rsp+110h+var_E0]
0x18001f599  mov     [rbp+57h+var_88], ecx
0x18001f59c  mov     [rbp+57h+var_70], rax
0x18001f5a0  lea     rax, aNull_2; "NULL"
0x18001f5a7  mov     [rbp+57h+var_60], rax
0x18001f5ab  lea     rax, [rbp+57h+var_A0]
0x18001f5af  mov     [rsp+110h+ReturnLength], rax
0x18001f5b4  mov     [rbp+57h+var_84], esi
0x18001f5b7  mov     [rbp+57h+var_80], r13
0x18001f5bb  mov     [rbp+57h+var_78], 25h ; '%'
0x18001f5c3  mov     [rbp+57h+var_68], r12
0x18001f5c7  mov     [rbp+57h+var_58], 0Ah
0x18001f5cf  call    McGenEventWrite_EventWriteTransfer
0x18001f5d4  cmp     [rbx], esi
0x18001f5d6  jz      loc_18001F692
0x18001f5dc  call    cs:__imp_GetCurrentThread
0x18001f5e2  mov     edx, 8; DesiredAccess
0x18001f5e7  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18001f5eb  mov     rcx, rax; ThreadHandle
0x18001f5ee  lea     r8d, [rdx-7]; OpenAsSelf
0x18001f5f2  call    cs:__imp_OpenThreadToken
0x18001f5f8  test    eax, eax
0x18001f5fa  jz      short loc_18001F62F
0x18001f5fc  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18001f600  lea     rax, [rsp+110h+var_E0]
0x18001f605  mov     r9d, r12d; TokenInformationLength
0x18001f608  mov     [rsp+110h+ReturnLength], rax; ReturnLength
0x18001f60d  mov     r8, rdi; TokenInformation
0x18001f610  mov     [rsp+110h+var_E0], esi
0x18001f614  mov     edx, 0Ch; TokenInformationClass
0x18001f619  call    cs:__imp_GetTokenInformation
0x18001f61f  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001f623  mov     ebx, eax
0x18001f625  call    cs:__imp_CloseHandle
0x18001f62b  test    ebx, ebx
0x18001f62d  jnz     short loc_18001F645
0x18001f62f  call    cs:__imp_GetLastError
0x18001f635  test    eax, eax
0x18001f637  jle     short loc_18001F641
0x18001f639  movzx   eax, ax
0x18001f63c  or      eax, 80070000h
0x18001f641  mov     [rsp+110h+var_D8], eax
0x18001f645  mov     eax, [rdi]
0x18001f647  lea     r9, aSessionidD; "SessionId=%d"
0x18001f64e  mov     r8d, 157h; unsigned int
0x18001f654  mov     dword ptr [rsp+110h+ReturnLength], eax
0x18001f658  mov     rdx, r14; char *
0x18001f65b  mov     ecx, r15d; unsigned __int8
0x18001f65e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001f663  mov     ebx, [rsp+110h+var_D8]
0x18001f667  lea     rcx, [rbp+57h+var_C8]
0x18001f66b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001f670  mov     eax, ebx
0x18001f672  mov     rcx, [rbp+57h+var_50]
0x18001f676  xor     rcx, rsp; StackCookie
0x18001f679  call    __security_check_cookie
0x18001f67e  add     rsp, 0D8h
0x18001f685  pop     r15
0x18001f687  pop     r14
0x18001f689  pop     r13
0x18001f68b  pop     r12
0x18001f68d  pop     rdi
0x18001f68e  pop     rsi
0x18001f68f  pop     rbx
0x18001f690  pop     rbp
0x18001f691  retn
0x18001f692  cmp     [rbx+4], esi
0x18001f695  jnz     loc_18001F5DC
0x18001f69b  mov     ebx, 80070005h
0x18001f6a0  mov     [rsp+110h+var_D8], ebx
0x18001f6a4  jmp     short loc_18001F667
0x18001f6a6  mov     rax, r14
0x18001f6a9  jmp     loc_18001F566
0x18001f6ae  sub     ecx, 1
0x18001f6b1  jz      loc_18001F87D
0x18001f6b7  sub     ecx, 1
0x18001f6ba  jz      loc_18001F82A
0x18001f6c0  sub     ecx, 1
0x18001f6c3  jz      loc_18001F7D7
0x18001f6c9  sub     ecx, 1
0x18001f6cc  jz      loc_18001F784
0x18001f6d2  sub     ecx, 1
0x18001f6d5  jz      short loc_18001F731
0x18001f6d7  cmp     ecx, 1
0x18001f6da  jnz     loc_18001F5D4
0x18001f6e0  test    cs:byte_1801C36CB, 10h
0x18001f6e7  jz      loc_18001F5D4
0x18001f6ed  lea     edx, [rcx+5Bh]; Ch
0x18001f6f0  mov     rcx, r14; Str
0x18001f6f3  call    cs:__imp_strrchr
0x18001f6f9  test    rax, rax
0x18001f6fc  jz      loc_18001F8CC
0x18001f702  inc     rax
0x18001f705  mov     [rsp+110h+var_E0], 13Eh
0x18001f70d  test    rax, rax
0x18001f710  jz      loc_18001F8F9
0x18001f716  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f71a  inc     rcx
0x18001f71d  cmp     [rax+rcx], sil
0x18001f721  jnz     short loc_18001F71A
0x18001f723  inc     ecx
0x18001f725  lea     rdx, Extension_TraceFunction_Enter
0x18001f72c  jmp     loc_18001F58D
0x18001f731  test    cs:byte_1801C36CA, 10h
0x18001f738  jz      loc_18001F5D4
0x18001f73e  mov     edx, 5Ch ; '\'; Ch
0x18001f743  mov     rcx, r14; Str
0x18001f746  call    cs:__imp_strrchr
0x18001f74c  test    rax, rax
0x18001f74f  jz      loc_18001F8D4
0x18001f755  inc     rax
0x18001f758  mov     [rsp+110h+var_E0], 13Eh
0x18001f760  test    rax, rax
0x18001f763  jz      loc_18001F908
0x18001f769  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f76d  inc     rcx
0x18001f770  cmp     [rax+rcx], sil
0x18001f774  jnz     short loc_18001F76D
0x18001f776  inc     ecx
0x18001f778  lea     rdx, TokenProvider_TraceFunction_Enter
0x18001f77f  jmp     loc_18001F58D
0x18001f784  test    cs:byte_1801C36C9, 10h
0x18001f78b  jz      loc_18001F5D4
0x18001f791  mov     edx, 5Ch ; '\'; Ch
0x18001f796  mov     rcx, r14; Str
0x18001f799  call    cs:__imp_strrchr
0x18001f79f  test    rax, rax
0x18001f7a2  jz      loc_18001F8DC
0x18001f7a8  inc     rax
0x18001f7ab  mov     [rsp+110h+var_E0], 13Eh
0x18001f7b3  test    rax, rax
0x18001f7b6  jz      loc_18001F917
0x18001f7bc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f7c0  inc     rcx
0x18001f7c3  cmp     [rax+rcx], sil
0x18001f7c7  jnz     short loc_18001F7C0
0x18001f7c9  inc     ecx
0x18001f7cb  lea     rdx, WlidBho_TraceFunction_Enter
0x18001f7d2  jmp     loc_18001F58D
0x18001f7d7  test    cs:byte_1801C36C8, 8
0x18001f7de  jz      loc_18001F5D4
0x18001f7e4  mov     edx, 5Ch ; '\'; Ch
0x18001f7e9  mov     rcx, r14; Str
0x18001f7ec  call    cs:__imp_strrchr
0x18001f7f2  test    rax, rax
0x18001f7f5  jz      loc_18001F8E4
0x18001f7fb  inc     rax
0x18001f7fe  mov     [rsp+110h+var_E0], 13Eh
0x18001f806  test    rax, rax
0x18001f809  jz      loc_18001F926
0x18001f80f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f813  inc     rcx
0x18001f816  cmp     [rax+rcx], sil
0x18001f81a  jnz     short loc_18001F813
0x18001f81c  inc     ecx
0x18001f81e  lea     rdx, WlidProv_TraceFunction_Enter
0x18001f825  jmp     loc_18001F58D
0x18001f82a  test    cs:byte_1801C36C7, 8
0x18001f831  jz      loc_18001F5D4
0x18001f837  mov     edx, 5Ch ; '\'; Ch
0x18001f83c  mov     rcx, r14; Str
0x18001f83f  call    cs:__imp_strrchr
0x18001f845  test    rax, rax
0x18001f848  jz      loc_18001F8EC
0x18001f84e  inc     rax
0x18001f851  mov     [rsp+110h+var_E0], 13Eh
0x18001f859  test    rax, rax
0x18001f85c  jz      loc_18001F935
0x18001f862  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f866  inc     rcx
0x18001f869  cmp     [rax+rcx], sil
0x18001f86d  jnz     short loc_18001F866
0x18001f86f  inc     ecx
0x18001f871  lea     rdx, WlidCli_TraceFunction_Enter
0x18001f878  jmp     loc_18001F58D
0x18001f87d  cmp     cs:byte_1801C36C5, sil
0x18001f884  jge     loc_18001F5D4
0x18001f88a  mov     edx, 5Ch ; '\'; Ch
0x18001f88f  mov     rcx, r14; Str
0x18001f892  call    cs:__imp_strrchr
0x18001f898  test    rax, rax
0x18001f89b  jz      short loc_18001F8F4
0x18001f89d  inc     rax
0x18001f8a0  mov     [rsp+110h+var_E0], 13Eh
0x18001f8a8  test    rax, rax
0x18001f8ab  jz      loc_18001F944
0x18001f8b1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f8b5  inc     rcx
0x18001f8b8  cmp     [rax+rcx], sil
0x18001f8bc  jnz     short loc_18001F8B5
0x18001f8be  inc     ecx
0x18001f8c0  lea     rdx, WlidModern_TraceFunction_Enter
0x18001f8c7  jmp     loc_18001F58D
0x18001f8cc  mov     rax, r14
0x18001f8cf  jmp     loc_18001F705
0x18001f8d4  mov     rax, r14
0x18001f8d7  jmp     loc_18001F758
0x18001f8dc  mov     rax, r14
0x18001f8df  jmp     loc_18001F7AB
0x18001f8e4  mov     rax, r14
0x18001f8e7  jmp     loc_18001F7FE
0x18001f8ec  mov     rax, r14
0x18001f8ef  jmp     loc_18001F851
0x18001f8f4  mov     rax, r14
0x18001f8f7  jmp     short loc_18001F8A0
0x18001f8f9  lea     rax, aNull_0; "NULL"
0x18001f900  mov     ecx, r15d
0x18001f903  jmp     loc_18001F725
0x18001f908  lea     rax, aNull_0; "NULL"
0x18001f90f  mov     ecx, r15d
0x18001f912  jmp     loc_18001F778
0x18001f917  lea     rax, aNull_0; "NULL"
0x18001f91e  mov     ecx, r15d
0x18001f921  jmp     loc_18001F7CB
0x18001f926  lea     rax, aNull_0; "NULL"
0x18001f92d  mov     ecx, r15d
0x18001f930  jmp     loc_18001F81E
0x18001f935  lea     rax, aNull_0; "NULL"
0x18001f93c  mov     ecx, r15d
0x18001f93f  jmp     loc_18001F871
0x18001f944  lea     rax, aNull_0; "NULL"
0x18001f94b  mov     ecx, r15d
0x18001f94e  jmp     loc_18001F8C0
0x18001f953  lea     rax, aNull_0; "NULL"
0x18001f95a  mov     ecx, r15d
0x18001f95d  jmp     loc_18001F586
```
