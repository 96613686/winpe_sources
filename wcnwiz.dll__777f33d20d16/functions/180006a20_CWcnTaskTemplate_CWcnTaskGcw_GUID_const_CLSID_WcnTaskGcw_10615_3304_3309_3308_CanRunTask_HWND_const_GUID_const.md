# CWcnTaskTemplate<CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,10615,3304,3309,3308>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180006a20`
- end: `0x180006af8`
- name: `?CanRunTask@?$CWcnTaskTemplate@VCWcnTaskGcw@@$1?CLSID_WcnTaskGcw@@3U_GUID@@B$0CJHH@$0MOI@$0MON@$0MOM@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180006a20`
- `0x180006d9c`
- `0x18000a39c`
- `0x18001b880`
- `0x18002f81c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ada`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ada`

## pseudocode

```c
__int64 __fastcall CWcnTaskTemplate<CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,10615,3304,3309,3308>::CanRunTask(
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
          &CWcnTaskTemplate<CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,10615,3304,3309,3308> `RTTI Type Descriptor',
          &CWcnTaskGcw `RTTI Type Descriptor',
          0);
  if ( !WcnSysCanWcnWizardRun() )
    return 1;
  CanRunTask = CXWizardTaskUIBaseClass<1570,CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,0,10615,3304,3309,3308,0>::CanRunTask(
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
0x180006a20  push    rbx
0x180006a22  push    rbp
0x180006a23  push    rsi
0x180006a24  push    rdi
0x180006a25  push    r12
0x180006a27  push    r14
0x180006a29  push    r15
0x180006a2b  sub     rsp, 50h
0x180006a2f  mov     r14d, r9d
0x180006a32  mov     [rsp+88h+var_68], 0
0x180006a3a  mov     r15, r8
0x180006a3d  lea     r9, ??_R0?AVCWcnTaskGcw@@@8; CWcnTaskGcw `RTTI Type Descriptor'
0x180006a44  mov     r12, rdx
0x180006a47  lea     r8, ??_R0?AV?$CWcnTaskTemplate@VCWcnTaskGcw@@$1?CLSID_WcnTaskGcw@@3U_GUID@@B$0CJHH@$0MOI@$0MON@$0MOM@@@@8; CWcnTaskTemplate<CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,10615,3304,3309,3308> `RTTI Type Descriptor'
0x180006a4e  xor     edx, edx
0x180006a50  mov     rbx, rcx
0x180006a53  call    __RTDynamicCast_0
0x180006a58  mov     rsi, rax
0x180006a5b  call    ?WcnSysCanWcnWizardRun@@YA_NXZ; WcnSysCanWcnWizardRun(void)
0x180006a60  test    al, al
0x180006a62  jnz     short loc_180006A6B
0x180006a64  mov     eax, 1
0x180006a69  jmp     short loc_180006AE9
0x180006a6b  mov     rax, [rsp+88h+arg_38]
0x180006a73  mov     r9d, r14d
0x180006a76  mov     rdi, [rsp+88h+arg_40]
0x180006a7e  mov     r8, r15
0x180006a81  mov     ebp, [rsp+88h+arg_20]
0x180006a88  mov     rdx, r12
0x180006a8b  mov     [rsp+88h+var_48], rdi
0x180006a90  mov     rcx, rbx
0x180006a93  mov     [rsp+88h+var_50], rax
0x180006a98  mov     eax, [rsp+88h+arg_30]
0x180006a9f  mov     [rsp+88h+var_58], eax
0x180006aa3  mov     rax, [rsp+88h+arg_28]
0x180006aab  mov     [rsp+88h+var_60], rax
0x180006ab0  mov     [rsp+88h+var_68], ebp
0x180006ab4  call    ?CanRunTask@?$CXWizardTaskUIBaseClass@$0GCC@VCWcnTaskGcw@@$1?CLSID_WcnTaskGcw@@3U_GUID@@B$0A@$0CJHH@$0MOI@$0MON@$0MOM@$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardTaskUIBaseClass<1570,CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,0,10615,3304,3309,3308,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180006ab9  mov     ebx, eax
0x180006abb  test    eax, eax
0x180006abd  js      short loc_180006AD7
0x180006abf  mov     r8d, ebp
0x180006ac2  mov     rdx, rsi
0x180006ac5  mov     rcx, rsi
0x180006ac8  call    ?LoadWcnWizardData@?$CWcnTaskTemplate@VCWcnTaskGcw@@$1?CLSID_WcnTaskGcw@@3U_GUID@@B$0CJHH@$0MOI@$0MON@$0MOM@@@AEAAJPEAVCWcnTaskGcw@@K@Z; CWcnTaskTemplate<CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,10615,3304,3309,3308>::LoadWcnWizardData(CWcnTaskGcw *,ulong)
0x180006acd  mov     ebx, eax
0x180006acf  test    eax, eax
0x180006ad1  js      short loc_180006AD7
0x180006ad3  xor     ebx, ebx
0x180006ad5  jmp     short loc_180006AE7
0x180006ad7  mov     rcx, [rdi]; pv
0x180006ada  call    cs:__imp_CoTaskMemFree
0x180006ae0  mov     qword ptr [rdi], 0
0x180006ae7  mov     eax, ebx
0x180006ae9  add     rsp, 50h
0x180006aed  pop     r15
0x180006aef  pop     r14
0x180006af1  pop     r12
0x180006af3  pop     rdi
0x180006af4  pop     rsi
0x180006af5  pop     rbp
0x180006af6  pop     rbx
0x180006af7  retn
```
