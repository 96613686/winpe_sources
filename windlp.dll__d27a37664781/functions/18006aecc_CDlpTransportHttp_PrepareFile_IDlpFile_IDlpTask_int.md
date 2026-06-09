# CDlpTransportHttp::PrepareFile(IDlpFile *,IDlpTask *,int *)

- ea: `0x18006aecc`
- end: `0x18006b4f1`
- name: `?PrepareFile@CDlpTransportHttp@@AEAAJPEAVIDlpFile@@PEAVIDlpTask@@PEAH@Z`
- size: `1573`
- prototype: `__int64 __fastcall(CDlpTransportHttp *__hidden this, struct IDlpFile *, struct IDlpTask *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006b570`
- `0x180079390`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18004b054`
- `0x18006aecc`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `msvcrt!_wcstoui64` at `0x18006b04b`
- `msvcrt!_wcstoui64` at `0x18006b04b`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b4c5`
- `OLEAUT32!__imp_SysFreeString` at `0x18006b4c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b125`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b47c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b125`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b47c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b133`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006b133`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b48a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b48a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b2ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b2ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b397`
- `WINHTTP!WinHttpReadData` at `0x18006b1f9`
- `WINHTTP!WinHttpReadData` at `0x18006b1f9`
- `WINHTTP!WinHttpCloseHandle` at `0x18006b0ab`
- `WINHTTP!WinHttpCloseHandle` at `0x18006b0c0`
- `WINHTTP!WinHttpCloseHandle` at `0x18006b49b`
- `WINHTTP!WinHttpCloseHandle` at `0x18006b4b0`
- `WINHTTP!WinHttpCloseHandle` at `0x18006b0ab`
- `WINHTTP!WinHttpCloseHandle` at `0x18006b0c0`
- `WINHTTP!WinHttpCloseHandle` at `0x18006b49b`
- `WINHTTP!WinHttpCloseHandle` at `0x18006b4b0`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18006b17f`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18006b25d`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18006b17f`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18006b25d`
- `WINHTTP!WinHttpQueryHeaders` at `0x18006b037`
- `WINHTTP!WinHttpQueryHeaders` at `0x18006b037`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDlpTransportHttp::PrepareFile(
        CDlpTransportHttp *this,
        struct IDlpFile *a2,
        struct IDlpTask *a3,
        int *a4)
{
  void *v7; // rdi
  signed int v8; // esi
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rbx
  _QWORD *v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  HANDLE ProcessHeap; // rax
  LPVOID v21; // rax
  signed int v22; // eax
  __int64 v23; // rcx
  DWORD v24; // eax
  DWORD v25; // r8d
  DWORD v26; // eax
  int v27; // eax
  signed int LastError; // eax
  signed int v29; // eax
  signed int v30; // eax
  __int64 v31; // rcx
  int v32; // eax
  HANDLE v33; // rax
  LPDWORD lpdwBufferLength; // [rsp+20h] [rbp-E0h]
  LPDWORD lpdwIndex; // [rsp+28h] [rbp-D8h]
  DWORD dwNumberOfBytesAvailable; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwBufferLength; // [rsp+44h] [rbp-BCh] BYREF
  HINTERNET hRequest; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+50h] [rbp-B0h] BYREF
  HINTERNET hInternet; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v42; // [rsp+60h] [rbp-A0h]
  __int128 v43; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h]
  __int64 v47; // [rsp+90h] [rbp-70h]
  wchar_t Buffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  v45 = 0;
  v46 = 0;
  v47 = 0;
  bstrString = 0;
  hInternet = 0;
  hRequest = 0;
  dwBufferLength = 0;
  dwNumberOfBytesAvailable = 0;
  dwNumberOfBytesRead = 0;
  v7 = 0;
  v42 = 0;
  v43 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    v9 = *((_QWORD *)this + 12);
    if ( v9 )
    {
      LODWORD(lpdwIndex) = -2147024809;
      LODWORD(lpdwBufferLength) = 753;
LABEL_4:
      v10 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v9,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpTransportHttp::PrepareFile",
              lpdwBufferLength,
              lpdwIndex);
      v11 = (unsigned int)v10;
      if ( v10 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v10);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
      goto LABEL_85;
    }
    goto LABEL_85;
  }
  if ( !a4 )
  {
    v8 = -2147024809;
    v9 = *((_QWORD *)this + 12);
    if ( v9 )
    {
      LODWORD(lpdwIndex) = -2147024809;
      LODWORD(lpdwBufferLength) = 754;
      goto LABEL_4;
    }
LABEL_85:
    if ( (**((int (__fastcall ***)(char *, _QWORD, _QWORD, int *))a2 + 2))((char *)a2 + 16, (unsigned int)v8, 0, a4) >= 0 )
    {
      v43 = (unsigned __int64)a2;
      if ( a3 )
        (*(void (__fastcall **)(char *, __int64, __int128 *))(*((_QWORD *)a3 + 2) + 24LL))((char *)a3 + 16, 65537, &v43);
    }
    (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)a2 + 2) + 16LL))((char *)a2 + 16, 0xFFFFFFFFLL);
    goto LABEL_89;
  }
  v12 = CDlpTransportHttp::ConnectToSourceUrl(this, a2, L"HEAD", 0, 0, &hInternet, &hRequest);
  v8 = v12;
  if ( v12 < 0 )
  {
    v13 = *((_QWORD *)this + 12);
    if ( !v13 )
      goto LABEL_84;
    LODWORD(lpdwIndex) = v12;
    LODWORD(lpdwBufferLength) = 770;
    goto LABEL_81;
  }
  memset_0(Buffer, 0, 0x208u);
  dwBufferLength = 259;
  if ( WinHttpQueryHeaders(hRequest, 5u, 0, Buffer, &dwBufferLength, 0) )
  {
    v14 = _wcstoui64(Buffer, 0, 10);
    v15 = v14;
    v16 = (_QWORD *)((char *)this + 96);
    v17 = *((_QWORD *)this + 12);
    if ( v17 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v17, 2, L"PrepareFile: HEAD -> Content-Length=[%I64u]", v14);
    goto LABEL_53;
  }
  if ( GetLastError() == 12150 )
  {
    v16 = (_QWORD *)((char *)this + 96);
    v18 = *((_QWORD *)this + 12);
    if ( v18 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v18, 3, L"PrepareFile: Content-Length header not found.  Trying GET...");
    if ( hRequest )
    {
      WinHttpCloseHandle(hRequest);
      hRequest = 0;
    }
    if ( hInternet )
    {
      WinHttpCloseHandle(hInternet);
      hInternet = 0;
    }
    v19 = CDlpTransportHttp::ConnectToSourceUrl(this, a2, L"GET", 0, 0, &hInternet, &hRequest);
    v8 = v19;
    if ( v19 < 0 )
    {
      v13 = *v16;
      if ( !*v16 )
        goto LABEL_84;
      LODWORD(lpdwIndex) = v19;
      LODWORD(lpdwBufferLength) = 802;
      goto LABEL_81;
    }
    dwBufferLength = 0x8000;
    ProcessHeap = GetProcessHeap();
    v21 = HeapAlloc(ProcessHeap, 0, 0x8000u);
    v7 = v21;
    v15 = 0;
    if ( !v21 )
    {
      v7 = 0;
      v42 = 0;
      v8 = -2147024882;
      v9 = *v16;
      if ( *v16 )
      {
        LODWORD(lpdwIndex) = -2147024882;
        LODWORD(lpdwBufferLength) = 806;
        goto LABEL_4;
      }
      goto LABEL_85;
    }
    v42 = v21;
    dwNumberOfBytesAvailable = 0;
    if ( WinHttpQueryDataAvailable(hRequest, &dwNumberOfBytesAvailable) )
    {
      v24 = dwNumberOfBytesAvailable;
      if ( !dwNumberOfBytesAvailable )
      {
LABEL_51:
        if ( *v16 )
          CDlpLogT<CEmptyType>::DlpLogFormat(*v16, 2, L"PrepareFile: Content-Length=[%I64u]", v15);
LABEL_53:
        v27 = (*(__int64 (__fastcall **)(char *, unsigned __int64, _QWORD))(*((_QWORD *)a2 + 2) + 8LL))(
                (char *)a2 + 16,
                v15,
                0);
        v8 = v27;
        if ( v27 >= 0 )
          goto LABEL_89;
        v13 = *v16;
        if ( *v16 )
        {
          LODWORD(lpdwIndex) = v27;
          LODWORD(lpdwBufferLength) = 841;
LABEL_81:
          v32 = CDlpLogT<CEmptyType>::DlpLogFormat(
                  v13,
                  4,
                  L"%s(%d): Result = 0x%X",
                  L"CDlpTransportHttp::PrepareFile",
                  lpdwBufferLength,
                  lpdwIndex);
          v23 = (unsigned int)v32;
          if ( v32 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v32);
          goto LABEL_83;
        }
LABEL_84:
        if ( v8 >= 0 )
          goto LABEL_89;
        goto LABEL_85;
      }
      while ( 1 )
      {
        v25 = dwBufferLength;
        if ( dwBufferLength > v24 )
          v25 = v24;
        if ( !WinHttpReadData(hRequest, v7, v25, &dwNumberOfBytesRead) )
          break;
        v26 = dwBufferLength;
        if ( dwBufferLength > dwNumberOfBytesAvailable )
          v26 = dwNumberOfBytesAvailable;
        if ( dwNumberOfBytesRead != v26 )
        {
          v8 = -2147467259;
          v9 = *v16;
          if ( !*v16 )
            goto LABEL_85;
          LODWORD(lpdwIndex) = -2147467259;
          LODWORD(lpdwBufferLength) = 819;
          goto LABEL_4;
        }
        if ( v15 + dwNumberOfBytesRead < v15 )
        {
          v8 = -2147024362;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        }
        else
        {
          v15 += dwNumberOfBytesRead;
          v8 = 0;
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
        if ( v8 < 0 )
        {
          v13 = *v16;
          if ( !*v16 )
            goto LABEL_84;
          LODWORD(lpdwIndex) = v8;
          LODWORD(lpdwBufferLength) = 821;
          goto LABEL_81;
        }
        dwNumberOfBytesAvailable = 0;
        if ( !WinHttpQueryDataAvailable(hRequest, &dwNumberOfBytesAvailable) )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v8 = -2147467259;
          }
          if ( !*v16 )
            goto LABEL_84;
          v23 = 0;
          if ( v8 >= 0 )
            goto LABEL_83;
          LODWORD(lpdwIndex) = v8;
          LODWORD(lpdwBufferLength) = 827;
          goto LABEL_37;
        }
        v24 = dwNumberOfBytesAvailable;
        if ( !dwNumberOfBytesAvailable )
          goto LABEL_51;
      }
      v29 = GetLastError();
      v8 = v29;
      if ( v29 )
      {
        if ( v29 > 0 )
          v8 = (unsigned __int16)v29 | 0x80070000;
      }
      else
      {
        v8 = -2147467259;
      }
      if ( !*v16 )
        goto LABEL_84;
      v23 = 0;
      if ( v8 >= 0 )
        goto LABEL_83;
      LODWORD(lpdwIndex) = v8;
      LODWORD(lpdwBufferLength) = 818;
    }
    else
    {
      v22 = GetLastError();
      v8 = v22;
      if ( v22 )
      {
        if ( v22 > 0 )
          v8 = (unsigned __int16)v22 | 0x80070000;
      }
      else
      {
        v8 = -2147467259;
      }
      if ( !*v16 )
        goto LABEL_84;
      v23 = 0;
      if ( v8 >= 0 )
      {
LABEL_83:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v23);
        goto LABEL_84;
      }
      LODWORD(lpdwIndex) = v8;
      LODWORD(lpdwBufferLength) = 812;
    }
LABEL_37:
    v13 = *v16;
    goto LABEL_81;
  }
  v30 = GetLastError();
  v8 = v30;
  if ( v30 > 0 )
    v8 = (unsigned __int16)v30 | 0x80070000;
  v31 = *((_QWORD *)this + 12);
  if ( v31 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v31, 4, L"PrepareFile: WinHttpQueryHeaders failed -> [0x%X]", (unsigned int)v8);
  if ( v8 < 0 )
  {
    v13 = *((_QWORD *)this + 12);
    if ( !v13 )
      goto LABEL_84;
    LODWORD(lpdwIndex) = v8;
    LODWORD(lpdwBufferLength) = 836;
    goto LABEL_81;
  }
LABEL_89:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( v7 )
  {
    v33 = GetProcessHeap();
    HeapFree(v33, 0, v7);
  }
  if ( hRequest )
  {
    WinHttpCloseHandle(hRequest);
    hRequest = 0;
  }
  if ( hInternet )
  {
    WinHttpCloseHandle(hInternet);
    hInternet = 0;
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006aecc  push    rbp
0x18006aece  push    rbx
0x18006aecf  push    rsi
0x18006aed0  push    rdi
0x18006aed1  push    r12
0x18006aed3  push    r13
0x18006aed5  push    r14
0x18006aed7  push    r15
0x18006aed9  lea     rbp, [rsp-1C8h]
0x18006aee1  sub     rsp, 2C8h
0x18006aee8  mov     rax, cs:__security_cookie
0x18006aeef  xor     rax, rsp
0x18006aef2  mov     [rbp+200h+var_50], rax
0x18006aef9  mov     r12, r8
0x18006aefc  mov     r13, rdx
0x18006aeff  mov     r15, rcx
0x18006af02  xor     ebx, ebx
0x18006af04  mov     [rbp+200h+var_280], rbx
0x18006af08  mov     [rbp+200h+var_278], rbx
0x18006af0c  mov     [rbp+200h+var_270], rbx
0x18006af10  mov     [rsp+300h+bstrString], rbx
0x18006af15  mov     [rsp+300h+hInternet], rbx
0x18006af1a  mov     [rsp+300h+hRequest], rbx
0x18006af1f  mov     [rsp+300h+dwBufferLength], ebx
0x18006af23  mov     [rsp+300h+dwNumberOfBytesAvailable], ebx
0x18006af27  mov     [rsp+300h+dwNumberOfBytesRead], ebx
0x18006af2b  mov     edi, ebx
0x18006af2d  mov     [rsp+300h+var_2A0], rbx
0x18006af32  xorps   xmm0, xmm0
0x18006af35  movups  [rsp+300h+var_298], xmm0
0x18006af3a  test    rdx, rdx
0x18006af3d  jnz     short loc_18006AF8C
0x18006af3f  mov     eax, 80070057h
0x18006af44  mov     esi, eax
0x18006af46  mov     rcx, [rcx+60h]
0x18006af4a  test    rcx, rcx
0x18006af4d  jz      loc_18006B412
0x18006af53  mov     dword ptr [rsp+300h+lpdwIndex], eax
0x18006af57  mov     dword ptr [rsp+300h+lpdwBufferLength], 2F1h
0x18006af5f  lea     r9, aCdlptransporth_2; "CDlpTransportHttp::PrepareFile"
0x18006af66  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006af6d  mov     edx, 4
0x18006af72  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18006af77  test    eax, eax
0x18006af79  mov     ecx, eax
0x18006af7b  jns     short loc_18006AF82
0x18006af7d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006af82  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006af87  jmp     loc_18006B412
0x18006af8c  test    r9, r9
0x18006af8f  jnz     short loc_18006AFB3
0x18006af91  mov     eax, 80070057h
0x18006af96  mov     esi, eax
0x18006af98  mov     rcx, [rcx+60h]; this
0x18006af9c  test    rcx, rcx
0x18006af9f  jz      loc_18006B412
0x18006afa5  mov     dword ptr [rsp+300h+lpdwIndex], eax
0x18006afa9  mov     dword ptr [rsp+300h+lpdwBufferLength], 2F2h
0x18006afb1  jmp     short loc_18006AF5F
0x18006afb3  lea     rax, [rsp+300h+hRequest]
0x18006afb8  mov     [rsp+300h+var_2D0], rax; void **
0x18006afbd  lea     rax, [rsp+300h+hInternet]
0x18006afc2  mov     [rsp+300h+lpdwIndex], rax; void **
0x18006afc7  mov     [rsp+300h+lpdwBufferLength], rbx; union _LARGE_INTEGER *
0x18006afcc  xor     r9d, r9d; union _LARGE_INTEGER *
0x18006afcf  lea     r8, aHead; "HEAD"
0x18006afd6  call    ?ConnectToSourceUrl@CDlpTransportHttp@@AEAAJPEAVIDlpFile@@PEBGPEAT_LARGE_INTEGER@@2PEAPEAX3@Z; CDlpTransportHttp::ConnectToSourceUrl(IDlpFile *,ushort const *,_LARGE_INTEGER *,_LARGE_INTEGER *,void * *,void * *)
0x18006afdb  mov     esi, eax
0x18006afdd  test    eax, eax
0x18006afdf  jns     short loc_18006AFFF
0x18006afe1  mov     rcx, [r15+60h]
0x18006afe5  test    rcx, rcx
0x18006afe8  jz      loc_18006B40E
0x18006afee  mov     dword ptr [rsp+300h+lpdwIndex], eax
0x18006aff2  mov     dword ptr [rsp+300h+lpdwBufferLength], 302h
0x18006affa  jmp     loc_18006B3E6
0x18006afff  xor     edx, edx; Val
0x18006b001  mov     r8d, 208h; Size
0x18006b007  lea     rcx, [rbp+200h+Buffer]; void *
0x18006b00b  call    memset_0
0x18006b010  mov     [rsp+300h+dwBufferLength], 103h
0x18006b018  mov     [rsp+300h+lpdwIndex], rbx; lpdwIndex
0x18006b01d  lea     rax, [rsp+300h+dwBufferLength]
0x18006b022  mov     [rsp+300h+lpdwBufferLength], rax; lpdwBufferLength
0x18006b027  lea     r9, [rbp+200h+Buffer]; lpBuffer
0x18006b02b  xor     r8d, r8d; pwszName
0x18006b02e  lea     edx, [r8+5]; dwInfoLevel
0x18006b032  mov     rcx, [rsp+300h+hRequest]; hRequest
0x18006b037  call    cs:__imp_WinHttpQueryHeaders
0x18006b03d  test    eax, eax
0x18006b03f  jz      short loc_18006B073
0x18006b041  xor     edx, edx; EndPtr
0x18006b043  lea     r8d, [rdx+0Ah]; Radix
0x18006b047  lea     rcx, [rbp+200h+Buffer]; String
0x18006b04b  call    cs:__imp__wcstoui64
0x18006b051  mov     rbx, rax
0x18006b054  lea     r14, [r15+60h]
0x18006b058  mov     rcx, [r14]
0x18006b05b  test    rcx, rcx
0x18006b05e  jz      loc_18006B28F
0x18006b064  mov     r9, rax
0x18006b067  lea     r8, aPreparefileHea; "PrepareFile: HEAD -> Content-Length=[%I"...
0x18006b06e  jmp     loc_18006B285
0x18006b073  call    cs:__imp_GetLastError
0x18006b079  cmp     eax, 2F76h
0x18006b07e  jnz     loc_18006B397
0x18006b084  lea     r14, [r15+60h]
0x18006b088  mov     rcx, [r14]
0x18006b08b  test    rcx, rcx
0x18006b08e  jz      short loc_18006B0A1
0x18006b090  lea     r8, aPreparefileCon_0; "PrepareFile: Content-Length header not "...
0x18006b097  mov     edx, 3
0x18006b09c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18006b0a1  mov     rcx, [rsp+300h+hRequest]; hInternet
0x18006b0a6  test    rcx, rcx
0x18006b0a9  jz      short loc_18006B0B6
0x18006b0ab  call    cs:__imp_WinHttpCloseHandle
0x18006b0b1  mov     [rsp+300h+hRequest], rbx
0x18006b0b6  mov     rcx, [rsp+300h+hInternet]; hInternet
0x18006b0bb  test    rcx, rcx
0x18006b0be  jz      short loc_18006B0CB
0x18006b0c0  call    cs:__imp_WinHttpCloseHandle
0x18006b0c6  mov     [rsp+300h+hInternet], rbx
0x18006b0cb  lea     rax, [rsp+300h+hRequest]
0x18006b0d0  mov     [rsp+300h+var_2D0], rax; void **
0x18006b0d5  lea     rax, [rsp+300h+hInternet]
0x18006b0da  mov     [rsp+300h+lpdwIndex], rax; void **
0x18006b0df  mov     [rsp+300h+lpdwBufferLength], rbx; union _LARGE_INTEGER *
0x18006b0e4  xor     r9d, r9d; union _LARGE_INTEGER *
0x18006b0e7  lea     r8, aGet; "GET"
0x18006b0ee  mov     rdx, r13; struct IDlpFile *
0x18006b0f1  mov     rcx, r15; this
0x18006b0f4  call    ?ConnectToSourceUrl@CDlpTransportHttp@@AEAAJPEAVIDlpFile@@PEBGPEAT_LARGE_INTEGER@@2PEAPEAX3@Z; CDlpTransportHttp::ConnectToSourceUrl(IDlpFile *,ushort const *,_LARGE_INTEGER *,_LARGE_INTEGER *,void * *,void * *)
0x18006b0f9  mov     esi, eax
0x18006b0fb  test    eax, eax
0x18006b0fd  jns     short loc_18006B11C
0x18006b0ff  mov     rcx, [r14]
0x18006b102  test    rcx, rcx
0x18006b105  jz      loc_18006B40E
0x18006b10b  mov     dword ptr [rsp+300h+lpdwIndex], eax
0x18006b10f  mov     dword ptr [rsp+300h+lpdwBufferLength], 322h
0x18006b117  jmp     loc_18006B3E6
0x18006b11c  mov     ebx, 8000h
0x18006b121  mov     [rsp+300h+dwBufferLength], ebx
0x18006b125  call    cs:__imp_GetProcessHeap
0x18006b12b  mov     rcx, rax; hHeap
0x18006b12e  mov     r8d, ebx; dwBytes
0x18006b131  xor     edx, edx; dwFlags
0x18006b133  call    cs:__imp_HeapAlloc
0x18006b139  mov     rdi, rax
0x18006b13c  xor     ebx, ebx
0x18006b13e  test    rax, rax
0x18006b141  jnz     short loc_18006B16C
0x18006b143  mov     edi, ebx
0x18006b145  mov     [rsp+300h+var_2A0], rbx
0x18006b14a  mov     esi, 8007000Eh
0x18006b14f  mov     rcx, [r14]
0x18006b152  test    rcx, rcx
0x18006b155  jz      loc_18006B412
0x18006b15b  mov     dword ptr [rsp+300h+lpdwIndex], esi
0x18006b15f  mov     dword ptr [rsp+300h+lpdwBufferLength], 326h
0x18006b167  jmp     loc_18006AF5F
0x18006b16c  mov     [rsp+300h+var_2A0], rdi
0x18006b171  mov     [rsp+300h+dwNumberOfBytesAvailable], ebx
0x18006b175  lea     rdx, [rsp+300h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x18006b17a  mov     rcx, [rsp+300h+hRequest]; hRequest
0x18006b17f  call    cs:__imp_WinHttpQueryDataAvailable
0x18006b185  test    eax, eax
0x18006b187  jnz     short loc_18006B1CE
0x18006b189  call    cs:__imp_GetLastError
0x18006b18f  mov     esi, eax
0x18006b191  test    eax, eax
0x18006b193  jnz     short loc_18006B19C
0x18006b195  mov     esi, 80004005h
0x18006b19a  jmp     short loc_18006B1A7
0x18006b19c  jle     short loc_18006B1A7
0x18006b19e  movzx   esi, ax
0x18006b1a1  or      esi, 80070000h
0x18006b1a7  cmp     [r14], rbx
0x18006b1aa  jz      loc_18006B40E
0x18006b1b0  mov     ecx, ebx
0x18006b1b2  test    esi, esi
0x18006b1b4  jns     loc_18006B409
0x18006b1ba  mov     dword ptr [rsp+300h+lpdwIndex], esi
0x18006b1be  mov     dword ptr [rsp+300h+lpdwBufferLength], 32Ch
0x18006b1c6  mov     rcx, [r14]
0x18006b1c9  jmp     loc_18006B3E6
0x18006b1ce  mov     eax, [rsp+300h+dwNumberOfBytesAvailable]
0x18006b1d2  test    eax, eax
0x18006b1d4  jz      loc_18006B273
0x18006b1da  mov     r15d, 80070216h
0x18006b1e0  mov     r8d, [rsp+300h+dwBufferLength]
0x18006b1e5  cmp     r8d, eax
0x18006b1e8  cmova   r8d, eax; dwNumberOfBytesToRead
0x18006b1ec  lea     r9, [rsp+300h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18006b1f1  mov     rdx, rdi; lpBuffer
0x18006b1f4  mov     rcx, [rsp+300h+hRequest]; hRequest
0x18006b1f9  call    cs:__imp_WinHttpReadData
0x18006b1ff  test    eax, eax
0x18006b201  jz      loc_18006B353
0x18006b207  mov     eax, [rsp+300h+dwBufferLength]
0x18006b20b  cmp     eax, [rsp+300h+dwNumberOfBytesAvailable]
0x18006b20f  cmova   eax, [rsp+300h+dwNumberOfBytesAvailable]
0x18006b214  cmp     [rsp+300h+dwNumberOfBytesRead], eax
0x18006b218  jnz     loc_18006B331
0x18006b21e  mov     ecx, [rsp+300h+dwNumberOfBytesRead]
0x18006b222  add     rcx, rbx
0x18006b225  cmp     rcx, rbx
0x18006b228  jb      short loc_18006B231
0x18006b22a  mov     rbx, rcx
0x18006b22d  xor     esi, esi
0x18006b22f  jmp     short loc_18006B23C
0x18006b231  mov     esi, r15d
0x18006b234  mov     ecx, r15d
0x18006b237  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006b23c  mov     ecx, esi
0x18006b23e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006b243  test    esi, esi
0x18006b245  js      loc_18006B312
0x18006b24b  mov     [rsp+300h+dwNumberOfBytesAvailable], 0
0x18006b253  lea     rdx, [rsp+300h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x18006b258  mov     rcx, [rsp+300h+hRequest]; hRequest
0x18006b25d  call    cs:__imp_WinHttpQueryDataAvailable
0x18006b263  test    eax, eax
0x18006b265  jz      short loc_18006B2CE
0x18006b267  mov     eax, [rsp+300h+dwNumberOfBytesAvailable]
0x18006b26b  test    eax, eax
0x18006b26d  jnz     loc_18006B1E0
0x18006b273  mov     rcx, [r14]
0x18006b276  test    rcx, rcx
0x18006b279  jz      short loc_18006B28F
0x18006b27b  mov     r9, rbx
0x18006b27e  lea     r8, aPreparefileCon; "PrepareFile: Content-Length=[%I64u]"
0x18006b285  mov     edx, 2
0x18006b28a  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18006b28f  xor     r8d, r8d
0x18006b292  lea     rcx, [r13+10h]
0x18006b296  mov     rax, [rcx]
0x18006b299  mov     rdx, rbx
0x18006b29c  mov     rax, [rax+8]
0x18006b2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2a5  mov     esi, eax
0x18006b2a7  xor     ebx, ebx
0x18006b2a9  test    eax, eax
0x18006b2ab  jns     loc_18006B46F
0x18006b2b1  mov     rcx, [r14]
0x18006b2b4  test    rcx, rcx
0x18006b2b7  jz      loc_18006B40E
0x18006b2bd  mov     dword ptr [rsp+300h+lpdwIndex], eax
0x18006b2c1  mov     dword ptr [rsp+300h+lpdwBufferLength], 349h
0x18006b2c9  jmp     loc_18006B3E6
0x18006b2ce  call    cs:__imp_GetLastError
0x18006b2d4  mov     esi, eax
0x18006b2d6  xor     ebx, ebx
0x18006b2d8  test    eax, eax
0x18006b2da  jnz     short loc_18006B2E3
0x18006b2dc  mov     esi, 80004005h
0x18006b2e1  jmp     short loc_18006B2EE
0x18006b2e3  jle     short loc_18006B2EE
0x18006b2e5  movzx   esi, ax
0x18006b2e8  or      esi, 80070000h
0x18006b2ee  cmp     [r14], rbx
0x18006b2f1  jz      loc_18006B40E
0x18006b2f7  mov     ecx, ebx
0x18006b2f9  test    esi, esi
0x18006b2fb  jns     loc_18006B409
0x18006b301  mov     dword ptr [rsp+300h+lpdwIndex], esi
0x18006b305  mov     dword ptr [rsp+300h+lpdwBufferLength], 33Bh
0x18006b30d  jmp     loc_18006B1C6
0x18006b312  mov     rcx, [r14]
0x18006b315  xor     ebx, ebx
0x18006b317  test    rcx, rcx
0x18006b31a  jz      loc_18006B40E
0x18006b320  mov     dword ptr [rsp+300h+lpdwIndex], esi
0x18006b324  mov     dword ptr [rsp+300h+lpdwBufferLength], 335h
0x18006b32c  jmp     loc_18006B3E6
0x18006b331  mov     esi, 80004005h
0x18006b336  mov     rcx, [r14]
0x18006b339  test    rcx, rcx
0x18006b33c  jz      loc_18006B412
0x18006b342  mov     dword ptr [rsp+300h+lpdwIndex], esi
0x18006b346  mov     dword ptr [rsp+300h+lpdwBufferLength], 333h
0x18006b34e  jmp     loc_18006AF5F
0x18006b353  call    cs:__imp_GetLastError
0x18006b359  mov     esi, eax
0x18006b35b  xor     ebx, ebx
0x18006b35d  test    eax, eax
0x18006b35f  jnz     short loc_18006B368
0x18006b361  mov     esi, 80004005h
0x18006b366  jmp     short loc_18006B373
0x18006b368  jle     short loc_18006B373
0x18006b36a  movzx   esi, ax
0x18006b36d  or      esi, 80070000h
0x18006b373  cmp     [r14], rbx
0x18006b376  jz      loc_18006B40E
0x18006b37c  mov     ecx, ebx
0x18006b37e  test    esi, esi
0x18006b380  jns     loc_18006B409
0x18006b386  mov     dword ptr [rsp+300h+lpdwIndex], esi
0x18006b38a  mov     dword ptr [rsp+300h+lpdwBufferLength], 332h
  ... truncated ...
```
