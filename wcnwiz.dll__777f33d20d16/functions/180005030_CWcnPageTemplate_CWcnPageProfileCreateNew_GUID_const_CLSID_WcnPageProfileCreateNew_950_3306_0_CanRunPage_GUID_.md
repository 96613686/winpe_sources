# CWcnPageTemplate<CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,950,3306,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005030`
- end: `0x1800050e3`
- name: `?CanRunPage@?$CWcnPageTemplate@VCWcnPageProfileCreateNew@@$1?CLSID_WcnPageProfileCreateNew@@3U_GUID@@B$0DLG@$0MOK@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005030`
- `0x180005ba8`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800050c4`

## pseudocode

```c
__int64 __fastcall CWcnPageTemplate<CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,950,3306,0>::CanRunPage(
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

  result = CXWizardPageUIBaseClass<1570,CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,0,950,3306,0,0,0,0>::CanRunPage(
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
0x180005030  mov     r11, rsp
0x180005033  mov     [r11+8], rbx
0x180005037  mov     [r11+10h], rsi
0x18000503b  push    rdi
0x18000503c  sub     rsp, 50h
0x180005040  mov     rax, [rsp+58h+arg_38]
0x180005048  mov     rbx, rcx
0x18000504b  mov     rsi, [rsp+58h+arg_40]
0x180005053  mov     [r11-18h], rsi
0x180005057  mov     [r11-20h], rax
0x18000505b  mov     eax, [rsp+58h+arg_30]
0x180005062  mov     [rsp+58h+var_28], eax
0x180005066  mov     rax, [rsp+58h+arg_28]
0x18000506e  mov     [r11-30h], rax
0x180005072  mov     eax, dword ptr [rsp+58h+arg_20]
0x180005079  mov     dword ptr [rsp+58h+var_38], eax; unsigned int *
0x18000507d  call    ?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageProfileCreateNew@@$1?CLSID_WcnPageProfileCreateNew@@3U_GUID@@B$0A@$0DLG@$0MOK@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageUIBaseClass<1570,CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,0,950,3306,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005082  test    eax, eax
0x180005084  js      short loc_1800050D3
0x180005086  lea     rdi, [rbx+0C0h]
0x18000508d  mov     r9, rdi; void **
0x180005090  lea     rcx, [rbx+40h]; this
0x180005094  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x18000509b  lea     rdx, stru_1800362D0; struct _GUID *
0x1800050a2  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x1800050a7  mov     ebx, eax
0x1800050a9  cmp     eax, 1
0x1800050ac  jz      short loc_1800050BC
0x1800050ae  cmp     qword ptr [rdi], 0
0x1800050b2  jz      short loc_1800050BC
0x1800050b4  test    eax, eax
0x1800050b6  js      short loc_1800050C1
0x1800050b8  xor     eax, eax
0x1800050ba  jmp     short loc_1800050D3
0x1800050bc  mov     ebx, 8007139Fh
0x1800050c1  mov     rcx, [rsi]; pv
0x1800050c4  call    cs:__imp_CoTaskMemFree
0x1800050ca  mov     eax, ebx
0x1800050cc  mov     qword ptr [rsi], 0
0x1800050d3  mov     rbx, [rsp+58h+arg_0]
0x1800050d8  mov     rsi, [rsp+58h+arg_8]
0x1800050dd  add     rsp, 50h
0x1800050e1  pop     rdi
0x1800050e2  retn
```
