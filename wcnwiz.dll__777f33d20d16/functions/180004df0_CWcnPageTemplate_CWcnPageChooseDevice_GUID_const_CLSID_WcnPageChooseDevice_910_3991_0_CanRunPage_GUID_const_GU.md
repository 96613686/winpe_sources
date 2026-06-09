# CWcnPageTemplate<CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,910,3991,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180004df0`
- end: `0x180004ea3`
- name: `?CanRunPage@?$CWcnPageTemplate@VCWcnPageChooseDevice@@$1?CLSID_WcnPageChooseDevice@@3U_GUID@@B$0DIO@$0PJH@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004df0`
- `0x180005830`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e84`

## pseudocode

```c
__int64 __fastcall CWcnPageTemplate<CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,910,3991,0>::CanRunPage(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        unsigned int *a5,
        __int64 a6,
        int a7,
        struct IXWizardSource *a8,
        LPVOID *a9)
{
  __int64 result; // rax
  _QWORD *v11; // rdi
  int Property; // eax
  unsigned int v13; // ebx
  unsigned int *v14; // [rsp+20h] [rbp-38h]

  result = CXWizardPageUIBaseClass<1570,CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,0,910,3991,0,0,0,0>::CanRunPage(
             a1,
             a2,
             a3,
             a4,
             (int)a5,
             a6,
             a7,
             a8,
             a9);
  if ( (int)result >= 0 )
  {
    v11 = (_QWORD *)(a1 + 192);
    Property = CXWizardClassRoot::GetProperty(
                 (CXWizardClassRoot *)(a1 + 64),
                 &stru_1800362D0,
                 L"wcn.wizard.data",
                 (void **const)(a1 + 192),
                 v14);
    v13 = Property;
    if ( Property == 1 || !*v11 )
    {
      v13 = -2147019873;
    }
    else if ( Property >= 0 )
    {
      return 0;
    }
    CoTaskMemFree(*a9);
    result = v13;
    *a9 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004df0  mov     r11, rsp
0x180004df3  mov     [r11+8], rbx
0x180004df7  mov     [r11+10h], rsi
0x180004dfb  push    rdi
0x180004dfc  sub     rsp, 50h
0x180004e00  mov     rax, [rsp+58h+arg_38]
0x180004e08  mov     rbx, rcx
0x180004e0b  mov     rsi, [rsp+58h+arg_40]
0x180004e13  mov     [r11-18h], rsi
0x180004e17  mov     [r11-20h], rax
0x180004e1b  mov     eax, [rsp+58h+arg_30]
0x180004e22  mov     [rsp+58h+var_28], eax
0x180004e26  mov     rax, [rsp+58h+arg_28]
0x180004e2e  mov     [r11-30h], rax
0x180004e32  mov     eax, dword ptr [rsp+58h+arg_20]
0x180004e39  mov     dword ptr [rsp+58h+var_38], eax; unsigned int *
0x180004e3d  call    ?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageChooseDevice@@$1?CLSID_WcnPageChooseDevice@@3U_GUID@@B$0A@$0DIO@$0PJH@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageUIBaseClass<1570,CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,0,910,3991,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180004e42  test    eax, eax
0x180004e44  js      short loc_180004E93
0x180004e46  lea     rdi, [rbx+0C0h]
0x180004e4d  mov     r9, rdi; void **
0x180004e50  lea     rcx, [rbx+40h]; this
0x180004e54  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x180004e5b  lea     rdx, stru_1800362D0; struct _GUID *
0x180004e62  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x180004e67  mov     ebx, eax
0x180004e69  cmp     eax, 1
0x180004e6c  jz      short loc_180004E7C
0x180004e6e  cmp     qword ptr [rdi], 0
0x180004e72  jz      short loc_180004E7C
0x180004e74  test    eax, eax
0x180004e76  js      short loc_180004E81
0x180004e78  xor     eax, eax
0x180004e7a  jmp     short loc_180004E93
0x180004e7c  mov     ebx, 8007139Fh
0x180004e81  mov     rcx, [rsi]; pv
0x180004e84  call    cs:__imp_CoTaskMemFree
0x180004e8a  mov     eax, ebx
0x180004e8c  mov     qword ptr [rsi], 0
0x180004e93  mov     rbx, [rsp+58h+arg_0]
0x180004e98  mov     rsi, [rsp+58h+arg_8]
0x180004e9d  add     rsp, 50h
0x180004ea1  pop     rdi
0x180004ea2  retn
```
