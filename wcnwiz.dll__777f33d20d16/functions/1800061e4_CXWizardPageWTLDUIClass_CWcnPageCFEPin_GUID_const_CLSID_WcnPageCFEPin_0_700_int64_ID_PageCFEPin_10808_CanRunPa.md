# CXWizardPageWTLDUIClass<CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,&__int64 ID_PageCFEPin,10808>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x1800061e4`
- end: `0x180006379`
- name: `?CanRunPage@?$CXWizardPageWTLDUIClass@VCWcnPageCFEPin@@$1?CLSID_WcnPageCFEPin@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFEPin@@3_JA$0CKDI@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, struct IXWizardSource *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005400`

## callees

- `0x180002294`
- `0x1800034c4`
- `0x180005740`
- `0x1800061e4`
- `0x18000a494`
- `0x18002f81c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006363`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180006363`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006255`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006283`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006283`

## pseudocode

```c
__int64 __fastcall CXWizardPageWTLDUIClass<CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,&__int64 ID_PageCFEPin,10808>::CanRunPage(
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
                                 &CXWizardPageWTLDUIClass<CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,&__int64 ID_PageCFEPin,10808> `RTTI Type Descriptor',
                                 &CWcnPageCFEPin `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v12 + 2) = 700;
        *((_QWORD *)v12 + 4) = L"PageCFEPin";
        *((_QWORD *)v12 + 9) = 10808;
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
0x1800061e4  push    rbx
0x1800061e6  push    rsi
0x1800061e7  push    rdi
0x1800061e8  push    r14
0x1800061ea  sub     rsp, 68h
0x1800061ee  mov     rax, [rsp+88h+arg_38]
0x1800061f6  mov     ebx, r9d
0x1800061f9  mov     r14, [rsp+88h+arg_40]
0x180006201  mov     rdi, rcx
0x180006204  mov     [rsp+88h+var_48], r14; __int64
0x180006209  mov     [rsp+88h+var_50], rax; struct IXWizardSource *
0x18000620e  mov     eax, [rsp+88h+arg_30]
0x180006215  mov     [rsp+88h+var_58], eax; int
0x180006219  mov     rax, qword ptr [rsp+88h+arg_28]
0x180006221  mov     qword ptr [rsp+88h+var_60], rax; int
0x180006226  mov     eax, [rsp+88h+arg_20]
0x18000622d  mov     [rsp+88h+var_68], eax; int
0x180006231  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180006236  test    eax, eax
0x180006238  js      loc_18000636F
0x18000623e  test    ebx, 620h
0x180006244  jnz     short loc_180006250
0x180006246  mov     eax, 80004001h
0x18000624b  jmp     loc_18000636F
0x180006250  mov     ecx, 68h ; 'h'; cb
0x180006255  call    cs:__imp_CoTaskMemAlloc
0x18000625b  mov     rsi, rax
0x18000625e  test    rax, rax
0x180006261  jz      loc_18000636A
0x180006267  lea     rbx, [rdi+0A0h]
0x18000626e  test    rbx, rbx
0x180006271  jz      loc_180006354
0x180006277  test    rdi, rdi
0x18000627a  jz      loc_180006354
0x180006280  mov     [rbx], rdi
0x180006283  call    cs:__imp_GetCurrentThreadId
0x180006289  lea     rcx, [rsp+88h+var_38]
0x18000628e  mov     [rsp+88h+var_30], 0
0x180006293  mov     [rbx+8], eax
0x180006296  lea     rax, qword_18004D8E8
0x18000629d  mov     [rsp+88h+var_38], rax
0x1800062a2  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800062a7  test    eax, eax
0x1800062a9  js      short loc_1800062BD
0x1800062ab  mov     rax, cs:qword_18004D910
0x1800062b2  mov     [rbx+10h], rax
0x1800062b6  mov     cs:qword_18004D910, rbx
0x1800062bd  lea     rcx, [rsp+88h+var_38]
0x1800062c2  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800062c7  xor     edx, edx; Val
0x1800062c9  lea     rcx, [rsi+8]; void *
0x1800062cd  lea     r8d, [rdx+60h]; Size
0x1800062d1  call    memset_0
0x1800062d6  mov     dword ptr [rsi], 68h ; 'h'
0x1800062dc  lea     r9, ??_R0?AVCWcnPageCFEPin@@@8; CWcnPageCFEPin `RTTI Type Descriptor'
0x1800062e3  mov     dword ptr [rsi+4], 1000h
0x1800062ea  lea     r8, ??_R0?AV?$CXWizardPageWTLDUIClass@VCWcnPageCFEPin@@$1?CLSID_WcnPageCFEPin@@3U_GUID@@B$0A@$0CLM@$1?ID_PageCFEPin@@3_JA$0CKDI@@@@8; CXWizardPageWTLDUIClass<CWcnPageCFEPin,&_GUID const CLSID_WcnPageCFEPin,0,700,&__int64 ID_PageCFEPin,10808> `RTTI Type Descriptor'
0x1800062f1  mov     rax, cs:hModule
0x1800062f8  xor     edx, edx
0x1800062fa  mov     rcx, rdi
0x1800062fd  mov     [rsi+8], rax
0x180006301  mov     [rsp+88h+var_68], 0
0x180006309  call    __RTDynamicCast_0
0x18000630e  mov     [rsi+30h], rax
0x180006312  mov     rdx, rsi
0x180006315  lea     rax, aPagecfepin; "PageCFEPin"
0x18000631c  mov     qword ptr [rsi+10h], 2BCh
0x180006324  mov     [rsi+20h], rax
0x180006328  mov     rcx, rdi
0x18000632b  lea     rax, ?PageDlgProcBase@?$CXWizardPageWTLBaseClass@$0GCC@VCWcnPageCFETransferFailed@@$1?CLSID_WcnPageCFETransferFailed@@3U_GUID@@B$0A@$0CLM@$0A@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageWTLBaseClass<1570,CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,0,0,0,0,0>::PageDlgProcBase(HWND__ *,uint,unsigned __int64,__int64)
0x180006332  mov     qword ptr [rsi+48h], 2A38h
0x18000633a  mov     [rsi+28h], rax
0x18000633e  mov     rax, [rdi]
0x180006341  mov     rax, [rax+0B0h]
0x180006348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000634d  xor     eax, eax
0x18000634f  mov     [r14], rsi
0x180006352  jmp     short loc_18000636F
0x180006354  xor     r9d, r9d; lpArguments
0x180006357  xor     r8d, r8d; nNumberOfArguments
0x18000635a  mov     ecx, 0C0000005h; dwExceptionCode
0x18000635f  lea     edx, [r9+1]; dwExceptionFlags
0x180006363  call    cs:__imp_RaiseException
0x180006369  int     3; Trap to Debugger
0x18000636a  mov     eax, 8007000Eh
0x18000636f  add     rsp, 68h
0x180006373  pop     r14
0x180006375  pop     rdi
0x180006376  pop     rsi
0x180006377  pop     rbx
0x180006378  retn
```
