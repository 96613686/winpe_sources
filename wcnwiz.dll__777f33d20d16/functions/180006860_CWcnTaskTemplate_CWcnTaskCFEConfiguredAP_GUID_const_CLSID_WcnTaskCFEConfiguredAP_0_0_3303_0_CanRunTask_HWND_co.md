# CWcnTaskTemplate<CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,3303,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180006860`
- end: `0x180006938`
- name: `?CanRunTask@?$CWcnTaskTemplate@VCWcnTaskCFEConfiguredAP@@$1?CLSID_WcnTaskCFEConfiguredAP@@3U_GUID@@B$0A@$0A@$0MOH@$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006860`
- `0x180006bfc`
- `0x18000a298`
- `0x18001b880`
- `0x18002f81c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000691a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000691a`

## pseudocode

```c
__int64 __fastcall CWcnTaskTemplate<CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,3303,0>::CanRunTask(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        int a7,
        __int64 a8,
        LPVOID *a9)
{
  int v12; // ebx
  __int64 v13; // rsi
  int CanRunTask; // ebx

  v12 = a1;
  v13 = _RTDynamicCast_0(
          a1,
          0,
          &CWcnTaskTemplate<CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,3303,0> `RTTI Type Descriptor',
          &CWcnTaskCFEConfiguredAP `RTTI Type Descriptor',
          0);
  if ( !WcnSysCanWcnWizardRun() )
    return 1;
  CanRunTask = CXWizardTaskUIBaseClass<1570,CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,0,3303,0,0>::CanRunTask(
                 v12,
                 a2,
                 a3,
                 a4,
                 a5,
                 a6,
                 a7,
                 a8,
                 (__int64)a9);
  if ( CanRunTask < 0
    || (CanRunTask = CWcnTaskTemplate<CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,3303,0>::LoadWcnWizardData(
                       v13,
                       v13,
                       a5),
        CanRunTask < 0) )
  {
    CoTaskMemFree(*a9);
    *a9 = 0;
  }
  else
  {
    return 0;
  }
  return (unsigned int)CanRunTask;
}

```

## disassembly

```asm
0x180006860  push    rbx
0x180006862  push    rbp
0x180006863  push    rsi
0x180006864  push    rdi
0x180006865  push    r12
0x180006867  push    r14
0x180006869  push    r15
0x18000686b  sub     rsp, 50h
0x18000686f  mov     r14d, r9d
0x180006872  mov     [rsp+88h+var_68], 0
0x18000687a  mov     r15, r8
0x18000687d  lea     r9, ??_R0?AVCWcnTaskCFEConfiguredAP@@@8; CWcnTaskCFEConfiguredAP `RTTI Type Descriptor'
0x180006884  mov     r12, rdx
0x180006887  lea     r8, ??_R0?AV?$CWcnTaskTemplate@VCWcnTaskCFEConfiguredAP@@$1?CLSID_WcnTaskCFEConfiguredAP@@3U_GUID@@B$0A@$0A@$0MOH@$0A@@@@8; CWcnTaskTemplate<CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,3303,0> `RTTI Type Descriptor'
0x18000688e  xor     edx, edx
0x180006890  mov     rbx, rcx
0x180006893  call    __RTDynamicCast_0
0x180006898  mov     rsi, rax
0x18000689b  call    ?WcnSysCanWcnWizardRun@@YA_NXZ; WcnSysCanWcnWizardRun(void)
0x1800068a0  test    al, al
0x1800068a2  jnz     short loc_1800068AB
0x1800068a4  mov     eax, 1
0x1800068a9  jmp     short loc_180006929
0x1800068ab  mov     rax, [rsp+88h+arg_38]
0x1800068b3  mov     r9d, r14d
0x1800068b6  mov     rdi, [rsp+88h+arg_40]
0x1800068be  mov     r8, r15
0x1800068c1  mov     ebp, [rsp+88h+arg_20]
0x1800068c8  mov     rdx, r12
0x1800068cb  mov     [rsp+88h+var_48], rdi
0x1800068d0  mov     rcx, rbx
0x1800068d3  mov     [rsp+88h+var_50], rax
0x1800068d8  mov     eax, [rsp+88h+arg_30]
0x1800068df  mov     [rsp+88h+var_58], eax
0x1800068e3  mov     rax, [rsp+88h+arg_28]
0x1800068eb  mov     [rsp+88h+var_60], rax
0x1800068f0  mov     [rsp+88h+var_68], ebp
0x1800068f4  call    ?CanRunTask@?$CXWizardTaskUIBaseClass@$0GCC@VCWcnTaskCFEConfiguredAP@@$1?CLSID_WcnTaskCFEConfiguredAP@@3U_GUID@@B$0A@$0A@$0A@$0MOH@$0A@$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardTaskUIBaseClass<1570,CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,0,3303,0,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x1800068f9  mov     ebx, eax
0x1800068fb  test    eax, eax
0x1800068fd  js      short loc_180006917
0x1800068ff  mov     r8d, ebp
0x180006902  mov     rdx, rsi
0x180006905  mov     rcx, rsi
0x180006908  call    ?LoadWcnWizardData@?$CWcnTaskTemplate@VCWcnTaskCFEConfiguredAP@@$1?CLSID_WcnTaskCFEConfiguredAP@@3U_GUID@@B$0A@$0A@$0MOH@$0A@@@AEAAJPEAVCWcnTaskCFEConfiguredAP@@K@Z; CWcnTaskTemplate<CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,3303,0>::LoadWcnWizardData(CWcnTaskCFEConfiguredAP *,ulong)
0x18000690d  mov     ebx, eax
0x18000690f  test    eax, eax
0x180006911  js      short loc_180006917
0x180006913  xor     ebx, ebx
0x180006915  jmp     short loc_180006927
0x180006917  mov     rcx, [rdi]; pv
0x18000691a  call    cs:__imp_CoTaskMemFree
0x180006920  mov     qword ptr [rdi], 0
0x180006927  mov     eax, ebx
0x180006929  add     rsp, 50h
0x18000692d  pop     r15
0x18000692f  pop     r14
0x180006931  pop     r12
0x180006933  pop     rdi
0x180006934  pop     rsi
0x180006935  pop     rbp
0x180006936  pop     rbx
0x180006937  retn
```
