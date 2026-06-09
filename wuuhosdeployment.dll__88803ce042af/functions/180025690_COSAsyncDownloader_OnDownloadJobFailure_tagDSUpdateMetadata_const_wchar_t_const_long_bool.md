# COSAsyncDownloader::OnDownloadJobFailure(tagDSUpdateMetadata const *,wchar_t const *,long,bool *)

- ea: `0x180025690`
- end: `0x180025849`
- name: `?OnDownloadJobFailure@COSAsyncDownloader@@UEAAJPEBUtagDSUpdateMetadata@@PEB_WJPEA_N@Z`
- size: `441`
- prototype: `int(COSAsyncDownloader *__hidden this, const struct tagDSUpdateMetadata *, const wchar_t *, int, bool *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000a4f4`
- `0x18001fb58`
- `0x180025690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800257c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800257c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002570f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002570f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025768`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025768`

## string_xrefs

- `0x1800257f0`: `OnDownloadJobFailure - Cancelling download request for update %ws`
- `0x1800256dc`: `OnDownloadJobFailure - UUP update %ws in the sandbox %ws failed with 0x%08x.`
- `0x180025793`: `OnDownloadJobFailure - UUP update %ws found %lu downloaders.`

## pseudocode

```c
__int64 __fastcall COSAsyncDownloader::OnDownloadJobFailure(
        COSAsyncDownloader *this,
        const struct tagDSUpdateMetadata *a2,
        const wchar_t *a3,
        __int64 a4,
        bool *a5)
{
  const struct tagDSGlobalUpdateId *v5; // r12
  unsigned int v8; // ebp
  __int64 v9; // rdi
  COSDownloader *v10; // r15
  const wchar_t *v11; // rax
  unsigned int v12; // edi
  int lpString2; // [rsp+20h] [rbp-D8h]
  _BYTE v15[168]; // [rsp+50h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v5 = (const struct tagDSUpdateMetadata *)((char *)a2 + 4);
  Trace::UpdateIdToString::UpdateIdToString(
    (Trace::UpdateIdToString *)v15,
    (const struct tagDSUpdateMetadata *)((char *)a2 + 4));
  lpString2 = 0;
  WUTrace(0, 0, 4096, 4);
  if ( a5 )
    *a5 = 0;
  if ( this != (COSAsyncDownloader *)-16LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v8 = *((_DWORD *)this + 21);
  v9 = 0;
  if ( v8 )
  {
    while ( (unsigned int)v9 < *((_DWORD *)this + 21) )
    {
      v10 = *(COSDownloader **)(*((_QWORD *)this + 9) + 40 * v9);
      v11 = (const wchar_t *)*((_QWORD *)v10 + 35);
      if ( a3 == v11 || a3 && v11 && CompareStringW(0x7Fu, 1u, a3, -1, v11, -1) == 2 )
      {
        Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v15, v5);
        WUTrace(0, 0, 4096, 4);
        COSDownloader::CancelDownloadRequest(v10);
        goto LABEL_12;
      }
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= v8 )
        goto LABEL_12;
    }
    v12 = -2145124345;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x224,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSAsyncDownloader.cpp",
      (const char *)0x80240007LL,
      lpString2);
  }
  else
  {
LABEL_12:
    Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v15, v5);
    WUTrace(0, 0, 4096, 4);
    v12 = 0;
  }
  if ( this != (COSAsyncDownloader *)-16LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v12;
}

```

## disassembly

```asm
0x180025690  push    rbx
0x180025692  push    rbp
0x180025693  push    rsi
0x180025694  push    rdi
0x180025695  push    r12
0x180025697  push    r14
0x180025699  push    r15
0x18002569b  sub     rsp, 0C0h
0x1800256a2  mov     rdi, [rsp+0F8h+arg_20]
0x1800256aa  lea     r12, [rdx+4]
0x1800256ae  mov     rsi, rcx
0x1800256b1  mov     rdx, r12; struct tagDSGlobalUpdateId *
0x1800256b4  lea     rcx, [rsp+0F8h+var_A8]; this
0x1800256b9  mov     ebx, r9d
0x1800256bc  mov     r14, r8
0x1800256bf  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800256c4  mov     [rsp+0F8h+var_B8], ebx
0x1800256c8  xor     edx, edx
0x1800256ca  mov     [rsp+0F8h+var_C0], r14
0x1800256cf  xor     ecx, ecx
0x1800256d1  mov     [rsp+0F8h+var_C8], rax
0x1800256d6  mov     r8d, 1000h
0x1800256dc  lea     rax, aOndownloadjobf_0; "OnDownloadJobFailure - UUP update %ws i"...
0x1800256e3  mov     qword ptr [rsp+0F8h+cchCount2], rax
0x1800256e8  lea     r9d, [rdx+4]
0x1800256ec  mov     [rsp+0F8h+lpString2], 0; int
0x1800256f5  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800256fa  test    rdi, rdi
0x1800256fd  jz      short loc_180025702
0x1800256ff  mov     byte ptr [rdi], 0
0x180025702  lea     rbx, [rsi+10h]
0x180025706  test    rbx, rbx
0x180025709  jz      short loc_180025715
0x18002570b  lea     rcx, [rbx+8]; lpCriticalSection
0x18002570f  call    cs:__imp_EnterCriticalSection
0x180025715  mov     ebp, [rsi+54h]
0x180025718  xor     edi, edi
0x18002571a  test    ebp, ebp
0x18002571c  jz      short loc_180025779
0x18002571e  cmp     edi, [rsi+54h]
0x180025721  jnb     loc_180025823
0x180025727  mov     rax, [rsi+48h]
0x18002572b  lea     rcx, [rdi+rdi*4]
0x18002572f  mov     r15, [rax+rcx*8]
0x180025733  mov     rax, [r15+118h]
0x18002573a  cmp     r14, rax
0x18002573d  jz      loc_1800257DC
0x180025743  test    r14, r14
0x180025746  jz      short loc_180025773
0x180025748  test    rax, rax
0x18002574b  jz      short loc_180025773
0x18002574d  or      r9d, 0FFFFFFFFh; cchCount1
0x180025751  mov     [rsp+0F8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180025759  mov     r8, r14; lpString1
0x18002575c  mov     [rsp+0F8h+lpString2], rax; lpString2
0x180025761  lea     edx, [r9+2]; dwCmpFlags
0x180025765  lea     ecx, [rdx+7Eh]; Locale
0x180025768  call    cs:__imp_CompareStringW
0x18002576e  cmp     eax, 2
0x180025771  jz      short loc_1800257DC
0x180025773  inc     edi
0x180025775  cmp     edi, ebp
0x180025777  jb      short loc_18002571E
0x180025779  mov     rdx, r12; struct tagDSGlobalUpdateId *
0x18002577c  lea     rcx, [rsp+0F8h+var_A8]; this
0x180025781  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180025786  mov     dword ptr [rsp+0F8h+var_C0], ebp
0x18002578a  xor     edx, edx
0x18002578c  mov     [rsp+0F8h+var_C8], rax
0x180025791  xor     ecx, ecx
0x180025793  lea     rax, aOndownloadjobf_1; "OnDownloadJobFailure - UUP update %ws f"...
0x18002579a  mov     r8d, 1000h
0x1800257a0  mov     qword ptr [rsp+0F8h+cchCount2], rax
0x1800257a5  lea     r9d, [rdx+4]
0x1800257a9  mov     [rsp+0F8h+lpString2], 0
0x1800257b2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800257b7  xor     edi, edi
0x1800257b9  test    rbx, rbx
0x1800257bc  jz      short loc_1800257C8
0x1800257be  lea     rcx, [rbx+8]; lpCriticalSection
0x1800257c2  call    cs:__imp_LeaveCriticalSection
0x1800257c8  mov     eax, edi
0x1800257ca  add     rsp, 0C0h
0x1800257d1  pop     r15
0x1800257d3  pop     r14
0x1800257d5  pop     r12
0x1800257d7  pop     rdi
0x1800257d8  pop     rsi
0x1800257d9  pop     rbp
0x1800257da  pop     rbx
0x1800257db  retn
0x1800257dc  mov     rdx, r12; struct tagDSGlobalUpdateId *
0x1800257df  lea     rcx, [rsp+0F8h+var_A8]; this
0x1800257e4  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800257e9  mov     [rsp+0F8h+var_C8], rax
0x1800257ee  xor     edx, edx
0x1800257f0  lea     rax, aOndownloadjobf; "OnDownloadJobFailure - Cancelling downl"...
0x1800257f7  xor     ecx, ecx
0x1800257f9  mov     qword ptr [rsp+0F8h+cchCount2], rax
0x1800257fe  mov     r8d, 1000h
0x180025804  mov     [rsp+0F8h+lpString2], 0
0x18002580d  lea     r9d, [rdx+4]
0x180025811  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180025816  mov     rcx, r15; this
0x180025819  call    ?CancelDownloadRequest@COSDownloader@@QEAAXXZ; COSDownloader::CancelDownloadRequest(void)
0x18002581e  jmp     loc_180025779
0x180025823  mov     rcx, [rsp+0F8h]; this
0x18002582b  lea     r8, aCW1SSrcClientE_17; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180025832  mov     edi, 80240007h
0x180025837  mov     edx, 224h; void *
0x18002583c  mov     r9d, edi; char *
0x18002583f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025844  jmp     loc_1800257B9
```
