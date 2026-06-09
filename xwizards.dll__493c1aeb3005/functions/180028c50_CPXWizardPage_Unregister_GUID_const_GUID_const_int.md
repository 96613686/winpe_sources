# CPXWizardPage::Unregister(_GUID * const,_GUID * const,int)

- ea: `0x180028c50`
- end: `0x180029070`
- name: `?Unregister@CPXWizardPage@@AEAAJQEAU_GUID@@0H@Z`
- size: `1056`
- prototype: `int(CPXWizardPage *__hidden this, struct _GUID *const, struct _GUID *const, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180029080`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000bd98`
- `0x18000df3c`
- `0x18000e098`
- `0x180028c50`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028d60`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028ea8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028d60`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028ea8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028f48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028f48`

## pseudocode

```c
__int64 __fastcall CPXWizardPage::Unregister(CPXWizardPage *this, struct _GUID *const a2, struct _GUID *const a3)
{
  const IID *v3; // rdi
  PVOID *v6; // rcx
  __int64 result; // rax
  struct IMultiObjectElevationFactory **v8; // rdx
  _QWORD *v9; // r15
  HWND v10; // rcx
  _QWORD *v11; // r12
  int v12; // ebx
  HRESULT Instance; // eax
  int v14; // ebx
  __int64 v15; // rax
  HRESULT v16; // eax
  int v17; // eax
  int v18; // esi
  GUID *v19; // rdx
  PVOID *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // [rsp+30h] [rbp-10h] BYREF
  char *v23; // [rsp+38h] [rbp-8h]
  IID *rclsid; // [rsp+78h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+40h] BYREF

  v3 = a2;
  if ( a2 && *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_NULL.Data4 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = 0;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_d(v6[2], 11, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids, 2147500035LL);
    return 2147500035LL;
  }
  v8 = (struct IMultiObjectElevationFactory **)*((_QWORD *)this + 11);
  v9 = (_QWORD *)((char *)this + 80);
  v10 = (HWND)*((_QWORD *)this + 8);
  v11 = (_QWORD *)((char *)this + 72);
  v23 = (char *)this + 80;
  v12 = HrEnsureComponentRegistrationModulesLoaded(
          v10,
          v8,
          (struct IPXWizardRegistration **)this + 9,
          (struct IPXWizardFactoryRegistration **)this + 10);
  if ( v12 < 0 )
    goto LABEL_56;
  if ( !v3 )
  {
    v15 = *(_QWORD *)this;
    v22 = 0;
    v12 = (*(__int64 (__fastcall **)(CPXWizardPage *, struct _GUID *const, _QWORD, __int64 *))(v15 + 48))(
            this,
            a3,
            0,
            &v22);
    if ( v12 < 0 )
      goto LABEL_53;
    rclsid = 0;
    do
    {
      v12 = (*(__int64 (__fastcall **)(__int64, __int64, IID **))(*(_QWORD *)v22 + 24LL))(v22, 1, &rclsid);
      if ( v12 )
        break;
      ppv = 0;
      v16 = CoCreateInstance(rclsid, 0, 0x401u, &IID_IXWizardPageEvent, &ppv);
      if ( v16 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids,
            (unsigned int)v16);
        v12 = 0;
      }
      else
      {
        v17 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *const))(*(_QWORD *)ppv + 72LL))(ppv, a3);
        v12 = v17;
        if ( v17 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_ddD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids,
              rclsid->Data1,
              a3->Data1,
              v17);
          v12 = -2147024891;
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      CoTaskMemFree(rclsid);
    }
    while ( !v12 );
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v9 = v23;
    if ( v12 < 0 )
    {
LABEL_53:
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return (unsigned int)v12;
      v21 = 16;
      goto LABEL_60;
    }
LABEL_43:
    v18 = IsFactoryRegisteredWizardComponent(a3);
    v19 = &GUID_NULL;
    if ( v3 )
      v19 = (GUID *)v3;
    v12 = (*(__int64 (__fastcall **)(_QWORD, GUID *, struct _GUID *const, _QWORD))(*(_QWORD *)*v11 + 56LL))(
            *v11,
            v19,
            a3,
            0);
    if ( v12 >= 0 && !v3 )
    {
      if ( v18 )
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *const))(*(_QWORD *)*v9 + 48LL))(*v9, a3);
        if ( v12 < 0 )
        {
          v20 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids,
              (unsigned int)v12);
            v20 = (PVOID *)WPP_GLOBAL_Control;
          }
          v12 = 1;
          goto LABEL_57;
        }
      }
    }
LABEL_56:
    v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_57:
    if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 0x10) == 0 )
      return (unsigned int)v12;
    v21 = 18;
LABEL_60:
    WPP_SF_d(v20[2], v21, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids, (unsigned int)v12);
    return (unsigned int)v12;
  }
  rclsid = 0;
  Instance = CoCreateInstance(v3, 0, 0x401u, &IID_IXWizardPageEvent, (LPVOID *)&rclsid);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids,
        (unsigned int)Instance);
    goto LABEL_43;
  }
  v14 = (*(__int64 (__fastcall **)(IID *, struct _GUID *const))(*(_QWORD *)&rclsid->Data1 + 72LL))(rclsid, a3);
  (*(void (__fastcall **)(IID *))(*(_QWORD *)&rclsid->Data1 + 16LL))(rclsid);
  if ( !v14 )
    goto LABEL_43;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_ddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids,
      v3->Data1,
      a3->Data1,
      v14);
  result = 2147942405LL;
  if ( v14 < 0 )
    return (unsigned int)v14;
  return result;
}

```

## disassembly

```asm
0x180028c50  mov     [rsp-28h+arg_0], rbx
0x180028c55  mov     [rsp-28h+arg_18], rsi
0x180028c5a  push    rbp
0x180028c5b  push    rdi
0x180028c5c  push    r12
0x180028c5e  push    r14
0x180028c60  push    r15
0x180028c62  mov     rbp, rsp
0x180028c65  sub     rsp, 40h
0x180028c69  mov     rdi, rdx
0x180028c6c  mov     r14, r8
0x180028c6f  lea     rdx, WPP_GLOBAL_Control
0x180028c76  mov     rsi, rcx
0x180028c79  test    rdi, rdi
0x180028c7c  jz      short loc_180028CD0
0x180028c7e  mov     rax, [rdi]
0x180028c81  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180028c88  jnz     short loc_180028CD0
0x180028c8a  mov     rax, [rdi+8]
0x180028c8e  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180028c95  jnz     short loc_180028CD0
0x180028c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c9e  cmp     rcx, rdx
0x180028ca1  jz      short loc_180028CCC
0x180028ca3  test    byte ptr [rcx+1Ch], 10h
0x180028ca7  jz      short loc_180028CCC
0x180028ca9  mov     rcx, [rcx+10h]
0x180028cad  lea     r8, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids
0x180028cb4  mov     edx, 0Ah
0x180028cb9  call    WPP_SF_
0x180028cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180028cc5  lea     rdx, WPP_GLOBAL_Control
0x180028ccc  xor     edi, edi
0x180028cce  jmp     short loc_180028CD7
0x180028cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180028cd7  test    r14, r14
0x180028cda  jnz     short loc_180028D0B
0x180028cdc  cmp     rcx, rdx
0x180028cdf  jz      short loc_180028D01
0x180028ce1  test    byte ptr [rcx+1Ch], 8
0x180028ce5  jz      short loc_180028D01
0x180028ce7  mov     rcx, [rcx+10h]
0x180028ceb  lea     edx, [r14+0Bh]
0x180028cef  mov     r9d, 80004003h
0x180028cf5  lea     r8, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids
0x180028cfc  call    WPP_SF_d
0x180028d01  mov     eax, 80004003h
0x180028d06  jmp     loc_180029057
0x180028d0b  mov     rdx, [rsi+58h]; struct IMultiObjectElevationFactory **
0x180028d0f  lea     r15, [rsi+50h]
0x180028d13  mov     rcx, [rsi+40h]; HWND
0x180028d17  lea     r12, [rsi+48h]
0x180028d1b  mov     r9, r15; struct IPXWizardFactoryRegistration **
0x180028d1e  mov     [rbp+var_8], r15
0x180028d22  mov     r8, r12; struct IPXWizardRegistration **
0x180028d25  call    ?HrEnsureComponentRegistrationModulesLoaded@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@PEAPEAUIPXWizardRegistration@@PEAPEAUIPXWizardFactoryRegistration@@@Z; HrEnsureComponentRegistrationModulesLoaded(HWND__ *,IMultiObjectElevationFactory * *,IPXWizardRegistration * *,IPXWizardFactoryRegistration * *)
0x180028d2a  mov     ebx, eax
0x180028d2c  test    eax, eax
0x180028d2e  js      loc_180029024
0x180028d34  test    rdi, rdi
0x180028d37  jz      loc_180028E20
0x180028d3d  lea     rax, [rbp+rclsid]
0x180028d41  mov     [rbp+rclsid], 0
0x180028d49  lea     r9, IID_IXWizardPageEvent; riid
0x180028d50  mov     [rsp+40h+ppv], rax; ppv
0x180028d55  xor     edx, edx; pUnkOuter
0x180028d57  mov     r8d, 401h; dwClsContext
0x180028d5d  mov     rcx, rdi; rclsid
0x180028d60  call    cs:__imp_CoCreateInstance
0x180028d66  test    eax, eax
0x180028d68  js      short loc_180028DE2
0x180028d6a  mov     rcx, [rbp+rclsid]
0x180028d6e  mov     rdx, r14
0x180028d71  mov     rax, [rcx]
0x180028d74  mov     rax, [rax+48h]
0x180028d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d7d  mov     rcx, [rbp+rclsid]
0x180028d81  mov     ebx, eax
0x180028d83  mov     rdx, [rcx]
0x180028d86  mov     rax, [rdx+10h]
0x180028d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d8f  test    ebx, ebx
0x180028d91  jz      loc_180028F72
0x180028d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d9e  lea     rdx, WPP_GLOBAL_Control
0x180028da5  cmp     rcx, rdx
0x180028da8  jz      short loc_180028DD3
0x180028daa  test    byte ptr [rcx+1Ch], 8
0x180028dae  jz      short loc_180028DD3
0x180028db0  mov     eax, [r14]
0x180028db3  lea     r8, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids
0x180028dba  mov     r9d, [rdi]
0x180028dbd  mov     edx, 0Dh
0x180028dc2  mov     rcx, [rcx+10h]
0x180028dc6  mov     [rsp+40h+var_18], ebx
0x180028dca  mov     dword ptr [rsp+40h+ppv], eax
0x180028dce  call    WPP_SF_ddD
0x180028dd3  test    ebx, ebx
0x180028dd5  mov     eax, 80070005h
0x180028dda  cmovs   eax, ebx
0x180028ddd  jmp     loc_180029057
0x180028de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180028de9  lea     rdx, WPP_GLOBAL_Control
0x180028df0  cmp     rcx, rdx
0x180028df3  jz      loc_180028F72
0x180028df9  test    byte ptr [rcx+1Ch], 10h
0x180028dfd  jz      loc_180028F72
0x180028e03  mov     rcx, [rcx+10h]
0x180028e07  lea     r8, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids
0x180028e0e  mov     edx, 0Ch
0x180028e13  mov     r9d, eax
0x180028e16  call    WPP_SF_d
0x180028e1b  jmp     loc_180028F72
0x180028e20  mov     rax, [rsi]
0x180028e23  lea     r9, [rbp+var_10]
0x180028e27  xor     r8d, r8d
0x180028e2a  mov     [rbp+var_10], 0
0x180028e32  mov     rdx, r14
0x180028e35  mov     rcx, rsi
0x180028e38  mov     rax, [rax+30h]
0x180028e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e41  mov     ebx, eax
0x180028e43  test    eax, eax
0x180028e45  js      loc_180029004
0x180028e4b  mov     [rbp+rclsid], 0
0x180028e53  lea     r15, WPP_GLOBAL_Control
0x180028e5a  mov     esi, 80070005h
0x180028e5f  mov     rcx, [rbp+var_10]
0x180028e63  lea     r8, [rbp+rclsid]
0x180028e67  xor     r9d, r9d
0x180028e6a  mov     rax, [rcx]
0x180028e6d  lea     edx, [r9+1]
0x180028e71  mov     rax, [rax+18h]
0x180028e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e7a  mov     ebx, eax
0x180028e7c  test    eax, eax
0x180028e7e  jnz     loc_180028F56
0x180028e84  mov     rcx, [rbp+rclsid]; rclsid
0x180028e88  lea     rax, [rbp+arg_10]
0x180028e8c  lea     r9, IID_IXWizardPageEvent; riid
0x180028e93  mov     [rsp+40h+ppv], rax; ppv
0x180028e98  xor     edx, edx; pUnkOuter
0x180028e9a  mov     [rbp+arg_10], 0
0x180028ea2  mov     r8d, 401h; dwClsContext
0x180028ea8  call    cs:__imp_CoCreateInstance
0x180028eae  test    eax, eax
0x180028eb0  js      short loc_180028F18
0x180028eb2  mov     rcx, [rbp+arg_10]
0x180028eb6  mov     rdx, r14
0x180028eb9  mov     rax, [rcx]
0x180028ebc  mov     rax, [rax+48h]
0x180028ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ec5  mov     ebx, eax
0x180028ec7  test    eax, eax
0x180028ec9  jz      short loc_180028F06
0x180028ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ed2  cmp     rcx, r15
0x180028ed5  jz      short loc_180028F04
0x180028ed7  test    byte ptr [rcx+1Ch], 8
0x180028edb  jz      short loc_180028F04
0x180028edd  mov     r9, [rbp+rclsid]
0x180028ee1  lea     r8, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids
0x180028ee8  mov     rcx, [rcx+10h]
0x180028eec  mov     edx, 0Eh
0x180028ef1  mov     [rsp+40h+var_18], eax
0x180028ef5  mov     eax, [r14]
0x180028ef8  mov     r9d, [r9]
0x180028efb  mov     dword ptr [rsp+40h+ppv], eax
0x180028eff  call    WPP_SF_ddD
0x180028f04  mov     ebx, esi
0x180028f06  mov     rcx, [rbp+arg_10]
0x180028f0a  mov     rax, [rcx]
0x180028f0d  mov     rax, [rax+10h]
0x180028f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f16  jmp     short loc_180028F44
0x180028f18  mov     rcx, cs:WPP_GLOBAL_Control
0x180028f1f  cmp     rcx, r15
0x180028f22  jz      short loc_180028F42
0x180028f24  test    byte ptr [rcx+1Ch], 10h
0x180028f28  jz      short loc_180028F42
0x180028f2a  mov     rcx, [rcx+10h]
0x180028f2e  lea     r8, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids
0x180028f35  mov     edx, 0Fh
0x180028f3a  mov     r9d, eax
0x180028f3d  call    WPP_SF_d
0x180028f42  xor     ebx, ebx
0x180028f44  mov     rcx, [rbp+rclsid]; pv
0x180028f48  call    cs:__imp_CoTaskMemFree
0x180028f4e  test    ebx, ebx
0x180028f50  jz      loc_180028E5F
0x180028f56  mov     rcx, [rbp+var_10]
0x180028f5a  mov     rax, [rcx]
0x180028f5d  mov     rax, [rax+10h]
0x180028f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f66  mov     r15, [rbp+var_8]
0x180028f6a  test    ebx, ebx
0x180028f6c  js      loc_180029004
0x180028f72  mov     rcx, r14; struct _GUID *
0x180028f75  call    ?IsFactoryRegisteredWizardComponent@@YAHPEBU_GUID@@@Z; IsFactoryRegisteredWizardComponent(_GUID const *)
0x180028f7a  mov     rcx, [r12]
0x180028f7e  mov     esi, eax
0x180028f80  test    rdi, rdi
0x180028f83  mov     r8, r14
0x180028f86  mov     rdx, [rcx]
0x180028f89  mov     rax, [rdx+38h]
0x180028f8d  lea     rdx, GUID_NULL
0x180028f94  cmovnz  rdx, rdi
0x180028f98  xor     r9d, r9d
0x180028f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fa0  mov     ebx, eax
0x180028fa2  test    eax, eax
0x180028fa4  js      short loc_180029024
0x180028fa6  test    rdi, rdi
0x180028fa9  jnz     short loc_180029024
0x180028fab  test    esi, esi
0x180028fad  jz      short loc_180029024
0x180028faf  mov     rcx, [r15]
0x180028fb2  mov     rdx, r14
0x180028fb5  mov     rax, [rcx]
0x180028fb8  mov     rax, [rax+30h]
0x180028fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fc1  mov     ebx, eax
0x180028fc3  test    eax, eax
0x180028fc5  jns     short loc_180029024
0x180028fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180028fce  lea     rax, WPP_GLOBAL_Control
0x180028fd5  cmp     rcx, rax
0x180028fd8  jz      short loc_180028FFD
0x180028fda  test    byte ptr [rcx+1Ch], 4
0x180028fde  jz      short loc_180028FFD
0x180028fe0  mov     rcx, [rcx+10h]
0x180028fe4  lea     edx, [rdi+11h]
0x180028fe7  mov     r9d, ebx
0x180028fea  lea     r8, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids
0x180028ff1  call    WPP_SF_d
0x180028ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ffd  mov     ebx, 1
0x180029002  jmp     short loc_18002902B
0x180029004  mov     rcx, cs:WPP_GLOBAL_Control
0x18002900b  lea     rax, WPP_GLOBAL_Control
0x180029012  cmp     rcx, rax
0x180029015  jz      short loc_180029055
0x180029017  test    byte ptr [rcx+1Ch], 8
0x18002901b  jz      short loc_180029055
0x18002901d  mov     edx, 10h
0x180029022  jmp     short loc_180029042
0x180029024  mov     rcx, cs:WPP_GLOBAL_Control
0x18002902b  lea     rax, WPP_GLOBAL_Control
0x180029032  cmp     rcx, rax
0x180029035  jz      short loc_180029055
0x180029037  test    byte ptr [rcx+1Ch], 10h
0x18002903b  jz      short loc_180029055
0x18002903d  mov     edx, 12h
0x180029042  mov     rcx, [rcx+10h]
0x180029046  lea     r8, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids
0x18002904d  mov     r9d, ebx
0x180029050  call    WPP_SF_d
0x180029055  mov     eax, ebx
0x180029057  lea     r11, [rsp+40h+var_s0]
0x18002905c  mov     rbx, [r11+30h]
0x180029060  mov     rsi, [r11+48h]
0x180029064  mov     rsp, r11
0x180029067  pop     r15
0x180029069  pop     r14
0x18002906b  pop     r12
0x18002906d  pop     rdi
0x18002906e  pop     rbp
0x18002906f  retn
```
