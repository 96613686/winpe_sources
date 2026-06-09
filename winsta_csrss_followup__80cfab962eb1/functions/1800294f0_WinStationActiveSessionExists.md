# WinStationActiveSessionExists

- ea: `0x1800294f0`
- end: `0x180029607`
- name: `WinStationActiveSessionExists`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800065f0`
- `0x1800075a0`
- `0x180025f04`
- `0x18002944c`
- `0x1800294f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800295e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800295e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029532`

## string_xrefs

- `0x180029523`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationActiveSessionExists(__int64 a1)
{
  char v2; // di
  signed int LastError; // eax
  int v4; // ecx
  DWORD v5; // ecx
  void *v6; // rax
  int active; // ebx
  unsigned __int16 v9[16]; // [rsp+28h] [rbp-20h] BYREF

  v2 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v9, 0, 0);
  if ( !CSmartPublicBinding::operator void *(v9) )
  {
    _DbgPrintMessage(8, "Failed to open binding");
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = LastError;
    goto LABEL_10;
  }
  if ( !a1 )
  {
    v5 = 87;
LABEL_11:
    SetLastError(v5);
    goto LABEL_12;
  }
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::GetImpl'::`2'::impl);
  v6 = CSmartPublicBinding::operator void *(v9);
  active = RpcActiveSessionExists(v6, a1);
  if ( active < 0 )
  {
    v4 = active;
LABEL_10:
    v5 = ConvertHRESULT2WIN32(v4);
    goto LABEL_11;
  }
  v2 = 1;
LABEL_12:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v9);
  return v2;
}

```

## disassembly

```asm
0x1800294f0  mov     [rsp+arg_0], rbx
0x1800294f5  push    rdi
0x1800294f6  sub     rsp, 40h
0x1800294fa  mov     rbx, rcx
0x1800294fd  xor     dil, dil
0x180029500  mov     [rsp+48h+arg_8], dil
0x180029505  xor     r8d, r8d; int
0x180029508  xor     edx, edx; void *
0x18002950a  lea     rcx, [rsp+48h+var_20]; this
0x18002950f  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x180029514  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180029519  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x18002951e  test    rax, rax
0x180029521  jnz     short loc_180029551
0x180029523  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x18002952a  lea     ecx, [rax+8]; int
0x18002952d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180029532  call    cs:__imp_GetLastError
0x180029539  nop     dword ptr [rax+rax+00h]
0x18002953e  test    eax, eax
0x180029540  jle     short loc_18002954A
0x180029542  movzx   eax, ax
0x180029545  or      eax, 80070000h
0x18002954a  mov     ecx, eax
0x18002954c  jmp     loc_1800295DB
0x180029551  test    rbx, rbx
0x180029554  jnz     short loc_18002955E
0x180029556  lea     ecx, [rbx+57h]
0x180029559  jmp     loc_1800295E2
0x18002955e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug> `wil::Feature<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::GetImpl(void)'::`2'::impl
0x180029565  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WTSActiveSessionExistsRPCBug>::__private_IsEnabled(void)
0x18002956a  test    al, al
0x18002956c  jz      short loc_1800295B9
0x18002956e  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x180029573  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180029578  mov     rcx, rax
0x18002957b  mov     rdx, rbx
0x18002957e  call    RpcActiveSessionExists
0x180029583  mov     ebx, eax
0x180029585  mov     [rsp+48h+var_28], eax
0x180029589  jmp     short loc_1800295D0
0x18002958b  mov     ebx, eax
0x18002958d  test    eax, eax
0x18002958f  jle     short loc_18002959A
0x180029591  movzx   ebx, ax
0x180029594  or      ebx, 80070000h
0x18002959a  mov     [rsp+48h+var_28], ebx
0x18002959e  mov     r8d, ebx
0x1800295a1  lea     rdx, aRpcactivesessi; "RpcActiveSessionExists threw an excepti"...
0x1800295a8  mov     ecx, 8; int
0x1800295ad  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800295b2  mov     dil, [rsp+48h+arg_8]
0x1800295b7  jmp     short loc_1800295D0
0x1800295b9  lea     rcx, [rsp+48h+var_20]; unsigned __int16 *
0x1800295be  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800295c3  mov     rcx, rax
0x1800295c6  mov     rdx, rbx
0x1800295c9  call    RpcActiveSessionExists
0x1800295ce  mov     ebx, eax
0x1800295d0  test    ebx, ebx
0x1800295d2  js      short loc_1800295D9
0x1800295d4  mov     dil, 1
0x1800295d7  jmp     short loc_1800295EE
0x1800295d9  mov     ecx, ebx; int
0x1800295db  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800295e0  mov     ecx, eax; dwErrCode
0x1800295e2  call    cs:__imp_SetLastError
0x1800295e9  nop     dword ptr [rax+rax+00h]
0x1800295ee  lea     rcx, [rsp+48h+var_20]; this
0x1800295f3  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x1800295f8  mov     al, dil
0x1800295fb  mov     rbx, [rsp+48h+arg_0]
0x180029600  add     rsp, 40h
0x180029604  pop     rdi
0x180029605  retn
0x18003372f  push    rbp
0x180033731  sub     rsp, 20h
0x180033735  mov     rbp, rdx
0x180033738  mov     rcx, [rcx]
0x18003373b  mov     ecx, [rcx]; ExceptionCode
0x18003373d  call    cs:__imp_I_RpcExceptionFilter
0x180033744  nop     dword ptr [rax+rax+00h]
0x180033749  nop
0x18003374a  add     rsp, 20h
0x18003374e  pop     rbp
0x18003374f  retn
```
