# CXWizardTaskUIBaseClass<1570,CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,0,3303,0,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180006bfc`
- end: `0x180006cbc`
- name: `?CanRunTask@?$CXWizardTaskUIBaseClass@$0GCC@VCWcnTaskCFEConfiguredAP@@$1?CLSID_WcnTaskCFEConfiguredAP@@3U_GUID@@B$0A@$0A@$0A@$0MOH@$0A@$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006860`

## callees

- `0x180002294`
- `0x180006b00`
- `0x180006bfc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006c57`

## pseudocode

```c
__int64 __fastcall CXWizardTaskUIBaseClass<1570,CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0,0,0,3303,0,0>::CanRunTask(
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
      *(_DWORD *)v12 = 96;
      result = 0;
      *((_DWORD *)v12 + 1) = 4;
      *((_QWORD *)v12 + 2) = hModule;
      *((_QWORD *)v12 + 1) = a2;
      *((_QWORD *)v12 + 4) = 0;
      *((_QWORD *)v12 + 3) = 0;
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
0x180006bfc  mov     r11, rsp
0x180006bff  mov     [r11+8], rbx
0x180006c03  mov     [r11+10h], rsi
0x180006c07  push    rdi
0x180006c08  sub     rsp, 50h
0x180006c0c  mov     rax, [rsp+58h+arg_38]
0x180006c14  mov     rdi, rdx
0x180006c17  mov     rsi, [rsp+58h+arg_40]
0x180006c1f  mov     [r11-18h], rsi
0x180006c23  mov     [r11-20h], rax
0x180006c27  mov     eax, [rsp+58h+arg_30]
0x180006c2e  mov     [rsp+58h+var_28], eax; int
0x180006c32  mov     rax, [rsp+58h+arg_28]
0x180006c3a  mov     [r11-30h], rax
0x180006c3e  mov     eax, [rsp+58h+arg_20]
0x180006c45  mov     [rsp+58h+var_38], eax; int
0x180006c49  call    ?CanRunTask@?$CXWizardTaskBaseClass@$0GCC@VCWcnTaskCFEConfiguredAP@@$1?CLSID_WcnTaskCFEConfiguredAP@@3U_GUID@@B$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardTaskBaseClass<1570,CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180006c4e  test    eax, eax
0x180006c50  js      short loc_180006CAC
0x180006c52  mov     ecx, 60h ; '`'; cb
0x180006c57  call    cs:__imp_CoTaskMemAlloc
0x180006c5d  mov     rbx, rax
0x180006c60  test    rax, rax
0x180006c63  jz      short loc_180006CA7
0x180006c65  xor     edx, edx; Val
0x180006c67  lea     rcx, [rax+8]; void *
0x180006c6b  lea     r8d, [rdx+58h]; Size
0x180006c6f  call    memset_0
0x180006c74  mov     dword ptr [rbx], 60h ; '`'
0x180006c7a  xor     eax, eax
0x180006c7c  mov     dword ptr [rbx+4], 4
0x180006c83  mov     rcx, cs:hModule
0x180006c8a  mov     [rbx+10h], rcx
0x180006c8e  mov     [rbx+8], rdi
0x180006c92  mov     qword ptr [rbx+20h], 0
0x180006c9a  mov     qword ptr [rbx+18h], 0
0x180006ca2  mov     [rsi], rbx
0x180006ca5  jmp     short loc_180006CAC
0x180006ca7  mov     eax, 8007000Eh
0x180006cac  mov     rbx, [rsp+58h+arg_0]
0x180006cb1  mov     rsi, [rsp+58h+arg_8]
0x180006cb6  add     rsp, 50h
0x180006cba  pop     rdi
0x180006cbb  retn
```
