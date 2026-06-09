# CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x1800051b0`
- end: `0x180005263`
- name: `?CanRunPage@?$CWcnPageTemplate@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0DIH@$0DMM@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800051b0`
- `0x180005df8`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005244`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005244`

## pseudocode

```c
__int64 __fastcall CWcnPageTemplate<CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,903,972,0>::CanRunPage(
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

  result = CXWizardPageUIBaseClass<1570,CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,0,903,972,0,0,0,0>::CanRunPage(
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
0x1800051b0  mov     r11, rsp
0x1800051b3  mov     [r11+8], rbx
0x1800051b7  mov     [r11+10h], rsi
0x1800051bb  push    rdi
0x1800051bc  sub     rsp, 50h
0x1800051c0  mov     rax, [rsp+58h+arg_38]
0x1800051c8  mov     rbx, rcx
0x1800051cb  mov     rsi, [rsp+58h+arg_40]
0x1800051d3  mov     [r11-18h], rsi
0x1800051d7  mov     [r11-20h], rax
0x1800051db  mov     eax, [rsp+58h+arg_30]
0x1800051e2  mov     [rsp+58h+var_28], eax
0x1800051e6  mov     rax, [rsp+58h+arg_28]
0x1800051ee  mov     [r11-30h], rax
0x1800051f2  mov     eax, dword ptr [rsp+58h+arg_20]
0x1800051f9  mov     dword ptr [rsp+58h+var_38], eax; unsigned int *
0x1800051fd  call    ?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0A@$0DIH@$0DMM@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageUIBaseClass<1570,CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,0,903,972,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005202  test    eax, eax
0x180005204  js      short loc_180005253
0x180005206  lea     rdi, [rbx+0C0h]
0x18000520d  mov     r9, rdi; void **
0x180005210  lea     rcx, [rbx+40h]; this
0x180005214  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x18000521b  lea     rdx, stru_1800362D0; struct _GUID *
0x180005222  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x180005227  mov     ebx, eax
0x180005229  cmp     eax, 1
0x18000522c  jz      short loc_18000523C
0x18000522e  cmp     qword ptr [rdi], 0
0x180005232  jz      short loc_18000523C
0x180005234  test    eax, eax
0x180005236  js      short loc_180005241
0x180005238  xor     eax, eax
0x18000523a  jmp     short loc_180005253
0x18000523c  mov     ebx, 8007139Fh
0x180005241  mov     rcx, [rsi]; pv
0x180005244  call    cs:__imp_CoTaskMemFree
0x18000524a  mov     eax, ebx
0x18000524c  mov     qword ptr [rsi], 0
0x180005253  mov     rbx, [rsp+58h+arg_0]
0x180005258  mov     rsi, [rsp+58h+arg_8]
0x18000525d  add     rsp, 50h
0x180005261  pop     rdi
0x180005262  retn
```
