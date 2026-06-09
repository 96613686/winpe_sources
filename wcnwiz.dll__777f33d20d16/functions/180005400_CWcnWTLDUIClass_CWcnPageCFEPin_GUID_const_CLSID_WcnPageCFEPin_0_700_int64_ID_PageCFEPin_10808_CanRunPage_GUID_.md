# CWcnWTLDUIClass<CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,&__int64 ID_PageCFEPin,10808>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005400`
- end: `0x1800054c8`
- name: `?CanRunPage@?$CWcnWTLDUIClass@VCWcnPageCFEPin@@$1?CLSID_WcnPageCFEPin@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFEPin@@3_JA$0CKDI@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned int *, __int64, int, __int64, LPVOID pv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005400`
- `0x1800061e4`
- `0x18000a1bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800054a7`

## pseudocode

```c
__int64 __fastcall CWcnWTLDUIClass<CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,&__int64 ID_PageCFEPin,10808>::CanRunPage(
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
  CanRunPage = CXWizardPageWTLDUIClass<CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,&__int64 ID_PageCFEPin,10808>::CanRunPage(
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
0x180005400  mov     r11, rsp
0x180005403  push    rbx
0x180005404  push    rsi
0x180005405  push    rdi
0x180005406  push    r14
0x180005408  sub     rsp, 58h
0x18000540c  mov     r14, [rsp+78h+pv]
0x180005414  lea     rax, [r11+48h]
0x180005418  mov     [r11-38h], rax
0x18000541c  mov     rsi, rcx
0x18000541f  mov     rax, [rsp+78h+arg_38]
0x180005427  mov     [r11-40h], rax
0x18000542b  mov     eax, [rsp+78h+arg_30]
0x180005432  mov     [rsp+78h+var_48], eax; int
0x180005436  mov     rax, [rsp+78h+arg_28]
0x18000543e  mov     [r11-50h], rax
0x180005442  mov     eax, dword ptr [rsp+78h+arg_20]
0x180005449  mov     dword ptr [rsp+78h+var_58], eax; unsigned int *
0x18000544d  mov     qword ptr [r14], 0
0x180005454  mov     qword ptr [r11+48h], 0
0x18000545c  call    ?CanRunPage@?$CXWizardPageWTLDUIClass@VCWcnPageCFEPin@@$1?CLSID_WcnPageCFEPin@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFEPin@@3_JA$0CKDI@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageWTLDUIClass<CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,&__int64 ID_PageCFEPin,10808>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005461  mov     ebx, eax
0x180005463  test    eax, eax
0x180005465  jnz     short loc_18000549F
0x180005467  lea     rdi, [rsi+168h]
0x18000546e  mov     r9, rdi; void **
0x180005471  lea     rcx, [rsi+40h]; this
0x180005475  lea     r8, aWcnWizardData; "wcn.wizard.data"
0x18000547c  lea     rdx, stru_1800362D0; struct _GUID *
0x180005483  call    ?GetProperty@CXWizardClassRoot@@QEAAJPEBU_GUID@@QEAGQEAPEAXQEAK@Z; CXWizardClassRoot::GetProperty(_GUID const *,ushort * const,void * * const,ulong * const)
0x180005488  mov     ebx, eax
0x18000548a  test    eax, eax
0x18000548c  jnz     short loc_18000549F
0x18000548e  mov     rax, [rdi]
0x180005491  test    byte ptr [rax+378h], 2
0x180005498  jz      short loc_1800054B9
0x18000549a  mov     ebx, 1
0x18000549f  mov     rcx, [rsp+78h+pv]; pv
0x1800054a7  call    cs:__imp_CoTaskMemFree
0x1800054ad  mov     eax, ebx
0x1800054af  add     rsp, 58h
0x1800054b3  pop     r14
0x1800054b5  pop     rdi
0x1800054b6  pop     rsi
0x1800054b7  pop     rbx
0x1800054b8  retn
0x1800054b9  mov     rax, [rsp+78h+pv]
0x1800054c1  xor     ecx, ecx
0x1800054c3  mov     [r14], rax
0x1800054c6  jmp     short loc_1800054A7
```
