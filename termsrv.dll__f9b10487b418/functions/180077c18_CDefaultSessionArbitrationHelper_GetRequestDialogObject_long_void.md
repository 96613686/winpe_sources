# CDefaultSessionArbitrationHelper::GetRequestDialogObject(long,void * *)

- ea: `0x180077c18`
- end: `0x180077dde`
- name: `?GetRequestDialogObject@CDefaultSessionArbitrationHelper@@AEAAJJPEAPEAX@Z`
- size: `454`
- prototype: `__int64 __fastcall(CDefaultSessionArbitrationHelper *__hidden this, int, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180078bd0`

## callees

- `0x18000a210`
- `0x180013150`
- `0x180014a2c`
- `0x180015ab0`
- `0x1800321f0`
- `0x18003269c`
- `0x180032700`
- `0x180077c18`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180077c8e`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180077c8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077d9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180077d9b`
- `ole32!CoGetObject` at `0x180077d40`
- `ole32!CoGetObject` at `0x180077d40`

## string_xrefs

- `0x180077c5b`: `Session:%d!clsid:%s`
- `0x180077c9a`: `StringFromCLSID failed: 0x%x in %s`
- `0x180077d77`: `ptrClassFactory->CreateInstance failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDefaultSessionArbitrationHelper::GetRequestDialogObject(
        CDefaultSessionArbitrationHelper *this,
        unsigned int a2,
        void **a3)
{
  unsigned __int16 *v5; // rdi
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rax
  int v11; // eax
  HRESULT Object; // eax
  int v13; // eax
  LPOLESTR lpsz; // [rsp+30h] [rbp-50h] BYREF
  void *ppv; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int64 v17; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 v18[8]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v19; // [rsp+58h] [rbp-28h]
  __int64 v20; // [rsp+68h] [rbp-18h]

  ppv = 0;
  lpsz = 0;
  v17 = 0;
  *(_OWORD *)v18 = *(_OWORD *)L"Session:%d!clsid:%s";
  v19 = *(_OWORD *)L"%d!clsid:%s";
  v20 = *(_QWORD *)L":%s";
  v5 = 0;
  *a3 = 0;
  v6 = StringFromCLSID(&CLSID_SessionDialog, &lpsz);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = StringCchLengthW(lpsz, 0x27u, &v17);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v9 = v17 + 30;
      v10 = 2 * (v17 + 30);
      if ( !is_mul_ok(v17 + 30, 2u) )
        v10 = -1;
      v5 = (unsigned __int16 *)operator new[](v10, (const struct std::nothrow_t *)std::nothrow);
      if ( v5 )
      {
        v11 = StringCchPrintfW(v5, v9, v18, a2, lpsz);
        v7 = v11;
        if ( v11 >= 0 )
        {
          Object = CoGetObject(v5, 0, &IID_IClassFactory, &ppv);
          v7 = Object;
          if ( Object >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, void **))(*(_QWORD *)ppv + 24LL))(
                    ppv,
                    0,
                    &IID_ISessionDialog,
                    a3);
            v7 = v13;
            if ( v13 < 0 )
              _DbgPrintMessage(
                8,
                "ptrClassFactory->CreateInstance failed: 0x%x in %s",
                (unsigned int)v13,
                "CDefaultSessionArbitrationHelper::GetRequestDialogObject");
          }
          else
          {
            _DbgPrintMessage(
              8,
              "CoGetObject failed: 0x%x in %s",
              (unsigned int)Object,
              "CDefaultSessionArbitrationHelper::GetRequestDialogObject");
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "StringCchPrintfW failed: 0x%x in %s",
            (unsigned int)v11,
            "CDefaultSessionArbitrationHelper::GetRequestDialogObject");
        }
      }
      else
      {
        v7 = -2147024882;
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "StringCchLength failed: 0x%x in %s",
        (unsigned int)v8,
        "CDefaultSessionArbitrationHelper::GetRequestDialogObject");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "StringFromCLSID failed: 0x%x in %s",
      (unsigned int)v6,
      "CDefaultSessionArbitrationHelper::GetRequestDialogObject");
  }
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( v5 )
    operator delete(v5);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>((__int64 *)&ppv);
  return v7;
}

```

## disassembly

```asm
0x180077c18  mov     [rsp-18h+arg_0], rbx
0x180077c1d  mov     [rsp-18h+arg_18], rsi
0x180077c22  push    rbp
0x180077c23  push    rdi
0x180077c24  push    r14
0x180077c26  mov     rbp, rsp
0x180077c29  sub     rsp, 80h
0x180077c30  mov     rax, cs:__security_cookie
0x180077c37  xor     rax, rsp
0x180077c3a  mov     [rbp+var_10], rax
0x180077c3e  mov     r14, r8
0x180077c41  mov     esi, edx
0x180077c43  mov     [rbp+ppv], 0
0x180077c4b  mov     [rbp+lpsz], 0
0x180077c53  mov     [rbp+var_40], 0
0x180077c5b  movups  xmm0, xmmword ptr cs:aSessionDClsidS; "Session:%d!clsid:%s"
0x180077c62  movups  xmmword ptr [rbp+var_38], xmm0
0x180077c66  movups  xmm1, xmmword ptr cs:aSessionDClsidS+10h; "%d!clsid:%s"
0x180077c6d  movups  [rbp+var_28], xmm1
0x180077c71  movsd   xmm0, qword ptr cs:aSessionDClsidS+20h; ":%s"
0x180077c79  movsd   [rbp+var_18], xmm0
0x180077c7e  xor     edi, edi
0x180077c80  mov     [r8], rdi
0x180077c83  lea     rdx, [rbp+lpsz]; lplpsz
0x180077c87  lea     rcx, CLSID_SessionDialog; rclsid
0x180077c8e  call    cs:__imp_StringFromCLSID
0x180077c94  mov     ebx, eax
0x180077c96  test    eax, eax
0x180077c98  jns     short loc_180077CA6
0x180077c9a  lea     rdx, aStringfromclsi_0; "StringFromCLSID failed: 0x%x in %s"
0x180077ca1  jmp     loc_180077D7E
0x180077ca6  lea     r8, [rbp+var_40]; unsigned __int64 *
0x180077caa  mov     edx, 27h ; '''; unsigned __int64
0x180077caf  mov     rcx, [rbp+lpsz]; unsigned __int16 *
0x180077cb3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180077cb8  mov     ebx, eax
0x180077cba  test    eax, eax
0x180077cbc  jns     short loc_180077CCA
0x180077cbe  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x180077cc5  jmp     loc_180077D7E
0x180077cca  mov     rbx, [rbp+var_40]
0x180077cce  add     rbx, 1Eh
0x180077cd2  mov     eax, 2
0x180077cd7  mul     rbx
0x180077cda  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180077ce1  cmovb   rax, rcx
0x180077ce5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180077cec  mov     rcx, rax; unsigned __int64
0x180077cef  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180077cf4  mov     rdi, rax
0x180077cf7  test    rax, rax
0x180077cfa  jnz     short loc_180077D06
0x180077cfc  mov     ebx, 8007000Eh
0x180077d01  jmp     loc_180077D92
0x180077d06  mov     rax, [rbp+lpsz]
0x180077d0a  mov     [rsp+80h+var_60], rax
0x180077d0f  mov     r9d, esi
0x180077d12  lea     r8, [rbp+var_38]; unsigned __int16 *
0x180077d16  mov     rdx, rbx; unsigned __int64
0x180077d19  mov     rcx, rdi; unsigned __int16 *
0x180077d1c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180077d21  mov     ebx, eax
0x180077d23  test    eax, eax
0x180077d25  jns     short loc_180077D30
0x180077d27  lea     rdx, aStringcchprint_1; "StringCchPrintfW failed: 0x%x in %s"
0x180077d2e  jmp     short loc_180077D7E
0x180077d30  lea     r9, [rbp+ppv]; ppv
0x180077d34  lea     r8, IID_IClassFactory; riid
0x180077d3b  xor     edx, edx; pBindOptions
0x180077d3d  mov     rcx, rdi; pszName
0x180077d40  call    cs:__imp_CoGetObject
0x180077d46  mov     ebx, eax
0x180077d48  test    eax, eax
0x180077d4a  jns     short loc_180077D55
0x180077d4c  lea     rdx, aCogetobjectFai; "CoGetObject failed: 0x%x in %s"
0x180077d53  jmp     short loc_180077D7E
0x180077d55  mov     rcx, [rbp+ppv]
0x180077d59  mov     rax, [rcx]
0x180077d5c  mov     r9, r14
0x180077d5f  lea     r8, IID_ISessionDialog
0x180077d66  xor     edx, edx
0x180077d68  mov     rax, [rax+18h]
0x180077d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077d71  mov     ebx, eax
0x180077d73  test    eax, eax
0x180077d75  jns     short loc_180077D92
0x180077d77  lea     rdx, aPtrclassfactor; "ptrClassFactory->CreateInstance failed:"...
0x180077d7e  lea     r9, aCdefaultsessio_3; "CDefaultSessionArbitrationHelper::GetRe"...
0x180077d85  mov     r8d, eax
0x180077d88  mov     ecx, 8; int
0x180077d8d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180077d92  mov     rcx, [rbp+lpsz]; pv
0x180077d96  test    rcx, rcx
0x180077d99  jz      short loc_180077DA1
0x180077d9b  call    cs:__imp_CoTaskMemFree
0x180077da1  test    rdi, rdi
0x180077da4  jz      short loc_180077DAF
0x180077da6  mov     rcx, rdi; Block
0x180077da9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180077dae  nop
0x180077daf  lea     rcx, [rbp+ppv]; void *
0x180077db3  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180077db8  mov     eax, ebx
0x180077dba  mov     rcx, [rbp+var_10]
0x180077dbe  xor     rcx, rsp; StackCookie
0x180077dc1  call    __security_check_cookie
0x180077dc6  lea     r11, [rsp+80h+var_s0]
0x180077dce  mov     rbx, [r11+20h]
0x180077dd2  mov     rsi, [r11+38h]
0x180077dd6  mov     rsp, r11
0x180077dd9  pop     r14
0x180077ddb  pop     rdi
0x180077ddc  pop     rbp
0x180077ddd  retn
```
