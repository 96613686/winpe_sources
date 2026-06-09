# CAssemblyCacheItem::CreateStream(ulong,ushort const *,ulong,ulong,IStream * *,_ULARGE_INTEGER *)

- ea: `0x180063d20`
- end: `0x18006422b`
- name: `?CreateStream@CAssemblyCacheItem@@UEAAJKPEBGKKPEAPEAUIStream@@PEAT_ULARGE_INTEGER@@@Z`
- size: `1291`
- prototype: `int(CAssemblyCacheItem *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, struct IStream **, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x180013af0`
- `0x180014260`
- `0x18001d6f0`
- `0x180029380`
- `0x18002e98c`
- `0x18002ff90`
- `0x180032350`
- `0x180033b50`
- `0x18005bf78`
- `0x18005cc58`
- `0x18005d2b0`
- `0x18005f8cc`
- `0x1800638dc`
- `0x180063900`
- `0x180063d20`
- `0x18006438c`
- `0x180064848`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `ntdll!wcsstr` at `0x180063f7c`
- `ntdll!wcsstr` at `0x180063f7c`
- `ntdll!wcscspn` at `0x180063fb0`
- `ntdll!wcscspn` at `0x180063fb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063ec1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063efe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063f2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063fd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006401f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006404d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064088`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800640d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064117`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064152`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063ec1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063efe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063f2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180063fd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006401f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006404d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064088`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800640d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064117`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064152`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800640a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800640a1`

## string_xrefs

- `0x180063dda`: `CAssemblyCacheItem::CreateStream`

## pseudocode

```c
__int64 __fastcall CAssemblyCacheItem::CreateStream(
        CAssemblyCacheItem *this,
        int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        struct IStream **a6,
        union _ULARGE_INTEGER *a7)
{
  const char *v11; // rcx
  char **v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // r8
  __int64 v15; // r15
  char **v16; // rcx
  CAssemblyCacheItemStream *v17; // rax
  int v18; // eax
  int v19; // ebx
  unsigned int v20; // ebx
  CFileStreamBase *v22; // [rsp+50h] [rbp-B0h] BYREF
  char v23; // [rsp+58h] [rbp-A8h]
  unsigned int v24; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h]
  __int64 *v27; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  int v29; // [rsp+88h] [rbp-78h]
  unsigned int *v30; // [rsp+90h] [rbp-70h]
  _BYTE v31[16]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v32; // [rsp+B0h] [rbp-50h]
  _BYTE v33[16]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 *v34; // [rsp+2E0h] [rbp+1E0h]
  _BYTE v35[560]; // [rsp+500h] [rbp+400h] BYREF

  v27 = &qword_180077420;
  v25 = 1;
  v30 = &v24;
  v24 = 0;
  v26 = 0;
  v28 = 544438355;
  v29 = 86;
  CFrame::BaseEnter((CFrame *)&v25);
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v33);
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v35);
  v22 = 0;
  v23 = 0;
  if ( a6 )
    *a6 = 0;
  FusionpDbgPrintEx(
    0x80400000,
    "SXS: %s called with:\n"
    "   dwFlags = 0x%08lx\n"
    "   pszName = \"%ls\"\n"
    "   dwFormat = %lu\n"
    "   dwFormatFlags = %lu\n"
    "   ppStream = %p\n"
    "   puliMaxSize = %p\n",
    "CAssemblyCacheItem::CreateStream",
    a2,
    a3,
    a4,
    a5,
    a6,
    a7);
  if ( a2 )
  {
    v29 = 116;
LABEL_61:
    FusionpTraceParameterCheck(v11);
    *v30 = -2147024809;
    goto LABEL_62;
  }
  if ( !a3 )
  {
    v29 = 117;
    goto LABEL_61;
  }
  if ( !a6 )
  {
    v29 = 118;
    goto LABEL_61;
  }
  if ( a4 == 3 || a4 >= 5 )
  {
    v29 = 125;
    goto LABEL_61;
  }
  if ( a5 )
  {
    v29 = 127;
    goto LABEL_61;
  }
  if ( *((_DWORD *)this + 4) && (a4 == 1 || a4 == 4) )
  {
    v29 = 130;
    goto LABEL_61;
  }
  *a6 = 0;
  if ( a4 == 1 || a4 == 4 )
  {
    if ( *((_DWORD *)this + 4) )
    {
      v29 = 137;
      goto LABEL_61;
    }
    *((_DWORD *)this + 4) = 1;
  }
  if ( !**((_WORD **)this + 6) )
  {
    *v30 = -2147023537;
    goto LABEL_62;
  }
  SetLastError(0);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v33, (char *)this + 32) )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v25);
    v12 = off_180077400;
LABEL_26:
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v12);
    goto LABEL_62;
  }
  SetLastError(0);
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(v33) )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v25);
    v12 = off_1800773E0;
    goto LABEL_26;
  }
  SetLastError(0);
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( a3[v14] );
  if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(v33, a3, v14) )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v25);
    v12 = off_1800773C0;
    goto LABEL_26;
  }
  if ( wcsstr(a3, L"..") )
  {
    v29 = 152;
    goto LABEL_61;
  }
  v15 = -1;
  do
    ++v15;
  while ( a3[v15] );
  if ( wcscspn(a3, L"\\/") != v15 )
  {
    CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v31);
    SetLastError(0);
    do
      ++v13;
    while ( a3[v13] );
    if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(v31, a3, v13) )
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v25);
      v16 = off_1800773A0;
LABEL_42:
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)v16);
      CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v31);
      goto LABEL_62;
    }
    SetLastError(0);
    if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveLastPathElement(v31) )
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v25);
      v16 = off_180077380;
      goto LABEL_42;
    }
    SetLastError(0);
    if ( !(unsigned int)SxspCreateMultiLevelDirectory(*((const unsigned __int16 **)this + 6), v32) )
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v25);
      v16 = off_180077360;
      goto LABEL_42;
    }
    CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v31);
  }
  SetLastError(0);
  v17 = (CAssemblyCacheItemStream *)HeapAlloc(g_hHeap, 0, 0x20u);
  if ( !v17 || (v22 = CAssemblyCacheItemStream::CAssemblyCacheItemStream(v17)) == 0 )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v25);
    v12 = off_180077340;
    goto LABEL_26;
  }
  v23 = 1;
  SetLastError(0);
  if ( !(unsigned int)CFileStreamBase::OpenForWrite(v22, v34) )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v25);
    v12 = off_180077320;
    goto LABEL_26;
  }
  if ( a4 == 1 || a4 == 4 )
  {
    SetLastError(0);
    if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign((char *)this + 760, v33) )
    {
      CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v25);
      v12 = off_180077300;
      goto LABEL_26;
    }
  }
  SetLastError(0);
  v18 = (**(__int64 (__fastcall ***)(CFileStreamBase *, GUID *, struct IStream **))v22)(v22, &IID_IStream, a6);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v22 = 0;
    v23 = 0;
    v24 = 0;
  }
  else
  {
    FusionpTraceCOMFailure(v18, byte_18008517D);
    CFnTracerHR::MarkCOMFailure((CFnTracerHR *)&v25, v19);
  }
LABEL_62:
  v20 = v24;
  CSmartPtr<CAssemblyCacheItemStream,CSmartPtrBaseTypeHelper<CAssemblyCacheItemStream>>::~CSmartPtr<CAssemblyCacheItemStream,CSmartPtrBaseTypeHelper<CAssemblyCacheItemStream>>(&v22);
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v35);
  CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(v33);
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v25);
  return v20;
}

```

## disassembly

```asm
0x180063d20  push    rbp
0x180063d22  push    rbx
0x180063d23  push    rsi
0x180063d24  push    rdi
0x180063d25  push    r12
0x180063d27  push    r13
0x180063d29  push    r14
0x180063d2b  push    r15
0x180063d2d  lea     rbp, [rsp-648h]
0x180063d35  sub     rsp, 748h
0x180063d3c  mov     rax, cs:__security_cookie
0x180063d43  xor     rax, rsp
0x180063d46  mov     [rbp+680h+var_50], rax
0x180063d4d  mov     r12, [rbp+680h+arg_28]
0x180063d54  lea     rax, qword_180077420
0x180063d5b  mov     rsi, [rbp+680h+arg_30]
0x180063d62  mov     r14, rcx
0x180063d65  mov     [rsp+780h+var_708], rax
0x180063d6a  lea     rcx, [rsp+780h+var_718]; this
0x180063d6f  lea     rax, [rsp+780h+var_720]
0x180063d74  mov     [rsp+780h+var_718], 1
0x180063d7c  xor     r13d, r13d
0x180063d7f  mov     [rbp+680h+var_6F0], rax
0x180063d83  mov     ebx, r9d
0x180063d86  mov     [rsp+780h+var_720], r13d
0x180063d8b  mov     rdi, r8
0x180063d8e  mov     [rsp+780h+var_710], r13
0x180063d93  mov     r15d, edx
0x180063d96  mov     [rbp+680h+var_700], 20737853h
0x180063d9e  mov     [rbp+680h+var_6F8], 56h ; 'V'
0x180063da5  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180063daa  lea     rcx, [rbp+680h+var_4B0]; void *
0x180063db1  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180063db6  lea     rcx, [rbp+680h+var_280]; void *
0x180063dbd  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180063dc2  mov     [rsp+780h+var_730], r13
0x180063dc7  mov     [rsp+780h+var_728], r13b
0x180063dcc  test    r12, r12
0x180063dcf  jz      short loc_180063DD5
0x180063dd1  mov     [r12], r13
0x180063dd5  mov     [rsp+780h+var_740], rsi
0x180063dda  lea     r8, aCassemblycache_6; "CAssemblyCacheItem::CreateStream"
0x180063de1  mov     esi, [rbp+680h+arg_20]
0x180063de7  lea     rdx, aSxsSCalledWith; "SXS: %s called with:\n   dwFlags = 0x%0"...
0x180063dee  mov     [rsp+780h+var_748], r12
0x180063df3  mov     r9d, r15d
0x180063df6  mov     [rsp+780h+var_750], esi
0x180063dfa  mov     ecx, 80400000h; unsigned int
0x180063dff  mov     [rsp+780h+var_758], ebx
0x180063e03  mov     qword ptr [rsp+780h+var_760], rdi; unsigned int
0x180063e08  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180063e0d  test    r15d, r15d
0x180063e10  jz      short loc_180063E1E
0x180063e12  mov     [rbp+680h+var_6F8], 74h ; 't'
0x180063e19  jmp     loc_1800641C6
0x180063e1e  test    rdi, rdi
0x180063e21  jnz     short loc_180063E2F
0x180063e23  mov     [rbp+680h+var_6F8], 75h ; 'u'
0x180063e2a  jmp     loc_1800641C6
0x180063e2f  test    r12, r12
0x180063e32  jnz     short loc_180063E40
0x180063e34  mov     [rbp+680h+var_6F8], 76h ; 'v'
0x180063e3b  jmp     loc_1800641C6
0x180063e40  cmp     ebx, 3
0x180063e43  jz      loc_1800641BF
0x180063e49  cmp     ebx, 5
0x180063e4c  jnb     loc_1800641BF
0x180063e52  test    esi, esi
0x180063e54  jz      short loc_180063E62
0x180063e56  mov     [rbp+680h+var_6F8], 7Fh
0x180063e5d  jmp     loc_1800641C6
0x180063e62  cmp     [r14+10h], r13d
0x180063e66  jz      short loc_180063E7E
0x180063e68  cmp     ebx, 1
0x180063e6b  jz      short loc_180063E72
0x180063e6d  cmp     ebx, 4
0x180063e70  jnz     short loc_180063E7E
0x180063e72  mov     [rbp+680h+var_6F8], 82h
0x180063e79  jmp     loc_1800641C6
0x180063e7e  mov     [r12], r13
0x180063e82  cmp     ebx, 1
0x180063e85  jz      short loc_180063E8C
0x180063e87  cmp     ebx, 4
0x180063e8a  jnz     short loc_180063EA6
0x180063e8c  cmp     [r14+10h], r13d
0x180063e90  jz      short loc_180063E9E
0x180063e92  mov     [rbp+680h+var_6F8], 89h
0x180063e99  jmp     loc_1800641C6
0x180063e9e  mov     dword ptr [r14+10h], 1
0x180063ea6  mov     rax, [r14+30h]
0x180063eaa  cmp     [rax], r13w
0x180063eae  jnz     short loc_180063EBF
0x180063eb0  mov     rax, [rbp+680h+var_6F0]
0x180063eb4  mov     dword ptr [rax], 8007054Fh
0x180063eba  jmp     loc_1800641D5
0x180063ebf  xor     ecx, ecx; dwErrCode
0x180063ec1  call    cs:__imp_SetLastError
0x180063ec8  nop     dword ptr [rax+rax+00h]
0x180063ecd  lea     rdx, [r14+20h]
0x180063ed1  lea     rcx, [rbp+680h+var_4B0]
0x180063ed8  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEBV1@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x180063edd  test    eax, eax
0x180063edf  jnz     short loc_180063EFC
0x180063ee1  lea     rcx, [rsp+780h+var_718]; this
0x180063ee6  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180063eeb  lea     rcx, off_180077400; struct _CALL_SITE_INFO *
0x180063ef2  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x180063ef7  jmp     loc_1800641D5
0x180063efc  xor     ecx, ecx; dwErrCode
0x180063efe  call    cs:__imp_SetLastError
0x180063f05  nop     dword ptr [rax+rax+00h]
0x180063f0a  lea     rcx, [rbp+680h+var_4B0]
0x180063f11  call    ?Win32EnsureTrailingPathSeparator@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32EnsureTrailingPathSeparator(void)
0x180063f16  test    eax, eax
0x180063f18  jnz     short loc_180063F2D
0x180063f1a  lea     rcx, [rsp+780h+var_718]; this
0x180063f1f  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180063f24  lea     rcx, off_1800773E0; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x180063f2b  jmp     short loc_180063EF2
0x180063f2d  xor     ecx, ecx; dwErrCode
0x180063f2f  call    cs:__imp_SetLastError
0x180063f36  nop     dword ptr [rax+rax+00h]
0x180063f3b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180063f3f  mov     r8, rsi
0x180063f42  inc     r8
0x180063f45  cmp     [rdi+r8*2], r13w
0x180063f4a  jnz     short loc_180063F42
0x180063f4c  mov     rdx, rdi
0x180063f4f  lea     rcx, [rbp+680h+var_4B0]
0x180063f56  call    ?Win32Append@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(ushort const *,unsigned __int64)
0x180063f5b  test    eax, eax
0x180063f5d  jnz     short loc_180063F72
0x180063f5f  lea     rcx, [rsp+780h+var_718]; this
0x180063f64  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180063f69  lea     rcx, off_1800773C0; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x180063f70  jmp     short loc_180063EF2
0x180063f72  lea     rdx, SubStr; ".."
0x180063f79  mov     rcx, rdi; Str
0x180063f7c  call    cs:__imp_wcsstr
0x180063f83  nop     dword ptr [rax+rax+00h]
0x180063f88  test    rax, rax
0x180063f8b  jz      short loc_180063F99
0x180063f8d  mov     [rbp+680h+var_6F8], 98h
0x180063f94  jmp     loc_1800641C6
0x180063f99  mov     r15, rsi
0x180063f9c  inc     r15
0x180063f9f  cmp     [rdi+r15*2], r13w
0x180063fa4  jnz     short loc_180063F9C
0x180063fa6  lea     rdx, ?Result@?1??PathSeparators@?$CCharTraitsBase@GD@@SAPEBGXZ@4QBGB; "\\/"
0x180063fad  mov     rcx, rdi; String
0x180063fb0  call    cs:__imp_wcscspn
0x180063fb7  nop     dword ptr [rax+rax+00h]
0x180063fbc  cmp     rax, r15
0x180063fbf  jz      loc_180064086
0x180063fc5  lea     rcx, [rbp+680h+var_6E0]; void *
0x180063fc9  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180063fce  xor     ecx, ecx; dwErrCode
0x180063fd0  call    cs:__imp_SetLastError
0x180063fd7  nop     dword ptr [rax+rax+00h]
0x180063fdc  inc     rsi
0x180063fdf  cmp     [rdi+rsi*2], r13w
0x180063fe4  jnz     short loc_180063FDC
0x180063fe6  mov     r8, rsi
0x180063fe9  lea     rcx, [rbp+680h+var_6E0]
0x180063fed  mov     rdx, rdi
0x180063ff0  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(ushort const *,unsigned __int64)
0x180063ff5  test    eax, eax
0x180063ff7  jnz     short loc_18006401D
0x180063ff9  lea     rcx, [rsp+780h+var_718]; this
0x180063ffe  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180064003  lea     rcx, off_1800773A0; struct _CALL_SITE_INFO *
0x18006400a  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18006400f  lea     rcx, [rbp+680h+var_6E0]; void *
0x180064013  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180064018  jmp     loc_1800641D5
0x18006401d  xor     ecx, ecx; dwErrCode
0x18006401f  call    cs:__imp_SetLastError
0x180064026  nop     dword ptr [rax+rax+00h]
0x18006402b  lea     rcx, [rbp+680h+var_6E0]
0x18006402f  call    ?Win32RemoveLastPathElement@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHXZ; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32RemoveLastPathElement(void)
0x180064034  test    eax, eax
0x180064036  jnz     short loc_18006404B
0x180064038  lea     rcx, [rsp+780h+var_718]; this
0x18006403d  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180064042  lea     rcx, off_180077380; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x180064049  jmp     short loc_18006400A
0x18006404b  xor     ecx, ecx; dwErrCode
0x18006404d  call    cs:__imp_SetLastError
0x180064054  nop     dword ptr [rax+rax+00h]
0x180064059  mov     rdx, [rbp+680h+var_6D0]; unsigned __int16 *
0x18006405d  mov     rcx, [r14+30h]; unsigned __int16 *
0x180064061  call    ?SxspCreateMultiLevelDirectory@@YAHPEBG0@Z; SxspCreateMultiLevelDirectory(ushort const *,ushort const *)
0x180064066  test    eax, eax
0x180064068  jnz     short loc_18006407D
0x18006406a  lea     rcx, [rsp+780h+var_718]; this
0x18006406f  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180064074  lea     rcx, off_180077360; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18006407b  jmp     short loc_18006400A
0x18006407d  lea     rcx, [rbp+680h+var_6E0]; void *
0x180064081  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180064086  xor     ecx, ecx; dwErrCode
0x180064088  call    cs:__imp_SetLastError
0x18006408f  nop     dword ptr [rax+rax+00h]
0x180064094  mov     rcx, cs:g_hHeap; hHeap
0x18006409b  xor     edx, edx; dwFlags
0x18006409d  lea     r8d, [rdx+20h]; dwBytes
0x1800640a1  call    cs:__imp_HeapAlloc
0x1800640a8  nop     dword ptr [rax+rax+00h]
0x1800640ad  test    rax, rax
0x1800640b0  jz      loc_1800641A9
0x1800640b6  mov     rcx, rax; this
0x1800640b9  call    ??0CAssemblyCacheItemStream@@QEAA@XZ; CAssemblyCacheItemStream::CAssemblyCacheItemStream(void)
0x1800640be  mov     [rsp+780h+var_730], rax
0x1800640c3  mov     rdi, rax
0x1800640c6  test    rax, rax
0x1800640c9  jz      loc_1800641A9
0x1800640cf  mov     [rsp+780h+var_728], 1
0x1800640d4  xor     ecx, ecx; dwErrCode
0x1800640d6  call    cs:__imp_SetLastError
0x1800640dd  nop     dword ptr [rax+rax+00h]
0x1800640e2  mov     rdx, [rbp+680h+var_4A0]; unsigned __int16 *
0x1800640e9  mov     rcx, rdi; this
0x1800640ec  call    ?OpenForWrite@CFileStreamBase@@QEAAHPEBGKKK@Z; CFileStreamBase::OpenForWrite(ushort const *,ulong,ulong,ulong)
0x1800640f1  test    eax, eax
0x1800640f3  jnz     short loc_18006410B
0x1800640f5  lea     rcx, [rsp+780h+var_718]; this
0x1800640fa  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x1800640ff  lea     rcx, off_180077320; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x180064106  jmp     loc_180063EF2
0x18006410b  cmp     ebx, 1
0x18006410e  jz      short loc_180064115
0x180064110  cmp     ebx, 4
0x180064113  jnz     short loc_180064150
0x180064115  xor     ecx, ecx; dwErrCode
0x180064117  call    cs:__imp_SetLastError
0x18006411e  nop     dword ptr [rax+rax+00h]
0x180064123  lea     rcx, [r14+2F8h]
0x18006412a  lea     rdx, [rbp+680h+var_4B0]
0x180064131  call    ?Win32Assign@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHAEBV1@@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Assign(CGenericBaseStringBuffer<CUnicodeCharTraits> const &)
0x180064136  test    eax, eax
0x180064138  jnz     short loc_180064150
0x18006413a  lea     rcx, [rsp+780h+var_718]; this
0x18006413f  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x180064144  lea     rcx, off_180077300; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x18006414b  jmp     loc_180063EF2
0x180064150  xor     ecx, ecx; dwErrCode
0x180064152  call    cs:__imp_SetLastError
0x180064159  nop     dword ptr [rax+rax+00h]
0x18006415e  mov     rax, [rdi]
0x180064161  lea     rdx, IID_IStream
0x180064168  mov     r8, r12
0x18006416b  mov     rcx, rdi
0x18006416e  mov     rax, [rax]
0x180064171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064176  mov     ebx, eax
0x180064178  test    eax, eax
0x18006417a  jns     short loc_180064198
0x18006417c  lea     rdx, byte_18008517D; char *
0x180064183  mov     ecx, eax; int
0x180064185  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18006418a  mov     edx, ebx; int
0x18006418c  lea     rcx, [rsp+780h+var_718]; this
0x180064191  call    ?MarkCOMFailure@CFnTracerHR@@QEAAXJ@Z; CFnTracerHR::MarkCOMFailure(long)
0x180064196  jmp     short loc_1800641D5
0x180064198  mov     [rsp+780h+var_730], r13
0x18006419d  mov     [rsp+780h+var_728], r13b
0x1800641a2  mov     [rsp+780h+var_720], r13d
0x1800641a7  jmp     short loc_1800641D5
0x1800641a9  lea     rcx, [rsp+780h+var_718]; this
0x1800641ae  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x1800641b3  lea     rcx, off_180077340; "clientcore\\base\\win32\\fusion\\sxs\\s"...
0x1800641ba  jmp     loc_180063EF2
0x1800641bf  mov     [rbp+680h+var_6F8], 7Dh ; '}'
0x1800641c6  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800641cb  mov     rax, [rbp+680h+var_6F0]
0x1800641cf  mov     dword ptr [rax], 80070057h
0x1800641d5  mov     ebx, [rsp+780h+var_720]
0x1800641d9  lea     rcx, [rsp+780h+var_730]
0x1800641de  call    ??1?$CSmartPtr@VCAssemblyCacheItemStream@@V?$CSmartPtrBaseTypeHelper@VCAssemblyCacheItemStream@@@@@@QEAA@XZ; CSmartPtr<CAssemblyCacheItemStream,CSmartPtrBaseTypeHelper<CAssemblyCacheItemStream>>::~CSmartPtr<CAssemblyCacheItemStream,CSmartPtrBaseTypeHelper<CAssemblyCacheItemStream>>(void)
0x1800641e3  lea     rcx, [rbp+680h+var_280]; void *
0x1800641ea  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x1800641ef  lea     rcx, [rbp+680h+var_4B0]; void *
0x1800641f6  call    ??1?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::~CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x1800641fb  lea     rcx, [rsp+780h+var_718]; this
0x180064200  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x180064205  mov     eax, ebx
0x180064207  mov     rcx, [rbp+680h+var_50]
0x18006420e  xor     rcx, rsp; StackCookie
0x180064211  call    __security_check_cookie
0x180064216  add     rsp, 748h
0x18006421d  pop     r15
0x18006421f  pop     r14
0x180064221  pop     r13
0x180064223  pop     r12
0x180064225  pop     rdi
0x180064226  pop     rsi
0x180064227  pop     rbx
0x180064228  pop     rbp
0x180064229  retn
```
