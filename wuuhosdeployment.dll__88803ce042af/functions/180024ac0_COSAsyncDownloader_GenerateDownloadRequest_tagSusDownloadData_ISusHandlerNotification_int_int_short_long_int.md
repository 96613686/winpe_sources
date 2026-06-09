# COSAsyncDownloader::GenerateDownloadRequest(tagSusDownloadData *,ISusHandlerNotification *,int *,int *,short *,long *,int *)

- ea: `0x180024ac0`
- end: `0x180024f73`
- name: `?GenerateDownloadRequest@COSAsyncDownloader@@UEAAJPEAUtagSusDownloadData@@PEAUISusHandlerNotification@@PEAH2PEAFPEAJ2@Z`
- size: `1203`
- prototype: `__int64 __fastcall(COSAsyncDownloader *this, struct tagSusDownloadData *, struct ISusHandlerNotification *, int *, int *, __int16 *, int *, int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000c0b4`
- `0x18001f92c`
- `0x180020fe8`
- `0x1800216c8`
- `0x180024ac0`
- `0x180025da0`
- `0x180025f98`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024d2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024db5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024db5`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180024da6`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180024da6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180024c88`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180024c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024d07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024d07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024e06`
- `OLEAUT32!__imp_SysStringLen` at `0x180024b3b`
- `OLEAUT32!__imp_SysStringLen` at `0x180024b3b`

## string_xrefs

- `0x180024dd3`: `UUP GDR: Completed`
- `0x180024cb8`: `UUP GDR: Fail to create the thread.`

## pseudocode

```c
__int64 __fastcall COSAsyncDownloader::GenerateDownloadRequest(
        COSAsyncDownloader *this,
        struct tagSusDownloadData *a2,
        struct ISusHandlerNotification *a3,
        int *a4,
        int *a5,
        __int16 *a6,
        int *a7,
        int *a8)
{
  __int64 v12; // rdx
  signed int Downloader; // ebx
  int *v14; // rax
  bool v15; // si
  __int64 v16; // rdx
  COSDownloader *v17; // rcx
  HANDLE Thread; // rbx
  __int64 v19; // r9
  signed int LastError; // eax
  _QWORD *v21; // r14
  void *v22; // rcx
  bool IsGDRRunning; // al
  DWORD v24; // eax
  signed int v25; // eax
  _QWORD *v26; // r14
  void *v27; // rcx
  int v28; // eax
  struct ISusFileRequestList *v29; // rdx
  __int64 v30; // rcx
  int v31; // eax
  bool v32; // bl
  __int64 v33; // rcx
  int v34; // eax
  int dwCreationFlags; // [rsp+20h] [rbp-71h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-71h]
  _QWORD v38[3]; // [rsp+40h] [rbp-51h] BYREF
  char v39; // [rsp+58h] [rbp-39h]
  int *v40; // [rsp+60h] [rbp-31h] BYREF
  char v41; // [rsp+68h] [rbp-29h] BYREF
  LPVOID lpParameter; // [rsp+70h] [rbp-21h] BYREF
  DWORD ExitCode; // [rsp+78h] [rbp-19h] BYREF
  int v44; // [rsp+7Ch] [rbp-15h] BYREF
  int v45; // [rsp+80h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+47h]

  v40 = a8;
  v41 = 0;
  lpParameter = 0;
  if ( !a2 )
  {
    v12 = 117;
LABEL_21:
    Downloader = -2147467261;
    goto LABEL_22;
  }
  if ( !*((_QWORD *)a2 + 3) )
  {
    v12 = 118;
    goto LABEL_21;
  }
  if ( !*((_QWORD *)a2 + 4) )
  {
    v12 = 119;
    goto LABEL_21;
  }
  if ( !SysStringLen(*((BSTR *)a2 + 2)) )
  {
    Downloader = -2147024809;
    v12 = 120;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
      (const char *)(unsigned int)Downloader,
      dwCreationFlags);
    goto LABEL_76;
  }
  if ( !a3 )
  {
    v12 = 121;
    goto LABEL_21;
  }
  if ( !a4 )
  {
    v12 = 122;
    goto LABEL_21;
  }
  if ( !a5 )
  {
    v12 = 123;
    goto LABEL_21;
  }
  if ( !a6 )
  {
    v12 = 124;
    goto LABEL_21;
  }
  if ( !a7 )
  {
    v12 = 125;
    goto LABEL_21;
  }
  v14 = v40;
  if ( !v40 )
  {
    v12 = 126;
    goto LABEL_21;
  }
  *a4 = 0;
  *a5 = 0;
  *a6 = 105;
  *a7 = 0;
  *v14 = 0;
  v38[0] = &lpParameter;
  v38[1] = &v41;
  v38[2] = &v40;
  v15 = 1;
  v39 = 1;
  if ( lpParameter )
  {
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)lpParameter + 16LL))(lpParameter, 0);
    lpParameter = 0;
  }
  Downloader = COSAsyncDownloader::GetOrCreateDownloader(
                 this,
                 (const struct tagDSGlobalUpdateId *)(*((_QWORD *)a2 + 4) + 4LL),
                 *((const wchar_t **)a2 + 21),
                 1,
                 (struct COSDownloader **)&lpParameter);
  if ( Downloader < 0 )
  {
    v16 = 152;
LABEL_30:
    v19 = (unsigned int)Downloader;
LABEL_61:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
      (const char *)v19,
      dwCreationFlagsa);
    goto LABEL_75;
  }
  v17 = (COSDownloader *)lpParameter;
  Thread = (HANDLE)*((_QWORD *)lpParameter + 51);
  if ( Thread == (HANDLE)-1LL )
  {
    Downloader = COSDownloader::SetDownloadData((COSDownloader *)lpParameter, a2, a3);
    if ( Downloader < 0 )
    {
      v16 = 158;
      goto LABEL_30;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpParameter + 8LL))(lpParameter);
    Thread = CreateThread(0, 0, COSDownloader::ThreadWorker_GenerateDownloadRequestAsync, lpParameter, 0, 0);
    if ( !Thread )
    {
      v41 = 1;
      LastError = GetLastError();
      Downloader = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        Downloader = LastError;
      if ( Downloader >= 0 )
        Downloader = -2147418113;
      dwCreationFlagsa = Downloader;
      WUTrace(0, 0, 4096, 1);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpParameter + 16LL))(lpParameter);
      v19 = (unsigned int)Downloader;
      v16 = 178;
      goto LABEL_61;
    }
    v21 = lpParameter;
    v22 = (void *)*((_QWORD *)lpParameter + 51);
    if ( v22 )
      CloseHandle(v22);
    v21[51] = Thread;
    v17 = (COSDownloader *)lpParameter;
  }
  IsGDRRunning = COSDownloader::IsGDRRunning(v17);
  v24 = WaitForSingleObject(Thread, !IsGDRRunning ? 0x3E8 : 0);
  if ( !v24 )
  {
    ExitCode = 0;
    if ( GetExitCodeThread(Thread, &ExitCode) )
    {
      Downloader = ExitCode;
    }
    else
    {
      v25 = GetLastError();
      Downloader = (unsigned __int16)v25 | 0x80070000;
      if ( v25 <= 0 )
        Downloader = v25;
      if ( Downloader >= 0 )
        Downloader = -2147418113;
    }
    dwCreationFlagsa = Downloader;
    WUTrace(0, 0, 4096, 4);
    v26 = lpParameter;
    v27 = (void *)*((_QWORD *)lpParameter + 51);
    if ( v27 )
      CloseHandle(v27);
    v26[51] = -1;
    v41 = 1;
    if ( Downloader < 0 )
    {
      if ( ((Downloader + 2145124344) & 0xFFFFDFFF) != 0 )
      {
        v19 = (unsigned int)Downloader;
        v16 = 213;
        goto LABEL_61;
      }
      goto LABEL_75;
    }
    v28 = COSDownloader::MoveDownloadRequest((COSDownloader *)lpParameter, *((struct ISusFileRequestList **)a2 + 3), 0);
    Downloader = v28;
    if ( v28 < 0 )
    {
      v16 = 227;
LABEL_60:
      v19 = (unsigned int)v28;
      goto LABEL_61;
    }
    v29 = (struct ISusFileRequestList *)*((_QWORD *)a2 + 23);
    if ( v29 )
    {
      v28 = COSDownloader::MoveDownloadRequest((COSDownloader *)lpParameter, v29, 1);
      Downloader = v28;
      if ( v28 < 0 )
      {
        v16 = 232;
        goto LABEL_60;
      }
    }
    v44 = 0;
    v30 = *((_QWORD *)a2 + 3);
    if ( v30 )
    {
      v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 56LL))(v30, &v44);
      if ( v31 >= 0 )
      {
        v32 = v44 == 0;
        goto LABEL_66;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xEE,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
        (const char *)(unsigned int)v31,
        dwCreationFlagsa);
    }
    v32 = 1;
LABEL_66:
    v45 = 0;
    v33 = *((_QWORD *)a2 + 23);
    if ( v33 )
    {
      v34 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 56LL))(v33, &v45);
      if ( v34 >= 0 )
        v15 = v45 == 0;
      else
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF5,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
          (const char *)(unsigned int)v34,
          dwCreationFlagsa);
    }
    if ( v32 && v15 )
      *((_BYTE *)lpParameter + 18) = 0;
    Downloader = 0;
    goto LABEL_75;
  }
  if ( v24 != 258 )
  {
    dwCreationFlagsa = 0;
    WUTrace(0, 0, 4096, 4);
    v41 = 1;
    Downloader = -2145112065;
    v19 = 2149855231LL;
    v16 = 224;
    goto LABEL_61;
  }
  WUTrace(0, 0, 4096, 4);
  Downloader = -2145124343;
LABEL_75:
  wil::details::lambda_call__lambda_e2aadd6bbbb0f48316da0cbdc3428db8___::_lambda_call__lambda_e2aadd6bbbb0f48316da0cbdc3428db8___(v38);
LABEL_76:
  if ( lpParameter )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpParameter + 16LL))(lpParameter);
  return (unsigned int)Downloader;
}

```

## disassembly

```asm
0x180024ac0  push    rbp
0x180024ac2  push    rbx
0x180024ac3  push    rsi
0x180024ac4  push    rdi
0x180024ac5  push    r12
0x180024ac7  push    r13
0x180024ac9  push    r14
0x180024acb  push    r15
0x180024acd  lea     rbp, [rsp-7]
0x180024ad2  sub     rsp, 98h
0x180024ad9  mov     rax, cs:__security_cookie
0x180024ae0  xor     rax, rsp
0x180024ae3  mov     [rbp+3Fh+var_48], rax
0x180024ae7  mov     rbx, r9
0x180024aea  mov     r12, r8
0x180024aed  mov     rdi, rdx
0x180024af0  mov     r13, rcx
0x180024af3  mov     rsi, [rbp+3Fh+arg_20]
0x180024af7  mov     r14, [rbp+3Fh+arg_28]
0x180024afb  mov     r15, [rbp+3Fh+arg_30]
0x180024aff  mov     rax, [rbp+3Fh+arg_38]
0x180024b06  mov     [rbp+3Fh+var_70], rax
0x180024b0a  xor     eax, eax
0x180024b0c  mov     [rbp+3Fh+var_68], al
0x180024b0f  mov     [rbp+3Fh+lpParameter], rax
0x180024b13  test    rdx, rdx
0x180024b16  jnz     short loc_180024B1D
0x180024b18  lea     edx, [rdi+75h]
0x180024b1b  jmp     short loc_180024B93
0x180024b1d  cmp     [rdx+18h], rax
0x180024b21  jnz     short loc_180024B2A
0x180024b23  mov     edx, 76h ; 'v'
0x180024b28  jmp     short loc_180024B93
0x180024b2a  cmp     [rdx+20h], rax
0x180024b2e  jnz     short loc_180024B37
0x180024b30  mov     edx, 77h ; 'w'
0x180024b35  jmp     short loc_180024B93
0x180024b37  mov     rcx, [rdx+10h]; pbstr
0x180024b3b  call    cs:__imp_SysStringLen
0x180024b41  xor     edx, edx
0x180024b43  test    eax, eax
0x180024b45  jnz     short loc_180024B51
0x180024b47  mov     ebx, 80070057h
0x180024b4c  lea     edx, [rax+78h]
0x180024b4f  jmp     short loc_180024B98
0x180024b51  test    r12, r12
0x180024b54  jnz     short loc_180024B5D
0x180024b56  lea     edx, [r12+79h]
0x180024b5b  jmp     short loc_180024B93
0x180024b5d  test    rbx, rbx
0x180024b60  jnz     short loc_180024B67
0x180024b62  lea     edx, [rbx+7Ah]
0x180024b65  jmp     short loc_180024B93
0x180024b67  test    rsi, rsi
0x180024b6a  jnz     short loc_180024B71
0x180024b6c  lea     edx, [rsi+7Bh]
0x180024b6f  jmp     short loc_180024B93
0x180024b71  test    r14, r14
0x180024b74  jnz     short loc_180024B7C
0x180024b76  lea     edx, [r14+7Ch]
0x180024b7a  jmp     short loc_180024B93
0x180024b7c  test    r15, r15
0x180024b7f  jnz     short loc_180024B87
0x180024b81  lea     edx, [r15+7Dh]
0x180024b85  jmp     short loc_180024B93
0x180024b87  mov     rax, [rbp+3Fh+var_70]
0x180024b8b  test    rax, rax
0x180024b8e  jnz     short loc_180024BB0
0x180024b90  lea     edx, [rax+7Eh]; void *
0x180024b93  mov     ebx, 80004003h
0x180024b98  mov     rcx, [rbp+47h]; this
0x180024b9c  mov     r9d, ebx; char *
0x180024b9f  lea     r8, aCW1SSrcClientE_17; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180024ba6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024bab  jmp     loc_180024F3B
0x180024bb0  mov     [rbx], edx
0x180024bb2  mov     [rsi], edx
0x180024bb4  mov     word ptr [r14], 69h ; 'i'
0x180024bba  mov     [r15], edx
0x180024bbd  xor     r15d, r15d
0x180024bc0  mov     [rax], r15d
0x180024bc3  lea     rax, [rbp+3Fh+lpParameter]
0x180024bc7  mov     [rbp+3Fh+var_90], rax
0x180024bcb  lea     rax, [rbp+3Fh+var_68]
0x180024bcf  mov     [rbp+3Fh+var_88], rax
0x180024bd3  lea     rax, [rbp+3Fh+var_70]
0x180024bd7  mov     [rbp+3Fh+var_80], rax
0x180024bdb  lea     esi, [r15+1]
0x180024bdf  mov     [rbp+3Fh+var_78], sil
0x180024be3  mov     rcx, [rbp+3Fh+lpParameter]
0x180024be7  test    rcx, rcx
0x180024bea  jz      short loc_180024BFC
0x180024bec  mov     rax, [rcx]
0x180024bef  mov     rax, [rax+10h]
0x180024bf3  call    _guard_dispatch_icall
0x180024bf8  mov     [rbp+3Fh+lpParameter], r15
0x180024bfc  mov     rdx, [rdi+20h]
0x180024c00  add     rdx, 4; struct tagDSGlobalUpdateId *
0x180024c04  lea     rax, [rbp+3Fh+lpParameter]
0x180024c08  mov     qword ptr [rsp+0D0h+dwCreationFlags], rax; struct COSDownloader **
0x180024c0d  mov     r9b, sil; bool
0x180024c10  mov     r8, [rdi+0A8h]; wchar_t *
0x180024c17  mov     rcx, r13; this
0x180024c1a  call    ?GetOrCreateDownloader@COSAsyncDownloader@@AEAAJAEBUtagDSGlobalUpdateId@@PEB_W_NPEAPEAVCOSDownloader@@@Z; COSAsyncDownloader::GetOrCreateDownloader(tagDSGlobalUpdateId const &,wchar_t const *,bool,COSDownloader * *)
0x180024c1f  mov     ebx, eax
0x180024c21  test    eax, eax
0x180024c23  jns     short loc_180024C2C
0x180024c25  mov     edx, 98h
0x180024c2a  jmp     short loc_180024C57
0x180024c2c  mov     rcx, [rbp+3Fh+lpParameter]; this
0x180024c30  mov     rbx, [rcx+198h]
0x180024c37  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180024c3b  jnz     loc_180024D18
0x180024c41  mov     r8, r12; struct ISusHandlerNotification *
0x180024c44  mov     rdx, rdi; struct tagSusDownloadData *
0x180024c47  call    ?SetDownloadData@COSDownloader@@QEAAJPEAUtagSusDownloadData@@PEAUISusHandlerNotification@@@Z; COSDownloader::SetDownloadData(tagSusDownloadData *,ISusHandlerNotification *)
0x180024c4c  mov     ebx, eax
0x180024c4e  test    eax, eax
0x180024c50  jns     short loc_180024C5F
0x180024c52  mov     edx, 9Eh
0x180024c57  mov     r9d, ebx
0x180024c5a  jmp     loc_180024E7D
0x180024c5f  mov     rcx, [rbp+3Fh+lpParameter]
0x180024c63  mov     rax, [rcx]
0x180024c66  mov     rax, [rax+8]
0x180024c6a  call    _guard_dispatch_icall
0x180024c6f  mov     [rsp+0D0h+lpThreadId], r15; lpThreadId
0x180024c74  mov     [rsp+0D0h+dwCreationFlags], r15d; dwCreationFlags
0x180024c79  mov     r9, [rbp+3Fh+lpParameter]; lpParameter
0x180024c7d  lea     r8, ?ThreadWorker_GenerateDownloadRequestAsync@COSDownloader@@SAKPEAX@Z; lpStartAddress
0x180024c84  xor     edx, edx; dwStackSize
0x180024c86  xor     ecx, ecx; lpThreadAttributes
0x180024c88  call    cs:__imp_CreateThread
0x180024c8e  mov     rbx, rax
0x180024c91  test    rax, rax
0x180024c94  jnz     short loc_180024CF7
0x180024c96  mov     [rbp+3Fh+var_68], sil
0x180024c9a  call    cs:__imp_GetLastError
0x180024ca0  movzx   ebx, ax
0x180024ca3  or      ebx, 80070000h
0x180024ca9  test    eax, eax
0x180024cab  cmovle  ebx, eax
0x180024cae  mov     eax, 8000FFFFh
0x180024cb3  test    ebx, ebx
0x180024cb5  cmovns  ebx, eax
0x180024cb8  lea     rax, aUupGdrFailToCr; "UUP GDR: Fail to create the thread."
0x180024cbf  mov     [rsp+0D0h+lpThreadId], rax
0x180024cc4  mov     [rsp+0D0h+dwCreationFlags], ebx
0x180024cc8  mov     r9d, esi
0x180024ccb  xor     edx, edx
0x180024ccd  xor     ecx, ecx
0x180024ccf  mov     r8d, 1000h
0x180024cd5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180024cda  mov     rcx, [rbp+3Fh+lpParameter]
0x180024cde  mov     rax, [rcx]
0x180024ce1  mov     rax, [rax+10h]
0x180024ce5  call    _guard_dispatch_icall
0x180024cea  mov     r9d, ebx
0x180024ced  mov     edx, 0B2h
0x180024cf2  jmp     loc_180024E7D
0x180024cf7  mov     r14, [rbp+3Fh+lpParameter]
0x180024cfb  mov     rcx, [r14+198h]; hObject
0x180024d02  test    rcx, rcx
0x180024d05  jz      short loc_180024D0D
0x180024d07  call    cs:__imp_CloseHandle
0x180024d0d  mov     [r14+198h], rbx
0x180024d14  mov     rcx, [rbp+3Fh+lpParameter]; this
0x180024d18  call    ?IsGDRRunning@COSDownloader@@QEAA_NXZ; COSDownloader::IsGDRRunning(void)
0x180024d1d  neg     al
0x180024d1f  sbb     edx, edx
0x180024d21  not     edx
0x180024d23  and     edx, 3E8h; dwMilliseconds
0x180024d29  mov     rcx, rbx; hHandle
0x180024d2c  call    cs:__imp_WaitForSingleObject
0x180024d32  test    eax, eax
0x180024d34  jz      short loc_180024D9B
0x180024d36  xor     edx, edx
0x180024d38  xor     ecx, ecx
0x180024d3a  lea     r9d, [rdx+4]
0x180024d3e  mov     r8d, 1000h
0x180024d44  cmp     eax, 102h
0x180024d49  jz      short loc_180024D7B
0x180024d4b  mov     [rsp+0D0h+var_A0], eax
0x180024d4f  lea     rax, aUupGdrEventFir_0; "UUP GDR: Event Fired: Error %lu"
0x180024d56  mov     [rsp+0D0h+lpThreadId], rax
0x180024d5b  mov     qword ptr [rsp+0D0h+dwCreationFlags], r15
0x180024d60  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180024d65  mov     [rbp+3Fh+var_68], sil
0x180024d69  mov     ebx, 80242FFFh
0x180024d6e  mov     r9d, ebx
0x180024d71  mov     edx, 0E0h
0x180024d76  jmp     loc_180024E7D
0x180024d7b  lea     rax, aUupGdrEventFir; "UUP GDR: Event Fired: TimeOut"
0x180024d82  mov     [rsp+0D0h+lpThreadId], rax
0x180024d87  mov     qword ptr [rsp+0D0h+dwCreationFlags], r15
0x180024d8c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180024d91  mov     ebx, 80240009h
0x180024d96  jmp     loc_180024F31
0x180024d9b  mov     [rbp+3Fh+ExitCode], r15d
0x180024d9f  lea     rdx, [rbp+3Fh+ExitCode]; lpExitCode
0x180024da3  mov     rcx, rbx; hThread
0x180024da6  call    cs:__imp_GetExitCodeThread
0x180024dac  test    eax, eax
0x180024dae  jz      short loc_180024DB5
0x180024db0  mov     ebx, [rbp+3Fh+ExitCode]
0x180024db3  jmp     short loc_180024DD3
0x180024db5  call    cs:__imp_GetLastError
0x180024dbb  movzx   ebx, ax
0x180024dbe  or      ebx, 80070000h
0x180024dc4  test    eax, eax
0x180024dc6  cmovle  ebx, eax
0x180024dc9  mov     eax, 8000FFFFh
0x180024dce  test    ebx, ebx
0x180024dd0  cmovns  ebx, eax
0x180024dd3  lea     rax, aUupGdrComplete; "UUP GDR: Completed"
0x180024dda  mov     [rsp+0D0h+lpThreadId], rax
0x180024ddf  mov     [rsp+0D0h+dwCreationFlags], ebx; int
0x180024de3  xor     edx, edx
0x180024de5  xor     ecx, ecx
0x180024de7  lea     r9d, [rdx+4]
0x180024deb  mov     r8d, 1000h
0x180024df1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180024df6  mov     r14, [rbp+3Fh+lpParameter]
0x180024dfa  mov     rcx, [r14+198h]; hObject
0x180024e01  test    rcx, rcx
0x180024e04  jz      short loc_180024E0C
0x180024e06  call    cs:__imp_CloseHandle
0x180024e0c  mov     qword ptr [r14+198h], 0FFFFFFFFFFFFFFFFh
0x180024e17  mov     [rbp+3Fh+var_68], sil
0x180024e1b  test    ebx, ebx
0x180024e1d  jns     short loc_180024E3A
0x180024e1f  lea     eax, [rbx+7FDBFFF8h]
0x180024e25  test    eax, 0FFFFDFFFh
0x180024e2a  jz      loc_180024F31
0x180024e30  mov     r9d, ebx
0x180024e33  mov     edx, 0D5h
0x180024e38  jmp     short loc_180024E7D
0x180024e3a  xor     r8d, r8d; bool
0x180024e3d  mov     rdx, [rdi+18h]; struct ISusFileRequestList *
0x180024e41  mov     rcx, [rbp+3Fh+lpParameter]; this
0x180024e45  call    ?MoveDownloadRequest@COSDownloader@@QEAAJPEAUISusFileRequestList@@_N@Z; COSDownloader::MoveDownloadRequest(ISusFileRequestList *,bool)
0x180024e4a  mov     ebx, eax
0x180024e4c  test    eax, eax
0x180024e4e  jns     short loc_180024E57
0x180024e50  mov     edx, 0E3h
0x180024e55  jmp     short loc_180024E7A
0x180024e57  mov     rdx, [rdi+0B8h]; struct ISusFileRequestList *
0x180024e5e  test    rdx, rdx
0x180024e61  jz      short loc_180024E92
0x180024e63  mov     r8b, sil; bool
0x180024e66  mov     rcx, [rbp+3Fh+lpParameter]; this
0x180024e6a  call    ?MoveDownloadRequest@COSDownloader@@QEAAJPEAUISusFileRequestList@@_N@Z; COSDownloader::MoveDownloadRequest(ISusFileRequestList *,bool)
0x180024e6f  mov     ebx, eax
0x180024e71  test    eax, eax
0x180024e73  jns     short loc_180024E92
0x180024e75  mov     edx, 0E8h; void *
0x180024e7a  mov     r9d, eax; char *
0x180024e7d  lea     r8, aCW1SSrcClientE_17; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180024e84  mov     rcx, [rbp+47h]; this
0x180024e88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e8d  jmp     loc_180024F31
0x180024e92  mov     [rbp+3Fh+var_54], r15d
0x180024e96  mov     rcx, [rdi+18h]
0x180024e9a  test    rcx, rcx
0x180024e9d  jz      short loc_180024ECB
0x180024e9f  mov     rax, [rcx]
0x180024ea2  lea     rdx, [rbp+3Fh+var_54]
0x180024ea6  mov     rax, [rax+38h]
0x180024eaa  call    _guard_dispatch_icall
0x180024eaf  mov     rcx, [rbp+47h]; this
0x180024eb3  test    eax, eax
0x180024eb5  jns     short loc_180024F0C
0x180024eb7  mov     r9d, eax; char *
0x180024eba  lea     r8, aCW1SSrcClientE_17; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180024ec1  mov     edx, 0EEh; void *
0x180024ec6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024ecb  mov     bl, sil
0x180024ece  mov     [rbp+3Fh+var_50], r15d
0x180024ed2  mov     rcx, [rdi+0B8h]
0x180024ed9  test    rcx, rcx
0x180024edc  jz      short loc_180024F1D
0x180024ede  mov     rax, [rcx]
0x180024ee1  lea     rdx, [rbp+3Fh+var_50]
0x180024ee5  mov     rax, [rax+38h]
0x180024ee9  call    _guard_dispatch_icall
0x180024eee  mov     rcx, [rbp+47h]; this
0x180024ef2  test    eax, eax
0x180024ef4  jns     short loc_180024F15
0x180024ef6  mov     r9d, eax; char *
0x180024ef9  lea     r8, aCW1SSrcClientE_17; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180024f00  mov     edx, 0F5h; void *
0x180024f05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024f0a  jmp     short loc_180024F1D
0x180024f0c  cmp     [rbp+3Fh+var_54], r15d
0x180024f10  setz    bl
0x180024f13  jmp     short loc_180024ECE
0x180024f15  cmp     [rbp+3Fh+var_50], r15d
0x180024f19  setz    sil
0x180024f1d  test    bl, bl
0x180024f1f  jz      short loc_180024F2E
  ... truncated ...
```
