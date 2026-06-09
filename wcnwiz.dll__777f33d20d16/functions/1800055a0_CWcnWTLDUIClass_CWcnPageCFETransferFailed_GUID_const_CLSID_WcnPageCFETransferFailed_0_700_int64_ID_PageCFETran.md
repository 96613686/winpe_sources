# CWcnWTLDUIClass<CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,&__int64 ID_PageCFETransferFailed,3984>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x1800055a0`
- end: `0x180005668`
- name: `?CanRunPage@?$CWcnWTLDUIClass@VCWcnPageCFETransferFailed@@$1?CLSID_WcnPageCFETransferFailed@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFETransferFailed@@3_JA$0PJA@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, LPVOID pv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800055a0`
- `0x18000651c`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005647`

## pseudocode

```c
__int64 __fastcall CWcnWTLDUIClass<CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,&__int64 ID_PageCFETransferFailed,3984>::CanRunPage(
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
  CanRunPage = CXWizardPageWTLDUIClass<CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,&__int64 ID_PageCFETransferFailed,3984>::CanRunPage(
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
0x1800055a0  mov     r11, rsp
0x1800055a3  push    rbx
0x1800055a4  push    rsi
0x1800055a5  push    rdi
0x1800055a6  push    r14
0x1800055a8  sub     rsp, 58h
0x1800055ac  mov     r14, [rsp+78h+pv]
0x1800055b4  lea     rax, [r11+48h]
0x1800055b8  mov     [r11-38h], rax
0x1800055bc  mov     rsi, rcx
0x1800055bf  mov     rax, [rsp+78h+arg_38]
0x1800055c7  mov     [r11-40h], rax
0x1800055cb  mov     eax, [rsp+78h+arg_30]
0x1800055d2  mov     [rsp+78h+var_48], eax; int
0x1800055d6  mov     rax, [rsp+78h+arg_28]
0x1800055de  mov     [r11-50h], rax
0x1800055e2  mov     eax, dword ptr [rsp+78h+arg_20]
0x1800055e9  mov     dword ptr [rsp+78h+var_58], eax; unsigned int *
0x1800055ed  mov     qword ptr [r14], 0
0x1800055f4  mov     qword ptr [r11+48h], 0
0x1800055fc  call    ?CanRunPage@?$CXWizardPageWTLDUIClass@VCWcnPageCFETransferFailed@@$1?CLSID_WcnPageCFETransferFailed@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFETransferFailed@@3_JA$0PJA@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageWTLDUIClass<CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,&__int64 ID_PageCFETransferFailed,3984>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005601  mov     ebx, eax
0x180005603  test    eax, eax
0x180005605  jnz     short loc_18000563F
0x180005607  lea     rdi, [rsi+168h]
0x18000560e  mov     r9, rdi; void **
0x180005611  lea     rcx, [rsi+40h]; this
0x180005615  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x18000561c  lea     rdx, stru_1800362D0; struct _GUID *
0x180005623  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x180005628  mov     ebx, eax
0x18000562a  test    eax, eax
0x18000562c  jnz     short loc_18000563F
0x18000562e  mov     rax, [rdi]
0x180005631  test    byte ptr [rax+378h], 2
0x180005638  jz      short loc_180005659
0x18000563a  mov     ebx, 1
0x18000563f  mov     rcx, [rsp+78h+pv]; pv
0x180005647  call    cs:__imp_CoTaskMemFree
0x18000564d  mov     eax, ebx
0x18000564f  add     rsp, 58h
0x180005653  pop     r14
0x180005655  pop     rdi
0x180005656  pop     rsi
0x180005657  pop     rbx
0x180005658  retn
0x180005659  mov     rax, [rsp+78h+pv]
0x180005661  xor     ecx, ecx
0x180005663  mov     [r14], rax
0x180005666  jmp     short loc_180005647
```
