# CAutoImpersonateClient::GetLogonId(_LUID &)

- ea: `0x180020b10`
- end: `0x180021044`
- name: `?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z`
- size: `1332`
- prototype: `__int64 __fastcall(CAutoImpersonateClient *__hidden this, struct _LUID *)`
- caller_count: `59`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000baac`
- `0x180010290`
- `0x18001f190`
- `0x1800216f8`
- `0x18002a57c`
- `0x18003100c`
- `0x18003b550`
- `0x18003e73c`
- `0x180040084`
- `0x18004a4b8`
- `0x18004e874`
- `0x180053640`
- `0x1800563d0`
- `0x180067f4c`
- `0x1800834d8`
- `0x18008a794`
- `0x18008be88`
- `0x18008c938`
- `0x18008cf4c`
- `0x18008e3ac`
- `0x18008f2cc`
- `0x180090afc`
- `0x1800921bc`
- `0x18009362c`
- `0x180093e30`
- `0x180094f84`
- `0x1800957f4`
- `0x180095b34`
- `0x180095f9c`
- `0x180096ff0`
- `0x180098310`
- `0x1800989a8`
- `0x18009939c`
- `0x18009ef98`
- `0x18009f768`
- `0x18009fdd0`
- `0x1800a05ac`
- `0x1800a1f78`
- `0x1800a2c38`
- `0x1800a3338`
- `0x1800b0604`
- `0x1800b0ae8`
- `0x1800b0bf4`
- `0x1800b1afc`
- `0x1800b4538`
- `0x1800b4804`
- `0x1800b51f4`
- `0x1800b5634`
- `0x1800b57d4`
- `0x1800b60bc`

## callees

- `0x180019690`
- `0x18001a9c0`
- `0x18001b760`
- `0x180020b10`
- `0x1800a3b60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020b89`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020d5c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020db6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020e10`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020e70`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020ed0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020f30`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020b89`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020d5c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020db6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020e10`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020e70`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020ed0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020f30`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020c7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020c1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020c1a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020c32`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020c32`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020c72`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180020c72`

## string_xrefs

- `0x180020b82`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020caa`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020d16`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020d55`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020daf`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020e09`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020e69`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020ec9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020f29`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020f6d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020f79`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020f85`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020f91`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020f9d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020fa9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\Include\svcapi.h`
- `0x180020b42`: `CAutoImpersonateClient::GetLogonId`

## pseudocode

```c
// Hidden C++ exception states: #wind=61
__int64 __fastcall CAutoImpersonateClient::GetLogonId(CAutoImpersonateClient *this, struct _LUID *a2)
{
  char *v4; // rax
  __int64 v5; // r8
  const char *v6; // rcx
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 *v9; // rdx
  HANDLE CurrentThread; // rax
  BOOL v11; // ebx
  signed int LastError; // eax
  unsigned int v13; // ebx
  char *v15; // rax
  __int64 v16; // rax
  char *v17; // rax
  __int64 v18; // rax
  char *v19; // rax
  __int64 v20; // rax
  char *v21; // rax
  __int64 v22; // rax
  char *v23; // rax
  __int64 v24; // rax
  char *v25; // rax
  __int64 v26; // rax
  PDWORD ReturnLength; // [rsp+20h] [rbp-69h]
  __int64 v28; // [rsp+30h] [rbp-59h] BYREF
  int v29; // [rsp+38h] [rbp-51h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v31[5]; // [rsp+48h] [rbp-41h] BYREF
  _BYTE TokenInformation[56]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v33; // [rsp+A8h] [rbp+1Fh]
  const wchar_t *v34; // [rsp+B0h] [rbp+27h]
  __int64 v35; // [rsp+B8h] [rbp+2Fh]

  v31[1] = &v29;
  TokenHandle = 0;
  v29 = 0;
  v31[0] = "CAutoImpersonateClient::GetLogonId";
  v31[2] = 0;
  v31[3] = 0;
  if ( dword_1801C3ABC == 4 )
  {
    if ( (byte_1801C36C4 & 4) != 0 )
    {
      v4 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
      if ( v4 )
        v6 = v4 + 1;
      else
        v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
      LODWORD(v28) = 277;
      if ( v6 )
      {
        v7 = -1;
        do
          ++v7;
        while ( v6[v7] );
        v8 = v7 + 1;
      }
      else
      {
        v8 = 5;
        v6 = "NULL";
      }
      v9 = WlidSvc_TraceFunction_Enter;
LABEL_10:
      *(_QWORD *)&TokenInformation[24] = v8;
      *(_QWORD *)&TokenInformation[16] = v6;
      *(_QWORD *)&TokenInformation[48] = &v28;
      v34 = L"NULL";
      *(_QWORD *)&TokenInformation[32] = "CAutoImpersonateClient::GetLogonId";
      *(_QWORD *)&TokenInformation[40] = 35;
      v33 = 4;
      v35 = 10;
      McGenEventWrite_EventWriteTransfer(v6, v9, v5, 5, TokenInformation);
    }
  }
  else
  {
    switch ( dword_1801C3ABC )
    {
      case 5:
        if ( byte_1801C36C5 < 0 )
        {
          v15 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
          if ( v15 )
            v6 = v15 + 1;
          else
            v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
          LODWORD(v28) = 277;
          if ( v6 )
          {
            v16 = -1;
            do
              ++v16;
            while ( v6[v16] );
            v8 = v16 + 1;
          }
          else
          {
            v8 = 5;
            v6 = "NULL";
          }
          v9 = WlidModern_TraceFunction_Enter;
          goto LABEL_10;
        }
        break;
      case 6:
        if ( (byte_1801C36C7 & 8) != 0 )
        {
          v17 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
          if ( v17 )
            v6 = v17 + 1;
          else
            v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
          LODWORD(v28) = 277;
          if ( v6 )
          {
            v18 = -1;
            do
              ++v18;
            while ( v6[v18] );
            v8 = v18 + 1;
          }
          else
          {
            v8 = 5;
            v6 = "NULL";
          }
          v9 = WlidCli_TraceFunction_Enter;
          goto LABEL_10;
        }
        break;
      case 7:
        if ( (byte_1801C36C8 & 8) != 0 )
        {
          v19 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
          if ( v19 )
            v6 = v19 + 1;
          else
            v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
          LODWORD(v28) = 277;
          if ( v6 )
          {
            v20 = -1;
            do
              ++v20;
            while ( v6[v20] );
            v8 = v20 + 1;
          }
          else
          {
            v8 = 5;
            v6 = "NULL";
          }
          v9 = WlidProv_TraceFunction_Enter;
          goto LABEL_10;
        }
        break;
      case 8:
        if ( (byte_1801C36C9 & 0x10) != 0 )
        {
          v21 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
          if ( v21 )
            v6 = v21 + 1;
          else
            v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
          LODWORD(v28) = 277;
          if ( v6 )
          {
            v22 = -1;
            do
              ++v22;
            while ( v6[v22] );
            v8 = v22 + 1;
          }
          else
          {
            v8 = 5;
            v6 = "NULL";
          }
          v9 = WlidBho_TraceFunction_Enter;
          goto LABEL_10;
        }
        break;
      case 9:
        if ( (byte_1801C36CA & 0x10) != 0 )
        {
          v23 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
          if ( v23 )
            v6 = v23 + 1;
          else
            v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
          LODWORD(v28) = 277;
          if ( v6 )
          {
            v24 = -1;
            do
              ++v24;
            while ( v6[v24] );
            v8 = v24 + 1;
          }
          else
          {
            v8 = 5;
            v6 = "NULL";
          }
          v9 = TokenProvider_TraceFunction_Enter;
          goto LABEL_10;
        }
        break;
      case 10:
        if ( (byte_1801C36CB & 0x10) != 0 )
        {
          v25 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h", 92);
          if ( v25 )
            v6 = v25 + 1;
          else
            v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h";
          LODWORD(v28) = 277;
          if ( v6 )
          {
            v26 = -1;
            do
              ++v26;
            while ( v6[v26] );
            v8 = v26 + 1;
          }
          else
          {
            v8 = 5;
            v6 = "NULL";
          }
          v9 = Extension_TraceFunction_Enter;
          goto LABEL_10;
        }
        break;
      default:
        break;
    }
  }
  if ( *(_DWORD *)this || *((_DWORD *)this + 1) )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
      && (memset(TokenInformation, 0, sizeof(TokenInformation)),
          LODWORD(v28) = 0,
          v11 = GetTokenInformation(TokenHandle, TokenStatistics, TokenInformation, 0x38u, (PDWORD)&v28),
          CloseHandle(TokenHandle),
          v11) )
    {
      *a2 = *(struct _LUID *)&TokenInformation[8];
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v29 = LastError;
    }
    LODWORD(ReturnLength) = a2->HighPart;
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\Include\\svcapi.h",
      0x134u,
      L"LUID=[%d,%d]",
      ReturnLength,
      a2->LowPart,
      v28);
    v13 = v29;
  }
  else
  {
    v13 = -2147024891;
    v29 = -2147024891;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>(v31);
  return v13;
}

```

## disassembly

```asm
0x180020b10  mov     [rsp-8+arg_0], rbx
0x180020b15  mov     [rsp-8+arg_10], rsi
0x180020b1a  push    rbp
0x180020b1b  push    rdi
0x180020b1c  push    r14
0x180020b1e  lea     rbp, [rsp-47h]
0x180020b23  sub     rsp, 0D0h
0x180020b2a  mov     rax, cs:__security_cookie
0x180020b31  xor     rax, rsp
0x180020b34  mov     [rbp+57h+var_20], rax
0x180020b38  xor     esi, esi
0x180020b3a  lea     rax, [rbp+57h+var_A8]
0x180020b3e  mov     [rbp+57h+var_90], rax
0x180020b42  lea     r14, aCautoimpersona_3; "CAutoImpersonateClient::GetLogonId"
0x180020b49  mov     eax, cs:dword_1801C3ABC
0x180020b4f  mov     rdi, rdx
0x180020b52  mov     [rbp+57h+TokenHandle], rsi
0x180020b56  mov     rbx, rcx
0x180020b59  mov     [rbp+57h+var_A8], esi
0x180020b5c  mov     [rbp+57h+var_98], r14
0x180020b60  mov     [rbp+57h+var_88], rsi
0x180020b64  mov     [rbp+57h+var_80], rsi
0x180020b68  cmp     eax, 4
0x180020b6b  jnz     loc_180020D22
0x180020b71  test    cs:byte_1801C36C4, al
0x180020b77  jz      def_180020D41; jumptable 0000000180020D41 default case
0x180020b7d  mov     edx, 5Ch ; '\'; Ch
0x180020b82  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020b89  call    cs:__imp_strrchr
0x180020b8f  test    rax, rax
0x180020b92  jz      loc_180020D16
0x180020b98  lea     rcx, [rax+1]
0x180020b9c  mov     dword ptr [rbp+57h+var_B0], 115h
0x180020ba3  test    rcx, rcx
0x180020ba6  jz      loc_180021018
0x180020bac  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180020bb3  inc     rax
0x180020bb6  cmp     [rcx+rax], sil
0x180020bba  jnz     short loc_180020BB3
0x180020bbc  inc     eax
0x180020bbe  lea     rdx, WlidSvc_TraceFunction_Enter
0x180020bc5  mov     dword ptr [rbp+57h+var_60+8], eax
0x180020bc8  mov     r9d, 5
0x180020bce  lea     rax, [rbp+57h+var_B0]
0x180020bd2  mov     qword ptr [rbp+57h+var_60], rcx
0x180020bd6  mov     [rbp+57h+var_40], rax
0x180020bda  lea     rax, aNull_2; "NULL"
0x180020be1  mov     [rbp+57h+var_30], rax
0x180020be5  lea     rax, [rbp+57h+TokenInformation]
0x180020be9  mov     [rsp+0E0h+ReturnLength], rax
0x180020bee  mov     dword ptr [rbp+57h+var_60+0Ch], esi
0x180020bf1  mov     qword ptr [rbp+57h+var_50], r14
0x180020bf5  mov     qword ptr [rbp+57h+var_50+8], 23h ; '#'
0x180020bfd  mov     [rbp+57h+var_38], 4
0x180020c05  mov     [rbp+57h+var_28], 0Ah
0x180020c0d  call    McGenEventWrite_EventWriteTransfer
0x180020c12  cmp     [rbx], esi; jumptable 0000000180020D41 default case
0x180020c14  jz      loc_180020D03
0x180020c1a  call    cs:__imp_GetCurrentThread
0x180020c20  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180020c24  mov     edx, 8; DesiredAccess
0x180020c29  mov     rcx, rax; ThreadHandle
0x180020c2c  mov     r8d, 1; OpenAsSelf
0x180020c32  call    cs:__imp_OpenThreadToken
0x180020c38  test    eax, eax
0x180020c3a  jz      short loc_180020C88
0x180020c3c  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180020c40  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180020c44  xorps   xmm0, xmm0
0x180020c47  mov     [rbp+57h+TokenInformation], esi
0x180020c4a  xor     eax, eax
0x180020c4c  mov     dword ptr [rbp+57h+var_B0], esi
0x180020c4f  mov     dword ptr [rbp+57h+var_40+4], eax
0x180020c52  mov     r9d, 38h ; '8'; TokenInformationLength
0x180020c58  lea     rax, [rbp+57h+var_B0]
0x180020c5c  mov     edx, 0Ah; TokenInformationClass
0x180020c61  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180020c66  movups  xmmword ptr [rbp-15h], xmm0
0x180020c6a  movups  [rbp+57h+var_60+4], xmm0
0x180020c6e  movups  [rbp+57h+var_50+4], xmm0
0x180020c72  call    cs:__imp_GetTokenInformation
0x180020c78  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180020c7c  mov     ebx, eax
0x180020c7e  call    cs:__imp_CloseHandle
0x180020c84  test    ebx, ebx
0x180020c86  jnz     short loc_180020CFA
0x180020c88  call    cs:__imp_GetLastError
0x180020c8e  test    eax, eax
0x180020c90  jle     short loc_180020C9A
0x180020c92  movzx   eax, ax
0x180020c95  or      eax, 80070000h
0x180020c9a  mov     [rbp+57h+var_A8], eax
0x180020c9d  mov     eax, [rdi]
0x180020c9f  lea     r9, aLuidDD; "LUID=[%d,%d]"
0x180020ca6  mov     [rsp+0E0h+var_B8], eax
0x180020caa  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020cb1  mov     eax, [rdi+4]
0x180020cb4  mov     r8d, 134h; unsigned int
0x180020cba  mov     ecx, 5; unsigned __int8
0x180020cbf  mov     dword ptr [rsp+0E0h+ReturnLength], eax
0x180020cc3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020cc8  mov     ebx, [rbp+57h+var_A8]
0x180020ccb  lea     rcx, [rbp+57h+var_98]
0x180020ccf  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180020cd4  mov     eax, ebx
0x180020cd6  mov     rcx, [rbp+57h+var_20]
0x180020cda  xor     rcx, rsp; StackCookie
0x180020cdd  call    __security_check_cookie
0x180020ce2  lea     r11, [rsp+0E0h+var_10]
0x180020cea  mov     rbx, [r11+20h]
0x180020cee  mov     rsi, [r11+30h]
0x180020cf2  mov     rsp, r11
0x180020cf5  pop     r14
0x180020cf7  pop     rdi
0x180020cf8  pop     rbp
0x180020cf9  retn
0x180020cfa  mov     rax, [rbp+57h+var_68]
0x180020cfe  mov     [rdi], rax
0x180020d01  jmp     short loc_180020C9D
0x180020d03  cmp     [rbx+4], esi
0x180020d06  jnz     loc_180020C1A
0x180020d0c  mov     ebx, 80070005h
0x180020d11  mov     [rbp+57h+var_A8], ebx
0x180020d14  jmp     short loc_180020CCB
0x180020d16  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020d1d  jmp     loc_180020B9C
0x180020d22  add     eax, 0FFFFFFFBh; switch 6 cases
0x180020d25  cmp     eax, 5
0x180020d28  ja      def_180020D41; jumptable 0000000180020D41 default case
0x180020d2e  lea     rdx, __ImageBase
0x180020d35  cdqe
0x180020d37  mov     ecx, ds:(jpt_180020D41 - 180000000h)[rdx+rax*4]
0x180020d3e  add     rcx, rdx
0x180020d41  jmp     rcx; switch jump
0x180020d43  cmp     cs:byte_1801C36C5, sil; jumptable 0000000180020D41 case 5
0x180020d4a  jge     def_180020D41; jumptable 0000000180020D41 default case
0x180020d50  mov     edx, 5Ch ; '\'; Ch
0x180020d55  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020d5c  call    cs:__imp_strrchr
0x180020d62  test    rax, rax
0x180020d65  jz      loc_180020F6D
0x180020d6b  lea     rcx, [rax+1]
0x180020d6f  mov     dword ptr [rbp+57h+var_B0], 115h
0x180020d76  test    rcx, rcx
0x180020d79  jz      loc_180020FB2
0x180020d7f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180020d86  inc     rax
0x180020d89  cmp     [rcx+rax], sil
0x180020d8d  jnz     short loc_180020D86
0x180020d8f  inc     eax
0x180020d91  lea     rdx, WlidModern_TraceFunction_Enter
0x180020d98  jmp     loc_180020BC5
0x180020d9d  test    cs:byte_1801C36C7, 8; jumptable 0000000180020D41 case 6
0x180020da4  jz      def_180020D41; jumptable 0000000180020D41 default case
0x180020daa  mov     edx, 5Ch ; '\'; Ch
0x180020daf  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020db6  call    cs:__imp_strrchr
0x180020dbc  test    rax, rax
0x180020dbf  jz      loc_180020F79
0x180020dc5  lea     rcx, [rax+1]
0x180020dc9  mov     dword ptr [rbp+57h+var_B0], 115h
0x180020dd0  test    rcx, rcx
0x180020dd3  jz      loc_180020FC3
0x180020dd9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180020de0  inc     rax
0x180020de3  cmp     [rcx+rax], sil
0x180020de7  jnz     short loc_180020DE0
0x180020de9  inc     eax
0x180020deb  lea     rdx, WlidCli_TraceFunction_Enter
0x180020df2  jmp     loc_180020BC5
0x180020df7  test    cs:byte_1801C36C8, 8; jumptable 0000000180020D41 case 7
0x180020dfe  jz      def_180020D41; jumptable 0000000180020D41 default case
0x180020e04  mov     edx, 5Ch ; '\'; Ch
0x180020e09  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020e10  call    cs:__imp_strrchr
0x180020e16  test    rax, rax
0x180020e19  jz      loc_180020F85
0x180020e1f  lea     rcx, [rax+1]
0x180020e23  mov     dword ptr [rbp+57h+var_B0], 115h
0x180020e2a  test    rcx, rcx
0x180020e2d  jz      loc_180020FD4
0x180020e33  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180020e3a  nop     word ptr [rax+rax+00h]
0x180020e40  inc     rax
0x180020e43  cmp     [rcx+rax], sil
0x180020e47  jnz     short loc_180020E40
0x180020e49  inc     eax
0x180020e4b  lea     rdx, WlidProv_TraceFunction_Enter
0x180020e52  jmp     loc_180020BC5
0x180020e57  test    cs:byte_1801C36C9, 10h; jumptable 0000000180020D41 case 8
0x180020e5e  jz      def_180020D41; jumptable 0000000180020D41 default case
0x180020e64  mov     edx, 5Ch ; '\'; Ch
0x180020e69  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020e70  call    cs:__imp_strrchr
0x180020e76  test    rax, rax
0x180020e79  jz      loc_180020F91
0x180020e7f  lea     rcx, [rax+1]
0x180020e83  mov     dword ptr [rbp+57h+var_B0], 115h
0x180020e8a  test    rcx, rcx
0x180020e8d  jz      loc_180020FE5
0x180020e93  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180020e9a  nop     word ptr [rax+rax+00h]
0x180020ea0  inc     rax
0x180020ea3  cmp     [rcx+rax], sil
0x180020ea7  jnz     short loc_180020EA0
0x180020ea9  inc     eax
0x180020eab  lea     rdx, WlidBho_TraceFunction_Enter
0x180020eb2  jmp     loc_180020BC5
0x180020eb7  test    cs:byte_1801C36CA, 10h; jumptable 0000000180020D41 case 9
0x180020ebe  jz      def_180020D41; jumptable 0000000180020D41 default case
0x180020ec4  mov     edx, 5Ch ; '\'; Ch
0x180020ec9  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020ed0  call    cs:__imp_strrchr
0x180020ed6  test    rax, rax
0x180020ed9  jz      loc_180020F9D
0x180020edf  lea     rcx, [rax+1]
0x180020ee3  mov     dword ptr [rbp+57h+var_B0], 115h
0x180020eea  test    rcx, rcx
0x180020eed  jz      loc_180020FF6
0x180020ef3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180020efa  nop     word ptr [rax+rax+00h]
0x180020f00  inc     rax
0x180020f03  cmp     [rcx+rax], sil
0x180020f07  jnz     short loc_180020F00
0x180020f09  inc     eax
0x180020f0b  lea     rdx, TokenProvider_TraceFunction_Enter
0x180020f12  jmp     loc_180020BC5
0x180020f17  test    cs:byte_1801C36CB, 10h; jumptable 0000000180020D41 case 10
0x180020f1e  jz      def_180020D41; jumptable 0000000180020D41 default case
0x180020f24  mov     edx, 5Ch ; '\'; Ch
0x180020f29  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020f30  call    cs:__imp_strrchr
0x180020f36  test    rax, rax
0x180020f39  jz      short loc_180020FA9
0x180020f3b  lea     rcx, [rax+1]
0x180020f3f  mov     dword ptr [rbp+57h+var_B0], 115h
0x180020f46  test    rcx, rcx
0x180020f49  jz      loc_180021007
0x180020f4f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180020f56  inc     rax
0x180020f59  cmp     [rcx+rax], sil
0x180020f5d  jnz     short loc_180020F56
0x180020f5f  inc     eax
0x180020f61  lea     rdx, Extension_TraceFunction_Enter
0x180020f68  jmp     loc_180020BC5
0x180020f6d  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020f74  jmp     loc_180020D6F
0x180020f79  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020f80  jmp     loc_180020DC9
0x180020f85  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020f8c  jmp     loc_180020E23
0x180020f91  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020f98  jmp     loc_180020E83
0x180020f9d  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020fa4  jmp     loc_180020EE3
0x180020fa9  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020fb0  jmp     short loc_180020F3F
0x180020fb2  mov     eax, 5
0x180020fb7  lea     rcx, aNull_0; "NULL"
0x180020fbe  jmp     loc_180020D91
0x180020fc3  mov     eax, 5
0x180020fc8  lea     rcx, aNull_0; "NULL"
0x180020fcf  jmp     loc_180020DEB
0x180020fd4  mov     eax, 5
0x180020fd9  lea     rcx, aNull_0; "NULL"
0x180020fe0  jmp     loc_180020E4B
0x180020fe5  mov     eax, 5
0x180020fea  lea     rcx, aNull_0; "NULL"
0x180020ff1  jmp     loc_180020EAB
0x180020ff6  mov     eax, 5
0x180020ffb  lea     rcx, aNull_0; "NULL"
0x180021002  jmp     loc_180020F0B
0x180021007  mov     eax, 5
0x18002100c  lea     rcx, aNull_0; "NULL"
0x180021013  jmp     loc_180020F61
0x180021018  mov     eax, 5
0x18002101d  lea     rcx, aNull_0; "NULL"
0x180021024  jmp     loc_180020BBE
```
