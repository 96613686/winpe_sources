# CDefaultSessionArbitrationHelper::GetRequestDialogObject(long,void * *)

- ea: `0x18007b230`
- end: `0x18007b409`
- name: `?GetRequestDialogObject@CDefaultSessionArbitrationHelper@@AEAAJJPEAPEAX@Z`
- size: `473`
- prototype: `__int64 __fastcall(CDefaultSessionArbitrationHelper *__hidden this, int, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007c240`

## callees

- `0x180009940`
- `0x1800139c0`
- `0x180015044`
- `0x180016558`
- `0x180033f60`
- `0x18003440c`
- `0x180034470`
- `0x18007b230`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007b2a6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18007b2a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b3bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b3bf`
- `ole32!CoGetObject` at `0x18007b35e`
- `ole32!CoGetObject` at `0x18007b35e`

## string_xrefs

- `0x18007b273`: `Session:%d!clsid:%s`
- `0x18007b2b8`: `StringFromCLSID failed: 0x%x in %s`
- `0x18007b39b`: `ptrClassFactory->CreateInstance failed: 0x%x in %s`

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
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&ppv);
  return v7;
}

```

## disassembly

```asm
0x18007b230  mov     [rsp-18h+arg_0], rbx
0x18007b235  mov     [rsp-18h+arg_18], rsi
0x18007b23a  push    rbp
0x18007b23b  push    rdi
0x18007b23c  push    r14
0x18007b23e  mov     rbp, rsp
0x18007b241  sub     rsp, 80h
0x18007b248  mov     rax, cs:__security_cookie
0x18007b24f  xor     rax, rsp
0x18007b252  mov     [rbp+var_10], rax
0x18007b256  mov     r14, r8
0x18007b259  mov     esi, edx
0x18007b25b  mov     [rbp+ppv], 0
0x18007b263  mov     [rbp+lpsz], 0
0x18007b26b  mov     [rbp+var_40], 0
0x18007b273  movups  xmm0, xmmword ptr cs:aSessionDClsidS; "Session:%d!clsid:%s"
0x18007b27a  movups  xmmword ptr [rbp+var_38], xmm0
0x18007b27e  movups  xmm1, xmmword ptr cs:aSessionDClsidS+10h; "%d!clsid:%s"
0x18007b285  movups  [rbp+var_28], xmm1
0x18007b289  movsd   xmm0, qword ptr cs:aSessionDClsidS+20h; ":%s"
0x18007b291  movsd   [rbp+var_18], xmm0
0x18007b296  xor     edi, edi
0x18007b298  mov     [r8], rdi
0x18007b29b  lea     rdx, [rbp+lpsz]; lplpsz
0x18007b29f  lea     rcx, CLSID_SessionDialog; rclsid
0x18007b2a6  call    cs:__imp_StringFromCLSID
0x18007b2ad  nop     dword ptr [rax+rax+00h]
0x18007b2b2  mov     ebx, eax
0x18007b2b4  test    eax, eax
0x18007b2b6  jns     short loc_18007B2C4
0x18007b2b8  lea     rdx, aStringfromclsi_0; "StringFromCLSID failed: 0x%x in %s"
0x18007b2bf  jmp     loc_18007B3A2
0x18007b2c4  lea     r8, [rbp+var_40]; unsigned __int64 *
0x18007b2c8  mov     edx, 27h ; '''; unsigned __int64
0x18007b2cd  mov     rcx, [rbp+lpsz]; unsigned __int16 *
0x18007b2d1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18007b2d6  mov     ebx, eax
0x18007b2d8  test    eax, eax
0x18007b2da  jns     short loc_18007B2E8
0x18007b2dc  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x18007b2e3  jmp     loc_18007B3A2
0x18007b2e8  mov     rbx, [rbp+var_40]
0x18007b2ec  add     rbx, 1Eh
0x18007b2f0  mov     eax, 2
0x18007b2f5  mul     rbx
0x18007b2f8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18007b2ff  cmovb   rax, rcx
0x18007b303  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007b30a  mov     rcx, rax; unsigned __int64
0x18007b30d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007b312  mov     rdi, rax
0x18007b315  test    rax, rax
0x18007b318  jnz     short loc_18007B324
0x18007b31a  mov     ebx, 8007000Eh
0x18007b31f  jmp     loc_18007B3B6
0x18007b324  mov     rax, [rbp+lpsz]
0x18007b328  mov     [rsp+80h+var_60], rax
0x18007b32d  mov     r9d, esi
0x18007b330  lea     r8, [rbp+var_38]; unsigned __int16 *
0x18007b334  mov     rdx, rbx; unsigned __int64
0x18007b337  mov     rcx, rdi; unsigned __int16 *
0x18007b33a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007b33f  mov     ebx, eax
0x18007b341  test    eax, eax
0x18007b343  jns     short loc_18007B34E
0x18007b345  lea     rdx, aStringcchprint_1; "StringCchPrintfW failed: 0x%x in %s"
0x18007b34c  jmp     short loc_18007B3A2
0x18007b34e  lea     r9, [rbp+ppv]; ppv
0x18007b352  lea     r8, IID_IClassFactory; riid
0x18007b359  xor     edx, edx; pBindOptions
0x18007b35b  mov     rcx, rdi; pszName
0x18007b35e  call    cs:__imp_CoGetObject
0x18007b365  nop     dword ptr [rax+rax+00h]
0x18007b36a  mov     ebx, eax
0x18007b36c  test    eax, eax
0x18007b36e  jns     short loc_18007B379
0x18007b370  lea     rdx, aCogetobjectFai; "CoGetObject failed: 0x%x in %s"
0x18007b377  jmp     short loc_18007B3A2
0x18007b379  mov     rcx, [rbp+ppv]
0x18007b37d  mov     rax, [rcx]
0x18007b380  mov     r9, r14
0x18007b383  lea     r8, IID_ISessionDialog
0x18007b38a  xor     edx, edx
0x18007b38c  mov     rax, [rax+18h]
0x18007b390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b395  mov     ebx, eax
0x18007b397  test    eax, eax
0x18007b399  jns     short loc_18007B3B6
0x18007b39b  lea     rdx, aPtrclassfactor; "ptrClassFactory->CreateInstance failed:"...
0x18007b3a2  lea     r9, aCdefaultsessio_3; "CDefaultSessionArbitrationHelper::GetRe"...
0x18007b3a9  mov     r8d, eax
0x18007b3ac  mov     ecx, 8; int
0x18007b3b1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007b3b6  mov     rcx, [rbp+lpsz]; pv
0x18007b3ba  test    rcx, rcx
0x18007b3bd  jz      short loc_18007B3CB
0x18007b3bf  call    cs:__imp_CoTaskMemFree
0x18007b3c6  nop     dword ptr [rax+rax+00h]
0x18007b3cb  test    rdi, rdi
0x18007b3ce  jz      short loc_18007B3D9
0x18007b3d0  mov     rcx, rdi; Block
0x18007b3d3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007b3d8  nop
0x18007b3d9  lea     rcx, [rbp+ppv]; void *
0x18007b3dd  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18007b3e2  mov     eax, ebx
0x18007b3e4  mov     rcx, [rbp+var_10]
0x18007b3e8  xor     rcx, rsp; StackCookie
0x18007b3eb  call    __security_check_cookie
0x18007b3f0  lea     r11, [rsp+80h+var_s0]
0x18007b3f8  mov     rbx, [r11+20h]
0x18007b3fc  mov     rsi, [r11+38h]
0x18007b400  mov     rsp, r11
0x18007b403  pop     r14
0x18007b405  pop     rdi
0x18007b406  pop     rbp
0x18007b407  retn
```
