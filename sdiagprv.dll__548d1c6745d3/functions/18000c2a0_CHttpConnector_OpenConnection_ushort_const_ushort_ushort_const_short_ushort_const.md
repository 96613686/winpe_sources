# CHttpConnector::OpenConnection(ushort const *,ushort,ushort const *,short,ushort const *)

- ea: `0x18000c2a0`
- end: `0x18000c5be`
- name: `?OpenConnection@CHttpConnector@@QEAAJPEBGG0F0@Z`
- size: `798`
- prototype: `__int64 __fastcall(HINTERNET *this, LPCWSTR pswzServerName, __int64, const unsigned __int16 *, __int16, LPCWSTR pwszObjectName)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180009e60`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180003400`
- `0x1800034e4`
- `0x18000b82c`
- `0x18000b9f0`
- `0x18000c2a0`
- `0x18000c8b4`
- `0x1800180be`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c405`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c405`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c54c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c54c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c3f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c53e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c3f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c53e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4b1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c320`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c320`
- `WINHTTP!WinHttpOpenRequest` at `0x18000c3ab`
- `WINHTTP!WinHttpOpenRequest` at `0x18000c3ab`
- `WINHTTP!WinHttpConnect` at `0x18000c372`
- `WINHTTP!WinHttpConnect` at `0x18000c372`

## string_xrefs

- `0x18000c4a0`: `CHttpConnector::OpenConnection`
- `0x18000c4e1`: `CHttpConnector::OpenConnection`
- `0x18000c528`: `CHttpConnector::OpenConnection`
- `0x18000c56a`: `CHttpConnector::OpenConnection`
- `0x18000c51b`: `UrlPath`

## pseudocode

```c
__int64 __fastcall CHttpConnector::OpenConnection(
        HINTERNET *this,
        LPCWSTR pswzServerName,
        __int64 a3,
        const unsigned __int16 *a4,
        __int16 a5,
        LPCWSTR pwszObjectName)
{
  const WCHAR *v8; // rbp
  unsigned __int16 *v9; // rdi
  int v10; // ebx
  char *v11; // rcx
  char *v12; // rax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v14; // rax
  __int64 *v15; // rdx
  __int64 v16; // r9
  signed int LastError; // eax
  HANDLE v18; // rax
  SIZE_T dwBytes; // [rsp+78h] [rbp+10h] BYREF
  __int16 v21; // [rsp+80h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+20h] BYREF

  ppv = 0;
  v21 = -1;
  dwBytes = 0;
  if ( pswzServerName )
  {
    v8 = pwszObjectName;
    v9 = 0;
    if ( pwszObjectName )
    {
      if ( !*this )
      {
        v10 = -2147019873;
LABEL_22:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_38;
        v16 = (unsigned int)v10;
        goto LABEL_24;
      }
      v10 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &IID_INetworkListManager, &ppv);
      if ( v10 >= 0 )
      {
        if ( (*(int (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 88LL))(ppv, &v21) >= 0 && !v21 )
        {
          v10 = -2147023674;
          goto LABEL_22;
        }
        v11 = (char *)WinHttpConnect(*this, pswzServerName, 0, 0);
        this[1] = v11;
        if ( (unsigned __int64)(v11 - 1) > 0xFFFFFFFFFFFFFFFDuLL
          || (v12 = (char *)WinHttpOpenRequest(v11, L"POST", v8, 0, 0, 0, 0x800000u),
              this[2] = v12,
              (unsigned __int64)(v12 - 1) > 0xFFFFFFFFFFFFFFFDuLL) )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          if ( v10 >= 0 )
          {
            v10 = -2147467259;
            goto LABEL_22;
          }
        }
        else
        {
          v10 = CHttpConnector::SetRequestOptions((CHttpConnector *)this);
          if ( v10 >= 0 )
          {
            v10 = ULongLongMult(0x104Au, 2u, &dwBytes);
            if ( v10 >= 0 )
            {
              ProcessHeap = GetProcessHeap();
              v14 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, dwBytes);
              v9 = v14;
              if ( !v14 )
              {
                v10 = -2147024882;
LABEL_15:
                if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
                  goto LABEL_38;
                v15 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
                goto LABEL_31;
              }
              memset_0(v14, 0, dwBytes);
              v10 = StringCchPrintfW(v9, 0x104Au, L"http%s://%s/%s", L"s", pswzServerName, v8);
              if ( v10 >= 0 )
              {
                v10 = CHttpConnector::BuildProxyLists((struct _PROXY_LIST **)this, v9);
                if ( v10 >= 0 )
                  goto LABEL_21;
              }
            }
          }
        }
      }
      if ( v10 == -2147024882 )
        goto LABEL_15;
      if ( v10 == -2147024809 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        {
          v16 = 2147942487LL;
LABEL_24:
          McTemplateU0sq_EventWriteTransfer(this, pswzServerName, "CHttpConnector::OpenConnection", v16);
          goto LABEL_38;
        }
        goto LABEL_38;
      }
LABEL_21:
      if ( v10 )
        goto LABEL_22;
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      {
        v15 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_31:
        McTemplateU0s_EventWriteTransfer(this, v15, "CHttpConnector::OpenConnection");
      }
LABEL_38:
      if ( v9 )
      {
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v9);
      }
      goto LABEL_43;
    }
LABEL_36:
    v10 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_43;
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)pswzServerName,
      (unsigned int)"CHttpConnector::OpenConnection",
      -2147024809,
      (__int64)"UrlPath");
    goto LABEL_38;
  }
  if ( !pwszObjectName )
  {
    v9 = 0;
    goto LABEL_36;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      0,
      (unsigned int)"CHttpConnector::OpenConnection",
      -2147024809,
      (__int64)"HostName");
  v10 = -2147024809;
LABEL_43:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID, LPCWSTR, __int64, const unsigned __int16 *))(*(_QWORD *)ppv + 16LL))(
      ppv,
      pswzServerName,
      a3,
      a4);
    ppv = 0;
  }
  if ( v10 < 0 )
    CHttpConnector::Abort((CHttpConnector *)this);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000c2a0  mov     r11, rsp
0x18000c2a3  mov     [r11+20h], r9
0x18000c2a7  mov     [r11+18h], r8w
0x18000c2ac  push    rbx
0x18000c2ad  push    rbp
0x18000c2ae  push    rsi
0x18000c2af  push    rdi
0x18000c2b0  push    r14
0x18000c2b2  sub     rsp, 40h
0x18000c2b6  or      eax, 0FFFFFFFFh
0x18000c2b9  mov     qword ptr [r11+20h], 0
0x18000c2c1  mov     [r11+18h], ax
0x18000c2c6  mov     r14, rdx
0x18000c2c9  mov     qword ptr [r11+10h], 0
0x18000c2d1  mov     rsi, rcx
0x18000c2d4  test    rdx, rdx
0x18000c2d7  jz      loc_18000C500
0x18000c2dd  mov     rbp, [rsp+68h+pwszObjectName]
0x18000c2e5  xor     edi, edi
0x18000c2e7  test    rbp, rbp
0x18000c2ea  jz      loc_18000C50D
0x18000c2f0  cmp     [rcx], rdi
0x18000c2f3  jnz     short loc_18000C2FF
0x18000c2f5  mov     ebx, 8007139Fh
0x18000c2fa  jmp     loc_18000C490
0x18000c2ff  xor     edx, edx; pUnkOuter
0x18000c301  lea     rax, [rsp+68h+arg_18]
0x18000c309  lea     r9, IID_INetworkListManager; riid
0x18000c310  mov     [rsp+68h+ppv], rax; ppv
0x18000c315  lea     rcx, CLSID_NetworkListManager; rclsid
0x18000c31c  lea     r8d, [rdx+1]; dwClsContext
0x18000c320  call    cs:__imp_CoCreateInstance
0x18000c326  mov     ebx, eax
0x18000c328  test    eax, eax
0x18000c32a  js      loc_18000C47C
0x18000c330  mov     rcx, [rsp+68h+arg_18]
0x18000c338  lea     rdx, [rsp+68h+arg_10]
0x18000c340  mov     rax, [rcx]
0x18000c343  mov     rax, [rax+58h]
0x18000c347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c34c  test    eax, eax
0x18000c34e  js      short loc_18000C366
0x18000c350  xor     eax, eax
0x18000c352  cmp     ax, [rsp+68h+arg_10]
0x18000c35a  jnz     short loc_18000C366
0x18000c35c  mov     ebx, 800704C6h
0x18000c361  jmp     loc_18000C490
0x18000c366  mov     rcx, [rsi]; hSession
0x18000c369  xor     r8d, r8d; nServerPort
0x18000c36c  xor     r9d, r9d; dwReserved
0x18000c36f  mov     rdx, r14; pswzServerName
0x18000c372  call    cs:__imp_WinHttpConnect
0x18000c378  mov     rcx, rax; hConnect
0x18000c37b  mov     [rsi+8], rax
0x18000c37f  dec     rax
0x18000c382  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c386  ja      loc_18000C4B1
0x18000c38c  mov     [rsp+68h+dwFlags], 800000h; dwFlags
0x18000c394  lea     rdx, pwszVerb; "POST"
0x18000c39b  mov     [rsp+68h+ppwszAcceptTypes], rdi; ppwszAcceptTypes
0x18000c3a0  xor     r9d, r9d; pwszVersion
0x18000c3a3  mov     r8, rbp; pwszObjectName
0x18000c3a6  mov     [rsp+68h+ppv], rdi; pwszReferrer
0x18000c3ab  call    cs:__imp_WinHttpOpenRequest
0x18000c3b1  mov     [rsi+10h], rax
0x18000c3b5  dec     rax
0x18000c3b8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c3bc  ja      loc_18000C4B1
0x18000c3c2  mov     rcx, rsi; this
0x18000c3c5  call    ?SetRequestOptions@CHttpConnector@@AEAAJXZ; CHttpConnector::SetRequestOptions(void)
0x18000c3ca  mov     ebx, eax
0x18000c3cc  test    eax, eax
0x18000c3ce  js      loc_18000C47C
0x18000c3d4  lea     r8, [rsp+68h+dwBytes]; unsigned __int64 *
0x18000c3d9  mov     edx, 2; unsigned __int64
0x18000c3de  mov     ecx, 104Ah; unsigned __int64
0x18000c3e3  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000c3e8  mov     ebx, eax
0x18000c3ea  test    eax, eax
0x18000c3ec  js      loc_18000C47C
0x18000c3f2  call    cs:__imp_GetProcessHeap
0x18000c3f8  mov     r8, [rsp+68h+dwBytes]; dwBytes
0x18000c3fd  mov     edx, 8; dwFlags
0x18000c402  mov     rcx, rax; hHeap
0x18000c405  call    cs:__imp_HeapAlloc
0x18000c40b  mov     rdi, rax
0x18000c40e  test    rax, rax
0x18000c411  jnz     short loc_18000C431
0x18000c413  mov     ebx, 8007000Eh
0x18000c418  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000c41f  jz      loc_18000C539
0x18000c425  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000c42c  jmp     loc_18000C4E1
0x18000c431  mov     r8, [rsp+68h+dwBytes]; Size
0x18000c436  xor     edx, edx; Val
0x18000c438  mov     rcx, rdi; void *
0x18000c43b  call    memset_0
0x18000c440  lea     r9, aS; "s"
0x18000c447  mov     [rsp+68h+ppwszAcceptTypes], rbp
0x18000c44c  lea     r8, aHttpSSS; "http%s://%s/%s"
0x18000c453  mov     [rsp+68h+ppv], r14
0x18000c458  mov     edx, 104Ah; unsigned __int64
0x18000c45d  mov     rcx, rdi; unsigned __int16 *
0x18000c460  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c465  mov     ebx, eax
0x18000c467  test    eax, eax
0x18000c469  js      short loc_18000C47C
0x18000c46b  mov     rdx, rdi; lpcwszUrl
0x18000c46e  mov     rcx, rsi; this
0x18000c471  call    ?BuildProxyLists@CHttpConnector@@AEAAJPEBG@Z; CHttpConnector::BuildProxyLists(ushort const *)
0x18000c476  mov     ebx, eax
0x18000c478  test    eax, eax
0x18000c47a  jns     short loc_18000C48C
0x18000c47c  cmp     ebx, 8007000Eh
0x18000c482  jz      short loc_18000C418
0x18000c484  cmp     ebx, 80070057h
0x18000c48a  jz      short loc_18000C4EF
0x18000c48c  test    ebx, ebx
0x18000c48e  jz      short loc_18000C4D1
0x18000c490  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000c497  jz      loc_18000C539
0x18000c49d  mov     r9d, ebx
0x18000c4a0  lea     r8, aChttpconnector_6; "CHttpConnector::OpenConnection"
0x18000c4a7  call    McTemplateU0sq_EventWriteTransfer
0x18000c4ac  jmp     loc_18000C539
0x18000c4b1  call    cs:__imp_GetLastError
0x18000c4b7  mov     ebx, eax
0x18000c4b9  test    eax, eax
0x18000c4bb  jle     short loc_18000C4C6
0x18000c4bd  movzx   ebx, ax
0x18000c4c0  or      ebx, 80070000h
0x18000c4c6  test    ebx, ebx
0x18000c4c8  js      short loc_18000C47C
0x18000c4ca  mov     ebx, 80004005h
0x18000c4cf  jmp     short loc_18000C490
0x18000c4d1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000c4d8  jz      short loc_18000C539
0x18000c4da  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000c4e1  lea     r8, aChttpconnector_6; "CHttpConnector::OpenConnection"
0x18000c4e8  call    McTemplateU0s_EventWriteTransfer
0x18000c4ed  jmp     short loc_18000C539
0x18000c4ef  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000c4f6  jz      short loc_18000C539
0x18000c4f8  mov     r9d, 80070057h
0x18000c4fe  jmp     short loc_18000C4A0
0x18000c500  cmp     [rsp+68h+pwszObjectName], 0
0x18000c509  jnz     short loc_18000C554
0x18000c50b  xor     edi, edi
0x18000c50d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000c514  mov     ebx, 80070057h
0x18000c519  jz      short loc_18000C580
0x18000c51b  lea     rax, aUrlpath; "UrlPath"
0x18000c522  mov     r9d, 80070057h
0x18000c528  lea     r8, aChttpconnector_6; "CHttpConnector::OpenConnection"
0x18000c52f  mov     [rsp+68h+ppv], rax
0x18000c534  call    McTemplateU0sqs_EventWriteTransfer
0x18000c539  test    rdi, rdi
0x18000c53c  jz      short loc_18000C580
0x18000c53e  call    cs:__imp_GetProcessHeap
0x18000c544  mov     r8, rdi; lpMem
0x18000c547  xor     edx, edx; dwFlags
0x18000c549  mov     rcx, rax; hHeap
0x18000c54c  call    cs:__imp_HeapFree
0x18000c552  jmp     short loc_18000C580
0x18000c554  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000c55b  jz      short loc_18000C57B
0x18000c55d  lea     rax, aHostname; "HostName"
0x18000c564  mov     r9d, 80070057h
0x18000c56a  lea     r8, aChttpconnector_6; "CHttpConnector::OpenConnection"
0x18000c571  mov     [rsp+68h+ppv], rax
0x18000c576  call    McTemplateU0sqs_EventWriteTransfer
0x18000c57b  mov     ebx, 80070057h
0x18000c580  mov     rcx, [rsp+68h+arg_18]
0x18000c588  test    rcx, rcx
0x18000c58b  jz      short loc_18000C5A5
0x18000c58d  mov     rax, [rcx]
0x18000c590  mov     rax, [rax+10h]
0x18000c594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c599  mov     [rsp+68h+arg_18], 0
0x18000c5a5  test    ebx, ebx
0x18000c5a7  jns     short loc_18000C5B1
0x18000c5a9  mov     rcx, rsi; this
0x18000c5ac  call    ?Abort@CHttpConnector@@QEAAJXZ; CHttpConnector::Abort(void)
0x18000c5b1  mov     eax, ebx
0x18000c5b3  add     rsp, 40h
0x18000c5b7  pop     r14
0x18000c5b9  pop     rdi
0x18000c5ba  pop     rsi
0x18000c5bb  pop     rbp
0x18000c5bc  pop     rbx
0x18000c5bd  retn
```
