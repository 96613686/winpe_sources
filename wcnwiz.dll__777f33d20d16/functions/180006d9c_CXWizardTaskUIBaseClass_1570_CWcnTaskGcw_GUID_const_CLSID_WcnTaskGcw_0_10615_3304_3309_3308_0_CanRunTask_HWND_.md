# CXWizardTaskUIBaseClass<1570,CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,0,10615,3304,3309,3308,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180006d9c`
- end: `0x180006e5c`
- name: `?CanRunTask@?$CXWizardTaskUIBaseClass@$0GCC@VCWcnTaskGcw@@$1?CLSID_WcnTaskGcw@@3U_GUID@@B$0A@$0CJHH@$0MOI@$0MON@$0MOM@$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006a20`

## callees

- `0x180002294`
- `0x180006b00`
- `0x180006d9c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006df7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006df7`

## pseudocode

```c
__int64 __fastcall CXWizardTaskUIBaseClass<1570,CWcnTaskGcw,&_GUID const CLSID_WcnTaskGcw,0,10615,3304,3309,3308,0>::CanRunTask(
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
      *((_QWORD *)v12 + 4) = 3304;
      *((_QWORD *)v12 + 3) = 10615;
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
0x180006d9c  mov     r11, rsp
0x180006d9f  mov     [r11+8], rbx
0x180006da3  mov     [r11+10h], rsi
0x180006da7  push    rdi
0x180006da8  sub     rsp, 50h
0x180006dac  mov     rax, [rsp+58h+arg_38]
0x180006db4  mov     rdi, rdx
0x180006db7  mov     rsi, [rsp+58h+arg_40]
0x180006dbf  mov     [r11-18h], rsi
0x180006dc3  mov     [r11-20h], rax
0x180006dc7  mov     eax, [rsp+58h+arg_30]
0x180006dce  mov     [rsp+58h+var_28], eax; int
0x180006dd2  mov     rax, [rsp+58h+arg_28]
0x180006dda  mov     [r11-30h], rax
0x180006dde  mov     eax, [rsp+58h+arg_20]
0x180006de5  mov     [rsp+58h+var_38], eax; int
0x180006de9  call    ?CanRunTask@?$CXWizardTaskBaseClass@$0GCC@VCWcnTaskCFEConfiguredAP@@$1?CLSID_WcnTaskCFEConfiguredAP@@3U_GUID@@B$0A@@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardTaskBaseClass<1570,CWcnTaskCFEConfiguredAP,&_GUID const CLSID_WcnTaskCFEConfiguredAP,0>::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180006dee  test    eax, eax
0x180006df0  js      short loc_180006E4C
0x180006df2  mov     ecx, 60h ; '`'; cb
0x180006df7  call    cs:__imp_CoTaskMemAlloc
0x180006dfd  mov     rbx, rax
0x180006e00  test    rax, rax
0x180006e03  jz      short loc_180006E47
0x180006e05  xor     edx, edx; Val
0x180006e07  lea     rcx, [rax+8]; void *
0x180006e0b  lea     r8d, [rdx+58h]; Size
0x180006e0f  call    memset_0
0x180006e14  mov     dword ptr [rbx], 60h ; '`'
0x180006e1a  xor     eax, eax
0x180006e1c  mov     dword ptr [rbx+4], 4
0x180006e23  mov     rcx, cs:hModule
0x180006e2a  mov     [rbx+10h], rcx
0x180006e2e  mov     [rbx+8], rdi
0x180006e32  mov     qword ptr [rbx+20h], 0CE8h
0x180006e3a  mov     qword ptr [rbx+18h], 2977h
0x180006e42  mov     [rsi], rbx
0x180006e45  jmp     short loc_180006E4C
0x180006e47  mov     eax, 8007000Eh
0x180006e4c  mov     rbx, [rsp+58h+arg_0]
0x180006e51  mov     rsi, [rsp+58h+arg_8]
0x180006e56  add     rsp, 50h
0x180006e5a  pop     rdi
0x180006e5b  retn
```
