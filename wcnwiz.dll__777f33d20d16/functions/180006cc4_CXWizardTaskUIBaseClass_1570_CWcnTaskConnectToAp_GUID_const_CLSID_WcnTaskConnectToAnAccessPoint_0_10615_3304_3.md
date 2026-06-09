# CXWizardTaskUIBaseClass<1570,CWcnTaskConnectToAp,&_GUID const CLSID_WcnTaskConnectToAnAccessPoint,0,10615,3304,3309,3308,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180006cc4`
- end: `0x180006d96`
- name: `?CanRunTask@?$CXWizardTaskUIBaseClass@$0GCC@VCWcnTaskConnectToAp@@$1?CLSID_WcnTaskConnectToAnAccessPoint@@3U_GUID@@B$0A@$0CJHH@$0MOI@$0MON@$0MOM@$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006940`

## callees

- `0x180002294`
- `0x180006b00`
- `0x180006cc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d1f`

## pseudocode

```c
__int64 __fastcall CXWizardTaskUIBaseClass<1570,CWcnTaskConnectToAp,&_GUID const CLSID_WcnTaskConnectToAnAccessPoint,0,10615,3304,3309,3308,0>::CanRunTask(
        int a1,
        __int64 a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        int a7,
        struct IXWizardSource *a8,
        _QWORD *a9)
{
  __int64 result; // rax
  char *v11; // rax
  char *v12; // rbx
  HINSTANCE v13; // rcx

  result = CXWizardTaskBaseClass<1570,CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0>::CanRunTask(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8,
             (__int64)a9);
  if ( (int)result >= 0 )
  {
    v11 = (char *)CoTaskMemAlloc(0x60u);
    v12 = v11;
    if ( v11 )
    {
      memset_0(v11 + 8, 0, 0x58u);
      *((_DWORD *)v12 + 1) = 4;
      *(_DWORD *)v12 = 96;
      v13 = hModule;
      *((_QWORD *)v12 + 8) = CWcnTaskConnectToAp::TaskDlgProc;
      result = 0;
      *((_QWORD *)v12 + 2) = v13;
      *((_QWORD *)v12 + 1) = a2;
      *((_QWORD *)v12 + 4) = 3304;
      *((_QWORD *)v12 + 3) = 10615;
      *((_DWORD *)v12 + 1) = 260;
      *a9 = v12;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006cc4  mov     r11, rsp
0x180006cc7  mov     [r11+8], rbx
0x180006ccb  mov     [r11+10h], rsi
0x180006ccf  push    rdi
0x180006cd0  sub     rsp, 50h
0x180006cd4  mov     rax, [rsp+58h+arg_38]
0x180006cdc  mov     rdi, rdx
0x180006cdf  mov     rsi, [rsp+58h+arg_40]
0x180006ce7  mov     [r11-18h], rsi
0x180006ceb  mov     [r11-20h], rax
0x180006cef  mov     eax, [rsp+58h+arg_30]
0x180006cf6  mov     [rsp+58h+var_28], eax; int
0x180006cfa  mov     rax, [rsp+58h+arg_28]
0x180006d02  mov     [r11-30h], rax
0x180006d06  mov     eax, [rsp+58h+arg_20]
0x180006d0d  mov     [rsp+58h+var_38], eax; int
0x180006d11  call    ?CanRunTask@?$CXWizardTaskBaseClass@$0GCC@VCWcnTaskCFEConfiguredAP@@$1?CLSID_WcnTaskCFEConfiguredAP@@3U_GUID@@B$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardTaskBaseClass<1570,CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180006d16  test    eax, eax
0x180006d18  js      short loc_180006D86
0x180006d1a  mov     ecx, 60h ; '`'; cb
0x180006d1f  call    cs:__imp_CoTaskMemAlloc
0x180006d25  mov     rbx, rax
0x180006d28  test    rax, rax
0x180006d2b  jz      short loc_180006D81
0x180006d2d  xor     edx, edx; Val
0x180006d2f  lea     rcx, [rax+8]; void *
0x180006d33  lea     r8d, [rdx+58h]; Size
0x180006d37  call    memset_0
0x180006d3c  mov     dword ptr [rbx+4], 4
0x180006d43  lea     rax, ?TaskDlgProc@CWcnTaskConnectToAp@@SAHPEAUHWND__@@I_J@Z; CWcnTaskConnectToAp::TaskDlgProc(HWND__ *,uint,__int64)
0x180006d4a  mov     dword ptr [rbx], 60h ; '`'
0x180006d50  mov     rcx, cs:hModule
0x180006d57  mov     [rbx+40h], rax
0x180006d5b  xor     eax, eax
0x180006d5d  mov     [rbx+10h], rcx
0x180006d61  mov     [rbx+8], rdi
0x180006d65  mov     qword ptr [rbx+20h], 0CE8h
0x180006d6d  mov     qword ptr [rbx+18h], 2977h
0x180006d75  mov     dword ptr [rbx+4], 104h
0x180006d7c  mov     [rsi], rbx
0x180006d7f  jmp     short loc_180006D86
0x180006d81  mov     eax, 8007000Eh
0x180006d86  mov     rbx, [rsp+58h+arg_0]
0x180006d8b  mov     rsi, [rsp+58h+arg_8]
0x180006d90  add     rsp, 50h
0x180006d94  pop     rdi
0x180006d95  retn
```
