# CWcnWTLDUIClass<CWcnPageWlanPbcCombo,&_GUID const CLSID_WcnPageWlanPbcCombo,0,700,&__int64 ID_PageWlanPbcCombo,3601>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005670`
- end: `0x180005738`
- name: `?CanRunPage@?$CWcnWTLDUIClass@VCWcnPageWlanPbcCombo@@$1?CLSID_WcnPageWlanPbcCombo@@3U_GUID@@B$0A@$0CLM@$1?ID_PageWlanPbcCombo@@3_JA$0OBB@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, LPVOID pv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005670`
- `0x1800066b8`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005717`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005717`

## pseudocode

```c
__int64 __fastcall CWcnWTLDUIClass<CWcnPageWlanPbcCombo,&_GUID const CLSID_WcnPageWlanPbcCombo,0,700,&__int64 ID_PageWlanPbcCombo,3601>::CanRunPage(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        unsigned int *a5,
        __int64 a6,
        int a7,
        struct IXWizardSource *a8,
        _QWORD *pv)
{
  _QWORD *v9; // r14
  unsigned int CanRunPage; // ebx
  void *v12; // rcx
  unsigned int *v14; // [rsp+20h] [rbp-58h]

  v9 = pv;
  *pv = 0;
  pv = 0;
  CanRunPage = CXWizardPageWTLDUIClass<CWcnPageWlanPbcCombo,&_GUID const CLSID_WcnPageWlanPbcCombo,0,700,&__int64 ID_PageWlanPbcCombo,3601>::CanRunPage(
                 a1,
                 a2,
                 a3,
                 a4,
                 (int)a5,
                 a6,
                 a7,
                 a8,
                 &pv);
  if ( !CanRunPage )
  {
    CanRunPage = CXWizardClassRoot::GetProperty(
                   (CXWizardClassRoot *)(a1 + 64),
                   &stru_1800362D0,
                   L"wcn.wizard.data",
                   (void **const)(a1 + 360),
                   v14);
    if ( !CanRunPage )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(a1 + 360) + 888LL) & 2) == 0 )
      {
        v12 = 0;
        *v9 = pv;
        goto LABEL_6;
      }
      CanRunPage = 1;
    }
  }
  v12 = pv;
LABEL_6:
  CoTaskMemFree(v12);
  return CanRunPage;
}

```

## disassembly

```asm
0x180005670  mov     r11, rsp
0x180005673  push    rbx
0x180005674  push    rsi
0x180005675  push    rdi
0x180005676  push    r14
0x180005678  sub     rsp, 58h
0x18000567c  mov     r14, [rsp+78h+pv]
0x180005684  lea     rax, [r11+48h]
0x180005688  mov     [r11-38h], rax
0x18000568c  mov     rsi, rcx
0x18000568f  mov     rax, [rsp+78h+arg_38]
0x180005697  mov     [r11-40h], rax
0x18000569b  mov     eax, [rsp+78h+arg_30]
0x1800056a2  mov     [rsp+78h+var_48], eax; int
0x1800056a6  mov     rax, [rsp+78h+arg_28]
0x1800056ae  mov     [r11-50h], rax
0x1800056b2  mov     eax, dword ptr [rsp+78h+arg_20]
0x1800056b9  mov     dword ptr [rsp+78h+var_58], eax; unsigned int *
0x1800056bd  mov     qword ptr [r14], 0
0x1800056c4  mov     qword ptr [r11+48h], 0
0x1800056cc  call    ?CanRunPage@?$CXWizardPageWTLDUIClass@VCWcnPageWlanPbcCombo@@$1?CLSID_WcnPageWlanPbcCombo@@3U_GUID@@B$0A@$0CLM@$1?ID_PageWlanPbcCombo@@3_JA$0OBB@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageWTLDUIClass<CWcnPageWlanPbcCombo,&_GUID const CLSID_WcnPageWlanPbcCombo,0,700,&__int64 ID_PageWlanPbcCombo,3601>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x1800056d1  mov     ebx, eax
0x1800056d3  test    eax, eax
0x1800056d5  jnz     short loc_18000570F
0x1800056d7  lea     rdi, [rsi+168h]
0x1800056de  mov     r9, rdi; void **
0x1800056e1  lea     rcx, [rsi+40h]; this
0x1800056e5  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x1800056ec  lea     rdx, stru_1800362D0; struct _GUID *
0x1800056f3  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x1800056f8  mov     ebx, eax
0x1800056fa  test    eax, eax
0x1800056fc  jnz     short loc_18000570F
0x1800056fe  mov     rax, [rdi]
0x180005701  test    byte ptr [rax+378h], 2
0x180005708  jz      short loc_180005729
0x18000570a  mov     ebx, 1
0x18000570f  mov     rcx, [rsp+78h+pv]; pv
0x180005717  call    cs:__imp_CoTaskMemFree
0x18000571d  mov     eax, ebx
0x18000571f  add     rsp, 58h
0x180005723  pop     r14
0x180005725  pop     rdi
0x180005726  pop     rsi
0x180005727  pop     rbx
0x180005728  retn
0x180005729  mov     rax, [rsp+78h+pv]
0x180005731  xor     ecx, ecx
0x180005733  mov     [r14], rax
0x180005736  jmp     short loc_180005717
```
