# CWcnTaskTemplate<CWcnTaskConnectToAp,&_GUID const CLSID_WcnTaskConnectToAnAccessPoint,10615,3304,3309,3308>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180006940`
- end: `0x180006a18`
- name: `?CanRunTask@?$CWcnTaskTemplate@VCWcnTaskConnectToAp@@$1?CLSID_WcnTaskConnectToAnAccessPoint@@3U_GUID@@B$0CJHH@$0MOI@$0MON@$0MOM@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180006940`
- `0x180006cc4`
- `0x18000a39c`
- `0x18001b880`
- `0x18002f81c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069fa`

## pseudocode

```c
__int64 __fastcall CWcnTaskTemplate<CWcnTaskConnectToAp,&_GUID const CLSID_WcnTaskConnectToAnAccessPoint,10615,3304,3309,3308>::CanRunTask(
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
          &CWcnTaskTemplate<CWcnTaskConnectToAp,&_GUID const CLSID_WcnTaskConnectToAnAccessPoint,10615,3304,3309,3308> `RTTI Type Descriptor',
          &CWcnTaskConnectToAp `RTTI Type Descriptor',
          0);
  if ( !WcnSysCanWcnWizardRun() )
    return 1;
  CanRunTask = CXWizardTaskUIBaseClass<1570,CWcnTaskConnectToAp,&_GUID const CLSID_WcnTaskConnectToAnAccessPoint,0,10615,3304,3309,3308,0>::CanRunTask(
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
    || (CanRunTask = CWcnTaskTemplate<CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,10615,3304,3309,3308>::LoadWcnWizardData(
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
0x180006940  push    rbx
0x180006942  push    rbp
0x180006943  push    rsi
0x180006944  push    rdi
0x180006945  push    r12
0x180006947  push    r14
0x180006949  push    r15
0x18000694b  sub     rsp, 50h
0x18000694f  mov     r14d, r9d
0x180006952  mov     [rsp+88h+var_68], 0
0x18000695a  mov     r15, r8
0x18000695d  lea     r9, ??_R0?AVCWcnTaskConnectToAp@@@8; CWcnTaskConnectToAp `RTTI Type Descriptor'
0x180006964  mov     r12, rdx
0x180006967  lea     r8, ??_R0?AV?$CWcnTaskTemplate@VCWcnTaskConnectToAp@@$1?CLSID_WcnTaskConnectToAnAccessPoint@@3U_GUID@@B$0CJHH@$0MOI@$0MON@$0MOM@@@@8; CWcnTaskTemplate<CWcnTaskConnectToAp,&_GUID const CLSID_WcnTaskConnectToAnAccessPoint,10615,3304,3309,3308> `RTTI Type Descriptor'
0x18000696e  xor     edx, edx
0x180006970  mov     rbx, rcx
0x180006973  call    __RTDynamicCast_0
0x180006978  mov     rsi, rax
0x18000697b  call    ?WcnSysCanWcnWizardRun@@YA_NXZ; WcnSysCanWcnWizardRun(void)
0x180006980  test    al, al
0x180006982  jnz     short loc_18000698B
0x180006984  mov     eax, 1
0x180006989  jmp     short loc_180006A09
0x18000698b  mov     rax, [rsp+88h+arg_38]
0x180006993  mov     r9d, r14d
0x180006996  mov     rdi, [rsp+88h+arg_40]
0x18000699e  mov     r8, r15
0x1800069a1  mov     ebp, [rsp+88h+arg_20]
0x1800069a8  mov     rdx, r12
0x1800069ab  mov     [rsp+88h+var_48], rdi
0x1800069b0  mov     rcx, rbx
0x1800069b3  mov     [rsp+88h+var_50], rax
0x1800069b8  mov     eax, [rsp+88h+arg_30]
0x1800069bf  mov     [rsp+88h+var_58], eax
0x1800069c3  mov     rax, [rsp+88h+arg_28]
0x1800069cb  mov     [rsp+88h+var_60], rax
0x1800069d0  mov     [rsp+88h+var_68], ebp
0x1800069d4  call    ?CanRunTask@?$CXWizardTaskUIBaseClass@$0GCC@VCWcnTaskConnectToAp@@$1?CLSID_WcnTaskConnectToAnAccessPoint@@3U_GUID@@B$0A@$0CJHH@$0MOI@$0MON@$0MOM@$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardTaskUIBaseClass<1570,CWcnTaskConnectToAp,&_GUID const CLSID_WcnTaskConnectToAnAccessPoint,0,10615,3304,3309,3308,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x1800069d9  mov     ebx, eax
0x1800069db  test    eax, eax
0x1800069dd  js      short loc_1800069F7
0x1800069df  mov     r8d, ebp
0x1800069e2  mov     rdx, rsi
0x1800069e5  mov     rcx, rsi
0x1800069e8  call    ?LoadWcnWizardData@?$CWcnTaskTemplate@VCWcnTaskGcw@@$1?CLSID_WcnTaskGcw@@3U_GUID@@B$0CJHH@$0MOI@$0MON@$0MOM@@@AEAAJPEAVCWcnTaskGcw@@K@Z; CWcnTaskTemplate<CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,10615,3304,3309,3308>::LoadWcnWizardData(CWcnTaskGcw *,ulong)
0x1800069ed  mov     ebx, eax
0x1800069ef  test    eax, eax
0x1800069f1  js      short loc_1800069F7
0x1800069f3  xor     ebx, ebx
0x1800069f5  jmp     short loc_180006A07
0x1800069f7  mov     rcx, [rdi]; pv
0x1800069fa  call    cs:__imp_CoTaskMemFree
0x180006a00  mov     qword ptr [rdi], 0
0x180006a07  mov     eax, ebx
0x180006a09  add     rsp, 50h
0x180006a0d  pop     r15
0x180006a0f  pop     r14
0x180006a11  pop     r12
0x180006a13  pop     rdi
0x180006a14  pop     rsi
0x180006a15  pop     rbp
0x180006a16  pop     rbx
0x180006a17  retn
```
