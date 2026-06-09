# CPXWizardHost::RegisterTask(_GUID * const,_GUID * const,ushort * const,ushort * const,ulong,ulong,ushort * const,void * const)

- ea: `0x18001cb40`
- end: `0x18001cd96`
- name: `?RegisterTask@CPXWizardHost@@UEAAJQEAU_GUID@@0QEAG1KK1QEAX@Z`
- size: `598`
- prototype: `int(CPXWizardHost *__hidden this, struct _GUID *const, struct _GUID *const, unsigned __int16 *const, unsigned __int16 *const, unsigned int, unsigned int, unsigned __int16 *const, void *const)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000bd98`
- `0x18000e098`
- `0x18001c220`
- `0x18001cb40`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cc46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001cc46`

## pseudocode

```c
__int64 __fastcall CPXWizardHost::RegisterTask(
        CPXWizardHost *this,
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
  _QWORD *v15; // r14
  __int64 *v16; // r15
  int v17; // edi
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  LPVOID ppv; // [rsp+A8h] [rbp+10h] BYREF

  v11 = a2;
  if ( a2 && *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)GUID_NULL.Data4 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids);
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
      WPP_SF_d(v13[2], 20, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids, 2147500035LL);
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
    goto LABEL_30;
  if ( !v11 )
  {
LABEL_29:
    v17 = HrRegisterComponentType<2,1,&_GUID const IID_IXWizardTaskEvent>(
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
LABEL_30:
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return (unsigned int)v17;
    v19 = 24;
    goto LABEL_33;
  }
  ppv = 0;
  v17 = CoCreateInstance(v11, 0, 0x401u, &IID_IXWizardHostEvent, &ppv);
  if ( v17 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return (unsigned int)v17;
    v19 = 21;
LABEL_33:
    WPP_SF_d(v18[2], v19, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids, (unsigned int)v17);
    return (unsigned int)v17;
  }
  v17 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *const))(*(_QWORD *)ppv + 24LL))(ppv, a3);
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v17 != 1 )
  {
    if ( v17 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        return (unsigned int)v17;
      v19 = 23;
      goto LABEL_33;
    }
    goto LABEL_29;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_ddD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids,
      v11->Data1,
      a3->Data1,
      1);
  return 2147942405LL;
}

```

## disassembly

```asm
0x18001cb40  push    rbx
0x18001cb42  push    rbp
0x18001cb43  push    rsi
0x18001cb44  push    rdi
0x18001cb45  push    r12
0x18001cb47  push    r13
0x18001cb49  push    r14
0x18001cb4b  push    r15
0x18001cb4d  sub     rsp, 58h
0x18001cb51  lea     r12, WPP_GLOBAL_Control
0x18001cb58  mov     rbp, r9
0x18001cb5b  lea     r13, WPP_92b693c277a233c1583b3c75af4e9d0c_Traceguids
0x18001cb62  mov     rsi, r8
0x18001cb65  mov     rbx, rdx
0x18001cb68  mov     rdi, rcx
0x18001cb6b  test    rdx, rdx
0x18001cb6e  jz      short loc_18001CBB7
0x18001cb70  mov     rax, [rdx]
0x18001cb73  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001cb7a  jnz     short loc_18001CBB7
0x18001cb7c  mov     rax, [rdx+8]
0x18001cb80  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001cb87  jnz     short loc_18001CBB7
0x18001cb89  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb90  cmp     rcx, r12
0x18001cb93  jz      short loc_18001CBB3
0x18001cb95  test    byte ptr [rcx+1Ch], 10h
0x18001cb99  jz      short loc_18001CBB3
0x18001cb9b  mov     rcx, [rcx+10h]
0x18001cb9f  mov     edx, 13h
0x18001cba4  mov     r8, r13
0x18001cba7  call    WPP_SF_
0x18001cbac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbb3  xor     ebx, ebx
0x18001cbb5  jmp     short loc_18001CBBE
0x18001cbb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbbe  test    rsi, rsi
0x18001cbc1  jnz     short loc_18001CBED
0x18001cbc3  cmp     rcx, r12
0x18001cbc6  jz      short loc_18001CBE3
0x18001cbc8  test    byte ptr [rcx+1Ch], 8
0x18001cbcc  jz      short loc_18001CBE3
0x18001cbce  mov     rcx, [rcx+10h]
0x18001cbd2  lea     edx, [rsi+14h]
0x18001cbd5  mov     r9d, 80004003h
0x18001cbdb  mov     r8, r13
0x18001cbde  call    WPP_SF_d
0x18001cbe3  mov     eax, 80004003h
0x18001cbe8  jmp     loc_18001CD85
0x18001cbed  mov     rdx, [rdi+58h]; struct IMultiObjectElevationFactory **
0x18001cbf1  lea     r14, [rdi+50h]
0x18001cbf5  mov     rcx, [rdi+40h]; HWND
0x18001cbf9  lea     r15, [rdi+48h]
0x18001cbfd  mov     r9, r14; struct IPXWizardFactoryRegistration **
0x18001cc00  mov     r8, r15; struct IPXWizardRegistration **
0x18001cc03  call    ?HrEnsureComponentRegistrationModulesLoaded@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@PEAPEAUIPXWizardRegistration@@PEAPEAUIPXWizardFactoryRegistration@@@Z; HrEnsureComponentRegistrationModulesLoaded(HWND__ *,IMultiObjectElevationFactory * *,IPXWizardRegistration * *,IPXWizardFactoryRegistration * *)
0x18001cc08  mov     edi, eax
0x18001cc0a  test    eax, eax
0x18001cc0c  js      loc_18001CD5D
0x18001cc12  test    rbx, rbx
0x18001cc15  jz      loc_18001CD05
0x18001cc1b  lea     rax, [rsp+98h+arg_8]
0x18001cc23  mov     [rsp+98h+arg_8], 0
0x18001cc2f  lea     r9, IID_IXWizardHostEvent; riid
0x18001cc36  mov     [rsp+98h+ppv], rax; ppv
0x18001cc3b  xor     edx, edx; pUnkOuter
0x18001cc3d  mov     r8d, 401h; dwClsContext
0x18001cc43  mov     rcx, rbx; rclsid
0x18001cc46  call    cs:__imp_CoCreateInstance
0x18001cc4c  mov     edi, eax
0x18001cc4e  test    eax, eax
0x18001cc50  jns     short loc_18001CC76
0x18001cc52  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc59  cmp     rcx, r12
0x18001cc5c  jz      loc_18001CD83
0x18001cc62  test    byte ptr [rcx+1Ch], 10h
0x18001cc66  jz      loc_18001CD83
0x18001cc6c  mov     edx, 15h
0x18001cc71  jmp     loc_18001CD74
0x18001cc76  mov     rcx, [rsp+98h+arg_8]
0x18001cc7e  mov     rdx, rsi
0x18001cc81  mov     rax, [rcx]
0x18001cc84  mov     rax, [rax+18h]
0x18001cc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc8d  mov     rcx, [rsp+98h+arg_8]
0x18001cc95  mov     edi, eax
0x18001cc97  mov     rdx, [rcx]
0x18001cc9a  mov     rax, [rdx+10h]
0x18001cc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cca3  cmp     edi, 1
0x18001cca6  jnz     short loc_18001CCE0
0x18001cca8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccaf  cmp     rcx, r12
0x18001ccb2  jz      short loc_18001CCD6
0x18001ccb4  test    byte ptr [rcx+1Ch], 8
0x18001ccb8  jz      short loc_18001CCD6
0x18001ccba  mov     eax, [rsi]
0x18001ccbc  lea     edx, [rdi+15h]
0x18001ccbf  mov     r9d, [rbx]
0x18001ccc2  mov     r8, r13
0x18001ccc5  mov     rcx, [rcx+10h]
0x18001ccc9  mov     [rsp+98h+var_70], edi
0x18001cccd  mov     dword ptr [rsp+98h+ppv], eax
0x18001ccd1  call    WPP_SF_ddD
0x18001ccd6  mov     eax, 80070005h
0x18001ccdb  jmp     loc_18001CD85
0x18001cce0  test    edi, edi
0x18001cce2  jns     short loc_18001CD05
0x18001cce4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cceb  cmp     rcx, r12
0x18001ccee  jz      loc_18001CD83
0x18001ccf4  test    byte ptr [rcx+1Ch], 8
0x18001ccf8  jz      loc_18001CD83
0x18001ccfe  mov     edx, 17h
0x18001cd03  jmp     short loc_18001CD74
0x18001cd05  mov     rax, [rsp+98h+arg_40]
0x18001cd0d  mov     r8, rbp
0x18001cd10  mov     r9, [rsp+98h+arg_20]
0x18001cd18  mov     rdx, rbx
0x18001cd1b  mov     [rsp+98h+var_50], rax; __int64
0x18001cd20  mov     rcx, rsi; struct _GUID *
0x18001cd23  mov     rax, [r14]
0x18001cd26  mov     [rsp+98h+pv], rax; pv
0x18001cd2b  mov     rax, [r15]
0x18001cd2e  mov     [rsp+98h+var_60], rax; __int64
0x18001cd33  mov     rax, [rsp+98h+arg_38]
0x18001cd3b  mov     [rsp+98h+var_68], rax; __int64
0x18001cd40  mov     eax, [rsp+98h+arg_30]
0x18001cd47  mov     [rsp+98h+var_70], eax; int
0x18001cd4b  mov     eax, [rsp+98h+arg_28]
0x18001cd52  mov     dword ptr [rsp+98h+ppv], eax; int
0x18001cd56  call    ??$HrRegisterComponentType@$01$00$1?IID_IXWizardTaskEvent@@3U_GUID@@B@@YAJPEAU_GUID@@0PEAG1KK1PEAUIPXWizardRegistration@@PEAUIPXWizardFactoryRegistration@@PEAX@Z; HrRegisterComponentType<2,1,&_GUID const IID_IXWizardTaskEvent>(_GUID *,_GUID *,ushort *,ushort *,ulong,ulong,ushort *,IPXWizardRegistration *,IPXWizardFactoryRegistration *,void *)
0x18001cd5b  mov     edi, eax
0x18001cd5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd64  cmp     rcx, r12
0x18001cd67  jz      short loc_18001CD83
0x18001cd69  test    byte ptr [rcx+1Ch], 10h
0x18001cd6d  jz      short loc_18001CD83
0x18001cd6f  mov     edx, 18h
0x18001cd74  mov     rcx, [rcx+10h]
0x18001cd78  mov     r9d, edi
0x18001cd7b  mov     r8, r13
0x18001cd7e  call    WPP_SF_d
0x18001cd83  mov     eax, edi
0x18001cd85  add     rsp, 58h
0x18001cd89  pop     r15
0x18001cd8b  pop     r14
0x18001cd8d  pop     r13
0x18001cd8f  pop     r12
0x18001cd91  pop     rdi
0x18001cd92  pop     rsi
0x18001cd93  pop     rbp
0x18001cd94  pop     rbx
0x18001cd95  retn
```
