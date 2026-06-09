# CXWizardPageWTLDUIClass<CWcnPageApTest,&_GUID const CLSID_WcnPageApTest,0,700,&__int64 ID_PageProgressSmall,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180006048`
- end: `0x1800061dd`
- name: `?CanRunPage@?$CXWizardPageWTLDUIClass@VCWcnPageApTest@@$1?CLSID_WcnPageApTest@@3U_GUID@@B$0A@$0CLM@$1?ID_PageProgressSmall@@3_JA$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `405`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, struct IXWizardSource *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005330`

## callees

- `0x180002294`
- `0x1800034c4`
- `0x180005740`
- `0x180006048`
- `0x18000a494`
- `0x18002f81c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800061c7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800061c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800060b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800060b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060e7`

## pseudocode

```c
__int64 __fastcall CXWizardPageWTLDUIClass<CWcnPageApTest,&_GUID const CLSID_WcnPageApTest,0,700,&__int64 ID_PageProgressSmall,0>::CanRunPage(
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
                                 &CXWizardPageWTLDUIClass<CWcnPageApTest,&_GUID const CLSID_WcnPageApTest,0,700,&__int64 ID_PageProgressSmall,0> `RTTI Type Descriptor',
                                 &CWcnPageApTest `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v12 + 2) = 700;
        *((_QWORD *)v12 + 4) = L"PageProgressSmall";
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
0x180006048  push    rbx
0x18000604a  push    rsi
0x18000604b  push    rdi
0x18000604c  push    r14
0x18000604e  sub     rsp, 68h
0x180006052  mov     rax, [rsp+88h+arg_38]
0x18000605a  mov     ebx, r9d
0x18000605d  mov     r14, [rsp+88h+arg_40]
0x180006065  mov     rdi, rcx
0x180006068  mov     [rsp+88h+var_48], r14; __int64
0x18000606d  mov     [rsp+88h+var_50], rax; struct IXWizardSource *
0x180006072  mov     eax, [rsp+88h+arg_30]
0x180006079  mov     [rsp+88h+var_58], eax; int
0x18000607d  mov     rax, qword ptr [rsp+88h+arg_28]
0x180006085  mov     qword ptr [rsp+88h+var_60], rax; int
0x18000608a  mov     eax, [rsp+88h+arg_20]
0x180006091  mov     [rsp+88h+var_68], eax; int
0x180006095  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x18000609a  test    eax, eax
0x18000609c  js      loc_1800061D3
0x1800060a2  test    ebx, 620h
0x1800060a8  jnz     short loc_1800060B4
0x1800060aa  mov     eax, 80004001h
0x1800060af  jmp     loc_1800061D3
0x1800060b4  mov     ecx, 68h ; 'h'; cb
0x1800060b9  call    cs:__imp_CoTaskMemAlloc
0x1800060bf  mov     rsi, rax
0x1800060c2  test    rax, rax
0x1800060c5  jz      loc_1800061CE
0x1800060cb  lea     rbx, [rdi+0A0h]
0x1800060d2  test    rbx, rbx
0x1800060d5  jz      loc_1800061B8
0x1800060db  test    rdi, rdi
0x1800060de  jz      loc_1800061B8
0x1800060e4  mov     [rbx], rdi
0x1800060e7  call    cs:__imp_GetCurrentThreadId
0x1800060ed  lea     rcx, [rsp+88h+var_38]
0x1800060f2  mov     [rsp+88h+var_30], 0
0x1800060f7  mov     [rbx+8], eax
0x1800060fa  lea     rax, qword_18004D8E8
0x180006101  mov     [rsp+88h+var_38], rax
0x180006106  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000610b  test    eax, eax
0x18000610d  js      short loc_180006121
0x18000610f  mov     rax, cs:qword_18004D910
0x180006116  mov     [rbx+10h], rax
0x18000611a  mov     cs:qword_18004D910, rbx
0x180006121  lea     rcx, [rsp+88h+var_38]
0x180006126  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000612b  xor     edx, edx; Val
0x18000612d  lea     rcx, [rsi+8]; void *
0x180006131  lea     r8d, [rdx+60h]; Size
0x180006135  call    memset_0
0x18000613a  mov     dword ptr [rsi], 68h ; 'h'
0x180006140  lea     r9, ??_R0?AVCWcnPageApTest@@@8; CWcnPageApTest `RTTI Type Descriptor'
0x180006147  mov     dword ptr [rsi+4], 1000h
0x18000614e  lea     r8, ??_R0?AV?$CXWizardPageWTLDUIClass@VCWcnPageApTest@@$1?CLSID_WcnPageApTest@@3U_GUID@@B$0A@$0CLM@$1?ID_PageProgressSmall@@3_JA$0A@@@@8; CXWizardPageWTLDUIClass<CWcnPageApTest,&_GUID const CLSID_WcnPageApTest,0,700,&__int64 ID_PageProgressSmall,0> `RTTI Type Descriptor'
0x180006155  mov     rax, cs:hModule
0x18000615c  xor     edx, edx
0x18000615e  mov     rcx, rdi
0x180006161  mov     [rsi+8], rax
0x180006165  mov     [rsp+88h+var_68], 0
0x18000616d  call    __RTDynamicCast_0
0x180006172  mov     [rsi+30h], rax
0x180006176  mov     rdx, rsi
0x180006179  lea     rax, aPageprogresssm; "PageProgressSmall"
0x180006180  mov     qword ptr [rsi+10h], 2BCh
0x180006188  mov     [rsi+20h], rax
0x18000618c  mov     rcx, rdi
0x18000618f  lea     rax, ?PageDlgProcBase@?$CXWizardPageWTLBaseClass@$0GCC@VCWcnPageCFETransferFailed@@$1?CLSID_WcnPageCFETransferFailed@@3U_GUID@@B$0A@$0CLM@$0A@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageWTLBaseClass<1570,CWcnPageCFETransferFailed,&_GUID const CLSID_WcnPageCFETransferFailed,0,700,0,0,0,0,0>::PageDlgProcBase(HWND__ *,uint,unsigned __int64,__int64)
0x180006196  mov     qword ptr [rsi+48h], 0
0x18000619e  mov     [rsi+28h], rax
0x1800061a2  mov     rax, [rdi]
0x1800061a5  mov     rax, [rax+0B0h]
0x1800061ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061b1  xor     eax, eax
0x1800061b3  mov     [r14], rsi
0x1800061b6  jmp     short loc_1800061D3
0x1800061b8  xor     r9d, r9d; lpArguments
0x1800061bb  xor     r8d, r8d; nNumberOfArguments
0x1800061be  mov     ecx, 0C0000005h; dwExceptionCode
0x1800061c3  lea     edx, [r9+1]; dwExceptionFlags
0x1800061c7  call    cs:__imp_RaiseException
0x1800061cd  int     3; Trap to Debugger
0x1800061ce  mov     eax, 8007000Eh
0x1800061d3  add     rsp, 68h
0x1800061d7  pop     r14
0x1800061d9  pop     rdi
0x1800061da  pop     rsi
0x1800061db  pop     rbx
0x1800061dc  retn
```
