# CWbemDispatchMgr::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800055c0`
- end: `0x1800058b3`
- name: `?Invoke@CWbemDispatchMgr@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `755`
- prototype: `__int64 __usercall@<rax>(CWbemDispatchMgr *__hidden this@<rcx>, int@<edx>, const struct _GUID *@<r8>, unsigned int@<r9d>, unsigned __int16, DISPPARAMS *, VARIANT *pvargDest, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800028b0`
- `0x1800055c0`
- `0x1800058c0`
- `0x180006550`
- `0x180013e30`
- `0x1800245b0`
- `0x180024774`
- `0x180025fa0`
- `0x180033d68`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000583f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000584d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000585b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000583f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000584d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000585b`
- `OLEAUT32!__imp_DispInvoke` at `0x18000576e`
- `OLEAUT32!__imp_DispInvoke` at `0x18000576e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180005632`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180005632`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000567d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000568a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000567d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000568a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000563f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000563f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005651`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005651`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000587a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000587a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemDispatchMgr::Invoke(
        CWbemDispatchMgr *this,
        int a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned __int16 a5,
        DISPPARAMS *a6,
        VARIANT *pvargDest,
        struct tagEXCEPINFO *a8,
        unsigned int *puArgErr)
{
  __int64 result; // rax
  struct tagEXCEPINFO *pexcepinfo; // rbp
  CWbemErrorCache *v13; // rdi
  DWORD CurrentThreadId; // r15d
  void *v15; // rcx
  void *v16; // r14
  int v17; // eax
  unsigned int v18; // edi
  int v19; // edx
  WORD v20; // r14
  DISPPARAMS *pparams; // r15
  unsigned int *v22; // r12
  VARIANTARG *v23; // r13
  HRESULT v24; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  struct _COAUTHIDENTITY *v28; // rcx
  LPCRITICAL_SECTION lpCriticalSection[11]; // [rsp+40h] [rbp-58h] BYREF
  ITypeInfo *ptinfo; // [rsp+A0h] [rbp+8h] BYREF

  ptinfo = 0;
  result = (*(__int64 (__fastcall **)(CWbemDispatchMgr *, _QWORD, _QWORD, ITypeInfo **))(*(_QWORD *)this + 8LL))(
             this,
             0,
             a4,
             &ptinfo);
  if ( (int)result >= 0 )
  {
    *((_DWORD *)this + 2) = 0;
    pexcepinfo = a8;
    if ( ((a2 + 4) & 0xFFFFFFFB) != 0 && (a2 & 0x3000000) != 0 )
    {
      if ( (a2 & 0x3000000) == 0x1000000 )
      {
        SetErrorInfo(0, 0);
        EnterCriticalSection(&g_csErrorCache);
        v13 = g_pErrorCache;
        if ( g_pErrorCache )
        {
          CurrentThreadId = GetCurrentThreadId();
          CInCritSec::CInCritSec((CInCritSec *)lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)v13 + 8));
          v15 = (void *)*((_QWORD *)v13 + 6);
          v16 = v15;
          if ( v15 )
          {
            while ( CurrentThreadId != *((_DWORD *)v16 + 4) )
            {
              v16 = *(void **)v16;
              if ( !v16 )
                goto LABEL_7;
            }
            if ( v16 == v15 )
              *((_QWORD *)v13 + 6) = *(_QWORD *)v16;
            if ( *(_QWORD *)v16 )
              *(_QWORD *)(*(_QWORD *)v16 + 8LL) = *((_QWORD *)v16 + 1);
            v25 = (_QWORD *)*((_QWORD *)v16 + 1);
            if ( v25 )
              *v25 = *(_QWORD *)v16;
            v26 = *((_QWORD *)v16 + 8);
            if ( v26 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              *((_QWORD *)v16 + 8) = 0;
            }
            v27 = *((_QWORD *)v16 + 7);
            if ( v27 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
              *((_QWORD *)v16 + 7) = 0;
            }
            SysFreeString(*((BSTR *)v16 + 6));
            *((_QWORD *)v16 + 6) = 0;
            SysFreeString(*((BSTR *)v16 + 4));
            *((_QWORD *)v16 + 4) = 0;
            SysFreeString(*((BSTR *)v16 + 5));
            *((_QWORD *)v16 + 5) = 0;
            v28 = (struct _COAUTHIDENTITY *)*((_QWORD *)v16 + 3);
            if ( v28 )
            {
              WbemFreeAuthIdentity(v28);
              *((_QWORD *)v16 + 3) = 0;
            }
            CWin32DefaultArena::WbemMemFree(v16);
          }
LABEL_7:
          LeaveCriticalSection(lpCriticalSection[0]);
        }
        LeaveCriticalSection(&g_csErrorCache);
        if ( (a2 & 0x800000) != 0 )
          v17 = CWbemDispatchMgr::InvokeWbemProperty(this, a2, a5, a6, pvargDest, pexcepinfo, puArgErr);
        else
          v17 = CWbemDispatchMgr::InvokeWbemMethod(this, a2, a6, pvargDest);
        v18 = v17;
        if ( v17 < 0 )
          CWbemDispatchMgr::RaiseException(this, v17);
      }
      else
      {
        v18 = -2147352573;
      }
    }
    else
    {
      v20 = a5;
      pparams = a6;
      if ( (a5 & 1) != 0 )
        MapNulls(a6);
      v22 = puArgErr;
      v23 = pvargDest;
      v24 = DispInvoke(*((void **)this + 3), ptinfo, a2, v20, pparams, pvargDest, pexcepinfo, puArgErr);
      v18 = v24;
      if ( v24 < 0 )
        v18 = CWbemDispatchMgr::HandleError(this, a2, v20, pparams, v23, v22, v24);
    }
    v19 = *((_DWORD *)this + 2);
    if ( v19 < 0 )
    {
      if ( pexcepinfo )
        SetException(pexcepinfo, v19, L"SWbemObjectEx");
      v18 = -2147352567;
    }
    if ( ptinfo )
      ((void (__fastcall *)(ITypeInfo *))ptinfo->lpVtbl->Release)(ptinfo);
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x1800055c0  mov     r11, rsp
0x1800055c3  push    rbx
0x1800055c4  push    rbp
0x1800055c5  push    rsi
0x1800055c6  push    rdi
0x1800055c7  push    r12
0x1800055c9  push    r13
0x1800055cb  push    r14
0x1800055cd  push    r15
0x1800055cf  sub     rsp, 58h
0x1800055d3  mov     r8d, r9d
0x1800055d6  mov     ebx, edx
0x1800055d8  mov     rsi, rcx
0x1800055db  xor     r12d, r12d
0x1800055de  mov     [r11+8], r12
0x1800055e2  mov     rax, [rcx]
0x1800055e5  lea     r9, [r11+8]
0x1800055e9  xor     edx, edx
0x1800055eb  mov     rax, [rax+8]
0x1800055ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055f4  test    eax, eax
0x1800055f6  js      loc_180005704
0x1800055fc  mov     [rsi+8], r12d
0x180005600  lea     eax, [rbx+4]
0x180005603  mov     rbp, [rsp+98h+arg_38]
0x18000560b  test    eax, 0FFFFFFFBh
0x180005610  jz      loc_18000571C
0x180005616  mov     eax, ebx
0x180005618  and     eax, 3000000h
0x18000561d  jz      loc_18000571C
0x180005623  cmp     eax, 1000000h
0x180005628  jnz     loc_180005715
0x18000562e  xor     edx, edx; perrinfo
0x180005630  xor     ecx, ecx; dwReserved
0x180005632  call    cs:__imp_SetErrorInfo
0x180005638  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000563f  call    cs:__imp_EnterCriticalSection
0x180005645  mov     rdi, cs:?g_pErrorCache@@3PEAVCWbemErrorCache@@EA; CWbemErrorCache * g_pErrorCache
0x18000564c  test    rdi, rdi
0x18000564f  jz      short loc_180005683
0x180005651  call    cs:__imp_GetCurrentThreadId
0x180005657  mov     r15d, eax
0x18000565a  lea     rdx, [rdi+8]; struct _RTL_CRITICAL_SECTION *
0x18000565e  lea     rcx, [rsp+98h+lpCriticalSection]; this
0x180005663  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180005668  mov     rcx, [rdi+30h]
0x18000566c  mov     r14, rcx
0x18000566f  test    rcx, rcx
0x180005672  jnz     loc_1800057CB
0x180005678  mov     rcx, [rsp+98h+lpCriticalSection]; lpCriticalSection
0x18000567d  call    cs:__imp_LeaveCriticalSection
0x180005683  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000568a  call    cs:__imp_LeaveCriticalSection
0x180005690  mov     edx, ebx; int
0x180005692  mov     rcx, rsi; this
0x180005695  bt      ebx, 17h
0x180005699  jnb     loc_1800057A4
0x18000569f  mov     rax, [rsp+98h+arg_40]
0x1800056a7  mov     [rsp+98h+pexcepinfo], rax; unsigned int *
0x1800056ac  mov     [rsp+98h+pvarResult], rbp; struct tagEXCEPINFO *
0x1800056b1  mov     rax, [rsp+98h+pvargDest]
0x1800056b9  mov     [rsp+98h+pparams], rax; pvargDest
0x1800056be  mov     r9, [rsp+98h+arg_28]; struct tagDISPPARAMS *
0x1800056c6  movzx   r8d, [rsp+98h+arg_20]; unsigned __int16
0x1800056cf  call    ?InvokeWbemProperty@CWbemDispatchMgr@@AEAAJJGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; CWbemDispatchMgr::InvokeWbemProperty(long,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x1800056d4  mov     edi, eax
0x1800056d6  test    eax, eax
0x1800056d8  js      loc_180005886
0x1800056de  mov     edx, [rsi+8]; int
0x1800056e1  test    edx, edx
0x1800056e3  js      loc_180005895
0x1800056e9  mov     rcx, [rsp+98h+ptinfo]
0x1800056f1  test    rcx, rcx
0x1800056f4  jz      short loc_180005702
0x1800056f6  mov     rax, [rcx]
0x1800056f9  mov     rax, [rax+10h]
0x1800056fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005702  mov     eax, edi
0x180005704  add     rsp, 58h
0x180005708  pop     r15
0x18000570a  pop     r14
0x18000570c  pop     r13
0x18000570e  pop     r12
0x180005710  pop     rdi
0x180005711  pop     rsi
0x180005712  pop     rbp
0x180005713  pop     rbx
0x180005714  retn
0x180005715  mov     edi, 80020003h
0x18000571a  jmp     short loc_1800056DE
0x18000571c  movzx   r14d, [rsp+98h+arg_20]
0x180005725  mov     r15, [rsp+98h+arg_28]
0x18000572d  test    r14b, 1
0x180005731  jnz     loc_1800057BE
0x180005737  mov     r12, [rsp+98h+arg_40]
0x18000573f  mov     [rsp+98h+puArgErr], r12; puArgErr
0x180005744  mov     [rsp+98h+pexcepinfo], rbp; pexcepinfo
0x180005749  mov     r13, [rsp+98h+pvargDest]
0x180005751  mov     [rsp+98h+pvarResult], r13; pvarResult
0x180005756  mov     [rsp+98h+pparams], r15; pparams
0x18000575b  movzx   r9d, r14w; wFlags
0x18000575f  mov     r8d, ebx; dispidMember
0x180005762  mov     rdx, [rsp+98h+ptinfo]; ptinfo
0x18000576a  mov     rcx, [rsi+18h]; this
0x18000576e  call    cs:__imp_DispInvoke
0x180005774  mov     edi, eax
0x180005776  test    eax, eax
0x180005778  jns     loc_1800056DE
0x18000577e  mov     dword ptr [rsp+98h+pexcepinfo], eax; rgIndices
0x180005782  mov     [rsp+98h+pvarResult], r12; unsigned int *
0x180005787  mov     [rsp+98h+pparams], r13; VARIANTARG *
0x18000578c  mov     r9, r15; struct tagDISPPARAMS *
0x18000578f  movzx   r8d, r14w; unsigned __int16
0x180005793  mov     edx, ebx; int
0x180005795  mov     rcx, rsi; this
0x180005798  call    ?HandleError@CWbemDispatchMgr@@AEAAJJGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAIJ@Z; CWbemDispatchMgr::HandleError(long,ushort,tagDISPPARAMS *,tagVARIANT *,uint *,long)
0x18000579d  mov     edi, eax
0x18000579f  jmp     loc_1800056DE
0x1800057a4  mov     r9, [rsp+98h+pvargDest]; struct tagVARIANT *
0x1800057ac  mov     r8, [rsp+98h+arg_28]; struct tagDISPPARAMS *
0x1800057b4  call    ?InvokeWbemMethod@CWbemDispatchMgr@@AEAAJJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z; CWbemDispatchMgr::InvokeWbemMethod(long,tagDISPPARAMS *,tagVARIANT *)
0x1800057b9  jmp     loc_1800056D4
0x1800057be  mov     rcx, r15; struct tagDISPPARAMS *
0x1800057c1  call    ?MapNulls@@YAXPEAUtagDISPPARAMS@@@Z; MapNulls(tagDISPPARAMS *)
0x1800057c6  jmp     loc_180005737
0x1800057cb  cmp     r15d, [r14+10h]
0x1800057cf  jz      short loc_1800057DE
0x1800057d1  mov     r14, [r14]
0x1800057d4  test    r14, r14
0x1800057d7  jnz     short loc_1800057CB
0x1800057d9  jmp     loc_180005678
0x1800057de  cmp     r14, rcx
0x1800057e1  jnz     short loc_1800057EA
0x1800057e3  mov     rax, [r14]
0x1800057e6  mov     [rdi+30h], rax
0x1800057ea  mov     rcx, [r14]
0x1800057ed  test    rcx, rcx
0x1800057f0  jz      short loc_1800057FA
0x1800057f2  mov     rax, [r14+8]
0x1800057f6  mov     [rcx+8], rax
0x1800057fa  mov     rcx, [r14+8]
0x1800057fe  test    rcx, rcx
0x180005801  jz      short loc_180005809
0x180005803  mov     rax, [r14]
0x180005806  mov     [rcx], rax
0x180005809  mov     rcx, [r14+40h]
0x18000580d  test    rcx, rcx
0x180005810  jz      short loc_180005822
0x180005812  mov     rax, [rcx]
0x180005815  mov     rax, [rax+10h]
0x180005819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000581e  mov     [r14+40h], r12
0x180005822  mov     rcx, [r14+38h]
0x180005826  test    rcx, rcx
0x180005829  jz      short loc_18000583B
0x18000582b  mov     rax, [rcx]
0x18000582e  mov     rax, [rax+10h]
0x180005832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005837  mov     [r14+38h], r12
0x18000583b  mov     rcx, [r14+30h]; bstrString
0x18000583f  call    cs:__imp_SysFreeString
0x180005845  mov     [r14+30h], r12
0x180005849  mov     rcx, [r14+20h]; bstrString
0x18000584d  call    cs:__imp_SysFreeString
0x180005853  mov     [r14+20h], r12
0x180005857  mov     rcx, [r14+28h]; bstrString
0x18000585b  call    cs:__imp_SysFreeString
0x180005861  mov     [r14+28h], r12
0x180005865  mov     rcx, [r14+18h]; pv
0x180005869  test    rcx, rcx
0x18000586c  jz      short loc_180005877
0x18000586e  call    ?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z; WbemFreeAuthIdentity(_COAUTHIDENTITY *)
0x180005873  mov     [r14+18h], r12
0x180005877  mov     rcx, r14
0x18000587a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180005880  nop
0x180005881  jmp     loc_180005678
0x180005886  mov     edx, edi; int
0x180005888  mov     rcx, rsi; this
0x18000588b  call    ?RaiseException@CWbemDispatchMgr@@QEAAXJ@Z; CWbemDispatchMgr::RaiseException(long)
0x180005890  jmp     loc_1800056DE
0x180005895  test    rbp, rbp
0x180005898  jz      short loc_1800058A9
0x18000589a  lea     r8, aSwbemobjectex; "SWbemObjectEx"
0x1800058a1  mov     rcx, rbp; struct tagEXCEPINFO *
0x1800058a4  call    ?SetException@@YAXPEAUtagEXCEPINFO@@JPEAG@Z; SetException(tagEXCEPINFO *,long,ushort *)
0x1800058a9  mov     edi, 80020009h
0x1800058ae  jmp     loc_1800056E9
```
