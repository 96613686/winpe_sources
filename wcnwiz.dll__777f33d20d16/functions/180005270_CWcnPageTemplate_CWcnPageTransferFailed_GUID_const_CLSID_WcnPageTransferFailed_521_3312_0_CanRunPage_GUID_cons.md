# CWcnPageTemplate<CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,521,3312,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005270`
- end: `0x180005323`
- name: `?CanRunPage@?$CWcnPageTemplate@VCWcnPageTransferFailed@@$1?CLSID_WcnPageTransferFailed@@3U_GUID@@B$0CAJ@$0MPA@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005270`
- `0x180005f20`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005304`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005304`

## pseudocode

```c
__int64 __fastcall CWcnPageTemplate<CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,521,3312,0>::CanRunPage(
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

  result = CXWizardPageUIBaseClass<1570,CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,0,521,3312,0,0,0,0>::CanRunPage(
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
0x180005270  mov     r11, rsp
0x180005273  mov     [r11+8], rbx
0x180005277  mov     [r11+10h], rsi
0x18000527b  push    rdi
0x18000527c  sub     rsp, 50h
0x180005280  mov     rax, [rsp+58h+arg_38]
0x180005288  mov     rbx, rcx
0x18000528b  mov     rsi, [rsp+58h+arg_40]
0x180005293  mov     [r11-18h], rsi
0x180005297  mov     [r11-20h], rax
0x18000529b  mov     eax, [rsp+58h+arg_30]
0x1800052a2  mov     [rsp+58h+var_28], eax
0x1800052a6  mov     rax, [rsp+58h+arg_28]
0x1800052ae  mov     [r11-30h], rax
0x1800052b2  mov     eax, dword ptr [rsp+58h+arg_20]
0x1800052b9  mov     dword ptr [rsp+58h+var_38], eax; unsigned int *
0x1800052bd  call    ?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageTransferFailed@@$1?CLSID_WcnPageTransferFailed@@3U_GUID@@B$0A@$0CAJ@$0MPA@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageUIBaseClass<1570,CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,0,521,3312,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x1800052c2  test    eax, eax
0x1800052c4  js      short loc_180005313
0x1800052c6  lea     rdi, [rbx+0C0h]
0x1800052cd  mov     r9, rdi; void **
0x1800052d0  lea     rcx, [rbx+40h]; this
0x1800052d4  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x1800052db  lea     rdx, stru_1800362D0; struct _GUID *
0x1800052e2  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x1800052e7  mov     ebx, eax
0x1800052e9  cmp     eax, 1
0x1800052ec  jz      short loc_1800052FC
0x1800052ee  cmp     qword ptr [rdi], 0
0x1800052f2  jz      short loc_1800052FC
0x1800052f4  test    eax, eax
0x1800052f6  js      short loc_180005301
0x1800052f8  xor     eax, eax
0x1800052fa  jmp     short loc_180005313
0x1800052fc  mov     ebx, 8007139Fh
0x180005301  mov     rcx, [rsi]; pv
0x180005304  call    cs:__imp_CoTaskMemFree
0x18000530a  mov     eax, ebx
0x18000530c  mov     qword ptr [rsi], 0
0x180005313  mov     rbx, [rsp+58h+arg_0]
0x180005318  mov     rsi, [rsp+58h+arg_8]
0x18000531d  add     rsp, 50h
0x180005321  pop     rdi
0x180005322  retn
```
