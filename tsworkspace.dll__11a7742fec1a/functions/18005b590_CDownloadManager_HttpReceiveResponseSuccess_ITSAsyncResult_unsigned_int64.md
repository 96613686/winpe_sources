# CDownloadManager::HttpReceiveResponseSuccess(ITSAsyncResult *,unsigned __int64)

- ea: `0x18005b590`
- end: `0x18005bab0`
- name: `?HttpReceiveResponseSuccess@CDownloadManager@@MEAAJPEAVITSAsyncResult@@_K@Z`
- size: `1312`
- prototype: `__int64 __fastcall(CDownloadManager *__hidden this, struct ITSAsyncResult *, unsigned __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003108`
- `0x18000b1d8`
- `0x18000dbdc`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e5d8`
- `0x180059088`
- `0x18005913c`
- `0x18005a5f0`
- `0x18005b590`
- `0x18005d018`

## import_xrefs

- `msvcrt!wcscspn` at `0x18005b8fc`
- `msvcrt!wcscspn` at `0x18005b8fc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18005ba06`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18005ba06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b95e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b7e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b89f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b8d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b95e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b933`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005b933`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005b63c`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005b7d9`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005b878`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005b63c`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005b7d9`
- `WINHTTP!WinHttpQueryHeaders` at `0x18005b878`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDownloadManager::HttpReceiveResponseSuccess(
        CDownloadManager *this,
        struct ITSAsyncResult *a2,
        __int64 a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v6; // r8d
  signed int LastError; // edi
  unsigned int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  wchar_t *v17; // rbx
  wchar_t *v18; // rax
  unsigned int v19; // eax
  signed int v20; // eax
  unsigned int v21; // edi
  unsigned int v22; // eax
  __int64 v23; // rdx
  signed int v24; // eax
  size_t v25; // rcx
  int v26; // eax
  signed int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  void *v30; // rbx
  void *v31; // rax
  LPDWORD lpdwIndex; // [rsp+30h] [rbp-31h]
  LPDWORD lpdwIndexa; // [rsp+30h] [rbp-31h]
  __int64 dwBufferLength; // [rsp+38h] [rbp-29h] BYREF
  __int64 v36; // [rsp+40h] [rbp-21h]
  _BYTE *v37; // [rsp+48h] [rbp-19h]
  _BYTE *v38; // [rsp+50h] [rbp-11h]
  _BYTE v39[32]; // [rsp+58h] [rbp-9h] BYREF
  _BYTE v40[32]; // [rsp+78h] [rbp+17h] BYREF
  DWORD lpdwBufferLength; // [rsp+D8h] [rbp+77h] BYREF
  int Buffer; // [rsp+E0h] [rbp+7Fh] BYREF

  v36 = -2;
  Buffer = 0;
  LODWORD(dwBufferLength) = 4;
  lpdwBufferLength = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      80,
      &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  if ( !WinHttpQueryHeaders(*(HINTERNET *)(a3 + 40), 0x20000013u, 0, &Buffer, (LPDWORD)&dwBufferLength, 0) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        81,
        &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v8,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    goto LABEL_75;
  }
  v9 = Buffer;
  *(_DWORD *)(a3 + 156) = Buffer;
  v10 = v9 - 200;
  if ( v10 )
  {
    v11 = v10 - 201;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( v12 && (v13 = v12 - 98) != 0 && v13 != 2 )
        LastError = -2147220987;
      else
        LastError = -2147012868;
      goto LABEL_75;
    }
    LastError = CDownloadManager::HandleAuthError(this, (struct _DM_CONTEXT *)a3, v6);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_75;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 87;
      v16 = "HandleAuthError failed";
      goto LABEL_27;
    }
    v17 = 0;
    LastError = CDownloadManager::CallSendRequest(this, (struct _DM_CONTEXT *)a3);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_75;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 88;
      v16 = "CallSendRequest failed";
LABEL_27:
      LODWORD(lpdwIndex) = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
        v14,
        (__int64)v16,
        lpdwIndex,
        dwBufferLength,
        v36);
      goto LABEL_75;
    }
    goto LABEL_69;
  }
  if ( (unsigned int)(*((_DWORD *)this + 106) - 2) <= 1 )
    *((_DWORD *)this + 107) = 2;
  if ( !WinHttpQueryHeaders(*(HINTERNET *)(a3 + 40), 1u, 0, 0, &lpdwBufferLength, 0) && GetLastError() == 122 )
  {
    v18 = (wchar_t *)operator new[](lpdwBufferLength, (const struct std::nothrow_t *)&std::nothrow);
    v17 = v18;
    if ( !v18 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          82,
          &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
          v19,
          -2147024882);
      }
      LastError = -2147024882;
      goto LABEL_75;
    }
    *v18 = 0;
    if ( WinHttpQueryHeaders(*(HINTERNET *)(a3 + 40), 1u, 0, v18, &lpdwBufferLength, 0) )
    {
      v25 = 2 * wcscspn(v17, L";");
      if ( v25 < lpdwBufferLength )
        v17[v25 / 2] = 0;
      v26 = CompareStringW(0x7Fu, 1u, v17, -1, L"application/x-msts-webfeed-login", -1);
      if ( v26 )
      {
        if ( v26 == 2 )
        {
          *(_DWORD *)(a3 + 152) = 1;
          std::wstring::assign((char *)this + 1984, &LocaleName);
        }
        LastError = CDownloadManager::CallQueryData(this, (struct _DM_CONTEXT *)a3);
        if ( LastError >= 0 )
        {
LABEL_69:
          LastError = 0;
          if ( !v17 )
            goto LABEL_75;
          goto LABEL_70;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v28 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(lpdwIndexa) = LastError;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            86,
            (unsigned int)&WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids,
            v28,
            (__int64)"CallQueryData failed",
            lpdwIndexa,
            dwBufferLength,
            v36);
        }
LABEL_70:
        operator delete[](v17);
        goto LABEL_75;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = GetLastError();
        v21 = v27;
        if ( v27 > 0 )
          v21 = (unsigned __int16)v27 | 0x80070000;
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        v23 = 84;
        goto LABEL_50;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v20 = GetLastError();
      v21 = v20;
      if ( v20 > 0 )
        v21 = (unsigned __int16)v20 | 0x80070000;
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 83;
LABEL_50:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v22, v21);
    }
    v24 = GetLastError();
    LastError = v24;
    if ( v24 > 0 )
      LastError = (unsigned __int16)v24 | 0x80070000;
    goto LABEL_70;
  }
  LastError = -2147418113;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids, v29);
  }
LABEL_75:
  if ( LastError < 0 )
  {
    v37 = v39;
    v30 = (void *)std::wstring::wstring(v39, a3 + 80);
    v38 = v40;
    v31 = (void *)std::wstring::wstring(v40, a3 + 48);
    CDownloadManager::ReportDownloadStatus(this, LastError, a3, v31, v30);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18005b590  mov     rax, rsp
0x18005b593  push    rbp
0x18005b594  push    rdi
0x18005b595  push    r13
0x18005b597  push    r14
0x18005b599  push    r15
0x18005b59b  lea     rbp, [rax-5Fh]
0x18005b59f  sub     rsp, 90h
0x18005b5a6  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x18005b5ae  mov     [rax+8], rbx
0x18005b5b2  mov     [rax+10h], rsi
0x18005b5b6  mov     r14, r8
0x18005b5b9  mov     r15, rcx
0x18005b5bc  mov     [rbp+57h+Buffer], 0
0x18005b5c3  mov     dword ptr [rbp+57h+dwBufferLength], 4
0x18005b5ca  mov     [rbp+57h+arg_10], 0
0x18005b5d1  lea     r13, WPP_GLOBAL_Control
0x18005b5d8  lea     rbx, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005b5df  mov     esi, 1
0x18005b5e4  mov     rax, cs:WPP_GLOBAL_Control
0x18005b5eb  cmp     rax, r13
0x18005b5ee  jz      short loc_18005B61A
0x18005b5f0  test    [rax+1Ch], sil
0x18005b5f4  jz      short loc_18005B61A
0x18005b5f6  cmp     byte ptr [rax+19h], 4
0x18005b5fa  jb      short loc_18005B61A
0x18005b5fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b601  lea     edx, [rsi+4Fh]
0x18005b604  mov     r9d, eax
0x18005b607  mov     r8, rbx
0x18005b60a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b611  mov     rcx, [rcx+10h]
0x18005b615  call    WPP_SF_D
0x18005b61a  mov     [rsp+0B0h+lpdwIndex], 0; lpdwIndex
0x18005b623  lea     rax, [rbp+57h+dwBufferLength]
0x18005b627  mov     [rsp+0B0h+lpdwBufferLength], rax; lpdwBufferLength
0x18005b62c  lea     r9, [rbp+57h+Buffer]; lpBuffer
0x18005b630  xor     r8d, r8d; pwszName
0x18005b633  mov     edx, 20000013h; dwInfoLevel
0x18005b638  mov     rcx, [r14+28h]; hRequest
0x18005b63c  call    cs:__imp_WinHttpQueryHeaders
0x18005b642  test    eax, eax
0x18005b644  jnz     short loc_18005B6A6
0x18005b646  call    cs:__imp_GetLastError
0x18005b64c  mov     edi, eax
0x18005b64e  mov     rax, cs:WPP_GLOBAL_Control
0x18005b655  cmp     rax, r13
0x18005b658  jz      short loc_18005B68A
0x18005b65a  test    byte ptr [rax+1Ch], 8
0x18005b65e  jz      short loc_18005B68A
0x18005b660  cmp     byte ptr [rax+19h], 2
0x18005b664  jb      short loc_18005B68A
0x18005b666  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b66b  mov     edx, 51h ; 'Q'
0x18005b670  mov     dword ptr [rsp+0B0h+lpdwBufferLength], edi
0x18005b674  mov     r9d, eax
0x18005b677  mov     r8, rbx
0x18005b67a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b681  mov     rcx, [rcx+10h]
0x18005b685  call    WPP_SF_Dd
0x18005b68a  test    edi, edi
0x18005b68c  jle     short loc_18005B697
0x18005b68e  movzx   edi, di
0x18005b691  or      edi, 80070000h
0x18005b697  mov     eax, 80004005h
0x18005b69c  test    edi, edi
0x18005b69e  cmovns  edi, eax
0x18005b6a1  jmp     loc_18005BA4B
0x18005b6a6  mov     eax, [rbp+57h+Buffer]
0x18005b6a9  mov     [r14+9Ch], eax
0x18005b6b0  sub     eax, 0C8h
0x18005b6b5  jz      loc_18005B7A2
0x18005b6bb  sub     eax, 0C9h
0x18005b6c0  jz      short loc_18005B6E5
0x18005b6c2  sub     eax, 3
0x18005b6c5  jz      short loc_18005B6DB
0x18005b6c7  sub     eax, 62h ; 'b'
0x18005b6ca  jz      short loc_18005B6DB
0x18005b6cc  cmp     eax, 2
0x18005b6cf  jz      short loc_18005B6DB
0x18005b6d1  mov     edi, 80040205h
0x18005b6d6  jmp     loc_18005BA4B
0x18005b6db  mov     edi, 80072EFCh
0x18005b6e0  jmp     loc_18005BA4B
0x18005b6e5  mov     rdx, r14; struct _DM_CONTEXT *
0x18005b6e8  mov     rcx, r15; this
0x18005b6eb  call    ?HandleAuthError@CDownloadManager@@IEAAJPEAU_DM_CONTEXT@@K@Z; CDownloadManager::HandleAuthError(_DM_CONTEXT *,ulong)
0x18005b6f0  mov     edi, eax
0x18005b6f2  test    eax, eax
0x18005b6f4  jns     short loc_18005B74F
0x18005b6f6  mov     rax, cs:WPP_GLOBAL_Control
0x18005b6fd  cmp     rax, r13
0x18005b700  jz      loc_18005BA4B
0x18005b706  test    byte ptr [rax+1Ch], 8
0x18005b70a  jz      loc_18005BA4B
0x18005b710  cmp     byte ptr [rax+19h], 2
0x18005b714  jb      loc_18005BA4B
0x18005b71a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b71f  mov     edx, 57h ; 'W'
0x18005b724  lea     rcx, aHandleautherro; "HandleAuthError failed"
0x18005b72b  mov     r8, rbx
0x18005b72e  mov     dword ptr [rsp+0B0h+lpdwIndex], edi
0x18005b732  mov     r9d, eax
0x18005b735  mov     [rsp+0B0h+lpdwBufferLength], rcx
0x18005b73a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b741  mov     rcx, [rcx+10h]
0x18005b745  call    WPP_SF_DsD
0x18005b74a  jmp     loc_18005BA4B
0x18005b74f  xor     ebx, ebx
0x18005b751  mov     rdx, r14; struct _DM_CONTEXT *
0x18005b754  mov     rcx, r15; this
0x18005b757  call    ?CallSendRequest@CDownloadManager@@IEAAJPEAU_DM_CONTEXT@@@Z; CDownloadManager::CallSendRequest(_DM_CONTEXT *)
0x18005b75c  mov     edi, eax
0x18005b75e  test    eax, eax
0x18005b760  jns     loc_18005B9FC
0x18005b766  mov     rax, cs:WPP_GLOBAL_Control
0x18005b76d  cmp     rax, r13
0x18005b770  jz      loc_18005BA4B
0x18005b776  test    byte ptr [rax+1Ch], 8
0x18005b77a  jz      loc_18005BA4B
0x18005b780  cmp     byte ptr [rax+19h], 2
0x18005b784  jb      loc_18005BA4B
0x18005b78a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b78f  lea     edx, [rbx+58h]
0x18005b792  lea     rcx, aCallsendreques; "CallSendRequest failed"
0x18005b799  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005b7a0  jmp     short loc_18005B72E
0x18005b7a2  mov     eax, [r15+1A8h]
0x18005b7a9  sub     eax, 2
0x18005b7ac  cmp     eax, esi
0x18005b7ae  ja      short loc_18005B7BB
0x18005b7b0  mov     dword ptr [r15+1ACh], 2
0x18005b7bb  mov     [rsp+0B0h+lpdwIndex], 0; lpdwIndex
0x18005b7c4  lea     rax, [rbp+57h+arg_10]
0x18005b7c8  mov     [rsp+0B0h+lpdwBufferLength], rax; lpdwBufferLength
0x18005b7cd  xor     r9d, r9d; lpBuffer
0x18005b7d0  xor     r8d, r8d; pwszName
0x18005b7d3  mov     edx, esi; dwInfoLevel
0x18005b7d5  mov     rcx, [r14+28h]; hRequest
0x18005b7d9  call    cs:__imp_WinHttpQueryHeaders
0x18005b7df  test    eax, eax
0x18005b7e1  jnz     loc_18005BA0E
0x18005b7e7  call    cs:__imp_GetLastError
0x18005b7ed  cmp     eax, 7Ah ; 'z'
0x18005b7f0  jnz     loc_18005BA0E
0x18005b7f6  mov     ecx, [rbp+57h+arg_10]; unsigned __int64
0x18005b7f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005b800  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18005b805  mov     rbx, rax
0x18005b808  test    rax, rax
0x18005b80b  jnz     short loc_18005B859
0x18005b80d  mov     rax, cs:WPP_GLOBAL_Control
0x18005b814  cmp     rax, r13
0x18005b817  jz      short loc_18005B84F
0x18005b819  test    byte ptr [rax+1Ch], 8
0x18005b81d  jz      short loc_18005B84F
0x18005b81f  cmp     byte ptr [rax+19h], 2
0x18005b823  jb      short loc_18005B84F
0x18005b825  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b82a  lea     edx, [rbx+52h]
0x18005b82d  mov     dword ptr [rsp+0B0h+lpdwBufferLength], 8007000Eh
0x18005b835  mov     r9d, eax
0x18005b838  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005b83f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b846  mov     rcx, [rcx+10h]
0x18005b84a  call    WPP_SF_Dd
0x18005b84f  mov     edi, 8007000Eh
0x18005b854  jmp     loc_18005BA4B
0x18005b859  xor     eax, eax
0x18005b85b  mov     [rbx], ax
0x18005b85e  mov     [rsp+0B0h+lpdwIndex], rax; lpdwIndex
0x18005b863  lea     rax, [rbp+57h+arg_10]
0x18005b867  mov     [rsp+0B0h+lpdwBufferLength], rax; lpdwBufferLength
0x18005b86c  mov     r9, rbx; lpBuffer
0x18005b86f  xor     r8d, r8d; pwszName
0x18005b872  mov     edx, esi; dwInfoLevel
0x18005b874  mov     rcx, [r14+28h]; hRequest
0x18005b878  call    cs:__imp_WinHttpQueryHeaders
0x18005b87e  test    eax, eax
0x18005b880  jnz     short loc_18005B8F2
0x18005b882  mov     esi, 80070000h
0x18005b887  mov     rax, cs:WPP_GLOBAL_Control
0x18005b88e  cmp     rax, r13
0x18005b891  jz      short loc_18005B8D8
0x18005b893  test    byte ptr [rax+1Ch], 8
0x18005b897  jz      short loc_18005B8D8
0x18005b899  cmp     byte ptr [rax+19h], 2
0x18005b89d  jb      short loc_18005B8D8
0x18005b89f  call    cs:__imp_GetLastError
0x18005b8a5  mov     edi, eax
0x18005b8a7  test    eax, eax
0x18005b8a9  jle     short loc_18005B8B0
0x18005b8ab  movzx   edi, ax
0x18005b8ae  or      edi, esi
0x18005b8b0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b8b5  mov     edx, 53h ; 'S'
0x18005b8ba  mov     dword ptr [rsp+0B0h+lpdwBufferLength], edi
0x18005b8be  mov     r9d, eax
0x18005b8c1  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005b8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b8cf  mov     rcx, [rcx+10h]
0x18005b8d3  call    WPP_SF_Dd
0x18005b8d8  call    cs:__imp_GetLastError
0x18005b8de  mov     edi, eax
0x18005b8e0  test    eax, eax
0x18005b8e2  jle     loc_18005BA03
0x18005b8e8  movzx   edi, ax
0x18005b8eb  or      edi, esi
0x18005b8ed  jmp     loc_18005BA03
0x18005b8f2  lea     rdx, Control; ";"
0x18005b8f9  mov     rcx, rbx; String
0x18005b8fc  call    cs:__imp_wcscspn
0x18005b902  lea     rcx, [rax+rax]
0x18005b906  mov     eax, [rbp+57h+arg_10]
0x18005b909  cmp     rcx, rax
0x18005b90c  jnb     short loc_18005B914
0x18005b90e  xor     eax, eax
0x18005b910  mov     [rcx+rbx], ax
0x18005b914  or      r9d, 0FFFFFFFFh; cchCount1
0x18005b918  mov     dword ptr [rsp+0B0h+lpdwIndex], r9d; cchCount2
0x18005b91d  lea     rax, aApplicationXMs_2; "application/x-msts-webfeed-login"
0x18005b924  mov     [rsp+0B0h+lpdwBufferLength], rax; lpString2
0x18005b929  mov     r8, rbx; lpString1
0x18005b92c  mov     edx, esi; dwCmpFlags
0x18005b92e  mov     ecx, 7Fh; Locale
0x18005b933  call    cs:__imp_CompareStringW
0x18005b939  test    eax, eax
0x18005b93b  jnz     short loc_18005B97E
0x18005b93d  mov     esi, 80070000h
0x18005b942  mov     rax, cs:WPP_GLOBAL_Control
0x18005b949  cmp     rax, r13
0x18005b94c  jz      short loc_18005B8D8
0x18005b94e  test    byte ptr [rax+1Ch], 8
0x18005b952  jz      short loc_18005B8D8
0x18005b954  cmp     byte ptr [rax+19h], 2
0x18005b958  jb      loc_18005B8D8
0x18005b95e  call    cs:__imp_GetLastError
0x18005b964  mov     edi, eax
0x18005b966  test    eax, eax
0x18005b968  jle     short loc_18005B96F
0x18005b96a  movzx   edi, ax
0x18005b96d  or      edi, esi
0x18005b96f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b974  mov     edx, 54h ; 'T'
0x18005b979  jmp     loc_18005B8BA
0x18005b97e  cmp     eax, 2
0x18005b981  jnz     short loc_18005B99D
0x18005b983  mov     [r14+98h], esi
0x18005b98a  lea     rcx, [r15+7C0h]
0x18005b991  lea     rdx, LocaleName
0x18005b998  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18005b99d  mov     rdx, r14; struct _DM_CONTEXT *
0x18005b9a0  mov     rcx, r15; this
0x18005b9a3  call    ?CallQueryData@CDownloadManager@@IEAAJPEAU_DM_CONTEXT@@@Z; CDownloadManager::CallQueryData(_DM_CONTEXT *)
0x18005b9a8  mov     edi, eax
0x18005b9aa  test    eax, eax
0x18005b9ac  jns     short loc_18005B9FC
0x18005b9ae  mov     rax, cs:WPP_GLOBAL_Control
0x18005b9b5  cmp     rax, r13
0x18005b9b8  jz      short loc_18005BA03
0x18005b9ba  test    byte ptr [rax+1Ch], 8
0x18005b9be  jz      short loc_18005BA03
0x18005b9c0  cmp     byte ptr [rax+19h], 2
0x18005b9c4  jb      short loc_18005BA03
0x18005b9c6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005b9cb  mov     edx, 56h ; 'V'
0x18005b9d0  mov     dword ptr [rsp+0B0h+lpdwIndex], edi
0x18005b9d4  lea     rcx, aCallquerydataF; "CallQueryData failed"
0x18005b9db  mov     [rsp+0B0h+lpdwBufferLength], rcx
0x18005b9e0  mov     r9d, eax
0x18005b9e3  lea     r8, WPP_8e224024bd62311eb89a10ac029d17ad_Traceguids
0x18005b9ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b9f1  mov     rcx, [rcx+10h]
0x18005b9f5  call    WPP_SF_DsD
0x18005b9fa  jmp     short loc_18005BA03
0x18005b9fc  xor     edi, edi
0x18005b9fe  test    rbx, rbx
0x18005ba01  jz      short loc_18005BA4B
0x18005ba03  mov     rcx, rbx
0x18005ba06  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18005ba0c  jmp     short loc_18005BA4B
0x18005ba0e  mov     edi, 8000FFFFh
0x18005ba13  mov     rax, cs:WPP_GLOBAL_Control
0x18005ba1a  cmp     rax, r13
0x18005ba1d  jz      short loc_18005BA4B
0x18005ba1f  test    [rax+1Ch], sil
0x18005ba23  jz      short loc_18005BA4B
0x18005ba25  cmp     byte ptr [rax+19h], 2
0x18005ba29  jb      short loc_18005BA4B
0x18005ba2b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005ba30  mov     edx, 55h ; 'U'
0x18005ba35  mov     r9d, eax
0x18005ba38  mov     r8, rbx
0x18005ba3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ba42  mov     rcx, [rcx+10h]
0x18005ba46  call    WPP_SF_D
0x18005ba4b  test    edi, edi
0x18005ba4d  jns     short loc_18005BA92
0x18005ba4f  lea     rax, [rbp+57h+var_60]
0x18005ba53  mov     [rbp+57h+var_70], rax
  ... truncated ...
```
