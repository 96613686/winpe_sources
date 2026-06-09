# CWcnWTLDUIClass<CWcnPageApTest,&_GUID const CLSID_WcnPageApTest,0,700,&__int64 ID_PageProgressSmall,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005330`
- end: `0x1800053f8`
- name: `?CanRunPage@?$CWcnWTLDUIClass@VCWcnPageApTest@@$1?CLSID_WcnPageApTest@@3U_GUID@@B$0A@$0CLM@$1?ID_PageProgressSmall@@3_JA$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, LPVOID pv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005330`
- `0x180006048`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800053d7`

## pseudocode

```c
__int64 __fastcall CWcnWTLDUIClass<CWcnPageApTest,&_GUID const CLSID_WcnPageApTest,0,700,&__int64 ID_PageProgressSmall,0>::CanRunPage(
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
  CanRunPage = CXWizardPageWTLDUIClass<CWcnPageApTest,&_GUID const CLSID_WcnPageApTest,0,700,&__int64 ID_PageProgressSmall,0>::CanRunPage(
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
0x180005330  mov     r11, rsp
0x180005333  push    rbx
0x180005334  push    rsi
0x180005335  push    rdi
0x180005336  push    r14
0x180005338  sub     rsp, 58h
0x18000533c  mov     r14, [rsp+78h+pv]
0x180005344  lea     rax, [r11+48h]
0x180005348  mov     [r11-38h], rax
0x18000534c  mov     rsi, rcx
0x18000534f  mov     rax, [rsp+78h+arg_38]
0x180005357  mov     [r11-40h], rax
0x18000535b  mov     eax, [rsp+78h+arg_30]
0x180005362  mov     [rsp+78h+var_48], eax; int
0x180005366  mov     rax, [rsp+78h+arg_28]
0x18000536e  mov     [r11-50h], rax
0x180005372  mov     eax, dword ptr [rsp+78h+arg_20]
0x180005379  mov     dword ptr [rsp+78h+var_58], eax; unsigned int *
0x18000537d  mov     qword ptr [r14], 0
0x180005384  mov     qword ptr [r11+48h], 0
0x18000538c  call    ?CanRunPage@?$CXWizardPageWTLDUIClass@VCWcnPageApTest@@$1?CLSID_WcnPageApTest@@3U_GUID@@B$0A@$0CLM@$1?ID_PageProgressSmall@@3_JA$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageWTLDUIClass<CWcnPageApTest,&_GUID const CLSID_WcnPageApTest,0,700,&__int64 ID_PageProgressSmall,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005391  mov     ebx, eax
0x180005393  test    eax, eax
0x180005395  jnz     short loc_1800053CF
0x180005397  lea     rdi, [rsi+168h]
0x18000539e  mov     r9, rdi; void **
0x1800053a1  lea     rcx, [rsi+40h]; this
0x1800053a5  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x1800053ac  lea     rdx, stru_1800362D0; struct _GUID *
0x1800053b3  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x1800053b8  mov     ebx, eax
0x1800053ba  test    eax, eax
0x1800053bc  jnz     short loc_1800053CF
0x1800053be  mov     rax, [rdi]
0x1800053c1  test    byte ptr [rax+378h], 2
0x1800053c8  jz      short loc_1800053E9
0x1800053ca  mov     ebx, 1
0x1800053cf  mov     rcx, [rsp+78h+pv]; pv
0x1800053d7  call    cs:__imp_CoTaskMemFree
0x1800053dd  mov     eax, ebx
0x1800053df  add     rsp, 58h
0x1800053e3  pop     r14
0x1800053e5  pop     rdi
0x1800053e6  pop     rsi
0x1800053e7  pop     rbx
0x1800053e8  retn
0x1800053e9  mov     rax, [rsp+78h+pv]
0x1800053f1  xor     ecx, ecx
0x1800053f3  mov     [r14], rax
0x1800053f6  jmp     short loc_1800053D7
```
