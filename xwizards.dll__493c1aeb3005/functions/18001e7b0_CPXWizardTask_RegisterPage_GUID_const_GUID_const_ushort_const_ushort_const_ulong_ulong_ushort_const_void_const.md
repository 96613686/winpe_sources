# CPXWizardTask::RegisterPage(_GUID * const,_GUID * const,ushort * const,ushort * const,ulong,ulong,ushort * const,void * const)

- ea: `0x18001e7b0`
- end: `0x18001e9e7`
- name: `?RegisterPage@CPXWizardTask@@UEAAJQEAU_GUID@@0QEAG1KK1QEAX@Z`
- size: `567`
- prototype: `int(CPXWizardTask *__hidden this, struct _GUID *const, struct _GUID *const, unsigned __int16 *const, unsigned __int16 *const, unsigned int, unsigned int, unsigned __int16 *const, void *const)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000bd98`
- `0x18000e098`
- `0x18001d200`
- `0x18001e7b0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e8b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e8b6`

## pseudocode

```c
__int64 __fastcall CPXWizardTask::RegisterPage(
        CPXWizardTask *this,
        struct _GUID *const a2,
        struct _GUID *const a3,
        unsigned __int16 *const a4,
        unsigned __int16 *const a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int16 *const a8,
        void *const a9)
{
  struct _GUID *v11; // rbx
  PVOID *v13; // rcx
  __int64 result; // rax
  _QWORD *v15; // r14
  __int64 *v16; // r15
  int v17; // edi
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  int v20; // edi
  LPVOID ppv; // [rsp+A8h] [rbp+10h] BYREF

  v11 = a2;
  if ( a2 && *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_NULL.Data4 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = 0;
  }
  else
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      WPP_SF_d(v13[2], 34, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, 2147500035LL);
    return 2147500035LL;
  }
  v15 = (_QWORD *)((char *)this + 80);
  v16 = (__int64 *)((char *)this + 72);
  v17 = HrEnsureComponentRegistrationModulesLoaded(
          *((HWND *)this + 8),
          *((struct IMultiObjectElevationFactory ***)this + 13),
          (struct IPXWizardRegistration **)this + 9,
          (struct IPXWizardFactoryRegistration **)this + 10);
  if ( v17 < 0 )
    goto LABEL_28;
  if ( !v11 )
    goto LABEL_27;
  ppv = 0;
  v17 = CoCreateInstance(v11, 0, 0x401u, &IID_IXWizardTaskEvent, &ppv);
  if ( v17 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return (unsigned int)v17;
    v19 = 35;
LABEL_31:
    WPP_SF_d(v18[2], v19, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, (unsigned int)v17);
    return (unsigned int)v17;
  }
  v20 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *const))(*(_QWORD *)ppv + 64LL))(ppv, a3);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( !v20 )
  {
LABEL_27:
    v17 = HrRegisterComponentType<3,2,&_GUID const IID_IXWizardPageEvent>(
            a3,
            v11,
            a4,
            (int *)a5,
            a6,
            a7,
            (int *)a8,
            *v16,
            *v15,
            a9);
LABEL_28:
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return (unsigned int)v17;
    v19 = 37;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_ddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids,
      v11->Data1,
      a3->Data1,
      v20);
  result = 2147942405LL;
  if ( v20 < 0 )
    return (unsigned int)v20;
  return result;
}

```

## disassembly

```asm
0x18001e7b0  push    rbx
0x18001e7b2  push    rbp
0x18001e7b3  push    rsi
0x18001e7b4  push    rdi
0x18001e7b5  push    r12
0x18001e7b7  push    r13
0x18001e7b9  push    r14
0x18001e7bb  push    r15
0x18001e7bd  sub     rsp, 58h
0x18001e7c1  lea     r12, WPP_GLOBAL_Control
0x18001e7c8  mov     rbp, r9
0x18001e7cb  lea     r13, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001e7d2  mov     rsi, r8
0x18001e7d5  mov     rbx, rdx
0x18001e7d8  mov     rdi, rcx
0x18001e7db  test    rdx, rdx
0x18001e7de  jz      short loc_18001E827
0x18001e7e0  mov     rax, [rdx]
0x18001e7e3  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001e7ea  jnz     short loc_18001E827
0x18001e7ec  mov     rax, [rdx+8]
0x18001e7f0  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001e7f7  jnz     short loc_18001E827
0x18001e7f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e800  cmp     rcx, r12
0x18001e803  jz      short loc_18001E823
0x18001e805  test    byte ptr [rcx+1Ch], 10h
0x18001e809  jz      short loc_18001E823
0x18001e80b  mov     rcx, [rcx+10h]
0x18001e80f  mov     edx, 21h ; '!'
0x18001e814  mov     r8, r13
0x18001e817  call    WPP_SF_
0x18001e81c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e823  xor     ebx, ebx
0x18001e825  jmp     short loc_18001E82E
0x18001e827  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e82e  test    rsi, rsi
0x18001e831  jnz     short loc_18001E85D
0x18001e833  cmp     rcx, r12
0x18001e836  jz      short loc_18001E853
0x18001e838  test    byte ptr [rcx+1Ch], 8
0x18001e83c  jz      short loc_18001E853
0x18001e83e  mov     rcx, [rcx+10h]
0x18001e842  lea     edx, [rsi+22h]
0x18001e845  mov     r9d, 80004003h
0x18001e84b  mov     r8, r13
0x18001e84e  call    WPP_SF_d
0x18001e853  mov     eax, 80004003h
0x18001e858  jmp     loc_18001E9D6
0x18001e85d  mov     rdx, [rdi+68h]; struct IMultiObjectElevationFactory **
0x18001e861  lea     r14, [rdi+50h]
0x18001e865  mov     rcx, [rdi+40h]; HWND
0x18001e869  lea     r15, [rdi+48h]
0x18001e86d  mov     r9, r14; struct IPXWizardFactoryRegistration **
0x18001e870  mov     r8, r15; struct IPXWizardRegistration **
0x18001e873  call    ?HrEnsureComponentRegistrationModulesLoaded@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@PEAPEAUIPXWizardRegistration@@PEAPEAUIPXWizardFactoryRegistration@@@Z; HrEnsureComponentRegistrationModulesLoaded(HWND__ *,IMultiObjectElevationFactory * *,IPXWizardRegistration * *,IPXWizardFactoryRegistration * *)
0x18001e878  mov     edi, eax
0x18001e87a  test    eax, eax
0x18001e87c  js      loc_18001E9AE
0x18001e882  test    rbx, rbx
0x18001e885  jz      loc_18001E956
0x18001e88b  lea     rax, [rsp+98h+arg_8]
0x18001e893  mov     [rsp+98h+arg_8], 0
0x18001e89f  lea     r9, IID_IXWizardTaskEvent; riid
0x18001e8a6  mov     [rsp+98h+ppv], rax; ppv
0x18001e8ab  xor     edx, edx; pUnkOuter
0x18001e8ad  mov     r8d, 401h; dwClsContext
0x18001e8b3  mov     rcx, rbx; rclsid
0x18001e8b6  call    cs:__imp_CoCreateInstance
0x18001e8bc  mov     edi, eax
0x18001e8be  test    eax, eax
0x18001e8c0  jns     short loc_18001E8E6
0x18001e8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8c9  cmp     rcx, r12
0x18001e8cc  jz      loc_18001E9D4
0x18001e8d2  test    byte ptr [rcx+1Ch], 10h
0x18001e8d6  jz      loc_18001E9D4
0x18001e8dc  mov     edx, 23h ; '#'
0x18001e8e1  jmp     loc_18001E9C5
0x18001e8e6  mov     rcx, [rsp+98h+arg_8]
0x18001e8ee  mov     rdx, rsi
0x18001e8f1  mov     rax, [rcx]
0x18001e8f4  mov     rax, [rax+40h]
0x18001e8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8fd  mov     rcx, [rsp+98h+arg_8]
0x18001e905  mov     edi, eax
0x18001e907  mov     rdx, [rcx]
0x18001e90a  mov     rax, [rdx+10h]
0x18001e90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e913  test    edi, edi
0x18001e915  jz      short loc_18001E956
0x18001e917  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e91e  cmp     rcx, r12
0x18001e921  jz      short loc_18001E947
0x18001e923  test    byte ptr [rcx+1Ch], 8
0x18001e927  jz      short loc_18001E947
0x18001e929  mov     eax, [rsi]
0x18001e92b  mov     edx, 24h ; '$'
0x18001e930  mov     r9d, [rbx]
0x18001e933  mov     r8, r13
0x18001e936  mov     rcx, [rcx+10h]
0x18001e93a  mov     [rsp+98h+var_70], edi
0x18001e93e  mov     dword ptr [rsp+98h+ppv], eax
0x18001e942  call    WPP_SF_ddD
0x18001e947  test    edi, edi
0x18001e949  mov     eax, 80070005h
0x18001e94e  cmovs   eax, edi
0x18001e951  jmp     loc_18001E9D6
0x18001e956  mov     rax, [rsp+98h+arg_40]
0x18001e95e  mov     r8, rbp
0x18001e961  mov     r9, [rsp+98h+arg_20]
0x18001e969  mov     rdx, rbx
0x18001e96c  mov     [rsp+98h+var_50], rax; __int64
0x18001e971  mov     rcx, rsi; struct _GUID *
0x18001e974  mov     rax, [r14]
0x18001e977  mov     [rsp+98h+pv], rax; pv
0x18001e97c  mov     rax, [r15]
0x18001e97f  mov     [rsp+98h+var_60], rax; __int64
0x18001e984  mov     rax, [rsp+98h+arg_38]
0x18001e98c  mov     [rsp+98h+var_68], rax; __int64
0x18001e991  mov     eax, [rsp+98h+arg_30]
0x18001e998  mov     [rsp+98h+var_70], eax; int
0x18001e99c  mov     eax, [rsp+98h+arg_28]
0x18001e9a3  mov     dword ptr [rsp+98h+ppv], eax; int
0x18001e9a7  call    ??$HrRegisterComponentType@$02$01$1?IID_IXWizardPageEvent@@3U_GUID@@B@@YAJPEAU_GUID@@0PEAG1KK1PEAUIPXWizardRegistration@@PEAUIPXWizardFactoryRegistration@@PEAX@Z; HrRegisterComponentType<3,2,&_GUID const IID_IXWizardPageEvent>(_GUID *,_GUID *,ushort *,ushort *,ulong,ulong,ushort *,IPXWizardRegistration *,IPXWizardFactoryRegistration *,void *)
0x18001e9ac  mov     edi, eax
0x18001e9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9b5  cmp     rcx, r12
0x18001e9b8  jz      short loc_18001E9D4
0x18001e9ba  test    byte ptr [rcx+1Ch], 10h
0x18001e9be  jz      short loc_18001E9D4
0x18001e9c0  mov     edx, 25h ; '%'
0x18001e9c5  mov     rcx, [rcx+10h]
0x18001e9c9  mov     r9d, edi
0x18001e9cc  mov     r8, r13
0x18001e9cf  call    WPP_SF_d
0x18001e9d4  mov     eax, edi
0x18001e9d6  add     rsp, 58h
0x18001e9da  pop     r15
0x18001e9dc  pop     r14
0x18001e9de  pop     r13
0x18001e9e0  pop     r12
0x18001e9e2  pop     rdi
0x18001e9e3  pop     rsi
0x18001e9e4  pop     rbp
0x18001e9e5  pop     rbx
0x18001e9e6  retn
```
