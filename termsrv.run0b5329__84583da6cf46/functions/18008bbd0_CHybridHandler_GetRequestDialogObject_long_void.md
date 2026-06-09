# CHybridHandler::GetRequestDialogObject(long,void * *)

- ea: `0x18008bbd0`
- end: `0x18008bd96`
- name: `?GetRequestDialogObject@CHybridHandler@@AEAAJJPEAPEAX@Z`
- size: `454`
- prototype: `__int64 __fastcall(CHybridHandler *__hidden this, int, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008ac4c`

## callees

- `0x18000a210`
- `0x180013150`
- `0x180014a2c`
- `0x180015ab0`
- `0x1800321f0`
- `0x18003269c`
- `0x180032700`
- `0x18008bbd0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18008bc46`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18008bc46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008bd53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008bd53`
- `ole32!CoGetObject` at `0x18008bcf8`
- `ole32!CoGetObject` at `0x18008bcf8`

## string_xrefs

- `0x18008bc13`: `Session:%d!clsid:%s`
- `0x18008bc52`: `StringFromCLSID failed: 0x%x in %s`
- `0x18008bd2f`: `ptrClassFactory->CreateInstance failed: 0x%x in %s`

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
0x18008bbd0  mov     [rsp-18h+arg_0], rbx
0x18008bbd5  mov     [rsp-18h+arg_18], rsi
0x18008bbda  push    rbp
0x18008bbdb  push    rdi
0x18008bbdc  push    r14
0x18008bbde  mov     rbp, rsp
0x18008bbe1  sub     rsp, 80h
0x18008bbe8  mov     rax, cs:__security_cookie
0x18008bbef  xor     rax, rsp
0x18008bbf2  mov     [rbp+var_10], rax
0x18008bbf6  mov     r14, r8
0x18008bbf9  mov     esi, edx
0x18008bbfb  mov     [rbp+ppv], 0
0x18008bc03  mov     [rbp+lpsz], 0
0x18008bc0b  mov     [rbp+var_40], 0
0x18008bc13  movups  xmm0, xmmword ptr cs:aSessionDClsidS; "Session:%d!clsid:%s"
0x18008bc1a  movups  xmmword ptr [rbp+var_38], xmm0
0x18008bc1e  movups  xmm1, xmmword ptr cs:aSessionDClsidS+10h; "%d!clsid:%s"
0x18008bc25  movups  [rbp+var_28], xmm1
0x18008bc29  movsd   xmm0, qword ptr cs:aSessionDClsidS+20h; ":%s"
0x18008bc31  movsd   [rbp+var_18], xmm0
0x18008bc36  xor     edi, edi
0x18008bc38  mov     [r8], rdi
0x18008bc3b  lea     rdx, [rbp+lpsz]; lplpsz
0x18008bc3f  lea     rcx, CLSID_SessionDialog; rclsid
0x18008bc46  call    cs:__imp_StringFromCLSID
0x18008bc4c  mov     ebx, eax
0x18008bc4e  test    eax, eax
0x18008bc50  jns     short loc_18008BC5E
0x18008bc52  lea     rdx, aStringfromclsi_0; "StringFromCLSID failed: 0x%x in %s"
0x18008bc59  jmp     loc_18008BD36
0x18008bc5e  lea     r8, [rbp+var_40]; unsigned __int64 *
0x18008bc62  mov     edx, 27h ; '''; unsigned __int64
0x18008bc67  mov     rcx, [rbp+lpsz]; unsigned __int16 *
0x18008bc6b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18008bc70  mov     ebx, eax
0x18008bc72  test    eax, eax
0x18008bc74  jns     short loc_18008BC82
0x18008bc76  lea     rdx, aStringcchlengt_2; "StringCchLength failed: 0x%x in %s"
0x18008bc7d  jmp     loc_18008BD36
0x18008bc82  mov     rbx, [rbp+var_40]
0x18008bc86  add     rbx, 1Eh
0x18008bc8a  mov     eax, 2
0x18008bc8f  mul     rbx
0x18008bc92  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008bc99  cmovb   rax, rcx
0x18008bc9d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008bca4  mov     rcx, rax; unsigned __int64
0x18008bca7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18008bcac  mov     rdi, rax
0x18008bcaf  test    rax, rax
0x18008bcb2  jnz     short loc_18008BCBE
0x18008bcb4  mov     ebx, 8007000Eh
0x18008bcb9  jmp     loc_18008BD4A
0x18008bcbe  mov     rax, [rbp+lpsz]
0x18008bcc2  mov     [rsp+80h+var_60], rax
0x18008bcc7  mov     r9d, esi
0x18008bcca  lea     r8, [rbp+var_38]; unsigned __int16 *
0x18008bcce  mov     rdx, rbx; unsigned __int64
0x18008bcd1  mov     rcx, rdi; unsigned __int16 *
0x18008bcd4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008bcd9  mov     ebx, eax
0x18008bcdb  test    eax, eax
0x18008bcdd  jns     short loc_18008BCE8
0x18008bcdf  lea     rdx, aStringcchprint_1; "StringCchPrintfW failed: 0x%x in %s"
0x18008bce6  jmp     short loc_18008BD36
0x18008bce8  lea     r9, [rbp+ppv]; ppv
0x18008bcec  lea     r8, IID_IClassFactory; riid
0x18008bcf3  xor     edx, edx; pBindOptions
0x18008bcf5  mov     rcx, rdi; pszName
0x18008bcf8  call    cs:__imp_CoGetObject
0x18008bcfe  mov     ebx, eax
0x18008bd00  test    eax, eax
0x18008bd02  jns     short loc_18008BD0D
0x18008bd04  lea     rdx, aCogetobjectFai; "CoGetObject failed: 0x%x in %s"
0x18008bd0b  jmp     short loc_18008BD36
0x18008bd0d  mov     rcx, [rbp+ppv]
0x18008bd11  mov     rax, [rcx]
0x18008bd14  mov     r9, r14
0x18008bd17  lea     r8, IID_ISessionDialog
0x18008bd1e  xor     edx, edx
0x18008bd20  mov     rax, [rax+18h]
0x18008bd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bd29  mov     ebx, eax
0x18008bd2b  test    eax, eax
0x18008bd2d  jns     short loc_18008BD4A
0x18008bd2f  lea     rdx, aPtrclassfactor; "ptrClassFactory->CreateInstance failed:"...
0x18008bd36  lea     r9, aChybridhandler; "CHybridHandler::GetRequestDialogObject"
0x18008bd3d  mov     r8d, eax
0x18008bd40  mov     ecx, 8; int
0x18008bd45  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18008bd4a  mov     rcx, [rbp+lpsz]; pv
0x18008bd4e  test    rcx, rcx
0x18008bd51  jz      short loc_18008BD59
0x18008bd53  call    cs:__imp_CoTaskMemFree
0x18008bd59  test    rdi, rdi
0x18008bd5c  jz      short loc_18008BD67
0x18008bd5e  mov     rcx, rdi; Block
0x18008bd61  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18008bd66  nop
0x18008bd67  lea     rcx, [rbp+ppv]; void *
0x18008bd6b  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18008bd70  mov     eax, ebx
0x18008bd72  mov     rcx, [rbp+var_10]
0x18008bd76  xor     rcx, rsp; StackCookie
0x18008bd79  call    __security_check_cookie
0x18008bd7e  lea     r11, [rsp+80h+var_s0]
0x18008bd86  mov     rbx, [r11+20h]
0x18008bd8a  mov     rsi, [r11+38h]
0x18008bd8e  mov     rsp, r11
0x18008bd91  pop     r14
0x18008bd93  pop     rdi
0x18008bd94  pop     rbp
0x18008bd95  retn
```
