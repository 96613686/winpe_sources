# CXWizardPageWTLDUIClass<CWcnPageWlanPbcCombo,&_GUID const CLSID_WcnPageWlanPbcCombo,0,700,&__int64 ID_PageWlanPbcCombo,3601>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x1800066b8`
- end: `0x18000684d`
- name: `?CanRunPage@?$CXWizardPageWTLDUIClass@VCWcnPageWlanPbcCombo@@$1?CLSID_WcnPageWlanPbcCombo@@3U_GUID@@B$0A@$0CLM@$1?ID_PageWlanPbcCombo@@3_JA$0OBB@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, struct IXWizardSource *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005670`

## callees

- `0x180002294`
- `0x1800034c4`
- `0x180005740`
- `0x1800066b8`
- `0x18000a494`
- `0x18002f81c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006837`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006757`

## string_xrefs

- `0x1800067e9`: `PageWlanPbcCombo`

## pseudocode

```c
__int64 __fastcall CXWizardPageWTLDUIClass<CWcnPageWlanPbcCombo,&_GUID const CLSID_WcnPageWlanPbcCombo,0,700,&__int64 ID_PageWlanPbcCombo,3601>::CanRunPage(
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
                                 &CXWizardPageWTLDUIClass<CWcnPageWlanPbcCombo,&_GUID const CLSID_WcnPageWlanPbcCombo,0,700,&__int64 ID_PageWlanPbcCombo,3601> `RTTI Type Descriptor',
                                 &CWcnPageWlanPbcCombo `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v12 + 2) = 700;
        *((_QWORD *)v12 + 4) = L"PageWlanPbcCombo";
        *((_QWORD *)v12 + 9) = 3601;
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
0x1800066b8  push    rbx
0x1800066ba  push    rsi
0x1800066bb  push    rdi
0x1800066bc  push    r14
0x1800066be  sub     rsp, 68h
0x1800066c2  mov     rax, [rsp+88h+arg_38]
0x1800066ca  mov     ebx, r9d
0x1800066cd  mov     r14, [rsp+88h+arg_40]
0x1800066d5  mov     rdi, rcx
0x1800066d8  mov     [rsp+88h+var_48], r14; __int64
0x1800066dd  mov     [rsp+88h+var_50], rax; struct IXWizardSource *
0x1800066e2  mov     eax, [rsp+88h+arg_30]
0x1800066e9  mov     [rsp+88h+var_58], eax; int
0x1800066ed  mov     rax, qword ptr [rsp+88h+arg_28]
0x1800066f5  mov     qword ptr [rsp+88h+var_60], rax; int
0x1800066fa  mov     eax, [rsp+88h+arg_20]
0x180006701  mov     [rsp+88h+var_68], eax; int
0x180006705  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x18000670a  test    eax, eax
0x18000670c  js      loc_180006843
0x180006712  test    ebx, 620h
0x180006718  jnz     short loc_180006724
0x18000671a  mov     eax, 80004001h
0x18000671f  jmp     loc_180006843
0x180006724  mov     ecx, 68h ; 'h'; cb
0x180006729  call    cs:__imp_CoTaskMemAlloc
0x18000672f  mov     rsi, rax
0x180006732  test    rax, rax
0x180006735  jz      loc_18000683E
0x18000673b  lea     rbx, [rdi+0A0h]
0x180006742  test    rbx, rbx
0x180006745  jz      loc_180006828
0x18000674b  test    rdi, rdi
0x18000674e  jz      loc_180006828
0x180006754  mov     [rbx], rdi
0x180006757  call    cs:__imp_GetCurrentThreadId
0x18000675d  lea     rcx, [rsp+88h+var_38]
0x180006762  mov     [rsp+88h+var_30], 0
0x180006767  mov     [rbx+8], eax
0x18000676a  lea     rax, qword_18004D8E8
0x180006771  mov     [rsp+88h+var_38], rax
0x180006776  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000677b  test    eax, eax
0x18000677d  js      short loc_180006791
0x18000677f  mov     rax, cs:qword_18004D910
0x180006786  mov     [rbx+10h], rax
0x18000678a  mov     cs:qword_18004D910, rbx
0x180006791  lea     rcx, [rsp+88h+var_38]
0x180006796  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000679b  xor     edx, edx; Val
0x18000679d  lea     rcx, [rsi+8]; void *
0x1800067a1  lea     r8d, [rdx+60h]; Size
0x1800067a5  call    memset_0
0x1800067aa  mov     dword ptr [rsi], 68h ; 'h'
0x1800067b0  lea     r9, ??_R0?AVCWcnPageWlanPbcCombo@@@8; CWcnPageWlanPbcCombo `RTTI Type Descriptor'
0x1800067b7  mov     dword ptr [rsi+4], 1000h
0x1800067be  lea     r8, ??_R0?AV?$CXWizardPageWTLDUIClass@VCWcnPageWlanPbcCombo@@$1?CLSID_WcnPageWlanPbcCombo@@3U_GUID@@B$0A@$0CLM@$1?ID_PageWlanPbcCombo@@3_JA$0OBB@@@@8; CXWizardPageWTLDUIClass<CWcnPageWlanPbcCombo,&_GUID const CLSID_WcnPageWlanPbcCombo,0,700,&__int64 ID_PageWlanPbcCombo,3601> `RTTI Type Descriptor'
0x1800067c5  mov     rax, cs:hModule
0x1800067cc  xor     edx, edx
0x1800067ce  mov     rcx, rdi
0x1800067d1  mov     [rsi+8], rax
0x1800067d5  mov     [rsp+88h+var_68], 0
0x1800067dd  call    __RTDynamicCast_0
0x1800067e2  mov     [rsi+30h], rax
0x1800067e6  mov     rdx, rsi
0x1800067e9  lea     rax, aPagewlanpbccom_0; "PageWlanPbcCombo"
0x1800067f0  mov     qword ptr [rsi+10h], 2BCh
0x1800067f8  mov     [rsi+20h], rax
0x1800067fc  mov     rcx, rdi
0x1800067ff  lea     rax, ?PageDlgProcBase@?$CXWizardPageWTLBaseClass@$0GCC@VCWcnPageCFETransferFailed@@$1?CLSID_WcnPageCFETransferFailed@@3U_GUID@@B$0A@$0CLM@$0A@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageWTLBaseClass<1570,CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,0,0,0,0,0>::PageDlgProcBase(HWND__ *,uint,unsigned __int64,__int64)
0x180006806  mov     qword ptr [rsi+48h], 0E11h
0x18000680e  mov     [rsi+28h], rax
0x180006812  mov     rax, [rdi]
0x180006815  mov     rax, [rax+0B0h]
0x18000681c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006821  xor     eax, eax
0x180006823  mov     [r14], rsi
0x180006826  jmp     short loc_180006843
0x180006828  xor     r9d, r9d; lpArguments
0x18000682b  xor     r8d, r8d; nNumberOfArguments
0x18000682e  mov     ecx, 0C0000005h; dwExceptionCode
0x180006833  lea     edx, [r9+1]; dwExceptionFlags
0x180006837  call    cs:__imp_RaiseException
0x18000683d  int     3; Trap to Debugger
0x18000683e  mov     eax, 8007000Eh
0x180006843  add     rsp, 68h
0x180006847  pop     r14
0x180006849  pop     rdi
0x18000684a  pop     rsi
0x18000684b  pop     rbx
0x18000684c  retn
```
