# CWcnPageTemplate<CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,951,3307,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x1800050f0`
- end: `0x1800051a3`
- name: `?CanRunPage@?$CWcnPageTemplate@VCWcnPageProfileUseExisting@@$1?CLSID_WcnPageProfileUseExisting@@3U_GUID@@B$0DLH@$0MOL@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800050f0`
- `0x180005cd0`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005184`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005184`

## pseudocode

```c
__int64 __fastcall CWcnPageTemplate<CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,951,3307,0>::CanRunPage(
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

  result = CXWizardPageUIBaseClass<1570,CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0,951,3307,0,0,0,0>::CanRunPage(
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
0x1800050f0  mov     r11, rsp
0x1800050f3  mov     [r11+8], rbx
0x1800050f7  mov     [r11+10h], rsi
0x1800050fb  push    rdi
0x1800050fc  sub     rsp, 50h
0x180005100  mov     rax, [rsp+58h+arg_38]
0x180005108  mov     rbx, rcx
0x18000510b  mov     rsi, [rsp+58h+arg_40]
0x180005113  mov     [r11-18h], rsi
0x180005117  mov     [r11-20h], rax
0x18000511b  mov     eax, [rsp+58h+arg_30]
0x180005122  mov     [rsp+58h+var_28], eax
0x180005126  mov     rax, [rsp+58h+arg_28]
0x18000512e  mov     [r11-30h], rax
0x180005132  mov     eax, dword ptr [rsp+58h+arg_20]
0x180005139  mov     dword ptr [rsp+58h+var_38], eax; unsigned int *
0x18000513d  call    ?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageProfileUseExisting@@$1?CLSID_WcnPageProfileUseExisting@@3U_GUID@@B$0A@$0DLH@$0MOL@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageUIBaseClass<1570,CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0,951,3307,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005142  test    eax, eax
0x180005144  js      short loc_180005193
0x180005146  lea     rdi, [rbx+0C0h]
0x18000514d  mov     r9, rdi; void **
0x180005150  lea     rcx, [rbx+40h]; this
0x180005154  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x18000515b  lea     rdx, stru_1800362D0; struct _GUID *
0x180005162  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x180005167  mov     ebx, eax
0x180005169  cmp     eax, 1
0x18000516c  jz      short loc_18000517C
0x18000516e  cmp     qword ptr [rdi], 0
0x180005172  jz      short loc_18000517C
0x180005174  test    eax, eax
0x180005176  js      short loc_180005181
0x180005178  xor     eax, eax
0x18000517a  jmp     short loc_180005193
0x18000517c  mov     ebx, 8007139Fh
0x180005181  mov     rcx, [rsi]; pv
0x180005184  call    cs:__imp_CoTaskMemFree
0x18000518a  mov     eax, ebx
0x18000518c  mov     qword ptr [rsi], 0
0x180005193  mov     rbx, [rsp+58h+arg_0]
0x180005198  mov     rsi, [rsp+58h+arg_8]
0x18000519d  add     rsp, 50h
0x1800051a1  pop     rdi
0x1800051a2  retn
```
