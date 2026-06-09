# IsTokenAppContainer(void *,int &)

- ea: `0x1800204c4`
- end: `0x18002096a`
- name: `?IsTokenAppContainer@@YAJPEAXAEAH@Z`
- size: `1190`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ff44`

## callees

- `0x18000c050`
- `0x180019690`
- `0x18001a9c0`
- `0x18001b760`
- `0x1800204c4`
- `0x1800a3b60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020549`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002069b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800206f3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002074b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800207a3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800207fb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020853`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020549`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002069b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800206f3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x18002074b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800207a3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1800207fb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x180020853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800208bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800205e4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800205e4`

## string_xrefs

- `0x1800204f2`: `IsTokenAppContainer`
- `0x18002051a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800205f5`: `isTokenAppContainer = %d`

## pseudocode

```c
__int64 __fastcall IsTokenAppContainer(HANDLE TokenHandle, int *a2)
{
  char *v4; // rax
  __int64 v5; // r8
  const char *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 *v9; // rdx
  BOOL v10; // eax
  unsigned int v11; // ebx
  char *v13; // rax
  __int64 v14; // rcx
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
  signed int LastError; // eax
  PDWORD ReturnLength; // [rsp+20h] [rbp-79h]
  int v27; // [rsp+30h] [rbp-69h] BYREF
  signed int v28; // [rsp+38h] [rbp-61h] BYREF
  int TokenInformation; // [rsp+3Ch] [rbp-5Dh] BYREF
  DWORD v30; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v31[5]; // [rsp+48h] [rbp-51h] BYREF
  char v32[16]; // [rsp+70h] [rbp-29h] BYREF
  const char *v33; // [rsp+80h] [rbp-19h]
  int v34; // [rsp+88h] [rbp-11h]
  int v35; // [rsp+8Ch] [rbp-Dh]
  const char *v36; // [rsp+90h] [rbp-9h]
  __int64 v37; // [rsp+98h] [rbp-1h]
  int *v38; // [rsp+A0h] [rbp+7h]
  __int64 v39; // [rsp+A8h] [rbp+Fh]
  const wchar_t *v40; // [rsp+B0h] [rbp+17h]
  __int64 v41; // [rsp+B8h] [rbp+1Fh]

  v28 = 0;
  TokenInformation = 0;
  v30 = 0;
  v31[0] = "IsTokenAppContainer";
  v31[1] = &v28;
  v31[2] = 0;
  v31[3] = 0;
  switch ( dword_1801C3ABC )
  {
    case 4:
      if ( (byte_1801C36C4 & 4) == 0 )
        break;
      v4 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
      if ( v4 )
        v6 = v4 + 1;
      else
        v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
      v27 = 11486;
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
      goto LABEL_10;
    case 5:
      if ( byte_1801C36C5 < 0 )
      {
        v23 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v23 )
          v6 = v23 + 1;
        else
          v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v27 = 11486;
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
        v9 = WlidModern_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 6:
      if ( (byte_1801C36C7 & 8) != 0 )
      {
        v21 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v21 )
          v6 = v21 + 1;
        else
          v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v27 = 11486;
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
        v9 = WlidCli_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 7:
      if ( (byte_1801C36C8 & 8) != 0 )
      {
        v19 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v19 )
          v6 = v19 + 1;
        else
          v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v27 = 11486;
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
        v9 = WlidProv_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 8:
      if ( (byte_1801C36C9 & 0x10) != 0 )
      {
        v17 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v17 )
          v6 = v17 + 1;
        else
          v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v27 = 11486;
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
        v9 = WlidBho_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    case 9:
      if ( (byte_1801C36CA & 0x10) != 0 )
      {
        v15 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v15 )
          v6 = v15 + 1;
        else
          v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v27 = 11486;
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
        v9 = TokenProvider_TraceFunction_Enter;
        goto LABEL_10;
      }
      break;
    default:
      if ( dword_1801C3ABC == 10 && (byte_1801C36CB & 0x10) != 0 )
      {
        v13 = strrchr("onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", 92);
        if ( v13 )
          v6 = v13 + 1;
        else
          v6 = "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp";
        v27 = 11486;
        if ( v6 )
        {
          v14 = -1;
          do
            ++v14;
          while ( v6[v14] );
          v8 = (unsigned int)(v14 + 1);
        }
        else
        {
          v6 = "NULL";
          v8 = 5;
        }
        v9 = Extension_TraceFunction_Enter;
LABEL_10:
        v33 = v6;
        v38 = &v27;
        v40 = L"NULL";
        v34 = v8;
        v35 = 0;
        v36 = "IsTokenAppContainer";
        v37 = 20;
        v39 = 4;
        v41 = 10;
        McGenEventWrite_EventWriteTransfer(v8, v9, v5, 5, v32);
      }
      break;
  }
  *a2 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &v30) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v28 = LastError;
    if ( LastError < 0 )
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "IsTokenAppContainer",
        0x2CE9u,
        LastError,
        "hr = HRESULT_FROM_WIN32(GetLastError())");
  }
  v10 = TokenInformation != 0;
  *a2 = v10;
  LODWORD(ReturnLength) = v10;
  TracePrintW(
    4u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    0x2CF0u,
    L"isTokenAppContainer = %d",
    ReturnLength);
  v11 = v28;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v31);
  return v11;
}

```

## disassembly

```asm
0x1800204c4  mov     [rsp-8+arg_10], rbx
0x1800204c9  mov     [rsp-8+arg_18], rsi
0x1800204ce  push    rbp
0x1800204cf  push    rdi
0x1800204d0  push    r12
0x1800204d2  push    r14
0x1800204d4  push    r15
0x1800204d6  lea     rbp, [rsp-37h]
0x1800204db  sub     rsp, 0D0h
0x1800204e2  mov     rax, cs:__security_cookie
0x1800204e9  xor     rax, rsp
0x1800204ec  mov     [rbp+57h+var_30], rax
0x1800204f0  xor     esi, esi
0x1800204f2  lea     r12, aIstokenappcont; "IsTokenAppContainer"
0x1800204f9  mov     rdi, rcx
0x1800204fc  mov     [rbp+57h+var_B8], esi
0x1800204ff  mov     ecx, cs:dword_1801C3ABC
0x180020505  lea     rax, [rbp+57h+var_B8]
0x180020509  mov     rbx, rdx
0x18002050c  mov     [rbp+57h+TokenInformation], esi
0x18002050f  lea     r15d, [rsi+4]
0x180020513  mov     [rbp+57h+var_B0], esi
0x180020516  mov     [rbp+57h+var_A8], r12
0x18002051a  lea     r14, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180020521  mov     [rbp+57h+var_A0], rax
0x180020525  mov     [rbp+57h+var_98], rsi
0x180020529  mov     [rbp+57h+var_90], rsi
0x18002052d  sub     ecx, r15d
0x180020530  jnz     loc_180020656
0x180020536  test    cs:byte_1801C36C4, r15b
0x18002053d  jz      loc_1800205CA
0x180020543  lea     edx, [rsi+5Ch]; Ch
0x180020546  mov     rcx, r14; Str
0x180020549  call    cs:__imp_strrchr
0x18002054f  test    rax, rax
0x180020552  jz      loc_18002064E
0x180020558  inc     rax
0x18002055b  mov     [rbp+57h+var_C0], 2CDEh
0x180020562  mov     r9d, 5
0x180020568  test    rax, rax
0x18002056b  jz      loc_18002095B
0x180020571  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020575  inc     rcx
0x180020578  cmp     [rax+rcx], sil
0x18002057c  jnz     short loc_180020575
0x18002057e  inc     ecx
0x180020580  lea     rdx, WlidSvc_TraceFunction_Enter
0x180020587  mov     [rbp+57h+var_70], rax
0x18002058b  lea     rax, [rbp+57h+var_C0]
0x18002058f  mov     [rbp+57h+var_50], rax
0x180020593  lea     rax, aNull_2; "NULL"
0x18002059a  mov     [rbp+57h+var_40], rax
0x18002059e  lea     rax, [rbp+57h+var_80]
0x1800205a2  mov     [rsp+0F0h+ReturnLength], rax
0x1800205a7  mov     [rbp+57h+var_68], ecx
0x1800205aa  mov     [rbp+57h+var_64], esi
0x1800205ad  mov     [rbp+57h+var_60], r12
0x1800205b1  mov     [rbp+57h+var_58], 14h
0x1800205b9  mov     [rbp+57h+var_48], r15
0x1800205bd  mov     [rbp+57h+var_38], 0Ah
0x1800205c5  call    McGenEventWrite_EventWriteTransfer
0x1800205ca  lea     rax, [rbp+57h+var_B0]
0x1800205ce  mov     [rbx], esi
0x1800205d0  mov     r9d, r15d; TokenInformationLength
0x1800205d3  mov     [rsp+0F0h+ReturnLength], rax; ReturnLength
0x1800205d8  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800205dc  mov     edx, 1Dh; TokenInformationClass
0x1800205e1  mov     rcx, rdi; TokenHandle
0x1800205e4  call    cs:__imp_GetTokenInformation
0x1800205ea  test    eax, eax
0x1800205ec  jz      loc_1800208BF
0x1800205f2  cmp     [rbp+57h+TokenInformation], esi
0x1800205f5  lea     r9, aIstokenappcont_0; "isTokenAppContainer = %d"
0x1800205fc  mov     eax, esi
0x1800205fe  mov     r8d, 2CF0h; unsigned int
0x180020604  setnz   al
0x180020607  mov     rdx, r14; char *
0x18002060a  mov     ecx, r15d; unsigned __int8
0x18002060d  mov     [rbx], eax
0x18002060f  mov     dword ptr [rsp+0F0h+ReturnLength], eax
0x180020613  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180020618  mov     ebx, [rbp+57h+var_B8]
0x18002061b  lea     rcx, [rbp+57h+var_A8]
0x18002061f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180020624  mov     eax, ebx
0x180020626  mov     rcx, [rbp+57h+var_30]
0x18002062a  xor     rcx, rsp; StackCookie
0x18002062d  call    __security_check_cookie
0x180020632  lea     r11, [rsp+0F0h+var_20]
0x18002063a  mov     rbx, [r11+40h]
0x18002063e  mov     rsi, [r11+48h]
0x180020642  mov     rsp, r11
0x180020645  pop     r15
0x180020647  pop     r14
0x180020649  pop     r12
0x18002064b  pop     rdi
0x18002064c  pop     rbp
0x18002064d  retn
0x18002064e  mov     rax, r14
0x180020651  jmp     loc_18002055B
0x180020656  sub     ecx, 1
0x180020659  jz      loc_18002083E
0x18002065f  sub     ecx, 1
0x180020662  jz      loc_1800207E6
0x180020668  sub     ecx, 1
0x18002066b  jz      loc_18002078E
0x180020671  sub     ecx, 1
0x180020674  jz      loc_180020736
0x18002067a  sub     ecx, 1
0x18002067d  jz      short loc_1800206DE
0x18002067f  cmp     ecx, 1
0x180020682  jnz     loc_1800205CA
0x180020688  test    cs:byte_1801C36CB, 10h
0x18002068f  jz      loc_1800205CA
0x180020695  lea     edx, [rcx+5Bh]; Ch
0x180020698  mov     rcx, r14; Str
0x18002069b  call    cs:__imp_strrchr
0x1800206a1  test    rax, rax
0x1800206a4  jz      loc_180020892
0x1800206aa  inc     rax
0x1800206ad  mov     [rbp+57h+var_C0], 2CDEh
0x1800206b4  mov     r9d, 5
0x1800206ba  test    rax, rax
0x1800206bd  jz      loc_180020901
0x1800206c3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800206c7  inc     rcx
0x1800206ca  cmp     [rax+rcx], sil
0x1800206ce  jnz     short loc_1800206C7
0x1800206d0  inc     ecx
0x1800206d2  lea     rdx, Extension_TraceFunction_Enter
0x1800206d9  jmp     loc_180020587
0x1800206de  test    cs:byte_1801C36CA, 10h
0x1800206e5  jz      loc_1800205CA
0x1800206eb  mov     edx, 5Ch ; '\'; Ch
0x1800206f0  mov     rcx, r14; Str
0x1800206f3  call    cs:__imp_strrchr
0x1800206f9  test    rax, rax
0x1800206fc  jz      loc_18002089A
0x180020702  inc     rax
0x180020705  mov     [rbp+57h+var_C0], 2CDEh
0x18002070c  mov     r9d, 5
0x180020712  test    rax, rax
0x180020715  jz      loc_180020910
0x18002071b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002071f  inc     rcx
0x180020722  cmp     [rax+rcx], sil
0x180020726  jnz     short loc_18002071F
0x180020728  inc     ecx
0x18002072a  lea     rdx, TokenProvider_TraceFunction_Enter
0x180020731  jmp     loc_180020587
0x180020736  test    cs:byte_1801C36C9, 10h
0x18002073d  jz      loc_1800205CA
0x180020743  mov     edx, 5Ch ; '\'; Ch
0x180020748  mov     rcx, r14; Str
0x18002074b  call    cs:__imp_strrchr
0x180020751  test    rax, rax
0x180020754  jz      loc_1800208A2
0x18002075a  inc     rax
0x18002075d  mov     [rbp+57h+var_C0], 2CDEh
0x180020764  mov     r9d, 5
0x18002076a  test    rax, rax
0x18002076d  jz      loc_18002091F
0x180020773  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020777  inc     rcx
0x18002077a  cmp     [rax+rcx], sil
0x18002077e  jnz     short loc_180020777
0x180020780  inc     ecx
0x180020782  lea     rdx, WlidBho_TraceFunction_Enter
0x180020789  jmp     loc_180020587
0x18002078e  test    cs:byte_1801C36C8, 8
0x180020795  jz      loc_1800205CA
0x18002079b  mov     edx, 5Ch ; '\'; Ch
0x1800207a0  mov     rcx, r14; Str
0x1800207a3  call    cs:__imp_strrchr
0x1800207a9  test    rax, rax
0x1800207ac  jz      loc_1800208AA
0x1800207b2  inc     rax
0x1800207b5  mov     [rbp+57h+var_C0], 2CDEh
0x1800207bc  mov     r9d, 5
0x1800207c2  test    rax, rax
0x1800207c5  jz      loc_18002092E
0x1800207cb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800207cf  inc     rcx
0x1800207d2  cmp     [rax+rcx], sil
0x1800207d6  jnz     short loc_1800207CF
0x1800207d8  inc     ecx
0x1800207da  lea     rdx, WlidProv_TraceFunction_Enter
0x1800207e1  jmp     loc_180020587
0x1800207e6  test    cs:byte_1801C36C7, 8
0x1800207ed  jz      loc_1800205CA
0x1800207f3  mov     edx, 5Ch ; '\'; Ch
0x1800207f8  mov     rcx, r14; Str
0x1800207fb  call    cs:__imp_strrchr
0x180020801  test    rax, rax
0x180020804  jz      loc_1800208B2
0x18002080a  inc     rax
0x18002080d  mov     [rbp+57h+var_C0], 2CDEh
0x180020814  mov     r9d, 5
0x18002081a  test    rax, rax
0x18002081d  jz      loc_18002093D
0x180020823  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020827  inc     rcx
0x18002082a  cmp     [rax+rcx], sil
0x18002082e  jnz     short loc_180020827
0x180020830  inc     ecx
0x180020832  lea     rdx, WlidCli_TraceFunction_Enter
0x180020839  jmp     loc_180020587
0x18002083e  cmp     cs:byte_1801C36C5, sil
0x180020845  jge     loc_1800205CA
0x18002084b  mov     edx, 5Ch ; '\'; Ch
0x180020850  mov     rcx, r14; Str
0x180020853  call    cs:__imp_strrchr
0x180020859  test    rax, rax
0x18002085c  jz      short loc_1800208BA
0x18002085e  inc     rax
0x180020861  mov     [rbp+57h+var_C0], 2CDEh
0x180020868  mov     r9d, 5
0x18002086e  test    rax, rax
0x180020871  jz      loc_18002094C
0x180020877  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002087b  inc     rcx
0x18002087e  cmp     [rax+rcx], sil
0x180020882  jnz     short loc_18002087B
0x180020884  inc     ecx
0x180020886  lea     rdx, WlidModern_TraceFunction_Enter
0x18002088d  jmp     loc_180020587
0x180020892  mov     rax, r14
0x180020895  jmp     loc_1800206AD
0x18002089a  mov     rax, r14
0x18002089d  jmp     loc_180020705
0x1800208a2  mov     rax, r14
0x1800208a5  jmp     loc_18002075D
0x1800208aa  mov     rax, r14
0x1800208ad  jmp     loc_1800207B5
0x1800208b2  mov     rax, r14
0x1800208b5  jmp     loc_18002080D
0x1800208ba  mov     rax, r14
0x1800208bd  jmp     short loc_180020861
0x1800208bf  call    cs:__imp_GetLastError
0x1800208c5  test    eax, eax
0x1800208c7  jle     short loc_1800208D1
0x1800208c9  movzx   eax, ax
0x1800208cc  or      eax, 80070000h
0x1800208d1  mov     [rbp+57h+var_B8], eax
0x1800208d4  test    eax, eax
0x1800208d6  jns     loc_1800205F2
0x1800208dc  lea     rcx, aHrHresultFromW_10; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x1800208e3  mov     r9d, eax; int
0x1800208e6  mov     [rsp+0F0h+ReturnLength], rcx; char *
0x1800208eb  mov     r8d, 2CE9h; unsigned int
0x1800208f1  mov     rcx, r14; char *
0x1800208f4  mov     rdx, r12; char *
0x1800208f7  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800208fc  jmp     loc_1800205F2
0x180020901  lea     rax, aNull_0; "NULL"
0x180020908  mov     ecx, r9d
0x18002090b  jmp     loc_1800206D2
0x180020910  lea     rax, aNull_0; "NULL"
0x180020917  mov     ecx, r9d
0x18002091a  jmp     loc_18002072A
0x18002091f  lea     rax, aNull_0; "NULL"
0x180020926  mov     ecx, r9d
0x180020929  jmp     loc_180020782
0x18002092e  lea     rax, aNull_0; "NULL"
0x180020935  mov     ecx, r9d
0x180020938  jmp     loc_1800207DA
0x18002093d  lea     rax, aNull_0; "NULL"
0x180020944  mov     ecx, r9d
0x180020947  jmp     loc_180020832
0x18002094c  lea     rax, aNull_0; "NULL"
0x180020953  mov     ecx, r9d
0x180020956  jmp     loc_180020886
0x18002095b  lea     rax, aNull_0; "NULL"
0x180020962  mov     ecx, r9d
0x180020965  jmp     loc_180020580
```
