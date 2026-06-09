# CPXWizardPage::RegisterPage(_GUID * const,_GUID * const,ushort * const,ushort * const,ulong,ulong,ushort * const,void * const)

- ea: `0x180028a10`
- end: `0x180028c47`
- name: `?RegisterPage@CPXWizardPage@@UEAAJQEAU_GUID@@0QEAG1KK1QEAX@Z`
- size: `567`
- prototype: `int(CPXWizardPage *__hidden this, struct _GUID *const, struct _GUID *const, unsigned __int16 *const, unsigned __int16 *const, unsigned int, unsigned int, unsigned __int16 *const, void *const)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000bd98`
- `0x18000e098`
- `0x18002841c`
- `0x180028a10`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028b16`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180028b16`

## pseudocode

```c
__int64 __fastcall CPXWizardPage::RegisterPage(
        CPXWizardPage *this,
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids);
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
      WPP_SF_d(v13[2], 20, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids, 2147500035LL);
    return 2147500035LL;
  }
  v15 = (_QWORD *)((char *)this + 80);
  v16 = (__int64 *)((char *)this + 72);
  v17 = HrEnsureComponentRegistrationModulesLoaded(
          *((HWND *)this + 8),
          *((struct IMultiObjectElevationFactory ***)this + 11),
          (struct IPXWizardRegistration **)this + 9,
          (struct IPXWizardFactoryRegistration **)this + 10);
  if ( v17 < 0 )
    goto LABEL_28;
  if ( !v11 )
    goto LABEL_27;
  ppv = 0;
  v17 = CoCreateInstance(v11, 0, 0x401u, &IID_IXWizardPageEvent, &ppv);
  if ( v17 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return (unsigned int)v17;
    v19 = 21;
LABEL_31:
    WPP_SF_d(v18[2], v19, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids, (unsigned int)v17);
    return (unsigned int)v17;
  }
  v20 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *const))(*(_QWORD *)ppv + 64LL))(ppv, a3);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( !v20 )
  {
LABEL_27:
    v17 = HrRegisterComponentType<3,3,&_GUID const IID_IXWizardPageEvent>(
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
    v19 = 23;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_ddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids,
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
0x180028a10  push    rbx
0x180028a12  push    rbp
0x180028a13  push    rsi
0x180028a14  push    rdi
0x180028a15  push    r12
0x180028a17  push    r13
0x180028a19  push    r14
0x180028a1b  push    r15
0x180028a1d  sub     rsp, 58h
0x180028a21  lea     r12, WPP_GLOBAL_Control
0x180028a28  mov     rbp, r9
0x180028a2b  lea     r13, WPP_1e1f3c3114153d31e2823df458ecd246_Traceguids
0x180028a32  mov     rsi, r8
0x180028a35  mov     rbx, rdx
0x180028a38  mov     rdi, rcx
0x180028a3b  test    rdx, rdx
0x180028a3e  jz      short loc_180028A87
0x180028a40  mov     rax, [rdx]
0x180028a43  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180028a4a  jnz     short loc_180028A87
0x180028a4c  mov     rax, [rdx+8]
0x180028a50  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180028a57  jnz     short loc_180028A87
0x180028a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a60  cmp     rcx, r12
0x180028a63  jz      short loc_180028A83
0x180028a65  test    byte ptr [rcx+1Ch], 10h
0x180028a69  jz      short loc_180028A83
0x180028a6b  mov     rcx, [rcx+10h]
0x180028a6f  mov     edx, 13h
0x180028a74  mov     r8, r13
0x180028a77  call    WPP_SF_
0x180028a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a83  xor     ebx, ebx
0x180028a85  jmp     short loc_180028A8E
0x180028a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a8e  test    rsi, rsi
0x180028a91  jnz     short loc_180028ABD
0x180028a93  cmp     rcx, r12
0x180028a96  jz      short loc_180028AB3
0x180028a98  test    byte ptr [rcx+1Ch], 8
0x180028a9c  jz      short loc_180028AB3
0x180028a9e  mov     rcx, [rcx+10h]
0x180028aa2  lea     edx, [rsi+14h]
0x180028aa5  mov     r9d, 80004003h
0x180028aab  mov     r8, r13
0x180028aae  call    WPP_SF_d
0x180028ab3  mov     eax, 80004003h
0x180028ab8  jmp     loc_180028C36
0x180028abd  mov     rdx, [rdi+58h]; struct IMultiObjectElevationFactory **
0x180028ac1  lea     r14, [rdi+50h]
0x180028ac5  mov     rcx, [rdi+40h]; HWND
0x180028ac9  lea     r15, [rdi+48h]
0x180028acd  mov     r9, r14; struct IPXWizardFactoryRegistration **
0x180028ad0  mov     r8, r15; struct IPXWizardRegistration **
0x180028ad3  call    ?HrEnsureComponentRegistrationModulesLoaded@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@PEAPEAUIPXWizardRegistration@@PEAPEAUIPXWizardFactoryRegistration@@@Z; HrEnsureComponentRegistrationModulesLoaded(HWND__ *,IMultiObjectElevationFactory * *,IPXWizardRegistration * *,IPXWizardFactoryRegistration * *)
0x180028ad8  mov     edi, eax
0x180028ada  test    eax, eax
0x180028adc  js      loc_180028C0E
0x180028ae2  test    rbx, rbx
0x180028ae5  jz      loc_180028BB6
0x180028aeb  lea     rax, [rsp+98h+arg_8]
0x180028af3  mov     [rsp+98h+arg_8], 0
0x180028aff  lea     r9, IID_IXWizardPageEvent; riid
0x180028b06  mov     [rsp+98h+ppv], rax; ppv
0x180028b0b  xor     edx, edx; pUnkOuter
0x180028b0d  mov     r8d, 401h; dwClsContext
0x180028b13  mov     rcx, rbx; rclsid
0x180028b16  call    cs:__imp_CoCreateInstance
0x180028b1c  mov     edi, eax
0x180028b1e  test    eax, eax
0x180028b20  jns     short loc_180028B46
0x180028b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b29  cmp     rcx, r12
0x180028b2c  jz      loc_180028C34
0x180028b32  test    byte ptr [rcx+1Ch], 8
0x180028b36  jz      loc_180028C34
0x180028b3c  mov     edx, 15h
0x180028b41  jmp     loc_180028C25
0x180028b46  mov     rcx, [rsp+98h+arg_8]
0x180028b4e  mov     rdx, rsi
0x180028b51  mov     rax, [rcx]
0x180028b54  mov     rax, [rax+40h]
0x180028b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b5d  mov     rcx, [rsp+98h+arg_8]
0x180028b65  mov     edi, eax
0x180028b67  mov     rdx, [rcx]
0x180028b6a  mov     rax, [rdx+10h]
0x180028b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028b73  test    edi, edi
0x180028b75  jz      short loc_180028BB6
0x180028b77  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b7e  cmp     rcx, r12
0x180028b81  jz      short loc_180028BA7
0x180028b83  test    byte ptr [rcx+1Ch], 8
0x180028b87  jz      short loc_180028BA7
0x180028b89  mov     eax, [rsi]
0x180028b8b  mov     edx, 16h
0x180028b90  mov     r9d, [rbx]
0x180028b93  mov     r8, r13
0x180028b96  mov     rcx, [rcx+10h]
0x180028b9a  mov     [rsp+98h+var_70], edi
0x180028b9e  mov     dword ptr [rsp+98h+ppv], eax
0x180028ba2  call    WPP_SF_ddD
0x180028ba7  test    edi, edi
0x180028ba9  mov     eax, 80070005h
0x180028bae  cmovs   eax, edi
0x180028bb1  jmp     loc_180028C36
0x180028bb6  mov     rax, [rsp+98h+arg_40]
0x180028bbe  mov     r8, rbp
0x180028bc1  mov     r9, [rsp+98h+arg_20]
0x180028bc9  mov     rdx, rbx
0x180028bcc  mov     [rsp+98h+var_50], rax; __int64
0x180028bd1  mov     rcx, rsi; struct _GUID *
0x180028bd4  mov     rax, [r14]
0x180028bd7  mov     [rsp+98h+pv], rax; pv
0x180028bdc  mov     rax, [r15]
0x180028bdf  mov     [rsp+98h+var_60], rax; __int64
0x180028be4  mov     rax, [rsp+98h+arg_38]
0x180028bec  mov     [rsp+98h+var_68], rax; __int64
0x180028bf1  mov     eax, [rsp+98h+arg_30]
0x180028bf8  mov     [rsp+98h+var_70], eax; int
0x180028bfc  mov     eax, [rsp+98h+arg_28]
0x180028c03  mov     dword ptr [rsp+98h+ppv], eax; int
0x180028c07  call    ??$HrRegisterComponentType@$02$02$1?IID_IXWizardPageEvent@@3U_GUID@@B@@YAJPEAU_GUID@@0PEAG1KK1PEAUIPXWizardRegistration@@PEAUIPXWizardFactoryRegistration@@PEAX@Z; HrRegisterComponentType<3,3,&_GUID const IID_IXWizardPageEvent>(_GUID *,_GUID *,ushort *,ushort *,ulong,ulong,ushort *,IPXWizardRegistration *,IPXWizardFactoryRegistration *,void *)
0x180028c0c  mov     edi, eax
0x180028c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c15  cmp     rcx, r12
0x180028c18  jz      short loc_180028C34
0x180028c1a  test    byte ptr [rcx+1Ch], 10h
0x180028c1e  jz      short loc_180028C34
0x180028c20  mov     edx, 17h
0x180028c25  mov     rcx, [rcx+10h]
0x180028c29  mov     r9d, edi
0x180028c2c  mov     r8, r13
0x180028c2f  call    WPP_SF_d
0x180028c34  mov     eax, edi
0x180028c36  add     rsp, 58h
0x180028c3a  pop     r15
0x180028c3c  pop     r14
0x180028c3e  pop     r13
0x180028c40  pop     r12
0x180028c42  pop     rdi
0x180028c43  pop     rsi
0x180028c44  pop     rbp
0x180028c45  pop     rbx
0x180028c46  retn
```
