# CPXWizardHost::Unregister(_GUID * const,_GUID * const,int)

- ea: `0x18001cd9c`
- end: `0x18001d1ca`
- name: `?Unregister@CPXWizardHost@@AEAAJQEAU_GUID@@0H@Z`
- size: `1070`
- prototype: `int(CPXWizardHost *__hidden this, struct _GUID *const, struct _GUID *const, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001d1d0`
- `0x18001d1f0`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000bd98`
- `0x18000df3c`
- `0x18000e098`
- `0x18001cd9c`
- `0x18001df3c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cea9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d020`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cea9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d020`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d097`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d097`

## pseudocode

```c
__int64 __fastcall CPXWizardHost::Unregister(
        CPXWizardHost *this,
        struct _GUID *const a2,
        struct _GUID *const a3,
        unsigned int a4)
{
  const IID *v4; // rdi
  PVOID *v8; // rcx
  _QWORD *v10; // r15
  _QWORD *v11; // r12
  HRESULT v12; // ebx
  PVOID *v13; // rcx
  __int64 v14; // rdx
  struct IMultiObjectElevationFactory **v15; // rdx
  HWND v16; // rcx
  HRESULT v17; // eax
  int v18; // esi
  GUID *v19; // rdx
  __int64 v20; // [rsp+30h] [rbp-10h] BYREF
  struct IPXWizardTask *v21; // [rsp+38h] [rbp-8h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+48h] BYREF
  IID *rclsid; // [rsp+90h] [rbp+50h] BYREF

  v4 = a2;
  if ( a2 && *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_NULL.Data4 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids);
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
      WPP_SF_d(v8[2], 11, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids, 2147500035LL);
    return 2147500035LL;
  }
  v10 = (_QWORD *)((char *)this + 80);
  v11 = (_QWORD *)((char *)this + 72);
  v12 = HrEnsureComponentRegistrationModulesLoaded(
          *((HWND *)this + 8),
          *((struct IMultiObjectElevationFactory ***)this + 11),
          (struct IPXWizardRegistration **)this + 9,
          (struct IPXWizardFactoryRegistration **)this + 10);
  if ( v12 < 0 )
    goto LABEL_56;
  ppv = 0;
  if ( !v4 )
  {
    v15 = (struct IMultiObjectElevationFactory **)*((_QWORD *)this + 11);
    v16 = (HWND)*((_QWORD *)this + 8);
    v21 = 0;
    v12 = CPXWizardTask::HrCreateInstance(v16, v15, &v21);
    if ( v12 < 0 )
      goto LABEL_53;
    v20 = 0;
    v12 = (*(__int64 (__fastcall **)(struct IPXWizardTask *, struct _GUID *const, _QWORD, __int64 *))(*(_QWORD *)v21 + 56LL))(
            v21,
            a3,
            0,
            &v20);
    if ( v12 >= 0 )
    {
      rclsid = 0;
      do
      {
        v12 = (*(__int64 (__fastcall **)(__int64, __int64, IID **))(*(_QWORD *)v20 + 24LL))(v20, 1, &rclsid);
        if ( v12 )
          break;
        v12 = CoCreateInstance(rclsid, 0, 0x401u, &IID_IXWizardHostEvent, &ppv);
        if ( v12 >= 0 )
        {
          v17 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *const))(*(_QWORD *)ppv + 32LL))(ppv, a3);
          v12 = v17;
          if ( v17 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_ddD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids,
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
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    (*(void (__fastcall **)(struct IPXWizardTask *))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v12 < 0 )
    {
LABEL_53:
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return (unsigned int)v12;
      v14 = 16;
      goto LABEL_60;
    }
LABEL_43:
    v18 = IsFactoryRegisteredWizardComponent(a3);
    v19 = &GUID_NULL;
    if ( v4 )
      v19 = (GUID *)v4;
    v12 = (*(__int64 (__fastcall **)(_QWORD, GUID *, struct _GUID *const, _QWORD))(*(_QWORD *)*v11 + 72LL))(
            *v11,
            v19,
            a3,
            a4);
    if ( v12 >= 0 && !v4 )
    {
      if ( v18 )
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *const))(*(_QWORD *)*v10 + 56LL))(*v10, a3);
        if ( v12 < 0 )
        {
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids,
              (unsigned int)v12);
            v13 = (PVOID *)WPP_GLOBAL_Control;
          }
          v12 = 1;
          goto LABEL_57;
        }
      }
    }
LABEL_56:
    v13 = (PVOID *)WPP_GLOBAL_Control;
LABEL_57:
    if ( v13 == &WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 0x10) == 0 )
      return (unsigned int)v12;
    v14 = 18;
    goto LABEL_60;
  }
  v12 = CoCreateInstance(v4, 0, 0x401u, &IID_IXWizardHostEvent, &ppv);
  if ( v12 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return (unsigned int)v12;
    v14 = 12;
LABEL_60:
    WPP_SF_d(v13[2], v14, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids, (unsigned int)v12);
    return (unsigned int)v12;
  }
  v12 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *const))(*(_QWORD *)ppv + 32LL))(ppv, a3);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v12 != 1 )
  {
    if ( v12 < 0 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return (unsigned int)v12;
      v14 = 14;
      goto LABEL_60;
    }
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_ddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids,
      v4->Data1,
      a3->Data1,
      1);
  return 2147942405LL;
}

```

## disassembly

```asm
0x18001cd9c  mov     [rsp-38h+arg_0], rbx
0x18001cda1  push    rbp
0x18001cda2  push    rsi
0x18001cda3  push    rdi
0x18001cda4  push    r12
0x18001cda6  push    r13
0x18001cda8  push    r14
0x18001cdaa  push    r15
0x18001cdac  mov     rbp, rsp
0x18001cdaf  sub     rsp, 40h
0x18001cdb3  mov     rdi, rdx
0x18001cdb6  mov     r13d, r9d
0x18001cdb9  lea     rdx, WPP_GLOBAL_Control
0x18001cdc0  mov     r14, r8
0x18001cdc3  mov     rsi, rcx
0x18001cdc6  test    rdi, rdi
0x18001cdc9  jz      short loc_18001CE1D
0x18001cdcb  mov     rax, [rdi]
0x18001cdce  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001cdd5  jnz     short loc_18001CE1D
0x18001cdd7  mov     rax, [rdi+8]
0x18001cddb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001cde2  jnz     short loc_18001CE1D
0x18001cde4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdeb  cmp     rcx, rdx
0x18001cdee  jz      short loc_18001CE19
0x18001cdf0  test    byte ptr [rcx+1Ch], 10h
0x18001cdf4  jz      short loc_18001CE19
0x18001cdf6  mov     rcx, [rcx+10h]
0x18001cdfa  lea     r8, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids
0x18001ce01  mov     edx, 0Ah
0x18001ce06  call    WPP_SF_
0x18001ce0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce12  lea     rdx, WPP_GLOBAL_Control
0x18001ce19  xor     edi, edi
0x18001ce1b  jmp     short loc_18001CE24
0x18001ce1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce24  test    r14, r14
0x18001ce27  jnz     short loc_18001CE58
0x18001ce29  cmp     rcx, rdx
0x18001ce2c  jz      short loc_18001CE4E
0x18001ce2e  test    byte ptr [rcx+1Ch], 8
0x18001ce32  jz      short loc_18001CE4E
0x18001ce34  mov     rcx, [rcx+10h]
0x18001ce38  lea     edx, [r14+0Bh]
0x18001ce3c  mov     r9d, 80004003h
0x18001ce42  lea     r8, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids
0x18001ce49  call    WPP_SF_d
0x18001ce4e  mov     eax, 80004003h
0x18001ce53  jmp     loc_18001D1B2
0x18001ce58  mov     rdx, [rsi+58h]; struct IMultiObjectElevationFactory **
0x18001ce5c  lea     r15, [rsi+50h]
0x18001ce60  mov     rcx, [rsi+40h]; HWND
0x18001ce64  lea     r12, [rsi+48h]
0x18001ce68  mov     r9, r15; struct IPXWizardFactoryRegistration **
0x18001ce6b  mov     r8, r12; struct IPXWizardRegistration **
0x18001ce6e  call    ?HrEnsureComponentRegistrationModulesLoaded@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@PEAPEAUIPXWizardRegistration@@PEAPEAUIPXWizardFactoryRegistration@@@Z; HrEnsureComponentRegistrationModulesLoaded(HWND__ *,IMultiObjectElevationFactory * *,IPXWizardRegistration * *,IPXWizardFactoryRegistration * *)
0x18001ce73  mov     ebx, eax
0x18001ce75  test    eax, eax
0x18001ce77  js      loc_18001D17F
0x18001ce7d  mov     [rbp+arg_8], 0
0x18001ce85  test    rdi, rdi
0x18001ce88  jz      loc_18001CF81
0x18001ce8e  lea     rax, [rbp+arg_8]
0x18001ce92  xor     edx, edx; pUnkOuter
0x18001ce94  lea     r9, IID_IXWizardHostEvent; riid
0x18001ce9b  mov     [rsp+40h+ppv], rax; ppv
0x18001cea0  mov     r8d, 401h; dwClsContext
0x18001cea6  mov     rcx, rdi; rclsid
0x18001cea9  call    cs:__imp_CoCreateInstance
0x18001ceaf  mov     ebx, eax
0x18001ceb1  test    eax, eax
0x18001ceb3  jns     short loc_18001CEE0
0x18001ceb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cebc  lea     rsi, WPP_GLOBAL_Control
0x18001cec3  cmp     rcx, rsi
0x18001cec6  jz      loc_18001D1B0
0x18001cecc  test    byte ptr [rcx+1Ch], 4
0x18001ced0  jz      loc_18001D1B0
0x18001ced6  mov     edx, 0Ch
0x18001cedb  jmp     loc_18001D19D
0x18001cee0  mov     rcx, [rbp+arg_8]
0x18001cee4  mov     rdx, r14
0x18001cee7  mov     rax, [rcx]
0x18001ceea  mov     rax, [rax+20h]
0x18001ceee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cef3  mov     rcx, [rbp+arg_8]
0x18001cef7  mov     ebx, eax
0x18001cef9  mov     rdx, [rcx]
0x18001cefc  mov     rax, [rdx+10h]
0x18001cf00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf05  cmp     ebx, 1
0x18001cf08  jnz     short loc_18001CF4E
0x18001cf0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf11  lea     rsi, WPP_GLOBAL_Control
0x18001cf18  cmp     rcx, rsi
0x18001cf1b  jz      short loc_18001CF44
0x18001cf1d  test    byte ptr [rcx+1Ch], 8
0x18001cf21  jz      short loc_18001CF44
0x18001cf23  mov     eax, [r14]
0x18001cf26  lea     edx, [rbx+0Ch]
0x18001cf29  mov     r9d, [rdi]
0x18001cf2c  lea     r8, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids
0x18001cf33  mov     rcx, [rcx+10h]
0x18001cf37  mov     [rsp+40h+var_18], ebx
0x18001cf3b  mov     dword ptr [rsp+40h+ppv], eax
0x18001cf3f  call    WPP_SF_ddD
0x18001cf44  mov     eax, 80070005h
0x18001cf49  jmp     loc_18001D1B2
0x18001cf4e  test    ebx, ebx
0x18001cf50  jns     loc_18001D0CD
0x18001cf56  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf5d  lea     rsi, WPP_GLOBAL_Control
0x18001cf64  cmp     rcx, rsi
0x18001cf67  jz      loc_18001D1B0
0x18001cf6d  test    byte ptr [rcx+1Ch], 8
0x18001cf71  jz      loc_18001D1B0
0x18001cf77  mov     edx, 0Eh
0x18001cf7c  jmp     loc_18001D19D
0x18001cf81  mov     rdx, [rsi+58h]; struct IMultiObjectElevationFactory **
0x18001cf85  lea     r8, [rbp+var_8]; struct IPXWizardTask **
0x18001cf89  mov     rcx, [rsi+40h]; HWND
0x18001cf8d  mov     [rbp+var_8], 0
0x18001cf95  call    ?HrCreateInstance@CPXWizardTask@@SAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@PEAPEAUIPXWizardTask@@@Z; CPXWizardTask::HrCreateInstance(HWND__ *,IMultiObjectElevationFactory * *,IPXWizardTask * *)
0x18001cf9a  mov     ebx, eax
0x18001cf9c  test    eax, eax
0x18001cf9e  js      loc_18001D15F
0x18001cfa4  mov     rcx, [rbp+var_8]
0x18001cfa8  lea     r9, [rbp+var_10]
0x18001cfac  mov     [rbp+var_10], 0
0x18001cfb4  xor     r8d, r8d
0x18001cfb7  mov     rdx, r14
0x18001cfba  mov     rax, [rcx]
0x18001cfbd  mov     rax, [rax+38h]
0x18001cfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfc6  mov     ebx, eax
0x18001cfc8  test    eax, eax
0x18001cfca  js      loc_18001D0B5
0x18001cfd0  mov     [rbp+rclsid], 0
0x18001cfd8  lea     rsi, WPP_GLOBAL_Control
0x18001cfdf  mov     rcx, [rbp+var_10]
0x18001cfe3  lea     r8, [rbp+rclsid]
0x18001cfe7  xor     r9d, r9d
0x18001cfea  mov     rax, [rcx]
0x18001cfed  lea     edx, [r9+1]
0x18001cff1  mov     rax, [rax+18h]
0x18001cff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cffa  mov     ebx, eax
0x18001cffc  test    eax, eax
0x18001cffe  jnz     loc_18001D0A5
0x18001d004  mov     rcx, [rbp+rclsid]; rclsid
0x18001d008  lea     rax, [rbp+arg_8]
0x18001d00c  lea     r9, IID_IXWizardHostEvent; riid
0x18001d013  mov     [rsp+40h+ppv], rax; ppv
0x18001d018  xor     edx, edx; pUnkOuter
0x18001d01a  mov     r8d, 401h; dwClsContext
0x18001d020  call    cs:__imp_CoCreateInstance
0x18001d026  mov     ebx, eax
0x18001d028  test    eax, eax
0x18001d02a  js      short loc_18001D093
0x18001d02c  mov     rcx, [rbp+arg_8]
0x18001d030  mov     rdx, r14
0x18001d033  mov     rax, [rcx]
0x18001d036  mov     rax, [rax+20h]
0x18001d03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d03f  mov     ebx, eax
0x18001d041  test    eax, eax
0x18001d043  jz      short loc_18001D083
0x18001d045  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d04c  cmp     rcx, rsi
0x18001d04f  jz      short loc_18001D07E
0x18001d051  test    byte ptr [rcx+1Ch], 8
0x18001d055  jz      short loc_18001D07E
0x18001d057  mov     r9, [rbp+rclsid]
0x18001d05b  lea     r8, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids
0x18001d062  mov     rcx, [rcx+10h]
0x18001d066  mov     edx, 0Fh
0x18001d06b  mov     [rsp+40h+var_18], eax
0x18001d06f  mov     eax, [r14]
0x18001d072  mov     r9d, [r9]
0x18001d075  mov     dword ptr [rsp+40h+ppv], eax
0x18001d079  call    WPP_SF_ddD
0x18001d07e  mov     ebx, 80070005h
0x18001d083  mov     rcx, [rbp+arg_8]
0x18001d087  mov     rax, [rcx]
0x18001d08a  mov     rax, [rax+10h]
0x18001d08e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d093  mov     rcx, [rbp+rclsid]; pv
0x18001d097  call    cs:__imp_CoTaskMemFree
0x18001d09d  test    ebx, ebx
0x18001d09f  jz      loc_18001CFDF
0x18001d0a5  mov     rcx, [rbp+var_10]
0x18001d0a9  mov     rax, [rcx]
0x18001d0ac  mov     rax, [rax+10h]
0x18001d0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0b5  mov     rcx, [rbp+var_8]
0x18001d0b9  mov     rax, [rcx]
0x18001d0bc  mov     rax, [rax+10h]
0x18001d0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0c5  test    ebx, ebx
0x18001d0c7  js      loc_18001D15F
0x18001d0cd  mov     rcx, r14; struct _GUID *
0x18001d0d0  call    ?IsFactoryRegisteredWizardComponent@@YAHPEBU_GUID@@@Z; IsFactoryRegisteredWizardComponent(_GUID const *)
0x18001d0d5  mov     rcx, [r12]
0x18001d0d9  mov     esi, eax
0x18001d0db  test    rdi, rdi
0x18001d0de  mov     r9d, r13d
0x18001d0e1  mov     r8, r14
0x18001d0e4  mov     rdx, [rcx]
0x18001d0e7  mov     rax, [rdx+48h]
0x18001d0eb  lea     rdx, GUID_NULL
0x18001d0f2  cmovnz  rdx, rdi
0x18001d0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0fb  mov     ebx, eax
0x18001d0fd  test    eax, eax
0x18001d0ff  js      short loc_18001D17F
0x18001d101  test    rdi, rdi
0x18001d104  jnz     short loc_18001D17F
0x18001d106  test    esi, esi
0x18001d108  jz      short loc_18001D17F
0x18001d10a  mov     rcx, [r15]
0x18001d10d  mov     rdx, r14
0x18001d110  mov     rax, [rcx]
0x18001d113  mov     rax, [rax+38h]
0x18001d117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d11c  mov     ebx, eax
0x18001d11e  test    eax, eax
0x18001d120  jns     short loc_18001D17F
0x18001d122  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d129  lea     rax, WPP_GLOBAL_Control
0x18001d130  cmp     rcx, rax
0x18001d133  jz      short loc_18001D158
0x18001d135  test    byte ptr [rcx+1Ch], 4
0x18001d139  jz      short loc_18001D158
0x18001d13b  mov     rcx, [rcx+10h]
0x18001d13f  lea     edx, [rdi+11h]
0x18001d142  mov     r9d, ebx
0x18001d145  lea     r8, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids
0x18001d14c  call    WPP_SF_d
0x18001d151  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d158  mov     ebx, 1
0x18001d15d  jmp     short loc_18001D186
0x18001d15f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d166  lea     rax, WPP_GLOBAL_Control
0x18001d16d  cmp     rcx, rax
0x18001d170  jz      short loc_18001D1B0
0x18001d172  test    byte ptr [rcx+1Ch], 8
0x18001d176  jz      short loc_18001D1B0
0x18001d178  mov     edx, 10h
0x18001d17d  jmp     short loc_18001D19D
0x18001d17f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d186  lea     rax, WPP_GLOBAL_Control
0x18001d18d  cmp     rcx, rax
0x18001d190  jz      short loc_18001D1B0
0x18001d192  test    byte ptr [rcx+1Ch], 10h
0x18001d196  jz      short loc_18001D1B0
0x18001d198  mov     edx, 12h
0x18001d19d  mov     rcx, [rcx+10h]
0x18001d1a1  lea     r8, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids
0x18001d1a8  mov     r9d, ebx
0x18001d1ab  call    WPP_SF_d
0x18001d1b0  mov     eax, ebx
0x18001d1b2  mov     rbx, [rsp+40h+arg_0]
0x18001d1ba  add     rsp, 40h
0x18001d1be  pop     r15
0x18001d1c0  pop     r14
0x18001d1c2  pop     r13
0x18001d1c4  pop     r12
0x18001d1c6  pop     rdi
0x18001d1c7  pop     rsi
0x18001d1c8  pop     rbp
0x18001d1c9  retn
```
