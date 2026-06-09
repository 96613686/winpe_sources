# _lambda_639341b02e32c8ae0d65114f396fb9ff_::operator()(void)

- ea: `0x18003c080`
- end: `0x18003c3b3`
- name: `??R_lambda_639341b02e32c8ae0d65114f396fb9ff_@@QEBA@XZ`
- size: `819`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ff10`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x180019750`
- `0x18001ba34`
- `0x1800275f8`
- `0x18002a508`
- `0x180035830`
- `0x18003bf18`
- `0x18003c080`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c269`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c2ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c2ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c269`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c2ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c2ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c33a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c36a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c33a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c36a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c0bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c0bb`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x18003c2f8`
- `api-ms-win-shell-namespace-l1-1-0!SHGetIDListFromObject` at `0x18003c2f8`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18003c0d1`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18003c0d1`
- `SHELL32!SHChangeNotify` at `0x18003c353`
- `SHELL32!SHChangeNotify` at `0x18003c353`

## string_xrefs

- `0x18003c0e4`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003c17f`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003c1f8`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003c29b`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18003c314`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _lambda_639341b02e32c8ae0d65114f396fb9ff_::operator()(__int64 a1)
{
  const WCHAR *StringRawBuffer; // rax
  HRESULT v3; // eax
  HRESULT v4; // ebx
  void *v5; // rdi
  int (__fastcall *v6)(void *, IUnknown **); // rbx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  void *v11; // rcx
  void *v12; // rcx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-49h] BYREF
  _QWORD v15[2]; // [rsp+30h] [rbp-39h] BYREF
  PROPERTYKEY ppidl; // [rsp+40h] [rbp-29h] BYREF
  IUnknown *punk; // [rsp+60h] [rbp-9h] BYREF
  __int64 v18; // [rsp+68h] [rbp-1h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+7h] BYREF
  __int64 v20; // [rsp+78h] [rbp+Fh] BYREF
  void *ppv; // [rsp+80h] [rbp+17h] BYREF
  int v22; // [rsp+88h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  StringRawBuffer = WindowsGetStringRawBuffer(**(HSTRING **)a1, 0);
  v3 = SHCreateItemFromParsingName(StringRawBuffer, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x456,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v3,
      (int)SRWLock[0]);
    goto LABEL_29;
  }
  punk = 0;
  v22 = 0;
  v5 = ppv;
  v6 = *(int (__fastcall **)(void *, IUnknown **))(*(_QWORD *)ppv + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk);
  if ( v6(v5, &punk) < 0
    || ((int (__fastcall *)(IUnknown *, __int64, int *))punk->lpVtbl[2].QueryInterface)(punk, 0x20000000, &v22) < 0 )
  {
LABEL_28:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk);
    v4 = 0;
    goto LABEL_29;
  }
  v15[0] = 0;
  v18 = 0;
  v7 = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v18, punk);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45D,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v7,
      (int)SRWLock[0]);
LABEL_7:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk);
    goto LABEL_29;
  }
  ppidl = PKEY_ThumbnailCacheId;
  if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt64<_tagpropertykey>(&v18, &ppidl, v15) < 0 )
  {
LABEL_27:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    goto LABEL_28;
  }
  v20 = 0;
  v8 = Microsoft::WRL::ComPtr<IThumbnailCachePrivate>::As<IThumbnailCache3>(*(_QWORD *)(a1 + 8), &v20);
  v4 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x461,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v8,
      (int)SRWLock[0]);
LABEL_11:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    goto LABEL_7;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, *(_QWORD *)(a1 + 16) + 64LL);
  v9 = **(_QWORD **)(a1 + 8);
  v15[1] = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v9 + 72LL))(v9, v15);
  v4 = v10;
  if ( v10 >= 0 )
  {
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    pv = 0;
    *(_QWORD *)&ppidl.fmtid.Data1 = &pv;
    *(_QWORD *)ppidl.fmtid.Data4 = 0;
    LOBYTE(ppidl.pid) = 1;
    v4 = SHGetIDListFromObject(punk, (LPITEMIDLIST *)ppidl.fmtid.Data4);
    wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&ppidl);
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46A,
        (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
        (const char *)(unsigned int)v4,
        (int)SRWLock[0]);
      v11 = pv;
      pv = 0;
      if ( v11 )
        CoTaskMemFree(v11);
      goto LABEL_11;
    }
    SHChangeNotify(0x2000, 0, pv, 0);
    v12 = pv;
    pv = 0;
    if ( v12 )
      CoTaskMemFree(v12);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
    goto LABEL_27;
  }
  if ( v10 != -2147287038 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x466,
      (unsigned int)"onecoreuap\\shell\\ext\\thumbnailcache\\lib\\thumbcacheapi.cpp",
      (const char *)(unsigned int)v10,
      (int)SRWLock[0]);
    if ( SRWLock[0] )
      ReleaseSRWLockExclusive(SRWLock[0]);
    goto LABEL_11;
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punk);
  v4 = -2147287038;
LABEL_29:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003c080  push    rbp
0x18003c082  push    rbx
0x18003c083  push    rsi
0x18003c084  push    rdi
0x18003c085  lea     rbp, [rsp-3Fh]
0x18003c08a  sub     rsp, 0A8h
0x18003c091  mov     rax, cs:__security_cookie
0x18003c098  xor     rax, rsp
0x18003c09b  mov     [rbp+57h+var_30], rax
0x18003c09f  mov     rsi, rcx
0x18003c0a2  mov     [rbp+57h+ppv], 0
0x18003c0aa  lea     rcx, [rbp+57h+ppv]
0x18003c0ae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c0b3  mov     rcx, [rsi]
0x18003c0b6  xor     edx, edx; length
0x18003c0b8  mov     rcx, [rcx]; string
0x18003c0bb  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c0c1  lea     r9, [rbp+57h+ppv]; ppv
0x18003c0c5  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003c0cc  xor     edx, edx; pbc
0x18003c0ce  mov     rcx, rax; pszPath
0x18003c0d1  call    cs:__imp_SHCreateItemFromParsingName
0x18003c0d7  mov     ebx, eax
0x18003c0d9  test    eax, eax
0x18003c0db  jns     short loc_18003C0FA
0x18003c0dd  mov     rcx, [rbp+5Fh]; this
0x18003c0e1  mov     r9d, eax; char *
0x18003c0e4  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003c0eb  mov     edx, 456h; void *
0x18003c0f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c0f5  jmp     loc_18003C390
0x18003c0fa  mov     [rbp+57h+punk], 0
0x18003c102  mov     [rbp+57h+var_38], 0
0x18003c109  mov     rdi, [rbp+57h+ppv]
0x18003c10d  mov     rax, [rdi]
0x18003c110  mov     rbx, [rax+20h]
0x18003c114  lea     rcx, [rbp+57h+punk]
0x18003c118  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c11d  lea     rdx, [rbp+57h+punk]
0x18003c121  mov     rcx, rdi
0x18003c124  mov     rax, rbx
0x18003c127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c12c  test    eax, eax
0x18003c12e  js      loc_18003C385
0x18003c134  mov     rcx, [rbp+57h+punk]
0x18003c138  mov     rax, [rcx]
0x18003c13b  lea     r8, [rbp+57h+var_38]
0x18003c13f  mov     edx, 20000000h
0x18003c144  mov     rax, [rax+30h]
0x18003c148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c14d  test    eax, eax
0x18003c14f  js      loc_18003C385
0x18003c155  mov     [rbp+57h+var_90], 0
0x18003c15d  mov     [rbp+57h+var_58], 0
0x18003c165  mov     rdx, [rbp+57h+punk]
0x18003c169  lea     rcx, [rbp+57h+var_58]
0x18003c16d  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x18003c172  mov     ebx, eax
0x18003c174  test    eax, eax
0x18003c176  jns     short loc_18003C1A9
0x18003c178  mov     rcx, [rbp+5Fh]; this
0x18003c17c  mov     r9d, eax; char *
0x18003c17f  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003c186  mov     edx, 45Dh; void *
0x18003c18b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c190  nop
0x18003c191  lea     rcx, [rbp+57h+var_58]
0x18003c195  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c19a  nop
0x18003c19b  lea     rcx, [rbp+57h+punk]
0x18003c19f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c1a4  jmp     loc_18003C390
0x18003c1a9  movups  xmm0, xmmword ptr cs:PKEY_ThumbnailCacheId.fmtid.Data1
0x18003c1b0  movaps  xmmword ptr [rbp+57h+ppidl], xmm0
0x18003c1b4  mov     eax, cs:PKEY_ThumbnailCacheId.pid
0x18003c1ba  mov     [rbp+57h+var_70], eax
0x18003c1bd  lea     r8, [rbp+57h+var_90]
0x18003c1c1  lea     rdx, [rbp+57h+ppidl]
0x18003c1c5  lea     rcx, [rbp+57h+var_58]
0x18003c1c9  call    ??$GetUInt64@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEA_K@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt64<_tagpropertykey>(_tagpropertykey,unsigned __int64 *)
0x18003c1ce  test    eax, eax
0x18003c1d0  js      loc_18003C37B
0x18003c1d6  mov     [rbp+57h+var_48], 0
0x18003c1de  lea     rdx, [rbp+57h+var_48]
0x18003c1e2  mov     rcx, [rsi+8]
0x18003c1e6  call    ??$As@UIThumbnailCache3@@@?$ComPtr@UIThumbnailCachePrivate@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIThumbnailCache3@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IThumbnailCachePrivate>::As<IThumbnailCache3>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IThumbnailCache3>>)
0x18003c1eb  mov     ebx, eax
0x18003c1ed  test    eax, eax
0x18003c1ef  jns     short loc_18003C218
0x18003c1f1  mov     rcx, [rbp+5Fh]; this
0x18003c1f5  mov     r9d, eax; char *
0x18003c1f8  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003c1ff  mov     edx, 461h; void *
0x18003c204  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c209  nop
0x18003c20a  lea     rcx, [rbp+57h+var_48]
0x18003c20e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c213  jmp     loc_18003C191
0x18003c218  mov     rdx, [rsi+10h]
0x18003c21c  add     rdx, 40h ; '@'
0x18003c220  lea     rcx, [rbp+57h+SRWLock]
0x18003c224  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18003c229  nop
0x18003c22a  mov     rax, [rsi+8]
0x18003c22e  mov     rcx, [rax]
0x18003c231  mov     rax, [rbp+57h+var_90]
0x18003c235  mov     [rbp+57h+var_90], rax
0x18003c239  mov     [rbp+57h+var_88], 0
0x18003c241  mov     rax, [rcx]
0x18003c244  lea     rdx, [rbp+57h+var_90]
0x18003c248  mov     rax, [rax+48h]
0x18003c24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c251  mov     ebx, eax
0x18003c253  test    eax, eax
0x18003c255  jns     short loc_18003C2C5
0x18003c257  mov     edi, 80030002h
0x18003c25c  cmp     eax, edi
0x18003c25e  jnz     short loc_18003C294
0x18003c260  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003c264  test    rcx, rcx
0x18003c267  jz      short loc_18003C270
0x18003c269  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c26f  nop
0x18003c270  lea     rcx, [rbp+57h+var_48]
0x18003c274  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c279  nop
0x18003c27a  lea     rcx, [rbp+57h+var_58]
0x18003c27e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c283  nop
0x18003c284  lea     rcx, [rbp+57h+punk]
0x18003c288  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c28d  mov     ebx, edi
0x18003c28f  jmp     loc_18003C390
0x18003c294  mov     rcx, [rbp+5Fh]; this
0x18003c298  mov     r9d, eax; char *
0x18003c29b  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003c2a2  mov     edx, 466h; void *
0x18003c2a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c2ac  nop
0x18003c2ad  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003c2b1  test    rcx, rcx
0x18003c2b4  jz      loc_18003C20A
0x18003c2ba  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c2c0  jmp     loc_18003C20A
0x18003c2c5  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18003c2c9  test    rcx, rcx
0x18003c2cc  jz      short loc_18003C2D4
0x18003c2ce  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c2d4  mov     [rbp+57h+pv], 0
0x18003c2dc  lea     rax, [rbp+57h+pv]
0x18003c2e0  mov     [rbp+57h+ppidl], rax
0x18003c2e4  mov     [rbp+57h+ppidl+8], 0
0x18003c2ec  mov     byte ptr [rbp+57h+var_70], 1
0x18003c2f0  lea     rdx, [rbp+57h+ppidl+8]; ppidl
0x18003c2f4  mov     rcx, [rbp+57h+punk]; punk
0x18003c2f8  call    cs:__imp_SHGetIDListFromObject
0x18003c2fe  mov     ebx, eax
0x18003c300  lea     rcx, [rbp+57h+ppidl]
0x18003c304  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18003c309  test    ebx, ebx
0x18003c30b  jns     short loc_18003C345
0x18003c30d  mov     rcx, [rbp+5Fh]; this
0x18003c311  mov     r9d, ebx; char *
0x18003c314  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\ext\\thumbnailcache"...
0x18003c31b  mov     edx, 46Ah; void *
0x18003c320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c325  mov     rcx, [rbp+57h+pv]; pv
0x18003c329  mov     [rbp+57h+pv], 0
0x18003c331  test    rcx, rcx
0x18003c334  jz      loc_18003C20A
0x18003c33a  call    cs:__imp_CoTaskMemFree
0x18003c340  jmp     loc_18003C20A
0x18003c345  xor     r9d, r9d; dwItem2
0x18003c348  mov     r8, [rbp+57h+pv]; dwItem1
0x18003c34c  xor     edx, edx; uFlags
0x18003c34e  mov     ecx, 2000h; wEventId
0x18003c353  call    cs:__imp_SHChangeNotify
0x18003c359  mov     rcx, [rbp+57h+pv]; pv
0x18003c35d  mov     [rbp+57h+pv], 0
0x18003c365  test    rcx, rcx
0x18003c368  jz      short loc_18003C371
0x18003c36a  call    cs:__imp_CoTaskMemFree
0x18003c370  nop
0x18003c371  lea     rcx, [rbp+57h+var_48]
0x18003c375  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c37a  nop
0x18003c37b  lea     rcx, [rbp+57h+var_58]
0x18003c37f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c384  nop
0x18003c385  lea     rcx, [rbp+57h+punk]
0x18003c389  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c38e  xor     ebx, ebx
0x18003c390  lea     rcx, [rbp+57h+ppv]
0x18003c394  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003c399  mov     eax, ebx
0x18003c39b  mov     rcx, [rbp+57h+var_30]
0x18003c39f  xor     rcx, rsp; StackCookie
0x18003c3a2  call    __security_check_cookie
0x18003c3a7  add     rsp, 0A8h
0x18003c3ae  pop     rdi
0x18003c3af  pop     rsi
0x18003c3b0  pop     rbx
0x18003c3b1  pop     rbp
0x18003c3b2  retn
```
