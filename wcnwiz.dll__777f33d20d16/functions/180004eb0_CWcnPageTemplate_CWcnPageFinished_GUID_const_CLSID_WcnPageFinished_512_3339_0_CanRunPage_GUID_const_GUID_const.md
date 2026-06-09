# CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180004eb0`
- end: `0x180004f63`
- name: `?CanRunPage@?$CWcnPageTemplate@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0CAA@$0NAL@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004eb0`
- `0x180005958`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004f44`

## pseudocode

```c
__int64 __fastcall CWcnPageTemplate<CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,512,3339,0>::CanRunPage(
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

  result = CXWizardPageUIBaseClass<1570,CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,0,512,3339,0,0,0,0>::CanRunPage(
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
0x180004eb0  mov     r11, rsp
0x180004eb3  mov     [r11+8], rbx
0x180004eb7  mov     [r11+10h], rsi
0x180004ebb  push    rdi
0x180004ebc  sub     rsp, 50h
0x180004ec0  mov     rax, [rsp+58h+arg_38]
0x180004ec8  mov     rbx, rcx
0x180004ecb  mov     rsi, [rsp+58h+arg_40]
0x180004ed3  mov     [r11-18h], rsi
0x180004ed7  mov     [r11-20h], rax
0x180004edb  mov     eax, [rsp+58h+arg_30]
0x180004ee2  mov     [rsp+58h+var_28], eax
0x180004ee6  mov     rax, [rsp+58h+arg_28]
0x180004eee  mov     [r11-30h], rax
0x180004ef2  mov     eax, dword ptr [rsp+58h+arg_20]
0x180004ef9  mov     dword ptr [rsp+58h+var_38], eax; unsigned int *
0x180004efd  call    ?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0A@$0CAA@$0NAL@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageUIBaseClass<1570,CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,0,512,3339,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180004f02  test    eax, eax
0x180004f04  js      short loc_180004F53
0x180004f06  lea     rdi, [rbx+0C0h]
0x180004f0d  mov     r9, rdi; void **
0x180004f10  lea     rcx, [rbx+40h]; this
0x180004f14  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x180004f1b  lea     rdx, stru_1800362D0; struct _GUID *
0x180004f22  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x180004f27  mov     ebx, eax
0x180004f29  cmp     eax, 1
0x180004f2c  jz      short loc_180004F3C
0x180004f2e  cmp     qword ptr [rdi], 0
0x180004f32  jz      short loc_180004F3C
0x180004f34  test    eax, eax
0x180004f36  js      short loc_180004F41
0x180004f38  xor     eax, eax
0x180004f3a  jmp     short loc_180004F53
0x180004f3c  mov     ebx, 8007139Fh
0x180004f41  mov     rcx, [rsi]; pv
0x180004f44  call    cs:__imp_CoTaskMemFree
0x180004f4a  mov     eax, ebx
0x180004f4c  mov     qword ptr [rsi], 0
0x180004f53  mov     rbx, [rsp+58h+arg_0]
0x180004f58  mov     rsi, [rsp+58h+arg_8]
0x180004f5d  add     rsp, 50h
0x180004f61  pop     rdi
0x180004f62  retn
```
