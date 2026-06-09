# CWcnPageTemplate<CWcnPagePasswordPin,&_GUID const CLSID_WcnPagePasswordPin,501,3701,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180004f70`
- end: `0x180005023`
- name: `?CanRunPage@?$CWcnPageTemplate@VCWcnPagePasswordPin@@$1?CLSID_WcnPagePasswordPin@@3U_GUID@@B$0BPF@$0OHF@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004f70`
- `0x180005a80`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005004`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005004`

## pseudocode

```c
__int64 __fastcall CWcnPageTemplate<CWcnPagePasswordPin,&_GUID const CLSID_WcnPagePasswordPin,501,3701,0>::CanRunPage(
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

  result = CXWizardPageUIBaseClass<1570,CWcnPagePasswordPin,&_GUID const CLSID_WcnPagePasswordPin,0,501,3701,0,0,0,0>::CanRunPage(
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
0x180004f70  mov     r11, rsp
0x180004f73  mov     [r11+8], rbx
0x180004f77  mov     [r11+10h], rsi
0x180004f7b  push    rdi
0x180004f7c  sub     rsp, 50h
0x180004f80  mov     rax, [rsp+58h+arg_38]
0x180004f88  mov     rbx, rcx
0x180004f8b  mov     rsi, [rsp+58h+arg_40]
0x180004f93  mov     [r11-18h], rsi
0x180004f97  mov     [r11-20h], rax
0x180004f9b  mov     eax, [rsp+58h+arg_30]
0x180004fa2  mov     [rsp+58h+var_28], eax
0x180004fa6  mov     rax, [rsp+58h+arg_28]
0x180004fae  mov     [r11-30h], rax
0x180004fb2  mov     eax, dword ptr [rsp+58h+arg_20]
0x180004fb9  mov     dword ptr [rsp+58h+var_38], eax; unsigned int *
0x180004fbd  call    ?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPagePasswordPin@@$1?CLSID_WcnPagePasswordPin@@3U_GUID@@B$0A@$0BPF@$0OHF@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageUIBaseClass<1570,CWcnPagePasswordPin,&_GUID const CLSID_WcnPagePasswordPin,0,501,3701,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180004fc2  test    eax, eax
0x180004fc4  js      short loc_180005013
0x180004fc6  lea     rdi, [rbx+0C0h]
0x180004fcd  mov     r9, rdi; void **
0x180004fd0  lea     rcx, [rbx+40h]; this
0x180004fd4  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x180004fdb  lea     rdx, stru_1800362D0; struct _GUID *
0x180004fe2  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x180004fe7  mov     ebx, eax
0x180004fe9  cmp     eax, 1
0x180004fec  jz      short loc_180004FFC
0x180004fee  cmp     qword ptr [rdi], 0
0x180004ff2  jz      short loc_180004FFC
0x180004ff4  test    eax, eax
0x180004ff6  js      short loc_180005001
0x180004ff8  xor     eax, eax
0x180004ffa  jmp     short loc_180005013
0x180004ffc  mov     ebx, 8007139Fh
0x180005001  mov     rcx, [rsi]; pv
0x180005004  call    cs:__imp_CoTaskMemFree
0x18000500a  mov     eax, ebx
0x18000500c  mov     qword ptr [rsi], 0
0x180005013  mov     rbx, [rsp+58h+arg_0]
0x180005018  mov     rsi, [rsp+58h+arg_8]
0x18000501d  add     rsp, 50h
0x180005021  pop     rdi
0x180005022  retn
```
