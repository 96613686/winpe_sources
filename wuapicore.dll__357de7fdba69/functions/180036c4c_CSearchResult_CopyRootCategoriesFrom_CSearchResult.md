# CSearchResult::CopyRootCategoriesFrom(CSearchResult *)

- ea: `0x180036c4c`
- end: `0x180036fbe`
- name: `?CopyRootCategoriesFrom@CSearchResult@@IEAAJPEAV1@@Z`
- size: `882`
- prototype: `__int64 __fastcall(CSearchResult *__hidden this, struct CSearchResult *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180020390`

## callees

- `0x180006ac4`
- `0x180007ecc`
- `0x180009b30`
- `0x180036c4c`
- `0x180037340`
- `0x180037af0`
- `0x1800388b0`
- `0x18009afb8`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036f20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036fb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036f20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036fb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036d11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036d11`
- `RPCRT4!UuidFromStringW` at `0x180036d79`
- `RPCRT4!UuidFromStringW` at `0x180036ea5`
- `RPCRT4!UuidFromStringW` at `0x180036d79`
- `RPCRT4!UuidFromStringW` at `0x180036ea5`
- `OLEAUT32!__imp_SysFreeString` at `0x180036d3d`
- `OLEAUT32!__imp_SysFreeString` at `0x180036dbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180036e44`
- `OLEAUT32!__imp_SysFreeString` at `0x180036e69`
- `OLEAUT32!__imp_SysFreeString` at `0x180036ef4`
- `OLEAUT32!__imp_SysFreeString` at `0x180036f97`
- `OLEAUT32!__imp_SysFreeString` at `0x180036d3d`
- `OLEAUT32!__imp_SysFreeString` at `0x180036dbc`
- `OLEAUT32!__imp_SysFreeString` at `0x180036e44`
- `OLEAUT32!__imp_SysFreeString` at `0x180036e69`
- `OLEAUT32!__imp_SysFreeString` at `0x180036ef4`
- `OLEAUT32!__imp_SysFreeString` at `0x180036f97`

## string_xrefs

- `0x180036c88`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x180036ce2`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x180036e12`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x180036e2f`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x180036f65`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`
- `0x180036f82`: `C:\__w\1\s\src\Client\comapi\SearchResult.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSearchResult::CopyRootCategoriesFrom(CSearchResult *this, struct CSearchResult *a2)
{
  UUID *v5; // rsi
  unsigned int v6; // r14d
  int v7; // eax
  unsigned int v8; // edi
  unsigned __int64 v9; // rbx
  __int64 i; // r15
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, RPC_WSTR *); // rdi
  int v13; // eax
  unsigned int v14; // eax
  int v15; // r14d
  __int64 v16; // rax
  __int64 j; // r14
  __int64 v18; // rdx
  struct CCategory *v19; // r15
  __int64 (__fastcall *v20)(char *, RPC_WSTR *); // rdi
  int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // [rsp+20h] [rbp-50h]
  unsigned __int64 v26; // [rsp+20h] [rbp-50h]
  RPC_WSTR StringUuid; // [rsp+28h] [rbp-48h] BYREF
  void **v28; // [rsp+30h] [rbp-40h] BYREF
  UUID *v29; // [rsp+38h] [rbp-38h]
  __int128 v30; // [rsp+40h] [rbp-30h]
  UUID Uuid; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  if ( a2 )
  {
    v5 = 0;
    v29 = 0;
    v30 = 0u;
    v6 = 0;
    v28 = &CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable';
    v7 = (*(__int64 (__fastcall **)(struct CSearchResult *))(*(_QWORD *)a2 + 16LL))(a2);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v9 = ((unsigned __int64)this + 232) & -(__int64)(this != 0);
      if ( v9 )
        EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
      v26 = ((unsigned __int64)this + 232) & -(__int64)(this != 0);
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v16 = *((_QWORD *)this + 59);
        if ( (unsigned int)i >= *(_DWORD *)(v16 + 68) )
          break;
        v11 = *(_QWORD *)(*(_QWORD *)(v16 + 56) + 8 * i);
        StringUuid = 0;
        v12 = *(__int64 (__fastcall **)(__int64, RPC_WSTR *))(*(_QWORD *)(v11 + 8) + 64LL);
        SysFreeString(0);
        StringUuid = 0;
        v13 = v12(v11 + 8, &StringUuid);
        v8 = v13;
        if ( v13 < 0 )
        {
          v18 = 1649;
LABEL_19:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
            (const char *)(unsigned int)v13,
            v26);
LABEL_20:
          SysFreeString(StringUuid);
LABEL_38:
          if ( v9 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
          goto LABEL_32;
        }
        Uuid = GUID_NULL;
        v14 = UuidFromStringW(StringUuid, &Uuid);
        if ( v14 )
        {
          v8 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x674,
                 (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
                 (const char *)v14,
                 v26);
          goto LABEL_20;
        }
        v13 = CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Grow(&v28, v6 + 1);
        v8 = v13;
        if ( v13 < 0 )
        {
          v18 = 1654;
          goto LABEL_19;
        }
        v15 = DWORD1(v30);
        v5 = v29;
        v29[DWORD1(v30)] = Uuid;
        v6 = v15 + 1;
        DWORD1(v30) = v6;
        SysFreeString(StringUuid);
        StringUuid = 0;
      }
      if ( v6 > 1 )
        qsort(v5, v6, 0x10u, CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::CompareWeights);
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        v24 = *((_QWORD *)a2 + 59);
        if ( (unsigned int)j >= *(_DWORD *)(v24 + 68) )
          break;
        v19 = *(struct CCategory **)(*(_QWORD *)(v24 + 56) + 8 * j);
        StringUuid = 0;
        v20 = *(__int64 (__fastcall **)(char *, RPC_WSTR *))(*((_QWORD *)v19 + 1) + 64LL);
        SysFreeString(0);
        StringUuid = 0;
        v21 = v20((char *)v19 + 8, &StringUuid);
        v8 = v21;
        if ( v21 < 0 )
        {
          v23 = 1670;
LABEL_36:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v23,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
            (const char *)(unsigned int)v21,
            v26);
LABEL_37:
          SysFreeString(StringUuid);
          StringUuid = 0;
          goto LABEL_38;
        }
        Uuid = GUID_NULL;
        v22 = UuidFromStringW(StringUuid, &Uuid);
        if ( v22 )
        {
          v8 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x689,
                 (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
                 (const char *)v22,
                 v26);
          goto LABEL_37;
        }
        v21 = CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Add(&v28, &Uuid, 1);
        v8 = v21;
        if ( v21 >= 0 )
        {
          v21 = CCategoryCollection::AddInner(*((CCategoryCollection **)this + 59), v19);
          v8 = v21;
          if ( v21 < 0 )
          {
            v23 = 1686;
            goto LABEL_36;
          }
        }
        else if ( v21 != -2145124333 )
        {
          v23 = 1678;
          goto LABEL_36;
        }
        SysFreeString(StringUuid);
        StringUuid = 0;
      }
      if ( v9 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
      v8 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x662,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
        (const char *)(unsigned int)v7,
        v25);
    }
LABEL_32:
    CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>(&v28);
    return v8;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65E,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\SearchResult.cpp",
      (const char *)0x80004003LL,
      v25);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180036c4c  mov     [rsp-38h+arg_10], rbx
0x180036c51  push    rbp
0x180036c52  push    rsi
0x180036c53  push    rdi
0x180036c54  push    r12
0x180036c56  push    r13
0x180036c58  push    r14
0x180036c5a  push    r15
0x180036c5c  mov     rbp, rsp
0x180036c5f  sub     rsp, 70h
0x180036c63  mov     rax, cs:__security_cookie
0x180036c6a  xor     rax, rsp
0x180036c6d  mov     [rbp+var_10], rax
0x180036c71  mov     r12, rdx
0x180036c74  mov     r13, rcx
0x180036c77  test    rdx, rdx
0x180036c7a  jnz     short loc_180036CA0
0x180036c7c  mov     rcx, [rbp+38h]; this
0x180036c80  mov     ebx, 80004003h
0x180036c85  mov     r9d, ebx; char *
0x180036c88  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180036c8f  mov     edx, 65Eh; void *
0x180036c94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036c99  mov     eax, ebx
0x180036c9b  jmp     loc_180036F33
0x180036ca0  xorps   xmm0, xmm0
0x180036ca3  movups  [rbp+var_40], xmm0
0x180036ca7  movups  [rbp+var_30], xmm0
0x180036cab  xor     esi, esi
0x180036cad  mov     qword ptr [rbp+var_40+8], rsi
0x180036cb1  mov     qword ptr [rbp+var_30], rsi
0x180036cb5  xor     r14d, r14d
0x180036cb8  lea     rax, ??_7?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@6B@; const CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::`vftable'
0x180036cbf  mov     qword ptr [rbp+var_40], rax
0x180036cc3  mov     dword ptr [rbp+var_30+8], esi
0x180036cc6  mov     rax, [rdx]
0x180036cc9  mov     rcx, r12
0x180036ccc  mov     rax, [rax+10h]
0x180036cd0  call    _guard_dispatch_icall
0x180036cd5  mov     edi, eax
0x180036cd7  test    eax, eax
0x180036cd9  jns     short loc_180036CF8
0x180036cdb  mov     rcx, [rbp+38h]; this
0x180036cdf  mov     r9d, eax; char *
0x180036ce2  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180036ce9  mov     edx, 662h; void *
0x180036cee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036cf3  jmp     loc_180036F28
0x180036cf8  mov     rax, r13
0x180036cfb  lea     rcx, [r13+0E8h]
0x180036d02  neg     rax
0x180036d05  sbb     rbx, rbx
0x180036d08  and     rbx, rcx
0x180036d0b  jz      short loc_180036D17
0x180036d0d  lea     rcx, [rbx+8]; lpCriticalSection
0x180036d11  call    cs:__imp_EnterCriticalSection
0x180036d17  mov     [rbp+var_50], rbx
0x180036d1b  xor     r15d, r15d
0x180036d1e  jmp     loc_180036DCD
0x180036d23  mov     rax, [rax+38h]
0x180036d27  mov     rsi, [rax+r15*8]
0x180036d2b  mov     [rbp+StringUuid], 0
0x180036d33  mov     rax, [rsi+8]
0x180036d37  mov     rdi, [rax+40h]
0x180036d3b  xor     ecx, ecx; bstrString
0x180036d3d  call    cs:__imp_SysFreeString
0x180036d43  mov     [rbp+StringUuid], 0
0x180036d4b  lea     rdx, [rbp+StringUuid]
0x180036d4f  lea     rcx, [rsi+8]
0x180036d53  mov     rax, rdi
0x180036d56  call    _guard_dispatch_icall
0x180036d5b  mov     edi, eax
0x180036d5d  test    eax, eax
0x180036d5f  js      loc_180036E27
0x180036d65  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180036d6c  movdqu  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180036d71  lea     rdx, [rbp+Uuid]; Uuid
0x180036d75  mov     rcx, [rbp+StringUuid]; StringUuid
0x180036d79  call    cs:__imp_UuidFromStringW
0x180036d7f  test    eax, eax
0x180036d81  jnz     loc_180036E0B
0x180036d87  lea     edx, [r14+1]
0x180036d8b  lea     rcx, [rbp+var_40]
0x180036d8f  call    ?Grow@?$CSusArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@QEAAJK@Z; CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Grow(ulong)
0x180036d94  mov     edi, eax
0x180036d96  test    eax, eax
0x180036d98  js      short loc_180036E04
0x180036d9a  mov     r14d, dword ptr [rbp+var_30+4]
0x180036d9e  mov     eax, r14d
0x180036da1  add     rax, rax
0x180036da4  movups  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180036da8  mov     rsi, qword ptr [rbp+var_40+8]
0x180036dac  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x180036db1  inc     r14d
0x180036db4  mov     dword ptr [rbp+var_30+4], r14d
0x180036db8  mov     rcx, [rbp+StringUuid]; bstrString
0x180036dbc  call    cs:__imp_SysFreeString
0x180036dc2  mov     [rbp+StringUuid], 0
0x180036dca  inc     r15d
0x180036dcd  mov     rax, [r13+1D8h]
0x180036dd4  cmp     r15d, [rax+44h]
0x180036dd8  jb      loc_180036D23
0x180036dde  cmp     r14d, 1
0x180036de2  jbe     short loc_180036DFC
0x180036de4  mov     edx, r14d; NumOfElements
0x180036de7  lea     r9, ?CompareWeights@?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@CAHPEBX0@Z; CompareFunction
0x180036dee  mov     r8d, 10h; SizeOfElements
0x180036df4  mov     rcx, rsi; Base
0x180036df7  call    qsort
0x180036dfc  xor     r14d, r14d
0x180036dff  jmp     loc_180036F05
0x180036e04  mov     edx, 676h
0x180036e09  jmp     short loc_180036E2C
0x180036e0b  mov     rcx, [rbp+38h]; this
0x180036e0f  mov     r9d, eax; char *
0x180036e12  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180036e19  mov     edx, 674h; void *
0x180036e1e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036e23  mov     edi, eax
0x180036e25  jmp     short loc_180036E40
0x180036e27  mov     edx, 671h; void *
0x180036e2c  mov     r9d, eax; char *
0x180036e2f  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180036e36  mov     rcx, [rbp+38h]; this
0x180036e3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036e3f  nop
0x180036e40  mov     rcx, [rbp+StringUuid]; bstrString
0x180036e44  call    cs:__imp_SysFreeString
0x180036e4a  jmp     loc_180036FA5
0x180036e4f  mov     rax, [rax+38h]
0x180036e53  mov     r15, [rax+r14*8]
0x180036e57  mov     [rbp+StringUuid], 0
0x180036e5f  mov     rax, [r15+8]
0x180036e63  mov     rdi, [rax+40h]
0x180036e67  xor     ecx, ecx; bstrString
0x180036e69  call    cs:__imp_SysFreeString
0x180036e6f  mov     [rbp+StringUuid], 0
0x180036e77  lea     rdx, [rbp+StringUuid]
0x180036e7b  lea     rcx, [r15+8]
0x180036e7f  mov     rax, rdi
0x180036e82  call    _guard_dispatch_icall
0x180036e87  mov     edi, eax
0x180036e89  test    eax, eax
0x180036e8b  js      loc_180036F7A
0x180036e91  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180036e98  movdqu  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180036e9d  lea     rdx, [rbp+Uuid]; Uuid
0x180036ea1  mov     rcx, [rbp+StringUuid]; StringUuid
0x180036ea5  call    cs:__imp_UuidFromStringW
0x180036eab  test    eax, eax
0x180036ead  jnz     loc_180036F5E
0x180036eb3  lea     r8d, [rax+1]
0x180036eb7  lea     rdx, [rbp+Uuid]
0x180036ebb  lea     rcx, [rbp+var_40]
0x180036ebf  call    ?Add@?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@QEAAJAEBU_GUID@@K@Z; CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::Add(_GUID const &,ulong)
0x180036ec4  mov     edi, eax
0x180036ec6  test    eax, eax
0x180036ec8  jns     short loc_180036EDB
0x180036eca  cmp     eax, 80240013h
0x180036ecf  jz      short loc_180036EF0
0x180036ed1  mov     edx, 68Eh
0x180036ed6  jmp     loc_180036F7F
0x180036edb  mov     rdx, r15; struct CCategory *
0x180036ede  mov     rcx, [r13+1D8h]; this
0x180036ee5  call    ?AddInner@CCategoryCollection@@IEAAJPEAVCCategory@@@Z; CCategoryCollection::AddInner(CCategory *)
0x180036eea  mov     edi, eax
0x180036eec  test    eax, eax
0x180036eee  js      short loc_180036F57
0x180036ef0  mov     rcx, [rbp+StringUuid]; bstrString
0x180036ef4  call    cs:__imp_SysFreeString
0x180036efa  mov     [rbp+StringUuid], 0
0x180036f02  inc     r14d
0x180036f05  mov     rax, [r12+1D8h]
0x180036f0d  cmp     r14d, [rax+44h]
0x180036f11  jb      loc_180036E4F
0x180036f17  test    rbx, rbx
0x180036f1a  jz      short loc_180036F26
0x180036f1c  lea     rcx, [rbx+8]; lpCriticalSection
0x180036f20  call    cs:__imp_LeaveCriticalSection
0x180036f26  xor     edi, edi
0x180036f28  lea     rcx, [rbp+var_40]
0x180036f2c  call    ??1?$CSusArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@UEAA@XZ; CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>(void)
0x180036f31  mov     eax, edi
0x180036f33  mov     rcx, [rbp+var_10]
0x180036f37  xor     rcx, rsp; StackCookie
0x180036f3a  call    __security_check_cookie
0x180036f3f  mov     rbx, [rsp+70h+arg_10]
0x180036f47  add     rsp, 70h
0x180036f4b  pop     r15
0x180036f4d  pop     r14
0x180036f4f  pop     r13
0x180036f51  pop     r12
0x180036f53  pop     rdi
0x180036f54  pop     rsi
0x180036f55  pop     rbp
0x180036f56  retn
0x180036f57  mov     edx, 696h
0x180036f5c  jmp     short loc_180036F7F
0x180036f5e  mov     rcx, [rbp+38h]; this
0x180036f62  mov     r9d, eax; char *
0x180036f65  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180036f6c  mov     edx, 689h; void *
0x180036f71  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036f76  mov     edi, eax
0x180036f78  jmp     short loc_180036F93
0x180036f7a  mov     edx, 686h; void *
0x180036f7f  mov     r9d, eax; char *
0x180036f82  lea     r8, aCW1SSrcClientC_67; "C:\\__w\\1\\s\\src\\Client\\comapi\\Sea"...
0x180036f89  mov     rcx, [rbp+38h]; this
0x180036f8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036f92  nop
0x180036f93  mov     rcx, [rbp+StringUuid]; bstrString
0x180036f97  call    cs:__imp_SysFreeString
0x180036f9d  mov     [rbp+StringUuid], 0
0x180036fa5  test    rbx, rbx
0x180036fa8  jz      loc_180036F28
0x180036fae  lea     rcx, [rbx+8]; lpCriticalSection
0x180036fb2  call    cs:__imp_LeaveCriticalSection
0x180036fb8  jmp     loc_180036F28
```
