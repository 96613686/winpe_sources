# SxsQueryAssemblyInfo

- ea: `0x180052c98`
- end: `0x180053092`
- name: `SxsQueryAssemblyInfo`
- size: `1018`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180052ba0`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180029380`
- `0x18002b5e4`
- `0x18002df40`
- `0x18002e98c`
- `0x18002ed00`
- `0x180030148`
- `0x180052c98`
- `0x180053098`
- `0x180053110`
- `0x18005c168`
- `0x18005c88c`
- `0x18005c978`
- `0x18005d2b0`
- `0x18005d38c`
- `0x180068724`
- `0x18006a0dd`
- `0x18006a110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052d2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052d7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052dc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052dee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052dfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052e58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052ea9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052ef0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052f21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053036`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052d2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052d7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052dc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052dee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052dfc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052e58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052ea9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052ef0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052f21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180053036`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052d48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180052d48`

## string_xrefs

- `0x180052fe5`: `SXS: %s - insufficient buffer passed in.  cchBuf passed in: %u; cchPath computed: %u\n`

## pseudocode

```c
__int64 __fastcall SxsQueryAssemblyInfo(int a1, const WCHAR *a2, __int64 a3)
{
  const char *v6; // rcx
  void *v7; // rax
  __int64 v8; // rdi
  HRESULT IsAssemblyInstalled; // ebx
  int v10; // edx
  char **v11; // rcx
  int v12; // eax
  int v13; // ebx
  DWORD v14; // ecx
  __int64 v15; // rbx
  __int64 v16; // rdx
  LPASSEMBLYNAME v17; // rcx
  int InstalledAssemblyName; // eax
  int v19; // r14d
  unsigned int v20; // ecx
  int v21; // eax
  int v22; // edi
  const void *v23; // rdx
  unsigned int v24; // eax
  unsigned int v25; // ebx
  unsigned int v26; // r9d
  size_t v27; // rbx
  unsigned int v28; // ebx
  bool v30; // [rsp+30h] [rbp-39h] BYREF
  int v31; // [rsp+38h] [rbp-31h] BYREF
  __int64 v32; // [rsp+40h] [rbp-29h] BYREF
  char v33; // [rsp+48h] [rbp-21h]
  int v34; // [rsp+50h] [rbp-19h] BYREF
  LPASSEMBLYNAME ppAssemblyNameObj; // [rsp+58h] [rbp-11h] BYREF
  int v36; // [rsp+60h] [rbp-9h] BYREF
  __int64 v37; // [rsp+68h] [rbp-1h]
  __int64 *v38; // [rsp+70h] [rbp+7h]
  __int64 v39; // [rsp+78h] [rbp+Fh]
  int v40; // [rsp+80h] [rbp+17h]
  int *v41; // [rsp+88h] [rbp+1Fh]

  v39 = 544438355;
  v34 = 0;
  v38 = &qword_1800722F0;
  v37 = 0;
  v40 = 3859;
  v36 = 1;
  v41 = &v34;
  CFrame::BaseEnter((CFrame *)&v36);
  ppAssemblyNameObj = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  if ( a1 || !a2 )
  {
    v40 = 3865;
    FusionpTraceParameterCheck(v6);
    v14 = 87;
    goto LABEL_41;
  }
  SetLastError(0);
  v7 = HeapAlloc(g_hHeap, 0, 0x460u);
  v8 = (__int64)v7;
  if ( !v7 )
  {
    v11 = off_180072330;
    goto LABEL_38;
  }
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v7);
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>((void *)(v8 + 560));
  v32 = v8;
  v33 = 1;
  SetLastError(0);
  IsAssemblyInstalled = CreateAssemblyNameObject(&ppAssemblyNameObj, a2, 1u, 0);
  if ( IsAssemblyInstalled >= 0 )
  {
    SetLastError(0);
    IsAssemblyInstalled = CAssemblyName::IsAssemblyInstalled((CAssemblyName *)ppAssemblyNameObj, &v31);
    if ( IsAssemblyInstalled >= 0 )
    {
      if ( !a3 )
      {
        if ( v31 )
        {
          SetLastError(0);
          SetLastError(0);
          *v41 = 1;
          goto LABEL_42;
        }
        CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v36, 0x490u);
        v11 = off_180075110;
LABEL_39:
        FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v11);
        goto LABEL_42;
      }
      if ( !v31 )
      {
        CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v36, 0x490u);
        v11 = off_1800750F0;
        goto LABEL_39;
      }
      *(_DWORD *)(a3 + 4) |= 1u;
      v31 = 0;
      SetLastError(0);
      v12 = CAssemblyName::DetermineAssemblyType((CAssemblyName *)ppAssemblyNameObj, &v31);
      v13 = v12;
      if ( v12 < 0 )
      {
        FusionpTraceCOMFailure(v12, byte_18008517D);
        v31 = v13;
        FusionpConvertCOMFailure(&v31);
        v14 = FusionpHRESULTToWin32(v31);
LABEL_41:
        SetLastError(v14);
        *v41 = 0;
        goto LABEL_42;
      }
      v15 = v8 + 560;
      SetLastError(0);
      v17 = ppAssemblyNameObj;
      if ( !v31 )
      {
        InstalledAssemblyName = CAssemblyName::GetInstalledAssemblyName((__int64)ppAssemblyNameObj, v16, 2u, v8);
        v19 = InstalledAssemblyName;
        if ( InstalledAssemblyName < 0 )
        {
          FusionpTraceCOMFailure(InstalledAssemblyName, byte_18008517D);
          v10 = v19;
          goto LABEL_6;
        }
        v30 = 0;
        SetLastError(0);
        if ( !SxspDoesFileExist(v20, *(const unsigned __int16 **)(v8 + 16), &v30) )
        {
          v11 = off_1800750D0;
LABEL_38:
          *v41 = 0;
          goto LABEL_39;
        }
        if ( v30 )
        {
          v23 = *(const void **)(v8 + 16);
          v24 = -1;
          if ( *(_QWORD *)(v8 + 32) <= 0xFFFFFFFF )
            v24 = *(_DWORD *)(v8 + 32);
          goto LABEL_29;
        }
        SetLastError(0);
        v17 = ppAssemblyNameObj;
      }
      v21 = CAssemblyName::GetInstalledAssemblyName((__int64)v17, v16, 1u, v8 + 560);
      v22 = v21;
      if ( v21 < 0 )
      {
        FusionpTraceCOMFailure(v21, byte_18008517D);
        v10 = v22;
        goto LABEL_6;
      }
      v23 = *(const void **)(v15 + 16);
      v24 = -1;
      if ( *(_QWORD *)(v15 + 32) <= 0xFFFFFFFF )
        v24 = *(_DWORD *)(v15 + 32);
LABEL_29:
      v25 = v24 + 1;
      if ( v24 + 1 < v24 )
      {
        CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v36, 0x216u);
        FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180072370);
        goto LABEL_42;
      }
      v26 = *(_DWORD *)(a3 + 24);
      if ( v26 < v25 )
      {
        if ( v26 || *(_QWORD *)(a3 + 16) )
        {
          FusionpDbgPrintEx(
            0x80000002,
            "SXS: %s - insufficient buffer passed in.  cchBuf passed in: %u; cchPath computed: %u\n",
            "SxsQueryAssemblyInfo",
            v26,
            v24 + 1);
          *(_DWORD *)(a3 + 24) = v25;
          CFnTracerWin32::MarkWin32Failure((CFnTracerWin32 *)&v36, 0x7Au);
          v11 = off_1800750B0;
          goto LABEL_39;
        }
      }
      else
      {
        v27 = 2LL * v24;
        memcpy_0(*(void **)(a3 + 16), v23, v27);
        *(_WORD *)(v27 + *(_QWORD *)(a3 + 16)) = 0;
      }
      v34 = 1;
      goto LABEL_42;
    }
  }
  FusionpTraceCOMFailure(IsAssemblyInstalled, byte_18008517D);
  v10 = IsAssemblyInstalled;
LABEL_6:
  CFnTracerWin32::MarkCOMFailure((CFnTracerWin32 *)&v36, v10);
LABEL_42:
  v28 = v34;
  CSmartPtr<CSxsQueryAssemblyInfoLocals,CSmartPtrBaseTypeHelper<CSxsQueryAssemblyInfoLocals>>::~CSmartPtr<CSxsQueryAssemblyInfoLocals,CSmartPtrBaseTypeHelper<CSxsQueryAssemblyInfoLocals>>(&v32);
  CSmartRef<CAssemblyName>::~CSmartRef<CAssemblyName>(&ppAssemblyNameObj);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v36);
  return v28;
}

```

## disassembly

```asm
0x180052c98  mov     [rsp-8+arg_0], rbx
0x180052c9d  mov     [rsp-8+arg_18], rsi
0x180052ca2  push    rbp
0x180052ca3  push    rdi
0x180052ca4  push    r12
0x180052ca6  push    r14
0x180052ca8  push    r15
0x180052caa  lea     rbp, [rsp-37h]
0x180052caf  sub     rsp, 0A0h
0x180052cb6  mov     rax, cs:__security_cookie
0x180052cbd  xor     rax, rsp
0x180052cc0  mov     [rbp+57h+var_30], rax
0x180052cc4  xor     r15d, r15d
0x180052cc7  mov     [rbp+57h+var_48], 20737853h
0x180052ccf  lea     rax, qword_1800722F0
0x180052cd6  mov     [rbp+57h+var_70], r15d
0x180052cda  mov     [rbp+57h+var_50], rax
0x180052cde  mov     ebx, ecx
0x180052ce0  lea     rax, [rbp+57h+var_70]
0x180052ce4  mov     [rbp+57h+var_58], r15
0x180052ce8  lea     r12d, [r15+1]
0x180052cec  mov     [rbp+57h+var_40], 0F13h
0x180052cf3  lea     rcx, [rbp+57h+var_60]; this
0x180052cf7  mov     [rbp+57h+var_60], r12d
0x180052cfb  mov     rsi, r8
0x180052cfe  mov     [rbp+57h+var_38], rax
0x180052d02  mov     r14, rdx
0x180052d05  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180052d0a  mov     [rbp+57h+ppAssemblyNameObj], r15
0x180052d0e  mov     [rbp+57h+var_88], r15d
0x180052d12  mov     [rbp+57h+var_80], r15
0x180052d16  mov     [rbp+57h+var_78], r15b
0x180052d1a  test    ebx, ebx
0x180052d1c  jnz     loc_180053025
0x180052d22  test    r14, r14
0x180052d25  jz      loc_180053025
0x180052d2b  xor     ecx, ecx; dwErrCode
0x180052d2d  call    cs:__imp_SetLastError
0x180052d34  nop     dword ptr [rax+rax+00h]
0x180052d39  mov     rcx, cs:g_hHeap; hHeap
0x180052d40  xor     edx, edx; dwFlags
0x180052d42  mov     r8d, 460h; dwBytes
0x180052d48  call    cs:__imp_HeapAlloc
0x180052d4f  nop     dword ptr [rax+rax+00h]
0x180052d54  mov     rdi, rax
0x180052d57  test    rax, rax
0x180052d5a  jz      loc_180053010
0x180052d60  mov     rcx, rax; void *
0x180052d63  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180052d68  lea     rcx, [rdi+230h]; void *
0x180052d6f  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180052d74  mov     [rbp+57h+var_80], rdi
0x180052d78  mov     [rbp+57h+var_78], r12b
0x180052d7c  xor     ecx, ecx; dwErrCode
0x180052d7e  call    cs:__imp_SetLastError
0x180052d85  nop     dword ptr [rax+rax+00h]
0x180052d8a  xor     r9d, r9d; pvReserved
0x180052d8d  lea     rcx, [rbp+57h+ppAssemblyNameObj]; ppAssemblyNameObj
0x180052d91  mov     r8d, r12d; dwFlags
0x180052d94  mov     rdx, r14; szAssemblyName
0x180052d97  call    CreateAssemblyNameObject
0x180052d9c  mov     ebx, eax
0x180052d9e  test    eax, eax
0x180052da0  jns     short loc_180052DC0
0x180052da2  lea     rdx, byte_18008517D; char *
0x180052da9  mov     ecx, ebx; int
0x180052dab  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x180052db0  mov     edx, ebx; int
0x180052db2  lea     rcx, [rbp+57h+var_60]; this
0x180052db6  call    ?MarkCOMFailure@CFnTracerWin32@@QEAAXJ@Z; CFnTracerWin32::MarkCOMFailure(long)
0x180052dbb  jmp     loc_180053049
0x180052dc0  xor     ecx, ecx; dwErrCode
0x180052dc2  call    cs:__imp_SetLastError
0x180052dc9  nop     dword ptr [rax+rax+00h]
0x180052dce  mov     rcx, [rbp+57h+ppAssemblyNameObj]; this
0x180052dd2  lea     rdx, [rbp+57h+var_88]; int *
0x180052dd6  call    ?IsAssemblyInstalled@CAssemblyName@@QEAAJAEAH@Z; CAssemblyName::IsAssemblyInstalled(int &)
0x180052ddb  mov     ebx, eax
0x180052ddd  test    eax, eax
0x180052ddf  js      short loc_180052DA2
0x180052de1  test    rsi, rsi
0x180052de4  jnz     short loc_180052E2E
0x180052de6  cmp     [rbp+57h+var_88], r15d
0x180052dea  jz      short loc_180052E14
0x180052dec  xor     ecx, ecx; dwErrCode
0x180052dee  call    cs:__imp_SetLastError
0x180052df5  nop     dword ptr [rax+rax+00h]
0x180052dfa  xor     ecx, ecx; dwErrCode
0x180052dfc  call    cs:__imp_SetLastError
0x180052e03  nop     dword ptr [rax+rax+00h]
0x180052e08  mov     rax, [rbp+57h+var_38]
0x180052e0c  mov     [rax], r12d
0x180052e0f  jmp     loc_180053049
0x180052e14  mov     edx, 490h; unsigned int
0x180052e19  lea     rcx, [rbp+57h+var_60]; this
0x180052e1d  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180052e22  lea     rcx, off_180075110; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x180052e29  jmp     loc_18005301E
0x180052e2e  cmp     [rbp+57h+var_88], r15d
0x180052e32  jnz     short loc_180052E4E
0x180052e34  mov     edx, 490h; unsigned int
0x180052e39  lea     rcx, [rbp+57h+var_60]; this
0x180052e3d  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180052e42  lea     rcx, off_1800750F0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x180052e49  jmp     loc_18005301E
0x180052e4e  or      [rsi+4], r12d
0x180052e52  xor     ecx, ecx; dwErrCode
0x180052e54  mov     [rbp+57h+var_88], r15d
0x180052e58  call    cs:__imp_SetLastError
0x180052e5f  nop     dword ptr [rax+rax+00h]
0x180052e64  mov     rcx, [rbp+57h+ppAssemblyNameObj]; this
0x180052e68  lea     rdx, [rbp+57h+var_88]; int *
0x180052e6c  call    ?DetermineAssemblyType@CAssemblyName@@QEAAJAEAH@Z; CAssemblyName::DetermineAssemblyType(int &)
0x180052e71  mov     ebx, eax
0x180052e73  test    eax, eax
0x180052e75  jns     short loc_180052EA0
0x180052e77  lea     rdx, byte_18008517D; char *
0x180052e7e  mov     ecx, eax; int
0x180052e80  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x180052e85  lea     rcx, [rbp+57h+var_88]; int *
0x180052e89  mov     [rbp+57h+var_88], ebx
0x180052e8c  call    ?FusionpConvertCOMFailure@@YAXAEAJ@Z; FusionpConvertCOMFailure(long &)
0x180052e91  mov     ecx, [rbp+57h+var_88]; int
0x180052e94  call    ?FusionpHRESULTToWin32@@YAKJ@Z; FusionpHRESULTToWin32(long)
0x180052e99  mov     ecx, eax
0x180052e9b  jmp     loc_180053036
0x180052ea0  xor     ecx, ecx; dwErrCode
0x180052ea2  lea     rbx, [rdi+230h]
0x180052ea9  call    cs:__imp_SetLastError
0x180052eb0  nop     dword ptr [rax+rax+00h]
0x180052eb5  mov     rcx, [rbp+57h+ppAssemblyNameObj]
0x180052eb9  cmp     [rbp+57h+var_88], r15d
0x180052ebd  jnz     short loc_180052F31
0x180052ebf  mov     r9, rdi
0x180052ec2  mov     r8d, 2
0x180052ec8  call    ?GetInstalledAssemblyName@CAssemblyName@@QEAAJKKAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CAssemblyName::GetInstalledAssemblyName(ulong,ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x180052ecd  mov     r14d, eax
0x180052ed0  test    eax, eax
0x180052ed2  jns     short loc_180052EEA
0x180052ed4  lea     rdx, byte_18008517D; char *
0x180052edb  mov     ecx, eax; int
0x180052edd  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x180052ee2  mov     edx, r14d
0x180052ee5  jmp     loc_180052DB2
0x180052eea  xor     ecx, ecx; dwErrCode
0x180052eec  mov     [rbp+57h+var_90], r15b
0x180052ef0  call    cs:__imp_SetLastError
0x180052ef7  nop     dword ptr [rax+rax+00h]
0x180052efc  mov     rdx, [rdi+10h]; unsigned __int16 *
0x180052f00  lea     r8, [rbp+57h+var_90]; bool *
0x180052f04  call    ?SxspDoesFileExist@@YAHKPEBGAEA_N@Z; SxspDoesFileExist(ulong,ushort const *,bool &)
0x180052f09  test    eax, eax
0x180052f0b  jnz     short loc_180052F19
0x180052f0d  lea     rcx, off_1800750D0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x180052f14  jmp     loc_180053017
0x180052f19  cmp     [rbp+57h+var_90], r15b
0x180052f1d  jnz     short loc_180052F57
0x180052f1f  xor     ecx, ecx; dwErrCode
0x180052f21  call    cs:__imp_SetLastError
0x180052f28  nop     dword ptr [rax+rax+00h]
0x180052f2d  mov     rcx, [rbp+57h+ppAssemblyNameObj]
0x180052f31  mov     r9, rbx
0x180052f34  mov     r8d, r12d
0x180052f37  call    ?GetInstalledAssemblyName@CAssemblyName@@QEAAJKKAEAV?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@@Z; CAssemblyName::GetInstalledAssemblyName(ulong,ulong,CGenericBaseStringBuffer<CUnicodeCharTraits> &)
0x180052f3c  mov     edi, eax
0x180052f3e  test    eax, eax
0x180052f40  jns     short loc_180052F6B
0x180052f42  lea     rdx, byte_18008517D; char *
0x180052f49  mov     ecx, eax; int
0x180052f4b  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x180052f50  mov     edx, edi
0x180052f52  jmp     loc_180052DB2
0x180052f57  mov     rdx, [rdi+10h]
0x180052f5b  mov     eax, 0FFFFFFFFh
0x180052f60  cmp     [rdi+20h], rax
0x180052f64  ja      short loc_180052F7D
0x180052f66  mov     eax, [rdi+20h]
0x180052f69  jmp     short loc_180052F7D
0x180052f6b  mov     rdx, [rbx+10h]; Src
0x180052f6f  mov     eax, 0FFFFFFFFh
0x180052f74  cmp     [rbx+20h], rax
0x180052f78  ja      short loc_180052F7D
0x180052f7a  mov     eax, [rbx+20h]
0x180052f7d  lea     ebx, [rax+1]
0x180052f80  cmp     ebx, eax
0x180052f82  jnb     short loc_180052FA3
0x180052f84  mov     edx, 216h; unsigned int
0x180052f89  lea     rcx, [rbp+57h+var_60]; this
0x180052f8d  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180052f92  lea     rcx, off_180072370; struct _CALL_SITE_INFO *
0x180052f99  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x180052f9e  jmp     loc_180053049
0x180052fa3  mov     r9d, [rsi+18h]
0x180052fa7  cmp     r9d, ebx
0x180052faa  jb      short loc_180052FC9
0x180052fac  mov     rcx, [rsi+10h]; void *
0x180052fb0  mov     eax, eax
0x180052fb2  lea     rbx, [rax+rax]
0x180052fb6  mov     r8, rbx; Size
0x180052fb9  call    memcpy_0
0x180052fbe  mov     rcx, [rsi+10h]
0x180052fc2  mov     [rbx+rcx], r15w
0x180052fc7  jmp     short loc_180052FD4
0x180052fc9  test    r9d, r9d
0x180052fcc  jnz     short loc_180052FDA
0x180052fce  cmp     [rsi+10h], r15
0x180052fd2  jnz     short loc_180052FDA
0x180052fd4  mov     [rbp+57h+var_70], r12d
0x180052fd8  jmp     short loc_180053049
0x180052fda  lea     r8, aSxsqueryassemb; "SxsQueryAssemblyInfo"
0x180052fe1  mov     [rsp+0C0h+var_A0], ebx
0x180052fe5  lea     rdx, aSxsSInsufficie; "SXS: %s - insufficient buffer passed in"...
0x180052fec  mov     ecx, 80000002h; unsigned int
0x180052ff1  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180052ff6  mov     edx, 7Ah ; 'z'; unsigned int
0x180052ffb  mov     [rsi+18h], ebx
0x180052ffe  lea     rcx, [rbp+57h+var_60]; this
0x180053002  call    ?MarkWin32Failure@CFnTracerWin32@@QEAAXK@Z; CFnTracerWin32::MarkWin32Failure(ulong)
0x180053007  lea     rcx, off_1800750B0; "clientcore\\base\\win32\\fusion\\sxs\\u"...
0x18005300e  jmp     short loc_18005301E
0x180053010  lea     rcx, off_180072330; struct _CALL_SITE_INFO *
0x180053017  mov     rax, [rbp+57h+var_38]
0x18005301b  mov     [rax], r15d
0x18005301e  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180053023  jmp     short loc_180053049
0x180053025  mov     [rbp+57h+var_40], 0F19h
0x18005302c  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180053031  mov     ecx, 57h ; 'W'; dwErrCode
0x180053036  call    cs:__imp_SetLastError
0x18005303d  nop     dword ptr [rax+rax+00h]
0x180053042  mov     rax, [rbp+57h+var_38]
0x180053046  mov     [rax], r15d
0x180053049  mov     ebx, [rbp+57h+var_70]
0x18005304c  lea     rcx, [rbp+57h+var_80]
0x180053050  call    ??1?$CSmartPtr@VCSxsQueryAssemblyInfoLocals@@V?$CSmartPtrBaseTypeHelper@VCSxsQueryAssemblyInfoLocals@@@@@@QEAA@XZ; CSmartPtr<CSxsQueryAssemblyInfoLocals,CSmartPtrBaseTypeHelper<CSxsQueryAssemblyInfoLocals>>::~CSmartPtr<CSxsQueryAssemblyInfoLocals,CSmartPtrBaseTypeHelper<CSxsQueryAssemblyInfoLocals>>(void)
0x180053055  lea     rcx, [rbp+57h+ppAssemblyNameObj]
0x180053059  call    ??1?$CSmartRef@VCAssemblyName@@@@QEAA@XZ; CSmartRef<CAssemblyName>::~CSmartRef<CAssemblyName>(void)
0x18005305e  lea     rcx, [rbp+57h+var_60]; this
0x180053062  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180053067  mov     eax, ebx
0x180053069  mov     rcx, [rbp+57h+var_30]
0x18005306d  xor     rcx, rsp; StackCookie
0x180053070  call    __security_check_cookie
0x180053075  lea     r11, [rsp+0C0h+var_20]
0x18005307d  mov     rbx, [r11+30h]
0x180053081  mov     rsi, [r11+48h]
0x180053085  mov     rsp, r11
0x180053088  pop     r15
0x18005308a  pop     r14
0x18005308c  pop     r12
0x18005308e  pop     rdi
0x18005308f  pop     rbp
0x180053090  retn
```
