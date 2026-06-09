# TLPCMgr::ProcessRequest(PROXY_MSG *,_REMOTE_PORT_VIEW *)

- ea: `0x140011bb0`
- end: `0x140012005`
- name: `?ProcessRequest@TLPCMgr@@QEBAKPEAUPROXY_MSG@@PEAU_REMOTE_PORT_VIEW@@@Z`
- size: `1109`
- prototype: `unsigned int __fastcall(TLPCMgr *__hidden this, struct PROXY_MSG *, struct _REMOTE_PORT_VIEW *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x140012390`

## callees

- `0x140001b50`
- `0x140001b90`
- `0x140001ee0`
- `0x140002174`
- `0x1400028b8`
- `0x140006388`
- `0x1400085d8`
- `0x1400086e0`
- `0x140010d98`
- `0x140010e70`
- `0x140011268`
- `0x140011bb0`
- `0x140012254`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140011e11`
- `KERNEL32!GetCurrentThreadId` at `0x140011e46`
- `KERNEL32!GetCurrentThreadId` at `0x140011e11`
- `KERNEL32!GetCurrentThreadId` at `0x140011e46`
- `KERNEL32!TlsSetValue` at `0x140011d66`
- `KERNEL32!TlsSetValue` at `0x140011fa3`
- `KERNEL32!TlsSetValue` at `0x140011d66`
- `KERNEL32!TlsSetValue` at `0x140011fa3`
- `USER32!GetGUIThreadInfo` at `0x140011df9`
- `USER32!GetGUIThreadInfo` at `0x140011df9`
- `USER32!AttachThreadInput` at `0x140011e22`
- `USER32!AttachThreadInput` at `0x140011e54`
- `USER32!AttachThreadInput` at `0x140011e22`
- `USER32!AttachThreadInput` at `0x140011e54`
- `USER32!IsWindow` at `0x140011e07`
- `USER32!IsWindow` at `0x140011e07`

## pseudocode

```c
__int64 __fastcall TLPCMgr::ProcessRequest(TLPCMgr *this, struct PROXY_MSG *a2, struct _REMOTE_PORT_VIEW *a3)
{
  DWORD v6; // r12d
  unsigned __int16 *v7; // rdx
  unsigned __int64 v8; // rax
  rsize_t v9; // r14
  PVOID ViewBase; // rcx
  rsize_t v11; // r8
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // r9
  unsigned int v14; // ebx
  unsigned int *v15; // rsi
  int v16; // eax
  unsigned __int64 v17; // rbx
  __int64 *v18; // rax
  __int64 *v19; // r15
  __int64 v20; // r8
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  bool v24; // zf
  unsigned int v25; // eax
  unsigned int v26; // eax
  DWORD CurrentThreadId; // eax
  DWORD v28; // eax
  void (__fastcall **v29)(_QWORD, __int64); // r12
  void (__fastcall ***v30)(_QWORD, __int64); // rax
  void (__fastcall ***v31)(_QWORD, __int64); // r14
  void (__fastcall **v32)(_QWORD, __int64); // rcx
  __int64 appended; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdi
  __int64 v39; // [rsp+30h] [rbp-59h] BYREF
  rsize_t SourceSize; // [rsp+38h] [rbp-51h]
  __int64 v41; // [rsp+40h] [rbp-49h] BYREF
  void *Destination; // [rsp+48h] [rbp-41h]
  tagGUITHREADINFO pgui; // [rsp+50h] [rbp-39h] BYREF

  SplWow64Telemetry::WriteDbgTraceInfo("TLPCMgr::ProcessRequest", L"Processing request.");
  v6 = 0;
  if ( !a2 )
  {
    v7 = L"Invalid parameter.  Error %d.";
LABEL_58:
    v14 = 87;
    SplWow64Telemetry::WriteDbgTraceError("TLPCMgr::ProcessRequest", v7, 87);
    return v14;
  }
  if ( *(_WORD *)a2 != 32 || !*((_QWORD *)this + 9) )
  {
    v7 = L"Failed to process the client request.  Error %d.";
    goto LABEL_58;
  }
  v8 = *((_QWORD *)a2 + 6);
  v9 = *((unsigned int *)a2 + 10);
  if ( v9 + v8 < v8
    || (ViewBase = a3->ViewBase, v8 < (unsigned __int64)ViewBase)
    || (v11 = (rsize_t)ViewBase + a3->ViewSize, v9 + v8 > v11)
    || (v12 = *((_QWORD *)a2 + 8), v13 = v12 + *((unsigned int *)a2 + 14), v13 < v12)
    || v12 < (unsigned __int64)ViewBase
    || v13 > v11 )
  {
    v7 = L"Invalid buffer bound.  Error %d.";
    goto LABEL_58;
  }
  if ( (unsigned int)v9 >= 0x10 )
  {
    v15 = (unsigned int *)operator new[](*((unsigned int *)a2 + 10), (const struct std::nothrow_t *)&std::nothrow);
    if ( !v15 )
    {
      v14 = 87;
      SplWow64Telemetry::WriteDbgTraceError(
        "TLPCMgr::ProcessRequest",
        L"Failed to validate and clone the input message, size %d.  Error %d.",
        (unsigned int)v9,
        87);
      return v14;
    }
    v16 = *((_DWORD *)a2 + 14);
    LODWORD(SourceSize) = v16;
    if ( v16 == -1 )
    {
      operator delete(v15);
      v7 = L"Failed to allocate output buffer.  Error %d.";
      goto LABEL_58;
    }
    v17 = (unsigned int)(v16 + 1);
    v18 = (__int64 *)operator new[](v17, (const struct std::nothrow_t *)&std::nothrow);
    v19 = v18;
    if ( !v18 )
    {
      operator delete(v15);
      v14 = 8;
      SplWow64Telemetry::WriteDbgTraceError(
        "TLPCMgr::ProcessRequest",
        L"Failed to allocate output buffer.  Error %d.",
        8);
      return v14;
    }
    memset_0(v18, 0, v17);
    memcpy_s(v15, v9, *((const void *const *)a2 + 6), v9);
    v20 = v15[1];
    Destination = (void *)*((_QWORD *)a2 + 8);
    SplWow64Telemetry::WriteDbgTraceInfo("TLPCMgr::ProcessRequest", L"Handling thunk %d.", v20);
    TlsSetValue(g_GlobalTlsIndex, (LPVOID)*((unsigned int *)a2 + 2));
    if ( *((__int16 *)a2 + 2) < 0 )
      goto LABEL_29;
    v21 = v15[1];
    if ( v21 > 0x70 )
    {
      v26 = v21 - 113;
      if ( !v26 )
        goto LABEL_29;
      v25 = v26 - 1;
      v24 = v25 == 0;
    }
    else
    {
      if ( v21 == 112 )
        goto LABEL_29;
      v22 = v21 - 106;
      if ( !v22 )
        goto LABEL_29;
      v23 = v22 - 1;
      if ( !v23 )
        goto LABEL_29;
      v25 = v23 - 2;
      v24 = v25 == 0;
    }
    if ( !v24 && v25 - 1 >= 2 )
    {
      v14 = 87;
      SplWow64Telemetry::WriteDbgTraceError(
        "TLPCMgr::ProcessRequest",
        L"Unauthorized request received for Kernel Mode API.  Error %d.",
        87);
LABEL_54:
      operator delete(v15);
      memcpy_s(Destination, (unsigned int)SourceSize, v19, (unsigned int)SourceSize);
      operator delete(v19);
      TlsSetValue(g_GlobalTlsIndex, 0);
      return v14;
    }
LABEL_29:
    v24 = v15[1] == 109;
    v14 = 0;
    LODWORD(v39) = 0;
    if ( v24 )
    {
      if ( *(_BYTE *)v15 )
      {
        memset_0(&pgui, 0, sizeof(pgui));
        pgui.cbSize = 72;
        v6 = *((_DWORD *)a2 + 4);
        if ( v6 )
        {
          if ( GetGUIThreadInfo(v6, &pgui) && IsWindow(pgui.hwndActive) )
          {
            CurrentThreadId = GetCurrentThreadId();
            LODWORD(v39) = AttachThreadInput(CurrentThreadId, v6, 1);
          }
        }
      }
    }
    (*((void (__fastcall **)(unsigned int *, _QWORD, __int64 *, _QWORD))this + 9))(
      v15,
      (unsigned int)v9,
      v19,
      (unsigned int)SourceSize);
    if ( (_DWORD)v39 )
    {
      v28 = GetCurrentThreadId();
      AttachThreadInput(v28, v6, 0);
    }
    if ( v15[1] == 109 || v15[1] == 110 || v15[1] == 116 )
      memcpy_s(*((void *const *)a2 + 6), v9, v15, v9);
    if ( v15[1] == 106 )
    {
      if ( *((_QWORD *)this + 10) )
      {
        v29 = (void (__fastcall **)(_QWORD, __int64))v19[1];
        v30 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x28u);
        v31 = v30;
        if ( v30 )
        {
          v32 = (void (__fastcall **)(_QWORD, __int64))*((_QWORD *)a2 + 1);
          *((_DWORD *)v30 + 2) = 0;
          *v30 = (void (__fastcall **)(_QWORD, __int64))&TLPCMgr::TPrinterHandleInfo::`vftable';
          v30[2] = v32;
          *((_DWORD *)v30 + 8) = 1431130180;
          v30[3] = v29;
          v39 = *((_QWORD *)a2 + 1);
          appended = TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(*((_QWORD *)this + 10), &v39);
          if ( appended
            || (v34 = *((_QWORD *)this + 10),
                v39 = *((_QWORD *)a2 + 1),
                (appended = TLstMgr<TLPCMgr::TConnectedClientsInfo,unsigned __int64>::AppendListByElem(v34, &v39)) != 0) )
          {
            TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::AppendListByElem(*(_QWORD *)(*(_QWORD *)appended + 40LL), v31);
          }
          else
          {
            (**v31)(v31, 1);
          }
        }
      }
      v19[1] = 0;
    }
    else if ( v15[1] == 107 )
    {
      v35 = *((_QWORD *)this + 10);
      v39 = *v19;
      v41 = *((_QWORD *)a2 + 1);
      v36 = TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(v35, &v41);
      v37 = v36;
      if ( v36 && TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(*(_QWORD *)(*(_QWORD *)v36 + 40LL), &v39) )
        TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::RmvElemFromList(*(_QWORD *)(*(_QWORD *)v37 + 40LL), &v39);
      *v19 = 0;
    }
    goto LABEL_54;
  }
  v14 = 87;
  SplWow64Telemetry::WriteDbgTraceError(
    "TLPCMgr::ProcessRequest",
    L"Input buffer too small for UMPD header.  Size %u, required %u.  Error %d.",
    (unsigned int)v9);
  return v14;
}

```

## disassembly

```asm
0x140011bb0  mov     [rsp-8+arg_10], rbx
0x140011bb5  push    rbp
0x140011bb6  push    rsi
0x140011bb7  push    rdi
0x140011bb8  push    r12
0x140011bba  push    r13
0x140011bbc  push    r14
0x140011bbe  push    r15
0x140011bc0  lea     rbp, [rsp-27h]
0x140011bc5  sub     rsp, 0B0h
0x140011bcc  mov     rax, cs:__security_cookie
0x140011bd3  xor     rax, rsp
0x140011bd6  mov     [rbp+57h+var_40], rax
0x140011bda  mov     rdi, rdx
0x140011bdd  lea     r15, aTlpcmgrProcess_1; "TLPCMgr::ProcessRequest"
0x140011be4  mov     r13, rcx
0x140011be7  lea     rdx, aProcessingRequ; "Processing request."
0x140011bee  mov     rcx, r15; char *
0x140011bf1  mov     rbx, r8
0x140011bf4  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140011bf9  xor     r12d, r12d
0x140011bfc  test    rdi, rdi
0x140011bff  jnz     short loc_140011C0D
0x140011c01  lea     rdx, aInvalidParamet; "Invalid parameter.  Error %d."
0x140011c08  jmp     loc_140011FCC
0x140011c0d  cmp     word ptr [rdi], 20h ; ' '
0x140011c11  jnz     loc_140011FC5
0x140011c17  cmp     [r13+48h], r12
0x140011c1b  jz      loc_140011FC5
0x140011c21  mov     rax, [rdi+30h]
0x140011c25  mov     r14d, [rdi+28h]
0x140011c29  lea     rdx, [r14+rax]
0x140011c2d  cmp     rdx, rax
0x140011c30  jb      loc_140011FBC
0x140011c36  mov     rcx, [rbx+10h]
0x140011c3a  cmp     rax, rcx
0x140011c3d  jb      loc_140011FBC
0x140011c43  mov     r8, [rbx+8]
0x140011c47  add     r8, rcx
0x140011c4a  cmp     rdx, r8
0x140011c4d  ja      loc_140011FBC
0x140011c53  mov     rdx, [rdi+40h]
0x140011c57  mov     r9d, [rdi+38h]
0x140011c5b  add     r9, rdx
0x140011c5e  cmp     r9, rdx
0x140011c61  jb      loc_140011FBC
0x140011c67  cmp     rdx, rcx
0x140011c6a  jb      loc_140011FBC
0x140011c70  cmp     r9, r8
0x140011c73  ja      loc_140011FBC
0x140011c79  mov     r9d, 10h
0x140011c7f  cmp     r14d, r9d
0x140011c82  jnb     short loc_140011CA3
0x140011c84  lea     ebx, [r9+47h]
0x140011c88  mov     r8d, r14d
0x140011c8b  lea     rdx, aInputBufferToo; "Input buffer too small for UMPD header."...
0x140011c92  mov     [rsp+0E0h+var_C0], ebx
0x140011c96  mov     rcx, r15; char *
0x140011c99  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140011c9e  jmp     loc_140011FDC
0x140011ca3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011caa  mov     rcx, r14; unsigned __int64
0x140011cad  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140011cb2  mov     rsi, rax
0x140011cb5  test    rax, rax
0x140011cb8  jnz     short loc_140011CD7
0x140011cba  lea     ebx, [rax+57h]
0x140011cbd  mov     r8d, r14d
0x140011cc0  mov     r9d, ebx
0x140011cc3  lea     rdx, aFailedToValida; "Failed to validate and clone the input "...
0x140011cca  mov     rcx, r15; char *
0x140011ccd  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140011cd2  jmp     loc_140011FDC
0x140011cd7  mov     eax, [rdi+38h]
0x140011cda  mov     dword ptr [rbp+57h+SourceSize], eax
0x140011cdd  cmp     eax, 0FFFFFFFFh
0x140011ce0  jnb     loc_140011FAB
0x140011ce6  inc     eax
0x140011ce8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011cef  mov     ecx, eax; unsigned __int64
0x140011cf1  mov     ebx, eax
0x140011cf3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140011cf8  mov     r15, rax
0x140011cfb  test    rax, rax
0x140011cfe  jnz     short loc_140011D1F
0x140011d00  mov     rcx, rsi; Block
0x140011d03  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011d08  lea     rdx, aFailedToAlloca; "Failed to allocate output buffer.  Erro"...
0x140011d0f  lea     rcx, aTlpcmgrProcess_1; "TLPCMgr::ProcessRequest"
0x140011d16  lea     ebx, [r15+8]
0x140011d1a  jmp     loc_140011FD4
0x140011d1f  mov     r8, rbx; Size
0x140011d22  xor     edx, edx; Val
0x140011d24  mov     rcx, r15; void *
0x140011d27  call    memset_0
0x140011d2c  mov     r8, [rdi+30h]; Source
0x140011d30  mov     r9, r14; SourceSize
0x140011d33  mov     rdx, r14; DestinationSize
0x140011d36  mov     rcx, rsi; Destination
0x140011d39  call    memcpy_s
0x140011d3e  mov     rax, [rdi+40h]
0x140011d42  lea     rdx, aHandlingThunkD; "Handling thunk %d."
0x140011d49  mov     r8d, [rsi+4]
0x140011d4d  lea     rcx, aTlpcmgrProcess_1; "TLPCMgr::ProcessRequest"
0x140011d54  mov     [rbp+57h+Destination], rax
0x140011d58  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140011d5d  mov     edx, [rdi+8]; lpTlsValue
0x140011d60  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x140011d66  call    cs:__imp_TlsSetValue
0x140011d6c  cmp     [rdi+4], r12w
0x140011d71  jl      short loc_140011DC0
0x140011d73  mov     eax, [rsi+4]
0x140011d76  cmp     eax, 70h ; 'p'
0x140011d79  ja      short loc_140011D8C
0x140011d7b  jz      short loc_140011DC0
0x140011d7d  sub     eax, 6Ah ; 'j'
0x140011d80  jz      short loc_140011DC0
0x140011d82  sub     eax, 1
0x140011d85  jz      short loc_140011DC0
0x140011d87  sub     eax, 2
0x140011d8a  jmp     short loc_140011D94
0x140011d8c  sub     eax, 71h ; 'q'
0x140011d8f  jz      short loc_140011DC0
0x140011d91  sub     eax, 1
0x140011d94  jz      short loc_140011DC0
0x140011d96  sub     eax, 1
0x140011d99  jz      short loc_140011DC0
0x140011d9b  cmp     eax, 1
0x140011d9e  jz      short loc_140011DC0
0x140011da0  mov     ebx, 57h ; 'W'
0x140011da5  lea     rdx, aUnauthorizedRe; "Unauthorized request received for Kerne"...
0x140011dac  mov     r8d, ebx
0x140011daf  lea     rcx, aTlpcmgrProcess_1; "TLPCMgr::ProcessRequest"
0x140011db6  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140011dbb  jmp     loc_140011F79
0x140011dc0  cmp     dword ptr [rsi+4], 6Dh ; 'm'
0x140011dc4  mov     ebx, r12d
0x140011dc7  mov     dword ptr [rbp+57h+var_B0], r12d
0x140011dcb  jnz     short loc_140011E2B
0x140011dcd  cmp     [rsi], bl
0x140011dcf  jz      short loc_140011E2B
0x140011dd1  mov     r12d, 48h ; 'H'
0x140011dd7  lea     rcx, [rbp+57h+pgui]; void *
0x140011ddb  mov     r8d, r12d; Size
0x140011dde  xor     edx, edx; Val
0x140011de0  call    memset_0
0x140011de5  mov     [rbp+57h+pgui.cbSize], r12d
0x140011de9  mov     r12d, [rdi+10h]
0x140011ded  test    r12d, r12d
0x140011df0  jz      short loc_140011E2B
0x140011df2  lea     rdx, [rbp+57h+pgui]; pgui
0x140011df6  mov     ecx, r12d; idThread
0x140011df9  call    cs:__imp_GetGUIThreadInfo
0x140011dff  test    eax, eax
0x140011e01  jz      short loc_140011E2B
0x140011e03  mov     rcx, [rbp+57h+pgui.hwndActive]; hWnd
0x140011e07  call    cs:__imp_IsWindow
0x140011e0d  test    eax, eax
0x140011e0f  jz      short loc_140011E2B
0x140011e11  call    cs:__imp_GetCurrentThreadId
0x140011e17  mov     r8d, 1; fAttach
0x140011e1d  mov     edx, r12d; idAttachTo
0x140011e20  mov     ecx, eax; idAttach
0x140011e22  call    cs:__imp_AttachThreadInput
0x140011e28  mov     dword ptr [rbp+57h+var_B0], eax
0x140011e2b  mov     r9d, dword ptr [rbp+57h+SourceSize]
0x140011e2f  mov     r8, r15
0x140011e32  mov     rax, [r13+48h]
0x140011e36  mov     edx, r14d
0x140011e39  mov     rcx, rsi
0x140011e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e41  cmp     dword ptr [rbp+57h+var_B0], ebx
0x140011e44  jz      short loc_140011E5A
0x140011e46  call    cs:__imp_GetCurrentThreadId
0x140011e4c  xor     r8d, r8d; fAttach
0x140011e4f  mov     edx, r12d; idAttachTo
0x140011e52  mov     ecx, eax; idAttach
0x140011e54  call    cs:__imp_AttachThreadInput
0x140011e5a  mov     ecx, [rsi+4]
0x140011e5d  sub     ecx, 6Dh ; 'm'
0x140011e60  jz      short loc_140011E6C
0x140011e62  sub     ecx, 1
0x140011e65  jz      short loc_140011E6C
0x140011e67  cmp     ecx, 6
0x140011e6a  jnz     short loc_140011E7E
0x140011e6c  mov     rcx, [rdi+30h]; Destination
0x140011e70  mov     r9, r14; SourceSize
0x140011e73  mov     r8, rsi; Source
0x140011e76  mov     rdx, r14; DestinationSize
0x140011e79  call    memcpy_s
0x140011e7e  cmp     dword ptr [rsi+4], 6Ah ; 'j'
0x140011e82  jnz     loc_140011F27
0x140011e88  cmp     [r13+50h], rbx
0x140011e8c  jz      loc_140011F21
0x140011e92  mov     r12, [r15+8]
0x140011e96  mov     ecx, 28h ; '('; Size
0x140011e9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140011ea0  mov     r14, rax
0x140011ea3  test    rax, rax
0x140011ea6  jz      short loc_140011F21
0x140011ea8  mov     rcx, [rdi+8]
0x140011eac  lea     rdx, [rbp+57h+var_B0]
0x140011eb0  mov     [rax+8], ebx
0x140011eb3  lea     rax, ??_7TPrinterHandleInfo@TLPCMgr@@6B@; const TLPCMgr::TPrinterHandleInfo::`vftable'
0x140011eba  mov     [r14], rax
0x140011ebd  mov     [r14+10h], rcx
0x140011ec1  mov     dword ptr [r14+20h], 554D5044h
0x140011ec9  mov     [r14+18h], r12
0x140011ecd  mov     rcx, [rdi+8]
0x140011ed1  mov     [rbp+57h+var_B0], rcx
0x140011ed5  mov     rcx, [r13+50h]
0x140011ed9  call    ?ElementInList@?$TLstMgr@VTPrinterHandleInfo@TLPCMgr@@PEAX@@QEBAPEAV?$TLstNd@VTPrinterHandleInfo@TLPCMgr@@PEAX@@AEBQEAX@Z; TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(void * const &)
0x140011ede  test    rax, rax
0x140011ee1  jnz     short loc_140011F12
0x140011ee3  mov     rax, [rdi+8]
0x140011ee7  lea     rdx, [rbp+57h+var_B0]
0x140011eeb  mov     rcx, [r13+50h]
0x140011eef  mov     [rbp+57h+var_B0], rax
0x140011ef3  call    ?AppendListByElem@?$TLstMgr@VTConnectedClientsInfo@TLPCMgr@@_K@@QEAAPEAV?$TLstNd@VTConnectedClientsInfo@TLPCMgr@@_K@@AEB_K@Z; TLstMgr<TLPCMgr::TConnectedClientsInfo,unsigned __int64>::AppendListByElem(unsigned __int64 const &)
0x140011ef8  test    rax, rax
0x140011efb  jnz     short loc_140011F12
0x140011efd  mov     rax, [r14]
0x140011f00  mov     edx, 1
0x140011f05  mov     rcx, r14
0x140011f08  mov     rax, [rax]
0x140011f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011f10  jmp     short loc_140011F21
0x140011f12  mov     rcx, [rax]
0x140011f15  mov     rdx, r14
0x140011f18  mov     rcx, [rcx+28h]
0x140011f1c  call    ?AppendListByElem@?$TLstMgr@VTPrinterHandleInfo@TLPCMgr@@PEAX@@QEAAPEAV?$TLstNd@VTPrinterHandleInfo@TLPCMgr@@PEAX@@PEAVTPrinterHandleInfo@TLPCMgr@@@Z; TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::AppendListByElem(TLPCMgr::TPrinterHandleInfo *)
0x140011f21  mov     [r15+8], rbx
0x140011f25  jmp     short loc_140011F79
0x140011f27  cmp     dword ptr [rsi+4], 6Bh ; 'k'
0x140011f2b  jnz     short loc_140011F79
0x140011f2d  mov     rax, [r15]
0x140011f30  lea     rdx, [rbp+57h+var_A0]
0x140011f34  mov     rcx, [r13+50h]
0x140011f38  mov     [rbp+57h+var_B0], rax
0x140011f3c  mov     rax, [rdi+8]
0x140011f40  mov     [rbp+57h+var_A0], rax
0x140011f44  call    ?ElementInList@?$TLstMgr@VTPrinterHandleInfo@TLPCMgr@@PEAX@@QEBAPEAV?$TLstNd@VTPrinterHandleInfo@TLPCMgr@@PEAX@@AEBQEAX@Z; TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(void * const &)
0x140011f49  mov     rdi, rax
0x140011f4c  test    rax, rax
0x140011f4f  jz      short loc_140011F76
0x140011f51  mov     rcx, [rax]
0x140011f54  lea     rdx, [rbp+57h+var_B0]
0x140011f58  mov     rcx, [rcx+28h]
0x140011f5c  call    ?ElementInList@?$TLstMgr@VTPrinterHandleInfo@TLPCMgr@@PEAX@@QEBAPEAV?$TLstNd@VTPrinterHandleInfo@TLPCMgr@@PEAX@@AEBQEAX@Z; TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(void * const &)
0x140011f61  test    rax, rax
0x140011f64  jz      short loc_140011F76
0x140011f66  mov     rcx, [rdi]
0x140011f69  lea     rdx, [rbp+57h+var_B0]
0x140011f6d  mov     rcx, [rcx+28h]
0x140011f71  call    ?RmvElemFromList@?$TLstMgr@VTPrinterHandleInfo@TLPCMgr@@PEAX@@QEAAJAEBQEAX@Z; TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::RmvElemFromList(void * const &)
0x140011f76  mov     [r15], rbx
0x140011f79  mov     rcx, rsi; Block
0x140011f7c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011f81  mov     edx, dword ptr [rbp+57h+SourceSize]; DestinationSize
0x140011f84  mov     r8, r15; Source
0x140011f87  mov     rcx, [rbp+57h+Destination]; Destination
0x140011f8b  mov     r9d, edx; SourceSize
0x140011f8e  call    memcpy_s
0x140011f93  mov     rcx, r15; Block
0x140011f96  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011f9b  mov     ecx, cs:?g_GlobalTlsIndex@@3VGlobalTlsIndex@@A; dwTlsIndex
0x140011fa1  xor     edx, edx; lpTlsValue
0x140011fa3  call    cs:__imp_TlsSetValue
0x140011fa9  jmp     short loc_140011FDC
0x140011fab  mov     rcx, rsi; Block
0x140011fae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011fb3  lea     rdx, aFailedToAlloca; "Failed to allocate output buffer.  Erro"...
0x140011fba  jmp     short loc_140011FCC
0x140011fbc  lea     rdx, aInvalidBufferB; "Invalid buffer bound.  Error %d."
0x140011fc3  jmp     short loc_140011FCC
0x140011fc5  lea     rdx, aFailedToProces; "Failed to process the client request.  "...
0x140011fcc  mov     ebx, 57h ; 'W'
0x140011fd1  mov     rcx, r15; char *
0x140011fd4  mov     r8d, ebx
0x140011fd7  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140011fdc  mov     eax, ebx
0x140011fde  mov     rcx, [rbp+57h+var_40]
0x140011fe2  xor     rcx, rsp; StackCookie
0x140011fe5  call    __security_check_cookie
0x140011fea  mov     rbx, [rsp+0E0h+arg_10]
0x140011ff2  add     rsp, 0B0h
0x140011ff9  pop     r15
0x140011ffb  pop     r14
0x140011ffd  pop     r13
0x140011fff  pop     r12
0x140012001  pop     rdi
0x140012002  pop     rsi
0x140012003  pop     rbp
0x140012004  retn
```
