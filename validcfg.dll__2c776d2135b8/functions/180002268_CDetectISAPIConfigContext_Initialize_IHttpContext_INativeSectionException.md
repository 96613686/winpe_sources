# CDetectISAPIConfigContext::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180002268`
- end: `0x1800027bc`
- name: `?Initialize@CDetectISAPIConfigContext@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `1364`
- prototype: `__int64 __fastcall(CDetectISAPIConfigContext *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180001510`

## callees

- `0x180001010`
- `0x180002268`
- `0x180003132`
- `0x180004010`

## string_xrefs

- `0x180002391`: `validateIntegratedModeConfiguration`
- `0x180002517`: `impersonate`

## pseudocode

```c
__int64 __fastcall CDetectISAPIConfigContext::Initialize(
        CDetectISAPIConfigContext *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  struct INativeSectionException *v4; // rcx
  __int64 v7; // r9
  int v8; // r14d
  int v9; // esi
  int v10; // ebx
  __int64 (__fastcall ***v11)(_QWORD); // rax
  wchar_t *v12; // r12
  __int64 (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rax
  int v14; // r12d
  __int64 v15; // rax
  __int64 v16; // r15
  CDetectISAPIConfigContext *v17; // rcx
  __int64 v18; // rcx
  CDetectISAPIConfigContext *v19; // rcx
  struct INativeSectionException *v21; // [rsp+40h] [rbp-49h] BYREF
  __int64 v22; // [rsp+48h] [rbp-41h] BYREF
  __int64 v23; // [rsp+50h] [rbp-39h] BYREF
  __int64 v24; // [rsp+58h] [rbp-31h] BYREF
  __int64 v25; // [rsp+60h] [rbp-29h] BYREF
  __int64 v26; // [rsp+68h] [rbp-21h] BYREF
  __int64 v27; // [rsp+70h] [rbp-19h] BYREF
  __int64 v28; // [rsp+78h] [rbp-11h] BYREF
  struct INativeConfigurationElementCollection *v29; // [rsp+80h] [rbp-9h] BYREF
  struct INativeConfigurationElementCollection *v30; // [rsp+88h] [rbp-1h] BYREF
  struct INativeConfigurationElementCollection *v31; // [rsp+90h] [rbp+7h] BYREF
  struct INativeConfigurationElementCollection *v32; // [rsp+98h] [rbp+Fh] BYREF
  _WORD *v33; // [rsp+A0h] [rbp+17h] BYREF
  wchar_t *String1; // [rsp+A8h] [rbp+1Fh]
  int v35; // [rsp+F8h] [rbp+6Fh] BYREF
  int v36; // [rsp+100h] [rbp+77h] BYREF
  int v37; // [rsp+108h] [rbp+7Fh] BYREF

  v22 = 0;
  v4 = 0;
  v21 = 0;
  v23 = 0;
  v28 = 0;
  v7 = 0;
  v26 = 0;
  v8 = 0;
  v25 = 0;
  v9 = 0;
  v27 = 0;
  v24 = 0;
  v30 = 0;
  v32 = 0;
  v31 = 0;
  v29 = 0;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v35 = 0;
  if ( !a2 )
  {
    v10 = -2147024809;
    goto LABEL_29;
  }
  v11 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(struct IHttpContext *, struct IHttpContext *, struct INativeSectionException **, _QWORD))(*(_QWORD *)a2 + 160LL))(
                                            a2,
                                            a2,
                                            a3,
                                            0);
  v12 = (wchar_t *)(**v11)(v11);
  String1 = v12;
  v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pHttpServer + 56LL))(g_pHttpServer);
  v10 = (**v13)(v13, &IID_INativeConfigurationSystem, &v22);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v22 + 24LL))(
            v22,
            L"system.webServer/validation",
            v12,
            &v23,
            &v21,
            0);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v23 + 72LL))(
              v23,
              L"validateIntegratedModeConfiguration",
              (char *)this + 8,
              0,
              0);
      if ( v10 >= 0 )
      {
        if ( *((_DWORD *)this + 2) )
        {
          v14 = wcscmp_0(String1, L"MACHINE/WEBROOT/APPHOST");
          v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 8LL))(a2);
          v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          if ( v14 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v22 + 24LL))(
                    v22,
                    L"system.web/httpModules",
                    L"MACHINE/WEBROOT",
                    &v26,
                    &v21,
                    0);
            if ( v10 < 0 )
              goto LABEL_28;
            v10 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElementCollection **))(*(_QWORD *)v26 + 40LL))(
                    v26,
                    &v32);
            if ( v10 < 0 )
              goto LABEL_28;
            v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v22 + 24LL))(
                    v22,
                    L"system.web/httpModules",
                    v16,
                    &v25,
                    &v21,
                    0);
            if ( v10 < 0 )
              goto LABEL_28;
            v10 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElementCollection **))(*(_QWORD *)v25 + 40LL))(
                    v25,
                    &v31);
            if ( v10 < 0 )
              goto LABEL_28;
            v10 = CDetectISAPIConfigContext::AreConfigurationCollectionsDifferent(v17, v32, v31, 1, &v35);
            if ( v10 < 0 )
              goto LABEL_28;
            v9 = v35;
          }
          v18 = v22;
          *((_DWORD *)this + 3) = v9;
          v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v18 + 24LL))(
                  v18,
                  L"system.web/identity",
                  v16,
                  &v24,
                  &v21,
                  0);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v24 + 72LL))(
                    v24,
                    L"impersonate",
                    &v36,
                    0,
                    0);
            if ( v10 >= 0 )
            {
              if ( v36 )
              {
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _WORD **, _QWORD, _QWORD))(*(_QWORD *)v24 + 64LL))(
                        v24,
                        L"userName",
                        &v33,
                        0,
                        0);
                if ( v10 < 0 )
                  goto LABEL_28;
                if ( !*v33 )
                  *((_DWORD *)this + 5) = 1;
              }
              if ( v14 )
              {
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v22 + 24LL))(
                        v22,
                        L"system.web/httpHandlers",
                        L"MACHINE/WEBROOT",
                        &v28,
                        &v21,
                        0);
                if ( v10 < 0 )
                  goto LABEL_28;
                v10 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElementCollection **))(*(_QWORD *)v28 + 40LL))(
                        v28,
                        &v30);
                if ( v10 < 0 )
                  goto LABEL_28;
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v22 + 24LL))(
                        v22,
                        L"system.web/httpHandlers",
                        String1,
                        &v27,
                        &v21,
                        0);
                if ( v10 < 0 )
                  goto LABEL_28;
                v10 = (*(__int64 (__fastcall **)(__int64, struct INativeConfigurationElementCollection **))(*(_QWORD *)v27 + 40LL))(
                        v27,
                        &v29);
                if ( v10 < 0 )
                  goto LABEL_28;
                v10 = CDetectISAPIConfigContext::AreConfigurationCollectionsDifferent(v19, v30, v29, 0, &v37);
                if ( v10 < 0 )
                  goto LABEL_28;
                v8 = v37;
              }
              *((_DWORD *)this + 4) = v8;
              v10 = 0;
            }
          }
        }
      }
    }
  }
LABEL_28:
  v7 = v23;
  v4 = v21;
LABEL_29:
  if ( a3 )
  {
    if ( !v4 )
      goto LABEL_34;
    *a3 = v4;
    v4 = 0;
    v21 = 0;
  }
  if ( v4 )
  {
    (*(void (__fastcall **)(struct INativeSectionException *, struct IHttpContext *, struct INativeSectionException **, __int64))(*(_QWORD *)v4 + 16LL))(
      v4,
      a2,
      a3,
      v7);
    v7 = v23;
    v21 = 0;
  }
LABEL_34:
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v23 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v29 + 16LL))(v29);
    v29 = 0;
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElementCollection *))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180002268  mov     [rsp-8+arg_0], rbx
0x18000226d  push    rbp
0x18000226e  push    rsi
0x18000226f  push    rdi
0x180002270  push    r12
0x180002272  push    r13
0x180002274  push    r14
0x180002276  push    r15
0x180002278  lea     rbp, [rsp-27h]
0x18000227d  sub     rsp, 0B0h
0x180002284  xor     r12d, r12d
0x180002287  mov     rdi, rcx
0x18000228a  mov     [rbp+57h+var_98], r12
0x18000228e  mov     ecx, r12d
0x180002291  mov     [rbp+57h+var_A0], rcx
0x180002295  mov     r13, r8
0x180002298  mov     [rbp+57h+var_90], r12
0x18000229c  mov     r15, rdx
0x18000229f  mov     [rbp+57h+var_68], r12
0x1800022a3  mov     r9d, r12d
0x1800022a6  mov     [rbp+57h+var_78], r12
0x1800022aa  mov     r14d, r12d
0x1800022ad  mov     [rbp+57h+var_80], r12
0x1800022b1  mov     esi, r12d
0x1800022b4  mov     [rbp+57h+var_70], r12
0x1800022b8  mov     [rbp+57h+var_88], r12
0x1800022bc  mov     [rbp+57h+var_58], r12
0x1800022c0  mov     [rbp+57h+var_48], r12
0x1800022c4  mov     [rbp+57h+var_50], r12
0x1800022c8  mov     [rbp+57h+var_60], r12
0x1800022cc  mov     [rbp+57h+var_40], r12
0x1800022d0  mov     [rbp+57h+arg_10], r12d
0x1800022d4  mov     [rbp+57h+arg_18], r12d
0x1800022d8  mov     [rbp+57h+arg_8], r12d
0x1800022dc  test    rdx, rdx
0x1800022df  jnz     short loc_1800022EB
0x1800022e1  mov     ebx, 80070057h
0x1800022e6  jmp     loc_180002663
0x1800022eb  mov     rax, [rdx]
0x1800022ee  mov     rcx, r15
0x1800022f1  mov     rax, [rax+0A0h]
0x1800022f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022fd  mov     rcx, rax
0x180002300  mov     rax, [rax]
0x180002303  mov     rax, [rax]
0x180002306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000230b  mov     rcx, cs:?g_pHttpServer@@3PEAVIHttpServer@@EA; IHttpServer * g_pHttpServer
0x180002312  mov     r12, rax
0x180002315  mov     [rbp+57h+String1], rax
0x180002319  mov     rax, [rcx]
0x18000231c  mov     rax, [rax+38h]
0x180002320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002325  mov     rcx, rax
0x180002328  lea     r8, [rbp+57h+var_98]
0x18000232c  lea     rdx, IID_INativeConfigurationSystem
0x180002333  mov     rax, [rax]
0x180002336  mov     rax, [rax]
0x180002339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233e  mov     ebx, eax
0x180002340  test    eax, eax
0x180002342  js      loc_180002658
0x180002348  mov     rcx, [rbp+57h+var_98]
0x18000234c  lea     rdx, [rbp+57h+var_A0]
0x180002350  mov     [rsp+0E0h+var_B8], rsi
0x180002355  lea     r9, [rbp+57h+var_90]
0x180002359  mov     [rsp+0E0h+var_C0], rdx
0x18000235e  mov     r8, r12
0x180002361  lea     rdx, aSystemWebserve; "system.webServer/validation"
0x180002368  mov     rax, [rcx]
0x18000236b  mov     rax, [rax+18h]
0x18000236f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002374  xor     r12d, r12d
0x180002377  mov     ebx, eax
0x180002379  test    eax, eax
0x18000237b  js      loc_18000265B
0x180002381  mov     rcx, [rbp+57h+var_90]
0x180002385  lea     r8, [rdi+8]
0x180002389  xor     r9d, r9d
0x18000238c  mov     [rsp+0E0h+var_C0], rsi
0x180002391  lea     rdx, aValidateintegr; "validateIntegratedModeConfiguration"
0x180002398  mov     rax, [rcx]
0x18000239b  mov     rax, [rax+48h]
0x18000239f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023a4  mov     ebx, eax
0x1800023a6  test    eax, eax
0x1800023a8  js      loc_18000265B
0x1800023ae  cmp     [rdi+8], esi
0x1800023b1  jz      loc_18000265B
0x1800023b7  mov     rcx, [rbp+57h+String1]; String1
0x1800023bb  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800023c2  call    wcscmp_0
0x1800023c7  mov     rcx, [r15]
0x1800023ca  mov     r12d, eax
0x1800023cd  mov     rax, [rcx+8]
0x1800023d1  mov     rcx, r15
0x1800023d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d9  mov     rdx, rax
0x1800023dc  mov     rcx, [rax]
0x1800023df  mov     rax, [rcx+10h]
0x1800023e3  mov     rcx, rdx
0x1800023e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023eb  mov     r15, rax
0x1800023ee  test    r12d, r12d
0x1800023f1  jz      loc_1800024CC
0x1800023f7  mov     rcx, [rbp+57h+var_98]
0x1800023fb  lea     r9, [rbp+57h+var_78]
0x1800023ff  mov     [rsp+0E0h+var_B8], rsi
0x180002404  lea     r8, aMachineWebroot_0; "MACHINE/WEBROOT"
0x18000240b  mov     rdx, [rcx]
0x18000240e  mov     rax, [rdx+18h]
0x180002412  lea     rdx, [rbp+57h+var_A0]
0x180002416  mov     [rsp+0E0h+var_C0], rdx
0x18000241b  lea     rdx, aSystemWebHttpm; "system.web/httpModules"
0x180002422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002427  mov     ebx, eax
0x180002429  test    eax, eax
0x18000242b  js      loc_180002658
0x180002431  mov     rcx, [rbp+57h+var_78]
0x180002435  lea     rdx, [rbp+57h+var_48]
0x180002439  mov     rax, [rcx]
0x18000243c  mov     rax, [rax+28h]
0x180002440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002445  mov     ebx, eax
0x180002447  test    eax, eax
0x180002449  js      loc_180002658
0x18000244f  mov     rcx, [rbp+57h+var_98]
0x180002453  lea     r8, [rbp+57h+var_A0]
0x180002457  mov     [rsp+0E0h+var_B8], rsi
0x18000245c  lea     r9, [rbp+57h+var_80]
0x180002460  mov     [rsp+0E0h+var_C0], r8
0x180002465  lea     rdx, aSystemWebHttpm; "system.web/httpModules"
0x18000246c  mov     r8, r15
0x18000246f  mov     rax, [rcx]
0x180002472  mov     rax, [rax+18h]
0x180002476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000247b  mov     ebx, eax
0x18000247d  test    eax, eax
0x18000247f  js      loc_180002658
0x180002485  mov     rcx, [rbp+57h+var_80]
0x180002489  lea     rdx, [rbp+57h+var_50]
0x18000248d  mov     rax, [rcx]
0x180002490  mov     rax, [rax+28h]
0x180002494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002499  mov     ebx, eax
0x18000249b  test    eax, eax
0x18000249d  js      loc_180002658
0x1800024a3  mov     r8, [rbp+57h+var_50]; struct INativeConfigurationElementCollection *
0x1800024a7  lea     rax, [rbp+57h+arg_8]
0x1800024ab  mov     rdx, [rbp+57h+var_48]; struct INativeConfigurationElementCollection *
0x1800024af  mov     r9d, 1; int
0x1800024b5  mov     [rsp+0E0h+var_C0], rax; int *
0x1800024ba  call    ?AreConfigurationCollectionsDifferent@CDetectISAPIConfigContext@@AEAAJPEAVINativeConfigurationElementCollection@@0HPEAH@Z; CDetectISAPIConfigContext::AreConfigurationCollectionsDifferent(INativeConfigurationElementCollection *,INativeConfigurationElementCollection *,int,int *)
0x1800024bf  mov     ebx, eax
0x1800024c1  test    eax, eax
0x1800024c3  js      loc_180002658
0x1800024c9  mov     esi, [rbp+57h+arg_8]
0x1800024cc  mov     rcx, [rbp+57h+var_98]
0x1800024d0  lea     rdx, [rbp+57h+var_A0]
0x1800024d4  mov     [rdi+0Ch], esi
0x1800024d7  lea     r9, [rbp+57h+var_88]
0x1800024db  xor     esi, esi
0x1800024dd  mov     r8, r15
0x1800024e0  mov     [rsp+0E0h+var_B8], rsi
0x1800024e5  mov     rax, [rcx]
0x1800024e8  mov     [rsp+0E0h+var_C0], rdx
0x1800024ed  lea     rdx, aSystemWebIdent; "system.web/identity"
0x1800024f4  mov     rax, [rax+18h]
0x1800024f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024fd  mov     ebx, eax
0x1800024ff  test    eax, eax
0x180002501  js      loc_180002658
0x180002507  mov     rcx, [rbp+57h+var_88]
0x18000250b  lea     r8, [rbp+57h+arg_10]
0x18000250f  xor     r9d, r9d
0x180002512  mov     [rsp+0E0h+var_C0], rsi
0x180002517  lea     rdx, aImpersonate; "impersonate"
0x18000251e  mov     rax, [rcx]
0x180002521  mov     rax, [rax+48h]
0x180002525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000252a  mov     ebx, eax
0x18000252c  test    eax, eax
0x18000252e  js      loc_180002658
0x180002534  cmp     [rbp+57h+arg_10], esi
0x180002537  jz      short loc_180002576
0x180002539  mov     rcx, [rbp+57h+var_88]
0x18000253d  lea     r8, [rbp+57h+var_40]
0x180002541  xor     r9d, r9d
0x180002544  mov     [rsp+0E0h+var_C0], rsi
0x180002549  lea     rdx, aUsername; "userName"
0x180002550  mov     rax, [rcx]
0x180002553  mov     rax, [rax+40h]
0x180002557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000255c  mov     ebx, eax
0x18000255e  test    eax, eax
0x180002560  js      loc_180002658
0x180002566  mov     rax, [rbp+57h+var_40]
0x18000256a  cmp     [rax], si
0x18000256d  jnz     short loc_180002576
0x18000256f  mov     dword ptr [rdi+14h], 1
0x180002576  test    r12d, r12d
0x180002579  jz      loc_18000264C
0x18000257f  mov     rcx, [rbp+57h+var_98]
0x180002583  lea     rdx, [rbp+57h+var_A0]
0x180002587  xor     r12d, r12d
0x18000258a  lea     r9, [rbp+57h+var_68]
0x18000258e  mov     [rsp+0E0h+var_B8], r12
0x180002593  lea     r8, aMachineWebroot_0; "MACHINE/WEBROOT"
0x18000259a  mov     [rsp+0E0h+var_C0], rdx
0x18000259f  lea     rdx, aSystemWebHttph; "system.web/httpHandlers"
0x1800025a6  mov     rax, [rcx]
0x1800025a9  mov     rax, [rax+18h]
0x1800025ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b2  mov     ebx, eax
0x1800025b4  test    eax, eax
0x1800025b6  js      loc_18000265B
0x1800025bc  mov     rcx, [rbp+57h+var_68]
0x1800025c0  lea     rdx, [rbp+57h+var_58]
0x1800025c4  mov     rax, [rcx]
0x1800025c7  mov     rax, [rax+28h]
0x1800025cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025d0  mov     ebx, eax
0x1800025d2  test    eax, eax
0x1800025d4  js      loc_18000265B
0x1800025da  mov     rcx, [rbp+57h+var_98]
0x1800025de  lea     r8, [rbp+57h+var_A0]
0x1800025e2  mov     [rsp+0E0h+var_B8], r12
0x1800025e7  lea     r9, [rbp+57h+var_70]
0x1800025eb  mov     [rsp+0E0h+var_C0], r8
0x1800025f0  lea     rdx, aSystemWebHttph; "system.web/httpHandlers"
0x1800025f7  mov     r8, [rbp+57h+String1]
0x1800025fb  mov     rax, [rcx]
0x1800025fe  mov     rax, [rax+18h]
0x180002602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002607  mov     ebx, eax
0x180002609  test    eax, eax
0x18000260b  js      short loc_18000265B
0x18000260d  mov     rcx, [rbp+57h+var_70]
0x180002611  lea     rdx, [rbp+57h+var_60]
0x180002615  mov     rax, [rcx]
0x180002618  mov     rax, [rax+28h]
0x18000261c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002621  mov     ebx, eax
0x180002623  test    eax, eax
0x180002625  js      short loc_18000265B
0x180002627  mov     r8, [rbp+57h+var_60]; struct INativeConfigurationElementCollection *
0x18000262b  lea     rax, [rbp+57h+arg_18]
0x18000262f  mov     rdx, [rbp+57h+var_58]; struct INativeConfigurationElementCollection *
0x180002633  xor     r9d, r9d; int
0x180002636  mov     [rsp+0E0h+var_C0], rax; int *
0x18000263b  call    ?AreConfigurationCollectionsDifferent@CDetectISAPIConfigContext@@AEAAJPEAVINativeConfigurationElementCollection@@0HPEAH@Z; CDetectISAPIConfigContext::AreConfigurationCollectionsDifferent(INativeConfigurationElementCollection *,INativeConfigurationElementCollection *,int,int *)
0x180002640  mov     ebx, eax
0x180002642  test    eax, eax
0x180002644  js      short loc_18000265B
0x180002646  mov     r14d, [rbp+57h+arg_18]
0x18000264a  jmp     short loc_18000264F
0x18000264c  xor     r12d, r12d
0x18000264f  mov     [rdi+10h], r14d
0x180002653  mov     ebx, r12d
0x180002656  jmp     short loc_18000265B
0x180002658  xor     r12d, r12d
0x18000265b  mov     r9, [rbp+57h+var_90]
0x18000265f  mov     rcx, [rbp+57h+var_A0]
0x180002663  test    r13, r13
0x180002666  jz      short loc_180002678
0x180002668  test    rcx, rcx
0x18000266b  jz      short loc_180002691
0x18000266d  mov     [r13+0], rcx
0x180002671  mov     rcx, r12
0x180002674  mov     [rbp+57h+var_A0], rcx
0x180002678  test    rcx, rcx
0x18000267b  jz      short loc_180002691
0x18000267d  mov     rax, [rcx]
0x180002680  mov     rax, [rax+10h]
0x180002684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002689  mov     r9, [rbp+57h+var_90]
0x18000268d  mov     [rbp+57h+var_A0], r12
0x180002691  test    r9, r9
0x180002694  jz      short loc_1800026A9
0x180002696  mov     rax, [r9]
0x180002699  mov     rcx, r9
0x18000269c  mov     rax, [rax+10h]
0x1800026a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026a5  mov     [rbp+57h+var_90], r12
0x1800026a9  mov     rcx, [rbp+57h+var_80]
0x1800026ad  test    rcx, rcx
0x1800026b0  jz      short loc_1800026C2
0x1800026b2  mov     rax, [rcx]
0x1800026b5  mov     rax, [rax+10h]
0x1800026b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026be  mov     [rbp+57h+var_80], r12
0x1800026c2  mov     rcx, [rbp+57h+var_78]
0x1800026c6  test    rcx, rcx
0x1800026c9  jz      short loc_1800026DB
0x1800026cb  mov     rax, [rcx]
0x1800026ce  mov     rax, [rax+10h]
0x1800026d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026d7  mov     [rbp+57h+var_78], r12
0x1800026db  mov     rcx, [rbp+57h+var_70]
0x1800026df  test    rcx, rcx
0x1800026e2  jz      short loc_1800026F4
  ... truncated ...
```
