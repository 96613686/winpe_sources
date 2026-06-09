# CXWizardPageWTLDUIClass<CWcnPageCFETransfer,&_GUID const CLSID_WcnPageCFETransfer,0,700,&__int64 ID_PageCFETransfer,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180006380`
- end: `0x180006515`
- name: `?CanRunPage@?$CXWizardPageWTLDUIClass@VCWcnPageCFETransfer@@$1?CLSID_WcnPageCFETransfer@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFETransfer@@3_JA$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, struct IXWizardSource *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800054d0`

## callees

- `0x180002294`
- `0x1800034c4`
- `0x180005740`
- `0x180006380`
- `0x18000a494`
- `0x18002f81c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800064ff`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800064ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800063f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800063f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000641f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000641f`

## pseudocode

```c
__int64 __fastcall CXWizardPageWTLDUIClass<CWcnPageCFETransfer,&_GUID const CLSID_WcnPageCFETransfer,0,700,&__int64 ID_PageCFETransfer,0>::CanRunPage(
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
                                 &CXWizardPageWTLDUIClass<CWcnPageCFETransfer,&_GUID const CLSID_WcnPageCFETransfer,0,700,&__int64 ID_PageCFETransfer,0> `RTTI Type Descriptor',
                                 &CWcnPageCFETransfer `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v12 + 2) = 700;
        *((_QWORD *)v12 + 4) = L"PageCFETransfer";
        *((_QWORD *)v12 + 9) = 0;
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
0x180006380  push    rbx
0x180006382  push    rsi
0x180006383  push    rdi
0x180006384  push    r14
0x180006386  sub     rsp, 68h
0x18000638a  mov     rax, [rsp+88h+arg_38]
0x180006392  mov     ebx, r9d
0x180006395  mov     r14, [rsp+88h+arg_40]
0x18000639d  mov     rdi, rcx
0x1800063a0  mov     [rsp+88h+var_48], r14; __int64
0x1800063a5  mov     [rsp+88h+var_50], rax; struct IXWizardSource *
0x1800063aa  mov     eax, [rsp+88h+arg_30]
0x1800063b1  mov     [rsp+88h+var_58], eax; int
0x1800063b5  mov     rax, qword ptr [rsp+88h+arg_28]
0x1800063bd  mov     qword ptr [rsp+88h+var_60], rax; int
0x1800063c2  mov     eax, [rsp+88h+arg_20]
0x1800063c9  mov     [rsp+88h+var_68], eax; int
0x1800063cd  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x1800063d2  test    eax, eax
0x1800063d4  js      loc_18000650B
0x1800063da  test    ebx, 620h
0x1800063e0  jnz     short loc_1800063EC
0x1800063e2  mov     eax, 80004001h
0x1800063e7  jmp     loc_18000650B
0x1800063ec  mov     ecx, 68h ; 'h'; cb
0x1800063f1  call    cs:__imp_CoTaskMemAlloc
0x1800063f7  mov     rsi, rax
0x1800063fa  test    rax, rax
0x1800063fd  jz      loc_180006506
0x180006403  lea     rbx, [rdi+0A0h]
0x18000640a  test    rbx, rbx
0x18000640d  jz      loc_1800064F0
0x180006413  test    rdi, rdi
0x180006416  jz      loc_1800064F0
0x18000641c  mov     [rbx], rdi
0x18000641f  call    cs:__imp_GetCurrentThreadId
0x180006425  lea     rcx, [rsp+88h+var_38]
0x18000642a  mov     [rsp+88h+var_30], 0
0x18000642f  mov     [rbx+8], eax
0x180006432  lea     rax, qword_18004D8E8
0x180006439  mov     [rsp+88h+var_38], rax
0x18000643e  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180006443  test    eax, eax
0x180006445  js      short loc_180006459
0x180006447  mov     rax, cs:qword_18004D910
0x18000644e  mov     [rbx+10h], rax
0x180006452  mov     cs:qword_18004D910, rbx
0x180006459  lea     rcx, [rsp+88h+var_38]
0x18000645e  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180006463  xor     edx, edx; Val
0x180006465  lea     rcx, [rsi+8]; void *
0x180006469  lea     r8d, [rdx+60h]; Size
0x18000646d  call    memset_0
0x180006472  mov     dword ptr [rsi], 68h ; 'h'
0x180006478  lea     r9, ??_R0?AVCWcnPageCFETransfer@@@8; CWcnPageCFETransfer `RTTI Type Descriptor'
0x18000647f  mov     dword ptr [rsi+4], 1000h
0x180006486  lea     r8, ??_R0?AV?$CXWizardPageWTLDUIClass@VCWcnPageCFETransfer@@$1?CLSID_WcnPageCFETransfer@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFETransfer@@3_JA$0A@@@@8; CXWizardPageWTLDUIClass<CWcnPageCFETransfer,&_GUID const CLSID_WcnPageCFETransfer,0,700,&__int64 ID_PageCFETransfer,0> `RTTI Type Descriptor'
0x18000648d  mov     rax, cs:hModule
0x180006494  xor     edx, edx
0x180006496  mov     rcx, rdi
0x180006499  mov     [rsi+8], rax
0x18000649d  mov     [rsp+88h+var_68], 0
0x1800064a5  call    __RTDynamicCast_0
0x1800064aa  mov     [rsi+30h], rax
0x1800064ae  mov     rdx, rsi
0x1800064b1  lea     rax, aPagecfetransfe_0; "PageCFETransfer"
0x1800064b8  mov     qword ptr [rsi+10h], 2BCh
0x1800064c0  mov     [rsi+20h], rax
0x1800064c4  mov     rcx, rdi
0x1800064c7  lea     rax, ?PageDlgProcBase@?$CXWizardPageWTLBaseClass@$0GCC@VCWcnPageCFETransferFailed@@$1?CLSID_WcnPageCFETransferFailed@@3U_GUID@@B$0A@$0CLM@$0A@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageWTLBaseClass<1570,CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,0,0,0,0,0>::PageDlgProcBase(HWND__ *,uint,unsigned __int64,__int64)
0x1800064ce  mov     qword ptr [rsi+48h], 0
0x1800064d6  mov     [rsi+28h], rax
0x1800064da  mov     rax, [rdi]
0x1800064dd  mov     rax, [rax+0B0h]
0x1800064e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e9  xor     eax, eax
0x1800064eb  mov     [r14], rsi
0x1800064ee  jmp     short loc_18000650B
0x1800064f0  xor     r9d, r9d; lpArguments
0x1800064f3  xor     r8d, r8d; nNumberOfArguments
0x1800064f6  mov     ecx, 0C0000005h; dwExceptionCode
0x1800064fb  lea     edx, [r9+1]; dwExceptionFlags
0x1800064ff  call    cs:__imp_RaiseException
0x180006505  int     3; Trap to Debugger
0x180006506  mov     eax, 8007000Eh
0x18000650b  add     rsp, 68h
0x18000650f  pop     r14
0x180006511  pop     rdi
0x180006512  pop     rsi
0x180006513  pop     rbx
0x180006514  retn
```
