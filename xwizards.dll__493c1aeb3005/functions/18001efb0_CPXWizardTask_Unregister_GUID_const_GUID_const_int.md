# CPXWizardTask::Unregister(_GUID * const,_GUID * const,int)

- ea: `0x18001efb0`
- end: `0x18001f54a`
- name: `?Unregister@CPXWizardTask@@AEAAJQEAU_GUID@@0H@Z`
- size: `1434`
- prototype: `int(CPXWizardTask *__hidden this, struct _GUID *const, struct _GUID *const, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001f550`
- `0x18001f570`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000bd98`
- `0x18000df3c`
- `0x18000e098`
- `0x18001efb0`
- `0x180028874`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f0c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f22d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f373`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f0c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f22d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001f373`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f2cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f2cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f413`

## pseudocode

```c
__int64 __fastcall CPXWizardTask::Unregister(
        CPXWizardTask *this,
        struct _GUID *const a2,
        struct _GUID *const a3,
        unsigned int a4)
{
  const IID *v4; // rsi
  PVOID *v8; // rcx
  __int64 result; // rax
  struct IMultiObjectElevationFactory **v10; // rdx
  _QWORD *v11; // r15
  HWND v12; // rcx
  _QWORD *v13; // r12
  int v14; // ebx
  HRESULT v15; // eax
  int v16; // ebx
  struct IMultiObjectElevationFactory **v17; // rdx
  HWND v18; // rcx
  HRESULT v19; // eax
  int v20; // eax
  HRESULT v21; // eax
  int v22; // eax
  int v23; // edi
  GUID *v24; // rdx
  PVOID *v25; // rcx
  __int64 v26; // rdx
  struct IPXWizardPage *v27; // [rsp+30h] [rbp-30h] BYREF
  __int64 v28; // [rsp+38h] [rbp-28h] BYREF
  LPVOID v29; // [rsp+40h] [rbp-20h] BYREF
  __int64 v30; // [rsp+48h] [rbp-18h] BYREF
  char *v31; // [rsp+50h] [rbp-10h]
  LPVOID ppv; // [rsp+A8h] [rbp+48h] BYREF
  IID *rclsid; // [rsp+B0h] [rbp+50h] BYREF

  v4 = a2;
  if ( a2 && *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_NULL.Data4 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v4 = 0;
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
      WPP_SF_d(v8[2], 13, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, 2147500035LL);
    return 2147500035LL;
  }
  v10 = (struct IMultiObjectElevationFactory **)*((_QWORD *)this + 13);
  v11 = (_QWORD *)((char *)this + 80);
  v12 = (HWND)*((_QWORD *)this + 8);
  v13 = (_QWORD *)((char *)this + 72);
  v31 = (char *)this + 80;
  v14 = HrEnsureComponentRegistrationModulesLoaded(
          v12,
          v10,
          (struct IPXWizardRegistration **)this + 9,
          (struct IPXWizardFactoryRegistration **)this + 10);
  if ( v14 < 0 )
    goto LABEL_74;
  ppv = 0;
  if ( !v4 )
  {
    v17 = (struct IMultiObjectElevationFactory **)*((_QWORD *)this + 13);
    v18 = (HWND)*((_QWORD *)this + 8);
    v27 = 0;
    v14 = CPXWizardPage::HrCreateInstance(v18, v17, &v27);
    if ( v14 < 0 )
      goto LABEL_71;
    v28 = 0;
    v30 = 0;
    v14 = (*(__int64 (__fastcall **)(struct IPXWizardPage *, struct _GUID *const, _QWORD, __int64 *))(*(_QWORD *)v27 + 56LL))(
            v27,
            a3,
            0,
            &v28);
    if ( v14 >= 0 )
    {
      rclsid = 0;
      do
      {
        v14 = (*(__int64 (__fastcall **)(__int64, __int64, IID **))(*(_QWORD *)v28 + 24LL))(v28, 1, &rclsid);
        if ( v14 )
          break;
        v19 = CoCreateInstance(rclsid, 0, 0x401u, &IID_IXWizardTaskEvent, &ppv);
        if ( v19 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
              (unsigned int)v19);
          v14 = 0;
        }
        else
        {
          v20 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *const))(*(_QWORD *)ppv + 72LL))(ppv, a3);
          v14 = v20;
          if ( v20 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_ddD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
                rclsid->Data1,
                a3->Data1,
                v20);
            v14 = -2147024891;
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        CoTaskMemFree(rclsid);
      }
      while ( !v14 );
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v11 = v31;
      if ( v14 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(struct IPXWizardPage *, struct _GUID *const, _QWORD, __int64 *))(*(_QWORD *)v27 + 48LL))(
                v27,
                a3,
                0,
                &v30);
        if ( v14 >= 0 )
        {
          rclsid = 0;
          do
          {
            v14 = (*(__int64 (__fastcall **)(__int64, __int64, IID **))(*(_QWORD *)v30 + 24LL))(v30, 1, &rclsid);
            if ( v14 )
              break;
            v29 = 0;
            v21 = CoCreateInstance(rclsid, 0, 0x401u, &IID_IXWizardPageEvent, &v29);
            if ( v21 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  19,
                  &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
                  (unsigned int)v21);
              v14 = 0;
            }
            else
            {
              v22 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *const))(*(_QWORD *)v29 + 72LL))(v29, a3);
              v14 = v22;
              if ( v22 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_ddD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    18,
                    &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
                    rclsid->Data1,
                    a3->Data1,
                    v22);
                v14 = -2147024891;
              }
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
            }
            CoTaskMemFree(rclsid);
          }
          while ( !v14 );
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          v11 = v31;
        }
      }
    }
    (*(void (__fastcall **)(struct IPXWizardPage *))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v14 < 0 )
    {
LABEL_71:
      v25 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return (unsigned int)v14;
      v26 = 20;
      goto LABEL_78;
    }
LABEL_61:
    v23 = IsFactoryRegisteredWizardComponent(a3);
    v24 = &GUID_NULL;
    if ( v4 )
      v24 = (GUID *)v4;
    v14 = (*(__int64 (__fastcall **)(_QWORD, GUID *, struct _GUID *const, _QWORD))(*(_QWORD *)*v13 + 64LL))(
            *v13,
            v24,
            a3,
            a4);
    if ( v14 >= 0 && !v4 )
    {
      if ( v23 )
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *const))(*(_QWORD *)*v11 + 48LL))(*v11, a3);
        if ( v14 < 0 )
        {
          v25 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
              (unsigned int)v14);
            v25 = (PVOID *)WPP_GLOBAL_Control;
          }
          v14 = 1;
          goto LABEL_75;
        }
      }
    }
LABEL_74:
    v25 = (PVOID *)WPP_GLOBAL_Control;
LABEL_75:
    if ( v25 == &WPP_GLOBAL_Control || (*((_BYTE *)v25 + 28) & 0x10) == 0 )
      return (unsigned int)v14;
    v26 = 22;
LABEL_78:
    WPP_SF_d(v25[2], v26, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, (unsigned int)v14);
    return (unsigned int)v14;
  }
  v15 = CoCreateInstance(v4, 0, 0x401u, &IID_IXWizardTaskEvent, &ppv);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
        (unsigned int)v15);
    goto LABEL_61;
  }
  v16 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *const))(*(_QWORD *)ppv + 72LL))(ppv, a3);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( !v16 )
    goto LABEL_61;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_ddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
      v4->Data1,
      a3->Data1,
      v16);
  result = 2147942405LL;
  if ( v16 < 0 )
    return (unsigned int)v16;
  return result;
}

```

## disassembly

```asm
0x18001efb0  mov     [rsp-38h+arg_0], rbx
0x18001efb5  push    rbp
0x18001efb6  push    rsi
0x18001efb7  push    rdi
0x18001efb8  push    r12
0x18001efba  push    r13
0x18001efbc  push    r14
0x18001efbe  push    r15
0x18001efc0  mov     rbp, rsp
0x18001efc3  sub     rsp, 60h
0x18001efc7  mov     rsi, rdx
0x18001efca  mov     r13d, r9d
0x18001efcd  lea     rdx, WPP_GLOBAL_Control
0x18001efd4  mov     r14, r8
0x18001efd7  mov     rdi, rcx
0x18001efda  test    rsi, rsi
0x18001efdd  jz      short loc_18001F031
0x18001efdf  mov     rax, [rsi]
0x18001efe2  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001efe9  jnz     short loc_18001F031
0x18001efeb  mov     rax, [rsi+8]
0x18001efef  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001eff6  jnz     short loc_18001F031
0x18001eff8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001efff  cmp     rcx, rdx
0x18001f002  jz      short loc_18001F02D
0x18001f004  test    byte ptr [rcx+1Ch], 10h
0x18001f008  jz      short loc_18001F02D
0x18001f00a  mov     rcx, [rcx+10h]
0x18001f00e  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001f015  mov     edx, 0Ch
0x18001f01a  call    WPP_SF_
0x18001f01f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f026  lea     rdx, WPP_GLOBAL_Control
0x18001f02d  xor     esi, esi
0x18001f02f  jmp     short loc_18001F038
0x18001f031  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f038  test    r14, r14
0x18001f03b  jnz     short loc_18001F06C
0x18001f03d  cmp     rcx, rdx
0x18001f040  jz      short loc_18001F062
0x18001f042  test    byte ptr [rcx+1Ch], 8
0x18001f046  jz      short loc_18001F062
0x18001f048  mov     rcx, [rcx+10h]
0x18001f04c  lea     edx, [r14+0Dh]
0x18001f050  mov     r9d, 80004003h
0x18001f056  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001f05d  call    WPP_SF_d
0x18001f062  mov     eax, 80004003h
0x18001f067  jmp     loc_18001F532
0x18001f06c  mov     rdx, [rdi+68h]; struct IMultiObjectElevationFactory **
0x18001f070  lea     r15, [rdi+50h]
0x18001f074  mov     rcx, [rdi+40h]; HWND
0x18001f078  lea     r12, [rdi+48h]
0x18001f07c  mov     r9, r15; struct IPXWizardFactoryRegistration **
0x18001f07f  mov     [rbp+var_10], r15
0x18001f083  mov     r8, r12; struct IPXWizardRegistration **
0x18001f086  call    ?HrEnsureComponentRegistrationModulesLoaded@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@PEAPEAUIPXWizardRegistration@@PEAPEAUIPXWizardFactoryRegistration@@@Z; HrEnsureComponentRegistrationModulesLoaded(HWND__ *,IMultiObjectElevationFactory * *,IPXWizardRegistration * *,IPXWizardFactoryRegistration * *)
0x18001f08b  mov     ebx, eax
0x18001f08d  test    eax, eax
0x18001f08f  js      loc_18001F4FF
0x18001f095  mov     [rbp+arg_8], 0
0x18001f09d  test    rsi, rsi
0x18001f0a0  jz      loc_18001F181
0x18001f0a6  lea     rax, [rbp+arg_8]
0x18001f0aa  xor     edx, edx; pUnkOuter
0x18001f0ac  lea     r9, IID_IXWizardTaskEvent; riid
0x18001f0b3  mov     [rsp+60h+ppv], rax; ppv
0x18001f0b8  mov     r8d, 401h; dwClsContext
0x18001f0be  mov     rcx, rsi; rclsid
0x18001f0c1  call    cs:__imp_CoCreateInstance
0x18001f0c7  test    eax, eax
0x18001f0c9  js      short loc_18001F143
0x18001f0cb  mov     rcx, [rbp+arg_8]
0x18001f0cf  mov     rdx, r14
0x18001f0d2  mov     rax, [rcx]
0x18001f0d5  mov     rax, [rax+48h]
0x18001f0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0de  mov     rcx, [rbp+arg_8]
0x18001f0e2  mov     ebx, eax
0x18001f0e4  mov     rdx, [rcx]
0x18001f0e7  mov     rax, [rdx+10h]
0x18001f0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0f0  test    ebx, ebx
0x18001f0f2  jz      loc_18001F44D
0x18001f0f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0ff  lea     rdx, WPP_GLOBAL_Control
0x18001f106  cmp     rcx, rdx
0x18001f109  jz      short loc_18001F134
0x18001f10b  test    byte ptr [rcx+1Ch], 8
0x18001f10f  jz      short loc_18001F134
0x18001f111  mov     eax, [r14]
0x18001f114  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001f11b  mov     r9d, [rsi]
0x18001f11e  mov     edx, 0Fh
0x18001f123  mov     rcx, [rcx+10h]
0x18001f127  mov     [rsp+60h+var_38], ebx
0x18001f12b  mov     dword ptr [rsp+60h+ppv], eax
0x18001f12f  call    WPP_SF_ddD
0x18001f134  test    ebx, ebx
0x18001f136  mov     eax, 80070005h
0x18001f13b  cmovs   eax, ebx
0x18001f13e  jmp     loc_18001F532
0x18001f143  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f14a  lea     rdx, WPP_GLOBAL_Control
0x18001f151  cmp     rcx, rdx
0x18001f154  jz      loc_18001F44D
0x18001f15a  test    byte ptr [rcx+1Ch], 10h
0x18001f15e  jz      loc_18001F44D
0x18001f164  mov     rcx, [rcx+10h]
0x18001f168  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001f16f  mov     edx, 0Eh
0x18001f174  mov     r9d, eax
0x18001f177  call    WPP_SF_d
0x18001f17c  jmp     loc_18001F44D
0x18001f181  mov     rdx, [rdi+68h]; struct IMultiObjectElevationFactory **
0x18001f185  lea     r8, [rbp+var_30]; struct IPXWizardPage **
0x18001f189  mov     rcx, [rdi+40h]; HWND
0x18001f18d  mov     [rbp+var_30], 0
0x18001f195  call    ?HrCreateInstance@CPXWizardPage@@SAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@PEAPEAUIPXWizardPage@@@Z; CPXWizardPage::HrCreateInstance(HWND__ *,IMultiObjectElevationFactory * *,IPXWizardPage * *)
0x18001f19a  mov     ebx, eax
0x18001f19c  test    eax, eax
0x18001f19e  js      loc_18001F4DF
0x18001f1a4  mov     rcx, [rbp+var_30]
0x18001f1a8  lea     r9, [rbp+var_28]
0x18001f1ac  mov     [rbp+var_28], 0
0x18001f1b4  xor     r8d, r8d
0x18001f1b7  mov     [rbp+var_18], 0
0x18001f1bf  mov     rdx, r14
0x18001f1c2  mov     rax, [rcx]
0x18001f1c5  mov     rax, [rax+38h]
0x18001f1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1ce  mov     ebx, eax
0x18001f1d0  test    eax, eax
0x18001f1d2  js      loc_18001F435
0x18001f1d8  mov     [rbp+rclsid], 0
0x18001f1e0  lea     r15, WPP_GLOBAL_Control
0x18001f1e7  mov     edi, 80070005h
0x18001f1ec  mov     rcx, [rbp+var_28]
0x18001f1f0  lea     r8, [rbp+rclsid]
0x18001f1f4  xor     r9d, r9d
0x18001f1f7  mov     rax, [rcx]
0x18001f1fa  lea     edx, [r9+1]
0x18001f1fe  mov     rax, [rax+18h]
0x18001f202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f207  mov     ebx, eax
0x18001f209  test    eax, eax
0x18001f20b  jnz     loc_18001F2DB
0x18001f211  mov     rcx, [rbp+rclsid]; rclsid
0x18001f215  lea     rax, [rbp+arg_8]
0x18001f219  lea     r9, IID_IXWizardTaskEvent; riid
0x18001f220  mov     [rsp+60h+ppv], rax; ppv
0x18001f225  xor     edx, edx; pUnkOuter
0x18001f227  mov     r8d, 401h; dwClsContext
0x18001f22d  call    cs:__imp_CoCreateInstance
0x18001f233  test    eax, eax
0x18001f235  js      short loc_18001F29D
0x18001f237  mov     rcx, [rbp+arg_8]
0x18001f23b  mov     rdx, r14
0x18001f23e  mov     rax, [rcx]
0x18001f241  mov     rax, [rax+48h]
0x18001f245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f24a  mov     ebx, eax
0x18001f24c  test    eax, eax
0x18001f24e  jz      short loc_18001F28B
0x18001f250  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f257  cmp     rcx, r15
0x18001f25a  jz      short loc_18001F289
0x18001f25c  test    byte ptr [rcx+1Ch], 8
0x18001f260  jz      short loc_18001F289
0x18001f262  mov     r9, [rbp+rclsid]
0x18001f266  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001f26d  mov     rcx, [rcx+10h]
0x18001f271  mov     edx, 10h
0x18001f276  mov     [rsp+60h+var_38], eax
0x18001f27a  mov     eax, [r14]
0x18001f27d  mov     r9d, [r9]
0x18001f280  mov     dword ptr [rsp+60h+ppv], eax
0x18001f284  call    WPP_SF_ddD
0x18001f289  mov     ebx, edi
0x18001f28b  mov     rcx, [rbp+arg_8]
0x18001f28f  mov     rax, [rcx]
0x18001f292  mov     rax, [rax+10h]
0x18001f296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f29b  jmp     short loc_18001F2C9
0x18001f29d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2a4  cmp     rcx, r15
0x18001f2a7  jz      short loc_18001F2C7
0x18001f2a9  test    byte ptr [rcx+1Ch], 10h
0x18001f2ad  jz      short loc_18001F2C7
0x18001f2af  mov     rcx, [rcx+10h]
0x18001f2b3  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001f2ba  mov     edx, 11h
0x18001f2bf  mov     r9d, eax
0x18001f2c2  call    WPP_SF_d
0x18001f2c7  xor     ebx, ebx
0x18001f2c9  mov     rcx, [rbp+rclsid]; pv
0x18001f2cd  call    cs:__imp_CoTaskMemFree
0x18001f2d3  test    ebx, ebx
0x18001f2d5  jz      loc_18001F1EC
0x18001f2db  mov     rcx, [rbp+var_28]
0x18001f2df  mov     rax, [rcx]
0x18001f2e2  mov     rax, [rax+10h]
0x18001f2e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2eb  mov     r15, [rbp+var_10]
0x18001f2ef  test    ebx, ebx
0x18001f2f1  js      loc_18001F435
0x18001f2f7  mov     rcx, [rbp+var_30]
0x18001f2fb  lea     r9, [rbp+var_18]
0x18001f2ff  xor     r8d, r8d
0x18001f302  mov     rdx, r14
0x18001f305  mov     rax, [rcx]
0x18001f308  mov     rax, [rax+30h]
0x18001f30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f311  mov     ebx, eax
0x18001f313  test    eax, eax
0x18001f315  js      loc_18001F435
0x18001f31b  mov     [rbp+rclsid], 0
0x18001f323  lea     r15, WPP_GLOBAL_Control
0x18001f32a  mov     rcx, [rbp+var_18]
0x18001f32e  lea     r8, [rbp+rclsid]
0x18001f332  xor     r9d, r9d
0x18001f335  mov     rax, [rcx]
0x18001f338  lea     edx, [r9+1]
0x18001f33c  mov     rax, [rax+18h]
0x18001f340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f345  mov     ebx, eax
0x18001f347  test    eax, eax
0x18001f349  jnz     loc_18001F421
0x18001f34f  mov     rcx, [rbp+rclsid]; rclsid
0x18001f353  lea     rax, [rbp+var_20]
0x18001f357  lea     r9, IID_IXWizardPageEvent; riid
0x18001f35e  mov     [rsp+60h+ppv], rax; ppv
0x18001f363  xor     edx, edx; pUnkOuter
0x18001f365  mov     [rbp+var_20], 0
0x18001f36d  mov     r8d, 401h; dwClsContext
0x18001f373  call    cs:__imp_CoCreateInstance
0x18001f379  test    eax, eax
0x18001f37b  js      short loc_18001F3E3
0x18001f37d  mov     rcx, [rbp+var_20]
0x18001f381  mov     rdx, r14
0x18001f384  mov     rax, [rcx]
0x18001f387  mov     rax, [rax+48h]
0x18001f38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f390  mov     ebx, eax
0x18001f392  test    eax, eax
0x18001f394  jz      short loc_18001F3D1
0x18001f396  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f39d  cmp     rcx, r15
0x18001f3a0  jz      short loc_18001F3CF
0x18001f3a2  test    byte ptr [rcx+1Ch], 8
0x18001f3a6  jz      short loc_18001F3CF
0x18001f3a8  mov     r9, [rbp+rclsid]
0x18001f3ac  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001f3b3  mov     rcx, [rcx+10h]
0x18001f3b7  mov     edx, 12h
0x18001f3bc  mov     [rsp+60h+var_38], eax
0x18001f3c0  mov     eax, [r14]
0x18001f3c3  mov     r9d, [r9]
0x18001f3c6  mov     dword ptr [rsp+60h+ppv], eax
0x18001f3ca  call    WPP_SF_ddD
0x18001f3cf  mov     ebx, edi
0x18001f3d1  mov     rcx, [rbp+var_20]
0x18001f3d5  mov     rax, [rcx]
0x18001f3d8  mov     rax, [rax+10h]
0x18001f3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3e1  jmp     short loc_18001F40F
0x18001f3e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f3ea  cmp     rcx, r15
0x18001f3ed  jz      short loc_18001F40D
0x18001f3ef  test    byte ptr [rcx+1Ch], 10h
0x18001f3f3  jz      short loc_18001F40D
0x18001f3f5  mov     rcx, [rcx+10h]
0x18001f3f9  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001f400  mov     edx, 13h
0x18001f405  mov     r9d, eax
0x18001f408  call    WPP_SF_d
0x18001f40d  xor     ebx, ebx
0x18001f40f  mov     rcx, [rbp+rclsid]; pv
0x18001f413  call    cs:__imp_CoTaskMemFree
0x18001f419  test    ebx, ebx
0x18001f41b  jz      loc_18001F32A
0x18001f421  mov     rcx, [rbp+var_18]
0x18001f425  mov     rax, [rcx]
0x18001f428  mov     rax, [rax+10h]
0x18001f42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f431  mov     r15, [rbp+var_10]
0x18001f435  mov     rcx, [rbp+var_30]
0x18001f439  mov     rax, [rcx]
0x18001f43c  mov     rax, [rax+10h]
0x18001f440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f445  test    ebx, ebx
0x18001f447  js      loc_18001F4DF
0x18001f44d  mov     rcx, r14; struct _GUID *
0x18001f450  call    ?IsFactoryRegisteredWizardComponent@@YAHPEBU_GUID@@@Z; IsFactoryRegisteredWizardComponent(_GUID const *)
0x18001f455  mov     rcx, [r12]
0x18001f459  mov     edi, eax
0x18001f45b  test    rsi, rsi
0x18001f45e  mov     r9d, r13d
0x18001f461  mov     r8, r14
  ... truncated ...
```
