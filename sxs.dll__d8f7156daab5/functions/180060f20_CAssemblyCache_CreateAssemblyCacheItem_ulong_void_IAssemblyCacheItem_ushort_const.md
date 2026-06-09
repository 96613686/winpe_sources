# CAssemblyCache::CreateAssemblyCacheItem(ulong,void *,IAssemblyCacheItem * *,ushort const *)

- ea: `0x180060f20`
- end: `0x180061106`
- name: `?CreateAssemblyCacheItem@CAssemblyCache@@UEAAJKPEAXPEAPEAUIAssemblyCacheItem@@PEBG@Z`
- size: `486`
- prototype: `__int64 __fastcall(CAssemblyCache *__hidden this, unsigned int, void *, struct IAssemblyCacheItem **, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18000df40`
- `0x18000dffc`
- `0x180020820`
- `0x180029380`
- `0x18002e98c`
- `0x18002ff90`
- `0x18005bf78`
- `0x18005cc58`
- `0x18005d2b0`
- `0x180060e58`
- `0x180060f20`
- `0x18006425c`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060faf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006101f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061056`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060faf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006101f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180061056`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060fca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060fca`

## pseudocode

```c
__int64 __fastcall CAssemblyCache::CreateAssemblyCacheItem(
        CAssemblyCache *this,
        int a2,
        void *a3,
        struct IAssemblyCacheItem **a4)
{
  const char *v7; // rcx
  _QWORD *v8; // rbx
  int v9; // eax
  int v10; // edi
  int v11; // edx
  int v12; // eax
  int v13; // ebx
  unsigned int v14; // ebx
  _QWORD *v16; // [rsp+20h] [rbp-50h] BYREF
  char v17; // [rsp+28h] [rbp-48h]
  unsigned int v18; // [rsp+30h] [rbp-40h] BYREF
  int v19; // [rsp+38h] [rbp-38h] BYREF
  __int64 v20; // [rsp+40h] [rbp-30h]
  __int64 *v21; // [rsp+48h] [rbp-28h]
  __int64 v22; // [rsp+50h] [rbp-20h]
  int v23; // [rsp+58h] [rbp-18h]
  unsigned int *v24; // [rsp+60h] [rbp-10h]

  v19 = 1;
  v21 = &qword_180076300;
  v22 = 544438355;
  v24 = &v18;
  v18 = 0;
  v20 = 0;
  v23 = 206;
  CFrame::BaseEnter((CFrame *)&v19);
  v16 = 0;
  v17 = 0;
  if ( !a4 || (*a4 = 0, a2) || a3 )
  {
    v23 = 212;
    FusionpTraceParameterCheck(v7);
    *v24 = -2147024809;
    goto LABEL_13;
  }
  SetLastError(0);
  v8 = HeapAlloc(g_hHeap, 0, 0x528u);
  if ( !v8 )
  {
    CFnTracerHR::MarkWin32LastErrorFailure((CFnTracerHR *)&v19);
    FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_1800762E0);
    goto LABEL_13;
  }
  v8[1] = 0;
  *v8 = &CAssemblyCacheItem::`vftable';
  v8[2] = 0;
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v8 + 4);
  CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(v8 + 74);
  CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(v8 + 95);
  v16 = v8;
  v17 = 1;
  SetLastError(0);
  v9 = CAssemblyCacheItem::Initialize((CAssemblyCacheItem *)v8);
  v10 = v9;
  if ( v9 >= 0 )
  {
    SetLastError(0);
    v12 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IAssemblyCacheItem **))*v8)(
            v8,
            &IID_IAssemblyCacheItem,
            a4);
    v13 = v12;
    if ( v12 >= 0 )
    {
      v16 = 0;
      v17 = 0;
      v18 = 0;
      goto LABEL_13;
    }
    FusionpTraceCOMFailure(v12, byte_18008517D);
    v11 = v13;
  }
  else
  {
    FusionpTraceCOMFailure(v9, byte_18008517D);
    v11 = v10;
  }
  CFnTracerHR::MarkCOMFailure((CFnTracerHR *)&v19, v11);
LABEL_13:
  v14 = v18;
  CSmartPtr<CAssemblyCacheItem,CSmartPtrBaseTypeHelper<CAssemblyCacheItem>>::~CSmartPtr<CAssemblyCacheItem,CSmartPtrBaseTypeHelper<CAssemblyCacheItem>>(&v16);
  CFnTracerHR::~CFnTracerHR((CFnTracerHR *)&v19);
  return v14;
}

```

## disassembly

```asm
0x180060f20  mov     [rsp-18h+arg_0], rbx
0x180060f25  mov     [rsp-18h+arg_8], rsi
0x180060f2a  push    rbp
0x180060f2b  push    rdi
0x180060f2c  push    r14
0x180060f2e  mov     rbp, rsp
0x180060f31  sub     rsp, 70h
0x180060f35  mov     rax, cs:__security_cookie
0x180060f3c  xor     rax, rsp
0x180060f3f  mov     [rbp+var_8], rax
0x180060f43  lea     rax, qword_180076300
0x180060f4a  mov     [rbp+var_38], 1
0x180060f51  mov     [rbp+var_28], rax
0x180060f55  lea     rcx, [rbp+var_38]; this
0x180060f59  lea     rax, [rbp+var_40]
0x180060f5d  mov     [rbp+var_20], 20737853h
0x180060f65  xor     r14d, r14d
0x180060f68  mov     [rbp+var_10], rax
0x180060f6c  mov     rsi, r9
0x180060f6f  mov     [rbp+var_40], r14d
0x180060f73  mov     rbx, r8
0x180060f76  mov     [rbp+var_30], r14
0x180060f7a  mov     edi, edx
0x180060f7c  mov     [rbp+var_18], 0CEh
0x180060f83  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180060f88  mov     [rbp+var_50], r14
0x180060f8c  mov     [rbp+var_48], r14b
0x180060f90  test    rsi, rsi
0x180060f93  jz      loc_1800610B7
0x180060f99  mov     [rsi], r14
0x180060f9c  test    edi, edi
0x180060f9e  jnz     loc_1800610B7
0x180060fa4  test    rbx, rbx
0x180060fa7  jnz     loc_1800610B7
0x180060fad  xor     ecx, ecx; dwErrCode
0x180060faf  call    cs:__imp_SetLastError
0x180060fb6  nop     dword ptr [rax+rax+00h]
0x180060fbb  mov     rcx, cs:g_hHeap; hHeap
0x180060fc2  xor     edx, edx; dwFlags
0x180060fc4  mov     r8d, 528h; dwBytes
0x180060fca  call    cs:__imp_HeapAlloc
0x180060fd1  nop     dword ptr [rax+rax+00h]
0x180060fd6  mov     rbx, rax
0x180060fd9  test    rax, rax
0x180060fdc  jz      loc_1800610A0
0x180060fe2  lea     rax, ??_7CAssemblyCacheItem@@6B@; const CAssemblyCacheItem::`vftable'
0x180060fe9  mov     [rbx+8], r14
0x180060fed  lea     rcx, [rbx+20h]; void *
0x180060ff1  mov     [rbx], rax
0x180060ff4  mov     [rbx+10h], r14
0x180060ff8  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180060ffd  lea     rcx, [rbx+250h]
0x180061004  call    ??0?$CGenericStringBuffer@$0EA@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<64,CUnicodeCharTraits>::CGenericStringBuffer<64,CUnicodeCharTraits>(void)
0x180061009  lea     rcx, [rbx+2F8h]; void *
0x180061010  call    ??0?$CGenericStringBuffer@$0BAE@VCUnicodeCharTraits@@@@QEAA@XZ; CGenericStringBuffer<260,CUnicodeCharTraits>::CGenericStringBuffer<260,CUnicodeCharTraits>(void)
0x180061015  mov     [rbp+var_50], rbx
0x180061019  mov     [rbp+var_48], 1
0x18006101d  xor     ecx, ecx; dwErrCode
0x18006101f  call    cs:__imp_SetLastError
0x180061026  nop     dword ptr [rax+rax+00h]
0x18006102b  mov     rcx, rbx; this
0x18006102e  call    ?Initialize@CAssemblyCacheItem@@QEAAJXZ; CAssemblyCacheItem::Initialize(void)
0x180061033  mov     edi, eax
0x180061035  test    eax, eax
0x180061037  jns     short loc_180061054
0x180061039  lea     rdx, byte_18008517D; char *
0x180061040  mov     ecx, eax; int
0x180061042  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x180061047  mov     edx, edi; int
0x180061049  lea     rcx, [rbp+var_38]; this
0x18006104d  call    ?MarkCOMFailure@CFnTracerHR@@QEAAXJ@Z; CFnTracerHR::MarkCOMFailure(long)
0x180061052  jmp     short loc_1800610CD
0x180061054  xor     ecx, ecx; dwErrCode
0x180061056  call    cs:__imp_SetLastError
0x18006105d  nop     dword ptr [rax+rax+00h]
0x180061062  mov     rax, [rbx]
0x180061065  lea     rdx, IID_IAssemblyCacheItem
0x18006106c  mov     r8, rsi
0x18006106f  mov     rcx, rbx
0x180061072  mov     rax, [rax]
0x180061075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006107a  mov     ebx, eax
0x18006107c  test    eax, eax
0x18006107e  jns     short loc_180061092
0x180061080  lea     rdx, byte_18008517D; char *
0x180061087  mov     ecx, eax; int
0x180061089  call    ?FusionpTraceCOMFailure@@YAXJPEBDZZ; FusionpTraceCOMFailure(long,char const *,...)
0x18006108e  mov     edx, ebx
0x180061090  jmp     short loc_180061049
0x180061092  mov     [rbp+var_50], r14
0x180061096  mov     [rbp+var_48], r14b
0x18006109a  mov     [rbp+var_40], r14d
0x18006109e  jmp     short loc_1800610CD
0x1800610a0  lea     rcx, [rbp+var_38]; this
0x1800610a4  call    ?MarkWin32LastErrorFailure@CFnTracerHR@@QEAAXXZ; CFnTracerHR::MarkWin32LastErrorFailure(void)
0x1800610a9  lea     rcx, off_1800762E0; struct _CALL_SITE_INFO *
0x1800610b0  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x1800610b5  jmp     short loc_1800610CD
0x1800610b7  mov     [rbp+var_18], 0D4h
0x1800610be  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x1800610c3  mov     rax, [rbp+var_10]
0x1800610c7  mov     dword ptr [rax], 80070057h
0x1800610cd  mov     ebx, [rbp+var_40]
0x1800610d0  lea     rcx, [rbp+var_50]
0x1800610d4  call    ??1?$CSmartPtr@VCAssemblyCacheItem@@V?$CSmartPtrBaseTypeHelper@VCAssemblyCacheItem@@@@@@QEAA@XZ; CSmartPtr<CAssemblyCacheItem,CSmartPtrBaseTypeHelper<CAssemblyCacheItem>>::~CSmartPtr<CAssemblyCacheItem,CSmartPtrBaseTypeHelper<CAssemblyCacheItem>>(void)
0x1800610d9  lea     rcx, [rbp+var_38]; this
0x1800610dd  call    ??1CFnTracerHR@@QEAA@XZ; CFnTracerHR::~CFnTracerHR(void)
0x1800610e2  mov     eax, ebx
0x1800610e4  mov     rcx, [rbp+var_8]
0x1800610e8  xor     rcx, rsp; StackCookie
0x1800610eb  call    __security_check_cookie
0x1800610f0  lea     r11, [rsp+70h+var_s0]
0x1800610f5  mov     rbx, [r11+20h]
0x1800610f9  mov     rsi, [r11+28h]
0x1800610fd  mov     rsp, r11
0x180061100  pop     r14
0x180061102  pop     rdi
0x180061103  pop     rbp
0x180061104  retn
```
