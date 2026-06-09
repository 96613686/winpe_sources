# SetCertificateToSsl

- ea: `0x18000863c`
- end: `0x18000895f`
- name: `SetCertificateToSsl`
- size: `803`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180008968`
- `0x180008be4`

## callees

- `0x18000863c`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000874f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000874f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008741`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008741`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008922`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008930`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008930`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800086ad`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800087bd`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800086ad`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800087bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000875d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000875d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087db`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x1800088a5`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x1800088a5`

## string_xrefs

- `0x1800088ed`: `HttpSetServiceConfiguration(v4) fails with error %d`

## pseudocode

```c
__int64 __fastcall SetCertificateToSsl(PCCERT_CONTEXT pCertContext, __int64 a2)
{
  ULONG LastError; // ebx
  __int64 v5; // r8
  const wchar_t *v6; // rdx
  DWORD v7; // ebx
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  void *v10; // rdi
  __int64 v11; // r8
  HANDLE v12; // rax
  __int64 v13; // r8
  __int64 v14; // r8
  HANDLE v15; // rax
  DWORD pcbData[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 pConfigInformation; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v19; // [rsp+48h] [rbp-B8h]
  void *v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+5Ch] [rbp-A4h]
  int v23; // [rsp+60h] [rbp-A0h]
  int v24; // [rsp+64h] [rbp-9Ch]
  const wchar_t *v25; // [rsp+68h] [rbp-98h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h]
  __int128 v28; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  pcbData[0] = 0;
  memset_0(&pConfigInformation, 0, 0x58u);
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  if ( CertGetCertificateContextProperty(pCertContext, 3u, 0, pcbData) )
  {
    v7 = pcbData[0];
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 0, v7);
    v10 = v9;
    if ( v9 )
    {
      if ( CertGetCertificateContextProperty(pCertContext, 3u, v9, pcbData) )
      {
        pConfigInformation = a2;
        v25 = L"MY";
        v21 = -1172743808;
        v22 = 1166789961;
        v23 = 1321739166;
        v24 = 1976413664;
        v20 = v10;
        v19 = pcbData[0];
        v26 = 4096;
        v27 = 0;
        v28 = 0;
        v29 = 0;
        LastError = HttpSetServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pConfigInformation, 0x58u, 0);
        if ( LastError )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v14, LastError);
          }
          if ( (_QWORD)xmmword_1800146E0 )
          {
            LOWORD(v30) = 0;
            FormatRRASErrorString(&v30, L"HttpSetServiceConfiguration(v4) fails with error %d", LastError);
            ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(
              gSstpCfgEtwContext,
              xmmword_1800146E0,
              &v30);
          }
        }
        v15 = GetProcessHeap();
        HeapFree(v15, 0, v10);
      }
      else
      {
        v12 = GetProcessHeap();
        HeapFree(v12, 0, v10);
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v13, LastError);
        }
        if ( (_QWORD)xmmword_1800146E0 )
        {
          v6 = L"CertGetCertificateContextProperty(2) for HASH failed: %d";
          goto LABEL_8;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v11, LastError);
      }
      if ( (_QWORD)xmmword_1800146E0 )
      {
        v6 = L"Unable to allocate memory for getting the cert. hash: %d";
        goto LABEL_8;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v5, LastError);
    }
    if ( (_QWORD)xmmword_1800146E0 )
    {
      v6 = L"CertGetCertificateContextProperty for HASH failed: %d";
LABEL_8:
      LOWORD(v30) = 0;
      FormatRRASErrorString(&v30, v6, LastError);
      ((void (__fastcall *)(__int64, _QWORD, int *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, xmmword_1800146E0, &v30);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000863c  mov     [rsp-8+arg_10], rbx
0x180008641  mov     [rsp-8+arg_18], rsi
0x180008646  push    rbp
0x180008647  push    rdi
0x180008648  push    r14
0x18000864a  lea     rbp, [rsp-7B0h]
0x180008652  sub     rsp, 8B0h
0x180008659  mov     rax, cs:__security_cookie
0x180008660  xor     rax, rsp
0x180008663  mov     [rbp+7C0h+var_20], rax
0x18000866a  mov     r14, rdx
0x18000866d  mov     [rsp+8C0h+pcbData], 0
0x180008675  xor     edx, edx; Val
0x180008677  mov     rsi, rcx
0x18000867a  lea     rcx, [rsp+8C0h+pConfigInformation]; void *
0x18000867f  lea     r8d, [rdx+58h]; Size
0x180008683  call    memset_0
0x180008688  xor     eax, eax
0x18000868a  lea     rcx, [rbp+7C0h+var_81C]; void *
0x18000868e  xor     edx, edx; Val
0x180008690  mov     [rbp+7C0h+var_820], eax
0x180008693  mov     r8d, 7FCh; Size
0x180008699  call    memset_0
0x18000869e  xor     r8d, r8d; pvData
0x1800086a1  lea     r9, [rsp+8C0h+pcbData]; pcbData
0x1800086a6  mov     rcx, rsi; pCertContext
0x1800086a9  lea     edx, [r8+3]; dwPropId
0x1800086ad  call    cs:__imp_CertGetCertificateContextProperty
0x1800086b3  test    eax, eax
0x1800086b5  jnz     loc_18000873D
0x1800086bb  call    cs:__imp_GetLastError
0x1800086c1  mov     ebx, eax
0x1800086c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086ca  lea     rax, WPP_GLOBAL_Control
0x1800086d1  cmp     rcx, rax
0x1800086d4  jz      short loc_1800086F3
0x1800086d6  test    byte ptr [rcx+1Ch], 40h
0x1800086da  jz      short loc_1800086F3
0x1800086dc  cmp     byte ptr [rcx+19h], 1
0x1800086e0  jb      short loc_1800086F3
0x1800086e2  mov     rcx, [rcx+10h]
0x1800086e6  mov     edx, 0Ah
0x1800086eb  mov     r9d, ebx
0x1800086ee  call    WPP_SF_d
0x1800086f3  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800086fb  jz      loc_180008936
0x180008701  lea     rdx, aCertgetcertifi_1; "CertGetCertificateContextProperty for H"...
0x180008708  xor     eax, eax
0x18000870a  lea     rcx, [rbp+7C0h+var_820]
0x18000870e  mov     r8d, ebx
0x180008711  mov     word ptr [rbp+7C0h+var_820], ax
0x180008715  call    FormatRRASErrorString
0x18000871a  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180008721  lea     r8, [rbp+7C0h+var_820]
0x180008725  mov     rcx, cs:gSstpCfgEtwContext
0x18000872c  mov     rax, cs:gSstpCfgTemplateFunc
0x180008733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008738  jmp     loc_180008936
0x18000873d  mov     ebx, [rsp+8C0h+pcbData]
0x180008741  call    cs:__imp_GetProcessHeap
0x180008747  mov     r8d, ebx; dwBytes
0x18000874a  xor     edx, edx; dwFlags
0x18000874c  mov     rcx, rax; hHeap
0x18000874f  call    cs:__imp_HeapAlloc
0x180008755  mov     rdi, rax
0x180008758  test    rax, rax
0x18000875b  jnz     short loc_1800087AD
0x18000875d  call    cs:__imp_GetLastError
0x180008763  mov     ebx, eax
0x180008765  mov     rcx, cs:WPP_GLOBAL_Control
0x18000876c  lea     rax, WPP_GLOBAL_Control
0x180008773  cmp     rcx, rax
0x180008776  jz      short loc_180008793
0x180008778  test    byte ptr [rcx+1Ch], 40h
0x18000877c  jz      short loc_180008793
0x18000877e  cmp     byte ptr [rcx+19h], 1
0x180008782  jb      short loc_180008793
0x180008784  mov     rcx, [rcx+10h]
0x180008788  lea     edx, [rdi+0Bh]
0x18000878b  mov     r9d, ebx
0x18000878e  call    WPP_SF_d
0x180008793  cmp     qword ptr cs:xmmword_1800146E0, 0
0x18000879b  jz      loc_180008936
0x1800087a1  lea     rdx, aUnableToAlloca_0; "Unable to allocate memory for getting t"...
0x1800087a8  jmp     loc_180008708
0x1800087ad  lea     r9, [rsp+8C0h+pcbData]; pcbData
0x1800087b2  mov     r8, rdi; pvData
0x1800087b5  mov     edx, 3; dwPropId
0x1800087ba  mov     rcx, rsi; pCertContext
0x1800087bd  call    cs:__imp_CertGetCertificateContextProperty
0x1800087c3  test    eax, eax
0x1800087c5  jnz     short loc_18000882D
0x1800087c7  call    cs:__imp_GetProcessHeap
0x1800087cd  mov     r8, rdi; lpMem
0x1800087d0  xor     edx, edx; dwFlags
0x1800087d2  mov     rcx, rax; hHeap
0x1800087d5  call    cs:__imp_HeapFree
0x1800087db  call    cs:__imp_GetLastError
0x1800087e1  mov     ebx, eax
0x1800087e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087ea  lea     rax, WPP_GLOBAL_Control
0x1800087f1  cmp     rcx, rax
0x1800087f4  jz      short loc_180008813
0x1800087f6  test    byte ptr [rcx+1Ch], 40h
0x1800087fa  jz      short loc_180008813
0x1800087fc  cmp     byte ptr [rcx+19h], 1
0x180008800  jb      short loc_180008813
0x180008802  mov     rcx, [rcx+10h]
0x180008806  mov     edx, 0Ch
0x18000880b  mov     r9d, ebx
0x18000880e  call    WPP_SF_d
0x180008813  cmp     qword ptr cs:xmmword_1800146E0, 0
0x18000881b  jz      loc_180008936
0x180008821  lea     rdx, aCertgetcertifi_2; "CertGetCertificateContextProperty(2) fo"...
0x180008828  jmp     loc_180008708
0x18000882d  lea     rax, aMy; "MY"
0x180008834  mov     [rsp+8C0h+pConfigInformation], r14
0x180008839  mov     r9d, 58h ; 'X'; ConfigInformationLength
0x18000883f  mov     [rsp+8C0h+var_858], rax
0x180008844  mov     eax, [rsp+8C0h+pcbData]
0x180008848  lea     r8, [rsp+8C0h+pConfigInformation]; pConfigInformation
0x18000884d  xorps   xmm0, xmm0
0x180008850  mov     [rsp+8C0h+var_868], 0BA195980h
0x180008858  xor     ecx, ecx; ServiceHandle
0x18000885a  mov     [rsp+8C0h+var_864], 458BCD49h
0x180008862  lea     edx, [r9-57h]; ConfigId
0x180008866  mov     [rsp+8C0h+var_860], 4EC8239Eh
0x18000886e  mov     [rsp+8C0h+var_85C], 75CDADE0h
0x180008876  mov     [rsp+8C0h+var_870], rdi
0x18000887b  mov     [rsp+8C0h+var_878], eax
0x18000887f  mov     [rsp+8C0h+var_850], 1000h
0x180008888  mov     [rsp+8C0h+var_848], 0
0x180008890  movdqa  [rbp+7C0h+var_840], xmm0
0x180008895  mov     [rbp+7C0h+var_830], 0
0x18000889c  mov     [rsp+8C0h+pOverlapped], 0; pOverlapped
0x1800088a5  call    cs:__imp_HttpSetServiceConfiguration
0x1800088ab  mov     ebx, eax
0x1800088ad  test    eax, eax
0x1800088af  jz      short loc_180008922
0x1800088b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088b8  lea     rax, WPP_GLOBAL_Control
0x1800088bf  cmp     rcx, rax
0x1800088c2  jz      short loc_1800088E1
0x1800088c4  test    byte ptr [rcx+1Ch], 40h
0x1800088c8  jz      short loc_1800088E1
0x1800088ca  cmp     byte ptr [rcx+19h], 1
0x1800088ce  jb      short loc_1800088E1
0x1800088d0  mov     rcx, [rcx+10h]
0x1800088d4  mov     edx, 0Dh
0x1800088d9  mov     r9d, ebx
0x1800088dc  call    WPP_SF_d
0x1800088e1  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800088e9  jz      short loc_180008922
0x1800088eb  xor     eax, eax
0x1800088ed  lea     rdx, aHttpsetservice_1; "HttpSetServiceConfiguration(v4) fails w"...
0x1800088f4  mov     r8d, ebx
0x1800088f7  mov     word ptr [rbp+7C0h+var_820], ax
0x1800088fb  lea     rcx, [rbp+7C0h+var_820]
0x1800088ff  call    FormatRRASErrorString
0x180008904  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000890b  lea     r8, [rbp+7C0h+var_820]
0x18000890f  mov     rcx, cs:gSstpCfgEtwContext
0x180008916  mov     rax, cs:gSstpCfgTemplateFunc
0x18000891d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008922  call    cs:__imp_GetProcessHeap
0x180008928  mov     r8, rdi; lpMem
0x18000892b  xor     edx, edx; dwFlags
0x18000892d  mov     rcx, rax; hHeap
0x180008930  call    cs:__imp_HeapFree
0x180008936  mov     eax, ebx
0x180008938  mov     rcx, [rbp+7C0h+var_20]
0x18000893f  xor     rcx, rsp; StackCookie
0x180008942  call    __security_check_cookie
0x180008947  lea     r11, [rsp+8C0h+var_10]
0x18000894f  mov     rbx, [r11+30h]
0x180008953  mov     rsi, [r11+38h]
0x180008957  mov     rsp, r11
0x18000895a  pop     r14
0x18000895c  pop     rdi
0x18000895d  pop     rbp
0x18000895e  retn
```
