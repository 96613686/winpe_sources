# CProviderRegistrationHooks::GetProvider(ushort const *,IWbemPath *,IWbemClassObject *,ushort * &)

- ea: `0x1800a4670`
- end: `0x1800a4d4f`
- name: `?GetProvider@CProviderRegistrationHooks@@AEAAJPEBGPEAUIWbemPath@@PEAUIWbemClassObject@@AEAPEAG@Z`
- size: `1759`
- prototype: `__int64 __fastcall(CProviderRegistrationHooks *__hidden this, const unsigned __int16 *, struct IWbemPath *, struct IWbemClassObject *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a6680`

## callees

- `0x18000b140`
- `0x1800a4670`
- `0x1800a516c`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a478b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a4b6f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a4c94`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a478b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a4b6f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a4c94`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a47d9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a4ce2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a4d12`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a47d9`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a4ce2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a4d12`
- `wbemcomn!GetMemLogObject` at `0x1800a46b0`
- `wbemcomn!GetMemLogObject` at `0x1800a4814`
- `wbemcomn!GetMemLogObject` at `0x1800a487c`
- `wbemcomn!GetMemLogObject` at `0x1800a48e4`
- `wbemcomn!GetMemLogObject` at `0x1800a494c`
- `wbemcomn!GetMemLogObject` at `0x1800a49b4`
- `wbemcomn!GetMemLogObject` at `0x1800a4a1c`
- `wbemcomn!GetMemLogObject` at `0x1800a4a7d`
- `wbemcomn!GetMemLogObject` at `0x1800a46b0`
- `wbemcomn!GetMemLogObject` at `0x1800a4814`
- `wbemcomn!GetMemLogObject` at `0x1800a487c`
- `wbemcomn!GetMemLogObject` at `0x1800a48e4`
- `wbemcomn!GetMemLogObject` at `0x1800a494c`
- `wbemcomn!GetMemLogObject` at `0x1800a49b4`
- `wbemcomn!GetMemLogObject` at `0x1800a4a1c`
- `wbemcomn!GetMemLogObject` at `0x1800a4a7d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a46c0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4824`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a488c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a48f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a495c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a49c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4a2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4a8d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a46c0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4824`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a488c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a48f4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a495c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a49c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4a2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800a4a8d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a4be0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a4be0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CProviderRegistrationHooks::GetProvider(
        CProviderRegistrationHooks *this,
        const unsigned __int16 *a2,
        struct IWbemPath *a3,
        struct IWbemClassObject *a4,
        unsigned __int16 **a5)
{
  int IsA; // eax
  __int64 v8; // rcx
  CMemoryLog *MemLogObject; // rax
  HRESULT v10; // ebx
  CClientCnt *v11; // rcx
  __int64 v12; // rdx
  struct IWbemPathVtbl *lpVtbl; // rax
  void **v14; // rdi
  void *v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  CMemoryLog *v19; // rax
  __int64 v20; // rcx
  CMemoryLog *v21; // rax
  __int64 v22; // rcx
  CMemoryLog *v23; // rax
  __int64 v24; // rcx
  CMemoryLog *v25; // rax
  __int64 v26; // rcx
  CMemoryLog *v27; // rax
  __int64 v28; // rcx
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  struct IWbemPathVtbl *v31; // rax
  void *v32; // rdi
  void **v33; // r14
  void *v34; // rax
  int v36; // [rsp+50h] [rbp-30h] BYREF
  __int64 v37; // [rsp+58h] [rbp-28h] BYREF
  __int64 v38; // [rsp+60h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-18h] BYREF
  __int64 v40; // [rsp+70h] [rbp-10h] BYREF
  CProviderRegistrationHooks *v41; // [rsp+B0h] [rbp+30h] BYREF
  const unsigned __int16 *v42; // [rsp+B8h] [rbp+38h] BYREF

  v42 = a2;
  v41 = this;
  IsA = CProviderRegistrationHooks::IsA(this, a4, L"__Win32Provider");
  if ( IsA == 4 )
  {
    MemLogObject = GetMemLogObject();
    v10 = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 111;
LABEL_57:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids, 2147749894LL);
      return (unsigned int)v10;
    }
    return (unsigned int)v10;
  }
  if ( !IsA )
  {
    lpVtbl = a3->lpVtbl;
    v37 = 0;
    v10 = ((__int64 (__fastcall *)(struct IWbemPath *, __int64 *))lpVtbl->GetKeyList)(a3, &v37);
    if ( v10 < 0 )
      return (unsigned int)v10;
    v14 = (void **)a5;
    LODWORD(v42) = 0;
    LODWORD(v41) = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, const unsigned __int16 **, _QWORD, CProviderRegistrationHooks **))(*(_QWORD *)v37 + 48LL))(
           v37,
           0,
           0,
           0,
           0,
           &v42,
           *a5,
           &v41) >= 0 )
    {
      v15 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(((unsigned __int64)(unsigned int)v42 >> 1) + 1, 2u));
      *v14 = v15;
      if ( !v15 )
      {
        v10 = -2147217402;
        goto LABEL_13;
      }
      v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, const unsigned __int16 **, void *, CProviderRegistrationHooks **))(*(_QWORD *)v37 + 48LL))(
              v37,
              0,
              0,
              0,
              0,
              &v42,
              v15,
              &v41);
      if ( v10 >= 0 )
      {
LABEL_13:
        v16 = v37;
        goto LABEL_76;
      }
      CWin32DefaultArena::WbemMemFree(*v14);
    }
    v10 = -2147217398;
    goto LABEL_13;
  }
  v10 = 0;
  if ( IsA != 1 )
    return (unsigned int)v10;
  v17 = CProviderRegistrationHooks::IsA(v8, a4, L"__EventProviderRegistration");
  if ( v17 != 4 )
  {
    if ( v17 == 1 )
    {
      v17 = CProviderRegistrationHooks::IsA(v18, a4, L"__EventProviderRegistration");
      if ( v17 == 4 )
      {
        v21 = GetMemLogObject();
        v10 = -2147217402;
        CMemoryLog::Write(v21, -2147217402);
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 113;
          goto LABEL_57;
        }
        return (unsigned int)v10;
      }
      if ( v17 == 1 )
      {
        v17 = CProviderRegistrationHooks::IsA(v20, a4, L"__EventConsumerProviderRegistration");
        if ( v17 == 4 )
        {
          v23 = GetMemLogObject();
          v10 = -2147217402;
          CMemoryLog::Write(v23, -2147217402);
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v12 = 114;
            goto LABEL_57;
          }
          return (unsigned int)v10;
        }
        if ( v17 == 1 )
        {
          v17 = CProviderRegistrationHooks::IsA(v22, a4, L"__InstanceProviderRegistration");
          if ( v17 == 4 )
          {
            v25 = GetMemLogObject();
            v10 = -2147217402;
            CMemoryLog::Write(v25, -2147217402);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 115;
              goto LABEL_57;
            }
            return (unsigned int)v10;
          }
          if ( v17 == 1 )
          {
            v17 = CProviderRegistrationHooks::IsA(v24, a4, L"__MethodProviderRegistration");
            if ( v17 == 4 )
            {
              v27 = GetMemLogObject();
              v10 = -2147217402;
              CMemoryLog::Write(v27, -2147217402);
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v12 = 116;
                goto LABEL_57;
              }
              return (unsigned int)v10;
            }
            if ( v17 == 1 )
            {
              v17 = CProviderRegistrationHooks::IsA(v26, a4, L"__PropertyProviderRegistration");
              if ( v17 == 4 )
              {
                v29 = GetMemLogObject();
                v10 = -2147217402;
                CMemoryLog::Write(v29, -2147217402);
                v11 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v12 = 117;
                  goto LABEL_57;
                }
                return (unsigned int)v10;
              }
              if ( v17 == 1 )
              {
                v17 = CProviderRegistrationHooks::IsA(v28, a4, L"__ClassProviderRegistration");
                if ( v17 == 4 )
                {
                  v30 = GetMemLogObject();
                  v10 = -2147217402;
                  CMemoryLog::Write(v30, -2147217402);
                  v11 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v12 = 118;
                    goto LABEL_57;
                  }
                  return (unsigned int)v10;
                }
              }
            }
          }
        }
      }
    }
    if ( v17 )
      return (unsigned int)-2147217406;
    v31 = a3->lpVtbl;
    v40 = 0;
    v10 = ((__int64 (__fastcall *)(struct IWbemPath *, __int64 *))v31->GetKeyList)(a3, &v40);
    if ( v10 < 0 )
      return (unsigned int)v10;
    LODWORD(v42) = 0;
    v36 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, const unsigned __int16 **, _QWORD, int *))(*(_QWORD *)v40 + 48LL))(
            v40,
            0,
            0,
            0,
            0,
            &v42,
            0,
            &v36);
    if ( v10 >= 0 )
    {
      v32 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(((unsigned __int64)(unsigned int)v42 >> 1) + 1, 2u));
      if ( v32 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, const unsigned __int16 **, void *, int *))(*(_QWORD *)v40 + 48LL))(
                v40,
                0,
                0,
                0,
                0,
                &v42,
                v32,
                &v36);
        if ( v10 >= 0 )
        {
          ppv = 0;
          v10 = CoCreateInstance(&CLSID_WbemDefPath, 0, 1u, &IID_IWbemPath, &ppv);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(LPVOID, __int64, void *))(*(_QWORD *)ppv + 24LL))(ppv, 12, v32);
            if ( v10 >= 0 )
            {
              v38 = 0;
              v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 176LL))(ppv, &v38);
              if ( v10 >= 0 )
              {
                v33 = (void **)a5;
                LODWORD(v41) = 0;
                LODWORD(v37) = 0;
                v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, CProviderRegistrationHooks **, _QWORD, __int64 *))(*(_QWORD *)v38 + 48LL))(
                        v38,
                        0,
                        0,
                        0,
                        0,
                        &v41,
                        *a5,
                        &v37);
                if ( v10 >= 0 )
                {
                  v34 = CWin32DefaultArena::WbemMemAlloc(saturated_mul(((unsigned __int64)(unsigned int)v41 >> 1) + 1, 2u));
                  *v33 = v34;
                  if ( v34 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, CProviderRegistrationHooks **, void *, __int64 *))(*(_QWORD *)v38 + 48LL))(
                            v38,
                            0,
                            0,
                            0,
                            0,
                            &v41,
                            v34,
                            &v37);
                    if ( v10 < 0 )
                      CWin32DefaultArena::WbemMemFree(*v33);
                  }
                  else
                  {
                    v10 = -2147217402;
                  }
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
              }
            }
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
        CWin32DefaultArena::WbemMemFree(v32);
      }
      else
      {
        v10 = -2147217402;
      }
    }
    v16 = v40;
LABEL_76:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    return (unsigned int)v10;
  }
  v19 = GetMemLogObject();
  v10 = -2147217402;
  CMemoryLog::Write(v19, -2147217402);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 112;
    goto LABEL_57;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800a4670  mov     [rsp-28h+arg_10], rbx
0x1800a4675  mov     [rsp-28h+arg_8], rdx
0x1800a467a  mov     [rsp-28h+arg_0], rcx
0x1800a467f  push    rbp
0x1800a4680  push    rsi
0x1800a4681  push    rdi
0x1800a4682  push    r14
0x1800a4684  push    r15
0x1800a4686  mov     rbp, rsp
0x1800a4689  sub     rsp, 80h
0x1800a4690  mov     rsi, r8
0x1800a4693  mov     rdx, r9
0x1800a4696  lea     r8, aWin32provider; "__Win32Provider"
0x1800a469d  mov     rdi, r9
0x1800a46a0  call    ?IsA@CProviderRegistrationHooks@@AEAA?AW4QuadState@QueryPreprocessor@@PEAUIWbemClassObject@@PEAG@Z; CProviderRegistrationHooks::IsA(IWbemClassObject *,ushort *)
0x1800a46a5  mov     r14d, 4
0x1800a46ab  cmp     eax, r14d
0x1800a46ae  jnz     short loc_1800A46FA
0x1800a46b0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a46b6  mov     ebx, 80041006h
0x1800a46bb  mov     rcx, rax
0x1800a46be  mov     edx, ebx
0x1800a46c0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a46c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a46cd  lea     rax, WPP_GLOBAL_Control
0x1800a46d4  cmp     rcx, rax
0x1800a46d7  jz      loc_1800A4D36
0x1800a46dd  test    byte ptr [rcx+1Ch], 1
0x1800a46e1  jz      loc_1800A4D36
0x1800a46e7  cmp     byte ptr [rcx+19h], 2
0x1800a46eb  jb      loc_1800A4D36
0x1800a46f1  lea     edx, [r14+6Bh]
0x1800a46f5  jmp     loc_1800A4AC3
0x1800a46fa  xor     r15d, r15d
0x1800a46fd  test    eax, eax
0x1800a46ff  jnz     loc_1800A47F4
0x1800a4705  mov     rax, [rsi]
0x1800a4708  lea     rdx, [rbp+var_28]
0x1800a470c  mov     rcx, rsi
0x1800a470f  mov     [rbp+var_28], r15
0x1800a4713  mov     rax, [rax+0B0h]
0x1800a471a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a471f  mov     ebx, eax
0x1800a4721  test    eax, eax
0x1800a4723  js      loc_1800A4D36
0x1800a4729  mov     rcx, [rbp+var_28]
0x1800a472d  lea     rdx, [rbp+arg_0]
0x1800a4731  mov     rdi, [rbp+arg_20]
0x1800a4735  xor     r9d, r9d
0x1800a4738  mov     [rsp+80h+var_48], rdx
0x1800a473d  xor     r8d, r8d
0x1800a4740  mov     dword ptr [rbp+arg_8], r15d
0x1800a4744  mov     dword ptr [rbp+arg_0], r15d
0x1800a4748  mov     rdx, [rdi]
0x1800a474b  mov     rax, [rcx]
0x1800a474e  mov     [rsp+80h+var_50], rdx
0x1800a4753  lea     rdx, [rbp+arg_8]
0x1800a4757  mov     [rsp+80h+var_58], rdx
0x1800a475c  xor     edx, edx
0x1800a475e  mov     [rsp+80h+ppv], r15
0x1800a4763  mov     rax, [rax+30h]
0x1800a4767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a476c  test    eax, eax
0x1800a476e  js      short loc_1800A47DF
0x1800a4770  mov     ecx, dword ptr [rbp+arg_8]
0x1800a4773  lea     eax, [r15+2]
0x1800a4777  shr     rcx, 1
0x1800a477a  lea     rsi, [r15-1]
0x1800a477e  inc     rcx
0x1800a4781  mul     rcx
0x1800a4784  cmovb   rax, rsi
0x1800a4788  mov     rcx, rax
0x1800a478b  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800a4791  mov     [rdi], rax
0x1800a4794  mov     r8, rax
0x1800a4797  test    rax, rax
0x1800a479a  jz      short loc_1800A47ED
0x1800a479c  mov     rcx, [rbp+var_28]
0x1800a47a0  xor     r9d, r9d
0x1800a47a3  mov     rdx, [rcx]
0x1800a47a6  mov     rax, [rdx+30h]
0x1800a47aa  lea     rdx, [rbp+arg_0]
0x1800a47ae  mov     [rsp+80h+var_48], rdx
0x1800a47b3  lea     rdx, [rbp+arg_8]
0x1800a47b7  mov     [rsp+80h+var_50], r8
0x1800a47bc  xor     r8d, r8d
0x1800a47bf  mov     [rsp+80h+var_58], rdx
0x1800a47c4  xor     edx, edx
0x1800a47c6  mov     [rsp+80h+ppv], r15
0x1800a47cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a47d0  mov     ebx, eax
0x1800a47d2  test    eax, eax
0x1800a47d4  jns     short loc_1800A47E4
0x1800a47d6  mov     rcx, [rdi]
0x1800a47d9  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800a47df  mov     ebx, 8004100Ah
0x1800a47e4  mov     rcx, [rbp+var_28]
0x1800a47e8  jmp     loc_1800A4D23
0x1800a47ed  mov     ebx, 80041006h
0x1800a47f2  jmp     short loc_1800A47E4
0x1800a47f4  mov     ebx, r15d
0x1800a47f7  cmp     eax, 1
0x1800a47fa  jnz     loc_1800A4D36
0x1800a4800  lea     r8, aEventproviderr; "__EventProviderRegistration"
0x1800a4807  mov     rdx, rdi
0x1800a480a  call    ?IsA@CProviderRegistrationHooks@@AEAA?AW4QuadState@QueryPreprocessor@@PEAUIWbemClassObject@@PEAG@Z; CProviderRegistrationHooks::IsA(IWbemClassObject *,ushort *)
0x1800a480f  cmp     eax, r14d
0x1800a4812  jnz     short loc_1800A485F
0x1800a4814  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a481a  mov     ebx, 80041006h
0x1800a481f  mov     rcx, rax
0x1800a4822  mov     edx, ebx
0x1800a4824  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a482a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4831  lea     rax, WPP_GLOBAL_Control
0x1800a4838  cmp     rcx, rax
0x1800a483b  jz      loc_1800A4D36
0x1800a4841  test    byte ptr [rcx+1Ch], 1
0x1800a4845  jz      loc_1800A4D36
0x1800a484b  cmp     byte ptr [rcx+19h], 2
0x1800a484f  jb      loc_1800A4D36
0x1800a4855  mov     edx, 70h ; 'p'
0x1800a485a  jmp     loc_1800A4AC3
0x1800a485f  cmp     eax, 1
0x1800a4862  jnz     loc_1800A4ADE
0x1800a4868  lea     r8, aEventproviderr; "__EventProviderRegistration"
0x1800a486f  mov     rdx, rdi
0x1800a4872  call    ?IsA@CProviderRegistrationHooks@@AEAA?AW4QuadState@QueryPreprocessor@@PEAUIWbemClassObject@@PEAG@Z; CProviderRegistrationHooks::IsA(IWbemClassObject *,ushort *)
0x1800a4877  cmp     eax, r14d
0x1800a487a  jnz     short loc_1800A48C7
0x1800a487c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a4882  mov     ebx, 80041006h
0x1800a4887  mov     rcx, rax
0x1800a488a  mov     edx, ebx
0x1800a488c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a4892  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4899  lea     rax, WPP_GLOBAL_Control
0x1800a48a0  cmp     rcx, rax
0x1800a48a3  jz      loc_1800A4D36
0x1800a48a9  test    byte ptr [rcx+1Ch], 1
0x1800a48ad  jz      loc_1800A4D36
0x1800a48b3  cmp     byte ptr [rcx+19h], 2
0x1800a48b7  jb      loc_1800A4D36
0x1800a48bd  mov     edx, 71h ; 'q'
0x1800a48c2  jmp     loc_1800A4AC3
0x1800a48c7  cmp     eax, 1
0x1800a48ca  jnz     loc_1800A4ADE
0x1800a48d0  lea     r8, aEventconsumerp_0; "__EventConsumerProviderRegistration"
0x1800a48d7  mov     rdx, rdi
0x1800a48da  call    ?IsA@CProviderRegistrationHooks@@AEAA?AW4QuadState@QueryPreprocessor@@PEAUIWbemClassObject@@PEAG@Z; CProviderRegistrationHooks::IsA(IWbemClassObject *,ushort *)
0x1800a48df  cmp     eax, r14d
0x1800a48e2  jnz     short loc_1800A492F
0x1800a48e4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a48ea  mov     ebx, 80041006h
0x1800a48ef  mov     rcx, rax
0x1800a48f2  mov     edx, ebx
0x1800a48f4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a48fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4901  lea     rax, WPP_GLOBAL_Control
0x1800a4908  cmp     rcx, rax
0x1800a490b  jz      loc_1800A4D36
0x1800a4911  test    byte ptr [rcx+1Ch], 1
0x1800a4915  jz      loc_1800A4D36
0x1800a491b  cmp     byte ptr [rcx+19h], 2
0x1800a491f  jb      loc_1800A4D36
0x1800a4925  mov     edx, 72h ; 'r'
0x1800a492a  jmp     loc_1800A4AC3
0x1800a492f  cmp     eax, 1
0x1800a4932  jnz     loc_1800A4ADE
0x1800a4938  lea     r8, aInstanceprovid; "__InstanceProviderRegistration"
0x1800a493f  mov     rdx, rdi
0x1800a4942  call    ?IsA@CProviderRegistrationHooks@@AEAA?AW4QuadState@QueryPreprocessor@@PEAUIWbemClassObject@@PEAG@Z; CProviderRegistrationHooks::IsA(IWbemClassObject *,ushort *)
0x1800a4947  cmp     eax, r14d
0x1800a494a  jnz     short loc_1800A4997
0x1800a494c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a4952  mov     ebx, 80041006h
0x1800a4957  mov     rcx, rax
0x1800a495a  mov     edx, ebx
0x1800a495c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a4962  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4969  lea     rax, WPP_GLOBAL_Control
0x1800a4970  cmp     rcx, rax
0x1800a4973  jz      loc_1800A4D36
0x1800a4979  test    byte ptr [rcx+1Ch], 1
0x1800a497d  jz      loc_1800A4D36
0x1800a4983  cmp     byte ptr [rcx+19h], 2
0x1800a4987  jb      loc_1800A4D36
0x1800a498d  mov     edx, 73h ; 's'
0x1800a4992  jmp     loc_1800A4AC3
0x1800a4997  cmp     eax, 1
0x1800a499a  jnz     loc_1800A4ADE
0x1800a49a0  lea     r8, aMethodprovider; "__MethodProviderRegistration"
0x1800a49a7  mov     rdx, rdi
0x1800a49aa  call    ?IsA@CProviderRegistrationHooks@@AEAA?AW4QuadState@QueryPreprocessor@@PEAUIWbemClassObject@@PEAG@Z; CProviderRegistrationHooks::IsA(IWbemClassObject *,ushort *)
0x1800a49af  cmp     eax, r14d
0x1800a49b2  jnz     short loc_1800A49FF
0x1800a49b4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a49ba  mov     ebx, 80041006h
0x1800a49bf  mov     rcx, rax
0x1800a49c2  mov     edx, ebx
0x1800a49c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a49ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a49d1  lea     rax, WPP_GLOBAL_Control
0x1800a49d8  cmp     rcx, rax
0x1800a49db  jz      loc_1800A4D36
0x1800a49e1  test    byte ptr [rcx+1Ch], 1
0x1800a49e5  jz      loc_1800A4D36
0x1800a49eb  cmp     byte ptr [rcx+19h], 2
0x1800a49ef  jb      loc_1800A4D36
0x1800a49f5  mov     edx, 74h ; 't'
0x1800a49fa  jmp     loc_1800A4AC3
0x1800a49ff  cmp     eax, 1
0x1800a4a02  jnz     loc_1800A4ADE
0x1800a4a08  lea     r8, aPropertyprovid; "__PropertyProviderRegistration"
0x1800a4a0f  mov     rdx, rdi
0x1800a4a12  call    ?IsA@CProviderRegistrationHooks@@AEAA?AW4QuadState@QueryPreprocessor@@PEAUIWbemClassObject@@PEAG@Z; CProviderRegistrationHooks::IsA(IWbemClassObject *,ushort *)
0x1800a4a17  cmp     eax, r14d
0x1800a4a1a  jnz     short loc_1800A4A64
0x1800a4a1c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a4a22  mov     ebx, 80041006h
0x1800a4a27  mov     rcx, rax
0x1800a4a2a  mov     edx, ebx
0x1800a4a2c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a4a32  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4a39  lea     rax, WPP_GLOBAL_Control
0x1800a4a40  cmp     rcx, rax
0x1800a4a43  jz      loc_1800A4D36
0x1800a4a49  test    byte ptr [rcx+1Ch], 1
0x1800a4a4d  jz      loc_1800A4D36
0x1800a4a53  cmp     byte ptr [rcx+19h], 2
0x1800a4a57  jb      loc_1800A4D36
0x1800a4a5d  mov     edx, 75h ; 'u'
0x1800a4a62  jmp     short loc_1800A4AC3
0x1800a4a64  cmp     eax, 1
0x1800a4a67  jnz     short loc_1800A4ADE
0x1800a4a69  lea     r8, aClassproviderr; "__ClassProviderRegistration"
0x1800a4a70  mov     rdx, rdi
0x1800a4a73  call    ?IsA@CProviderRegistrationHooks@@AEAA?AW4QuadState@QueryPreprocessor@@PEAUIWbemClassObject@@PEAG@Z; CProviderRegistrationHooks::IsA(IWbemClassObject *,ushort *)
0x1800a4a78  cmp     eax, r14d
0x1800a4a7b  jnz     short loc_1800A4ADE
0x1800a4a7d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800a4a83  mov     ebx, 80041006h
0x1800a4a88  mov     rcx, rax
0x1800a4a8b  mov     edx, ebx
0x1800a4a8d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800a4a93  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a4a9a  lea     rax, WPP_GLOBAL_Control
0x1800a4aa1  cmp     rcx, rax
0x1800a4aa4  jz      loc_1800A4D36
0x1800a4aaa  test    byte ptr [rcx+1Ch], 1
0x1800a4aae  jz      loc_1800A4D36
0x1800a4ab4  cmp     byte ptr [rcx+19h], 2
0x1800a4ab8  jb      loc_1800A4D36
0x1800a4abe  mov     edx, 76h ; 'v'
0x1800a4ac3  mov     rcx, [rcx+10h]
0x1800a4ac7  lea     r8, WPP_38f52a6b533d390cb272ca3924e37b8b_Traceguids
0x1800a4ace  mov     r9d, 80041006h
0x1800a4ad4  call    WPP_SF_d
0x1800a4ad9  jmp     loc_1800A4D36
0x1800a4ade  test    eax, eax
0x1800a4ae0  jnz     loc_1800A4D31
0x1800a4ae6  mov     rax, [rsi]
0x1800a4ae9  lea     rdx, [rbp+var_10]
0x1800a4aed  mov     rcx, rsi
0x1800a4af0  mov     [rbp+var_10], r15
0x1800a4af4  mov     rax, [rax+0B0h]
0x1800a4afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4b00  mov     ebx, eax
0x1800a4b02  test    eax, eax
0x1800a4b04  js      loc_1800A4D36
0x1800a4b0a  mov     rcx, [rbp+var_10]
0x1800a4b0e  lea     rdx, [rbp+var_30]
0x1800a4b12  mov     [rsp+80h+var_48], rdx
0x1800a4b17  xor     r9d, r9d
0x1800a4b1a  lea     rdx, [rbp+arg_8]
0x1800a4b1e  mov     dword ptr [rbp+arg_8], r15d
0x1800a4b22  mov     [rbp+var_30], r15d
0x1800a4b26  xor     r8d, r8d
0x1800a4b29  mov     rax, [rcx]
0x1800a4b2c  mov     [rsp+80h+var_50], r15
0x1800a4b31  mov     [rsp+80h+var_58], rdx
0x1800a4b36  xor     edx, edx
0x1800a4b38  mov     [rsp+80h+ppv], r15
0x1800a4b3d  mov     rax, [rax+30h]
0x1800a4b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4b46  mov     ebx, eax
0x1800a4b48  test    eax, eax
0x1800a4b4a  js      loc_1800A4D1F
0x1800a4b50  mov     ecx, dword ptr [rbp+arg_8]
0x1800a4b53  mov     eax, 2
0x1800a4b58  shr     rcx, 1
0x1800a4b5b  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800a4b62  inc     rcx
0x1800a4b65  mul     rcx
0x1800a4b68  cmovb   rax, rsi
0x1800a4b6c  mov     rcx, rax
0x1800a4b6f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800a4b75  mov     rdi, rax
0x1800a4b78  test    rax, rax
0x1800a4b7b  jz      loc_1800A4D1A
  ... truncated ...
```
