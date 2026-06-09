# CXWizardUIPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602,10102>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x1800157ec`
- end: `0x180015975`
- name: `?CanRunPage@?$CXWizardUIPageBase@VCInfraSetupPage@@$1?CLSID_InfraSetupPage@@3U_GUID@@B$0CJGK@$0CHHG@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180015980`

## callees

- `0x180003014`
- `0x180008560`
- `0x1800157ec`
- `0x18002d80e`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001596e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001596e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015804`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015804`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015930`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015930`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015848`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015848`

## pseudocode

```c
__int64 __fastcall CXWizardUIPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602,10102>::CanRunPage(
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
    JUMPOUT(0x180015974LL);
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
  *((_QWORD *)v12 + 5) = CXWizardUIPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602,10102>::PageDlgProc;
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
0x1800157ec  push    rbx
0x1800157ee  push    rbp
0x1800157ef  push    rsi
0x1800157f0  push    rdi
0x1800157f1  push    r14
0x1800157f3  sub     rsp, 30h
0x1800157f7  mov     rdi, rcx
0x1800157fa  mov     esi, 68h ; 'h'
0x1800157ff  mov     ecx, esi; cb
0x180015801  mov     r14, rdx
0x180015804  call    cs:__imp_CoTaskMemAlloc
0x18001580a  mov     rbx, rax
0x18001580d  test    rax, rax
0x180015810  jnz     short loc_180015822
0x180015812  mov     eax, 8007000Eh
0x180015817  add     rsp, 30h
0x18001581b  pop     r14
0x18001581d  pop     rdi
0x18001581e  pop     rsi
0x18001581f  pop     rbp
0x180015820  pop     rbx
0x180015821  retn
0x180015822  mov     r8, rsi; Size
0x180015825  xor     edx, edx; Val
0x180015827  mov     rcx, rbx; void *
0x18001582a  call    memset_0
0x18001582f  lea     rsi, [rdi+70h]
0x180015833  test    rsi, rsi
0x180015836  jz      loc_18001595F
0x18001583c  test    rdi, rdi
0x18001583f  jz      loc_18001595F
0x180015845  mov     [rsi], rdi
0x180015848  call    cs:__imp_GetCurrentThreadId
0x18001584e  lea     rcx, [rsp+58h+var_38]
0x180015853  mov     [rsp+58h+var_30], 0
0x180015858  mov     [rsi+8], eax
0x18001585b  xor     ebp, ebp
0x18001585d  lea     rax, qword_18003FA18
0x180015864  mov     [rsp+58h+var_38], rax
0x180015869  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18001586e  test    eax, eax
0x180015870  js      short loc_180015884
0x180015872  mov     rax, cs:qword_18003FA40
0x180015879  mov     [rsi+10h], rax
0x18001587d  mov     cs:qword_18003FA40, rsi
0x180015884  lea     rcx, [rsp+58h+var_38]
0x180015889  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001588e  movups  xmm0, xmmword ptr [rdi+0A0h]
0x180015895  mov     rcx, [rsp+58h+arg_38]
0x18001589d  lea     rax, ?PageDlgProc@?$CXWizardUIPageBase@VCInfraSetupPage@@$1?CLSID_InfraSetupPage@@3U_GUID@@B$0CJGK@$0CHHG@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardUIPageBase<CInfraSetupPage,&_GUID const CLSID_InfraSetupPage,10602,10102>::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800158a4  movups  xmmword ptr [rbx], xmm0
0x1800158a7  movups  xmm1, xmmword ptr [rdi+0B0h]
0x1800158ae  movups  xmmword ptr [rbx+10h], xmm1
0x1800158b2  movups  xmm0, xmmword ptr [rdi+0C0h]
0x1800158b9  movups  xmmword ptr [rbx+20h], xmm0
0x1800158bd  movups  xmm1, xmmword ptr [rdi+0D0h]
0x1800158c4  movups  xmmword ptr [rbx+30h], xmm1
0x1800158c8  movups  xmm0, xmmword ptr [rdi+0E0h]
0x1800158cf  movups  xmmword ptr [rbx+40h], xmm0
0x1800158d3  movups  xmm1, xmmword ptr [rdi+0F0h]
0x1800158da  movups  xmmword ptr [rbx+50h], xmm1
0x1800158de  movsd   xmm0, qword ptr [rdi+100h]
0x1800158e6  movsd   qword ptr [rbx+60h], xmm0
0x1800158eb  mov     dword ptr [rbx+4], 3008h
0x1800158f2  mov     [rbx+28h], rax
0x1800158f6  mov     [rbx+38h], rbp
0x1800158fa  movups  xmm0, xmmword ptr [r14]
0x1800158fe  mov     [rdi+50h], rcx
0x180015902  movdqu  xmmword ptr [rdi+40h], xmm0
0x180015907  test    rcx, rcx
0x18001590a  jz      short loc_180015938
0x18001590c  lea     r8, [rdi+58h]
0x180015910  cmp     [r8], rbp
0x180015913  jnz     short loc_180015938
0x180015915  mov     rax, [rcx]
0x180015918  lea     rdx, IID_IXWizardPropertyBag
0x18001591f  mov     rax, [rax]
0x180015922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015927  mov     ebp, eax
0x180015929  test    eax, eax
0x18001592b  jns     short loc_180015938
0x18001592d  mov     rcx, rbx; pv
0x180015930  call    cs:__imp_CoTaskMemFree
0x180015936  xor     ebx, ebx
0x180015938  mov     rcx, [rdi]
0x18001593b  mov     rdx, rbx
0x18001593e  mov     rax, [rcx+98h]
0x180015945  mov     rcx, rdi
0x180015948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001594d  mov     rax, [rsp+58h+arg_40]
0x180015955  mov     [rax], rbx
0x180015958  mov     eax, ebp
0x18001595a  jmp     loc_180015817
0x18001595f  xor     r9d, r9d; lpArguments
0x180015962  xor     r8d, r8d; nNumberOfArguments
0x180015965  mov     ecx, 0C0000005h; dwExceptionCode
0x18001596a  lea     edx, [r9+1]; dwExceptionFlags
0x18001596e  call    cs:__imp_RaiseException
```
