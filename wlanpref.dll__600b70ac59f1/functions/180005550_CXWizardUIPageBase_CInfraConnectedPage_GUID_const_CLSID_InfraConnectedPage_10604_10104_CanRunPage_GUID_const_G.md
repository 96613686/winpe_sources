# CXWizardUIPageBase<CInfraConnectedPage,&_GUID const CLSID_InfraConnectedPage,10604,10104>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005550`
- end: `0x1800056d9`
- name: `?CanRunPage@?$CXWizardUIPageBase@VCInfraConnectedPage@@$1?CLSID_InfraConnectedPage@@3U_GUID@@B$0CJGM@$0CHHI@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180003014`
- `0x180005550`
- `0x180008560`
- `0x18002d80e`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800056d2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800056d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005568`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005694`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055ac`

## pseudocode

```c
__int64 __fastcall CXWizardUIPageBase<CInfraConnectedPage,&_GUID const CLSID_InfraConnectedPage,10604,10104>::CanRunPage(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        __int64 (__fastcall ***a8)(_QWORD, GUID *),
        _QWORD *a9)
{
  _OWORD *v11; // rax
  _OWORD *v12; // rbx
  int v14; // ebp
  __int128 v15; // xmm0
  __int64 *v16; // [rsp+20h] [rbp-38h] BYREF
  char v17; // [rsp+28h] [rbp-30h]

  v11 = CoTaskMemAlloc(0x68u);
  v12 = v11;
  if ( !v11 )
    return 2147942414LL;
  memset_0(v11, 0, 0x68u);
  if ( a1 == -112 || !a1 )
  {
    RaiseException(0xC0000005, 1u, 0, 0);
    JUMPOUT(0x1800056D8LL);
  }
  *(_QWORD *)(a1 + 112) = a1;
  v17 = 0;
  *(_DWORD *)(a1 + 120) = GetCurrentThreadId();
  v14 = 0;
  v16 = qword_18003FA18;
  if ( (int)ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v16) >= 0 )
  {
    *(_QWORD *)(a1 + 128) = qword_18003FA40;
    qword_18003FA40 = a1 + 112;
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v16);
  *v12 = *(_OWORD *)(a1 + 160);
  v12[1] = *(_OWORD *)(a1 + 176);
  v12[2] = *(_OWORD *)(a1 + 192);
  v12[3] = *(_OWORD *)(a1 + 208);
  v12[4] = *(_OWORD *)(a1 + 224);
  v12[5] = *(_OWORD *)(a1 + 240);
  *((_QWORD *)v12 + 12) = *(_QWORD *)(a1 + 256);
  *((_DWORD *)v12 + 1) = 12296;
  *((_QWORD *)v12 + 5) = CXWizardUIPageBase<CVANSettingsPage,&_GUID const CLSID_VANSettingsPage,10608,10107>::PageDlgProc;
  *((_QWORD *)v12 + 7) = 0;
  v15 = *a2;
  *(_QWORD *)(a1 + 80) = a8;
  *(_OWORD *)(a1 + 64) = v15;
  if ( a8 && !*(_QWORD *)(a1 + 88) )
  {
    v14 = (**a8)(a8, &IID_IXWizardPropertyBag);
    if ( v14 < 0 )
    {
      CoTaskMemFree(v12);
      v12 = 0;
    }
  }
  (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)a1 + 152LL))(a1, v12);
  *a9 = v12;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180005550  push    rbx
0x180005552  push    rbp
0x180005553  push    rsi
0x180005554  push    rdi
0x180005555  push    r14
0x180005557  sub     rsp, 30h
0x18000555b  mov     rdi, rcx
0x18000555e  mov     esi, 68h ; 'h'
0x180005563  mov     ecx, esi; cb
0x180005565  mov     r14, rdx
0x180005568  call    cs:__imp_CoTaskMemAlloc
0x18000556e  mov     rbx, rax
0x180005571  test    rax, rax
0x180005574  jnz     short loc_180005586
0x180005576  mov     eax, 8007000Eh
0x18000557b  add     rsp, 30h
0x18000557f  pop     r14
0x180005581  pop     rdi
0x180005582  pop     rsi
0x180005583  pop     rbp
0x180005584  pop     rbx
0x180005585  retn
0x180005586  mov     r8, rsi; Size
0x180005589  xor     edx, edx; Val
0x18000558b  mov     rcx, rbx; void *
0x18000558e  call    memset_0
0x180005593  lea     rsi, [rdi+70h]
0x180005597  test    rsi, rsi
0x18000559a  jz      loc_1800056C3
0x1800055a0  test    rdi, rdi
0x1800055a3  jz      loc_1800056C3
0x1800055a9  mov     [rsi], rdi
0x1800055ac  call    cs:__imp_GetCurrentThreadId
0x1800055b2  lea     rcx, [rsp+58h+var_38]
0x1800055b7  mov     [rsp+58h+var_30], 0
0x1800055bc  mov     [rsi+8], eax
0x1800055bf  xor     ebp, ebp
0x1800055c1  lea     rax, qword_18003FA18
0x1800055c8  mov     [rsp+58h+var_38], rax
0x1800055cd  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800055d2  test    eax, eax
0x1800055d4  js      short loc_1800055E8
0x1800055d6  mov     rax, cs:qword_18003FA40
0x1800055dd  mov     [rsi+10h], rax
0x1800055e1  mov     cs:qword_18003FA40, rsi
0x1800055e8  lea     rcx, [rsp+58h+var_38]
0x1800055ed  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800055f2  movups  xmm0, xmmword ptr [rdi+0A0h]
0x1800055f9  mov     rcx, [rsp+58h+arg_38]
0x180005601  lea     rax, ?PageDlgProc@?$CXWizardUIPageBase@VCVANSettingsPage@@$1?CLSID_VANSettingsPage@@3U_GUID@@B$0CJHA@$0CHHL@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardUIPageBase<CVANSettingsPage,&_GUID const CLSID_VANSettingsPage,10608,10107>::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180005608  movups  xmmword ptr [rbx], xmm0
0x18000560b  movups  xmm1, xmmword ptr [rdi+0B0h]
0x180005612  movups  xmmword ptr [rbx+10h], xmm1
0x180005616  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18000561d  movups  xmmword ptr [rbx+20h], xmm0
0x180005621  movups  xmm1, xmmword ptr [rdi+0D0h]
0x180005628  movups  xmmword ptr [rbx+30h], xmm1
0x18000562c  movups  xmm0, xmmword ptr [rdi+0E0h]
0x180005633  movups  xmmword ptr [rbx+40h], xmm0
0x180005637  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18000563e  movups  xmmword ptr [rbx+50h], xmm1
0x180005642  movsd   xmm0, qword ptr [rdi+100h]
0x18000564a  movsd   qword ptr [rbx+60h], xmm0
0x18000564f  mov     dword ptr [rbx+4], 3008h
0x180005656  mov     [rbx+28h], rax
0x18000565a  mov     [rbx+38h], rbp
0x18000565e  movups  xmm0, xmmword ptr [r14]
0x180005662  mov     [rdi+50h], rcx
0x180005666  movdqu  xmmword ptr [rdi+40h], xmm0
0x18000566b  test    rcx, rcx
0x18000566e  jz      short loc_18000569C
0x180005670  lea     r8, [rdi+58h]
0x180005674  cmp     [r8], rbp
0x180005677  jnz     short loc_18000569C
0x180005679  mov     rax, [rcx]
0x18000567c  lea     rdx, IID_IXWizardPropertyBag
0x180005683  mov     rax, [rax]
0x180005686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000568b  mov     ebp, eax
0x18000568d  test    eax, eax
0x18000568f  jns     short loc_18000569C
0x180005691  mov     rcx, rbx; pv
0x180005694  call    cs:__imp_CoTaskMemFree
0x18000569a  xor     ebx, ebx
0x18000569c  mov     rcx, [rdi]
0x18000569f  mov     rdx, rbx
0x1800056a2  mov     rax, [rcx+98h]
0x1800056a9  mov     rcx, rdi
0x1800056ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b1  mov     rax, [rsp+58h+arg_40]
0x1800056b9  mov     [rax], rbx
0x1800056bc  mov     eax, ebp
0x1800056be  jmp     loc_18000557B
0x1800056c3  xor     r9d, r9d; lpArguments
0x1800056c6  xor     r8d, r8d; nNumberOfArguments
0x1800056c9  mov     ecx, 0C0000005h; dwExceptionCode
0x1800056ce  lea     edx, [r9+1]; dwExceptionFlags
0x1800056d2  call    cs:__imp_RaiseException
```
