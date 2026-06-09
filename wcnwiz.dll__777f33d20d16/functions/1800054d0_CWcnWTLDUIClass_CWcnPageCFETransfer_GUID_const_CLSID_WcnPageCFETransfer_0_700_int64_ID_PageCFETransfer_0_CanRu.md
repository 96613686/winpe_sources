# CWcnWTLDUIClass<CWcnPageCFETransfer,&_GUID const CLSID_WcnPageCFETransfer,0,700,&__int64 ID_PageCFETransfer,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x1800054d0`
- end: `0x180005598`
- name: `?CanRunPage@?$CWcnWTLDUIClass@VCWcnPageCFETransfer@@$1?CLSID_WcnPageCFETransfer@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFETransfer@@3_JA$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, LPVOID pv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800054d0`
- `0x180006380`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005577`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005577`

## pseudocode

```c
__int64 __fastcall CWcnWTLDUIClass<CWcnPageCFETransfer,&_GUID const CLSID_WcnPageCFETransfer,0,700,&__int64 ID_PageCFETransfer,0>::CanRunPage(
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
  CanRunPage = CXWizardPageWTLDUIClass<CWcnPageCFETransfer,&_GUID const CLSID_WcnPageCFETransfer,0,700,&__int64 ID_PageCFETransfer,0>::CanRunPage(
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
0x1800054d0  mov     r11, rsp
0x1800054d3  push    rbx
0x1800054d4  push    rsi
0x1800054d5  push    rdi
0x1800054d6  push    r14
0x1800054d8  sub     rsp, 58h
0x1800054dc  mov     r14, [rsp+78h+pv]
0x1800054e4  lea     rax, [r11+48h]
0x1800054e8  mov     [r11-38h], rax
0x1800054ec  mov     rsi, rcx
0x1800054ef  mov     rax, [rsp+78h+arg_38]
0x1800054f7  mov     [r11-40h], rax
0x1800054fb  mov     eax, [rsp+78h+arg_30]
0x180005502  mov     [rsp+78h+var_48], eax; int
0x180005506  mov     rax, [rsp+78h+arg_28]
0x18000550e  mov     [r11-50h], rax
0x180005512  mov     eax, dword ptr [rsp+78h+arg_20]
0x180005519  mov     dword ptr [rsp+78h+var_58], eax; unsigned int *
0x18000551d  mov     qword ptr [r14], 0
0x180005524  mov     qword ptr [r11+48h], 0
0x18000552c  call    ?CanRunPage@?$CXWizardPageWTLDUIClass@VCWcnPageCFETransfer@@$1?CLSID_WcnPageCFETransfer@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFETransfer@@3_JA$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageWTLDUIClass<CWcnPageCFETransfer,&_GUID const CLSID_WcnPageCFETransfer,0,700,&__int64 ID_PageCFETransfer,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005531  mov     ebx, eax
0x180005533  test    eax, eax
0x180005535  jnz     short loc_18000556F
0x180005537  lea     rdi, [rsi+168h]
0x18000553e  mov     r9, rdi; void **
0x180005541  lea     rcx, [rsi+40h]; this
0x180005545  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x18000554c  lea     rdx, stru_1800362D0; struct _GUID *
0x180005553  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x180005558  mov     ebx, eax
0x18000555a  test    eax, eax
0x18000555c  jnz     short loc_18000556F
0x18000555e  mov     rax, [rdi]
0x180005561  test    byte ptr [rax+378h], 2
0x180005568  jz      short loc_180005589
0x18000556a  mov     ebx, 1
0x18000556f  mov     rcx, [rsp+78h+pv]; pv
0x180005577  call    cs:__imp_CoTaskMemFree
0x18000557d  mov     eax, ebx
0x18000557f  add     rsp, 58h
0x180005583  pop     r14
0x180005585  pop     rdi
0x180005586  pop     rsi
0x180005587  pop     rbx
0x180005588  retn
0x180005589  mov     rax, [rsp+78h+pv]
0x180005591  xor     ecx, ecx
0x180005593  mov     [r14], rax
0x180005596  jmp     short loc_180005577
```
