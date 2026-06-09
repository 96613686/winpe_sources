# CHybridHandler::GetRequestDialogObject(long,void * *)

- ea: `0x18008f7d0`
- end: `0x18008f9a9`
- name: `?GetRequestDialogObject@CHybridHandler@@AEAAJJPEAPEAX@Z`
- size: `473`
- prototype: `__int64 __fastcall(CHybridHandler *__hidden this, int, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008e7ec`

## callees

- `0x180009940`
- `0x1800139c0`
- `0x180015044`
- `0x180016558`
- `0x180033f60`
- `0x18003440c`
- `0x180034470`
- `0x18008f7d0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18008f846`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18008f846`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f95f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f95f`
- `ole32!CoGetObject` at `0x18008f8fe`
- `ole32!CoGetObject` at `0x18008f8fe`

## string_xrefs

- `0x18008f813`: `Session:%d!clsid:%s`
- `0x18008f858`: `StringFromCLSID failed: 0x%x in %s`
- `0x18008f93b`: `ptrClassFactory->CreateInstance failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CHybridHandler::GetRequestDialogObject(CHybridHandler *this, unsigned int a2, void **a3)
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
                "CHybridHandler::GetRequestDialogObject");
          }
          else
          {
            _DbgPrintMessage(
              8,
              "CoGetObject failed: 0x%x in %s",
              (unsigned int)Object,
              "CHybridHandler::GetRequestDialogObject");
          }
        }
        else
        {
          _DbgPrintMessage(
            8,
            "StringCchPrintfW failed: 0x%x in %s",
            (unsigned int)v11,
            "CHybridHandler::GetRequestDialogObject");
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
        "CHybridHandler::GetRequestDialogObject");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "StringFromCLSID failed: 0x%x in %s",
      (unsigned int)v6,
      "CHybridHandler::GetRequestDialogObject");
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
0x18008f7d0  mov     [rsp-18h+arg_0], rbx
0x18008f7d5  mov     [rsp-18h+arg_18], rsi
0x18008f7da  push    rbp
0x18008f7db  push    rdi
0x18008f7dc  push    r14
0x18008f7de  mov     rbp, rsp
0x18008f7e1  sub     rsp, 80h
0x18008f7e8  mov     rax, cs:__security_cookie
0x18008f7ef  xor     rax, rsp
0x18008f7f2  mov     [rbp+var_10], rax
0x18008f7f6  mov     r14, r8
0x18008f7f9  mov     esi, edx
0x18008f7fb  mov     [rbp+ppv], 0
0x18008f803  mov     [rbp+lpsz], 0
0x18008f80b  mov     [rbp+var_40], 0
0x18008f813  movups  xmm0, xmmword ptr cs:aSessionDClsidS; "Session:%d!clsid:%s"
0x18008f81a  movups  xmmword ptr [rbp+var_38], xmm0
0x18008f81e  movups  xmm1, xmmword ptr cs:aSessionDClsidS+10h; "%d!clsid:%s"
0x18008f825  movups  [rbp+var_28], xmm1
0x18008f829  movsd   xmm0, qword ptr cs:aSessionDClsidS+20h; ":%s"
0x18008f831  movsd   [rbp+var_18], xmm0
0x18008f836  xor     edi, edi
0x18008f838  mov     [r8], rdi
0x18008f83b  lea     rdx, [rbp+lpsz]; lplpsz
0x18008f83f  lea     rcx, CLSID_SessionDialog; rclsid
0x18008f846  call    cs:__imp_StringFromCLSID
0x18008f84d  nop     dword ptr [rax+rax+00h]
0x18008f852  mov     ebx, eax
0x18008f854  test    eax, eax
0x18008f856  jns     short loc_18008F864
0x18008f858  lea     rdx, aStringfromclsi_0; "StringFromCLSID failed: 0x%x in %s"
0x18008f85f  jmp     loc_18008F942
0x18008f864  lea     r8, [rbp+var_40]; unsigned __int64 *
0x18008f868  mov     edx, 27h ; '''; unsigned __int64
0x18008f86d  mov     rcx, [rbp+lpsz]; unsigned __int16 *
0x18008f871  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18008f876  mov     ebx, eax
0x18008f878  test    eax, eax
0x18008f87a  jns     short loc_18008F888
0x18008f87c  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x18008f883  jmp     loc_18008F942
0x18008f888  mov     rbx, [rbp+var_40]
0x18008f88c  add     rbx, 1Eh
0x18008f890  mov     eax, 2
0x18008f895  mul     rbx
0x18008f898  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008f89f  cmovb   rax, rcx
0x18008f8a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008f8aa  mov     rcx, rax; unsigned __int64
0x18008f8ad  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008f8b2  mov     rdi, rax
0x18008f8b5  test    rax, rax
0x18008f8b8  jnz     short loc_18008F8C4
0x18008f8ba  mov     ebx, 8007000Eh
0x18008f8bf  jmp     loc_18008F956
0x18008f8c4  mov     rax, [rbp+lpsz]
0x18008f8c8  mov     [rsp+80h+var_60], rax
0x18008f8cd  mov     r9d, esi
0x18008f8d0  lea     r8, [rbp+var_38]; unsigned __int16 *
0x18008f8d4  mov     rdx, rbx; unsigned __int64
0x18008f8d7  mov     rcx, rdi; unsigned __int16 *
0x18008f8da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008f8df  mov     ebx, eax
0x18008f8e1  test    eax, eax
0x18008f8e3  jns     short loc_18008F8EE
0x18008f8e5  lea     rdx, aStringcchprint_1; "StringCchPrintfW failed: 0x%x in %s"
0x18008f8ec  jmp     short loc_18008F942
0x18008f8ee  lea     r9, [rbp+ppv]; ppv
0x18008f8f2  lea     r8, IID_IClassFactory; riid
0x18008f8f9  xor     edx, edx; pBindOptions
0x18008f8fb  mov     rcx, rdi; pszName
0x18008f8fe  call    cs:__imp_CoGetObject
0x18008f905  nop     dword ptr [rax+rax+00h]
0x18008f90a  mov     ebx, eax
0x18008f90c  test    eax, eax
0x18008f90e  jns     short loc_18008F919
0x18008f910  lea     rdx, aCogetobjectFai; "CoGetObject failed: 0x%x in %s"
0x18008f917  jmp     short loc_18008F942
0x18008f919  mov     rcx, [rbp+ppv]
0x18008f91d  mov     rax, [rcx]
0x18008f920  mov     r9, r14
0x18008f923  lea     r8, IID_ISessionDialog
0x18008f92a  xor     edx, edx
0x18008f92c  mov     rax, [rax+18h]
0x18008f930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f935  mov     ebx, eax
0x18008f937  test    eax, eax
0x18008f939  jns     short loc_18008F956
0x18008f93b  lea     rdx, aPtrclassfactor; "ptrClassFactory->CreateInstance failed:"...
0x18008f942  lea     r9, aChybridhandler; "CHybridHandler::GetRequestDialogObject"
0x18008f949  mov     r8d, eax
0x18008f94c  mov     ecx, 8; int
0x18008f951  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008f956  mov     rcx, [rbp+lpsz]; pv
0x18008f95a  test    rcx, rcx
0x18008f95d  jz      short loc_18008F96B
0x18008f95f  call    cs:__imp_CoTaskMemFree
0x18008f966  nop     dword ptr [rax+rax+00h]
0x18008f96b  test    rdi, rdi
0x18008f96e  jz      short loc_18008F979
0x18008f970  mov     rcx, rdi; Block
0x18008f973  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008f978  nop
0x18008f979  lea     rcx, [rbp+ppv]; void *
0x18008f97d  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18008f982  mov     eax, ebx
0x18008f984  mov     rcx, [rbp+var_10]
0x18008f988  xor     rcx, rsp; StackCookie
0x18008f98b  call    __security_check_cookie
0x18008f990  lea     r11, [rsp+80h+var_s0]
0x18008f998  mov     rbx, [r11+20h]
0x18008f99c  mov     rsi, [r11+38h]
0x18008f9a0  mov     rsp, r11
0x18008f9a3  pop     r14
0x18008f9a5  pop     rdi
0x18008f9a6  pop     rbp
0x18008f9a7  retn
```
