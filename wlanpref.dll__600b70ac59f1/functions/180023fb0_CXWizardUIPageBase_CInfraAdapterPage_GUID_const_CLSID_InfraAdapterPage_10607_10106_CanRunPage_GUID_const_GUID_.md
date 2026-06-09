# CXWizardUIPageBase<CInfraAdapterPage,&_GUID const CLSID_InfraAdapterPage,10607,10106>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180023fb0`
- end: `0x180024139`
- name: `?CanRunPage@?$CXWizardUIPageBase@VCInfraAdapterPage@@$1?CLSID_InfraAdapterPage@@3U_GUID@@B$0CJGP@$0CHHK@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180024140`

## callees

- `0x180003014`
- `0x180008560`
- `0x180023fb0`
- `0x18002d80e`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024132`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023fc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023fc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800240f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800240f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002400c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002400c`

## pseudocode

```c
__int64 __fastcall CXWizardUIPageBase<CInfraAdapterPage,&_GUID const CLSID_InfraAdapterPage,10607,10106>::CanRunPage(
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
    JUMPOUT(0x180024138LL);
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
  *((_QWORD *)v12 + 5) = CXWizardUIPageBase<CInfraAdapterPage,&_GUID const CLSID_InfraAdapterPage,10607,10106>::PageDlgProc;
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
0x180023fb0  push    rbx
0x180023fb2  push    rbp
0x180023fb3  push    rsi
0x180023fb4  push    rdi
0x180023fb5  push    r14
0x180023fb7  sub     rsp, 30h
0x180023fbb  mov     rdi, rcx
0x180023fbe  mov     esi, 68h ; 'h'
0x180023fc3  mov     ecx, esi; cb
0x180023fc5  mov     r14, rdx
0x180023fc8  call    cs:__imp_CoTaskMemAlloc
0x180023fce  mov     rbx, rax
0x180023fd1  test    rax, rax
0x180023fd4  jnz     short loc_180023FE6
0x180023fd6  mov     eax, 8007000Eh
0x180023fdb  add     rsp, 30h
0x180023fdf  pop     r14
0x180023fe1  pop     rdi
0x180023fe2  pop     rsi
0x180023fe3  pop     rbp
0x180023fe4  pop     rbx
0x180023fe5  retn
0x180023fe6  mov     r8, rsi; Size
0x180023fe9  xor     edx, edx; Val
0x180023feb  mov     rcx, rbx; void *
0x180023fee  call    memset_0
0x180023ff3  lea     rsi, [rdi+70h]
0x180023ff7  test    rsi, rsi
0x180023ffa  jz      loc_180024123
0x180024000  test    rdi, rdi
0x180024003  jz      loc_180024123
0x180024009  mov     [rsi], rdi
0x18002400c  call    cs:__imp_GetCurrentThreadId
0x180024012  lea     rcx, [rsp+58h+var_38]
0x180024017  mov     [rsp+58h+var_30], 0
0x18002401c  mov     [rsi+8], eax
0x18002401f  xor     ebp, ebp
0x180024021  lea     rax, qword_18003FA18
0x180024028  mov     [rsp+58h+var_38], rax
0x18002402d  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180024032  test    eax, eax
0x180024034  js      short loc_180024048
0x180024036  mov     rax, cs:qword_18003FA40
0x18002403d  mov     [rsi+10h], rax
0x180024041  mov     cs:qword_18003FA40, rsi
0x180024048  lea     rcx, [rsp+58h+var_38]
0x18002404d  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180024052  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180024059  mov     rcx, [rsp+58h+arg_38]
0x180024061  lea     rax, ?PageDlgProc@?$CXWizardUIPageBase@VCInfraAdapterPage@@$1?CLSID_InfraAdapterPage@@3U_GUID@@B$0CJGP@$0CHHK@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardUIPageBase<CInfraAdapterPage,&_GUID const CLSID_InfraAdapterPage,10607,10106>::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180024068  movups  xmmword ptr [rbx], xmm0
0x18002406b  movups  xmm1, xmmword ptr [rdi+0B0h]
0x180024072  movups  xmmword ptr [rbx+10h], xmm1
0x180024076  movups  xmm0, xmmword ptr [rdi+0C0h]
0x18002407d  movups  xmmword ptr [rbx+20h], xmm0
0x180024081  movups  xmm1, xmmword ptr [rdi+0D0h]
0x180024088  movups  xmmword ptr [rbx+30h], xmm1
0x18002408c  movups  xmm0, xmmword ptr [rdi+0E0h]
0x180024093  movups  xmmword ptr [rbx+40h], xmm0
0x180024097  movups  xmm1, xmmword ptr [rdi+0F0h]
0x18002409e  movups  xmmword ptr [rbx+50h], xmm1
0x1800240a2  movsd   xmm0, qword ptr [rdi+100h]
0x1800240aa  movsd   qword ptr [rbx+60h], xmm0
0x1800240af  mov     dword ptr [rbx+4], 3008h
0x1800240b6  mov     [rbx+28h], rax
0x1800240ba  mov     [rbx+38h], rbp
0x1800240be  movups  xmm0, xmmword ptr [r14]
0x1800240c2  mov     [rdi+50h], rcx
0x1800240c6  movdqu  xmmword ptr [rdi+40h], xmm0
0x1800240cb  test    rcx, rcx
0x1800240ce  jz      short loc_1800240FC
0x1800240d0  lea     r8, [rdi+58h]
0x1800240d4  cmp     [r8], rbp
0x1800240d7  jnz     short loc_1800240FC
0x1800240d9  mov     rax, [rcx]
0x1800240dc  lea     rdx, IID_IXWizardPropertyBag
0x1800240e3  mov     rax, [rax]
0x1800240e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240eb  mov     ebp, eax
0x1800240ed  test    eax, eax
0x1800240ef  jns     short loc_1800240FC
0x1800240f1  mov     rcx, rbx; pv
0x1800240f4  call    cs:__imp_CoTaskMemFree
0x1800240fa  xor     ebx, ebx
0x1800240fc  mov     rcx, [rdi]
0x1800240ff  mov     rdx, rbx
0x180024102  mov     rax, [rcx+98h]
0x180024109  mov     rcx, rdi
0x18002410c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024111  mov     rax, [rsp+58h+arg_40]
0x180024119  mov     [rax], rbx
0x18002411c  mov     eax, ebp
0x18002411e  jmp     loc_180023FDB
0x180024123  xor     r9d, r9d; lpArguments
0x180024126  xor     r8d, r8d; nNumberOfArguments
0x180024129  mov     ecx, 0C0000005h; dwExceptionCode
0x18002412e  lea     edx, [r9+1]; dwExceptionFlags
0x180024132  call    cs:__imp_RaiseException
```
