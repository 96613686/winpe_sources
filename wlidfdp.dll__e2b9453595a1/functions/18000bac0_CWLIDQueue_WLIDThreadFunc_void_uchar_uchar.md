# CWLIDQueue::WLIDThreadFunc(void *,uchar,uchar)

- ea: `0x18000bac0`
- end: `0x18000bbf2`
- name: `?WLIDThreadFunc@CWLIDQueue@@SAXPEAXEE@Z`
- size: `306`
- prototype: `void __fastcall(CWLIDItem *this, __int64, char)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180008edc`
- `0x180008f6c`
- `0x18000a3bc`
- `0x18000a3e8`
- `0x18000bac0`
- `0x18000bc8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000baea`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000baea`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bb95`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bbcd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bb95`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bbcd`

## string_xrefs

- `0x18000bb10`: `CWLIDQueue::WLIDThreadFunc`

## pseudocode

```c
void __fastcall CWLIDQueue::WLIDThreadFunc(CWLIDItem *this, __int64 a2, char a3)
{
  HRESULT v5; // edx
  unsigned int v6; // r9d
  int v7; // r8d
  int v8; // r8d
  int v9; // ecx
  int v10; // eax
  int v11; // ecx
  int v12; // ecx
  const unsigned __int16 *v13; // [rsp+20h] [rbp-48h] BYREF
  __int64 v14; // [rsp+28h] [rbp-40h]
  const wil::ResultException *v15; // [rsp+30h] [rbp-38h] BYREF
  ATL::CAtlException *v16; // [rsp+38h] [rbp-30h] BYREF
  CPassportException *v17; // [rsp+40h] [rbp-28h] BYREF
  CPassportException *v18; // [rsp+48h] [rbp-20h] BYREF
  ATL::CAtlException *v19; // [rsp+50h] [rbp-18h] BYREF
  __int64 v20; // [rsp+58h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+70h] [rbp+8h]
  CWLIDItem *v22; // [rsp+88h] [rbp+20h] BYREF

  v22 = 0;
  v14 = 0;
  v5 = CoInitializeEx(0, 0);
  if ( v5 < 0 )
    HIDWORD(v14) = v5 == -2147417850;
  else
    LODWORD(v14) = 1;
  ((void (__fastcall *)(MsaTracingInternal *, const char *, const char *, unsigned int, const unsigned __int16 *))MsaTracingInternal::TraceFunctionEnter)(
    (MsaTracingInternal *)"\\wlidqueue.cpp",
    "CWLIDQueue::WLIDThreadFunc",
    (const char *)0x221,
    v6,
    v13);
  CAutoRefPtr<CWLIDItem>::Deinit(&v22);
  v22 = this;
  if ( this && *((_QWORD *)this + 7) && !a3 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v21 = ((__int64 (__fastcall *)(CWLIDItem *))CWLIDItem::Execute)(this);
      ((void (__fastcall *)(MsaTracingInternal *, const char *, int))MsaTracingInternal::TraceFunctionExit)(
        (MsaTracingInternal *)"CWLIDQueue::WLIDThreadFunc",
        0,
        v8);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &CPassportException `RTTI Type Descriptor', &v17) )
      {
        v12 = *((_DWORD *)v17 + 2);
        if ( v12 >= 0 )
          v12 = -2147418113;
        v21 = v12;
        __eh34_try_continuation(0, &CPassportException `RTTI Type Descriptor', &loc_18000BB6F);
        goto LABEL_39;
      }
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v16) )
      {
        v11 = *(_DWORD *)v16;
        if ( *(int *)v16 >= 0 )
          v11 = -2147418113;
        v21 = v11;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000BBE9);
        goto LABEL_39;
      }
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v21 = -2147024882;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000BBE7);
        goto LABEL_39;
      }
      if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v13) )
      {
        v10 = (int)v13;
        if ( (int)v13 >= 0 )
          v10 = -2147418113;
        v21 = v10;
        __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_18000BBE5);
        goto LABEL_39;
      }
      if ( __eh34_catch_type(0, &wil::ResultException `RTTI Type Descriptor', &v15) )
      {
        v9 = *((_DWORD *)v15 + 8);
        if ( v9 >= 0 )
          v9 = -2147418113;
        v21 = v9;
        __eh34_try_continuation(0, &wil::ResultException `RTTI Type Descriptor', &loc_18000BBE3);
      }
    }
LABEL_39:
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      CWLIDQueue::_ItemFinished(*((_QWORD *)v22 + 7), &v22, v21);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &CPassportException `RTTI Type Descriptor', &v18) )
      {
        __eh34_try_continuation(2, &CPassportException `RTTI Type Descriptor', &loc_18000BBEB);
        goto LABEL_8;
      }
      if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', &v19) )
      {
        __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000BBED);
        goto LABEL_8;
      }
      if ( __eh34_catch_type(2, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        __eh34_try_continuation(2, &std::bad_alloc `RTTI Type Descriptor', &loc_18000BBEF);
        goto LABEL_8;
      }
      if ( __eh34_catch_type(2, &long `RTTI Type Descriptor', (long *)&v20) )
        __eh34_try_continuation(2, &long `RTTI Type Descriptor', &loc_18000BB8E);
    }
LABEL_8:
    if ( (_DWORD)v14 )
      CoUninitialize();
    CAutoRefPtr<CWLIDItem>::Deinit(&v22);
    return;
  }
  ((void (__fastcall *)(MsaTracingInternal *, const char *, int))MsaTracingInternal::TraceFunctionExit)(
    (MsaTracingInternal *)"CWLIDQueue::WLIDThreadFunc",
    0,
    v7);
  if ( (_DWORD)v14 )
    CoUninitialize();
  CAutoRefPtr<CWLIDItem>::Deinit(&v22);
}

```

## disassembly

```asm
0x18000bac0  mov     rax, rsp
0x18000bac3  mov     [rax+10h], rbx
0x18000bac7  mov     [rax+18h], rsi
0x18000bacb  push    rdi
0x18000bacc  sub     rsp, 60h
0x18000bad0  mov     dil, r8b
0x18000bad3  mov     rbx, rcx
0x18000bad6  mov     qword ptr [rax+20h], 0
0x18000bade  mov     qword ptr [rax-40h], 0
0x18000bae6  xor     edx, edx; dwCoInit
0x18000bae8  xor     ecx, ecx; pvReserved
0x18000baea  call    cs:__imp_CoInitializeEx
0x18000baf0  mov     edx, eax
0x18000baf2  mov     ecx, 1
0x18000baf7  test    eax, eax
0x18000baf9  js      short loc_18000BB01
0x18000bafb  mov     [rsp+68h+var_40], ecx
0x18000baff  jmp     short loc_18000BB10
0x18000bb01  xor     eax, eax
0x18000bb03  cmp     edx, 80010106h
0x18000bb09  cmovz   eax, ecx
0x18000bb0c  mov     [rsp+68h+var_3C], eax
0x18000bb10  lea     rsi, aCwlidqueueWlid_0; "CWLIDQueue::WLIDThreadFunc"
0x18000bb17  mov     [rsp+68h+arg_0], rsi
0x18000bb1c  mov     r8d, 221h; char *
0x18000bb22  mov     rdx, rsi; char *
0x18000bb25  lea     rcx, aWlidqueueCpp; "\\wlidqueue.cpp"
0x18000bb2c  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000bb31  nop
0x18000bb32  lea     rcx, [rsp+68h+arg_18]
0x18000bb3a  call    ?Deinit@?$CAutoRefPtr@VCWLIDItem@@@@IEAAXXZ; CAutoRefPtr<CWLIDItem>::Deinit(void)
0x18000bb3f  mov     [rsp+68h+arg_18], rbx
0x18000bb47  test    rbx, rbx
0x18000bb4a  jz      short loc_18000BBBB
0x18000bb4c  cmp     qword ptr [rbx+38h], 0
0x18000bb51  jz      short loc_18000BBBB
0x18000bb53  test    dil, dil
0x18000bb56  jnz     short loc_18000BBBB
0x18000bb58  mov     rcx, rbx; this
0x18000bb5b  call    ?Execute@CWLIDItem@@QEAAJXZ; CWLIDItem::Execute(void)
0x18000bb60  mov     dword ptr [rsp+68h+arg_0], eax
0x18000bb64  xor     edx, edx; char *
0x18000bb66  mov     rcx, rsi; this
0x18000bb69  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18000bb6e  nop
0x18000bb6f  mov     r8d, dword ptr [rsp+68h+arg_0]
0x18000bb74  lea     rdx, [rsp+68h+arg_18]
0x18000bb7c  mov     rcx, [rsp+68h+arg_18]
0x18000bb84  mov     rcx, [rcx+38h]
0x18000bb88  call    ?_ItemFinished@CWLIDQueue@@AEAAXAEAV?$CAutoRefPtr@VCWLIDItem@@@@J@Z; CWLIDQueue::_ItemFinished(CAutoRefPtr<CWLIDItem> &,long)
0x18000bb8d  nop
0x18000bb8e  cmp     [rsp+68h+var_40], 0
0x18000bb93  jz      short loc_18000BB9C
0x18000bb95  call    cs:__imp_CoUninitialize
0x18000bb9b  nop
0x18000bb9c  lea     rcx, [rsp+68h+arg_18]
0x18000bba4  call    ?Deinit@?$CAutoRefPtr@VCWLIDItem@@@@IEAAXXZ; CAutoRefPtr<CWLIDItem>::Deinit(void)
0x18000bba9  lea     r11, [rsp+68h+var_8]
0x18000bbae  mov     rbx, [r11+18h]
0x18000bbb2  mov     rsi, [r11+20h]
0x18000bbb6  mov     rsp, r11
0x18000bbb9  pop     rdi
0x18000bbba  retn
0x18000bbbb  xor     edx, edx; char *
0x18000bbbd  mov     rcx, rsi; this
0x18000bbc0  call    ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x18000bbc5  nop
0x18000bbc6  cmp     [rsp+68h+var_40], 0
0x18000bbcb  jz      short loc_18000BBD4
0x18000bbcd  call    cs:__imp_CoUninitialize
0x18000bbd3  nop
0x18000bbd4  lea     rcx, [rsp+68h+arg_18]
0x18000bbdc  call    ?Deinit@?$CAutoRefPtr@VCWLIDItem@@@@IEAAXXZ; CAutoRefPtr<CWLIDItem>::Deinit(void)
0x18000bbe1  jmp     short loc_18000BBA9
0x18000bbe3  jmp     short loc_18000BB6F
0x18000bbe5  jmp     short loc_18000BB6F
0x18000bbe7  jmp     short loc_18000BB6F
0x18000bbe9  jmp     short loc_18000BB6F
0x18000bbeb  jmp     short loc_18000BB8E
0x18000bbed  jmp     short loc_18000BB8E
0x18000bbef  jmp     short loc_18000BB8E
```
