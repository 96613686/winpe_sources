# CClientLibrary::ExecuteRpcSession(CClientLibrary::Session *,void *,ulong,void * *,ulong *,ulong)

- ea: `0x180005558`
- end: `0x1800059f0`
- name: `?ExecuteRpcSession@CClientLibrary@@AEAAKPEAUSession@1@PEAXKPEAPEAXPEAKK@Z`
- size: `1176`
- prototype: `unsigned int(CClientLibrary *__hidden this, struct Session *, void *, unsigned int, void **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009d78`

## callees

- `0x1800026c4`
- `0x180005064`
- `0x180005558`
- `0x180006080`
- `0x18000bd5c`
- `0x18000d6d2`
- `0x18000d700`
- `0x18000e010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800057ae`
- `KERNEL32!WaitForSingleObject` at `0x1800057fe`
- `KERNEL32!WaitForSingleObject` at `0x1800057ae`
- `KERNEL32!WaitForSingleObject` at `0x1800057fe`
- `KERNEL32!GetLastError` at `0x1800056d9`
- `KERNEL32!GetLastError` at `0x18000580e`
- `KERNEL32!GetLastError` at `0x180005960`
- `KERNEL32!GetLastError` at `0x1800056d9`
- `KERNEL32!GetLastError` at `0x18000580e`
- `KERNEL32!GetLastError` at `0x180005960`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800056c9`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x1800056c9`
- `ADVAPI32!RevertToSelf` at `0x1800059af`
- `ADVAPI32!RevertToSelf` at `0x1800059af`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000dbf3`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000dbf3`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800057d2`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800057d2`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180005740`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180005740`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180005832`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180005877`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180005832`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180005877`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180005653`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180005653`
- `WdsCommonLib!?Allocate@CMemoryBuffer@@SAPEAV1@K@Z` at `0x1800055d9`
- `WdsCommonLib!?Allocate@CMemoryBuffer@@SAPEAV1@K@Z` at `0x1800055d9`

## pseudocode

```c
__int64 __fastcall CClientLibrary::ExecuteRpcSession(
        CClientLibrary *this,
        struct Session *a2,
        void *a3,
        unsigned int a4,
        void **a5,
        unsigned int *a6,
        DWORD dwMilliseconds)
{
  size_t v7; // rdi
  int v10; // r12d
  struct CMemoryBuffer *v11; // rax
  CClientLibrary *v12; // rcx
  struct CMemoryBuffer *v13; // r14
  __int64 v14; // rdi
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  HANDLE *v19; // r15
  void *v20; // rcx
  DWORD LastError; // eax
  _QWORD *v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rdx
  DWORD v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  size_t v31; // r8
  __int64 v32; // rcx
  unsigned int v34; // [rsp+50h] [rbp-F8h] BYREF
  unsigned int Reply; // [rsp+54h] [rbp-F4h] BYREF
  int v36; // [rsp+58h] [rbp-F0h]
  void *v37; // [rsp+60h] [rbp-E8h] BYREF
  int v38; // [rsp+68h] [rbp-E0h]
  unsigned int *v39; // [rsp+70h] [rbp-D8h]
  void **v40; // [rsp+78h] [rbp-D0h]
  struct CMemoryBuffer *v41; // [rsp+80h] [rbp-C8h]
  char *v42; // [rsp+88h] [rbp-C0h]
  _QWORD *v43; // [rsp+90h] [rbp-B8h]
  _RPC_ASYNC_STATE pAsync; // [rsp+A0h] [rbp-A8h] BYREF

  v7 = a4;
  v40 = a5;
  v39 = a6;
  Reply = 0;
  v10 = 0;
  v36 = 0;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v34 = 0;
  v37 = 0;
  v38 = v7 + 40;
  v11 = CMemoryBuffer::Allocate((int)v7 + 40);
  v13 = v11;
  v41 = v11;
  if ( !v11 )
  {
    LODWORD(v14) = 8;
    goto LABEL_32;
  }
  v15 = *((_QWORD *)v11 + 5);
  *(_QWORD *)(v15 + 8) = 0;
  *(_QWORD *)(v15 + 16) = 0;
  *(_QWORD *)(v15 + 24) = 0;
  *(_QWORD *)(v15 + 32) = 0;
  *(_DWORD *)v15 = 16777256;
  *(_DWORD *)(v15 + 4) = v7;
  v43 = (_QWORD *)((char *)a2 + 1064);
  *(_OWORD *)(v15 + 8) = *(_OWORD *)((char *)a2 + 1064);
  memmove_0((void *)(*((_QWORD *)v13 + 5) + 40LL), a3, v7);
  v16 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  v14 = (unsigned int)ElValidateWin32(v16, v17, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1447);
  if ( !(unsigned int)ElValidateWin32(v14, v18, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1448) )
  {
    pAsync.NotificationType = RpcNotificationTypeEvent;
    pAsync.UserInfo = 0;
    v19 = (HANDLE *)((char *)a2 + 2128);
    v42 = (char *)a2 + 2128;
    pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)*((_QWORD *)a2 + 266);
    v20 = (void *)*((_QWORD *)a2 + 268);
    if ( v20 )
    {
      if ( !ImpersonateLoggedOnUser(v20) )
      {
        LastError = GetLastError();
        v23 = 1462;
LABEL_30:
        v32 = LastError;
LABEL_31:
        LODWORD(v14) = ElValidateWin32(v32, v22, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", v23);
        goto LABEL_32;
      }
      v10 = 1;
      v36 = 1;
    }
    Ndr64AsyncClientCall(
      (MIDL_STUBLESS_PROXY_INFO *)&WdsRpcInterface_ProxyInfo,
      0,
      0,
      &pAsync,
      *((_QWORD *)a2 + 267),
      v38,
      *((_QWORD *)v13 + 5),
      &v34,
      &v37);
    if ( (unsigned int)ElValidateWin32((unsigned int)v14, v24, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1484) )
      goto LABEL_32;
    v25 = WaitForSingleObject(*v19, dwMilliseconds);
    if ( v25 == 258 )
    {
      v14 = (unsigned int)RpcAsyncCancelCall(&pAsync, 1);
      if ( (unsigned int)ElValidateWin32(v14, v26, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1497) )
        goto LABEL_32;
      if ( WaitForSingleObject(*v19, 0xFFFFFFFF) )
      {
        LastError = GetLastError();
        v23 = 1506;
        goto LABEL_30;
      }
      v14 = (unsigned int)RpcAsyncCompleteCall(&pAsync, &Reply);
      if ( !(unsigned int)ElValidateWin32(v14, v27, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1514) )
        LODWORD(v14) = 1460;
    }
    else
    {
      if ( v25 )
      {
        LastError = GetLastError();
        v23 = 1577;
        goto LABEL_30;
      }
      v14 = (unsigned int)RpcAsyncCompleteCall(&pAsync, &Reply);
      if ( !(unsigned int)ElValidateWin32(v14, v28, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1524) )
      {
        v14 = (unsigned int)ElValidateWin32(Reply, v29, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1530);
        if ( !(unsigned int)ElValidateWin32(v14, v30, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1531) )
        {
          if ( v34 >= 0x28 && v37 )
          {
            if ( *((_WORD *)v37 + 1) == 256 && *(_WORD *)v37 == 40 )
            {
              v22 = v43;
              if ( *((_QWORD *)v37 + 1) == *v43 && *((_QWORD *)v37 + 2) == v43[1] )
              {
                v31 = v34 - 40LL;
                if ( *((_DWORD *)v37 + 1) == v31 )
                {
                  memmove_0(v37, (char *)v37 + 40, v31);
                  v34 -= 40;
                  *v39 = v34;
                  v12 = (CClientLibrary *)v40;
                  *v40 = v37;
                  v37 = 0;
                  goto LABEL_32;
                }
              }
            }
            v23 = 1552;
          }
          else
          {
            v23 = 1539;
          }
          v32 = 13;
          goto LABEL_31;
        }
      }
    }
  }
LABEL_32:
  if ( v13 )
    (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v13 + 8LL))(v13);
  if ( v37 )
    CClientLibrary::FreePacket((CClientLibrary *)&stru_1800158D0, 0, v37);
  if ( v10 )
    RevertToSelf();
  if ( (_DWORD)v14 )
    CClientLibrary::DumpRpcErrors(v12);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180005558  mov     [rsp+arg_0], rsi
0x18000555d  push    rdi
0x18000555e  push    r12
0x180005560  push    r13
0x180005562  push    r14
0x180005564  push    r15
0x180005566  sub     rsp, 120h
0x18000556d  mov     rax, cs:__security_cookie
0x180005574  xor     rax, rsp
0x180005577  mov     [rsp+148h+var_38], rax
0x18000557f  mov     edi, r9d
0x180005582  mov     rsi, r8
0x180005585  mov     r13, rdx
0x180005588  mov     rax, [rsp+148h+arg_20]
0x180005590  mov     [rsp+148h+var_D0], rax
0x180005595  mov     rax, [rsp+148h+arg_28]
0x18000559d  mov     [rsp+148h+var_D8], rax
0x1800055a2  and     [rsp+148h+Reply], 0
0x1800055a7  xor     r12d, r12d
0x1800055aa  mov     [rsp+148h+var_F0], r12d
0x1800055af  lea     r15d, [r12+70h]
0x1800055b4  mov     r8d, r15d; Size
0x1800055b7  xor     edx, edx; Val
0x1800055b9  lea     rcx, [rsp+148h+pAsync]; void *
0x1800055c1  call    memset_0
0x1800055c6  and     [rsp+148h+var_F8], r12d
0x1800055cb  and     [rsp+148h+var_E8], r12
0x1800055d0  lea     eax, [rdi+28h]
0x1800055d3  mov     [rsp+148h+var_E0], eax
0x1800055d7  mov     ecx, eax
0x1800055d9  call    cs:__imp_?Allocate@CMemoryBuffer@@SAPEAV1@K@Z; CMemoryBuffer::Allocate(ulong)
0x1800055e0  nop     dword ptr [rax+rax+00h]
0x1800055e5  mov     r14, rax
0x1800055e8  mov     [rsp+148h+var_C8], rax
0x1800055f0  test    rax, rax
0x1800055f3  jnz     short loc_1800055FD
0x1800055f5  lea     edi, [rax+8]
0x1800055f8  jmp     loc_18000597E
0x1800055fd  mov     rax, [rax+28h]
0x180005601  and     [rax+8], r12
0x180005605  and     [rax+10h], r12
0x180005609  and     [rax+18h], r12
0x18000560d  and     [rax+20h], r12
0x180005611  mov     edx, 28h ; '('
0x180005616  mov     dword ptr [rax], 1000028h
0x18000561c  mov     [rax+4], edi
0x18000561f  lea     rcx, [r13+428h]
0x180005626  mov     [rsp+148h+var_B8], rcx
0x18000562e  movups  xmm0, xmmword ptr [rcx]
0x180005631  movdqu  xmmword ptr [rax+8], xmm0
0x180005636  mov     r8, rdi; Size
0x180005639  mov     rcx, [r14+28h]
0x18000563d  add     rcx, rdx; void *
0x180005640  mov     rdx, rsi; Src
0x180005643  call    memmove_0
0x180005648  mov     edx, r15d; Size
0x18000564b  lea     rcx, [rsp+148h+pAsync]; pAsync
0x180005653  call    cs:__imp_RpcAsyncInitializeHandle
0x18000565a  nop     dword ptr [rax+rax+00h]
0x18000565f  mov     ecx, eax
0x180005661  mov     r9d, 5A7h
0x180005667  lea     rsi, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x18000566e  mov     r8, rsi
0x180005671  call    ElValidateWin32
0x180005676  mov     edi, eax
0x180005678  mov     r9d, 5A8h
0x18000567e  mov     r8, rsi
0x180005681  mov     ecx, eax
0x180005683  call    ElValidateWin32
0x180005688  test    eax, eax
0x18000568a  jnz     loc_18000597E
0x180005690  mov     [rsp+148h+pAsync.NotificationType], 1
0x18000569b  and     [rsp+148h+pAsync.UserInfo], r12
0x1800056a3  lea     r15, [r13+850h]
0x1800056aa  mov     [rsp+148h+var_C0], r15
0x1800056b2  mov     rax, [r15]
0x1800056b5  mov     qword ptr [rsp+148h+pAsync.u], rax
0x1800056bd  mov     rcx, [r13+860h]; hToken
0x1800056c4  test    rcx, rcx
0x1800056c7  jz      short loc_1800056FB
0x1800056c9  call    cs:__imp_ImpersonateLoggedOnUser
0x1800056d0  nop     dword ptr [rax+rax+00h]
0x1800056d5  test    eax, eax
0x1800056d7  jnz     short loc_1800056F0
0x1800056d9  call    cs:__imp_GetLastError
0x1800056e0  nop     dword ptr [rax+rax+00h]
0x1800056e5  mov     r9d, 5B6h
0x1800056eb  jmp     loc_180005972
0x1800056f0  mov     r12d, 1
0x1800056f6  mov     [rsp+148h+var_F0], r12d
0x1800056fb  mov     rax, [r14+28h]
0x1800056ff  mov     rcx, [r13+858h]
0x180005706  lea     rdx, [rsp+148h+var_E8]
0x18000570b  mov     [rsp+148h+var_108], rdx
0x180005710  lea     rdx, [rsp+148h+var_F8]
0x180005715  mov     [rsp+148h+var_110], rdx
0x18000571a  mov     [rsp+148h+var_118], rax
0x18000571f  mov     eax, [rsp+148h+var_E0]
0x180005723  mov     [rsp+148h+var_120], eax
0x180005727  mov     [rsp+148h+var_128], rcx
0x18000572c  lea     r9, [rsp+148h+pAsync]
0x180005734  xor     r8d, r8d; pReturnValue
0x180005737  xor     edx, edx; nProcNum
0x180005739  lea     rcx, ?WdsRpcInterface_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180005740  call    cs:__imp_Ndr64AsyncClientCall
0x180005747  nop     dword ptr [rax+rax+00h]
0x18000574c  mov     r13d, 28h ; '('
0x180005752  jmp     short loc_18000578C
0x180005754  mov     ecx, eax
0x180005756  mov     r9d, 5C8h
0x18000575c  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180005763  call    ElValidateWin32
0x180005768  mov     edi, eax
0x18000576a  mov     r13d, 28h ; '('
0x180005770  lea     rsi, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180005777  mov     r12d, [rsp+148h+var_F0]
0x18000577c  mov     r14, [rsp+148h+var_C8]
0x180005784  mov     r15, [rsp+148h+var_C0]
0x18000578c  mov     r9d, 5CCh
0x180005792  mov     r8, rsi
0x180005795  mov     ecx, edi
0x180005797  call    ElValidateWin32
0x18000579c  test    eax, eax
0x18000579e  jnz     loc_18000597E
0x1800057a4  mov     edx, [rsp+148h+dwMilliseconds]; dwMilliseconds
0x1800057ab  mov     rcx, [r15]; hHandle
0x1800057ae  call    cs:__imp_WaitForSingleObject
0x1800057b5  nop     dword ptr [rax+rax+00h]
0x1800057ba  cmp     eax, 102h
0x1800057bf  jnz     loc_180005862
0x1800057c5  mov     edx, 1; fAbort
0x1800057ca  lea     rcx, [rsp+148h+pAsync]; pAsync
0x1800057d2  call    cs:__imp_RpcAsyncCancelCall
0x1800057d9  nop     dword ptr [rax+rax+00h]
0x1800057de  mov     edi, eax
0x1800057e0  mov     r9d, 5D9h
0x1800057e6  mov     r8, rsi
0x1800057e9  mov     ecx, eax
0x1800057eb  call    ElValidateWin32
0x1800057f0  test    eax, eax
0x1800057f2  jnz     loc_18000597E
0x1800057f8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800057fb  mov     rcx, [r15]; hHandle
0x1800057fe  call    cs:__imp_WaitForSingleObject
0x180005805  nop     dword ptr [rax+rax+00h]
0x18000580a  test    eax, eax
0x18000580c  jz      short loc_180005825
0x18000580e  call    cs:__imp_GetLastError
0x180005815  nop     dword ptr [rax+rax+00h]
0x18000581a  mov     r9d, 5E2h
0x180005820  jmp     loc_180005972
0x180005825  lea     rdx, [rsp+148h+Reply]; Reply
0x18000582a  lea     rcx, [rsp+148h+pAsync]; pAsync
0x180005832  call    cs:__imp_RpcAsyncCompleteCall
0x180005839  nop     dword ptr [rax+rax+00h]
0x18000583e  mov     edi, eax
0x180005840  mov     r9d, 5EAh
0x180005846  mov     r8, rsi
0x180005849  mov     ecx, eax
0x18000584b  call    ElValidateWin32
0x180005850  test    eax, eax
0x180005852  jnz     loc_18000597E
0x180005858  mov     edi, 5B4h
0x18000585d  jmp     loc_18000597E
0x180005862  test    eax, eax
0x180005864  jnz     loc_180005960
0x18000586a  lea     rdx, [rsp+148h+Reply]; Reply
0x18000586f  lea     rcx, [rsp+148h+pAsync]; pAsync
0x180005877  call    cs:__imp_RpcAsyncCompleteCall
0x18000587e  nop     dword ptr [rax+rax+00h]
0x180005883  mov     edi, eax
0x180005885  mov     r9d, 5F4h
0x18000588b  mov     r8, rsi
0x18000588e  mov     ecx, eax
0x180005890  call    ElValidateWin32
0x180005895  test    eax, eax
0x180005897  jnz     loc_18000597E
0x18000589d  mov     r9d, 5FAh
0x1800058a3  mov     r8, rsi
0x1800058a6  mov     ecx, [rsp+148h+Reply]
0x1800058aa  call    ElValidateWin32
0x1800058af  mov     edi, eax
0x1800058b1  mov     r9d, 5FBh
0x1800058b7  mov     r8, rsi
0x1800058ba  mov     ecx, eax
0x1800058bc  call    ElValidateWin32
0x1800058c1  test    eax, eax
0x1800058c3  jnz     loc_18000597E
0x1800058c9  cmp     [rsp+148h+var_F8], r13d
0x1800058ce  jb      loc_180005958
0x1800058d4  mov     rcx, [rsp+148h+var_E8]; void *
0x1800058d9  test    rcx, rcx
0x1800058dc  jz      short loc_180005958
0x1800058de  mov     eax, 100h
0x1800058e3  cmp     [rcx+2], ax
0x1800058e7  jnz     short loc_18000594B
0x1800058e9  cmp     [rcx], r13w
0x1800058ed  jnz     short loc_18000594B
0x1800058ef  mov     rax, [rcx+8]
0x1800058f3  mov     rdx, [rsp+148h+var_B8]
0x1800058fb  cmp     rax, [rdx]
0x1800058fe  jnz     short loc_18000594B
0x180005900  mov     rax, [rcx+10h]
0x180005904  cmp     rax, [rdx+8]
0x180005908  jnz     short loc_18000594B
0x18000590a  mov     r8d, [rsp+148h+var_F8]
0x18000590f  add     r8, 0FFFFFFFFFFFFFFD8h; Size
0x180005913  mov     eax, [rcx+4]
0x180005916  cmp     rax, r8
0x180005919  jnz     short loc_18000594B
0x18000591b  lea     rdx, [rcx+28h]; Src
0x18000591f  call    memmove_0
0x180005924  mov     eax, [rsp+148h+var_F8]
0x180005928  add     eax, 0FFFFFFD8h
0x18000592b  mov     [rsp+148h+var_F8], eax
0x18000592f  mov     rcx, [rsp+148h+var_D8]
0x180005934  mov     [rcx], eax
0x180005936  mov     rax, [rsp+148h+var_E8]
0x18000593b  mov     rcx, [rsp+148h+var_D0]
0x180005940  mov     [rcx], rax
0x180005943  and     [rsp+148h+var_E8], 0
0x180005949  jmp     short loc_18000597E
0x18000594b  mov     r9d, 610h
0x180005951  mov     ecx, 0Dh
0x180005956  jmp     short loc_180005974
0x180005958  mov     r9d, 603h
0x18000595e  jmp     short loc_180005951
0x180005960  call    cs:__imp_GetLastError
0x180005967  nop     dword ptr [rax+rax+00h]
0x18000596c  mov     r9d, 629h
0x180005972  mov     ecx, eax
0x180005974  mov     r8, rsi
0x180005977  call    ElValidateWin32
0x18000597c  mov     edi, eax
0x18000597e  test    r14, r14
0x180005981  jz      short loc_180005992
0x180005983  mov     rax, [r14]
0x180005986  mov     rcx, r14
0x180005989  mov     rax, [rax+8]
0x18000598d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005992  mov     r8, [rsp+148h+var_E8]; void *
0x180005997  test    r8, r8
0x18000599a  jz      short loc_1800059AA
0x18000599c  xor     edx, edx; void *
0x18000599e  lea     rcx, stru_1800158D0; this
0x1800059a5  call    ?FreePacket@CClientLibrary@@QEAAKPEAX0@Z; CClientLibrary::FreePacket(void *,void *)
0x1800059aa  test    r12d, r12d
0x1800059ad  jz      short loc_1800059BB
0x1800059af  call    cs:__imp_RevertToSelf
0x1800059b6  nop     dword ptr [rax+rax+00h]
0x1800059bb  test    edi, edi
0x1800059bd  jz      short loc_1800059C4
0x1800059bf  call    ?DumpRpcErrors@CClientLibrary@@AEAAXXZ; CClientLibrary::DumpRpcErrors(void)
0x1800059c4  mov     eax, edi
0x1800059c6  mov     rcx, [rsp+148h+var_38]
0x1800059ce  xor     rcx, rsp; StackCookie
0x1800059d1  call    __security_check_cookie
0x1800059d6  mov     rsi, [rsp+148h+arg_0]
0x1800059de  add     rsp, 120h
0x1800059e5  pop     r15
0x1800059e7  pop     r14
0x1800059e9  pop     r13
0x1800059eb  pop     r12
0x1800059ed  pop     rdi
0x1800059ee  retn
0x18000dbe5  push    rbp
0x18000dbe7  sub     rsp, 50h
0x18000dbeb  mov     rbp, rdx
0x18000dbee  mov     rax, [rcx]
0x18000dbf1  mov     ecx, [rax]; ExceptionCode
0x18000dbf3  call    cs:__imp_I_RpcExceptionFilter
0x18000dbfa  nop     dword ptr [rax+rax+00h]
0x18000dbff  nop
0x18000dc00  add     rsp, 50h
0x18000dc04  pop     rbp
0x18000dc05  retn
```
