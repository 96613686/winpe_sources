# CLicensingStateTools::InstallProofOfPurchase(ushort *)

- ea: `0x1800052a0`
- end: `0x18000547f`
- name: `?InstallProofOfPurchase@CLicensingStateTools@@UEAAJPEAG@Z`
- size: `479`
- prototype: `__int64 __fastcall(CLicensingStateTools *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x180004ca8`
- `0x1800052a0`
- `0x18003c560`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800053be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800053be`
- `OLEAUT32!__imp_SysAllocString` at `0x180005353`
- `OLEAUT32!__imp_SysAllocString` at `0x180005353`
- `OLEAUT32!__imp_SysFreeString` at `0x18000543b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000543b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000544f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000544f`

## pseudocode

```c
__int64 __fastcall CLicensingStateTools::InstallProofOfPurchase(CLicensingStateTools *this, unsigned __int16 *a2)
{
  __int64 v2; // rcx
  OLECHAR *v3; // rbx
  SAFEARRAY *v4; // rsi
  unsigned int v6; // edi
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  BSTR v13; // rax
  HRESULT v14; // eax
  SAFEARRAY *psa; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-28h] BYREF
  __int64 v18; // [rsp+40h] [rbp-20h] BYREF
  __int128 v19; // [rsp+48h] [rbp-18h] BYREF

  v2 = *((_QWORD *)this + 18);
  v3 = 0;
  v4 = 0;
  v18 = 0;
  psa = 0;
  ppv = 0;
  v19 = 0;
  if ( v2 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 96LL))(v2, &v18);
    v6 = v8;
    if ( v8 >= 0 )
      goto LABEL_6;
    v7 = (unsigned int)v8;
  }
  else
  {
    v6 = -2147024891;
    v7 = 2147942405LL;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_6:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( (v6 & 0x80000000) != 0 )
  {
LABEL_7:
    v11 = v6;
LABEL_19:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
    goto LABEL_20;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    goto LABEL_7;
  }
  v12 = CSafeArrayHelperT<CEmptyType>::BuildSafeArray(v10, v9, &psa);
  v6 = v12;
  if ( v12 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12);
LABEL_12:
    v4 = psa;
    goto LABEL_20;
  }
  v13 = SysAllocString(L"msft:rm/algorithm/pkey/detect");
  v3 = v13;
  if ( !v13 )
  {
    v6 = -2147024882;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
    goto LABEL_12;
  }
  v4 = psa;
  v14 = (*(__int64 (__fastcall **)(__int64, BSTR, unsigned __int16 *, SAFEARRAY *, __int128 *))(*(_QWORD *)v18 + 40LL))(
          v18,
          v13,
          a2,
          psa,
          &v19);
  v6 = v14;
  if ( v14 < 0
    || (v14 = CoCreateInstance(&CLSID_LicensingStateTools, 0, 1u, &IID_ILicensingStateTools, &ppv), v6 = v14, v14 < 0)
    || (v14 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 192LL))(ppv, 0), v6 = v14, v14 < 0) )
  {
    v11 = (unsigned int)v14;
    goto LABEL_19;
  }
LABEL_20:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v3 )
    SysFreeString(v3);
  if ( v4 )
    SafeArrayDestroy(v4);
  return v6;
}

```

## disassembly

```asm
0x1800052a0  mov     [rsp-18h+arg_10], rbx
0x1800052a5  mov     [rsp-18h+arg_18], rsi
0x1800052aa  push    rbp
0x1800052ab  push    rdi
0x1800052ac  push    r14
0x1800052ae  mov     rbp, rsp
0x1800052b1  sub     rsp, 60h
0x1800052b5  mov     rax, cs:__security_cookie
0x1800052bc  xor     rax, rsp
0x1800052bf  mov     [rbp+var_8], rax
0x1800052c3  mov     rcx, [rcx+90h]
0x1800052ca  xor     ebx, ebx
0x1800052cc  xor     esi, esi
0x1800052ce  mov     [rbp+var_20], rbx
0x1800052d2  mov     [rbp+psa], rsi
0x1800052d6  xorps   xmm0, xmm0
0x1800052d9  mov     [rbp+var_28], rbx
0x1800052dd  mov     r14, rdx
0x1800052e0  movups  [rbp+var_18], xmm0
0x1800052e4  test    rcx, rcx
0x1800052e7  jnz     short loc_1800052F2
0x1800052e9  mov     edi, 80070005h
0x1800052ee  mov     ecx, edi
0x1800052f0  jmp     short loc_18000530A
0x1800052f2  mov     rax, [rcx]
0x1800052f5  lea     rdx, [rbp+var_20]
0x1800052f9  mov     rax, [rax+60h]
0x1800052fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005302  mov     edi, eax
0x180005304  test    eax, eax
0x180005306  jns     short loc_18000530F
0x180005308  mov     ecx, eax
0x18000530a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000530f  mov     ecx, edi
0x180005311  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180005316  test    edi, edi
0x180005318  jns     short loc_180005321
0x18000531a  mov     ecx, edi
0x18000531c  jmp     loc_1800053ED
0x180005321  test    r14, r14
0x180005324  jnz     short loc_18000532D
0x180005326  mov     edi, 80070057h
0x18000532b  jmp     short loc_18000531A
0x18000532d  lea     r8, [rbp+psa]
0x180005331  call    ?BuildSafeArray@?$CSafeArrayHelperT@VCEmptyType@@@@SAJPEBEKPEAPEAUtagSAFEARRAY@@@Z; CSafeArrayHelperT<CEmptyType>::BuildSafeArray(uchar const *,ulong,tagSAFEARRAY * *)
0x180005336  mov     edi, eax
0x180005338  test    eax, eax
0x18000533a  jns     short loc_18000534C
0x18000533c  mov     ecx, eax
0x18000533e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180005343  mov     rsi, [rbp+psa]
0x180005347  jmp     loc_1800053F2
0x18000534c  lea     rcx, psz; "msft:rm/algorithm/pkey/detect"
0x180005353  call    cs:__imp_SysAllocString
0x18000535a  nop     dword ptr [rax+rax+00h]
0x18000535f  mov     rbx, rax
0x180005362  test    rax, rax
0x180005365  jnz     short loc_180005375
0x180005367  mov     edi, 8007000Eh
0x18000536c  mov     ecx, edi
0x18000536e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180005373  jmp     short loc_180005343
0x180005375  mov     rcx, [rbp+var_20]
0x180005379  lea     rdx, [rbp+var_18]
0x18000537d  mov     rsi, [rbp+psa]
0x180005381  mov     r8, r14
0x180005384  mov     [rsp+60h+ppv], rdx
0x180005389  mov     r9, rsi
0x18000538c  mov     rdx, rbx
0x18000538f  mov     rax, [rcx]
0x180005392  mov     rax, [rax+28h]
0x180005396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539b  mov     edi, eax
0x18000539d  test    eax, eax
0x18000539f  js      short loc_1800053EB
0x1800053a1  xor     edx, edx; pUnkOuter
0x1800053a3  lea     rax, [rbp+var_28]
0x1800053a7  lea     r9, IID_ILicensingStateTools; riid
0x1800053ae  mov     [rsp+60h+ppv], rax; ppv
0x1800053b3  lea     rcx, CLSID_LicensingStateTools; rclsid
0x1800053ba  lea     r8d, [rdx+1]; dwClsContext
0x1800053be  call    cs:__imp_CoCreateInstance
0x1800053c5  nop     dword ptr [rax+rax+00h]
0x1800053ca  mov     edi, eax
0x1800053cc  test    eax, eax
0x1800053ce  js      short loc_1800053EB
0x1800053d0  mov     rcx, [rbp+var_28]
0x1800053d4  xor     edx, edx
0x1800053d6  mov     rax, [rcx]
0x1800053d9  mov     rax, [rax+0C0h]
0x1800053e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e5  mov     edi, eax
0x1800053e7  test    eax, eax
0x1800053e9  jns     short loc_1800053F2
0x1800053eb  mov     ecx, eax
0x1800053ed  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800053f2  mov     ecx, edi
0x1800053f4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800053f9  mov     rcx, [rbp+var_28]
0x1800053fd  test    rcx, rcx
0x180005400  jz      short loc_180005416
0x180005402  mov     rax, [rcx]
0x180005405  mov     rax, [rax+10h]
0x180005409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000540e  mov     [rbp+var_28], 0
0x180005416  mov     rcx, [rbp+var_20]
0x18000541a  test    rcx, rcx
0x18000541d  jz      short loc_180005433
0x18000541f  mov     rax, [rcx]
0x180005422  mov     rax, [rax+10h]
0x180005426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000542b  mov     [rbp+var_20], 0
0x180005433  test    rbx, rbx
0x180005436  jz      short loc_180005447
0x180005438  mov     rcx, rbx; bstrString
0x18000543b  call    cs:__imp_SysFreeString
0x180005442  nop     dword ptr [rax+rax+00h]
0x180005447  test    rsi, rsi
0x18000544a  jz      short loc_18000545B
0x18000544c  mov     rcx, rsi; psa
0x18000544f  call    cs:__imp_SafeArrayDestroy
0x180005456  nop     dword ptr [rax+rax+00h]
0x18000545b  mov     eax, edi
0x18000545d  mov     rcx, [rbp+var_8]
0x180005461  xor     rcx, rsp; StackCookie
0x180005464  call    __security_check_cookie
0x180005469  lea     r11, [rsp+60h+var_s0]
0x18000546e  mov     rbx, [r11+30h]
0x180005472  mov     rsi, [r11+38h]
0x180005476  mov     rsp, r11
0x180005479  pop     r14
0x18000547b  pop     rdi
0x18000547c  pop     rbp
0x18000547d  retn
```
