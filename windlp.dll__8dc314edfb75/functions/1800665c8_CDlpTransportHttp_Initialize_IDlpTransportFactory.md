# CDlpTransportHttp::Initialize(IDlpTransportFactory *)

- ea: `0x1800665c8`
- end: `0x1800667a5`
- name: `?Initialize@CDlpTransportHttp@@QEAAJPEAVIDlpTransportFactory@@@Z`
- size: `477`
- prototype: `__int64 __fastcall(CDlpTransportHttp *__hidden this, struct IDlpTransportFactory *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004f010`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x1800665c8`
- `0x18006e40c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800666f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800666f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006660b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006660b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066632`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180066632`
- `WINHTTP!WinHttpCloseHandle` at `0x1800666e2`
- `WINHTTP!WinHttpCloseHandle` at `0x1800666e2`
- `WINHTTP!WinHttpOpen` at `0x1800666cd`
- `WINHTTP!WinHttpOpen` at `0x1800666cd`

## pseudocode

```c
__int64 __fastcall CDlpTransportHttp::Initialize(CDlpTransportHttp *this, struct IDlpTransportFactory *a2)
{
  __int64 v4; // rcx
  signed int v5; // ebx
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  int v7; // r15d
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  HINTERNET v11; // rax
  void *v12; // rcx
  HINTERNET v13; // rbx
  signed int LastError; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  __int64 dwFlags; // [rsp+20h] [rbp-58h]
  __int64 v21; // [rsp+28h] [rbp-50h]

  if ( a2 )
  {
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
    v7 = *((_DWORD *)this + 50);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    LeaveCriticalSection(v6);
    v5 = 0;
    if ( v7 != -21037378 )
    {
      v8 = *((_QWORD *)this + 12);
      v5 = -2147023649;
      if ( v8 )
      {
        v9 = CDlpLogT<CEmptyType>::DlpLogFormat(
               v8,
               4u,
               (__int64)L"%s(%d): Result = 0x%X",
               L"CDlpTransportImpl<class CDlpErrorImpl<class CDlpObjectInternalImpl<class CUnknownRefChainImpl<class IDlpT"
                "ransport> > > >::CheckUninitialized",
               2787,
               -2147023649);
        v10 = (unsigned int)v9;
        if ( v9 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
      }
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
    if ( v5 >= 0 )
    {
      v11 = WinHttpOpen(L"Windows Dlp Manager", 0, 0, 0, 0);
      v12 = (void *)*((_QWORD *)this + 69);
      v13 = v11;
      if ( v12 )
        WinHttpCloseHandle(v12);
      if ( v13 )
      {
        *((_QWORD *)this + 69) = v13;
        *((_QWORD *)this + 11) = a2;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        v17 = CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>::ResetState(
                this,
                v16,
                0);
        v5 = v17;
        if ( v17 >= 0 )
          goto LABEL_30;
        v4 = *((_QWORD *)this + 12);
        if ( !v4 )
          goto LABEL_30;
        LODWORD(v21) = v17;
        LODWORD(dwFlags) = 128;
      }
      else
      {
        *((_QWORD *)this + 69) = 0;
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v5 = -2147467259;
        }
        if ( !*((_QWORD *)this + 12) )
          goto LABEL_30;
        v15 = 0;
        if ( v5 >= 0 )
        {
LABEL_29:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
          goto LABEL_30;
        }
        v4 = *((_QWORD *)this + 12);
        LODWORD(v21) = v5;
        LODWORD(dwFlags) = 120;
      }
    }
    else
    {
      v4 = *((_QWORD *)this + 12);
      if ( !v4 )
        goto LABEL_30;
      LODWORD(v21) = v5;
      LODWORD(dwFlags) = 111;
    }
LABEL_27:
    v18 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v4,
            4u,
            (__int64)L"%s(%d): Result = 0x%X",
            L"CDlpTransportHttp::Initialize",
            dwFlags,
            v21);
    v15 = (unsigned int)v18;
    if ( v18 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
    goto LABEL_29;
  }
  v4 = *((_QWORD *)this + 12);
  v5 = -2147024809;
  if ( v4 )
  {
    LODWORD(v21) = -2147024809;
    LODWORD(dwFlags) = 107;
    goto LABEL_27;
  }
LABEL_30:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800665c8  push    rbx
0x1800665ca  push    rdi
0x1800665cb  push    r14
0x1800665cd  push    r15
0x1800665cf  sub     rsp, 58h
0x1800665d3  mov     r14, rdx
0x1800665d6  mov     rdi, rcx
0x1800665d9  test    rdx, rdx
0x1800665dc  jnz     short loc_180066601
0x1800665de  mov     rcx, [rcx+60h]
0x1800665e2  mov     ebx, 80070057h
0x1800665e7  test    rcx, rcx
0x1800665ea  jz      loc_180066791
0x1800665f0  mov     dword ptr [rsp+78h+var_50], ebx
0x1800665f4  mov     dword ptr [rsp+78h+dwFlags], 6Bh ; 'k'
0x1800665fc  jmp     loc_180066769
0x180066601  lea     rbx, [rcx+0D8h]
0x180066608  mov     rcx, rbx; lpCriticalSection
0x18006660b  call    cs:__imp_EnterCriticalSection
0x180066611  mov     r15d, [rdi+0C8h]
0x180066618  mov     [rsp+78h+var_38], 1
0x180066620  xor     ecx, ecx
0x180066622  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180066627  mov     eax, [rsp+78h+var_38]
0x18006662b  test    eax, eax
0x18006662d  jz      short loc_180066640
0x18006662f  mov     rcx, rbx; lpCriticalSection
0x180066632  call    cs:__imp_LeaveCriticalSection
0x180066638  mov     [rsp+78h+var_38], 0
0x180066640  xor     ebx, ebx
0x180066642  cmp     r15d, 0FEBEFEBEh
0x180066649  jz      short loc_18006668D
0x18006664b  mov     rcx, [rdi+60h]
0x18006664f  mov     ebx, 800704DFh
0x180066654  test    rcx, rcx
0x180066657  jz      short loc_18006668D
0x180066659  mov     dword ptr [rsp+78h+var_50], ebx
0x18006665d  lea     r9, aCdlptransporti_15; "CDlpTransportImpl<class CDlpErrorImpl<c"...
0x180066664  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006666b  mov     dword ptr [rsp+78h+dwFlags], 0AE3h
0x180066673  mov     edx, 4
0x180066678  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18006667d  mov     ecx, eax
0x18006667f  test    eax, eax
0x180066681  jns     short loc_180066688
0x180066683  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180066688  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006668d  mov     ecx, ebx
0x18006668f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180066694  test    ebx, ebx
0x180066696  jns     short loc_1800666B6
0x180066698  mov     rcx, [rdi+60h]
0x18006669c  test    rcx, rcx
0x18006669f  jz      loc_180066791
0x1800666a5  mov     dword ptr [rsp+78h+var_50], ebx
0x1800666a9  mov     dword ptr [rsp+78h+dwFlags], 6Fh ; 'o'
0x1800666b1  jmp     loc_180066769
0x1800666b6  xor     r9d, r9d; pszProxyBypassW
0x1800666b9  mov     dword ptr [rsp+78h+dwFlags], 0; dwFlags
0x1800666c1  xor     r8d, r8d; pszProxyW
0x1800666c4  lea     rcx, pszAgentW; "Windows Dlp Manager"
0x1800666cb  xor     edx, edx; dwAccessType
0x1800666cd  call    cs:__imp_WinHttpOpen
0x1800666d3  mov     rcx, [rdi+228h]; hInternet
0x1800666da  mov     rbx, rax
0x1800666dd  test    rcx, rcx
0x1800666e0  jz      short loc_1800666E8
0x1800666e2  call    cs:__imp_WinHttpCloseHandle
0x1800666e8  test    rbx, rbx
0x1800666eb  jnz     short loc_180066731
0x1800666ed  mov     [rdi+228h], rbx
0x1800666f4  call    cs:__imp_GetLastError
0x1800666fa  mov     ebx, eax
0x1800666fc  test    eax, eax
0x1800666fe  jnz     short loc_180066707
0x180066700  mov     ebx, 80004005h
0x180066705  jmp     short loc_180066712
0x180066707  jle     short loc_180066712
0x180066709  movzx   ebx, ax
0x18006670c  or      ebx, 80070000h
0x180066712  cmp     qword ptr [rdi+60h], 0
0x180066717  jz      short loc_180066791
0x180066719  xor     ecx, ecx
0x18006671b  test    ebx, ebx
0x18006671d  jns     short loc_18006678C
0x18006671f  mov     rcx, [rdi+60h]
0x180066723  mov     dword ptr [rsp+78h+var_50], ebx
0x180066727  mov     dword ptr [rsp+78h+dwFlags], 78h ; 'x'
0x18006672f  jmp     short loc_180066769
0x180066731  mov     [rdi+228h], rbx
0x180066738  mov     [rdi+58h], r14
0x18006673c  xor     ecx, ecx
0x18006673e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180066743  xor     r8d, r8d
0x180066746  mov     rcx, rdi
0x180066749  call    ?ResetState@?$CDlpTransportImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownRefChainImpl@VIDlpTransport@@@@@@@@@@QEAAJW4WINDLP_STATE@@H@Z; CDlpTransportImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownRefChainImpl<IDlpTransport>>>>::ResetState(WINDLP_STATE,int)
0x18006674e  mov     ebx, eax
0x180066750  test    eax, eax
0x180066752  jns     short loc_180066791
0x180066754  mov     rcx, [rdi+60h]
0x180066758  test    rcx, rcx
0x18006675b  jz      short loc_180066791
0x18006675d  mov     dword ptr [rsp+78h+var_50], eax
0x180066761  mov     dword ptr [rsp+78h+dwFlags], 80h
0x180066769  lea     r9, aCdlptransporth_5; "CDlpTransportHttp::Initialize"
0x180066770  mov     edx, 4
0x180066775  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006677c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180066781  mov     ecx, eax
0x180066783  test    eax, eax
0x180066785  jns     short loc_18006678C
0x180066787  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006678c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180066791  mov     ecx, ebx
0x180066793  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180066798  mov     eax, ebx
0x18006679a  add     rsp, 58h
0x18006679e  pop     r15
0x1800667a0  pop     r14
0x1800667a2  pop     rdi
0x1800667a3  pop     rbx
0x1800667a4  retn
```
