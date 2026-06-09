# CXWizardPageWTLDUIClass<CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,&__int64 ID_PageCFETransferFailed,3984>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x18000651c`
- end: `0x1800066b1`
- name: `?CanRunPage@?$CXWizardPageWTLDUIClass@VCWcnPageCFETransferFailed@@$1?CLSID_WcnPageCFETransferFailed@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFETransferFailed@@3_JA$0PJA@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, struct IXWizardSource *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800055a0`

## callees

- `0x180002294`
- `0x1800034c4`
- `0x180005740`
- `0x18000651c`
- `0x18000a494`
- `0x18002f81c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000669b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000669b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000658d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000658d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065bb`

## pseudocode

```c
__int64 __fastcall CXWizardPageWTLDUIClass<CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,&__int64 ID_PageCFETransferFailed,3984>::CanRunPage(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        struct IXWizardSource *a8,
        _QWORD *a9)
{
  __int16 v9; // bx
  __int64 result; // rax
  _DWORD *v12; // rsi
  __int64 *v13; // [rsp+50h] [rbp-38h] BYREF
  char v14; // [rsp+58h] [rbp-30h]

  v9 = a4;
  result = CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8,
             (__int64)a9);
  if ( (int)result >= 0 )
  {
    if ( (v9 & 0x620) != 0 )
    {
      v12 = CoTaskMemAlloc(0x68u);
      if ( v12 )
      {
        if ( a1 == -160 || !a1 )
        {
          RaiseException(0xC0000005, 1u, 0, 0);
          __debugbreak();
        }
        *(_QWORD *)(a1 + 160) = a1;
        v14 = 0;
        *(_DWORD *)(a1 + 168) = GetCurrentThreadId();
        v13 = qword_18004D8E8;
        if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v13) >= 0 )
        {
          *(_QWORD *)(a1 + 176) = qword_18004D910;
          qword_18004D910 = a1 + 160;
        }
        ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v13);
        memset_0(v12 + 2, 0, 0x60u);
        *v12 = 104;
        v12[1] = 4096;
        *((_QWORD *)v12 + 1) = hModule;
        *((_QWORD *)v12 + 6) = _RTDynamicCast_0(
                                 a1,
                                 0,
                                 &CXWizardPageWTLDUIClass<CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,&__int64 ID_PageCFETransferFailed,3984> `RTTI Type Descriptor',
                                 &CWcnPageCFETransferFailed `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v12 + 2) = 700;
        *((_QWORD *)v12 + 4) = L"PageCFETransferFailed";
        *((_QWORD *)v12 + 9) = 3984;
        *((_QWORD *)v12 + 5) = CXWizardPageWTLBaseClass<1570,CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,0,0,0,0,0>::PageDlgProcBase;
        (*(void (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a1 + 176LL))(a1, v12);
        result = 0;
        *a9 = v12;
      }
      else
      {
        return 2147942414LL;
      }
    }
    else
    {
      return 2147500033LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000651c  push    rbx
0x18000651e  push    rsi
0x18000651f  push    rdi
0x180006520  push    r14
0x180006522  sub     rsp, 68h
0x180006526  mov     rax, [rsp+88h+arg_38]
0x18000652e  mov     ebx, r9d
0x180006531  mov     r14, [rsp+88h+arg_40]
0x180006539  mov     rdi, rcx
0x18000653c  mov     [rsp+88h+var_48], r14; __int64
0x180006541  mov     [rsp+88h+var_50], rax; struct IXWizardSource *
0x180006546  mov     eax, [rsp+88h+arg_30]
0x18000654d  mov     [rsp+88h+var_58], eax; int
0x180006551  mov     rax, qword ptr [rsp+88h+arg_28]
0x180006559  mov     qword ptr [rsp+88h+var_60], rax; int
0x18000655e  mov     eax, [rsp+88h+arg_20]
0x180006565  mov     [rsp+88h+var_68], eax; int
0x180006569  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x18000656e  test    eax, eax
0x180006570  js      loc_1800066A7
0x180006576  test    ebx, 620h
0x18000657c  jnz     short loc_180006588
0x18000657e  mov     eax, 80004001h
0x180006583  jmp     loc_1800066A7
0x180006588  mov     ecx, 68h ; 'h'; cb
0x18000658d  call    cs:__imp_CoTaskMemAlloc
0x180006593  mov     rsi, rax
0x180006596  test    rax, rax
0x180006599  jz      loc_1800066A2
0x18000659f  lea     rbx, [rdi+0A0h]
0x1800065a6  test    rbx, rbx
0x1800065a9  jz      loc_18000668C
0x1800065af  test    rdi, rdi
0x1800065b2  jz      loc_18000668C
0x1800065b8  mov     [rbx], rdi
0x1800065bb  call    cs:__imp_GetCurrentThreadId
0x1800065c1  lea     rcx, [rsp+88h+var_38]
0x1800065c6  mov     [rsp+88h+var_30], 0
0x1800065cb  mov     [rbx+8], eax
0x1800065ce  lea     rax, qword_18004D8E8
0x1800065d5  mov     [rsp+88h+var_38], rax
0x1800065da  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800065df  test    eax, eax
0x1800065e1  js      short loc_1800065F5
0x1800065e3  mov     rax, cs:qword_18004D910
0x1800065ea  mov     [rbx+10h], rax
0x1800065ee  mov     cs:qword_18004D910, rbx
0x1800065f5  lea     rcx, [rsp+88h+var_38]
0x1800065fa  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800065ff  xor     edx, edx; Val
0x180006601  lea     rcx, [rsi+8]; void *
0x180006605  lea     r8d, [rdx+60h]; Size
0x180006609  call    memset_0
0x18000660e  mov     dword ptr [rsi], 68h ; 'h'
0x180006614  lea     r9, ??_R0?AVCWcnPageCFETransferFailed@@@8; CWcnPageCFETransferFailed `RTTI Type Descriptor'
0x18000661b  mov     dword ptr [rsi+4], 1000h
0x180006622  lea     r8, ??_R0?AV?$CXWizardPageWTLDUIClass@VCWcnPageCFETransferFailed@@$1?CLSID_WcnPageCFETransferFailed@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFETransferFailed@@3_JA$0PJA@@@@8; CXWizardPageWTLDUIClass<CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,&__int64 ID_PageCFETransferFailed,3984> `RTTI Type Descriptor'
0x180006629  mov     rax, cs:hModule
0x180006630  xor     edx, edx
0x180006632  mov     rcx, rdi
0x180006635  mov     [rsi+8], rax
0x180006639  mov     [rsp+88h+var_68], 0
0x180006641  call    __RTDynamicCast_0
0x180006646  mov     [rsi+30h], rax
0x18000664a  mov     rdx, rsi
0x18000664d  lea     rax, aPagecfetransfe; "PageCFETransferFailed"
0x180006654  mov     qword ptr [rsi+10h], 2BCh
0x18000665c  mov     [rsi+20h], rax
0x180006660  mov     rcx, rdi
0x180006663  lea     rax, ?PageDlgProcBase@?$CXWizardPageWTLBaseClass@$0GCC@VCWcnPageCFETransferFailed@@$1?CLSID_WcnPageCFETransferFailed@@3U_GUID@@B$0A@$0CLM@$0A@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageWTLBaseClass<1570,CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,0,0,0,0,0>::PageDlgProcBase(HWND__ *,uint,unsigned __int64,__int64)
0x18000666a  mov     qword ptr [rsi+48h], 0F90h
0x180006672  mov     [rsi+28h], rax
0x180006676  mov     rax, [rdi]
0x180006679  mov     rax, [rax+0B0h]
0x180006680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006685  xor     eax, eax
0x180006687  mov     [r14], rsi
0x18000668a  jmp     short loc_1800066A7
0x18000668c  xor     r9d, r9d; lpArguments
0x18000668f  xor     r8d, r8d; nNumberOfArguments
0x180006692  mov     ecx, 0C0000005h; dwExceptionCode
0x180006697  lea     edx, [r9+1]; dwExceptionFlags
0x18000669b  call    cs:__imp_RaiseException
0x1800066a1  int     3; Trap to Debugger
0x1800066a2  mov     eax, 8007000Eh
0x1800066a7  add     rsp, 68h
0x1800066ab  pop     r14
0x1800066ad  pop     rdi
0x1800066ae  pop     rsi
0x1800066af  pop     rbx
0x1800066b0  retn
```
