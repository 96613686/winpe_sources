# CWdsTransportSetupManager::get_ContentProviders(IWdsTransportCollection * *)

- ea: `0x18000aa90`
- end: `0x18000aeb6`
- name: `?get_ContentProviders@CWdsTransportSetupManager@@UEAAJPEAPEAUIWdsTransportCollection@@@Z`
- size: `1062`
- prototype: `__int64 __fastcall(CWdsTransportSetupManager *__hidden this, struct IWdsTransportCollection **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005e70`
- `0x180005ed0`
- `0x180006ac0`
- `0x180006de0`
- `0x180009e20`
- `0x18000aa90`
- `0x18000b048`
- `0x18000b16c`
- `0x180018538`
- `0x180020010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ad06`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ad1f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ad38`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ad51`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae05`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae1e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae37`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae50`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ad06`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ad1f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ad38`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ad51`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae05`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae1e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae37`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000ae50`
- `ADVAPI32!RegOpenKeyExW` at `0x18000abec`
- `ADVAPI32!RegOpenKeyExW` at `0x18000abec`
- `WdsCommonLib!?EnumKeyClose@CRegKey@@QEAAKPEAX@Z` at `0x18000adec`
- `WdsCommonLib!?EnumKeyClose@CRegKey@@QEAAKPEAX@Z` at `0x18000adec`
- `WdsCommonLib!?GetValueExpSzOrSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x18000ac50`
- `WdsCommonLib!?GetValueExpSzOrSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x18000ac50`
- `WdsCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x18000ac1e`
- `WdsCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x18000ac82`
- `WdsCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x18000ac1e`
- `WdsCommonLib!?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x18000ac82`
- `WdsCommonLib!?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z` at `0x18000ab95`
- `WdsCommonLib!?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z` at `0x18000ab95`
- `WdsCommonLib!?EnumKeyFirst@CRegKey@@QEAAKPEAPEAX@Z` at `0x18000ab62`
- `WdsCommonLib!?EnumKeyFirst@CRegKey@@QEAAKPEAPEAX@Z` at `0x18000ab62`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000aafe`
- `WdsCommonLib!?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z` at `0x18000aafe`

## string_xrefs

- `0x18000aae0`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSMC\Providers`
- `0x18000ac45`: `ProviderDll`

## pseudocode

```c
__int64 __fastcall CWdsTransportSetupManager::get_ContentProviders(
        CWdsTransportSetupManager *this,
        struct IWdsTransportCollection **a2)
{
  CWdsTransportCollection *v4; // rsi
  __int64 Instance; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  const WCHAR *v16; // rbx
  HKEY v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  unsigned __int16 *v33; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 *v34; // [rsp+38h] [rbp-38h] BYREF
  struct IDispatch *v35; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  void *v37; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v38[24]; // [rsp+58h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+30h] BYREF
  LPCWSTR lpSubKey; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int16 *v41; // [rsp+B8h] [rbp+48h] BYREF

  hKey = 0;
  v37 = 0;
  phkResult = 0;
  v4 = 0;
  v35 = 0;
  lpSubKey = 0;
  v41 = 0;
  v33 = 0;
  v34 = 0;
  CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(v38, (char *)this + 80);
  Instance = CRegKey::RemoteOpen(
               (CRegKey *)&hKey,
               *(const unsigned __int16 **)(*((_QWORD *)this + 8) + 112LL),
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSMC\\Providers",
               0x20019u);
  if ( (unsigned int)ElValidateWin32_2(Instance, v6, v7, 988) )
    goto LABEL_2;
  Instance = (unsigned int)CWdsTransportCollection::CreateInstance(
                             &IID_IWdsTransportContentProvider,
                             (struct CWdsTransportCollection **)&phkResult);
  if ( (int)ElValidateHr_2(Instance, v8, v9, 996) < 0 )
  {
    v4 = (CWdsTransportCollection *)phkResult;
    goto LABEL_30;
  }
  Instance = CRegKey::EnumKeyFirst((CRegKey *)&hKey, &v37);
  v12 = ElValidateWin32_2(Instance, v10, v11, 1003);
  v4 = (CWdsTransportCollection *)phkResult;
  if ( v12 )
  {
LABEL_2:
    if ( (int)Instance > 0 )
      LODWORD(Instance) = (unsigned __int16)Instance | 0x80070000;
  }
  else
  {
    while ( 1 )
    {
      phkResult = 0;
      v13 = CRegKey::EnumKeyNext((CRegKey *)&hKey, v37, (unsigned __int16 **)&lpSubKey);
      LODWORD(Instance) = v13;
      if ( v13 == 259 )
        break;
      if ( (unsigned int)ElValidateWin32_2(v13, v14, v15, 1019)
        || (v16 = lpSubKey,
            v17 = hKey,
            CRegKey::Close((CRegKey *)&phkResult),
            Instance = (unsigned int)RegOpenKeyExW(v17, v16, 0, 0x20119u, &phkResult),
            (unsigned int)ElValidateWin32_2(Instance, v18, v19, 1027))
        || (Instance = CRegKey::GetValueSz((CRegKey *)&phkResult, L"Description", &v41),
            (unsigned int)ElValidateWin32_2(Instance, v20, v21, 1034))
        || (Instance = CRegKey::GetValueExpSzOrSz((CRegKey *)&phkResult, L"ProviderDll", &v33),
            (unsigned int)ElValidateWin32_2(Instance, v22, v23, 1041))
        || (Instance = CRegKey::GetValueSz((CRegKey *)&phkResult, L"InitRoutine", &v34),
            (unsigned int)ElValidateWin32_2(Instance, v24, v25, 1048)) )
      {
        if ( (int)Instance > 0 )
          LODWORD(Instance) = (unsigned __int16)Instance | 0x80070000;
LABEL_27:
        CRegKey::Close((CRegKey *)&phkResult);
        goto LABEL_30;
      }
      Instance = (unsigned int)CWdsTransportContentProvider::CreateInstance(
                                 (unsigned __int16 *)lpSubKey,
                                 v41,
                                 v33,
                                 v34,
                                 (struct IWdsTransportContentProvider **)&v35);
      if ( (int)ElValidateHr_2(Instance, v26, v27, 1058) < 0 )
        goto LABEL_27;
      Instance = (unsigned int)CWdsTransportCollection::Add(v4, v35);
      if ( (int)ElValidateHr_2(Instance, v28, v29, 1064) < 0 )
        goto LABEL_27;
      if ( lpSubKey )
      {
        operator delete[]((void *)lpSubKey);
        lpSubKey = 0;
      }
      if ( v41 )
      {
        operator delete[](v41);
        v41 = 0;
      }
      if ( v33 )
      {
        operator delete[](v33);
        v33 = 0;
      }
      if ( v34 )
      {
        operator delete[](v34);
        v34 = 0;
      }
      CRegKey::Close((CRegKey *)&phkResult);
      if ( v35 )
      {
        ((void (__fastcall *)(struct IDispatch *))v35->lpVtbl->Release)(v35);
        v35 = 0;
      }
      CRegKey::Close((CRegKey *)&phkResult);
    }
    CRegKey::Close((CRegKey *)&phkResult);
    Instance = (**(unsigned int (__fastcall ***)(CWdsTransportCollection *, GUID *, struct IWdsTransportCollection **))v4)(
                 v4,
                 &IID_IWdsTransportCollection,
                 a2);
    ElValidateHr_2(Instance, v30, v31, 1079);
  }
LABEL_30:
  if ( v37 )
  {
    CRegKey::EnumKeyClose((CRegKey *)&hKey, v37);
    v37 = 0;
  }
  if ( lpSubKey )
  {
    operator delete[]((void *)lpSubKey);
    lpSubKey = 0;
  }
  if ( v41 )
  {
    operator delete[](v41);
    v41 = 0;
  }
  if ( v33 )
  {
    operator delete[](v33);
    v33 = 0;
  }
  if ( v34 )
  {
    operator delete[](v34);
    v34 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(CWdsTransportCollection *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v35 )
  {
    ((void (__fastcall *)(struct IDispatch *))v35->lpVtbl->Release)(v35);
    v35 = 0;
  }
  CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(v38);
  CRegKey::Close((CRegKey *)&hKey);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000aa90  mov     [rsp-28h+arg_8], rbx
0x18000aa95  push    rbp
0x18000aa96  push    rsi
0x18000aa97  push    rdi
0x18000aa98  push    r14
0x18000aa9a  push    r15
0x18000aa9c  mov     rbp, rsp
0x18000aa9f  sub     rsp, 70h
0x18000aaa3  xor     r15d, r15d
0x18000aaa6  mov     r14, rdx
0x18000aaa9  lea     rdx, [rcx+50h]
0x18000aaad  mov     [rbp+hKey], r15
0x18000aab1  mov     rbx, rcx
0x18000aab4  mov     [rbp+var_20], r15
0x18000aab8  lea     rcx, [rbp+var_18]
0x18000aabc  mov     [rbp+arg_0], r15
0x18000aac0  mov     esi, r15d
0x18000aac3  mov     [rbp+var_30], r15
0x18000aac7  mov     [rbp+lpSubKey], r15
0x18000aacb  mov     [rbp+arg_18], r15
0x18000aacf  mov     [rbp+var_40], r15
0x18000aad3  mov     [rbp+var_38], r15
0x18000aad7  call    ??0?$CAutoTypeLock@VCCriticalSection@@@@QEAA@PEAVCCriticalSection@@H@Z; CAutoTypeLock<CCriticalSection>::CAutoTypeLock<CCriticalSection>(CCriticalSection *,int)
0x18000aadc  mov     rax, [rbx+40h]
0x18000aae0  lea     r9, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\WD"...
0x18000aae7  mov     r8, 0FFFFFFFF80000002h
0x18000aaee  mov     dword ptr [rsp+70h+phkResult], 20019h
0x18000aaf6  lea     rcx, [rbp+hKey]
0x18000aafa  mov     rdx, [rax+70h]
0x18000aafe  call    cs:__imp_?RemoteOpen@CRegKey@@QEAAKPEBGPEAUHKEY__@@0K@Z; CRegKey::RemoteOpen(ushort const *,HKEY__ *,ushort const *,ulong)
0x18000ab05  nop     dword ptr [rax+rax+00h]
0x18000ab0a  mov     ecx, eax
0x18000ab0c  mov     r9d, 3DCh
0x18000ab12  mov     ebx, eax
0x18000ab14  call    ElValidateWin32_2
0x18000ab19  test    eax, eax
0x18000ab1b  jz      short loc_18000AB33
0x18000ab1d  test    ebx, ebx
0x18000ab1f  jle     loc_18000ADDF
0x18000ab25  movzx   ebx, bx
0x18000ab28  or      ebx, 80070000h
0x18000ab2e  jmp     loc_18000ADDF
0x18000ab33  lea     rdx, [rbp+arg_0]; struct CWdsTransportCollection **
0x18000ab37  lea     rcx, IID_IWdsTransportContentProvider; struct _GUID *
0x18000ab3e  call    ?CreateInstance@CWdsTransportCollection@@SAJAEBU_GUID@@PEAPEAV1@@Z; CWdsTransportCollection::CreateInstance(_GUID const &,CWdsTransportCollection * *)
0x18000ab43  mov     r9d, 3E4h
0x18000ab49  mov     ecx, eax
0x18000ab4b  mov     ebx, eax
0x18000ab4d  call    ElValidateHr_2
0x18000ab52  test    eax, eax
0x18000ab54  js      loc_18000ADDB
0x18000ab5a  lea     rdx, [rbp+var_20]
0x18000ab5e  lea     rcx, [rbp+hKey]
0x18000ab62  call    cs:__imp_?EnumKeyFirst@CRegKey@@QEAAKPEAPEAX@Z; CRegKey::EnumKeyFirst(void * *)
0x18000ab69  nop     dword ptr [rax+rax+00h]
0x18000ab6e  mov     ecx, eax
0x18000ab70  mov     r9d, 3EBh
0x18000ab76  mov     ebx, eax
0x18000ab78  call    ElValidateWin32_2
0x18000ab7d  mov     rsi, [rbp+arg_0]
0x18000ab81  test    eax, eax
0x18000ab83  jnz     short loc_18000AB1D
0x18000ab85  mov     rdx, [rbp+var_20]
0x18000ab89  lea     r8, [rbp+lpSubKey]
0x18000ab8d  lea     rcx, [rbp+hKey]
0x18000ab91  mov     [rbp+arg_0], r15
0x18000ab95  call    cs:__imp_?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z; CRegKey::EnumKeyNext(void *,ushort * *)
0x18000ab9c  nop     dword ptr [rax+rax+00h]
0x18000aba1  mov     ebx, eax
0x18000aba3  cmp     eax, 103h
0x18000aba8  jz      loc_18000ADA9
0x18000abae  mov     r9d, 3FBh
0x18000abb4  mov     ecx, eax
0x18000abb6  call    ElValidateWin32_2
0x18000abbb  test    eax, eax
0x18000abbd  jnz     loc_18000AD91
0x18000abc3  mov     rbx, [rbp+lpSubKey]
0x18000abc7  lea     rcx, [rbp+arg_0]; this
0x18000abcb  mov     rdi, [rbp+hKey]
0x18000abcf  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000abd4  lea     rax, [rbp+arg_0]
0x18000abd8  mov     r9d, 20119h; samDesired
0x18000abde  xor     r8d, r8d; ulOptions
0x18000abe1  mov     [rsp+70h+phkResult], rax; phkResult
0x18000abe6  mov     rdx, rbx; lpSubKey
0x18000abe9  mov     rcx, rdi; hKey
0x18000abec  call    cs:__imp_RegOpenKeyExW
0x18000abf3  nop     dword ptr [rax+rax+00h]
0x18000abf8  mov     ecx, eax
0x18000abfa  mov     r9d, 403h
0x18000ac00  mov     ebx, eax
0x18000ac02  call    ElValidateWin32_2
0x18000ac07  test    eax, eax
0x18000ac09  jnz     loc_18000AD91
0x18000ac0f  lea     r8, [rbp+arg_18]
0x18000ac13  lea     rdx, aDescription; "Description"
0x18000ac1a  lea     rcx, [rbp+arg_0]
0x18000ac1e  call    cs:__imp_?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x18000ac25  nop     dword ptr [rax+rax+00h]
0x18000ac2a  mov     ecx, eax
0x18000ac2c  mov     r9d, 40Ah
0x18000ac32  mov     ebx, eax
0x18000ac34  call    ElValidateWin32_2
0x18000ac39  test    eax, eax
0x18000ac3b  jnz     loc_18000AD91
0x18000ac41  lea     r8, [rbp+var_40]
0x18000ac45  lea     rdx, aProviderdll; "ProviderDll"
0x18000ac4c  lea     rcx, [rbp+arg_0]
0x18000ac50  call    cs:__imp_?GetValueExpSzOrSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueExpSzOrSz(ushort const *,ushort * *)
0x18000ac57  nop     dword ptr [rax+rax+00h]
0x18000ac5c  mov     ecx, eax
0x18000ac5e  mov     r9d, 411h
0x18000ac64  mov     ebx, eax
0x18000ac66  call    ElValidateWin32_2
0x18000ac6b  test    eax, eax
0x18000ac6d  jnz     loc_18000AD91
0x18000ac73  lea     r8, [rbp+var_38]
0x18000ac77  lea     rdx, aInitroutine; "InitRoutine"
0x18000ac7e  lea     rcx, [rbp+arg_0]
0x18000ac82  call    cs:__imp_?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x18000ac89  nop     dword ptr [rax+rax+00h]
0x18000ac8e  mov     ecx, eax
0x18000ac90  mov     r9d, 418h
0x18000ac96  mov     ebx, eax
0x18000ac98  call    ElValidateWin32_2
0x18000ac9d  test    eax, eax
0x18000ac9f  jnz     loc_18000AD91
0x18000aca5  mov     r9, [rbp+var_38]; unsigned __int16 *
0x18000aca9  lea     rax, [rbp+var_30]
0x18000acad  mov     r8, [rbp+var_40]; unsigned __int16 *
0x18000acb1  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18000acb5  mov     rcx, [rbp+lpSubKey]; unsigned __int16 *
0x18000acb9  mov     [rsp+70h+phkResult], rax; struct IWdsTransportContentProvider **
0x18000acbe  call    ?CreateInstance@CWdsTransportContentProvider@@SAJPEAG000PEAPEAUIWdsTransportContentProvider@@@Z; CWdsTransportContentProvider::CreateInstance(ushort *,ushort *,ushort *,ushort *,IWdsTransportContentProvider * *)
0x18000acc3  mov     r9d, 422h
0x18000acc9  mov     ecx, eax
0x18000accb  mov     ebx, eax
0x18000accd  call    ElValidateHr_2
0x18000acd2  test    eax, eax
0x18000acd4  js      loc_18000AD9E
0x18000acda  mov     rdx, [rbp+var_30]; struct IDispatch *
0x18000acde  mov     rcx, rsi; this
0x18000ace1  call    ?Add@CWdsTransportCollection@@QEAAJPEAUIDispatch@@@Z; CWdsTransportCollection::Add(IDispatch *)
0x18000ace6  mov     r9d, 428h
0x18000acec  mov     ecx, eax
0x18000acee  mov     ebx, eax
0x18000acf0  call    ElValidateHr_2
0x18000acf5  test    eax, eax
0x18000acf7  js      loc_18000AD9E
0x18000acfd  mov     rcx, [rbp+lpSubKey]
0x18000ad01  test    rcx, rcx
0x18000ad04  jz      short loc_18000AD16
0x18000ad06  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ad0d  nop     dword ptr [rax+rax+00h]
0x18000ad12  mov     [rbp+lpSubKey], r15
0x18000ad16  mov     rcx, [rbp+arg_18]
0x18000ad1a  test    rcx, rcx
0x18000ad1d  jz      short loc_18000AD2F
0x18000ad1f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ad26  nop     dword ptr [rax+rax+00h]
0x18000ad2b  mov     [rbp+arg_18], r15
0x18000ad2f  mov     rcx, [rbp+var_40]
0x18000ad33  test    rcx, rcx
0x18000ad36  jz      short loc_18000AD48
0x18000ad38  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ad3f  nop     dword ptr [rax+rax+00h]
0x18000ad44  mov     [rbp+var_40], r15
0x18000ad48  mov     rcx, [rbp+var_38]
0x18000ad4c  test    rcx, rcx
0x18000ad4f  jz      short loc_18000AD61
0x18000ad51  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ad58  nop     dword ptr [rax+rax+00h]
0x18000ad5d  mov     [rbp+var_38], r15
0x18000ad61  lea     rcx, [rbp+arg_0]; this
0x18000ad65  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000ad6a  mov     rcx, [rbp+var_30]
0x18000ad6e  test    rcx, rcx
0x18000ad71  jz      short loc_18000AD83
0x18000ad73  mov     rax, [rcx]
0x18000ad76  mov     rax, [rax+10h]
0x18000ad7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad7f  mov     [rbp+var_30], r15
0x18000ad83  lea     rcx, [rbp+arg_0]; this
0x18000ad87  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000ad8c  jmp     loc_18000AB85
0x18000ad91  test    ebx, ebx
0x18000ad93  jle     short loc_18000AD9E
0x18000ad95  movzx   ebx, bx
0x18000ad98  or      ebx, 80070000h
0x18000ad9e  lea     rcx, [rbp+arg_0]; this
0x18000ada2  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000ada7  jmp     short loc_18000ADDF
0x18000ada9  lea     rcx, [rbp+arg_0]; this
0x18000adad  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000adb2  mov     rax, [rsi]
0x18000adb5  lea     rdx, IID_IWdsTransportCollection
0x18000adbc  mov     r8, r14
0x18000adbf  mov     rcx, rsi
0x18000adc2  mov     rax, [rax]
0x18000adc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adca  mov     r9d, 437h
0x18000add0  mov     ecx, eax
0x18000add2  mov     ebx, eax
0x18000add4  call    ElValidateHr_2
0x18000add9  jmp     short loc_18000ADDF
0x18000addb  mov     rsi, [rbp+arg_0]
0x18000addf  mov     rdx, [rbp+var_20]
0x18000ade3  test    rdx, rdx
0x18000ade6  jz      short loc_18000ADFC
0x18000ade8  lea     rcx, [rbp+hKey]
0x18000adec  call    cs:__imp_?EnumKeyClose@CRegKey@@QEAAKPEAX@Z; CRegKey::EnumKeyClose(void *)
0x18000adf3  nop     dword ptr [rax+rax+00h]
0x18000adf8  mov     [rbp+var_20], r15
0x18000adfc  mov     rcx, [rbp+lpSubKey]
0x18000ae00  test    rcx, rcx
0x18000ae03  jz      short loc_18000AE15
0x18000ae05  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ae0c  nop     dword ptr [rax+rax+00h]
0x18000ae11  mov     [rbp+lpSubKey], r15
0x18000ae15  mov     rcx, [rbp+arg_18]
0x18000ae19  test    rcx, rcx
0x18000ae1c  jz      short loc_18000AE2E
0x18000ae1e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ae25  nop     dword ptr [rax+rax+00h]
0x18000ae2a  mov     [rbp+arg_18], r15
0x18000ae2e  mov     rcx, [rbp+var_40]
0x18000ae32  test    rcx, rcx
0x18000ae35  jz      short loc_18000AE47
0x18000ae37  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ae3e  nop     dword ptr [rax+rax+00h]
0x18000ae43  mov     [rbp+var_40], r15
0x18000ae47  mov     rcx, [rbp+var_38]
0x18000ae4b  test    rcx, rcx
0x18000ae4e  jz      short loc_18000AE60
0x18000ae50  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000ae57  nop     dword ptr [rax+rax+00h]
0x18000ae5c  mov     [rbp+var_38], r15
0x18000ae60  test    rsi, rsi
0x18000ae63  jz      short loc_18000AE74
0x18000ae65  mov     rax, [rsi]
0x18000ae68  mov     rcx, rsi
0x18000ae6b  mov     rax, [rax+10h]
0x18000ae6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae74  mov     rcx, [rbp+var_30]
0x18000ae78  test    rcx, rcx
0x18000ae7b  jz      short loc_18000AE8D
0x18000ae7d  mov     rax, [rcx]
0x18000ae80  mov     rax, [rax+10h]
0x18000ae84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae89  mov     [rbp+var_30], r15
0x18000ae8d  lea     rcx, [rbp+var_18]
0x18000ae91  call    ??1?$CAutoTypeLock@VCCriticalSection@@@@QEAA@XZ; CAutoTypeLock<CCriticalSection>::~CAutoTypeLock<CCriticalSection>(void)
0x18000ae96  lea     rcx, [rbp+hKey]; this
0x18000ae9a  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x18000ae9f  mov     eax, ebx
0x18000aea1  mov     rbx, [rsp+70h+arg_8]
0x18000aea9  add     rsp, 70h
0x18000aead  pop     r15
0x18000aeaf  pop     r14
0x18000aeb1  pop     rdi
0x18000aeb2  pop     rsi
0x18000aeb3  pop     rbp
0x18000aeb4  retn
```
