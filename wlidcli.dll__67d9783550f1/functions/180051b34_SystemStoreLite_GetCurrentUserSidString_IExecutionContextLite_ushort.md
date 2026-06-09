# SystemStoreLite::GetCurrentUserSidString(IExecutionContextLite *,ushort * *)

- ea: `0x180051b34`
- end: `0x180051ef6`
- name: `?GetCurrentUserSidString@SystemStoreLite@@SAJPEAVIExecutionContextLite@@PEAPEAG@Z`
- size: `962`
- prototype: `__int64 __fastcall(struct IExecutionContextLite *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180051a00`
- `0x1800528b4`

## callees

- `0x18000cc9c`
- `0x18000e870`
- `0x180021a64`
- `0x180021a90`
- `0x180022eb0`
- `0x180051250`
- `0x1800512f8`
- `0x180051b34`
- `0x1800530e4`
- `0x180053890`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051d68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180051d68`

## string_xrefs

- `0x180051b8d`: `SystemStoreLite::GetCurrentUserSidString`
- `0x180051e7a`: `pContext != nullptr && ppSidString != nullptr`
- `0x180051c58`: `OpenThreadToken failed. (win32 = 0x%0x)`
- `0x180051cd3`: `OpenProcessToken failed. (win32 = 0x%0x)`
- `0x180051d17`: `(result = pWinApiFunctions->GetTokenInformation(accessToken, TokenUser, nullptr, 0, &tokenUserLength)) == FALSE`
- `0x180051d4e`: `OpenProccessToken failed. (win32 = 0x%0x)`
- `0x180051e08`: `OpenProccessToken failed. (win32 = 0x%0x)`
- `0x180051e51`: `ConvertSidToStringSid failed. (win32 = 0x%0x)`

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
    &qword_180081998);
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
      Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(v25);
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
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v27);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>();
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(v24);
  return v17;
}

```

## disassembly

```asm
0x180051b34  mov     [rsp-8+arg_8], rbx
0x180051b39  push    rbp
0x180051b3a  push    rsi
0x180051b3b  push    rdi
0x180051b3c  push    r14
0x180051b3e  push    r15
0x180051b40  lea     rbp, [rsp-37h]
0x180051b45  sub     rsp, 0D0h
0x180051b4c  mov     rsi, rdx
0x180051b4f  mov     rax, [rcx]
0x180051b52  mov     rax, [rax+18h]
0x180051b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b5b  mov     rbx, rax
0x180051b5e  xor     r14d, r14d
0x180051b61  mov     [rbp+57h+var_98], r14
0x180051b65  mov     [rbp+57h+var_88], rax
0x180051b69  mov     [rbp+57h+var_90], r14
0x180051b6d  mov     dword ptr [rbp+57h+uBytes], r14d
0x180051b71  mov     [rbp+57h+var_80], r14
0x180051b75  mov     [rbp+57h+var_70], r14
0x180051b79  mov     [rbp+57h+var_78], r14
0x180051b7d  mov     [rbp+57h+var_B0], r14
0x180051b81  mov     [rbp+57h+var_A0], r14
0x180051b85  mov     [rbp+57h+var_A8], r14
0x180051b89  mov     [rbp+57h+arg_0], r14d
0x180051b8d  lea     rdi, aSystemstorelit_2; "SystemStoreLite::GetCurrentUserSidStrin"...
0x180051b94  mov     [rbp+57h+var_48], rdi
0x180051b98  lea     rax, [rbp+57h+arg_0]
0x180051b9c  mov     [rbp+57h+var_40], rax
0x180051ba0  mov     [rbp+57h+var_38], r14
0x180051ba4  mov     [rbp+57h+var_30], r14
0x180051ba8  xor     r9d, r9d; unsigned int
0x180051bab  mov     r8d, 162h; char *
0x180051bb1  mov     rdx, rdi; char *
0x180051bb4  lea     r15, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180051bbb  mov     rcx, r15; this
0x180051bbe  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180051bc3  nop
0x180051bc4  lea     rax, qword_180081998
0x180051bcb  mov     [rsp+0F0h+var_D0], rax; int *
0x180051bd0  lea     r9d, [r14+0Ah]; unsigned __int64
0x180051bd4  lea     r8, [rbp+57h+arg_0]; int *
0x180051bd8  mov     rdx, rdi; char *
0x180051bdb  lea     rcx, [rbp+57h+var_68]; this
0x180051bdf  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180051be4  nop
0x180051be5  test    rsi, rsi
0x180051be8  jz      loc_180051E74
0x180051bee  mov     [rsi], r14
0x180051bf1  mov     rax, [rbx]
0x180051bf4  mov     rcx, rbx
0x180051bf7  mov     rax, [rax+50h]
0x180051bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c00  mov     rcx, [rbx]
0x180051c03  mov     r10, [rcx+0E0h]
0x180051c0a  lea     rcx, [rbp+57h+var_98]
0x180051c0e  mov     [rsp+0F0h+var_D0], rcx
0x180051c13  lea     r9d, [r14+1]
0x180051c17  lea     r8d, [r14+8]
0x180051c1b  mov     rdx, rax
0x180051c1e  mov     rcx, rbx
0x180051c21  mov     rax, r10
0x180051c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c29  test    eax, eax
0x180051c2b  jnz     loc_180051CE2
0x180051c31  mov     rax, [rbx]
0x180051c34  mov     rcx, rbx
0x180051c37  mov     rax, [rax+78h]
0x180051c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c40  cmp     eax, 3F0h
0x180051c45  jz      short loc_180051C7E
0x180051c47  test    eax, eax
0x180051c49  jg      short loc_180051C4F
0x180051c4b  mov     ecx, eax
0x180051c4d  jmp     short loc_180051C58
0x180051c4f  movzx   ecx, ax
0x180051c52  or      ecx, 80070000h
0x180051c58  lea     r9, aOpenthreadtoke_1; "OpenThreadToken failed. (win32 = 0x%0x)"
0x180051c5f  mov     r8d, 175h; unsigned int
0x180051c65  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180051c69  mov     [rbp+57h+arg_0], ecx
0x180051c6c  mov     rdx, r15; char *
0x180051c6f  mov     ecx, 2; unsigned __int8
0x180051c74  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180051c79  jmp     loc_180051E9B
0x180051c7e  mov     rax, [rbx]
0x180051c81  mov     rcx, rbx
0x180051c84  mov     rax, [rax+58h]
0x180051c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c8d  mov     rcx, [rbx]
0x180051c90  mov     r10, [rcx+100h]
0x180051c97  lea     r9, [rbp+57h+var_98]
0x180051c9b  mov     r8d, 8
0x180051ca1  mov     rdx, rax
0x180051ca4  mov     rcx, rbx
0x180051ca7  mov     rax, r10
0x180051caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051caf  test    eax, eax
0x180051cb1  jnz     short loc_180051CE2
0x180051cb3  mov     rax, [rbx]
0x180051cb6  mov     rcx, rbx
0x180051cb9  mov     rax, [rax+78h]
0x180051cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051cc2  test    eax, eax
0x180051cc4  jg      short loc_180051CCA
0x180051cc6  mov     ecx, eax
0x180051cc8  jmp     short loc_180051CD3
0x180051cca  movzx   ecx, ax
0x180051ccd  or      ecx, 80070000h
0x180051cd3  lea     r9, aOpenprocesstok; "OpenProcessToken failed. (win32 = 0x%0x"...
0x180051cda  mov     r8d, 186h
0x180051ce0  jmp     short loc_180051C65
0x180051ce2  mov     rax, [rbx]
0x180051ce5  lea     rcx, [rbp+57h+uBytes]
0x180051ce9  mov     [rsp+0F0h+var_C8], rcx
0x180051cee  mov     dword ptr [rsp+0F0h+var_D0], r14d
0x180051cf3  xor     r9d, r9d
0x180051cf6  lea     r8d, [r9+1]
0x180051cfa  mov     rdx, [rbp+57h+var_98]
0x180051cfe  mov     rcx, rbx
0x180051d01  mov     rax, [rax+90h]
0x180051d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d0d  test    eax, eax
0x180051d0f  jz      short loc_180051D29
0x180051d11  mov     r9d, 8000FFFFh
0x180051d17  lea     rax, aResultPwinapif; "(result = pWinApiFunctions->GetTokenInf"...
0x180051d1e  mov     r8d, 18Dh
0x180051d24  jmp     loc_180051E87
0x180051d29  mov     rax, [rbx]
0x180051d2c  mov     rcx, rbx
0x180051d2f  mov     rax, [rax+78h]
0x180051d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d38  cmp     eax, 7Ah ; 'z'
0x180051d3b  jz      short loc_180051D60
0x180051d3d  test    eax, eax
0x180051d3f  jg      short loc_180051D45
0x180051d41  mov     ecx, eax
0x180051d43  jmp     short loc_180051D4E
0x180051d45  movzx   ecx, ax
0x180051d48  or      ecx, 80070000h
0x180051d4e  lea     r9, aOpenproccessto; "OpenProccessToken failed. (win32 = 0x%0"...
0x180051d55  mov     r8d, 193h
0x180051d5b  jmp     loc_180051C65
0x180051d60  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x180051d63  mov     ecx, 40h ; '@'; uFlags
0x180051d68  call    cs:__imp_LocalAlloc
0x180051d6e  mov     rdi, rax
0x180051d71  test    rax, rax
0x180051d74  jnz     short loc_180051DA8
0x180051d76  mov     rax, [rbx]
0x180051d79  mov     rcx, rbx
0x180051d7c  mov     rax, [rax+78h]
0x180051d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d85  test    eax, eax
0x180051d87  jg      short loc_180051D8D
0x180051d89  mov     ecx, eax
0x180051d8b  jmp     short loc_180051D96
0x180051d8d  movzx   ecx, ax
0x180051d90  or      ecx, 80070000h
0x180051d96  lea     r9, aLocalallocFail; "LocalAlloc failed. (win32 = 0x%0x)"
0x180051d9d  mov     r8d, 19Dh
0x180051da3  jmp     loc_180051C65
0x180051da8  lea     rcx, [rbp+57h+var_80]
0x180051dac  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x180051db1  mov     [rbp+57h+var_80], rdi
0x180051db5  mov     ecx, dword ptr [rbp+57h+uBytes]
0x180051db8  mov     rax, [rbx]
0x180051dbb  lea     rdx, [rbp+57h+uBytes]
0x180051dbf  mov     [rsp+0F0h+var_C8], rdx
0x180051dc4  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x180051dc8  mov     r9, rdi
0x180051dcb  mov     r8d, 1
0x180051dd1  mov     rdx, [rbp+57h+var_98]
0x180051dd5  mov     rcx, rbx
0x180051dd8  mov     rax, [rax+90h]
0x180051ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051de4  mov     r9, [rbx]
0x180051de7  mov     rcx, rbx
0x180051dea  test    eax, eax
0x180051dec  jnz     short loc_180051E1A
0x180051dee  mov     rax, [r9+78h]
0x180051df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051df7  test    eax, eax
0x180051df9  jg      short loc_180051DFF
0x180051dfb  mov     ecx, eax
0x180051dfd  jmp     short loc_180051E08
0x180051dff  movzx   ecx, ax
0x180051e02  or      ecx, 80070000h
0x180051e08  lea     r9, aOpenproccessto; "OpenProccessToken failed. (win32 = 0x%0"...
0x180051e0f  mov     r8d, 1AFh
0x180051e15  jmp     loc_180051C65
0x180051e1a  lea     r8, [rbp+57h+var_B0]
0x180051e1e  mov     rdx, [rdi]
0x180051e21  mov     rax, [r9+0C0h]
0x180051e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e2d  test    eax, eax
0x180051e2f  jnz     short loc_180051E63
0x180051e31  mov     rax, [rbx]
0x180051e34  mov     rcx, rbx
0x180051e37  mov     rax, [rax+78h]
0x180051e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e40  test    eax, eax
0x180051e42  jg      short loc_180051E48
0x180051e44  mov     ecx, eax
0x180051e46  jmp     short loc_180051E51
0x180051e48  movzx   ecx, ax
0x180051e4b  or      ecx, 80070000h
0x180051e51  lea     r9, aConvertsidtost; "ConvertSidToStringSid failed. (win32 = "...
0x180051e58  mov     r8d, 1BCh
0x180051e5e  jmp     loc_180051C65
0x180051e63  mov     rax, [rbp+57h+var_B0]
0x180051e67  mov     [rbp+57h+var_B0], r14
0x180051e6b  mov     [rbp+57h+var_A8], r14
0x180051e6f  mov     [rsi], rax
0x180051e72  jmp     short loc_180051E9B
0x180051e74  mov     r9d, 80070057h; int
0x180051e7a  lea     rax, aPcontextNullpt_0; "pContext != nullptr && ppSidString != n"...
0x180051e81  mov     r8d, 167h; unsigned int
0x180051e87  mov     [rsp+0F0h+var_D0], rax; char *
0x180051e8c  mov     [rbp+57h+arg_0], r9d
0x180051e90  mov     rdx, rdi; char *
0x180051e93  mov     rcx, r15; char *
0x180051e96  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180051e9b  mov     ebx, [rbp+57h+arg_0]
0x180051e9e  mov     r9, [rbp+57h+var_68]; int *
0x180051ea2  mov     r8, [rbp+57h+var_60]; unsigned __int64
0x180051ea6  mov     rdx, [rbp+57h+var_58]
0x180051eaa  mov     edx, [rdx]; int
0x180051eac  mov     rcx, [rbp+57h+var_50]; char *
0x180051eb0  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180051eb5  nop
0x180051eb6  lea     rcx, [rbp+57h+var_48]
0x180051eba  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180051ebf  nop
0x180051ec0  lea     rcx, [rbp+57h+var_B0]
0x180051ec4  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180051ec9  nop
0x180051eca  lea     rcx, [rbp+57h+var_80]
0x180051ece  call    ??1?$Auto@PEAU_TOKEN_USER@@V?$LocalAllocFunctor@PEAU_TOKEN_USER@@@@VDummyContext@@@@QEAA@XZ; Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(void)
0x180051ed3  nop
0x180051ed4  lea     rcx, [rbp+57h+var_98]
0x180051ed8  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x180051edd  mov     eax, ebx
0x180051edf  mov     rbx, [rsp+0F0h+arg_8]
0x180051ee7  add     rsp, 0D0h
0x180051eee  pop     r15
0x180051ef0  pop     r14
0x180051ef2  pop     rdi
0x180051ef3  pop     rsi
0x180051ef4  pop     rbp
0x180051ef5  retn
```
