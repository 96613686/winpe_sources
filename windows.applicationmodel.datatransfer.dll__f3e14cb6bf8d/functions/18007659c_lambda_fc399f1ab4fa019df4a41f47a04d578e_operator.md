# _lambda_fc399f1ab4fa019df4a41f47a04d578e_::operator()

- ea: `0x18007659c`
- end: `0x1800768b0`
- name: `_lambda_fc399f1ab4fa019df4a41f47a04d578e_::operator()`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180074820`

## callees

- `0x180008b68`
- `0x180048954`
- `0x18007659c`
- `0x180077fbc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007661b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800766e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007677e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007681e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007687f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007661b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180076657`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800766e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007677e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007681e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007687f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall lambda_fc399f1ab4fa019df4a41f47a04d578e_::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  struct Windows::Storage::Streams::IRandomAccessStreamReference *v7; // rcx
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  struct Windows::Storage::Streams::IRandomAccessStreamReference *v11; // rcx
  DataPackageCloner *v12; // rbx
  void **v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  struct Windows::Storage::Streams::IRandomAccessStreamReference *v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  struct Windows::Storage::Streams::IRandomAccessStreamReference *v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  struct Windows::Storage::Streams::IRandomAccessStreamReference *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  struct Windows::Storage::Streams::IRandomAccessStreamReference *v27; // rcx
  int v28; // [rsp+20h] [rbp-20h]
  __int64 v29; // [rsp+30h] [rbp-10h] BYREF
  __int64 v30; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  struct Windows::Storage::Streams::IRandomAccessStreamReference *v32; // [rsp+78h] [rbp+38h] BYREF
  __int64 v33; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF

  v33 = a3;
  v32 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IRandomAccessStreamReference **))(*(_QWORD *)a2 + 56LL))(
         a2,
         &v32);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v5,
      v28);
    v7 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStreamReference *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v6;
  }
  string = 0;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v10 = v9(a2, &string);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v10,
      v28);
    WindowsDeleteString(string);
    string = 0;
    v11 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStreamReference *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return v6;
  }
  v29 = 0;
  v12 = *(DataPackageCloner **)a1;
  v13 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v29);
  v14 = DataPackageCloner::CloneStreamRef(v12, v32, &GUID_33ee3134_1dd6_4e3a_8067_d1c162e8642b, v13);
  v6 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v14,
      v28);
    v15 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    WindowsDeleteString(string);
    string = 0;
    v16 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStreamReference *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v6;
  }
  v30 = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(***(_QWORD ***)(a1 + 8) + 152LL))(**(_QWORD **)(a1 + 8), &v30);
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v17,
      v28);
    v18 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    WindowsDeleteString(string);
    string = 0;
    v20 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStreamReference *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v6;
  }
  LOBYTE(v33) = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64 *))(*(_QWORD *)v30 + 80LL))(
          v30,
          string,
          v29,
          &v33);
  v6 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackagecloner.cpp",
      (const char *)(unsigned int)v21,
      v28);
    v22 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    WindowsDeleteString(string);
    string = 0;
    v24 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStreamReference *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    return v6;
  }
  v25 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  WindowsDeleteString(string);
  string = 0;
  v27 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(struct Windows::Storage::Streams::IRandomAccessStreamReference *))(*(_QWORD *)v27 + 16LL))(v27);
  }
  return 0;
}

```

## disassembly

```asm
0x18007659c  mov     [rsp-28h+arg_10], r8
0x1800765a1  push    rbp
0x1800765a2  push    rbx
0x1800765a3  push    rsi
0x1800765a4  push    rdi
0x1800765a5  push    r14
0x1800765a7  mov     rbp, rsp
0x1800765aa  sub     rsp, 40h
0x1800765ae  mov     rdi, rdx
0x1800765b1  mov     rsi, rcx
0x1800765b4  xor     r14d, r14d
0x1800765b7  mov     [rbp+arg_8], r14
0x1800765bb  mov     rax, [rdx]
0x1800765be  lea     rdx, [rbp+arg_8]
0x1800765c2  mov     rcx, rdi
0x1800765c5  mov     rax, [rax+38h]
0x1800765c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800765ce  mov     ebx, eax
0x1800765d0  test    eax, eax
0x1800765d2  jns     short loc_18007660E
0x1800765d4  mov     rcx, [rbp+28h]; this
0x1800765d8  mov     r9d, eax; char *
0x1800765db  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800765e2  mov     edx, 9Dh; void *
0x1800765e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800765ec  nop
0x1800765ed  mov     rcx, [rbp+arg_8]
0x1800765f1  test    rcx, rcx
0x1800765f4  jz      short loc_180076607
0x1800765f6  mov     [rbp+arg_8], r14
0x1800765fa  mov     rax, [rcx]
0x1800765fd  mov     rax, [rax+10h]
0x180076601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076606  nop
0x180076607  mov     eax, ebx
0x180076609  jmp     loc_1800768A5
0x18007660e  mov     [rbp+string], r14
0x180076612  mov     rax, [rdi]
0x180076615  mov     rbx, [rax+30h]
0x180076619  xor     ecx, ecx; string
0x18007661b  call    cs:__imp_WindowsDeleteString
0x180076621  mov     [rbp+string], r14
0x180076625  lea     rdx, [rbp+string]
0x180076629  mov     rcx, rdi
0x18007662c  mov     rax, rbx
0x18007662f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076634  mov     ebx, eax
0x180076636  test    eax, eax
0x180076638  jns     short loc_18007667D
0x18007663a  mov     rcx, [rbp+28h]; this
0x18007663e  mov     r9d, eax; char *
0x180076641  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180076648  mov     edx, 0A0h; void *
0x18007664d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076652  nop
0x180076653  mov     rcx, [rbp+string]; string
0x180076657  call    cs:__imp_WindowsDeleteString
0x18007665d  mov     [rbp+string], r14
0x180076661  mov     rcx, [rbp+arg_8]
0x180076665  test    rcx, rcx
0x180076668  jz      short loc_18007667B
0x18007666a  mov     [rbp+arg_8], r14
0x18007666e  mov     rax, [rcx]
0x180076671  mov     rax, [rax+10h]
0x180076675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007667a  nop
0x18007667b  jmp     short loc_180076607
0x18007667d  mov     [rbp+var_10], r14
0x180076681  mov     rbx, [rsi]
0x180076684  lea     rcx, [rbp+var_10]
0x180076688  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18007668d  mov     r9, rax; void **
0x180076690  lea     r8, _GUID_33ee3134_1dd6_4e3a_8067_d1c162e8642b; struct _GUID *
0x180076697  mov     rdx, [rbp+arg_8]; struct Windows::Storage::Streams::IRandomAccessStreamReference *
0x18007669b  mov     rcx, rbx; this
0x18007669e  call    ?CloneStreamRef@DataPackageCloner@@AEAAJPEAUIRandomAccessStreamReference@Streams@Storage@Windows@@AEBU_GUID@@PEAPEAX@Z; DataPackageCloner::CloneStreamRef(Windows::Storage::Streams::IRandomAccessStreamReference *,_GUID const &,void * *)
0x1800766a3  mov     ebx, eax
0x1800766a5  test    eax, eax
0x1800766a7  jns     short loc_180076709
0x1800766a9  mov     rcx, [rbp+28h]; this
0x1800766ad  mov     r9d, eax; char *
0x1800766b0  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800766b7  mov     edx, 0A3h; void *
0x1800766bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800766c1  nop
0x1800766c2  mov     rcx, [rbp+var_10]
0x1800766c6  test    rcx, rcx
0x1800766c9  jz      short loc_1800766DC
0x1800766cb  mov     [rbp+var_10], r14
0x1800766cf  mov     rax, [rcx]
0x1800766d2  mov     rax, [rax+10h]
0x1800766d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800766db  nop
0x1800766dc  mov     rcx, [rbp+string]; string
0x1800766e0  call    cs:__imp_WindowsDeleteString
0x1800766e6  mov     [rbp+string], r14
0x1800766ea  mov     rcx, [rbp+arg_8]
0x1800766ee  test    rcx, rcx
0x1800766f1  jz      short loc_180076704
0x1800766f3  mov     [rbp+arg_8], r14
0x1800766f7  mov     rax, [rcx]
0x1800766fa  mov     rax, [rax+10h]
0x1800766fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076703  nop
0x180076704  jmp     loc_180076607
0x180076709  mov     [rbp+var_8], r14
0x18007670d  mov     rax, [rsi+8]
0x180076711  mov     rcx, [rax]
0x180076714  mov     rax, [rcx]
0x180076717  lea     rdx, [rbp+var_8]
0x18007671b  mov     rax, [rax+98h]
0x180076722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076727  mov     ebx, eax
0x180076729  test    eax, eax
0x18007672b  jns     short loc_1800767A7
0x18007672d  mov     rcx, [rbp+28h]; this
0x180076731  mov     r9d, eax; char *
0x180076734  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x18007673b  mov     edx, 0A6h; void *
0x180076740  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076745  nop
0x180076746  mov     rcx, [rbp+var_8]
0x18007674a  test    rcx, rcx
0x18007674d  jz      short loc_180076760
0x18007674f  mov     [rbp+var_8], r14
0x180076753  mov     rax, [rcx]
0x180076756  mov     rax, [rax+10h]
0x18007675a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007675f  nop
0x180076760  mov     rcx, [rbp+var_10]
0x180076764  test    rcx, rcx
0x180076767  jz      short loc_18007677A
0x180076769  mov     [rbp+var_10], r14
0x18007676d  mov     rax, [rcx]
0x180076770  mov     rax, [rax+10h]
0x180076774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076779  nop
0x18007677a  mov     rcx, [rbp+string]; string
0x18007677e  call    cs:__imp_WindowsDeleteString
0x180076784  mov     [rbp+string], r14
0x180076788  mov     rcx, [rbp+arg_8]
0x18007678c  test    rcx, rcx
0x18007678f  jz      short loc_1800767A2
0x180076791  mov     [rbp+arg_8], r14
0x180076795  mov     rax, [rcx]
0x180076798  mov     rax, [rax+10h]
0x18007679c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800767a1  nop
0x1800767a2  jmp     loc_180076607
0x1800767a7  mov     byte ptr [rbp+arg_10], r14b
0x1800767ab  mov     rcx, [rbp+var_8]
0x1800767af  mov     rax, [rcx]
0x1800767b2  lea     r9, [rbp+arg_10]
0x1800767b6  mov     r8, [rbp+var_10]
0x1800767ba  mov     rdx, [rbp+string]
0x1800767be  mov     rax, [rax+50h]
0x1800767c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800767c7  mov     ebx, eax
0x1800767c9  test    eax, eax
0x1800767cb  jns     short loc_180076847
0x1800767cd  mov     rcx, [rbp+28h]; this
0x1800767d1  mov     r9d, eax; char *
0x1800767d4  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800767db  mov     edx, 0A9h; void *
0x1800767e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800767e5  nop
0x1800767e6  mov     rcx, [rbp+var_8]
0x1800767ea  test    rcx, rcx
0x1800767ed  jz      short loc_180076800
0x1800767ef  mov     [rbp+var_8], r14
0x1800767f3  mov     rax, [rcx]
0x1800767f6  mov     rax, [rax+10h]
0x1800767fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800767ff  nop
0x180076800  mov     rcx, [rbp+var_10]
0x180076804  test    rcx, rcx
0x180076807  jz      short loc_18007681A
0x180076809  mov     [rbp+var_10], r14
0x18007680d  mov     rax, [rcx]
0x180076810  mov     rax, [rax+10h]
0x180076814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076819  nop
0x18007681a  mov     rcx, [rbp+string]; string
0x18007681e  call    cs:__imp_WindowsDeleteString
0x180076824  mov     [rbp+string], r14
0x180076828  mov     rcx, [rbp+arg_8]
0x18007682c  test    rcx, rcx
0x18007682f  jz      short loc_180076842
0x180076831  mov     [rbp+arg_8], r14
0x180076835  mov     rax, [rcx]
0x180076838  mov     rax, [rax+10h]
0x18007683c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076841  nop
0x180076842  jmp     loc_180076607
0x180076847  mov     rcx, [rbp+var_8]
0x18007684b  test    rcx, rcx
0x18007684e  jz      short loc_180076861
0x180076850  mov     [rbp+var_8], r14
0x180076854  mov     rax, [rcx]
0x180076857  mov     rax, [rax+10h]
0x18007685b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076860  nop
0x180076861  mov     rcx, [rbp+var_10]
0x180076865  test    rcx, rcx
0x180076868  jz      short loc_18007687B
0x18007686a  mov     [rbp+var_10], r14
0x18007686e  mov     rax, [rcx]
0x180076871  mov     rax, [rax+10h]
0x180076875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007687a  nop
0x18007687b  mov     rcx, [rbp+string]; string
0x18007687f  call    cs:__imp_WindowsDeleteString
0x180076885  mov     [rbp+string], r14
0x180076889  mov     rcx, [rbp+arg_8]
0x18007688d  test    rcx, rcx
0x180076890  jz      short loc_1800768A3
0x180076892  mov     [rbp+arg_8], r14
0x180076896  mov     rax, [rcx]
0x180076899  mov     rax, [rax+10h]
0x18007689d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800768a2  nop
0x1800768a3  xor     eax, eax
0x1800768a5  add     rsp, 40h
0x1800768a9  pop     r14
0x1800768ab  pop     rdi
0x1800768ac  pop     rsi
0x1800768ad  pop     rbx
0x1800768ae  pop     rbp
0x1800768af  retn
```
