# SystemStoreLite::GetCurrentUserSidString(IExecutionContextLite *,ushort * *)

- ea: `0x1800054bc`
- end: `0x18000587e`
- name: `?GetCurrentUserSidString@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEAPEAG@Z`
- size: `962`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180005430`
- `0x1800058b8`
- `0x180024a94`

## callees

- `0x180004824`
- `0x180004910`
- `0x180004b2c`
- `0x1800054bc`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18001173c`
- `0x180013cd8`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800056f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800056f0`

## string_xrefs

- `0x180005802`: `pContext != nullptr && ppSidString != nullptr`
- `0x180005515`: `SystemStoreLite::GetCurrentUserSidString`
- `0x18000565b`: `OpenProcessToken failed. (win32 = 0x%0x)`
- `0x1800055e0`: `OpenThreadToken failed. (win32 = 0x%0x)`
- `0x1800056d6`: `OpenProccessToken failed. (win32 = 0x%0x)`
- `0x180005790`: `OpenProccessToken failed. (win32 = 0x%0x)`
- `0x18000569f`: `(result = pWinApiFunctions->GetTokenInformation(accessToken, TokenUser, nullptr, 0, &tokenUserLength)) == FALSE`
- `0x1800057d9`: `ConvertSidToStringSid failed. (win32 = 0x%0x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemStoreLite::GetCurrentUserSidString(struct IExecutionContextLite *a1, unsigned __int16 **a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // ecx
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  __int64 v9; // rax
  int v10; // r9d
  const char *v11; // rax
  unsigned int v12; // r8d
  _QWORD *v13; // rdi
  int v14; // eax
  __int64 v15; // r9
  unsigned __int16 *v16; // rax
  unsigned int v17; // ebx
  char *v19; // [rsp+20h] [rbp-79h]
  char *v20; // [rsp+20h] [rbp-79h]
  unsigned __int16 *v21; // [rsp+40h] [rbp-59h] BYREF
  __int64 v22; // [rsp+48h] [rbp-51h]
  __int64 v23; // [rsp+50h] [rbp-49h]
  _QWORD v24[3]; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v25[3]; // [rsp+70h] [rbp-29h] BYREF
  int *v26[4]; // [rsp+88h] [rbp-11h] BYREF
  _QWORD v27[9]; // [rsp+A8h] [rbp+Fh] BYREF
  int v28; // [rsp+100h] [rbp+67h] BYREF
  SIZE_T uBytes; // [rsp+110h] [rbp+77h] BYREF

  v3 = (*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)a1 + 24LL))(a1);
  v24[0] = 0;
  v24[2] = v3;
  v24[1] = 0;
  LODWORD(uBytes) = 0;
  memset(v25, 0, sizeof(v25));
  v21 = 0;
  v23 = 0;
  v22 = 0;
  v28 = 0;
  v27[0] = "SystemStoreLite::GetCurrentUserSidString";
  v27[1] = &v28;
  v27[2] = 0;
  v27[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
    "SystemStoreLite::GetCurrentUserSidString",
    (const char *)0x162,
    0,
    (const unsigned __int16 *)v19);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v26,
    "SystemStoreLite::GetCurrentUserSidString",
    &v28,
    0xAu,
    &qword_1800726C8);
  if ( !a2 )
  {
    v10 = -2147024809;
    v11 = "pContext != nullptr && ppSidString != nullptr";
    v12 = 359;
    goto LABEL_38;
  }
  *a2 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 80LL))(v3);
  if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, __int64, _QWORD *))(*(_QWORD *)v3 + 224LL))(
          v3,
          v4,
          8,
          1,
          v24) )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
    if ( v5 != 1008 )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      else
        v6 = v5;
      v7 = L"OpenThreadToken failed. (win32 = 0x%0x)";
      v8 = 373;
      goto LABEL_8;
    }
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 88LL))(v3);
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, _QWORD *))(*(_QWORD *)v3 + 256LL))(v3, v9, 8, v24) )
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      else
        v6 = v5;
      v7 = L"OpenProcessToken failed. (win32 = 0x%0x)";
      v8 = 390;
      goto LABEL_8;
    }
  }
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v3 + 144LL))(v3, v24[0], 1) )
  {
    v10 = -2147418113;
    v11 = "(result = pWinApiFunctions->GetTokenInformation(accessToken, TokenUser, nullptr, 0, &tokenUserLength)) == FALSE";
    v12 = 397;
LABEL_38:
    v28 = v10;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp",
      "SystemStoreLite::GetCurrentUserSidString",
      v12,
      v10,
      v11);
    goto LABEL_39;
  }
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
  if ( v5 == 122 )
  {
    v13 = LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( v13 )
    {
      Auto<unsigned char *,LocalAllocFunctor<unsigned char *>,DummyContext>::Clear(v25);
      v25[0] = v13;
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD *, _DWORD, SIZE_T *))(*(_QWORD *)v3 + 144LL))(
              v3,
              v24[0],
              1,
              v13,
              uBytes,
              &uBytes);
      v15 = *(_QWORD *)v3;
      if ( v14 )
      {
        if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(v15 + 192))(v3, *v13, &v21) )
        {
          v16 = v21;
          v21 = 0;
          v22 = 0;
          *a2 = v16;
          goto LABEL_39;
        }
        v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
        if ( v5 > 0 )
          v6 = (unsigned __int16)v5 | 0x80070000;
        else
          v6 = v5;
        v7 = L"ConvertSidToStringSid failed. (win32 = 0x%0x)";
        v8 = 444;
      }
      else
      {
        v5 = (*(__int64 (__fastcall **)(__int64))(v15 + 120))(v3);
        if ( v5 > 0 )
          v6 = (unsigned __int16)v5 | 0x80070000;
        else
          v6 = v5;
        v7 = L"OpenProccessToken failed. (win32 = 0x%0x)";
        v8 = 431;
      }
    }
    else
    {
      v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 120LL))(v3);
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      else
        v6 = v5;
      v7 = L"LocalAlloc failed. (win32 = 0x%0x)";
      v8 = 413;
    }
  }
  else
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    else
      v6 = v5;
    v7 = L"OpenProccessToken failed. (win32 = 0x%0x)";
    v8 = 403;
  }
LABEL_8:
  LODWORD(v20) = v5;
  v28 = v6;
  TracePrintW(2u, "onecoreuap\\ds\\ext\\live\\identity\\lib\\systemstorelite\\systemstorelite.cpp", v8, v7, v20);
LABEL_39:
  v17 = v28;
  ErrorVerifier::CheckAgainstList((const char *)v26[3], *v26[2], (unsigned __int64)v26[1], v26[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v27);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(&v21);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(v25);
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(v24);
  return v17;
}

```

## disassembly

```asm
0x1800054bc  mov     [rsp-8+arg_8], rbx
0x1800054c1  push    rbp
0x1800054c2  push    rsi
0x1800054c3  push    rdi
0x1800054c4  push    r14
0x1800054c6  push    r15
0x1800054c8  lea     rbp, [rsp-37h]
0x1800054cd  sub     rsp, 0D0h
0x1800054d4  mov     rsi, rdx
0x1800054d7  mov     rax, [rcx]
0x1800054da  mov     rax, [rax+18h]
0x1800054de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e3  mov     rbx, rax
0x1800054e6  xor     r14d, r14d
0x1800054e9  mov     [rbp+57h+var_98], r14
0x1800054ed  mov     [rbp+57h+var_88], rax
0x1800054f1  mov     [rbp+57h+var_90], r14
0x1800054f5  mov     dword ptr [rbp+57h+uBytes], r14d
0x1800054f9  mov     [rbp+57h+var_80], r14
0x1800054fd  mov     [rbp+57h+var_70], r14
0x180005501  mov     [rbp+57h+var_78], r14
0x180005505  mov     [rbp+57h+var_B0], r14
0x180005509  mov     [rbp+57h+var_A0], r14
0x18000550d  mov     [rbp+57h+var_A8], r14
0x180005511  mov     [rbp+57h+arg_0], r14d
0x180005515  lea     rdi, aSystemstorelit_2; "SystemStoreLite::GetCurrentUserSidStrin"...
0x18000551c  mov     [rbp+57h+var_48], rdi
0x180005520  lea     rax, [rbp+57h+arg_0]
0x180005524  mov     [rbp+57h+var_40], rax
0x180005528  mov     [rbp+57h+var_38], r14
0x18000552c  mov     [rbp+57h+var_30], r14
0x180005530  xor     r9d, r9d; unsigned int
0x180005533  mov     r8d, 162h; char *
0x180005539  mov     rdx, rdi; char *
0x18000553c  lea     r15, aOnecoreuapDsEx_16; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180005543  mov     rcx, r15; this
0x180005546  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000554b  nop
0x18000554c  lea     rax, qword_1800726C8
0x180005553  mov     [rsp+0F0h+var_D0], rax; int *
0x180005558  lea     r9d, [r14+0Ah]; unsigned __int64
0x18000555c  lea     r8, [rbp+57h+arg_0]; int *
0x180005560  mov     rdx, rdi; char *
0x180005563  lea     rcx, [rbp+57h+var_68]; this
0x180005567  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x18000556c  nop
0x18000556d  test    rsi, rsi
0x180005570  jz      loc_1800057FC
0x180005576  mov     [rsi], r14
0x180005579  mov     rax, [rbx]
0x18000557c  mov     rcx, rbx
0x18000557f  mov     rax, [rax+50h]
0x180005583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005588  mov     rcx, [rbx]
0x18000558b  mov     r10, [rcx+0E0h]
0x180005592  lea     rcx, [rbp+57h+var_98]
0x180005596  mov     [rsp+0F0h+var_D0], rcx
0x18000559b  lea     r9d, [r14+1]
0x18000559f  lea     r8d, [r14+8]
0x1800055a3  mov     rdx, rax
0x1800055a6  mov     rcx, rbx
0x1800055a9  mov     rax, r10
0x1800055ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b1  test    eax, eax
0x1800055b3  jnz     loc_18000566A
0x1800055b9  mov     rax, [rbx]
0x1800055bc  mov     rcx, rbx
0x1800055bf  mov     rax, [rax+78h]
0x1800055c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055c8  cmp     eax, 3F0h
0x1800055cd  jz      short loc_180005606
0x1800055cf  test    eax, eax
0x1800055d1  jg      short loc_1800055D7
0x1800055d3  mov     ecx, eax
0x1800055d5  jmp     short loc_1800055E0
0x1800055d7  movzx   ecx, ax
0x1800055da  or      ecx, 80070000h
0x1800055e0  lea     r9, aOpenthreadtoke; "OpenThreadToken failed. (win32 = 0x%0x)"
0x1800055e7  mov     r8d, 175h; unsigned int
0x1800055ed  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1800055f1  mov     [rbp+57h+arg_0], ecx
0x1800055f4  mov     rdx, r15; char *
0x1800055f7  mov     ecx, 2; unsigned __int8
0x1800055fc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180005601  jmp     loc_180005823
0x180005606  mov     rax, [rbx]
0x180005609  mov     rcx, rbx
0x18000560c  mov     rax, [rax+58h]
0x180005610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005615  mov     rcx, [rbx]
0x180005618  mov     r10, [rcx+100h]
0x18000561f  lea     r9, [rbp+57h+var_98]
0x180005623  mov     r8d, 8
0x180005629  mov     rdx, rax
0x18000562c  mov     rcx, rbx
0x18000562f  mov     rax, r10
0x180005632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005637  test    eax, eax
0x180005639  jnz     short loc_18000566A
0x18000563b  mov     rax, [rbx]
0x18000563e  mov     rcx, rbx
0x180005641  mov     rax, [rax+78h]
0x180005645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000564a  test    eax, eax
0x18000564c  jg      short loc_180005652
0x18000564e  mov     ecx, eax
0x180005650  jmp     short loc_18000565B
0x180005652  movzx   ecx, ax
0x180005655  or      ecx, 80070000h
0x18000565b  lea     r9, aOpenprocesstok; "OpenProcessToken failed. (win32 = 0x%0x"...
0x180005662  mov     r8d, 186h
0x180005668  jmp     short loc_1800055ED
0x18000566a  mov     rax, [rbx]
0x18000566d  lea     rcx, [rbp+57h+uBytes]
0x180005671  mov     [rsp+0F0h+var_C8], rcx
0x180005676  mov     dword ptr [rsp+0F0h+var_D0], r14d
0x18000567b  xor     r9d, r9d
0x18000567e  lea     r8d, [r9+1]
0x180005682  mov     rdx, [rbp+57h+var_98]
0x180005686  mov     rcx, rbx
0x180005689  mov     rax, [rax+90h]
0x180005690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005695  test    eax, eax
0x180005697  jz      short loc_1800056B1
0x180005699  mov     r9d, 8000FFFFh
0x18000569f  lea     rax, aResultPwinapif; "(result = pWinApiFunctions->GetTokenInf"...
0x1800056a6  mov     r8d, 18Dh
0x1800056ac  jmp     loc_18000580F
0x1800056b1  mov     rax, [rbx]
0x1800056b4  mov     rcx, rbx
0x1800056b7  mov     rax, [rax+78h]
0x1800056bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c0  cmp     eax, 7Ah ; 'z'
0x1800056c3  jz      short loc_1800056E8
0x1800056c5  test    eax, eax
0x1800056c7  jg      short loc_1800056CD
0x1800056c9  mov     ecx, eax
0x1800056cb  jmp     short loc_1800056D6
0x1800056cd  movzx   ecx, ax
0x1800056d0  or      ecx, 80070000h
0x1800056d6  lea     r9, aOpenproccessto; "OpenProccessToken failed. (win32 = 0x%0"...
0x1800056dd  mov     r8d, 193h
0x1800056e3  jmp     loc_1800055ED
0x1800056e8  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x1800056eb  mov     ecx, 40h ; '@'; uFlags
0x1800056f0  call    cs:__imp_LocalAlloc
0x1800056f6  mov     rdi, rax
0x1800056f9  test    rax, rax
0x1800056fc  jnz     short loc_180005730
0x1800056fe  mov     rax, [rbx]
0x180005701  mov     rcx, rbx
0x180005704  mov     rax, [rax+78h]
0x180005708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000570d  test    eax, eax
0x18000570f  jg      short loc_180005715
0x180005711  mov     ecx, eax
0x180005713  jmp     short loc_18000571E
0x180005715  movzx   ecx, ax
0x180005718  or      ecx, 80070000h
0x18000571e  lea     r9, aLocalallocFail; "LocalAlloc failed. (win32 = 0x%0x)"
0x180005725  mov     r8d, 19Dh
0x18000572b  jmp     loc_1800055ED
0x180005730  lea     rcx, [rbp+57h+var_80]
0x180005734  call    ?Clear@?$Auto@PEAEV?$LocalAllocFunctor@PEAE@@VDummyContext@@@@QEAAXXZ; Auto<uchar *,LocalAllocFunctor<uchar *>,DummyContext>::Clear(void)
0x180005739  mov     [rbp+57h+var_80], rdi
0x18000573d  mov     ecx, dword ptr [rbp+57h+uBytes]
0x180005740  mov     rax, [rbx]
0x180005743  lea     rdx, [rbp+57h+uBytes]
0x180005747  mov     [rsp+0F0h+var_C8], rdx
0x18000574c  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x180005750  mov     r9, rdi
0x180005753  mov     r8d, 1
0x180005759  mov     rdx, [rbp+57h+var_98]
0x18000575d  mov     rcx, rbx
0x180005760  mov     rax, [rax+90h]
0x180005767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000576c  mov     r9, [rbx]
0x18000576f  mov     rcx, rbx
0x180005772  test    eax, eax
0x180005774  jnz     short loc_1800057A2
0x180005776  mov     rax, [r9+78h]
0x18000577a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000577f  test    eax, eax
0x180005781  jg      short loc_180005787
0x180005783  mov     ecx, eax
0x180005785  jmp     short loc_180005790
0x180005787  movzx   ecx, ax
0x18000578a  or      ecx, 80070000h
0x180005790  lea     r9, aOpenproccessto; "OpenProccessToken failed. (win32 = 0x%0"...
0x180005797  mov     r8d, 1AFh
0x18000579d  jmp     loc_1800055ED
0x1800057a2  lea     r8, [rbp+57h+var_B0]
0x1800057a6  mov     rdx, [rdi]
0x1800057a9  mov     rax, [r9+0C0h]
0x1800057b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b5  test    eax, eax
0x1800057b7  jnz     short loc_1800057EB
0x1800057b9  mov     rax, [rbx]
0x1800057bc  mov     rcx, rbx
0x1800057bf  mov     rax, [rax+78h]
0x1800057c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c8  test    eax, eax
0x1800057ca  jg      short loc_1800057D0
0x1800057cc  mov     ecx, eax
0x1800057ce  jmp     short loc_1800057D9
0x1800057d0  movzx   ecx, ax
0x1800057d3  or      ecx, 80070000h
0x1800057d9  lea     r9, aConvertsidtost_0; "ConvertSidToStringSid failed. (win32 = "...
0x1800057e0  mov     r8d, 1BCh
0x1800057e6  jmp     loc_1800055ED
0x1800057eb  mov     rax, [rbp+57h+var_B0]
0x1800057ef  mov     [rbp+57h+var_B0], r14
0x1800057f3  mov     [rbp+57h+var_A8], r14
0x1800057f7  mov     [rsi], rax
0x1800057fa  jmp     short loc_180005823
0x1800057fc  mov     r9d, 80070057h; int
0x180005802  lea     rax, aPcontextNullpt_0; "pContext != nullptr && ppSidString != n"...
0x180005809  mov     r8d, 167h; unsigned int
0x18000580f  mov     [rsp+0F0h+var_D0], rax; char *
0x180005814  mov     [rbp+57h+arg_0], r9d
0x180005818  mov     rdx, rdi; char *
0x18000581b  mov     rcx, r15; char *
0x18000581e  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180005823  mov     ebx, [rbp+57h+arg_0]
0x180005826  mov     r9, [rbp+57h+var_68]; int *
0x18000582a  mov     r8, [rbp+57h+var_60]; unsigned __int64
0x18000582e  mov     rdx, [rbp+57h+var_58]
0x180005832  mov     edx, [rdx]; int
0x180005834  mov     rcx, [rbp+57h+var_50]; char *
0x180005838  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x18000583d  nop
0x18000583e  lea     rcx, [rbp+57h+var_48]
0x180005842  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180005847  nop
0x180005848  lea     rcx, [rbp+57h+var_B0]
0x18000584c  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180005851  nop
0x180005852  lea     rcx, [rbp+57h+var_80]
0x180005856  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x18000585b  nop
0x18000585c  lea     rcx, [rbp+57h+var_98]
0x180005860  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x180005865  mov     eax, ebx
0x180005867  mov     rbx, [rsp+0F0h+arg_8]
0x18000586f  add     rsp, 0D0h
0x180005876  pop     r15
0x180005878  pop     r14
0x18000587a  pop     rdi
0x18000587b  pop     rsi
0x18000587c  pop     rbp
0x18000587d  retn
```
